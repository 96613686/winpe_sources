# _lambda_ff1938da65d60cabaa1a6e57ec4bb303_::operator()

- ea: `0x1400324fc`
- end: `0x14003267d`
- name: `_lambda_ff1938da65d60cabaa1a6e57ec4bb303_::operator()`
- size: `385`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140034e40`

## callees

- `0x140004190`
- `0x140018a58`
- `0x14001e874`
- `0x140021534`
- `0x140023aac`
- `0x140025aa0`
- `0x14002f8f0`
- `0x140031280`
- `0x1400324fc`
- `0x140035148`
- `0x1400365b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140032537`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140032537`
- `SmartScreen!CheckFileReputation` at `0x140032619`
- `SmartScreen!CheckFileReputation` at `0x140032619`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x14003264a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x14003264a`

## pseudocode

```c
__int64 __fastcall lambda_ff1938da65d60cabaa1a6e57ec4bb303_::operator()(__int64 a1, __int64 a2)
{
  DWORD ProcessId; // ebx
  unsigned int IWindowHandle; // r15d
  char v6; // si
  __int64 v7; // rdi
  __int64 v8; // rax
  int v9; // edi
  char v11; // [rsp+28h] [rbp-D8h]
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+58h] [rbp-A8h]
  _BYTE v14[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v15[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v16[32]; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v17; // [rsp+C8h] [rbp-38h] BYREF
  int v18; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v19; // [rsp+D8h] [rbp-28h]
  _BYTE v20[40]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v21[128]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v22[384]; // [rsp+190h] [rbp+90h] BYREF

  ProcessId = GetProcessId(*(HANDLE *)a1);
  IWindowHandle = 0;
  if ( (unsigned __int8)com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>::operator!=<std::nullptr_t>(a1 + 72) )
    IWindowHandle = GetIWindowHandle(a1 + 72);
  v17 = *(HANDLE *)a1;
  *(_QWORD *)a1 = 0;
  process_from_handle(&v18, &v17);
  v6 = *(_BYTE *)(a1 + 88);
  v12 = v18;
  v13 = v19;
  std::wstring::wstring(v14, v20);
  v7 = std::wstring::wstring(v15, a1 + 40);
  v8 = std::wstring::wstring(v16, a1 + 8);
  v11 = v6;
  ContextBuilder::ContextBuilder(v22, v8, v7, IWindowHandle, &v12, v11);
  ContextBuilder::GetCFileReputationContext(v22, v21);
  LODWORD(v17) = 0;
  v9 = CheckFileReputation(v21, &v17);
  if ( v9 >= 0 )
    *(_DWORD *)(a2 + 16) = TranslateAppReputationResult((unsigned int)v17);
  ContextBuilder::~ContextBuilder((ContextBuilder *)v22);
  path::~path((path *)v20);
  AllowSetForegroundWindow(ProcessId);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400324fc  mov     [rsp-8+arg_10], rbx
0x140032501  mov     [rsp-8+arg_18], rsi
0x140032506  push    rbp
0x140032507  push    rdi
0x140032508  push    r13
0x14003250a  push    r14
0x14003250c  push    r15
0x14003250e  lea     rbp, [rsp-220h]
0x140032516  sub     rsp, 320h
0x14003251d  mov     rax, cs:__security_cookie
0x140032524  xor     rax, rsp
0x140032527  mov     [rbp+240h+var_30], rax
0x14003252e  mov     r13, rdx
0x140032531  mov     r14, rcx
0x140032534  mov     rcx, [rcx]; Process
0x140032537  call    cs:__imp_GetProcessId
0x14003253d  mov     ebx, eax
0x14003253f  mov     [rsp+340h+var_310], eax
0x140032543  mov     [rsp+340h+var_30C], 1
0x140032548  xor     r15d, r15d
0x14003254b  lea     rcx, [r14+48h]
0x14003254f  call    ??$?9$$T@?$marshaled_ptr@UIWindow@SmartScreen@Security@Internal@Windows@@@com@@QEBA_NAEB$$T@Z
0x140032554  test    al, al
0x140032556  jz      short loc_140032564
0x140032558  lea     rcx, [r14+48h]
0x14003255c  call    GetIWindowHandle
0x140032561  mov     r15d, eax
0x140032564  mov     rcx, [r14]
0x140032567  mov     [rbp+240h+var_278], rcx
0x14003256b  mov     qword ptr [r14], 0
0x140032572  lea     rdx, [rbp+240h+var_278]
0x140032576  lea     rcx, [rbp+240h+var_270]
0x14003257a  call    process_from_handle
0x14003257f  nop
0x140032580  mov     sil, [r14+58h]
0x140032584  lea     rax, [rsp+340h+var_2F0]
0x140032589  mov     [rsp+340h+var_308], rax
0x14003258e  mov     eax, [rbp+240h+var_270]
0x140032591  mov     [rsp+340h+var_2F0], eax
0x140032595  movups  xmm0, [rbp+240h+var_268]
0x140032599  movdqu  [rsp+340h+var_2E8], xmm0
0x14003259f  lea     rdx, [rbp+240h+var_258]
0x1400325a3  lea     rcx, [rsp+340h+var_2D8]
0x1400325a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400325ad  nop
0x1400325ae  lea     rax, [rbp+240h+var_2B8]
0x1400325b2  mov     [rsp+340h+var_300], rax
0x1400325b7  lea     rdx, [r14+28h]
0x1400325bb  lea     rcx, [rbp+240h+var_2B8]
0x1400325bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400325c4  mov     rdi, rax
0x1400325c7  lea     rdx, [r14+8]
0x1400325cb  lea     rcx, [rbp+240h+var_298]
0x1400325cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400325d4  nop
0x1400325d5  mov     [rsp+340h+var_318], sil
0x1400325da  lea     rcx, [rsp+340h+var_2F0]
0x1400325df  mov     [rsp+340h+var_320], rcx
0x1400325e4  mov     r9d, r15d
0x1400325e7  mov     r8, rdi
0x1400325ea  mov     rdx, rax
0x1400325ed  lea     rcx, [rbp+240h+var_1B0]
0x1400325f4  call    ??0ContextBuilder@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0IUprocess_information@@_N@Z; ContextBuilder::ContextBuilder(std::wstring,std::wstring,uint,process_information,bool)
0x1400325f9  nop
0x1400325fa  lea     rdx, [rbp+240h+var_230]
0x1400325fe  lea     rcx, [rbp+240h+var_1B0]
0x140032605  call    ?GetCFileReputationContext@ContextBuilder@@QEAA?AUCFileReputationContext@@XZ; ContextBuilder::GetCFileReputationContext(void)
0x14003260a  mov     dword ptr [rbp+240h+var_278], 0
0x140032611  lea     rdx, [rbp+240h+var_278]
0x140032615  lea     rcx, [rbp+240h+var_230]
0x140032619  call    cs:__imp_CheckFileReputation
0x14003261f  mov     edi, eax
0x140032621  test    eax, eax
0x140032623  js      short loc_140032631
0x140032625  mov     ecx, dword ptr [rbp+240h+var_278]
0x140032628  call    TranslateAppReputationResult
0x14003262d  mov     [r13+10h], eax
0x140032631  lea     rcx, [rbp+240h+var_1B0]; this
0x140032638  call    ??1ContextBuilder@@QEAA@XZ; ContextBuilder::~ContextBuilder(void)
0x14003263d  nop
0x14003263e  lea     rcx, [rbp+240h+var_258]; this
0x140032642  call    ??1path@@QEAA@XZ; path::~path(void)
0x140032647  nop
0x140032648  mov     ecx, ebx; dwProcessId
0x14003264a  call    cs:__imp_AllowSetForegroundWindow
0x140032650  mov     eax, edi
0x140032652  mov     rcx, [rbp+240h+var_30]
0x140032659  xor     rcx, rsp; StackCookie
0x14003265c  call    __security_check_cookie
0x140032661  lea     r11, [rsp+340h+var_20]
0x140032669  mov     rbx, [r11+40h]
0x14003266d  mov     rsi, [r11+48h]
0x140032671  mov     rsp, r11
0x140032674  pop     r15
0x140032676  pop     r14
0x140032678  pop     r13
0x14003267a  pop     rdi
0x14003267b  pop     rbp
0x14003267c  retn
```
