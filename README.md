// App.jsx
import { useEffect } from "react";
import { motion } from "framer-motion";
import { Button } from "@/components/ui/button";
import { Phone, MapPin } from "lucide-react";

const appliances = [
  {
    title: "Washer & Dryer",
    img: "/images/washer-dryer.jpg",
    desc: "Fast repair of washing machines and dryers."
  },
  {
    title: "Dishwasher",
    img: "/images/dishwasher.jpg",
    desc: "Fix leaks, no cleaning, and draining issues."
  },
  {
    title: "Refrigerator",
    img: "/images/refrigerator.jpg",
    desc: "Cooling problems, ice maker repairs, and more."
  },
  {
    title: "Microwave",
    img: "/images/microwave.jpg",
    desc: "We handle no heating, sparking, and more."
  },
  {
    title: "Oven",
    img: "/images/oven.jpg",
    desc: "Accurate temperature repairs and more."
  },
  {
    title: "Stove",
    img: "/images/stove.jpg",
    desc: "Ignition issues, broken burners, and more."
  }
];

export default function App() {
  useEffect(() => {
    document.title = "Pacific Repair Solutions – Appliance Repair Sacramento";
  }, []);

  return (
    <main className="min-h-screen bg-white text-gray-800">
      <header className="text-center py-10 bg-gradient-to-r from-blue-100 to-blue-50">
        <h1 className="text-4xl font-bold mb-2">Pacific Repair Solutions</h1>
        <p className="text-xl text-gray-600">Trusted Appliance Repair in Sacramento</p>
        <Button className="mt-4 gap-2 text-lg">
          <Phone className="w-5 h-5" /> Call Now: (916) 836-7616
        </Button>
      </header>

      <section className="max-w-6xl mx-auto px-4 py-12 grid gap-8 grid-cols-1 md:grid-cols-3">
        {appliances.map(({ title, img, desc }, i) => (
          <motion.div
            key={i}
            whileHover={{ scale: 1.02 }}
            className="rounded-2xl overflow-hidden shadow-lg bg-white border"
          >
            <img src={img} alt={title} className="w-full h-48 object-cover" />
            <div className="p-4">
              <h3 className="text-xl font-semibold mb-1">{title}</h3>
              <p className="text-gray-500 text-sm">{desc}</p>
            </div>
          </motion.div>
        ))}
      </section>

      <section className="bg-gray-50 py-10 text-center">
        <h2 className="text-2xl font-bold mb-4">Book a Service</h2>
        <form className="max-w-md mx-auto space-y-4">
          <input type="text" placeholder="Your Name" className="w-full border p-2 rounded" />
          <input type="email" placeholder="Email" className="w-full border p-2 rounded" />
          <input type="text" placeholder="Phone" className="w-full border p-2 rounded" />
          <textarea placeholder="Issue Description" className="w-full border p-2 rounded" rows="4" />
          <Button className="w-full">Submit</Button>
        </form>
      </section>

      <section className="max-w-3xl mx-auto px-4 py-10">
        <h2 className="text-2xl font-bold mb-4 text-center">Customer Reviews</h2>
        <form className="space-y-4">
          <textarea placeholder="Write your comment here..." className="w-full border p-2 rounded" rows="3" />
          <Button>Post Comment</Button>
        </form>
      </section>

      <section className="bg-blue-50 py-6 text-center">
        <h3 className="text-lg font-semibold mb-2">Our Location</h3>
        <div className="flex justify-center">
          <MapPin className="w-5 h-5 mr-1" />
          <span>Sacramento, CA 95814</span>
        </div>
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3133.245193716854!2d-121.49440068449035!3d38.581571179612224!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8085299ed3f11111%3A0xcccccccccccccccc!2sSacramento%2C%20CA!5e0!3m2!1sen!2sus!4v1686242400000"
          width="100%"
          height="300"
          style={{ border: 0 }}
          allowFullScreen=""
          loading="lazy"
          title="Pacific Repair Solutions Location"
        ></iframe>
      </section>

      <footer className="text-center text-sm text-gray-500 py-6">
        &copy; {new Date().getFullYear()} Pacific Repair Solutions LLC. All rights reserved.
      </footer>
    </main>
  );
}
