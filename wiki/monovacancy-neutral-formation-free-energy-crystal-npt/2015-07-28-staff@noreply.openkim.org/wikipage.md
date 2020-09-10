This property is intended to quantify the free energy of formation of a monovacancy in an infinite host crystal at a specific stress state and non-zero temperature.  If the energy of formation at zero temperature is desired, please use either the 'monovacancy-neutral-relaxed-formation-potential-energy-crystal-npt' or 'monovacancy-neutral-unrelaxed-formation-potential-energy-crystal-npt' properties as appropriate.

The host crystal may be monoatomic or multiatomic and may have any lattice geometry which is in a state of thermodynamic equilibrium at the given temperature and stress state.  This geometry is defined in terms of 1) three independent lengths and three independent angles which describe the lattice formed by the time-averaged positions of the constituent atoms and 2) the unique Wyckoff positions and corresponding space group.  The single atom which is removed from the host crystal to form the monovacancy is specified by its position in the list of Wyckoff sites which is provided.  This also indicates its species and coordinates since the order of the elements in 'host-wyckoff-multiplicity-and-letter', 'host-wyckoff-species', and 'host-wyckoff-coordinates' all correspond to one another.

The quantity contained in the 'formation-free-energy' key is the formation free energy of a vacancy of designated species (denoted in this documentation as "species $$v$$") in the host crystal plus the chemical potential of a monoatomic reference "reservoir" crystal of the same species as the atom being removed to introduce the vacancy.  The reservoir crystal is also an infinite, periodic structure and may be at a stress state and non-zero temperature which possibly differ from that of the host crystal so long as it is in thermodynamic equilibrium.  The expression for the free energy of formation is then

$$E^f_v = E_{\mathrm{vac},v}(T_\mathrm{host},\sigma_\mathrm{host}) - E_\mathrm{ideal}(T_\mathrm{host},\sigma_\mathrm{host}) + \mu_v(T_\mathrm{res},\sigma_\mathrm{res})$$

where $$E_{\mathrm{vac},v}$$ is the total Gibbs free energy of the host crystal with the vacancy of species $$v$$ at temperature $$T_\mathrm{host}$$ and stress state $$\sigma_\mathrm{host}$$, $$E_\mathrm{ideal}$$ is the total Gibbs free energy of the host crystal before the vacancy is introduced, and $$\mu_v$$ is the Gibbs free energy per atom of the reservoir crystal composed of species type $$v$$.  Notionally, the energy of formation reported in this property can thus be understood as the difference between the free energy of the host crystal if a specific atom is removed from it and the free energy of the reservoir crystal if that atom was used to fill an on-lattice vacancy in it.

In the case where the host crystal is monoatomic, the chemical potential is usually removed from consideration by taking the reservoir crystal to be of the same lattice geometry as the host crystal at the same temperature and stress state.  As an example, suppose we were to compute the formation energy of a monovacancy in bcc Al at temperature $$T$$ and stress state $$\sigma$$, which we model with a periodic cell of 128 atoms.  If the reservoir crystal is chosen as aforementioned, then the chemical potential $$\mu$$ is equal to the Gibbs free energy per atom of the ideal host crystal and we get

$$E^f = E_\mathrm{vac}(T,\sigma) - E_\mathrm{ideal}(T,\sigma) + \mu(T,\sigma)$$

where $$E_\mathrm{vac}(T,\sigma)$$ is the total Gibbs free energy of the 127-atom system after the vacancy atom is removed, $$E_\mathrm{ideal}$$ is the total Gibbs free energy of the 128-atom system before the vacancy atom is removed, and $$\mu(T,\sigma)$$ is the cohesive free energy per atom.  Thus, we may write $$\mu(T,\sigma) = E_\mathrm{ideal}(T,\sigma)/128$$, and

$$
\begin{align*}
E^f = & E_\mathrm{vac}(T,\sigma) - E_\mathrm{ideal}(T,\sigma) + E_\mathrm{ideal}(T,\sigma)/128 \\
      = & E_\mathrm{vac}(T,\sigma) - 127*E_\mathrm{ideal}(T,\sigma)/128
\end{align*}
$$

However, when the host crystal is not monoatomic or the reservoir crystal is chosen to be different from the host crystal, either in its geometry or thermodynamic state, it is essential to retain the chemical potential term.

References:
[1] T. Maeda, T. Wada.  *J. Phys. Chem. Solids* **66** (2005) 1924-1927.
[2] T. Maeda, S. Nakamura, T. Wada. *Jpn. J. Appl. Phys.* **50** (2011) 04DP07.
[3] M. Posselt, F. Gao, W.J. Weber, V. Belko. *J. Phys.: Condens. Matter* **16** (2004) 1307.
[4] S. Zhang, J. Northup. *Phys. Rev. Lett.* **67**, No. 17 (1991) 2339.
