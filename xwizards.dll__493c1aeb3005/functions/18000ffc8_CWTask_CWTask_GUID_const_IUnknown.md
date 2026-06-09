# CWTask::CWTask(_GUID const *,IUnknown *)

- ea: `0x18000ffc8`
- end: `0x180010203`
- name: `??0CWTask@@AEAA@PEBU_GUID@@PEAUIUnknown@@@Z`
- size: `571`
- prototype: `CWTask *(CWTask *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010b0c`

## callees

- `0x18000ae04`
- `0x18000ffc8`
- `0x18001c19c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001010f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010123`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010137`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001014b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001015f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010173`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010187`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001019e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001010f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010123`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010137`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001014b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001015f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010173`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010187`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001019e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101e3`

## string_xrefs

- `0x1800100cc`: `XWCanHostTask`
- `0x1800100dc`: `XWCanRunTask`
- `0x18001017c`: `XWOnCommit`

## pseudocode

```c
CWTask *__fastcall CWTask::CWTask(CWTask *this, const struct _GUID *a2, struct IUnknown *a3)
{
  struct IUnknown *v3; // rax
  HMODULE *v5; // rdi
  int WizardCommonModule; // eax
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  HMODULE v16; // rcx
  FARPROC v17; // rax
  HMODULE v18; // rcx
  FARPROC v19; // rax
  HMODULE v20; // rcx
  FARPROC v21; // rax
  HMODULE v22; // rcx
  FARPROC v23; // rax
  HMODULE v24; // rcx
  FARPROC v25; // rax
  HMODULE v26; // rcx
  FARPROC v27; // rax
  HMODULE v28; // rcx
  FARPROC v29; // rax
  HMODULE v30; // rcx
  FARPROC v31; // rax
  HMODULE v32; // rcx

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CUnknown::`vftable';
  v3 = (struct IUnknown *)this;
  if ( a3 )
    v3 = a3;
  *((_QWORD *)this + 2) = v3;
  _InterlockedIncrement(&CUnknown::s_cActiveComponents);
  v5 = (HMODULE *)((char *)this + 48);
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *(_QWORD *)this = &CWTask::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CWTask::`vftable'{for `IXWizardTaskEvent'};
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 6) = 0;
  *((struct _GUID *)this + 2) = *a2;
  WizardCommonModule = HrGetWizardCommonModule(a2, (HINSTANCE *)this + 6);
  if ( WizardCommonModule >= 0 )
  {
    ProcAddress = GetProcAddress(*v5, "XWCanHostTask");
    v8 = *v5;
    *((_QWORD *)this + 7) = ProcAddress;
    v9 = GetProcAddress(v8, "XWCanRunTask");
    v10 = *v5;
    *((_QWORD *)this + 8) = v9;
    v11 = GetProcAddress(v10, "XWCanRegisterPage");
    v12 = *v5;
    *((_QWORD *)this + 9) = v11;
    v13 = GetProcAddress(v12, "XWCanUnregisterPage");
    v14 = *v5;
    *((_QWORD *)this + 10) = v13;
    v15 = GetProcAddress(v14, "XWCanNavigatePage");
    v16 = *v5;
    *((_QWORD *)this + 11) = v15;
    v17 = GetProcAddress(v16, "XWOnRecyclePage");
    v18 = *v5;
    *((_QWORD *)this + 12) = v17;
    v19 = GetProcAddress(v18, "XWOnGetWizardTypesSupported");
    v20 = *v5;
    *((_QWORD *)this + 13) = v19;
    v21 = GetProcAddress(v20, "XWOnApply");
    v22 = *v5;
    *((_QWORD *)this + 14) = v21;
    v23 = GetProcAddress(v22, "XWOnReset");
    v24 = *v5;
    *((_QWORD *)this + 15) = v23;
    v25 = GetProcAddress(v24, "XWOnCommit");
    v26 = *v5;
    *((_QWORD *)this + 16) = v25;
    v27 = GetProcAddress(v26, "XWOnAbort");
    v28 = *v5;
    *((_QWORD *)this + 17) = v27;
    v29 = GetProcAddress(v28, "XWOnError");
    v30 = *v5;
    *((_QWORD *)this + 18) = v29;
    v31 = GetProcAddress(v30, "XWOnDisplay");
    v32 = *v5;
    *((_QWORD *)this + 19) = v31;
    *((_QWORD *)this + 20) = GetProcAddress(v32, "XWOnLog");
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids,
      (unsigned int)WizardCommonModule);
  }
  return this;
}

