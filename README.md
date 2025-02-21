import React from "react";
import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { FaYoutube, FaEnvelope, FaHome, FaInfoCircle, FaVideo, FaTrophy } from "react-icons/fa";

"homepage": "https://yourusername.github.io/your-repo",
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
};

const logo = "/snapedit_1725361109010.jpeg";

const Home = () => (
  <div className="p-6 text-center">
    <img src={logo} alt="YouTube Logo" className="mx-auto w-32 h-32 rounded-full" />
    <h1 className="text-4xl font-bold mt-4">Welcome to My YouTube Journey</h1>
    <p className="mt-4 text-lg">Follow my journey and explore my content.</p>
    <iframe
      className="mt-6 rounded-xl shadow-lg"
      width="560"
      height="315"
      src="https://www.youtube.com/embed/JD6KRU1lxKk"
      title="YouTube Video"
      allowFullScreen
    ></iframe>
  </div>
);

const About = () => (
  <div className="p-6 text-center">
    <h1 className="text-3xl font-bold">About Me</h1>
    <p className="mt-4 text-lg">I create engaging content on YouTube, covering [your niche].</p>
  </div>
);

const Portfolio = () => (
  <div className="p-6 grid grid-cols-1 md:grid-cols-3 gap-6">
    <Card>
      <CardContent>
        <iframe width="100%" height="200" src="https://www.youtube.com/embed/JD6KRU1lxKk" allowFullScreen></iframe>
        <p className="mt-2 text-center">My Latest Video</p>
      </CardContent>
    </Card>
  </div>
);

const Tournaments = () => (
  <div className="p-6 text-center">
    <h1 className="text-3xl font-bold">Tournaments</h1>
    <p className="mt-4 text-lg">Check out my past and upcoming tournaments.</p>
    <div className="mt-6 grid grid-cols-1 md:grid-cols-2 gap-6">
      <Card>
        <CardContent>
          <h2 className="text-xl font-bold">Upcoming Tournament</h2>
          <p>Tournament: SINGH GAMING TOURNAMENT SUMMER SHOWDOWN 2025</p>
          <p>Game: GARENA FREE FIRE MAX</p>
          <p>Winner: TBD</p>
          <p>1ST RUNNER UP: TBD</p>
          <p>2ND RUNNER UP: TBD</p>
          <p>Prize Pool: 50,000 INR</p>
        </CardContent>
      </Card>
      <Card>
        <CardContent>
          <h2 className="text-xl font-bold">Recent Tournament</h2>
          <p>Tournament: SINGH GAMING TOURNAMENT SPRING 2025</p>
          <p>Game: GARENA FREE FIRE MAX</p>
          <p>Winner: ASSASSIN'S ARMY</p>
          <p>1ST RUNNER UP: RTP ESPORTS</p>
          <p>2ND RUNNER UP: TEAM ELITE</p>
          <p>Prize Pool: 25,000 INR</p>
        </CardContent>
      </Card>
      <Card>
        <CardContent>
          <h2 className="text-xl font-bold">Past Tournament</h2>
          <p>Tournament: SINGH GAMING TOURNAMENT WINTER 2024</p>
          <p>Game: GARENA FREE FIRE MAX</p>
          <p>Winner: AGENT GAMING</p>
          <p>1ST RUNNER UP: BABLU GAMING</p>
          <p>2ND RUNNER UP: FACT STORAGE</p>
          <p>Prize Pool: 15,000 INR</p>
        </CardContent>
      </Card>
    </div>
  </div>
);

const Contact = () => (
  <div className="p-6 text-center">
    <h1 className="text-3xl font-bold">Contact Me</h1>
    <p className="mt-4">Reach out via email or connect on social media.</p>
    <div className="mt-4 flex justify-center gap-4">
      <Button variant="outline" asChild>
        <a href="mailto:your.email@example.com"><FaEnvelope /> Email</a>
      </Button>
      <Button variant="outline" asChild>
        <a href="https://www.youtube.com/@thesinghgaming"><FaYoutube /> YouTube</a>
      </Button>
    </div>
  </div>
);

const App = () => {
  return (
    <Router>
      <div className="min-h-screen flex flex-col">
        <nav className="p-4 bg-gray-900 text-white flex justify-center gap-6">
          <Link to="/" className="flex items-center gap-1"><FaHome /> Home</Link>
          <Link to="/about" className="flex items-center gap-1"><FaInfoCircle /> About</Link>
          <Link to="/portfolio" className="flex items-center gap-1"><FaVideo /> Portfolio</Link>
          <Link to="/tournaments" className="flex items-center gap-1"><FaTrophy /> Tournaments</Link>
          <Link to="/contact" className="flex items-center gap-1"><FaEnvelope /> Contact</Link>
        </nav>
        <div className="flex-grow">
          <Routes>
            <Route path="/" element={<Home />} />
            <Route path="/about" element={<About />} />
            <Route path="/portfolio" element={<Portfolio />} />
            <Route path="/tournaments" element={<Tournaments />} />
            <Route path="/contact" element={<Contact />} />
          </Routes>
        </div>
      </div>
    </Router>
  );
};

export default App;
