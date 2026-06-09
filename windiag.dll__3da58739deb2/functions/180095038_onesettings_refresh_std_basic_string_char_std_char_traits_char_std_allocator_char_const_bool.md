# onesettings::refresh(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool)

- ea: `0x180095038`
- end: `0x1800951e8`
- name: `?refresh@onesettings@@YA?AV?$unique_ptr@Upayload@onesettings@@U?$default_delete@Upayload@onesettings@@@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@_N@Z`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007cd80`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x180094a14`
- `0x180095038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800950dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800950dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180095079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180095079`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009508c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009508c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095106`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800950d2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800950d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall onesettings::refresh(__int64 a1, __int64 a2, char a3)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v7; // r8
  DWORD v8; // eax
  bool v9; // di
  void *v10; // rcx
  bool v12; // [rsp+30h] [rbp-D0h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-CCh] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+70h] [rbp-90h] BYREF
  char v18; // [rsp+4E0h] [rbp+3E0h] BYREF

  v18 = a3;
  TokenHandle[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "check_for_extended_capabilities",
        75);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  ReturnLength = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation(TokenHandle[0], TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    v8 = GetLastError();
    if ( v8 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v8,
        0,
        "[%s:%d] failed; ",
        "check_for_extended_capabilities",
        78);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v9 = TokenInformation != 0;
  v10 = TokenHandle[0];
  if ( TokenHandle[0] )
  {
    TokenHandle[0] = 0;
    CloseHandle(v10);
  }
  v12 = v9;
  v16[0] = a2;
  v16[1] = &v12;
  v16[2] = &v18;
  *(_OWORD *)TokenHandle = *(_OWORD *)&off_18009FDE8;
  anonymous_namespace_::try_winrt__lambda_c3595caa5402c3d79b445e63dcca546c___(a1, v16, v7, TokenHandle);
  return a1;
}

```

## disassembly

```asm
0x180095038  mov     [rsp-8+arg_8], rbx
0x18009503d  mov     [rsp-8+arg_10], r8b
0x180095042  push    rbp
0x180095043  push    rsi
0x180095044  push    rdi
0x180095045  lea     rbp, [rsp-3B0h]
0x18009504d  sub     rsp, 4B0h
0x180095054  mov     rax, cs:__security_cookie
0x18009505b  xor     rax, rsp
0x18009505e  mov     [rbp+3C0h+var_20], rax
0x180095065  mov     rsi, rdx
0x180095068  mov     rbx, rcx
0x18009506b  mov     [rsp+4C0h+TokenHandle], rcx
0x180095070  mov     [rsp+4C0h+TokenHandle], 0
0x180095079  call    cs:__imp_GetCurrentProcess
0x18009507f  lea     r8, [rsp+4C0h+TokenHandle]; TokenHandle
0x180095084  mov     edx, 8; DesiredAccess
0x180095089  mov     rcx, rax; ProcessHandle
0x18009508c  call    cs:__imp_OpenProcessToken
0x180095092  test    eax, eax
0x180095094  jnz     short loc_1800950A4
0x180095096  call    cs:__imp_GetLastError
0x18009509c  test    eax, eax
0x18009509e  jnz     loc_1800951AC
0x1800950a4  mov     [rsp+4C0h+var_488], 0
0x1800950ac  mov     [rsp+4C0h+TokenInformation], 0
0x1800950b4  lea     rax, [rsp+4C0h+var_488]
0x1800950b9  mov     [rsp+4C0h+ReturnLength], rax; ReturnLength
0x1800950be  mov     r9d, 4; TokenInformationLength
0x1800950c4  lea     r8, [rsp+4C0h+TokenInformation]; TokenInformation
0x1800950c9  lea     edx, [r9+8]; TokenInformationClass
0x1800950cd  mov     rcx, [rsp+4C0h+TokenHandle]; TokenHandle
0x1800950d2  call    cs:__imp_GetTokenInformation
0x1800950d8  test    eax, eax
0x1800950da  jnz     short loc_1800950EA
0x1800950dc  call    cs:__imp_GetLastError
0x1800950e2  test    eax, eax
0x1800950e4  jnz     loc_180095170
0x1800950ea  cmp     [rsp+4C0h+TokenInformation], 0
0x1800950ef  setnz   dil
0x1800950f3  mov     rcx, [rsp+4C0h+TokenHandle]; hObject
0x1800950f8  test    rcx, rcx
0x1800950fb  jz      short loc_18009510C
0x1800950fd  mov     [rsp+4C0h+TokenHandle], 0
0x180095106  call    cs:__imp_CloseHandle
0x18009510c  mov     [rsp+4C0h+var_490], dil
0x180095111  mov     [rsp+4C0h+var_468], rsi
0x180095116  lea     rax, [rsp+4C0h+var_490]
0x18009511b  mov     [rsp+4C0h+var_460], rax
0x180095120  lea     rax, [rbp+3C0h+arg_10]
0x180095127  mov     [rsp+4C0h+var_458], rax
0x18009512c  movups  xmm0, xmmword ptr cs:off_18009FDE8
0x180095133  movdqu  xmmword ptr [rsp+4C0h+TokenHandle], xmm0
0x180095139  lea     r9, [rsp+4C0h+TokenHandle]
0x18009513e  lea     rdx, [rsp+4C0h+var_468]
0x180095143  mov     rcx, rbx
0x180095146  call    _anonymous_namespace___try_winrt__lambda_c3595caa5402c3d79b445e63dcca546c___
0x18009514b  mov     rax, rbx
0x18009514e  mov     rcx, [rbp+3C0h+var_20]
0x180095155  xor     rcx, rsp; StackCookie
0x180095158  call    __security_check_cookie
0x18009515d  mov     rbx, [rsp+4C0h+arg_8]
0x180095165  add     rsp, 4B0h
0x18009516c  pop     rdi
0x18009516d  pop     rsi
0x18009516e  pop     rbp
0x18009516f  retn
0x180095170  mov     edx, eax; __int64
0x180095172  mov     [rsp+4C0h+var_498], 4Eh ; 'N'
0x18009517a  lea     rax, aCheckForExtend; "check_for_extended_capabilities"
0x180095181  mov     [rsp+4C0h+ReturnLength], rax
0x180095186  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18009518d  xor     r8d, r8d; void *
0x180095190  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x180095195  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18009519a  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800951a1  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x1800951a6  call    _CxxThrowException_0
0x1800951ac  mov     edx, eax; __int64
0x1800951ae  mov     [rsp+4C0h+var_498], 4Bh ; 'K'
0x1800951b6  lea     rax, aCheckForExtend; "check_for_extended_capabilities"
0x1800951bd  mov     [rsp+4C0h+ReturnLength], rax
0x1800951c2  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800951c9  xor     r8d, r8d; void *
0x1800951cc  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x1800951d1  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800951d6  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800951dd  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x1800951e2  call    _CxxThrowException_0
```
