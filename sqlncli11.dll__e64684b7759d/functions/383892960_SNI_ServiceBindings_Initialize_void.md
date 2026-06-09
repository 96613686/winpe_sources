# SNI_ServiceBindings::Initialize(void)

- ea: `0x383892960`
- end: `0x383892a15`
- name: `?Initialize@SNI_ServiceBindings@@SAKXZ`
- size: `181`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3838928e0`

## callees

- `0x3838434c0`
- `0x383846430`
- `0x3838832d0`
- `0x383892960`
- `0x38391ac20`
- `0x38391ac40`
- `0x38391ae80`
- `0x383ab0c30`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x3838929c3`
- `WS2_32!__imp_WSAStartup` at `0x383902656`
- `WS2_32!__imp_WSAStartup` at `0x3838929c3`
- `WS2_32!__imp_WSAStartup` at `0x383902656`
- `WS2_32!__imp_WSACleanup` at `0x3839026a7`
- `WS2_32!__imp_WSACleanup` at `0x3839026a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SNI_ServiceBindings::Initialize(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  char *v3; // r8
  __int64 v4; // rdx
  char *v5; // rcx
  WSAData WSAData; // [rsp+40h] [rbp-1B8h] BYREF

  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48B88[0] && bidID != -1 )
    off_383B15048();
  v0 = CCriticalSectionNT_SNI::Initialize(&SNI_ServiceBindings::s_pcsDynamicNameAddressInfoList);
  v1 = v0;
  if ( v0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B47AD0[0] )
    {
      v3 = off_383B47AD0[0];
      v4 = 156672;
      v5 = off_383B45450[0];
LABEL_17:
      bidTraceA(v5, v4, v3, v0);
    }
  }
  else
  {
    if ( !WSAStartup(0x202u, &WSAData) || (v0 = WSAStartup(0x101u, &WSAData)) == 0 )
    {
      SNI_ServiceBindings::s_fWSAStarted = 1;
      goto LABEL_5;
    }
    v1 = v0;
    if ( (bidGblFlags & 2) != 0 && off_383B47AC8[0] )
    {
      v3 = off_383B47AC8[0];
      v4 = 167936;
      v5 = off_383B45448[0];
      goto LABEL_17;
    }
  }
  if ( v1 )
  {
    if ( SNI_ServiceBindings::s_fWSAStarted )
    {
      WSACleanup();
      SNI_ServiceBindings::s_fWSAStarted = 0;
    }
    if ( SNI_ServiceBindings::s_pcsDynamicNameAddressInfoList )
    {
      (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))SNI_ServiceBindings::s_pcsDynamicNameAddressInfoList)(
        SNI_ServiceBindings::s_pcsDynamicNameAddressInfoList,
        1);
      SNI_ServiceBindings::s_pcsDynamicNameAddressInfoList = 0;
    }
    if ( (bidGblFlags & 2) != 0 && off_383B47AC0[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceA(off_383B45440[0], 179200, off_383B47AC0[0], 9);
    }
    SNISetLastError(9, v1, 50100);
  }
LABEL_5:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B47AB8[0] )
    bidTraceA(off_383B45438[0], 182272, off_383B47AB8[0], v1);
  return v1;
}

```

## disassembly

