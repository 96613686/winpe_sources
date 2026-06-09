# COSInstaller::Resume(void)

- ea: `0x180028ad0`
- end: `0x180028c9a`
- name: `?Resume@COSInstaller@@UEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180003950`
- `0x18000956c`
- `0x180028ad0`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b0c`

## string_xrefs

- `0x180028b28`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180028c2a`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSInstaller::Resume(COSInstaller *this)
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
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 128LL))(v11);
      if ( v6 >= 0 )
      {
        v6 = 0;
        goto LABEL_14;
      }
      v10 = v6;
      WUTrace(0, 0, 4096, 2);
      v7 = 760;
    }
    else
    {
      v10 = v6;
      WUTrace(0, 0, 4096, 4);
      v7 = 751;
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
    (void *)0x2E5,
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
0x180028ad0  mov     r11, rsp
0x180028ad3  mov     [r11+10h], rbx
0x180028ad7  mov     [r11+18h], rbp
0x180028adb  mov     [r11+20h], rsi
0x180028adf  push    rdi
0x180028ae0  sub     rsp, 40h
0x180028ae4  mov     rax, cs:__security_cookie
0x180028aeb  xor     rax, rsp
0x180028aee  mov     [rsp+48h+var_10], rax
0x180028af3  mov     rdi, rcx
0x180028af6  xor     esi, esi
0x180028af8  mov     [r11-18h], rsi
0x180028afc  lea     rbx, [rcx+40h]
0x180028b00  lea     rbp, [rbx+8]
0x180028b04  test    rbx, rbx
0x180028b07  jz      short loc_180028B12
0x180028b09  mov     rcx, rbp; lpCriticalSection
0x180028b0c  call    cs:__imp_EnterCriticalSection
0x180028b12  mov     rcx, [rdi+70h]
0x180028b16  test    rcx, rcx
0x180028b19  jnz     short loc_180028B50
0x180028b1b  mov     rcx, [rsp+48h]; this
0x180028b20  mov     edi, 8000FFFFh
0x180028b25  mov     r9d, edi; char *
0x180028b28  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180028b2f  mov     edx, 2E5h; void *
0x180028b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b39  test    rbx, rbx
0x180028b3c  jz      loc_180028C42
0x180028b42  mov     rcx, rbp; lpCriticalSection
0x180028b45  call    cs:__imp_LeaveCriticalSection
0x180028b4b  jmp     loc_180028C42
0x180028b50  mov     rax, [rcx]
0x180028b53  mov     rax, [rax+8]
0x180028b57  call    _guard_dispatch_icall
0x180028b5c  mov     rsi, [rdi+70h]
0x180028b60  test    rbx, rbx
0x180028b63  jz      short loc_180028B6E
0x180028b65  mov     rcx, rbp; lpCriticalSection
0x180028b68  call    cs:__imp_LeaveCriticalSection
0x180028b6e  mov     rcx, [rsp+48h+var_18]
0x180028b73  test    rcx, rcx
0x180028b76  jz      short loc_180028B84
0x180028b78  mov     rax, [rcx]
0x180028b7b  mov     rax, [rax+10h]
0x180028b7f  call    _guard_dispatch_icall
0x180028b84  mov     rax, [rsi]
0x180028b87  lea     r8, [rsp+48h+var_18]
0x180028b8c  lea     rdx, _GUID_7d79e71d_36c6_4a20_bab0_0e44763c8ba9
0x180028b93  mov     rcx, rsi
0x180028b96  mov     rax, [rax]
0x180028b99  call    _guard_dispatch_icall
0x180028b9e  mov     edi, eax
0x180028ba0  xor     edx, edx
0x180028ba2  xor     ecx, ecx
0x180028ba4  lea     r9d, [rdx+4]
0x180028ba8  mov     r8d, 1000h
0x180028bae  test    eax, eax
0x180028bb0  jns     short loc_180028BCE
0x180028bb2  lea     rax, aResumeApiNotAv; "Resume API not available"
0x180028bb9  mov     [rsp+48h+var_20], rax
0x180028bbe  mov     [rsp+48h+var_28], edi
0x180028bc2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028bc7  mov     edx, 2EFh
0x180028bcc  jmp     short loc_180028C2A
0x180028bce  lea     rax, aCallingResume; "Calling Resume"
0x180028bd5  mov     [rsp+48h+var_20], rax
0x180028bda  mov     qword ptr [rsp+48h+var_28], 0
0x180028be3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028be8  mov     rcx, [rsp+48h+var_18]
0x180028bed  mov     rax, [rcx]
0x180028bf0  mov     rax, [rax+80h]
0x180028bf7  call    _guard_dispatch_icall
0x180028bfc  mov     edi, eax
0x180028bfe  test    eax, eax
0x180028c00  jns     short loc_180028C40
0x180028c02  lea     rax, aCallingResumeF; "Calling Resume FAILED"
0x180028c09  mov     [rsp+48h+var_20], rax
0x180028c0e  mov     [rsp+48h+var_28], edi; int
0x180028c12  xor     edx, edx
0x180028c14  xor     ecx, ecx
0x180028c16  lea     r9d, [rdx+2]
0x180028c1a  mov     r8d, 1000h
0x180028c20  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028c25  mov     edx, 2F8h; void *
0x180028c2a  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180028c31  mov     r9d, edi; char *
0x180028c34  mov     rcx, [rsp+48h]; this
0x180028c39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c3e  jmp     short loc_180028C42
0x180028c40  xor     edi, edi
0x180028c42  mov     rcx, [rsp+48h+var_18]
0x180028c47  test    rcx, rcx
0x180028c4a  jz      short loc_180028C61
0x180028c4c  mov     rax, [rcx]
0x180028c4f  mov     rax, [rax+10h]
0x180028c53  call    _guard_dispatch_icall
0x180028c58  mov     [rsp+48h+var_18], 0
0x180028c61  test    rsi, rsi
0x180028c64  jz      short loc_180028C76
0x180028c66  mov     rcx, [rsi]
0x180028c69  mov     rax, [rcx+10h]
0x180028c6d  mov     rcx, rsi
0x180028c70  call    _guard_dispatch_icall
0x180028c75  nop
0x180028c76  mov     eax, edi
0x180028c78  mov     rcx, [rsp+48h+var_10]
0x180028c7d  xor     rcx, rsp; StackCookie
0x180028c80  call    __security_check_cookie
0x180028c85  mov     rbx, [rsp+48h+arg_8]
0x180028c8a  mov     rbp, [rsp+48h+arg_10]
0x180028c8f  mov     rsi, [rsp+48h+arg_18]
0x180028c94  add     rsp, 40h
0x180028c98  pop     rdi
0x180028c99  retn
```
