# SiPerformParallelOperation2(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)

- ea: `0x14000bef0`
- end: `0x14000c012`
- name: `?SiPerformParallelOperation2@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z`
- size: `290`
- prototype: `__int64 __fastcall(int, void **, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000ccd0`

## callees

- `0x14000bef0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14000bfcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14000bfcc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000bf8b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000bf8b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14000bfc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14000bfc3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000bfaf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000bfaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bfee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bfee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bf62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bf62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000bf41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000bf41`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000bf56`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000bf56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bfff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bfff`

## pseudocode

```c
__int64 __fastcall SiPerformParallelOperation2(int a1, void **a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  unsigned int v6; // ebx
  BOOL v8; // esi
  HANDLE CurrentThread; // rax
  struct _TP_WORK *v10; // r14
  void **v11; // rbx
  void **i; // rax
  DWORD v13; // ecx
  int pv; // [rsp+20h] [rbp-40h] BYREF
  void **v16; // [rsp+28h] [rbp-38h]
  __int64 v17; // [rsp+30h] [rbp-30h]
  __int64 v18; // [rsp+38h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-20h]
  __int64 v20; // [rsp+48h] [rbp-18h]
  void *TokenHandle[2]; // [rsp+50h] [rbp-10h] BYREF

  v19 = a5;
  v6 = 1;
  v20 = a6;
  v8 = 1;
  *(_OWORD *)TokenHandle = 0;
  pv = a1;
  v16 = a2;
  v17 = a3;
  v18 = a4;
  if ( !a2 )
    goto LABEL_10;
  if ( *a2 != a2 )
  {
    CurrentThread = GetCurrentThread();
    v8 = OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle[1]);
    if ( v8 )
    {
LABEL_6:
      v10 = CreateThreadpoolWork((PTP_WORK_CALLBACK)SI_DISPATCH::Callback, &pv, &ThreadpoolEnv);
      if ( !v10 )
      {
LABEL_17:
        v6 = 0;
        goto LABEL_18;
      }
      TokenHandle[0] = *v16;
      v11 = (void **)*v16;
      if ( *v16 != v16 )
      {
        do
        {
          SubmitThreadpoolWork(v10);
          v11 = (void **)*v11;
        }
        while ( v11 != v16 );
      }
      WaitForThreadpoolWorkCallbacks(v10, 0);
      CloseThreadpoolWork(v10);
      goto LABEL_10;
    }
    if ( GetLastError() == 1008 )
    {
      SetLastError(0);
      v8 = 1;
      goto LABEL_6;
    }
LABEL_10:
    v6 = v8;
    if ( !v8 )
      goto LABEL_18;
  }
  for ( i = (void **)*a2; i != a2; i = (void **)*i )
  {
    v13 = *((_DWORD *)i + 4);
    if ( v13 )
    {
      SetLastError(v13);
      goto LABEL_17;
    }
  }
LABEL_18:
  if ( TokenHandle[1] )
    CloseHandle(TokenHandle[1]);
  return v6;
}

```

## disassembly

