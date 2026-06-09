# SrvNetRefreshLanmanServerParameters

- ea: `0x140056534`
- end: `0x14005682b`
- name: `SrvNetRefreshLanmanServerParameters`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140050940`
- `0x1400564f0`

## callees

- `0x140001008`
- `0x140001040`
- `0x14001aff0`
- `0x14001b060`
- `0x14002a3e0`
- `0x14004156c`
- `0x140047ab0`
- `0x140056534`

## string_xrefs

- `0x140056577`: `DisableNetBufferLookAside`
- `0x140056562`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x1400565e6`: `AuditSmb1Access`
- `0x1400566e9`: `RestrictNamedPipeAccessViaQuic`
- `0x140056620`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x14005663d`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x140056783`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`

## pseudocode

```c
signed __int8 SrvNetRefreshLanmanServerParameters()
{
  char v0; // r14
  __int16 v1; // si
  int DWord; // eax
  int v3; // ecx
  char v4; // al
  char v5; // bl
  bool v6; // di
  char v7; // cl
  signed __int8 result; // al

  v0 = SrvDisableNetBufferLookAsideList;
  v1 = SrvQuicListenPort;
  RfsRegGetDWord(
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    L"DisableNetBufferLookAside");
  SrvDisableNetBufferLookAsideList = 0;
  RfsRegGetDWord(
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    L"ServerQuicPort");
  SrvQuicListenPort = 443;
  DWord = RfsRegGetDWord(
            L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
            L"EnabledTransports");
  v3 = -1;
  if ( DWord >= 0 )
    v3 = 0;
  SrvNetEnabledTransports = v3;
  RfsRegGetDWord(
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    L"AuditSmb1Access");
  SrvNetAuditSmb1Access = 0;
  RfsRegGetDWord(
    L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
    L"RequireSessionSigningIfSpnValidationFails");
  if ( (int)RfsRegGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"AuditClientSpnSupport") < 0 )
    RfsRegGetDWord(
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
      L"AuditClientSpnSupport");
  SrvNetAuditClientSpnSupport = 0;
  SrvNetRestrictNamedPipeAccessViaQuic = (int)RfsRegGetDWord(
                                                L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                                                L"RestrictNamedPipeAccessViaQuic") < 0;
  v4 = (int)RfsRegGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableRdmaSupport") < 0;
  v5 = SrvNetEnableRdmaSupport;
  SrvNetEnableRdmaSupport = v4;
  v6 = v5 != v4;
  RfsRegGetDWord(
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    L"EnableBidirectionalRdma");
  _InterlockedExchange(&SrvNetEnableBidirectionalRdma, 0);
  if ( v6 || v5 != 0 )
    SrvNetRefreshRdmaStateOnAllInterfaces();
  v7 = (int)RfsRegGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"EnableSMBQUIC") < 0
    && (int)RfsRegGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableSMBQUIC") < 0;
  result = SrvNetEnableSmbQuic;
  SrvNetEnableSmbQuic = v7;
  if ( v7 != result )
    result = SrvNetQUICBringToDesiredState();
  if ( v1 != SrvQuicListenPort )
  {
    result = _InterlockedCompareExchange8(&SrvNetEnableSmbQuic, 0, 1);
    if ( result == 1 )
    {
      SrvNetQUICBringToDesiredState();
      result = _InterlockedCompareExchange8(&SrvNetEnableSmbQuic, 1, 0);
      if ( !result )
        result = SrvNetQUICBringToDesiredState();
    }
  }
  if ( !v0 )
  {
    if ( SrvDisableNetBufferLookAsideList )
      return SrvNetFlushBufferLookasides();
  }
  return result;
}

