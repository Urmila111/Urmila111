import React, { useEffect, useState } from "react";
import Typing from "react-typing-animation";
import { FaLinkedin, FaTwitter, FaFacebook } from "react-icons/fa";
import styles from "./ProfileReadme.module.css"; // CSS module styles (see below)

// Utility function to fetch GitHub user data
async function fetchGitHubStats(username) {
  const res = await fetch(`https://api.github.com/users/${username}/repos`);
  if (!res.ok) return null;
  const repos = await res.json();
  // Calculate total stars, forks etc if needed
  const totalStars = repos.reduce((acc, repo) => acc + repo.stargazers_count, 0);
  return { totalRepos: repos.length, totalStars };
}

const socialLinks = [
  {
    href: "https://www.linkedin.com/in/urmila-basnet/",
    icon: <FaLinkedin />,
    color: "#0077B5",
    label: "LinkedIn",
  },
  {
    href: "https://twitter.com/_urmila_basnet",
    icon: <FaTwitter />,
    color: "#1DA1F2",
    label: "Twitter",
  },
  {
    href: "https://www.facebook.com/urmila.basnet.71",
    icon: <FaFacebook />,
    color: "#1877F2",
    label: "Facebook",
  },
];

export default function ProfileReadme() {
  const [githubStats, setGithubStats] = useState(null);
  const [visitorCount, setVisitorCount] = useState(null);

  useEffect(() => {
    fetchGitHubStats("Urmila111").then(setGithubStats);

    // Example visitor count fetch, replace with your actual API
    // For demo, just simulate visitor count
    setVisitorCount(2543);
  }, []);

  return (
    <div className={styles.container}>

      <div className={styles.typingSection}>
        <a href="https://github.com/Urmila111" target="_blank" rel="noreferrer">
          <Typing speed={60} loop>
            <span>Backend Developer</span>
            <Typing.Delay ms={1000} />
            <Typing.Backspace count={18} />
            <span>Finance & Cybersecurity Enthusiast</span>
            <Typing.Delay ms={1000} />
            <Typing.Backspace count={30} />
            <span>AI | Quant Learner</span>
            <Typing.Delay ms={1000} />
            <Typing.Backspace count={14} />
            <span>Aspiring Financial Engineer</span>
            <Typing.Delay ms={2000} />
            <Typing.Reset />
          </Typing>
        </a>
      </div>

      <div className={styles.visitorCount}>
        <span>👀 Profile Visitors: </span>
        <strong>{visitorCount !== null ? visitorCount.toLocaleString() : "Loading..."}</strong>
      </div>

      <h3 className={styles.welcome}>
        Hello! I&apos;m <a href="https://www.linkedin.com/in/urmila-basnet/" target="_blank" rel="noreferrer">Urmila Basnet</a>, passionate about backend development, cybersecurity, finance, and AI.
      </h3>

      <div className={styles.musicLink}>
        <a href="https://www.youtube.com/watch?v=DXCd7Moy3to&list=RDDXCd7Moy3to&start_radio=1" target="_blank" rel="noreferrer">
          <img src="https://raw.githubusercontent.com/trinib/spotify-github-profile/master/img/default.svg" alt="Music Playlist" width={300} height={130} />
        </a>
      </div>

      <div className={styles.socialIcons}>
        {socialLinks.map(({ href, icon, color, label }) => (
          <a
            href={href}
            key={label}
            target="_blank"
            rel="noreferrer"
            className={styles.socialIcon}
            style={{ backgroundColor: color }}
            aria-label={label}
          >
            {icon}
          </a>
        ))}
      </div>

      <section className={styles.techStack}>
        <h2>🧰 Tech Stack I Work With</h2>
        <img
          src="https://skillicons.dev/icons?i=nodejs,express,mongodb,react,vercel,git,linux,python,typescript,docker,figma,postgresql,tailwind&perline=10"
          alt="Tech stack icons"
        />
      </section>

      <section className={styles.githubStats}>
        <h2>📊 GitHub Stats</h2>
        {githubStats ? (
          <>
            <p>Total Public Repos: <strong>{githubStats.totalRepos}</strong></p>
            <p>Total Stars: <strong>{githubStats.totalStars}</strong></p>
            <img
              src={`https://github-readme-streak-stats.herokuapp.com/?user=Urmila111&theme=radical&border=7F3FBF&background=0D1117`}
              alt="GitHub Streak"
              className={styles.streakImg}
            />
            <img
              src={`https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Urmila111&theme=radical`}
              alt="GitHub Profile Summary"
              className={styles.summaryImg}
            />
          </>
        ) : (
          <p>Loading stats...</p>
        )}
      </section>

      <section className={styles.languageStats}>
        <img
          src="https://denvercoder1-github-readme-stats.vercel.app/api/top-langs/?username=Urmila111&langs_count=8&layout=compact&theme=react&border_color=7F3FBF&bg_color=0D1117&title_color=F85D7F&icon_color=F8D866"
          alt="Top Languages"
          className={styles.langImg}
        />
      </section>

      <section className={styles.activityGraph}>
        <img
          src="https://github-readme-activity-graph.vercel.app/graph?username=Urmila111&custom_title=Urmila%20Basnet%20GitHub%20Activity&bg_color=0D1117&color=7F3FBF&line=7F3FBF&point=7F3FBF&area_color=FFFFFF&title_color=FFFFFF&area=true"
          alt="GitHub Activity Graph"
          className={styles.activityImg}
        />
      </section>
    </div>
  );
}


  
