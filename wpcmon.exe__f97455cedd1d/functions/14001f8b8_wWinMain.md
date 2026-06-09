# wWinMain

- ea: `0x14001f8b8`
- end: `0x14001fb23`
- name: `wWinMain`
- size: `619`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140005380`

## callees

- `0x140005530`
- `0x140008480`
- `0x1400089e0`
- `0x140009858`
- `0x14000ccac`
- `0x140013228`
- `0x140016944`
- `0x140018050`
- `0x14001f568`
- `0x14001f654`
- `0x14001f8b8`
- `0x1400200b0`
- `0x14005bbac`
- `0x140082d80`
- `0x140082fe8`

## import_xrefs

- `ADVAPI32!RegisterTraceGuidsW` at `0x14001f96d`
- `ADVAPI32!RegisterTraceGuidsW` at `0x14001f96d`
- `KERNEL32!LocalFree` at `0x14001fae8`
- `KERNEL32!LocalFree` at `0x14001fae8`
- `SHELL32!CommandLineToArgvW` at `0x14001fa45`
- `SHELL32!CommandLineToArgvW` at `0x14001fa45`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  char v5; // si
  ULONG64 *v6; // rbx
  const GUID **v7; // rdi
  const GUID *v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 Current; // rbx
  __int64 v12; // rsi
  LPWSTR *v13; // rbx
  const wchar_t *v14; // rdx
  const wchar_t *p_TraceGuidReg; // rcx
  char v16; // di
  int pNumArgs; // [rsp+40h] [rbp-C0h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+48h] [rbp-B8h] BYREF
  size_t N[3]; // [rsp+58h] [rbp-A8h]
  _BYTE v21[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[72]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v23[40]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v24[72]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v25[40]; // [rsp+168h] [rbp+68h] BYREF

  v5 = 0;
  pNumArgs = 0;
  qword_14010FCD8 = 0;
  v6 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v7 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  qword_14010FCE0 = 1;
  do
  {
    v8 = *v7;
    TraceGuidReg.Guid = v8;
    ++v7;
    TraceGuidReg.RegHandle = 0;
    v6[4] = (ULONG64)v8;
    RegisterTraceGuidsW(WppControlCallback, v6, v8, 1u, &TraceGuidReg, 0, 0, v6 + 1);
    v6 = (ULONG64 *)*v6;
  }
  while ( v6 );
  McGenEventRegister_EventRegister();
  ScopeGuard::ScopeGuard__lambda_861a06afb95744e9dddaf79e5f04d3e3___(v21);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, lpCmdLine);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( lpCmdLine[v10] );
  if ( !v10 )
  {
    Current = Sid::GetCurrent(v24);
    v12 = Sid::FromWellKnownSid(v22) + 72;
    if ( !(unsigned __int8)std::operator<<unsigned short>(Current + 72, v12) )
      LODWORD(v9) = (unsigned __int8)std::operator<<unsigned short>(v12, Current + 72) != 0;
    std::wstring::~wstring(v23);
    std::wstring::~wstring(v25);
    if ( (_DWORD)v9 )
      anonymous_namespace_::StartMonitoringTask_0();
    else
      anonymous_namespace_::MonitorChildAccounts();
    goto LABEL_30;
  }
  pNumArgs = 0;
  v13 = CommandLineToArgvW(lpCmdLine, &pNumArgs);
  if ( pNumArgs == 3 )
  {
    TraceGuidReg = 0;
    *(_OWORD *)N = 0;
    std::wstring::_Construct<1,unsigned short const *>(&TraceGuidReg, L"getticket", 9);
    v14 = *v13;
    do
      ++v9;
    while ( v14[v9] );
    p_TraceGuidReg = (const wchar_t *)&TraceGuidReg;
    if ( N[1] > 7 )
      p_TraceGuidReg = (const wchar_t *)TraceGuidReg.Guid;
    if ( N[0] == v9 && (!N[0] || !wmemcmp(p_TraceGuidReg, v14, N[0])) )
    {
      v16 = 1;
      v5 = 1;
      goto LABEL_24;
    }
    v5 = 1;
  }
  v16 = 0;
LABEL_24:
  if ( (v5 & 1) != 0 )
    std::wstring::~wstring(&TraceGuidReg);
  if ( !v16 )
    anonymous_namespace_::Run(lpCmdLine, v13, (unsigned int)pNumArgs);
  if ( v13 )
    LocalFree(v13);
LABEL_30:
  ScopeGuard::~ScopeGuard((ScopeGuard *)v21);
  return 0;
}

```

