# ComputeService::Net::UpdateInterface(ulong,uint,bool,ulong)

- ea: `0x1400b2508`
- end: `0x1400b26a2`
- name: `?UpdateInterface@Net@ComputeService@@YAXKI_NK@Z`
- size: `410`
- prototype: `void(ComputeService::Net *__hidden this, unsigned int, unsigned int, bool, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400ad3a0`

## callees

- `0x140005360`
- `0x140006098`
- `0x1400341ac`
- `0x1400b1b90`
- `0x1400b2508`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400b25c3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400b25c3`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b2562`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b2562`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x1400b2597`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x1400b2597`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x1400b260f`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x1400b260f`
- `IPHLPAPI!GetIpInterfaceEntry` at `0x1400b25af`
- `IPHLPAPI!GetIpInterfaceEntry` at `0x1400b25af`

## string_xrefs

- `0x1400b2666`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b267b`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b2690`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Net::UpdateInterface(
        ComputeService::Net *this,
        NET_IF_COMPARTMENT_ID a2,
        char a3,
        int a4)
{
  NET_IFINDEX v7; // r13d
  unsigned int v8; // eax
  int *v9; // rbx
  ADDRESS_FAMILY v10; // si
  unsigned int v11; // r14d
  unsigned int IpInterfaceEntry; // edi
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // [rsp+20h] [rbp-A9h] BYREF
  int v16; // [rsp+24h] [rbp-A5h] BYREF
  char v17; // [rsp+28h] [rbp-A1h] BYREF
  _MIB_IPINTERFACE_ROW Row; // [rsp+30h] [rbp-99h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v7 = (unsigned int)this;
  memset_0(&Row, 0, sizeof(Row));
  v16 = 1507330;
  v8 = SetCurrentThreadCompartmentId(a2);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v8,
      v15);
  *(_WORD *)((char *)&v15 + 1) = 258;
  v9 = &v16;
  do
  {
    v10 = *(_WORD *)v9;
    if ( *(_WORD *)v9 != 23 || a3 )
    {
      InitializeIpInterfaceEntry(&Row);
      Row.InterfaceIndex = v7;
      Row.Family = v10;
      v11 = 0;
      do
      {
        IpInterfaceEntry = GetIpInterfaceEntry(&Row);
        if ( IpInterfaceEntry != 1168 )
          break;
        Sleep(0xFu);
        v13 = v11++;
      }
      while ( v13 < 0x3C );
      if ( IpInterfaceEntry )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x286,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
          (const char *)IpInterfaceEntry,
          v15);
      if ( a3 )
      {
        Row.UseAutomaticMetric = 0;
        Row.Metric = 500;
      }
      if ( v10 == 2 && a4 )
        Row.NlMtu -= a4;
      Row.SitePrefixLength = 0;
      v14 = SetIpInterfaceEntry(&Row);
      if ( v14 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x297,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
          (const char *)v14,
          v15);
    }
    v9 = (int *)((char *)v9 + 2);
  }
  while ( v9 != (int *)&v17 );
  wil::details::ScopeExitFnGuard__lambda_d6d2541099fc7e2a91d28a9f5de2928d___::operator()(&v15);
}

```

## disassembly