```

## disassembly

```asm
0x140056534  push    rbp
0x140056536  push    rbx
0x140056537  push    rsi
0x140056538  push    rdi
0x140056539  push    r12
0x14005653b  push    r13
0x14005653d  push    r14
0x14005653f  push    r15
0x140056541  lea     rbp, [rsp-1Fh]
0x140056546  sub     rsp, 98h
0x14005654d  mov     rax, cs:__security_cookie
0x140056554  xor     rax, rsp
0x140056557  mov     [rbp+57h+var_50], rax
0x14005655b  mov     r14b, cs:SrvDisableNetBufferLookAsideList
0x140056562  lea     r13, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140056569  movzx   esi, cs:SrvQuicListenPort
0x140056570  lea     r8, [rbp+57h+var_A0]
0x140056574  xor     r15d, r15d
0x140056577  lea     rdx, aDisablenetbuff; "DisableNetBufferLookAside"
0x14005657e  mov     rcx, r13; SourceString
0x140056581  mov     [rbp+57h+var_A0], r15d
0x140056585  call    RfsRegGetDWord
0x14005658a  test    eax, eax
0x14005658c  js      short loc_140056597
0x14005658e  cmp     [rbp+57h+var_A0], r15d
0x140056592  setnz   al
0x140056595  jmp     short loc_14005659A
0x140056597  mov     al, r15b
0x14005659a  lea     r8, [rbp+57h+var_A0]
0x14005659e  mov     cs:SrvDisableNetBufferLookAsideList, al
0x1400565a4  lea     rdx, aServerquicport; "ServerQuicPort"
0x1400565ab  mov     rcx, r13; SourceString
0x1400565ae  call    RfsRegGetDWord
0x1400565b3  test    eax, eax
0x1400565b5  js      short loc_1400565BE
0x1400565b7  mov     eax, [rbp+57h+var_A0]
0x1400565ba  test    eax, eax
0x1400565bc  jnz     short loc_1400565C3
0x1400565be  mov     eax, 1BBh
0x1400565c3  lea     r8, [rbp+57h+var_A0]
0x1400565c7  mov     cs:SrvQuicListenPort, ax
0x1400565ce  lea     rdx, aEnabledtranspo; "EnabledTransports"
0x1400565d5  mov     rcx, r13; SourceString
0x1400565d8  call    RfsRegGetDWord
0x1400565dd  or      ecx, 0FFFFFFFFh
0x1400565e0  lea     r8, [rbp+57h+var_A0]
0x1400565e4  test    eax, eax
0x1400565e6  lea     rdx, aAuditsmb1acces; "AuditSmb1Access"
0x1400565ed  cmovns  ecx, [rbp+57h+var_A0]
0x1400565f1  mov     cs:SrvNetEnabledTransports, ecx
0x1400565f7  mov     rcx, r13; SourceString
0x1400565fa  call    RfsRegGetDWord
0x1400565ff  test    eax, eax
0x140056601  js      short loc_14005660C
0x140056603  cmp     [rbp+57h+var_A0], r15d
0x140056607  setnz   al
0x14005660a  jmp     short loc_14005660F
0x14005660c  mov     al, r15b
0x14005660f  lea     r8, [rbp+57h+var_A0]
0x140056613  mov     cs:SrvNetAuditSmb1Access, al
0x140056619  lea     rdx, aRequiresession; "RequireSessionSigningIfSpnValidationFai"...
0x140056620  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Policies"...
0x140056627  call    RfsRegGetDWord
0x14005662c  mov     bl, cs:SrvNetAuditClientSpnSupport
0x140056632  lea     r8, [rbp+57h+var_A0]
0x140056636  lea     rdx, aAuditclientspn; "AuditClientSpnSupport"
0x14005663d  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Policies"...
0x140056644  call    RfsRegGetDWord
0x140056649  test    eax, eax
0x14005664b  jns     short loc_140056664
0x14005664d  lea     r8, [rbp+57h+var_A0]
0x140056651  mov     rcx, r13; SourceString
0x140056654  lea     rdx, aAuditclientspn; "AuditClientSpnSupport"
0x14005665b  call    RfsRegGetDWord
0x140056660  test    eax, eax
0x140056662  js      short loc_14005666D
0x140056664  cmp     [rbp+57h+var_A0], r15d
0x140056668  setnz   al
0x14005666b  jmp     short loc_140056670
0x14005666d  mov     al, r15b
0x140056670  mov     cs:SrvNetAuditClientSpnSupport, al
0x140056676  mov     r12d, 1
0x14005667c  test    bl, bl
0x14005667e  jnz     short loc_1400566E2
0x140056680  test    al, al
0x140056682  jz      short loc_1400566E2
0x140056684  mov     eax, cs:dword_140036120
0x14005668a  cmp     eax, 5
0x14005668d  jbe     short loc_1400566E2
0x14005668f  call    _tlgKeywordOn
0x140056694  test    al, al
0x140056696  jz      short loc_1400566E2
0x140056698  lea     rax, [rbp+57h+var_98]
0x14005669c  mov     [rbp+57h+var_98], 1000000h
0x1400566a4  mov     [rbp+57h+var_70], rax
0x1400566a8  lea     rdx, byte_140031991; int
0x1400566af  mov     al, cs:SrvNetAuditClientSpnSupport
0x1400566b5  mov     [rbp+57h+var_9C], al
0x1400566b8  lea     rax, [rbp+57h+var_9C]
0x1400566bc  mov     [rbp+57h+var_60], rax
0x1400566c0  lea     rax, [rbp+57h+var_90]
0x1400566c4  mov     [rsp+0D0h+var_A8], rax; __int64
0x1400566c9  mov     [rsp+0D0h+var_B0], 4; ULONG
0x1400566d1  mov     [rbp+57h+var_68], 8
0x1400566d9  mov     [rbp+57h+var_58], r12
0x1400566dd  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400566e2  lea     r8, [rbp+57h+var_A0]
0x1400566e6  mov     rcx, r13; SourceString
0x1400566e9  lea     rdx, aRestrictnamedp; "RestrictNamedPipeAccessViaQuic"
0x1400566f0  call    RfsRegGetDWord
0x1400566f5  test    eax, eax
0x1400566f7  js      short loc_140056705
0x1400566f9  cmp     [rbp+57h+var_A0], r15d
0x1400566fd  mov     eax, r15d
0x140056700  setnz   al
0x140056703  jmp     short loc_140056708
0x140056705  mov     eax, r12d
0x140056708  lea     r8, [rbp+57h+var_A0]
0x14005670c  mov     cs:SrvNetRestrictNamedPipeAccessViaQuic, eax
0x140056712  lea     rdx, aEnablerdmasupp; "EnableRdmaSupport"
0x140056719  mov     rcx, r13; SourceString
0x14005671c  call    RfsRegGetDWord
0x140056721  test    eax, eax
0x140056723  js      short loc_14005672E
0x140056725  cmp     [rbp+57h+var_A0], r15d
0x140056729  setnz   al
0x14005672c  jmp     short loc_140056731
0x14005672e  mov     al, r12b
0x140056731  mov     bl, al
0x140056733  lea     r8, [rbp+57h+var_A0]
0x140056737  xchg    bl, cs:SrvNetEnableRdmaSupport
0x14005673d  cmp     bl, al
0x14005673f  lea     rdx, aEnablebidirect; "EnableBidirectionalRdma"
0x140056746  mov     rcx, r13; SourceString
0x140056749  setnz   dil
0x14005674d  call    RfsRegGetDWord
0x140056752  mov     edx, [rbp+57h+var_A0]
0x140056755  test    eax, eax
0x140056757  movzx   ecx, bl
0x14005675a  cmovs   edx, r15d
0x14005675e  cmp     ecx, edx
0x140056760  mov     [rbp+57h+var_A0], edx
0x140056763  mov     eax, edx
0x140056765  xchg    eax, cs:SrvNetEnableBidirectionalRdma
0x14005676b  setnz   al
0x14005676e  or      al, dil
0x140056771  jz      short loc_140056778
0x140056773  call    SrvNetRefreshRdmaStateOnAllInterfaces
0x140056778  lea     r8, [rbp+57h+var_A0]
0x14005677c  lea     rdx, aEnablesmbquic; "EnableSMBQUIC"
0x140056783  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Policies"...
0x14005678a  call    RfsRegGetDWord
0x14005678f  test    eax, eax
0x140056791  jns     short loc_1400567AA
0x140056793  lea     r8, [rbp+57h+var_A0]
0x140056797  mov     rcx, r13; SourceString
0x14005679a  lea     rdx, aEnablesmbquic; "EnableSMBQUIC"
0x1400567a1  call    RfsRegGetDWord
0x1400567a6  test    eax, eax
0x1400567a8  js      short loc_1400567B3
0x1400567aa  cmp     [rbp+57h+var_A0], r15d
0x1400567ae  setnz   cl
0x1400567b1  jmp     short loc_1400567B6
0x1400567b3  mov     cl, r12b
0x1400567b6  mov     al, cl
0x1400567b8  xchg    al, cs:SrvNetEnableSmbQuic
0x1400567be  cmp     cl, al
0x1400567c0  jz      short loc_1400567C7
0x1400567c2  call    SrvNetQUICBringToDesiredState
0x1400567c7  cmp     si, cs:SrvQuicListenPort
0x1400567ce  jz      short loc_1400567F7
0x1400567d0  mov     ecx, r15d
0x1400567d3  mov     al, r12b
0x1400567d6  lock cmpxchg cs:SrvNetEnableSmbQuic, cl
0x1400567de  jnz     short loc_1400567F7
0x1400567e0  call    SrvNetQUICBringToDesiredState
0x1400567e5  xor     eax, eax
0x1400567e7  lock cmpxchg cs:SrvNetEnableSmbQuic, r12b
0x1400567f0  jnz     short loc_1400567F7
0x1400567f2  call    SrvNetQUICBringToDesiredState
0x1400567f7  test    r14b, r14b
0x1400567fa  jnz     short loc_14005680A
0x1400567fc  cmp     cs:SrvDisableNetBufferLookAsideList, r15b
0x140056803  jz      short loc_14005680A
0x140056805  call    SrvNetFlushBufferLookasides
0x14005680a  mov     rcx, [rbp+57h+var_50]
0x14005680e  xor     rcx, rsp; StackCookie
0x140056811  call    __security_check_cookie
0x140056816  add     rsp, 98h
0x14005681d  pop     r15
0x14005681f  pop     r14
0x140056821  pop     r13
0x140056823  pop     r12
0x140056825  pop     rdi
0x140056826  pop     rsi
0x140056827  pop     rbx
0x140056828  pop     rbp
0x140056829  retn
```
