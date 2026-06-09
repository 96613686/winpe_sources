# COSInstaller::put_Priority(tagDeploymentHandlerPriority)

- ea: `0x180028ca0`
- end: `0x180028ea2`
- name: `?put_Priority@COSInstaller@@UEAAJW4tagDeploymentHandlerPriority@@@Z`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180003950`
- `0x18000956c`
- `0x180028ca0`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028cfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028cfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028cde`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028cde`

## string_xrefs

- `0x180028dfd`: `UpdatePriority`
- `0x180028e89`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSInstaller::put_Priority(__int64 a1, int a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v10; // rdx
  __int64 v11; // rbp
  int v12; // ecx
  int v13; // [rsp+20h] [rbp-48h]
  __int64 v14; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = 0;
  v14 = 0;
  v5 = a1 + 64;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 72);
  if ( a1 != -64 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  *(_DWORD *)(a1 + 168) = a2;
  v7 = *(_QWORD *)(a1 + 112);
  if ( !v7 )
  {
    if ( v5 )
      LeaveCriticalSection(v6);
LABEL_6:
    v8 = 0;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v4 = *(_QWORD *)(a1 + 112);
  if ( v5 )
    LeaveCriticalSection(v6);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v4)(
         v4,
         &GUID_57816c47_d685_423a_89c6_feefbd90ed47,
         &v14);
  if ( v8 >= 0 )
  {
    v11 = 0;
    v12 = *(_DWORD *)(a1 + 168);
    if ( v12 )
    {
      if ( v12 == 1 )
        v11 = 2;
    }
    else
    {
      v11 = 1;
    }
    WUTrace(0, 0, 4096, 4);
    v8 = (*(__int64 (**)(__int64, _QWORD, const wchar_t *, __int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v14 + 168LL))(
           v14,
           0,
           L"UpdatePriority",
           v11,
           0,
           L"Calling SetAttributeInt [%ws, %lld]",
           L"UpdatePriority",
           v11);
    if ( v8 >= 0 )
      goto LABEL_6;
    v13 = v8;
    WUTrace(0, 0, 4096, 4);
    v10 = 822;
  }
  else
  {
    v13 = v8;
    WUTrace(0, 0, 4096, 4);
    v10 = 792;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)(unsigned int)v8,
    v13);
LABEL_7:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028ca0  mov     [rsp+arg_8], rbx
0x180028ca5  mov     [rsp+arg_10], rbp
0x180028caa  push    rsi
0x180028cab  push    rdi
0x180028cac  push    r14
0x180028cae  sub     rsp, 50h
0x180028cb2  mov     rax, cs:__security_cookie
0x180028cb9  xor     rax, rsp
0x180028cbc  mov     [rsp+68h+var_20], rax
0x180028cc1  mov     r14d, edx
0x180028cc4  mov     rdi, rcx
0x180028cc7  xor     esi, esi
0x180028cc9  mov     [rsp+68h+var_28], rsi
0x180028cce  lea     rbx, [rcx+40h]
0x180028cd2  lea     rbp, [rbx+8]
0x180028cd6  test    rbx, rbx
0x180028cd9  jz      short loc_180028CE4
0x180028cdb  mov     rcx, rbp; lpCriticalSection
0x180028cde  call    cs:__imp_EnterCriticalSection
0x180028ce4  mov     [rdi+0A8h], r14d
0x180028ceb  mov     rcx, [rdi+70h]
0x180028cef  test    rcx, rcx
0x180028cf2  jnz     short loc_180028D5C
0x180028cf4  test    rbx, rbx
0x180028cf7  jz      short loc_180028D02
0x180028cf9  mov     rcx, rbp; lpCriticalSection
0x180028cfc  call    cs:__imp_LeaveCriticalSection
0x180028d02  xor     ebx, ebx
0x180028d04  mov     rcx, [rsp+68h+var_28]
0x180028d09  test    rcx, rcx
0x180028d0c  jz      short loc_180028D23
0x180028d0e  mov     rax, [rcx]
0x180028d11  mov     rax, [rax+10h]
0x180028d15  call    _guard_dispatch_icall
0x180028d1a  mov     [rsp+68h+var_28], 0
0x180028d23  test    rsi, rsi
0x180028d26  jz      short loc_180028D38
0x180028d28  mov     rcx, [rsi]
0x180028d2b  mov     rax, [rcx+10h]
0x180028d2f  mov     rcx, rsi
0x180028d32  call    _guard_dispatch_icall
0x180028d37  nop
0x180028d38  mov     eax, ebx
0x180028d3a  mov     rcx, [rsp+68h+var_20]
0x180028d3f  xor     rcx, rsp; StackCookie
0x180028d42  call    __security_check_cookie
0x180028d47  lea     r11, [rsp+68h+var_18]
0x180028d4c  mov     rbx, [r11+28h]
0x180028d50  mov     rbp, [r11+30h]
0x180028d54  mov     rsp, r11
0x180028d57  pop     r14
0x180028d59  pop     rdi
0x180028d5a  pop     rsi
0x180028d5b  retn
0x180028d5c  mov     rax, [rcx]
0x180028d5f  mov     rax, [rax+8]
0x180028d63  call    _guard_dispatch_icall
0x180028d68  mov     rsi, [rdi+70h]
0x180028d6c  test    rbx, rbx
0x180028d6f  jz      short loc_180028D7A
0x180028d71  mov     rcx, rbp; lpCriticalSection
0x180028d74  call    cs:__imp_LeaveCriticalSection
0x180028d7a  mov     rcx, [rsp+68h+var_28]
0x180028d7f  test    rcx, rcx
0x180028d82  jz      short loc_180028D90
0x180028d84  mov     rax, [rcx]
0x180028d87  mov     rax, [rax+10h]
0x180028d8b  call    _guard_dispatch_icall
0x180028d90  mov     rax, [rsi]
0x180028d93  lea     r8, [rsp+68h+var_28]
0x180028d98  lea     rdx, _GUID_57816c47_d685_423a_89c6_feefbd90ed47
0x180028d9f  mov     rcx, rsi
0x180028da2  mov     rax, [rax]
0x180028da5  call    _guard_dispatch_icall
0x180028daa  mov     ebx, eax
0x180028dac  test    eax, eax
0x180028dae  jns     short loc_180028DDD
0x180028db0  lea     rax, aSetattributein; "SetAttributeInt API not available"
0x180028db7  mov     [rsp+68h+var_40], rax
0x180028dbc  mov     [rsp+68h+var_48], ebx
0x180028dc0  xor     edx, edx
0x180028dc2  xor     ecx, ecx
0x180028dc4  lea     r9d, [rdx+4]
0x180028dc8  mov     r8d, 1000h
0x180028dce  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028dd3  mov     edx, 318h
0x180028dd8  jmp     loc_180028E89
0x180028ddd  xor     ebp, ebp
0x180028ddf  mov     ecx, [rdi+0A8h]
0x180028de5  test    ecx, ecx
0x180028de7  jz      short loc_180028DF3
0x180028de9  cmp     ecx, 1
0x180028dec  jnz     short loc_180028DF8
0x180028dee  lea     ebp, [rcx+1]
0x180028df1  jmp     short loc_180028DF8
0x180028df3  mov     ebp, 1
0x180028df8  mov     [rsp+68h+var_30], rbp
0x180028dfd  lea     rdi, aUpdatepriority; "UpdatePriority"
0x180028e04  mov     [rsp+68h+var_38], rdi
0x180028e09  lea     rax, aCallingSetattr; "Calling SetAttributeInt [%ws, %lld]"
0x180028e10  mov     [rsp+68h+var_40], rax
0x180028e15  mov     qword ptr [rsp+68h+var_48], 0
0x180028e1e  xor     edx, edx
0x180028e20  xor     ecx, ecx
0x180028e22  lea     r9d, [rdx+4]
0x180028e26  mov     r8d, 1000h
0x180028e2c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028e31  mov     rcx, [rsp+68h+var_28]
0x180028e36  mov     rax, [rcx]
0x180028e39  mov     r9, rbp
0x180028e3c  mov     r8, rdi
0x180028e3f  xor     edx, edx
0x180028e41  mov     rax, [rax+0A8h]
0x180028e48  call    _guard_dispatch_icall
0x180028e4d  mov     ebx, eax
0x180028e4f  test    eax, eax
0x180028e51  jns     loc_180028D02
0x180028e57  mov     [rsp+68h+var_30], rbp
0x180028e5c  mov     [rsp+68h+var_38], rdi
0x180028e61  lea     rax, aFailedToSetAtt; "Failed to set Attribute [%ws] value = %"...
0x180028e68  mov     [rsp+68h+var_40], rax
0x180028e6d  mov     [rsp+68h+var_48], ebx; int
0x180028e71  xor     edx, edx
0x180028e73  xor     ecx, ecx
0x180028e75  lea     r9d, [rdx+4]
0x180028e79  mov     r8d, 1000h
0x180028e7f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028e84  mov     edx, 336h; void *
0x180028e89  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180028e90  mov     r9d, ebx; char *
0x180028e93  mov     rcx, [rsp+68h]; this
0x180028e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028e9d  jmp     loc_180028D04
```