```asm
0x1400b2508  mov     [rsp-8+arg_10], rbx
0x1400b250d  push    rbp
0x1400b250e  push    rsi
0x1400b250f  push    rdi
0x1400b2510  push    r12
0x1400b2512  push    r13
0x1400b2514  push    r14
0x1400b2516  push    r15
0x1400b2518  lea     rbp, [rsp-27h]
0x1400b251d  sub     rsp, 0F0h
0x1400b2524  mov     rax, cs:__security_cookie
0x1400b252b  xor     rax, rsp
0x1400b252e  mov     [rbp+57h+var_40], rax
0x1400b2532  mov     r15d, r9d
0x1400b2535  mov     r12b, r8b
0x1400b2538  mov     ebx, edx
0x1400b253a  mov     r13d, ecx
0x1400b253d  xor     edx, edx; Val
0x1400b253f  mov     r8d, 0A8h; Size
0x1400b2545  lea     rcx, [rsp+120h+Row]; void *
0x1400b254a  call    memset_0
0x1400b254f  mov     edi, 2
0x1400b2554  mov     [rsp+120h+var_FC], 170002h
0x1400b255c  lea     r14d, [rdi+15h]
0x1400b2560  mov     ecx, ebx; CompartmentId
0x1400b2562  call    cs:__imp_SetCurrentThreadCompartmentId
0x1400b2568  mov     rcx, [rbp+5Fh]; this
0x1400b256c  test    eax, eax
0x1400b256e  jnz     loc_1400B268D
0x1400b2574  mov     [rsp+120h+var_FF], 102h
0x1400b257b  lea     rbx, [rsp+120h+var_FC]
0x1400b2580  movzx   esi, word ptr [rbx]
0x1400b2583  cmp     si, r14w
0x1400b2587  jnz     short loc_1400B2592
0x1400b2589  test    r12b, r12b
0x1400b258c  jz      loc_1400B2621
0x1400b2592  lea     rcx, [rsp+120h+Row]; Row
0x1400b2597  call    cs:__imp_InitializeIpInterfaceEntry
0x1400b259d  mov     [rsp+120h+Row.InterfaceIndex], r13d
0x1400b25a2  mov     [rsp+120h+Row.Family], si
0x1400b25a7  xor     r14d, r14d
0x1400b25aa  lea     rcx, [rsp+120h+Row]; Row
0x1400b25af  call    cs:__imp_GetIpInterfaceEntry
0x1400b25b5  mov     edi, eax
0x1400b25b7  cmp     eax, 490h
0x1400b25bc  jnz     short loc_1400B25D4
0x1400b25be  mov     ecx, 0Fh; dwMilliseconds
0x1400b25c3  call    cs:__imp_Sleep
0x1400b25c9  mov     ecx, r14d
0x1400b25cc  inc     r14d
0x1400b25cf  cmp     ecx, 3Ch ; '<'
0x1400b25d2  jb      short loc_1400B25AA
0x1400b25d4  mov     rcx, [rbp+5Fh]; this
0x1400b25d8  test    edi, edi
0x1400b25da  jnz     loc_1400B2678
0x1400b25e0  test    r12b, r12b
0x1400b25e3  jz      short loc_1400B25F0
0x1400b25e5  mov     [rbp+57h+Row.UseAutomaticMetric], dil
0x1400b25e9  mov     [rbp+57h+Row.Metric], 1F4h
0x1400b25f0  mov     edi, 2
0x1400b25f5  cmp     si, di
0x1400b25f8  jnz     short loc_1400B2603
0x1400b25fa  test    r15d, r15d
0x1400b25fd  jz      short loc_1400B2603
0x1400b25ff  sub     [rbp+57h+Row.NlMtu], r15d
0x1400b2603  mov     [rbp+57h+Row.SitePrefixLength], 0
0x1400b260a  lea     rcx, [rsp+120h+Row]; Row
0x1400b260f  call    cs:__imp_SetIpInterfaceEntry
0x1400b2615  mov     rcx, [rbp+5Fh]; this
0x1400b2619  test    eax, eax
0x1400b261b  jnz     short loc_1400B2663
0x1400b261d  lea     r14d, [rax+17h]
0x1400b2621  add     rbx, rdi
0x1400b2624  lea     rax, [rsp+120h+var_F8]
0x1400b2629  cmp     rbx, rax
0x1400b262c  jnz     loc_1400B2580
0x1400b2632  lea     rcx, [rsp+120h+var_100]
0x1400b2637  call    wil__details__ScopeExitFnGuard__lambda_d6d2541099fc7e2a91d28a9f5de2928d_____operator__
0x1400b263c  mov     rcx, [rbp+57h+var_40]
0x1400b2640  xor     rcx, rsp; StackCookie
0x1400b2643  call    __security_check_cookie
0x1400b2648  mov     rbx, [rsp+120h+arg_10]
0x1400b2650  add     rsp, 0F0h
0x1400b2657  pop     r15
0x1400b2659  pop     r14
0x1400b265b  pop     r13
0x1400b265d  pop     r12
0x1400b265f  pop     rdi
0x1400b2660  pop     rsi
0x1400b2661  pop     rbp
0x1400b2662  retn
0x1400b2663  mov     r9d, eax; char *
0x1400b2666  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b266d  mov     edx, 297h; void *
0x1400b2672  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b2678  mov     r9d, edi; char *
0x1400b267b  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b2682  mov     edx, 286h; void *
0x1400b2687  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b268d  mov     r9d, eax; char *
0x1400b2690  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b2697  mov     edx, 268h; void *
0x1400b269c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
