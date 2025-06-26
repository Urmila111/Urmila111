import React, { useEffect, useState } from "react";
import Typing from "react-typing-animation";
import { FaLinkedin, FaTwitter, FaFacebook } from "react-icons/fa";

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
  const [visitorCount, setVisitorCount] = useState(null);

  useEffect(() => {
    setVisitorCount(2543); // Simulate visitor count
  }, []);

  // Inline styles
  const containerStyle = {
    maxWidth: 900,
    margin: "2rem auto",
    padding: "1rem",
    backgroundColor: "#0d1117",
    color: "#c9d1d9",
    fontFamily: "'Fira Code', monospace",
    borderRadius: 12,
    boxShadow: "0 0 15px #7f3fbf88",
    textAlign: "center",
  };

  const socialIconStyle = (color) => ({
    width: 44,
    height: 44,
    color: "white",
    fontSize: 26,
    borderRadius: "50%",
    display: "inline-flex",
    alignItems: "center",
    justifyContent: "center",
    backgroundColor: color,
    margin: "0 8px",
    cursor: "pointer",
    transition: "transform 0.25s ease, box-shadow 0.25s ease",
  });

  return (
    <div style={containerStyle}>
      <div style={{ fontSize: 24, color: "#f700ff", fontWeight: 600, marginBottom: 16 }}>
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
      </div>

      <div style={{ fontWeight: 600, fontSize: 18, color: "#f700ff", marginBottom: 20 }}>
        👀 Profile Visitors: {visitorCount !== null ? visitorCount.toLocaleString() : "Loading..."}
      </div>

      <h3>
        Hello! I&apos;m{" "}
        <a
          href="https://www.linkedin.com/in/urmila-basnet/"
          target="_blank"
          rel="noreferrer"
          style={{ color: "#f700ff", textDecoration: "none" }}
        >
          Urmila Basnet
        </a>
        , passionate about backend development, cybersecurity, finance, and AI.
      </h3>

      <div style={{ margin: "2rem 0" }}>
        <a
          href="https://www.youtube.com/watch?v=DXCd7Moy3to&list=RDDXCd7Moy3to&start_radio=1"
          target="_blank"
          rel="noreferrer"
        >
          <img
            src="https://raw.githubusercontent.com/trinib/spotify-github-profile/master/img/default.svg"
            alt="Music Playlist"
            width={300}
            height={130}
          />
        </a>
      </div>

      <div>
        {socialLinks.map(({ href, icon, color, label }) => (
          <a
            key={label}
            href={href}
            target="_blank"
            rel="noreferrer"
            aria-label={label}
            style={socialIconStyle(color)}
            onMouseOver={(e) => {
              e.currentTarget.style.transform = "scale(1.15)";
              e.currentTarget.style.boxShadow = "0 0 10px #f700ffaa";
            }}
            onMouseOut={(e) => {
              e.currentTarget.style.transform = "scale(1)";
              e.currentTarget.style.boxShadow = "none";
            }}
          >
            {icon}
          </a>
        ))}
      </div>

      <section style={{ marginTop: 40 }}>
        <h2>🧰 Tech Stack I Work With</h2>
        <img
          src="https://skillicons.dev/icons?i=nodejs,express,mongodb,react,vercel,git,linux,python,typescript,docker,figma,postgresql,tailwind&perline=10"
          alt="Tech stack icons"
          style={{ maxWidth: "100%", marginTop: 16 }}
        />
      </section>

      <section style={{ marginTop: 40 }}>
        <h2>📊 GitHub Stats</h2>
        <img
          src="https://github-readme-streak-stats.herokuapp.com/?user=Urmila111&theme=radical&border=7F3FBF&background=0D1117"
          alt="GitHub Streak"
          style={{ maxWidth: "100%", borderRadius: 10, marginTop: 16 }}
        />
        <img
          src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Urmila111&theme=radical"
          alt="GitHub Profile Summary"
          style={{ maxWidth: "100%", borderRadius: 10, marginTop: 16 }}
        />
      </section>

      <section style={{ marginTop: 40 }}>
        <img
          src="https://denvercoder1-github-readme-stats.vercel.app/api/top-langs/?username=Urmila111&langs_count=8&layout=compact&theme=react&border_color=7F3FBF&bg_color=0D1117&title_color=F85D7F&icon_color=F8D866"
          alt="Top Languages"
          style={{ maxWidth: "100%", borderRadius: 10, marginTop: 16 }}
        />
      </section>

      <section style={{ marginTop: 40, marginBottom: 40 }}>
        <img
          src="https://github-readme-activity-graph.vercel.app/graph?username=Urmila111&custom_title=Urmila%20Basnet%20GitHub%20Activity&bg_color=0D1117&color=7F3FBF&line=7F3FBF&point=7F3FBF&area_color=FFFFFF&title_color=FFFFFF&area=true"
          alt="GitHub Activity Graph"
          style={{ maxWidth: "100%", borderRadius: 10, marginTop: 16 }}
        />
      </section>
    </div>
  );
}
