# _lambda_ff1938da65d60cabaa1a6e57ec4bb303_::operator()

- ea: `0x140033974`
- end: `0x140033b08`
- name: `_lambda_ff1938da65d60cabaa1a6e57ec4bb303_::operator()`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140036350`

## callees

- `0x140004370`
- `0x140019740`
- `0x14001fa34`
- `0x1400226a4`
- `0x140024c44`
- `0x140026c20`
- `0x140030bc8`
- `0x140032640`
- `0x140033974`
- `0x140036678`
- `0x140037ae0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400339af`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400339af`
- `SmartScreen!CheckFileReputation` at `0x140033a97`
- `SmartScreen!CheckFileReputation` at `0x140033a97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x140033ace`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x140033ace`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_ff1938da65d60cabaa1a6e57ec4bb303_::operator()(__int64 a1, __int64 a2)
{
  DWORD ProcessId; // ebx
  unsigned int IWindowHandle; // r15d
  char v6; // si
  __int64 v7; // rdi
  __int64 v8; // rax
  int v9; // edi
  char v11; // [rsp+28h] [rbp-D8h]
  __int64 v12; // [rsp+30h] [rbp-D0h]
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+58h] [rbp-A8h]
  _BYTE v15[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v16[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v17[32]; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v18; // [rsp+C8h] [rbp-38h] BYREF
  int v19; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v20; // [rsp+D8h] [rbp-28h]
  _BYTE v21[40]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v22[128]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v23[384]; // [rsp+190h] [rbp+90h] BYREF

  ProcessId = GetProcessId(*(HANDLE *)a1);
  LODWORD(v12) = ProcessId;
  BYTE4(v12) = 1;
  IWindowHandle = 0;
  if ( (unsigned __int8)com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>::operator!=<std::nullptr_t>(a1 + 72) )
    IWindowHandle = GetIWindowHandle(a1 + 72);
  v18 = *(HANDLE *)a1;
  *(_QWORD *)a1 = 0;
  process_from_handle(&v19, &v18);
  v6 = *(_BYTE *)(a1 + 88);
  v13 = v19;
  v14 = v20;
  std::wstring::wstring(v15, v21);
  v7 = std::wstring::wstring(v16, a1 + 40);
  v8 = std::wstring::wstring(v17, a1 + 8);
  v11 = v6;
  ContextBuilder::ContextBuilder(v23, v8, v7, IWindowHandle, &v13, v11, v12);
  ContextBuilder::GetCFileReputationContext(v23, v22);
  LODWORD(v18) = 0;
  v9 = CheckFileReputation(v22, &v18);
  if ( v9 >= 0 )
    *(_DWORD *)(a2 + 16) = TranslateAppReputationResult((unsigned int)v18);
  ContextBuilder::~ContextBuilder((ContextBuilder *)v23);
  path::~path((path *)v21);
  AllowSetForegroundWindow(ProcessId);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140033974  mov     [rsp-8+arg_10], rbx
0x140033979  mov     [rsp-8+arg_18], rsi
0x14003397e  push    rbp
0x14003397f  push    rdi
0x140033980  push    r13
0x140033982  push    r14
0x140033984  push    r15
0x140033986  lea     rbp, [rsp-220h]
0x14003398e  sub     rsp, 320h
0x140033995  mov     rax, cs:__security_cookie
0x14003399c  xor     rax, rsp
0x14003399f  mov     [rbp+240h+var_30], rax
0x1400339a6  mov     r13, rdx
0x1400339a9  mov     r14, rcx
0x1400339ac  mov     rcx, [rcx]; Process
0x1400339af  call    cs:__imp_GetProcessId
0x1400339b6  nop     dword ptr [rax+rax+00h]
0x1400339bb  mov     ebx, eax
0x1400339bd  mov     [rsp+340h+var_310], eax
0x1400339c1  mov     [rsp+340h+var_30C], 1
0x1400339c6  xor     r15d, r15d
0x1400339c9  lea     rcx, [r14+48h]
0x1400339cd  call    ??$?9$$T@?$marshaled_ptr@UIWindow@SmartScreen@Security@Internal@Windows@@@com@@QEBA_NAEB$$T@Z
0x1400339d2  test    al, al
0x1400339d4  jz      short loc_1400339E2
0x1400339d6  lea     rcx, [r14+48h]
0x1400339da  call    GetIWindowHandle
0x1400339df  mov     r15d, eax
0x1400339e2  mov     rcx, [r14]
0x1400339e5  mov     [rbp+240h+var_278], rcx
0x1400339e9  mov     qword ptr [r14], 0
0x1400339f0  lea     rdx, [rbp+240h+var_278]
0x1400339f4  lea     rcx, [rbp+240h+var_270]
0x1400339f8  call    process_from_handle
0x1400339fd  nop
0x1400339fe  mov     sil, [r14+58h]
0x140033a02  lea     rax, [rsp+340h+var_2F0]
0x140033a07  mov     [rsp+340h+var_308], rax
0x140033a0c  mov     eax, [rbp+240h+var_270]
0x140033a0f  mov     [rsp+340h+var_2F0], eax
0x140033a13  movups  xmm0, [rbp+240h+var_268]
0x140033a17  movdqu  [rsp+340h+var_2E8], xmm0
0x140033a1d  lea     rdx, [rbp+240h+var_258]
0x140033a21  lea     rcx, [rsp+340h+var_2D8]
0x140033a26  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140033a2b  nop
0x140033a2c  lea     rax, [rbp+240h+var_2B8]
0x140033a30  mov     [rsp+340h+var_300], rax
0x140033a35  lea     rdx, [r14+28h]
0x140033a39  lea     rcx, [rbp+240h+var_2B8]
0x140033a3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140033a42  mov     rdi, rax
0x140033a45  lea     rdx, [r14+8]
0x140033a49  lea     rcx, [rbp+240h+var_298]
0x140033a4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140033a52  nop
0x140033a53  mov     [rsp+340h+var_318], sil
0x140033a58  lea     rcx, [rsp+340h+var_2F0]
0x140033a5d  mov     [rsp+340h+var_320], rcx
0x140033a62  mov     r9d, r15d
0x140033a65  mov     r8, rdi
0x140033a68  mov     rdx, rax
0x140033a6b  lea     rcx, [rbp+240h+var_1B0]
0x140033a72  call    ??0ContextBuilder@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0IUprocess_information@@_N@Z; ContextBuilder::ContextBuilder(std::wstring,std::wstring,uint,process_information,bool)
0x140033a77  nop
0x140033a78  lea     rdx, [rbp+240h+var_230]
0x140033a7c  lea     rcx, [rbp+240h+var_1B0]
0x140033a83  call    ?GetCFileReputationContext@ContextBuilder@@QEAA?AUCFileReputationContext@@XZ; ContextBuilder::GetCFileReputationContext(void)
0x140033a88  mov     dword ptr [rbp+240h+var_278], 0
0x140033a8f  lea     rdx, [rbp+240h+var_278]
0x140033a93  lea     rcx, [rbp+240h+var_230]
0x140033a97  call    cs:__imp_CheckFileReputation
0x140033a9e  nop     dword ptr [rax+rax+00h]
0x140033aa3  mov     edi, eax
0x140033aa5  test    eax, eax
0x140033aa7  js      short loc_140033AB5
0x140033aa9  mov     ecx, dword ptr [rbp+240h+var_278]
0x140033aac  call    TranslateAppReputationResult
0x140033ab1  mov     [r13+10h], eax
0x140033ab5  lea     rcx, [rbp+240h+var_1B0]; this
0x140033abc  call    ??1ContextBuilder@@QEAA@XZ; ContextBuilder::~ContextBuilder(void)
0x140033ac1  nop
0x140033ac2  lea     rcx, [rbp+240h+var_258]; this
0x140033ac6  call    ??1path@@QEAA@XZ; path::~path(void)
0x140033acb  nop
0x140033acc  mov     ecx, ebx; dwProcessId
0x140033ace  call    cs:__imp_AllowSetForegroundWindow
0x140033ad5  nop     dword ptr [rax+rax+00h]
0x140033ada  mov     eax, edi
0x140033adc  mov     rcx, [rbp+240h+var_30]
0x140033ae3  xor     rcx, rsp; StackCookie
0x140033ae6  call    __security_check_cookie
0x140033aeb  lea     r11, [rsp+340h+var_20]
0x140033af3  mov     rbx, [r11+40h]
0x140033af7  mov     rsi, [r11+48h]
0x140033afb  mov     rsp, r11
0x140033afe  pop     r15
0x140033b00  pop     r14
0x140033b02  pop     r13
0x140033b04  pop     rdi
0x140033b05  pop     rbp
0x140033b06  retn
```
