# gradiantColor

// ViewDidLoad

self.ViewLogin.applyGradient(colors: [UIColor(red: 91.0/255.0, green: 194.0/255.0, blue: 188.0/255.0, alpha: 1.0).cgColor,UIColor(red: 158.0/255.0, green: 219.0/255.0, blue: 215.0/255.0, alpha: 0.72).cgColor])

// outside class

  extension UIView {
    func applyGradient(colors: [CGColor]) {
        self.backgroundColor = nil
        self.layoutIfNeeded()
        let gradientLayer = CAGradientLayer()
        gradientLayer.colors = colors
        gradientLayer.startPoint = CGPoint(x: 0, y: 0)
        gradientLayer.endPoint = CGPoint(x: 1, y: 0)
        gradientLayer.frame = self.bounds
        gradientLayer.cornerRadius = self.frame.height/2

        gradientLayer.shadowColor = UIColor.darkGray.cgColor
        gradientLayer.shadowOffset = CGSize(width: 2.5, height: 2.5)
        gradientLayer.shadowRadius = 5.0
        gradientLayer.shadowOpacity = 0.3
        gradientLayer.masksToBounds = false

        self.layer.insertSublayer(gradientLayer, at: 0)

    }
}