```asm
0x14000bef0  push    rbp
0x14000bef2  push    rbx
0x14000bef3  push    rsi
0x14000bef4  push    rdi
0x14000bef5  push    r14
0x14000bef7  mov     rbp, rsp
0x14000befa  sub     rsp, 60h
0x14000befe  mov     rax, [rbp+arg_20]
0x14000bf02  xorps   xmm0, xmm0
0x14000bf05  mov     [rbp+var_20], rax
0x14000bf09  mov     ebx, 1
0x14000bf0e  mov     rax, [rbp+arg_28]
0x14000bf12  mov     rdi, rdx
0x14000bf15  mov     [rbp+var_18], rax
0x14000bf19  mov     esi, ebx
0x14000bf1b  movdqa  xmmword ptr [rbp+TokenHandle], xmm0
0x14000bf20  mov     [rbp+pv], ecx
0x14000bf23  mov     [rbp+var_38], rdx
0x14000bf27  mov     [rbp+var_30], r8
0x14000bf2b  mov     [rbp+var_28], r9
0x14000bf2f  test    rdx, rdx
0x14000bf32  jz      loc_14000BFD2
0x14000bf38  cmp     [rdx], rdx
0x14000bf3b  jz      loc_14000BFD8
0x14000bf41  call    cs:__imp_GetCurrentThread
0x14000bf47  lea     r9, [rbp+TokenHandle+8]; TokenHandle
0x14000bf4b  xor     r8d, r8d; OpenAsSelf
0x14000bf4e  mov     rcx, rax; ThreadHandle
0x14000bf51  mov     edx, 2000Ch; DesiredAccess
0x14000bf56  call    cs:__imp_OpenThreadToken
0x14000bf5c  mov     esi, eax
0x14000bf5e  test    eax, eax
0x14000bf60  jnz     short loc_14000BF79
0x14000bf62  call    cs:__imp_GetLastError
0x14000bf68  cmp     eax, 3F0h
0x14000bf6d  jnz     short loc_14000BFD2
0x14000bf6f  xor     ecx, ecx; dwErrCode
0x14000bf71  call    cs:__imp_SetLastError
0x14000bf77  mov     esi, ebx
0x14000bf79  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x14000bf80  lea     rdx, [rbp+pv]; pv
0x14000bf84  lea     rcx, ?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14000bf8b  call    cs:__imp_CreateThreadpoolWork
0x14000bf91  mov     r14, rax
0x14000bf94  test    rax, rax
0x14000bf97  jz      short loc_14000BFF4
0x14000bf99  mov     rcx, [rbp+var_38]
0x14000bf9d  mov     rax, [rcx]
0x14000bfa0  mov     [rbp+TokenHandle], rax
0x14000bfa4  mov     rbx, [rcx]
0x14000bfa7  cmp     rbx, rcx
0x14000bfaa  jz      short loc_14000BFBE
0x14000bfac  mov     rcx, r14; pwk
0x14000bfaf  call    cs:__imp_SubmitThreadpoolWork
0x14000bfb5  mov     rbx, [rbx]
0x14000bfb8  cmp     rbx, [rbp+var_38]
0x14000bfbc  jnz     short loc_14000BFAC
0x14000bfbe  xor     edx, edx; fCancelPendingCallbacks
0x14000bfc0  mov     rcx, r14; pwk
0x14000bfc3  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x14000bfc9  mov     rcx, r14; pwk
0x14000bfcc  call    cs:__imp_CloseThreadpoolWork
0x14000bfd2  mov     ebx, esi
0x14000bfd4  test    esi, esi
0x14000bfd6  jz      short loc_14000BFF6
0x14000bfd8  mov     rax, [rdi]
0x14000bfdb  jmp     short loc_14000BFE7
0x14000bfdd  mov     ecx, [rax+10h]; dwErrCode
0x14000bfe0  test    ecx, ecx
0x14000bfe2  jnz     short loc_14000BFEE
0x14000bfe4  mov     rax, [rax]
0x14000bfe7  cmp     rax, rdi
0x14000bfea  jnz     short loc_14000BFDD
0x14000bfec  jmp     short loc_14000BFF6
0x14000bfee  call    cs:__imp_SetLastError
0x14000bff4  xor     ebx, ebx
0x14000bff6  mov     rcx, [rbp+TokenHandle+8]; hObject
0x14000bffa  test    rcx, rcx
0x14000bffd  jz      short loc_14000C005
0x14000bfff  call    cs:__imp_CloseHandle
0x14000c005  mov     eax, ebx
0x14000c007  add     rsp, 60h
0x14000c00b  pop     r14
0x14000c00d  pop     rdi
0x14000c00e  pop     rsi
0x14000c00f  pop     rbx
0x14000c010  pop     rbp
0x14000c011  retn
```
