# TetheringService::UpdatePeerListWorker(void)

- ea: `0x180020f4c`
- end: `0x18002136c`
- name: `?UpdatePeerListWorker@TetheringService@@AEAAXXZ`
- size: `1056`
- prototype: `void __fastcall(TetheringService *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180015430`
- `0x180021380`

## callees

- `0x180002590`
- `0x180003070`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d9dc`
- `0x18001c184`
- `0x180020f4c`
- `0x180029c10`
- `0x1800315d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800211dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800211dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021010`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021010`
- `ntdll!RtlIpv4AddressToStringW` at `0x18002108c`
- `ntdll!RtlIpv4AddressToStringW` at `0x18002108c`
- `IpNatHlpClient!IpNatHlpGetConnectedDevices` at `0x180020fc8`
- `IpNatHlpClient!IpNatHlpGetConnectedDevices` at `0x180020fc8`
- `IpNatHlpClient!IpNatHlpFree` at `0x180021202`
- `IpNatHlpClient!IpNatHlpFree` at `0x180021202`

## pseudocode

```c
void __fastcall TetheringService::UpdatePeerListWorker(struct _RTL_CRITICAL_SECTION *this)
{
  char v2; // bl
  int ConnectedDevices; // eax
  TetheringServiceTelemetry *v4; // rcx
  PRTL_CRITICAL_SECTION_DEBUG i; // rbx
  unsigned int v6; // ecx
  __int64 v7; // rdi
  __int64 v8; // rsi
  int v9; // eax
  size_t v10; // r8
  const wchar_t *v11; // rcx
  int v12; // r15d
  char v13; // di
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  rsize_t v16; // r9
  char v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  struct in_addr Addr; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[220]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR S[48]; // [rsp+120h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v2 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  ConnectedDevices = IpNatHlpGetConnectedDevices(&v18, &v19);
  if ( ConnectedDevices < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        234,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        (unsigned int)ConnectedDevices);
LABEL_38:
      v4 = WPP_GLOBAL_Control;
    }
    goto LABEL_39;
  }
  EnterCriticalSection(this + 34);
  for ( i = this[35].DebugInfo; ; i = *(PRTL_CRITICAL_SECTION_DEBUG *)&i[4].Flags )
  {
    if ( !i )
    {
      LeaveCriticalSection(this + 34);
      v2 = v17;
      goto LABEL_38;
    }
    v6 = 0;
    if ( v18 )
      break;
LABEL_35:
    ;
  }
  while ( 1 )
  {
    v7 = v19;
    v8 = 140LL * v6;
    if ( *(_DWORD *)(v8 + v19 + 132) == *(_DWORD *)&i->Type
      && *(_WORD *)(v8 + v19 + 136) == *(&i->CreatorBackTraceIndex + 1) )
    {
      break;
    }
    if ( ++v6 >= v18 )
      goto LABEL_35;
  }
  memset_0(S, 0, 0x5Cu);
  Addr = 0;
  Addr = *(struct in_addr *)(v8 + v7 + 128);
  if ( RtlIpv4AddressToStringW(&Addr, S) )
  {
    v9 = wcsncmp_0(S, (const wchar_t *)&i->CreatorBackTraceIndex + 2, 0x2Eu);
    v10 = -1;
    v11 = (const wchar_t *)(v8 + v19);
    v12 = v9;
    do
      ++v10;
    while ( v11[v10] );
    if ( !wcsncmp_0(v11, &i[2].CreatorBackTraceIndex, v10)
      || (v13 = 1, wcsncmp_0(L"Unknown", &i[2].CreatorBackTraceIndex, 0)) )
    {
      v13 = 0;
    }
    if ( BYTE2(i[4].EntryCount) )
    {
      if ( v12 )
      {
LABEL_24:
        if ( o_wmemcpy_s_0(&i->CreatorBackTraceIndex + 2, 0x2Eu, S, 0x2Eu) )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_65;
          }
          v14 = 236;
          goto LABEL_64;
        }
LABEL_28:
        if ( !v13 )
          goto LABEL_68;
        v15 = (const wchar_t *)(v8 + v19);
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        if ( o_wmemcpy_s_0(&i[2].CreatorBackTraceIndex, 0x40u, v15, v16) )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_65;
          }
          v14 = 237;
        }
        else
        {
LABEL_68:
          if ( i[2].CreatorBackTraceIndex || !o_wmemcpy_s_0(&i[2].CreatorBackTraceIndex, 0x40u, L"Unknown", 7u) )
          {
            BYTE2(i[4].EntryCount) = 1;
            v17 = 1;
            goto LABEL_35;
          }
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_65;
          }
          v14 = 238;
        }
LABEL_64:
        WPP_SF_(*((_QWORD *)v4 + 2), v14, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
        v4 = WPP_GLOBAL_Control;
        goto LABEL_65;
      }
      if ( !v13 )
        goto LABEL_35;
    }
    if ( !v12 )
      goto LABEL_28;
    goto LABEL_24;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 235;
    goto LABEL_64;
  }
LABEL_65:
  v2 = v17;
LABEL_39:
  if ( v19 )
  {
    IpNatHlpFree(v19);
    v4 = WPP_GLOBAL_Control;
    v19 = 0;
  }
  if ( v2 )
  {
    if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v4 + 2), 239, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    memset_0(v22, 0, 0xD0u);
    v21 = 3;
    TetheringService::SendNotification((TetheringService *)this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v21);
    if ( !IsMobile() )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      CSebHelper::PublishWnfEvent(&this[32].LockCount, 12);
    }
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v4 + 2), 241, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
}

```

