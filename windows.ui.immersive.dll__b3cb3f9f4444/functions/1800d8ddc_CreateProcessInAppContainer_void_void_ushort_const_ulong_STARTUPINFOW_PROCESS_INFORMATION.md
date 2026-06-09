# _CreateProcessInAppContainer(void *,void *,ushort const *,ulong,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x1800d8ddc`
- end: `0x1800d8f8a`
- name: `?_CreateProcessInAppContainer@@YAJPEAX0PEBGKPEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `430`
- prototype: `int(void *, void *, const unsigned __int16 *, unsigned int, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d92dc`

## callees

- `0x180006800`
- `0x18003d244`
- `0x180054ad4`
- `0x1800d8ddc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d8e1e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d8e6d`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d8e1e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d8e6d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800d8ec2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800d8ec2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800d8f3c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800d8f3c`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d8f5a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d8f5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8f69`

## pseudocode

```c
__int64 __fastcall _CreateProcessInAppContainer(
        void *a1,
        void *a2,
        WCHAR *a3,
        __int64 a4,
        struct _STARTUPINFOW *Size,
        LPPROCESS_INFORMATION a6)
{
  struct _PROCESS_INFORMATION *lpProcessInformation; // rsi
  void *v10; // rcx
  int Error; // ebx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v12; // rdi
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+60h] [rbp-79h] BYREF
  void *Value; // [rsp+68h] [rbp-71h] BYREF
  __int128 v16; // [rsp+70h] [rbp-69h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-59h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v18; // [rsp+E8h] [rbp+Fh]

  lpProcessInformation = a6;
  Size = 0;
  *(_OWORD *)&a6->hProcess = 0;
  *(_QWORD *)&lpProcessInformation->dwProcessId = 0;
  InitializeProcThreadAttributeList(0, 1u, 0, (PSIZE_T)&Size);
  Error = ResultFromKnownLastError();
  if ( Error == -2147024774 )
  {
    lpAttributeList = 0;
    Error = CTCoAllocPolicy::Alloc(v10, 1u, (unsigned int)Size, (void **)&lpAttributeList);
    if ( Error >= 0 )
    {
      v12 = lpAttributeList;
      if ( InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, (PSIZE_T)&Size)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        Value = a1;
        v16 = 0;
        if ( UpdateProcThreadAttribute(v12, 0, 0x20009u, &Value, 0x18u, 0, 0)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          *(_QWORD *)&StartupInfo.cb = 112;
          memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
          v18 = v12;
          if ( CreateProcessAsUserW(a2, 0, a3, 0, 0, 0, 0x80004u, 0, 0, &StartupInfo, lpProcessInformation) )
            Error = 0;
          else
            Error = ResultFromKnownLastError();
        }
        DeleteProcThreadAttributeList(v12);
      }
      CoTaskMemFree(v12);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d8ddc  push    rbp
0x1800d8dde  push    rbx
0x1800d8ddf  push    rsi
0x1800d8de0  push    rdi
0x1800d8de1  push    r12
0x1800d8de3  push    r14
0x1800d8de5  push    r15
0x1800d8de7  lea     rbp, [rsp-17h]
0x1800d8dec  sub     rsp, 0F0h
0x1800d8df3  mov     rsi, [rbp+47h+arg_28]
0x1800d8df7  lea     r9, [rbp+47h+Size]; lpSize
0x1800d8dfb  xor     eax, eax
0x1800d8dfd  xorps   xmm0, xmm0
0x1800d8e00  mov     r15, r8
0x1800d8e03  mov     [rbp+47h+Size], rax
0x1800d8e07  mov     r12, rdx
0x1800d8e0a  mov     r14, rcx
0x1800d8e0d  movups  xmmword ptr [rsi], xmm0
0x1800d8e10  lea     edi, [rax+1]
0x1800d8e13  mov     [rsi+10h], rax
0x1800d8e17  mov     edx, edi; dwAttributeCount
0x1800d8e19  xor     r8d, r8d; dwFlags
0x1800d8e1c  xor     ecx, ecx; lpAttributeList
0x1800d8e1e  call    cs:__imp_InitializeProcThreadAttributeList
0x1800d8e25  nop     dword ptr [rax+rax+00h]
0x1800d8e2a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8e2f  mov     ebx, eax
0x1800d8e31  cmp     eax, 8007007Ah
0x1800d8e36  jnz     loc_1800D8F75
0x1800d8e3c  mov     r8d, dword ptr [rbp+47h+Size]; unsigned __int64
0x1800d8e40  lea     r9, [rbp+47h+lpAttributeList]; void **
0x1800d8e44  mov     edx, edi; unsigned int
0x1800d8e46  mov     [rbp+47h+lpAttributeList], 0
0x1800d8e4e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800d8e53  mov     ebx, eax
0x1800d8e55  test    eax, eax
0x1800d8e57  js      loc_1800D8F75
0x1800d8e5d  mov     edx, edi; dwAttributeCount
0x1800d8e5f  lea     r9, [rbp+47h+Size]; lpSize
0x1800d8e63  mov     rdi, [rbp+47h+lpAttributeList]
0x1800d8e67  xor     r8d, r8d; dwFlags
0x1800d8e6a  mov     rcx, rdi; lpAttributeList
0x1800d8e6d  call    cs:__imp_InitializeProcThreadAttributeList
0x1800d8e74  nop     dword ptr [rax+rax+00h]
0x1800d8e79  test    eax, eax
0x1800d8e7b  jnz     short loc_1800D8E8C
0x1800d8e7d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8e82  mov     ebx, eax
0x1800d8e84  test    eax, eax
0x1800d8e86  js      loc_1800D8F66
0x1800d8e8c  xorps   xmm0, xmm0
0x1800d8e8f  mov     [rsp+120h+lpReturnSize], 0; lpReturnSize
0x1800d8e98  mov     [rsp+120h+lpPreviousValue], 0; lpPreviousValue
0x1800d8ea1  lea     r9, [rbp+47h+Value]; lpValue
0x1800d8ea5  xor     edx, edx; dwFlags
0x1800d8ea7  mov     [rsp+120h+cbSize], 18h; cbSize
0x1800d8eb0  mov     r8d, 20009h; Attribute
0x1800d8eb6  mov     [rbp+47h+Value], r14
0x1800d8eba  mov     rcx, rdi; lpAttributeList
0x1800d8ebd  movdqu  [rbp+47h+var_B0], xmm0
0x1800d8ec2  call    cs:__imp_UpdateProcThreadAttribute
0x1800d8ec9  nop     dword ptr [rax+rax+00h]
0x1800d8ece  test    eax, eax
0x1800d8ed0  jnz     short loc_1800D8EDD
0x1800d8ed2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8ed7  mov     ebx, eax
0x1800d8ed9  test    eax, eax
0x1800d8edb  js      short loc_1800D8F57
0x1800d8edd  xor     edx, edx; Val
0x1800d8edf  mov     qword ptr [rbp+47h+StartupInfo.cb], 70h ; 'p'
0x1800d8ee7  lea     rcx, [rbp+47h+StartupInfo.lpReserved]; void *
0x1800d8eeb  lea     r8d, [rdx+68h]; Size
0x1800d8eef  call    memset_0
0x1800d8ef4  mov     [rsp+120h+lpProcessInformation], rsi; lpProcessInformation
0x1800d8ef9  lea     rax, [rbp+47h+StartupInfo]
0x1800d8efd  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x1800d8f02  xor     r9d, r9d; lpProcessAttributes
0x1800d8f05  mov     [rsp+120h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800d8f0e  mov     r8, r15; lpCommandLine
0x1800d8f11  mov     [rsp+120h+lpEnvironment], 0; lpEnvironment
0x1800d8f1a  xor     edx, edx; lpApplicationName
0x1800d8f1c  mov     dword ptr [rsp+120h+lpReturnSize], 80004h; dwCreationFlags
0x1800d8f24  mov     rcx, r12; hToken
0x1800d8f27  mov     dword ptr [rsp+120h+lpPreviousValue], 0; bInheritHandles
0x1800d8f2f  mov     [rsp+120h+cbSize], 0; lpThreadAttributes
0x1800d8f38  mov     [rbp+47h+var_38], rdi
0x1800d8f3c  call    cs:__imp_CreateProcessAsUserW
0x1800d8f43  nop     dword ptr [rax+rax+00h]
0x1800d8f48  test    eax, eax
0x1800d8f4a  jz      short loc_1800D8F50
0x1800d8f4c  xor     ebx, ebx
0x1800d8f4e  jmp     short loc_1800D8F57
0x1800d8f50  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8f55  mov     ebx, eax
0x1800d8f57  mov     rcx, rdi; lpAttributeList
0x1800d8f5a  call    cs:__imp_DeleteProcThreadAttributeList
0x1800d8f61  nop     dword ptr [rax+rax+00h]
0x1800d8f66  mov     rcx, rdi; pv
0x1800d8f69  call    cs:__imp_CoTaskMemFree
0x1800d8f70  nop     dword ptr [rax+rax+00h]
0x1800d8f75  mov     eax, ebx
0x1800d8f77  add     rsp, 0F0h
0x1800d8f7e  pop     r15
0x1800d8f80  pop     r14
0x1800d8f82  pop     r12
0x1800d8f84  pop     rdi
0x1800d8f85  pop     rsi
0x1800d8f86  pop     rbx
0x1800d8f87  pop     rbp
0x1800d8f88  retn
```
