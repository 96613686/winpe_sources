# CDataFormat::InternalGetDataOnMedium(Windows::ApplicationModel::DataTransfer::IDataPackage *,Microsoft::WRL::Wrappers::SRWLock &&,tagSTGMEDIUM *)

- ea: `0x180038eb8`
- end: `0x180039068`
- name: `?InternalGetDataOnMedium@CDataFormat@@IEAAJPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@$$QEAVSRWLock@Wrappers@WRL@Microsoft@@PEAUtagSTGMEDIUM@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, struct Windows::ApplicationModel::DataTransfer::IDataPackage *, RTL_SRWLOCK *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019f64`
- `0x18002e9a0`

## callees

- `0x180038eb8`
- `0x18005dcac`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038f86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038f1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038ee3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038ee3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038fb5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038fb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038f32`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038f49`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fe6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038fc3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039018`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataFormat::InternalGetDataOnMedium(
        __int64 a1,
        struct Windows::ApplicationModel::DataTransfer::IDataPackage *a2,
        RTL_SRWLOCK *a3,
        __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rsi
  HANDLE CurrentThread; // rax
  signed int v12; // eax
  signed int v13; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  char *v15; // rdx
  signed int LastError; // eax
  signed int v17; // eax
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  __int64 v20; // [rsp+80h] [rbp+18h] BYREF

  v8 = 0;
  v20 = 0;
  AcquireSRWLockShared(a3);
  v9 = *(_QWORD *)(a1 + 16);
  v10 = 0;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    v8 = v9;
    v20 = v9;
    v10 = v9;
  }
  if ( a3 )
    ReleaseSRWLockShared(a3);
  if ( !v10 )
    goto LABEL_30;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    if ( RevertToSelf() )
    {
LABEL_12:
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 8), 0);
      v13 = CDataFormat::s_InvokeDelegate((const struct AgileGitPtr *)&v20, a2, StringRawBuffer, 1);
      goto LABEL_13;
    }
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 >= 0 )
      v13 = -2147467259;
  }
  else
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v13 >= 0 )
    {
      v13 = -2147467259;
      goto LABEL_13;
    }
    if ( v13 == -2147023888 )
      goto LABEL_12;
  }
LABEL_13:
  v15 = (char *)TokenHandle;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( SetThreadToken(0, TokenHandle) )
    {
      v13 = 0;
    }
    else
    {
      v17 = GetLastError();
      v13 = v17;
      if ( v17 > 0 )
        v13 = (unsigned __int16)v17 | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147467259;
    }
    v15 = (char *)TokenHandle;
  }
  TokenHandle = 0;
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v15);
  if ( v13 >= 0 )
LABEL_30:
    v13 = (*(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::DataTransfer::IDataPackage *, RTL_SRWLOCK *, __int64))(*(_QWORD *)a1 + 96LL))(
            a1,
            a2,
            a3,
            a4);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180038eb8  mov     rax, rsp
0x180038ebb  mov     [rax+10h], rbx
0x180038ebf  push    rbp
0x180038ec0  push    rsi
0x180038ec1  push    rdi
0x180038ec2  push    r12
0x180038ec4  push    r13
0x180038ec6  push    r14
0x180038ec8  push    r15
0x180038eca  sub     rsp, 30h
0x180038ece  mov     r12, r9
0x180038ed1  mov     rbp, r8
0x180038ed4  mov     r15, rdx
0x180038ed7  mov     r14, rcx
0x180038eda  xor     ebx, ebx
0x180038edc  mov     [rax+18h], rbx
0x180038ee0  mov     rcx, r8; SRWLock
0x180038ee3  call    cs:__imp_AcquireSRWLockShared
0x180038ee9  mov     rdi, [r14+10h]
0x180038eed  xor     esi, esi
0x180038eef  test    rdi, rdi
0x180038ef2  jz      short loc_180038F12
0x180038ef4  mov     rax, [rdi]
0x180038ef7  mov     rcx, rdi
0x180038efa  mov     rax, [rax+8]
0x180038efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f03  nop
0x180038f04  mov     rbx, rdi
0x180038f07  mov     [rsp+68h+arg_10], rbx
0x180038f0f  mov     rsi, rdi
0x180038f12  test    rbp, rbp
0x180038f15  jz      short loc_180038F20
0x180038f17  mov     rcx, rbp; SRWLock
0x180038f1a  call    cs:__imp_ReleaseSRWLockShared
0x180038f20  test    rsi, rsi
0x180038f23  jz      loc_180039022
0x180038f29  mov     [rsp+68h+TokenHandle], 0
0x180038f32  call    cs:__imp_GetCurrentThread
0x180038f38  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180038f3d  mov     edx, 4; DesiredAccess
0x180038f42  lea     r8d, [rdx-3]; OpenAsSelf
0x180038f46  mov     rcx, rax; ThreadHandle
0x180038f49  call    cs:__imp_OpenThreadToken
0x180038f4f  mov     esi, 80070000h
0x180038f54  mov     r13d, 80004005h
0x180038f5a  test    eax, eax
0x180038f5c  jnz     short loc_180038FC3
0x180038f5e  call    cs:__imp_GetLastError
0x180038f64  mov     edi, eax
0x180038f66  test    eax, eax
0x180038f68  jle     short loc_180038F6F
0x180038f6a  movzx   edi, ax
0x180038f6d  or      edi, esi
0x180038f6f  test    edi, edi
0x180038f71  js      short loc_180038F78
0x180038f73  mov     edi, r13d
0x180038f76  jmp     short loc_180038FA4
0x180038f78  cmp     edi, 800703F0h
0x180038f7e  jnz     short loc_180038FA4
0x180038f80  xor     edx, edx; length
0x180038f82  mov     rcx, [r14+8]; string
0x180038f86  call    cs:__imp_WindowsGetStringRawBuffer
0x180038f8c  mov     r9b, 1; bool
0x180038f8f  mov     r8, rax; unsigned __int16 *
0x180038f92  mov     rdx, r15; struct Windows::ApplicationModel::DataTransfer::IDataPackage *
0x180038f95  lea     rcx, [rsp+68h+arg_10]; struct AgileGitPtr *
0x180038f9d  call    ?s_InvokeDelegate@CDataFormat@@SAJAEBVAgileGitPtr@@PEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@PEBG_N@Z; CDataFormat::s_InvokeDelegate(AgileGitPtr const &,Windows::ApplicationModel::DataTransfer::IDataPackage *,ushort const *,bool)
0x180038fa2  mov     edi, eax
0x180038fa4  mov     rdx, [rsp+68h+TokenHandle]; Token
0x180038fa9  lea     rcx, [rdx-1]
0x180038fad  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180038fb1  ja      short loc_180039002
0x180038fb3  xor     ecx, ecx; Thread
0x180038fb5  call    cs:__imp_SetThreadToken
0x180038fbb  test    eax, eax
0x180038fbd  jz      short loc_180038FE6
0x180038fbf  xor     edi, edi
0x180038fc1  jmp     short loc_180038FFD
0x180038fc3  call    cs:__imp_RevertToSelf
0x180038fc9  test    eax, eax
0x180038fcb  jnz     short loc_180038F80
0x180038fcd  call    cs:__imp_GetLastError
0x180038fd3  mov     edi, eax
0x180038fd5  test    eax, eax
0x180038fd7  jle     short loc_180038FDE
0x180038fd9  movzx   edi, ax
0x180038fdc  or      edi, esi
0x180038fde  test    edi, edi
0x180038fe0  cmovns  edi, r13d
0x180038fe4  jmp     short loc_180038FA4
0x180038fe6  call    cs:__imp_GetLastError
0x180038fec  mov     edi, eax
0x180038fee  test    eax, eax
0x180038ff0  jle     short loc_180038FF7
0x180038ff2  movzx   edi, ax
0x180038ff5  or      edi, esi
0x180038ff7  test    edi, edi
0x180038ff9  cmovns  edi, r13d
0x180038ffd  mov     rdx, [rsp+68h+TokenHandle]
0x180039002  mov     [rsp+68h+TokenHandle], 0
0x18003900b  lea     rax, [rdx-1]
0x18003900f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180039013  ja      short loc_18003901E
0x180039015  mov     rcx, rdx; hObject
0x180039018  call    cs:__imp_CloseHandle
0x18003901e  test    edi, edi
0x180039020  js      short loc_18003903C
0x180039022  mov     rax, [r14]
0x180039025  mov     r9, r12
0x180039028  mov     r8, rbp
0x18003902b  mov     rdx, r15
0x18003902e  mov     rcx, r14
0x180039031  mov     rax, [rax+60h]
0x180039035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003903a  mov     edi, eax
0x18003903c  test    rbx, rbx
0x18003903f  jz      short loc_180039051
0x180039041  mov     rax, [rbx]
0x180039044  mov     rcx, rbx
0x180039047  mov     rax, [rax+10h]
0x18003904b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039050  nop
0x180039051  mov     eax, edi
0x180039053  mov     rbx, [rsp+68h+arg_8]
0x180039058  add     rsp, 30h
0x18003905c  pop     r15
0x18003905e  pop     r14
0x180039060  pop     r13
0x180039062  pop     r12
0x180039064  pop     rdi
0x180039065  pop     rsi
0x180039066  pop     rbp
0x180039067  retn
```