## disassembly

```asm
0x180020f4c  push    rbp
0x180020f4e  push    rbx
0x180020f4f  push    rsi
0x180020f50  push    rdi
0x180020f51  push    r12
0x180020f53  push    r13
0x180020f55  push    r14
0x180020f57  push    r15
0x180020f59  lea     rbp, [rsp-98h]
0x180020f61  sub     rsp, 198h
0x180020f68  mov     rax, cs:__security_cookie
0x180020f6f  xor     rax, rsp
0x180020f72  mov     [rbp+0D0h+var_50], rax
0x180020f79  mov     r13, rcx
0x180020f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f83  lea     r14, WPP_GLOBAL_Control
0x180020f8a  cmp     rcx, r14
0x180020f8d  jz      short loc_180020FAA
0x180020f8f  test    byte ptr [rcx+1Ch], 8
0x180020f93  jz      short loc_180020FAA
0x180020f95  mov     rcx, [rcx+10h]
0x180020f99  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020fa0  mov     edx, 0E9h
0x180020fa5  call    WPP_SF_
0x180020faa  xor     r15d, r15d
0x180020fad  lea     rdx, [rsp+1D0h+var_1A8]
0x180020fb2  mov     bl, r15b
0x180020fb5  mov     [rsp+1D0h+var_1AC], r15d
0x180020fba  lea     rcx, [rsp+1D0h+var_1AC]
0x180020fbf  mov     [rsp+1D0h+var_1B0], bl
0x180020fc3  mov     [rsp+1D0h+var_1A8], r15
0x180020fc8  call    cs:__imp_IpNatHlpGetConnectedDevices
0x180020fce  test    eax, eax
0x180020fd0  jns     short loc_180021009
0x180020fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fd9  cmp     rcx, r14
0x180020fdc  jz      loc_1800211EE
0x180020fe2  test    byte ptr [rcx+1Ch], 1
0x180020fe6  jz      loc_1800211EE
0x180020fec  mov     rcx, [rcx+10h]
0x180020ff0  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020ff7  mov     edx, 0EAh
0x180020ffc  mov     r9d, eax
0x180020fff  call    WPP_SF_d
0x180021004  jmp     loc_1800211E7
0x180021009  lea     rcx, [r13+550h]; lpCriticalSection
0x180021010  call    cs:__imp_EnterCriticalSection
0x180021016  mov     rbx, [r13+578h]
0x18002101d  jmp     loc_1800211CD
0x180021022  mov     ecx, r15d
0x180021025  cmp     [rsp+1D0h+var_1AC], r15d
0x18002102a  jbe     loc_1800211C6
0x180021030  mov     rdi, [rsp+1D0h+var_1A8]
0x180021035  mov     eax, ecx
0x180021037  imul    rsi, rax, 8Ch
0x18002103e  mov     eax, [rsi+rdi+84h]
0x180021045  cmp     eax, [rbx]
0x180021047  jnz     short loc_180021057
0x180021049  movzx   eax, word ptr [rsi+rdi+88h]
0x180021051  cmp     ax, [rbx+4]
0x180021055  jz      short loc_180021064
0x180021057  inc     ecx
0x180021059  cmp     ecx, [rsp+1D0h+var_1AC]
0x18002105d  jb      short loc_180021030
0x18002105f  jmp     loc_1800211C6
0x180021064  xor     edx, edx; Val
0x180021066  lea     rcx, [rbp+0D0h+S]; void *
0x18002106a  lea     r8d, [rdx+5Ch]; Size
0x18002106e  call    memset_0
0x180021073  mov     dword ptr [rsp+1D0h+Addr.S_un], r15d
0x180021078  lea     rdx, [rbp+0D0h+S]; S
0x18002107c  mov     eax, [rsi+rdi+80h]
0x180021083  lea     rcx, [rsp+1D0h+Addr]; Addr
0x180021088  mov     dword ptr [rsp+1D0h+Addr.S_un], eax
0x18002108c  call    cs:__imp_RtlIpv4AddressToStringW
0x180021092  test    rax, rax
0x180021095  jz      loc_18002132E
0x18002109b  mov     r8d, 2Eh ; '.'; MaxCount
0x1800210a1  lea     rdx, [rbx+6]; String2
0x1800210a5  lea     rcx, [rbp+0D0h+S]; String1
0x1800210a9  call    wcsncmp_0
0x1800210ae  mov     rcx, [rsp+1D0h+var_1A8]
0x1800210b3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800210b7  add     rcx, rsi; String1
0x1800210ba  mov     r15d, eax
0x1800210bd  xor     eax, eax
0x1800210bf  inc     r8; MaxCount
0x1800210c2  cmp     [rcx+r8*2], ax
0x1800210c7  jnz     short loc_1800210BF
0x1800210c9  lea     r14, [rbx+62h]
0x1800210cd  mov     rdx, r14; String2
0x1800210d0  call    wcsncmp_0
0x1800210d5  xor     ecx, ecx
0x1800210d7  test    eax, eax
0x1800210d9  jz      short loc_1800210F6
0x1800210db  xor     r8d, r8d; MaxCount
0x1800210de  lea     rcx, aUnknown_0; "Unknown"
0x1800210e5  mov     rdx, r14; String2
0x1800210e8  call    wcsncmp_0
0x1800210ed  xor     ecx, ecx
0x1800210ef  mov     dil, 1
0x1800210f2  test    eax, eax
0x1800210f4  jz      short loc_1800210F9
0x1800210f6  mov     dil, cl
0x1800210f9  cmp     [rbx+0E2h], cl
0x1800210ff  jz      short loc_18002110F
0x180021101  test    r15d, r15d
0x180021104  jnz     short loc_180021114
0x180021106  test    dil, dil
0x180021109  jz      loc_1800211C3
0x18002110f  test    r15d, r15d
0x180021112  jz      short loc_18002115B
0x180021114  mov     edx, 2Eh ; '.'; N1
0x180021119  lea     r8, [rbp+0D0h+S]; S2
0x18002111d  mov     r9d, edx; N
0x180021120  lea     rcx, [rbx+6]; S1
0x180021124  call    _o_wmemcpy_s_0
0x180021129  xor     r15d, r15d
0x18002112c  test    eax, eax
0x18002112e  jz      short loc_18002115E
0x180021130  mov     rcx, cs:WPP_GLOBAL_Control
0x180021137  lea     rdi, WPP_GLOBAL_Control
0x18002113e  cmp     rcx, rdi
0x180021141  jz      loc_180021363
0x180021147  test    byte ptr [rcx+1Ch], 1
0x18002114b  jz      loc_180021363
0x180021151  mov     edx, 0ECh
0x180021156  jmp     loc_18002134C
0x18002115b  xor     r15d, r15d
0x18002115e  test    dil, dil
0x180021161  jz      short loc_18002118E
0x180021163  mov     r8, [rsp+1D0h+var_1A8]
0x180021168  add     r8, rsi; S2
0x18002116b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002116f  inc     r9; N
0x180021172  cmp     [r8+r9*2], r15w
0x180021177  jnz     short loc_18002116F
0x180021179  mov     edx, 40h ; '@'; N1
0x18002117e  mov     rcx, r14; S1
0x180021181  call    _o_wmemcpy_s_0
0x180021186  test    eax, eax
0x180021188  jnz     loc_1800212EE
0x18002118e  cmp     [r14], r15w
0x180021192  jnz     short loc_1800211B5
0x180021194  mov     r9d, 7; N
0x18002119a  lea     r8, aUnknown_0; "Unknown"
0x1800211a1  mov     rcx, r14; S1
0x1800211a4  lea     edx, [r9+39h]; N1
0x1800211a8  call    _o_wmemcpy_s_0
0x1800211ad  test    eax, eax
0x1800211af  jnz     loc_18002130E
0x1800211b5  mov     byte ptr [rbx+0E2h], 1
0x1800211bc  mov     [rsp+1D0h+var_1B0], 1
0x1800211c1  jmp     short loc_1800211C6
0x1800211c3  xor     r15d, r15d
0x1800211c6  mov     rbx, [rbx+0E8h]
0x1800211cd  test    rbx, rbx
0x1800211d0  jnz     loc_180021022
0x1800211d6  lea     rcx, [r13+550h]; lpCriticalSection
0x1800211dd  call    cs:__imp_LeaveCriticalSection
0x1800211e3  mov     bl, [rsp+1D0h+var_1B0]
0x1800211e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211ee  lea     rdi, WPP_GLOBAL_Control
0x1800211f5  mov     rax, [rsp+1D0h+var_1A8]
0x1800211fa  test    rax, rax
0x1800211fd  jz      short loc_180021214
0x1800211ff  mov     rcx, rax
0x180021202  call    cs:__imp_IpNatHlpFree
0x180021208  mov     rcx, cs:WPP_GLOBAL_Control
0x18002120f  mov     [rsp+1D0h+var_1A8], r15
0x180021214  test    bl, bl
0x180021216  jz      loc_1800212AB
0x18002121c  cmp     rcx, rdi
0x18002121f  jz      short loc_18002123C
0x180021221  test    byte ptr [rcx+1Ch], 4
0x180021225  jz      short loc_18002123C
0x180021227  mov     rcx, [rcx+10h]
0x18002122b  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180021232  mov     edx, 0EFh
0x180021237  call    WPP_SF_
0x18002123c  xor     edx, edx; Val
0x18002123e  lea     rcx, [rsp+1D0h+var_18C]; void *
0x180021243  mov     r8d, 0D0h; Size
0x180021249  call    memset_0
0x18002124e  lea     rdx, [rsp+1D0h+var_190]; struct _TETHERING_WNF_NOTIFICATION_MSG *
0x180021253  mov     [rsp+1D0h+var_190], 3
0x18002125b  mov     rcx, r13; this
0x18002125e  call    ?SendNotification@TetheringService@@AEAAXPEAU_TETHERING_WNF_NOTIFICATION_MSG@@@Z; TetheringService::SendNotification(_TETHERING_WNF_NOTIFICATION_MSG *)
0x180021263  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x180021268  test    al, al
0x18002126a  jnz     short loc_1800212A4
0x18002126c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021273  cmp     rcx, rdi
0x180021276  jz      short loc_180021293
0x180021278  test    byte ptr [rcx+1Ch], 4
0x18002127c  jz      short loc_180021293
0x18002127e  mov     rcx, [rcx+10h]
0x180021282  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180021289  mov     edx, 0F0h
0x18002128e  call    WPP_SF_
0x180021293  lea     rcx, [r13+508h]
0x18002129a  mov     edx, 0Ch
0x18002129f  call    ?PublishWnfEvent@CSebHelper@@SAJAEBU_GUID@@W4NotificationMessageType@@I@Z; CSebHelper::PublishWnfEvent(_GUID const &,NotificationMessageType,uint)
0x1800212a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212ab  cmp     rcx, rdi
0x1800212ae  jz      short loc_1800212CB
0x1800212b0  test    byte ptr [rcx+1Ch], 8
0x1800212b4  jz      short loc_1800212CB
0x1800212b6  mov     rcx, [rcx+10h]
0x1800212ba  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800212c1  mov     edx, 0F1h
0x1800212c6  call    WPP_SF_
0x1800212cb  mov     rcx, [rbp+0D0h+var_50]
0x1800212d2  xor     rcx, rsp; StackCookie
0x1800212d5  call    __security_check_cookie
0x1800212da  add     rsp, 198h
0x1800212e1  pop     r15
0x1800212e3  pop     r14
0x1800212e5  pop     r13
0x1800212e7  pop     r12
0x1800212e9  pop     rdi
0x1800212ea  pop     rsi
0x1800212eb  pop     rbx
0x1800212ec  pop     rbp
0x1800212ed  retn
0x1800212ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212f5  lea     rdi, WPP_GLOBAL_Control
0x1800212fc  cmp     rcx, rdi
0x1800212ff  jz      short loc_180021363
0x180021301  test    byte ptr [rcx+1Ch], 1
0x180021305  jz      short loc_180021363
0x180021307  mov     edx, 0EDh
0x18002130c  jmp     short loc_18002134C
0x18002130e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021315  lea     rdi, WPP_GLOBAL_Control
0x18002131c  cmp     rcx, rdi
0x18002131f  jz      short loc_180021363
0x180021321  test    byte ptr [rcx+1Ch], 1
0x180021325  jz      short loc_180021363
0x180021327  mov     edx, 0EEh
0x18002132c  jmp     short loc_18002134C
0x18002132e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021335  lea     rdi, WPP_GLOBAL_Control
0x18002133c  cmp     rcx, rdi
0x18002133f  jz      short loc_180021363
0x180021341  test    byte ptr [rcx+1Ch], 1
0x180021345  jz      short loc_180021363
0x180021347  mov     edx, 0EBh
0x18002134c  mov     rcx, [rcx+10h]
0x180021350  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180021357  call    WPP_SF_
0x18002135c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021363  mov     bl, [rsp+1D0h+var_1B0]
0x180021367  jmp     loc_1800211F5
```
