# COSInstaller::Pause(void)

- ea: `0x180028900`
- end: `0x180028ac7`
- name: `?Pause@COSInstaller@@UEAAJXZ`
- size: `455`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180003950`
- `0x18000956c`
- `0x180028900`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002893c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002893c`

## string_xrefs

- `0x180028958`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180028a57`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSInstaller::Pause(COSInstaller *this)
{
  __int64 v2; // rsi
  char *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 v5; // rcx
  int v6; // edi
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-28h]
  int v10; // [rsp+20h] [rbp-28h]
  __int64 v11; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  v11 = 0;
  v3 = (char *)this + 64;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  if ( this != (COSInstaller *)-64LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    v2 = *((_QWORD *)this + 14);
    if ( v3 )
      LeaveCriticalSection(v4);
    v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v2)(
           v2,
           &GUID_7d79e71d_36c6_4a20_bab0_0e44763c8ba9,
           &v11);
    if ( v6 >= 0 )
    {
      WUTrace(0, 0, 4096, 4);
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 120LL))(v11);
      if ( v6 >= 0 )
      {
        v6 = 0;
        goto LABEL_14;
      }
      v10 = v6;
      WUTrace(0, 0, 4096, 2);
      v7 = 719;
    }
    else
    {
      v10 = v6;
      WUTrace(0, 0, 4096, 4);
      v7 = 710;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v6,
      v10);
    goto LABEL_14;
  }
  v6 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2BC,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)0x8000FFFFLL,
    v9);
  if ( v3 )
    LeaveCriticalSection(v4);
LABEL_14:
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180028900  mov     r11, rsp
0x180028903  mov     [r11+10h], rbx
0x180028907  mov     [r11+18h], rbp
0x18002890b  mov     [r11+20h], rsi
0x18002890f  push    rdi
0x180028910  sub     rsp, 40h
0x180028914  mov     rax, cs:__security_cookie
0x18002891b  xor     rax, rsp
0x18002891e  mov     [rsp+48h+var_10], rax
0x180028923  mov     rdi, rcx
0x180028926  xor     esi, esi
0x180028928  mov     [r11-18h], rsi
0x18002892c  lea     rbx, [rcx+40h]
0x180028930  lea     rbp, [rbx+8]
0x180028934  test    rbx, rbx
0x180028937  jz      short loc_180028942
0x180028939  mov     rcx, rbp; lpCriticalSection
0x18002893c  call    cs:__imp_EnterCriticalSection
0x180028942  mov     rcx, [rdi+70h]
0x180028946  test    rcx, rcx
0x180028949  jnz     short loc_180028980
0x18002894b  mov     rcx, [rsp+48h]; this
0x180028950  mov     edi, 8000FFFFh
0x180028955  mov     r9d, edi; char *
0x180028958  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002895f  mov     edx, 2BCh; void *
0x180028964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028969  test    rbx, rbx
0x18002896c  jz      loc_180028A6F
0x180028972  mov     rcx, rbp; lpCriticalSection
0x180028975  call    cs:__imp_LeaveCriticalSection
0x18002897b  jmp     loc_180028A6F
0x180028980  mov     rax, [rcx]
0x180028983  mov     rax, [rax+8]
0x180028987  call    _guard_dispatch_icall
0x18002898c  mov     rsi, [rdi+70h]
0x180028990  test    rbx, rbx
0x180028993  jz      short loc_18002899E
0x180028995  mov     rcx, rbp; lpCriticalSection
0x180028998  call    cs:__imp_LeaveCriticalSection
0x18002899e  mov     rcx, [rsp+48h+var_18]
0x1800289a3  test    rcx, rcx
0x1800289a6  jz      short loc_1800289B4
0x1800289a8  mov     rax, [rcx]
0x1800289ab  mov     rax, [rax+10h]
0x1800289af  call    _guard_dispatch_icall
0x1800289b4  mov     rax, [rsi]
0x1800289b7  lea     r8, [rsp+48h+var_18]
0x1800289bc  lea     rdx, _GUID_7d79e71d_36c6_4a20_bab0_0e44763c8ba9
0x1800289c3  mov     rcx, rsi
0x1800289c6  mov     rax, [rax]
0x1800289c9  call    _guard_dispatch_icall
0x1800289ce  mov     edi, eax
0x1800289d0  xor     edx, edx
0x1800289d2  xor     ecx, ecx
0x1800289d4  lea     r9d, [rdx+4]
0x1800289d8  mov     r8d, 1000h
0x1800289de  test    eax, eax
0x1800289e0  jns     short loc_1800289FE
0x1800289e2  lea     rax, aPauseApiNotAva; "Pause API not available"
0x1800289e9  mov     [rsp+48h+var_20], rax
0x1800289ee  mov     [rsp+48h+var_28], edi
0x1800289f2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800289f7  mov     edx, 2C6h
0x1800289fc  jmp     short loc_180028A57
0x1800289fe  lea     rax, aCallingPause; "Calling Pause"
0x180028a05  mov     [rsp+48h+var_20], rax
0x180028a0a  mov     qword ptr [rsp+48h+var_28], 0
0x180028a13  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028a18  mov     rcx, [rsp+48h+var_18]
0x180028a1d  mov     rax, [rcx]
0x180028a20  mov     rax, [rax+78h]
0x180028a24  call    _guard_dispatch_icall
0x180028a29  mov     edi, eax
0x180028a2b  test    eax, eax
0x180028a2d  jns     short loc_180028A6D
0x180028a2f  lea     rax, aCallingPauseFa; "Calling Pause FAILED"
0x180028a36  mov     [rsp+48h+var_20], rax
0x180028a3b  mov     [rsp+48h+var_28], edi; int
0x180028a3f  xor     edx, edx
0x180028a41  xor     ecx, ecx
0x180028a43  lea     r9d, [rdx+2]
0x180028a47  mov     r8d, 1000h
0x180028a4d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028a52  mov     edx, 2CFh; void *
0x180028a57  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180028a5e  mov     r9d, edi; char *
0x180028a61  mov     rcx, [rsp+48h]; this
0x180028a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a6b  jmp     short loc_180028A6F
0x180028a6d  xor     edi, edi
0x180028a6f  mov     rcx, [rsp+48h+var_18]
0x180028a74  test    rcx, rcx
0x180028a77  jz      short loc_180028A8E
0x180028a79  mov     rax, [rcx]
0x180028a7c  mov     rax, [rax+10h]
0x180028a80  call    _guard_dispatch_icall
0x180028a85  mov     [rsp+48h+var_18], 0
0x180028a8e  test    rsi, rsi
0x180028a91  jz      short loc_180028AA3
0x180028a93  mov     rcx, [rsi]
0x180028a96  mov     rax, [rcx+10h]
0x180028a9a  mov     rcx, rsi
0x180028a9d  call    _guard_dispatch_icall
0x180028aa2  nop
0x180028aa3  mov     eax, edi
0x180028aa5  mov     rcx, [rsp+48h+var_10]
0x180028aaa  xor     rcx, rsp; StackCookie
0x180028aad  call    __security_check_cookie
0x180028ab2  mov     rbx, [rsp+48h+arg_8]
0x180028ab7  mov     rbp, [rsp+48h+arg_10]
0x180028abc  mov     rsi, [rsp+48h+arg_18]
0x180028ac1  add     rsp, 40h
0x180028ac5  pop     rdi
0x180028ac6  retn
```