## disassembly

```asm
0x14001f8b8  push    rbp
0x14001f8ba  push    rbx
0x14001f8bb  push    rsi
0x14001f8bc  push    rdi
0x14001f8bd  push    r14
0x14001f8bf  push    r15
0x14001f8c1  lea     rbp, [rsp-0A8h]
0x14001f8c9  sub     rsp, 1A8h
0x14001f8d0  mov     rax, cs:__security_cookie
0x14001f8d7  xor     rax, rsp
0x14001f8da  mov     [rbp+0D0h+var_40], rax
0x14001f8e1  xor     r15d, r15d
0x14001f8e4  mov     r14, r8
0x14001f8e7  mov     esi, r15d
0x14001f8ea  mov     [rsp+1D0h+pNumArgs], r15d
0x14001f8ef  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14001f8f6  mov     cs:qword_14010FCD8, r15
0x14001f8fd  lea     rbx, WPP_MAIN_CB
0x14001f904  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x14001f90b  mov     cs:WPP_GLOBAL_Control, rbx
0x14001f912  lea     rdi, WPP_REGISTRATION_GUIDS
0x14001f919  mov     cs:WPP_MAIN_CB, r15
0x14001f920  mov     cs:qword_14010FCE0, 1
0x14001f92b  mov     r8, [rdi]; ControlGuid
0x14001f92e  lea     rax, [rbx+8]
0x14001f932  mov     [rsp+1D0h+RegistrationHandle], rax; RegistrationHandle
0x14001f937  lea     rcx, WppControlCallback; RequestAddress
0x14001f93e  mov     [rsp+1D0h+MofResourceName], r15; MofResourceName
0x14001f943  lea     rax, [rsp+1D0h+var_188]
0x14001f948  mov     [rsp+1D0h+var_188.Guid], r8
0x14001f94d  lea     rdi, [rdi+8]
0x14001f951  mov     [rsp+1D0h+var_188.RegHandle], r15
0x14001f956  mov     r9d, 1; GuidCount
0x14001f95c  mov     [rsp+1D0h+MofImagePath], r15; MofImagePath
0x14001f961  mov     rdx, rbx; RequestContext
0x14001f964  mov     [rsp+1D0h+TraceGuidReg], rax; TraceGuidReg
0x14001f969  mov     [rbx+20h], r8
0x14001f96d  call    cs:__imp_RegisterTraceGuidsW
0x14001f973  mov     rbx, [rbx]
0x14001f976  test    rbx, rbx
0x14001f979  jnz     short loc_14001F92B
0x14001f97b  call    McGenEventRegister_EventRegister
0x14001f980  lea     rcx, [rsp+1D0h+var_160]
0x14001f985  call    ScopeGuard__ScopeGuard__lambda_861a06afb95744e9dddaf79e5f04d3e3___
0x14001f98a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f991  lea     rax, WPP_GLOBAL_Control
0x14001f998  cmp     rcx, rax
0x14001f99b  jz      short loc_14001F9B9
0x14001f99d  test    byte ptr [rcx+1Ch], 4
0x14001f9a1  jz      short loc_14001F9B9
0x14001f9a3  mov     rcx, [rcx+10h]
0x14001f9a7  lea     edx, [rbx+23h]
0x14001f9aa  mov     r9, r14
0x14001f9ad  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x14001f9b4  call    WPP_SF_S
0x14001f9b9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001f9bd  mov     rax, rdi
0x14001f9c0  inc     rax
0x14001f9c3  cmp     [r14+rax*2], r15w
0x14001f9c8  jnz     short loc_14001F9C0
0x14001f9ca  test    rax, rax
0x14001f9cd  jnz     short loc_14001FA38
0x14001f9cf  lea     rcx, [rbp+0D0h+var_B0]
0x14001f9d3  call    ?GetCurrent@Sid@@SA?AV1@XZ; Sid::GetCurrent(void)
0x14001f9d8  lea     rcx, [rbp+0D0h+var_120]
0x14001f9dc  mov     rbx, rax
0x14001f9df  call    ?FromWellKnownSid@Sid@@SA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; Sid::FromWellKnownSid(WELL_KNOWN_SID_TYPE)
0x14001f9e4  lea     rcx, [rbx+48h]
0x14001f9e8  lea     rsi, [rax+48h]
0x14001f9ec  mov     rdx, rsi
0x14001f9ef  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x14001f9f4  test    al, al
0x14001f9f6  jnz     short loc_14001FA0E
0x14001f9f8  lea     rdx, [rbx+48h]
0x14001f9fc  mov     rcx, rsi
0x14001f9ff  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x14001fa04  mov     ecx, r15d
0x14001fa07  test    al, al
0x14001fa09  setnz   cl
0x14001fa0c  mov     edi, ecx
0x14001fa0e  lea     rcx, [rbp+0D0h+var_D8]
0x14001fa12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001fa17  lea     rcx, [rbp+0D0h+var_68]
0x14001fa1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001fa20  test    edi, edi
0x14001fa22  jnz     short loc_14001FA2E
0x14001fa24  call    _anonymous_namespace___MonitorChildAccounts
0x14001fa29  jmp     loc_14001FAEE
0x14001fa2e  call    _anonymous_namespace___StartMonitoringTask_0
0x14001fa33  jmp     loc_14001FAEE
0x14001fa38  lea     rdx, [rsp+1D0h+pNumArgs]; pNumArgs
0x14001fa3d  mov     [rsp+1D0h+pNumArgs], r15d
0x14001fa42  mov     rcx, r14; lpCmdLine
0x14001fa45  call    cs:__imp_CommandLineToArgvW
0x14001fa4b  cmp     [rsp+1D0h+pNumArgs], 3
0x14001fa50  mov     rbx, rax
0x14001fa53  jnz     short loc_14001FAB8
0x14001fa55  xorps   xmm0, xmm0
0x14001fa58  lea     rdx, aGetticket; "getticket"
0x14001fa5f  xorps   xmm1, xmm1
0x14001fa62  lea     rcx, [rsp+1D0h+var_188]
0x14001fa67  mov     r8d, 9
0x14001fa6d  movups  xmmword ptr [rsp+1D0h+var_188.Guid], xmm0
0x14001fa72  movdqu  xmmword ptr [rsp+1D0h+N], xmm1
0x14001fa78  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001fa7d  mov     rdx, [rbx]; S2
0x14001fa80  inc     rdi
0x14001fa83  cmp     [rdx+rdi*2], r15w
0x14001fa88  jnz     short loc_14001FA80
0x14001fa8a  cmp     [rsp+1D0h+N+8], 7
0x14001fa90  lea     rcx, [rsp+1D0h+var_188]
0x14001fa95  mov     r8, [rsp+1D0h+N]; N
0x14001fa9a  cmova   rcx, [rsp+1D0h+var_188.Guid]; S1
0x14001faa0  cmp     r8, rdi
0x14001faa3  jnz     short loc_14001FAB3
0x14001faa5  test    r8, r8
0x14001faa8  jz      short loc_14001FB19
0x14001faaa  call    wmemcmp
0x14001faaf  test    eax, eax
0x14001fab1  jz      short loc_14001FB19
0x14001fab3  mov     esi, 1
0x14001fab8  mov     dil, r15b
0x14001fabb  test    sil, 1
0x14001fabf  jz      short loc_14001FACB
0x14001fac1  lea     rcx, [rsp+1D0h+var_188]
0x14001fac6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001facb  test    dil, dil
0x14001face  jnz     short loc_14001FAE0
0x14001fad0  mov     r8d, [rsp+1D0h+pNumArgs]
0x14001fad5  mov     rdx, rbx
0x14001fad8  mov     rcx, r14
0x14001fadb  call    _anonymous_namespace___Run
0x14001fae0  test    rbx, rbx
0x14001fae3  jz      short loc_14001FAEE
0x14001fae5  mov     rcx, rbx; hMem
0x14001fae8  call    cs:__imp_LocalFree
0x14001faee  lea     rcx, [rsp+1D0h+var_160]; this
0x14001faf3  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x14001faf8  xor     eax, eax
0x14001fafa  mov     rcx, [rbp+0D0h+var_40]
0x14001fb01  xor     rcx, rsp; StackCookie
0x14001fb04  call    __security_check_cookie
0x14001fb09  add     rsp, 1A8h
0x14001fb10  pop     r15
0x14001fb12  pop     r14
0x14001fb14  pop     rdi
0x14001fb15  pop     rsi
0x14001fb16  pop     rbx
0x14001fb17  pop     rbp
0x14001fb18  retn
0x14001fb19  mov     dil, 1
0x14001fb1c  mov     esi, 1
0x14001fb21  jmp     short loc_14001FABB
```