```

## disassembly

```asm
0x18000ffc8  mov     [rsp+arg_0], rbx
0x18000ffcd  mov     [rsp+arg_8], rsi
0x18000ffd2  push    rdi
0x18000ffd3  sub     rsp, 20h
0x18000ffd7  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x18000ffde  mov     dword ptr [rcx+8], 1
0x18000ffe5  mov     [rcx], rax
0x18000ffe8  xor     esi, esi
0x18000ffea  test    r8, r8
0x18000ffed  mov     rax, rcx
0x18000fff0  mov     r9, rdx
0x18000fff3  mov     rbx, rcx
0x18000fff6  cmovnz  rax, r8
0x18000fffa  mov     [rcx+10h], rax
0x18000fffe  lock inc cs:?s_cActiveComponents@CUnknown@@0JA; long CUnknown::s_cActiveComponents
0x180010005  lea     rdi, [rcx+30h]
0x180010009  mov     [rcx+0A8h], rsi
0x180010010  mov     [rcx+0B0h], rsi
0x180010017  lea     rax, ??_7CWTask@@6BCUnknown@@@; const CWTask::`vftable'{for `CUnknown'}
0x18001001e  mov     [rcx], rax
0x180010021  lea     rax, ??_7CWTask@@6BIXWizardTaskEvent@@@; const CWTask::`vftable'{for `IXWizardTaskEvent'}
0x180010028  mov     [rcx+18h], rax
0x18001002c  mov     [rcx+38h], rsi
0x180010030  mov     [rcx+40h], rsi
0x180010034  mov     [rcx+48h], rsi
0x180010038  mov     [rcx+50h], rsi
0x18001003c  mov     [rcx+58h], rsi
0x180010040  mov     [rcx+60h], rsi
0x180010044  mov     [rcx+68h], rsi
0x180010048  mov     [rcx+70h], rsi
0x18001004c  mov     [rcx+78h], rsi
0x180010050  mov     [rcx+80h], rsi
0x180010057  mov     [rcx+88h], rsi
0x18001005e  mov     [rcx+90h], rsi
0x180010065  mov     [rcx+98h], rsi
0x18001006c  mov     [rcx+0A0h], rsi
0x180010073  mov     [rdi], rsi
0x180010076  movups  xmm0, xmmword ptr [rdx]
0x180010079  mov     rdx, rdi; HINSTANCE *
0x18001007c  movdqu  xmmword ptr [rcx+20h], xmm0
0x180010081  mov     rcx, r9; struct _GUID *
0x180010084  call    ?HrGetWizardCommonModule@@YAJPEBU_GUID@@PEAPEAUHINSTANCE__@@@Z; HrGetWizardCommonModule(_GUID const *,HINSTANCE__ * *)
0x180010089  test    eax, eax
0x18001008b  jns     short loc_1800100C9
0x18001008d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010094  lea     rdx, WPP_GLOBAL_Control
0x18001009b  cmp     rcx, rdx
0x18001009e  jz      loc_1800101F0
0x1800100a4  test    byte ptr [rcx+1Ch], 4
0x1800100a8  jz      loc_1800101F0
0x1800100ae  mov     rcx, [rcx+10h]
0x1800100b2  lea     edx, [rsi+0Ah]
0x1800100b5  mov     r9d, eax
0x1800100b8  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x1800100bf  call    WPP_SF_d
0x1800100c4  jmp     loc_1800101F0
0x1800100c9  mov     rcx, [rdi]; hModule
0x1800100cc  lea     rdx, aXwcanhosttask; "XWCanHostTask"
0x1800100d3  call    cs:__imp_GetProcAddress
0x1800100d9  mov     rcx, [rdi]; hModule
0x1800100dc  lea     rdx, aXwcanruntask; "XWCanRunTask"
0x1800100e3  mov     [rbx+38h], rax
0x1800100e7  call    cs:__imp_GetProcAddress
0x1800100ed  mov     rcx, [rdi]; hModule
0x1800100f0  lea     rdx, aXwcanregisterp; "XWCanRegisterPage"
0x1800100f7  mov     [rbx+40h], rax
0x1800100fb  call    cs:__imp_GetProcAddress
0x180010101  mov     rcx, [rdi]; hModule
0x180010104  lea     rdx, aXwcanunregiste; "XWCanUnregisterPage"
0x18001010b  mov     [rbx+48h], rax
0x18001010f  call    cs:__imp_GetProcAddress
0x180010115  mov     rcx, [rdi]; hModule
0x180010118  lea     rdx, aXwcannavigatep; "XWCanNavigatePage"
0x18001011f  mov     [rbx+50h], rax
0x180010123  call    cs:__imp_GetProcAddress
0x180010129  mov     rcx, [rdi]; hModule
0x18001012c  lea     rdx, aXwonrecyclepag; "XWOnRecyclePage"
0x180010133  mov     [rbx+58h], rax
0x180010137  call    cs:__imp_GetProcAddress
0x18001013d  mov     rcx, [rdi]; hModule
0x180010140  lea     rdx, aXwongetwizardt; "XWOnGetWizardTypesSupported"
0x180010147  mov     [rbx+60h], rax
0x18001014b  call    cs:__imp_GetProcAddress
0x180010151  mov     rcx, [rdi]; hModule
0x180010154  lea     rdx, aXwonapply; "XWOnApply"
0x18001015b  mov     [rbx+68h], rax
0x18001015f  call    cs:__imp_GetProcAddress
0x180010165  mov     rcx, [rdi]; hModule
0x180010168  lea     rdx, aXwonreset; "XWOnReset"
0x18001016f  mov     [rbx+70h], rax
0x180010173  call    cs:__imp_GetProcAddress
0x180010179  mov     rcx, [rdi]; hModule
0x18001017c  lea     rdx, aXwoncommit; "XWOnCommit"
0x180010183  mov     [rbx+78h], rax
0x180010187  call    cs:__imp_GetProcAddress
0x18001018d  mov     rcx, [rdi]; hModule
0x180010190  lea     rdx, aXwonabort; "XWOnAbort"
0x180010197  mov     [rbx+80h], rax
0x18001019e  call    cs:__imp_GetProcAddress
0x1800101a4  mov     rcx, [rdi]; hModule
0x1800101a7  lea     rdx, aXwonerror; "XWOnError"
0x1800101ae  mov     [rbx+88h], rax
0x1800101b5  call    cs:__imp_GetProcAddress
0x1800101bb  mov     rcx, [rdi]; hModule
0x1800101be  lea     rdx, aXwondisplay; "XWOnDisplay"
0x1800101c5  mov     [rbx+90h], rax
0x1800101cc  call    cs:__imp_GetProcAddress
0x1800101d2  mov     rcx, [rdi]; hModule
0x1800101d5  lea     rdx, aXwonlog; "XWOnLog"
0x1800101dc  mov     [rbx+98h], rax
0x1800101e3  call    cs:__imp_GetProcAddress
0x1800101e9  mov     [rbx+0A0h], rax
0x1800101f0  mov     rsi, [rsp+28h+arg_8]
0x1800101f5  mov     rax, rbx
0x1800101f8  mov     rbx, [rsp+28h+arg_0]
0x1800101fd  add     rsp, 20h
0x180010201  pop     rdi
0x180010202  retn
```
