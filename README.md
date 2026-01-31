def check_tackle(defender, ball_carrier):
    # Calculate momentum for both players
    defender_momentum = defender.mass * defender.velocity
    carrier_momentum = ball_carrier.mass * ball_carrier.velocity

    # If they collide
    if defender.rect.colliderect(ball_carrier.rect):
        if defender_momentum > carrier_momentum:
            ball_carrier.is_down = True
            print("Tackle Successful!")
        else:
            # The "Truck" animation logic
            defender.stumbled = True
            print("Defender got trucked!")