```asm
0x383892960  push    rbx
0x383892962  sub     rsp, 1F0h
0x383892969  mov     [rsp+1F8h+var_1C0], 0FFFFFFFFFFFFFFFEh
0x383892972  mov     rax, cs:__security_cookie
0x383892979  xor     rax, rsp
0x38389297c  mov     [rsp+1F8h+var_18], rax
0x383892984  mov     [rsp+1F8h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x38389298d  mov     eax, cs:_bidGblFlags
0x383892993  and     eax, 20004h
0x383892998  cmp     eax, 20004h
0x38389299d  jz      loc_3839025D2
0x3838929a3  lea     rcx, ?s_pcsDynamicNameAddressInfoList@SNI_ServiceBindings@@0PEAVCCriticalSectionNT_SNI@@EA; struct CCriticalSectionNT_SNI **
0x3838929aa  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x3838929af  mov     ebx, eax
0x3838929b1  test    eax, eax
0x3838929b3  jnz     loc_383902622
0x3838929b9  mov     ecx, 202h; wVersionRequested
0x3838929be  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x3838929c3  call    cs:__imp_WSAStartup
0x3838929c9  test    eax, eax
0x3838929cb  jnz     loc_38390264C
0x3838929d1  mov     cs:?s_fWSAStarted@SNI_ServiceBindings@@0_NA, 1; bool SNI_ServiceBindings::s_fWSAStarted
0x3838929d8  mov     eax, cs:_bidGblFlags
0x3838929de  and     eax, 20002h
0x3838929e3  cmp     eax, 20002h
0x3838929e8  jz      loc_383902731
0x3838929ee  cmp     [rsp+1F8h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x3838929f4  jnz     loc_383902762
0x3838929fa  mov     eax, ebx
0x3838929fc  mov     rcx, [rsp+1F8h+var_18]
0x383892a04  xor     rcx, rsp; StackCookie
0x383892a07  call    __security_check_cookie
0x383892a0c  add     rsp, 1F0h
0x383892a13  pop     rbx
0x383892a14  retn
0x3839025d2  mov     rax, cs:off_383B48B88; "<SNI_ServiceBindings::Initialize|API|SN"...
0x3839025d9  test    rax, rax
0x3839025dc  jz      loc_3838929A3
0x3839025e2  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3839025ea  jz      loc_3838929A3
0x3839025f0  mov     [rsp+1F8h+var_1D0], 0
0x3839025f9  mov     rax, cs:off_383B48B88; "<SNI_ServiceBindings::Initialize|API|SN"...
0x383902600  mov     [rsp+1F8h+var_1D8], rax
0x383902605  lea     r9, [rsp+1F8h+var_1C8]
0x38390260a  xor     r8d, r8d
0x38390260d  xor     edx, edx
0x38390260f  mov     rcx, cs:_bidID
0x383902616  call    cs:off_383B15048
0x38390261c  nop
0x38390261d  jmp     loc_3838929A3
0x383902622  test    byte ptr cs:_bidGblFlags, 2
0x383902629  jz      short loc_383902696
0x38390262b  mov     rcx, cs:off_383B47AD0; "<SNI_ServiceBindings::Initialize|ERR|SN"...
0x383902632  test    rcx, rcx
0x383902635  jz      short loc_383902696
0x383902637  mov     r8, cs:off_383B47AD0; "<SNI_ServiceBindings::Initialize|ERR|SN"...
0x38390263e  mov     edx, 26400h
0x383902643  mov     rcx, cs:off_383B45450; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x38390264a  jmp     short loc_38390268E
0x38390264c  mov     ecx, 101h; wVersionRequested
0x383902651  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x383902656  call    cs:__imp_WSAStartup
0x38390265c  test    eax, eax
0x38390265e  jz      loc_3838929D1
0x383902664  mov     ebx, eax
0x383902666  test    byte ptr cs:_bidGblFlags, 2
0x38390266d  jz      short loc_383902696
0x38390266f  mov     rcx, cs:off_383B47AC8; "<SNI_ServiceBindings::Initialize|ERR|SN"...
0x383902676  test    rcx, rcx
0x383902679  jz      short loc_383902696
0x38390267b  mov     r8, cs:off_383B47AC8; "<SNI_ServiceBindings::Initialize|ERR|SN"...
0x383902682  mov     edx, 29000h
0x383902687  mov     rcx, cs:off_383B45448; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x38390268e  mov     r9d, eax
0x383902691  call    _bidTraceA
0x383902696  test    ebx, ebx
0x383902698  jz      loc_3838929D8
0x38390269e  cmp     cs:?s_fWSAStarted@SNI_ServiceBindings@@0_NA, 0; bool SNI_ServiceBindings::s_fWSAStarted
0x3839026a5  jz      short loc_3839026B4
0x3839026a7  call    cs:__imp_WSACleanup
0x3839026ad  mov     cs:?s_fWSAStarted@SNI_ServiceBindings@@0_NA, 0; bool SNI_ServiceBindings::s_fWSAStarted
0x3839026b4  mov     rcx, cs:?s_pcsDynamicNameAddressInfoList@SNI_ServiceBindings@@0PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * SNI_ServiceBindings::s_pcsDynamicNameAddressInfoList
0x3839026bb  test    rcx, rcx
0x3839026be  jz      short loc_3839026D5
0x3839026c0  mov     rax, [rcx]
0x3839026c3  mov     edx, 1
0x3839026c8  call    qword ptr [rax]
0x3839026ca  mov     cs:?s_pcsDynamicNameAddressInfoList@SNI_ServiceBindings@@0PEAVCCriticalSectionNT_SNI@@EA, 0; CCriticalSectionNT_SNI * SNI_ServiceBindings::s_pcsDynamicNameAddressInfoList
0x3839026d5  test    byte ptr cs:_bidGblFlags, 2
0x3839026dc  jz      short loc_38390271A
0x3839026de  mov     rax, cs:off_383B47AC0; "<SNI_ServiceBindings::Initialize|ERR|SN"...
0x3839026e5  test    rax, rax
0x3839026e8  jz      short loc_38390271A
0x3839026ea  mov     ecx, 0C3B4h; unsigned int
0x3839026ef  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3839026f4  mov     dword ptr [rsp+1F8h+var_1D0], ebx
0x3839026f8  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x3839026fc  mov     r9d, 9
0x383902702  mov     r8, cs:off_383B47AC0; "<SNI_ServiceBindings::Initialize|ERR|SN"...
0x383902709  mov     edx, 2BC00h
0x38390270e  mov     rcx, cs:off_383B45440; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383902715  call    _bidTraceA
0x38390271a  mov     r8d, 0C3B4h
0x383902720  mov     edx, ebx
0x383902722  mov     ecx, 9
0x383902727  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x38390272c  jmp     loc_3838929D8
0x383902731  mov     rax, cs:off_383B47AB8; "<SNI_ServiceBindings::Initialize|RET|SN"...
0x383902738  test    rax, rax
0x38390273b  jz      loc_3838929EE
0x383902741  mov     r9d, ebx
0x383902744  mov     r8, cs:off_383B47AB8; "<SNI_ServiceBindings::Initialize|RET|SN"...
0x38390274b  mov     edx, 2C800h
0x383902750  mov     rcx, cs:off_383B45438; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383902757  call    _bidTraceA
0x38390275c  nop
0x38390275d  jmp     loc_3838929EE
0x383902762  test    byte ptr cs:_bidGblFlags, 4
0x383902769  jz      loc_3838929FA
0x38390276f  mov     rcx, cs:_bidID
0x383902776  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x38390277a  jz      loc_3838929FA
0x383902780  lea     r9, [rsp+1F8h+var_1C8]
0x383902785  xor     r8d, r8d
0x383902788  xor     edx, edx
0x38390278a  call    cs:off_383B15058
0x383902790  nop
0x383902791  jmp     loc_3838929FA
```
