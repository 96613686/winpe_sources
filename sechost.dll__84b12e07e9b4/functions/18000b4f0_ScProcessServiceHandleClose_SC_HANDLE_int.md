# ScProcessServiceHandleClose(SC_HANDLE__ * *,int *)

- ea: `0x18000b4f0`
- end: `0x18000b99a`
- name: `?ScProcessServiceHandleClose@@YAKPEAPEAUSC_HANDLE__@@PEAH@Z`
- size: `1194`
- prototype: `unsigned int __fastcall(struct SC_HANDLE__ **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b460`

## callees

- `0x18000b4f0`
- `0x18003b770`
- `0x18003c49c`
- `0x18004abac`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b6fe`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b6fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b649`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b649`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b709`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b75c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b75c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000b8f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000b8f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b6cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b6cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b5ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b679`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b77a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b5ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b679`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b77a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b52d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b73a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b52d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b73a`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000b68c`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000b6f0`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000b68c`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000b6f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b69f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b69f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b611`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b652`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b611`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b652`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b785`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b785`
- `RPCRT4!RpcSmDestroyClientContext` at `0x18000b96d`
- `RPCRT4!RpcSmDestroyClientContext` at `0x18000b96d`
- `RPCRT4!NdrClientCall2` at `0x18000b844`
- `RPCRT4!NdrClientCall2` at `0x18000b844`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc4e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc6a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc4e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc6a`

## pseudocode

```c
__int64 __fastcall ScProcessServiceHandleClose(struct SC_HANDLE__ **a1, int *a2)
{
  void *v4; // rdi
  _UNKNOWN **i; // rbx
  _UNKNOWN **v7; // rsi
  _UNKNOWN **v8; // rax
  _QWORD *v9; // rcx
  void *v10; // rbx
  void *v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdi
  int v16; // esi
  HANDLE v17; // r13
  void *v18; // r12
  _UNKNOWN **j; // rbx
  _UNKNOWN **k; // rcx
  _UNKNOWN **v21; // rcx
  _QWORD *m; // rdx
  unsigned int v23; // ebx
  _DWORD *v24; // r15
  unsigned int Pointer; // eax
  int v26; // ecx
  int v27; // edx
  __int64 v28; // r8
  int v29; // [rsp+24h] [rbp-54h]
  int v30; // [rsp+88h] [rbp+10h] BYREF
  _QWORD *v31; // [rsp+90h] [rbp+18h]
  __int64 v32; // [rsp+98h] [rbp+20h]

  v30 = 1;
  *a2 = 0;
  v4 = *a1;
  if ( !*a1 )
    return 0;
LABEL_2:
  EnterCriticalSection(&SccCritsec);
  for ( i = (_UNKNOWN **)off_180079780; i != &off_180079780; i = (_UNKNOWN **)*i )
  {
    v7 = i - 1;
    if ( i[4] == v4 )
    {
      v7[9] = 0;
      if ( *((_DWORD *)v7 + 32) && !*((_DWORD *)v7 + 33) && WaitForSingleObjectEx(v7[7], 0, 0) )
      {
        LeaveCriticalSection(&SccCritsec);
        SleepEx(0xFAu, 1);
        goto LABEL_2;
      }
      v8 = (_UNKNOWN **)*i;
      if ( *((_UNKNOWN ***)*i + 1) != i )
        goto LABEL_72;
      v9 = i[1];
      if ( (_UNKNOWN **)*v9 != i )
        goto LABEL_72;
      *v9 = v8;
      v8[1] = v9;
      i[1] = i;
      *i = i;
      v10 = v7[3];
      v7[3] = 0;
      LeaveCriticalSection(&SccCritsec);
      if ( v10 )
        RtlUnsubscribeWnfNotificationWaitForCompletion(v10);
      EnterCriticalSection(&SccCritsec);
      v11 = v7[7];
      if ( v11 )
      {
        CloseHandle(v11);
        v7[7] = 0;
      }
      if ( *((_DWORD *)v7 + 33) )
        *((_DWORD *)v7 + 34) = 1;
      else
        LocalFree(v7);
      i = &off_180079780;
    }
  }
  LeaveCriticalSection(&SccCritsec);
  if ( !g_fNotificationInitialized )
    return 0;
  v15 = 0;
  v31 = 0;
  v16 = 0;
  v17 = 0;
  v32 = 0;
LABEL_35:
  EnterCriticalSection(&SccCritsec);
  v18 = *a1;
  for ( j = (_UNKNOWN **)off_180079808; j != &off_180079808; j = (_UNKNOWN **)*j )
  {
    if ( j[2] == v18 && *((_DWORD *)j + 6) != GetCurrentThreadId() )
    {
      LeaveCriticalSection(&SccCritsec);
      Sleep(0xFAu);
      goto LABEL_35;
    }
  }
  for ( k = (_UNKNOWN **)off_1800797B8; k != &off_1800797B8; k = (_UNKNOWN **)*k )
  {
    v15 = k - 2;
    v31 = k - 2;
    if ( k[3] == (_UNKNOWN *)*a1 )
    {
      v16 = 1;
      break;
    }
  }
  if ( !v16 )
  {
    v21 = (_UNKNOWN **)off_180079798;
    if ( off_180079798 != (_UNKNOWN *)&off_180079798 )
    {
      do
      {
        for ( m = *(v21 - 2); m != v21 - 2; m = (_QWORD *)*m )
        {
          v15 = m - 2;
          v31 = m - 2;
          if ( (struct SC_HANDLE__ *)m[3] == *a1 )
            goto LABEL_54;
        }
        v21 = (_UNKNOWN **)*v21;
      }
      while ( v21 != &off_180079798 );
    }
    v23 = 0;
    goto LABEL_22;
  }
LABEL_54:
  *a2 = 1;
  v24 = (_DWORD *)v15 + 1;
  *((_DWORD *)v15 + 1) |= 1u;
  Pointer = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_18005FFA2, a1).Pointer;
  v23 = Pointer;
  v26 = 0;
  v27 = 0;
  v15[1] = 0;
  v15[5] = 0;
  if ( (Pointer & 0xFFFF75F0) == 0xFFFF75F0 )
  {
    if ( Pointer == -35331 )
    {
      v27 = 1;
LABEL_59:
      v23 = 0;
      goto LABEL_60;
    }
    if ( Pointer == -35330 )
    {
      v26 = 1;
      goto LABEL_59;
    }
  }
LABEL_60:
  *v24 &= ~1u;
  if ( v23 )
    goto LABEL_22;
  v28 = v15[4];
  if ( (_UNKNOWN *)v28 == &g_SccRemoteNotifyCompletedList )
    goto LABEL_22;
  if ( (*(_BYTE *)(v28 + 60) & 1) == 0 )
  {
    if ( v27 == 1 )
    {
      v17 = OpenThread(0x100040u, 0, *(_DWORD *)(v28 + 56));
      goto LABEL_22;
    }
    if ( v26 != 1 || v15[6] )
      goto LABEL_22;
LABEL_19:
    v12 = v15 + 2;
    v13 = v15[2];
    if ( *(_QWORD **)(v13 + 8) != v15 + 2 || (v14 = (_QWORD *)v15[3], (_QWORD *)*v14 != v12) )
LABEL_72:
      __fastfail(3u);
    *v14 = v13;
    *(_QWORD *)(v13 + 8) = v14;
    v15[3] = v15 + 2;
    *v12 = v12;
    CloseHandle((HANDLE)v15[7]);
    LocalFree(v15);
    v15 = 0;
    goto LABEL_22;
  }
  *v24 |= 1u;
  v29 = RCloseNotifyHandle(v15 + 6, &v30);
  *v24 &= ~1u;
  if ( v29 )
    RpcSmDestroyClientContext((void **)v15 + 6);
  v15[6] = 0;
  if ( !v30 )
    goto LABEL_19;
  v16 = 1;
LABEL_22:
  if ( v15 && (*((_BYTE *)v15 + 4) & 2) != 0 )
    ScApcNotifyCallback(v15, 0, 0);
  LeaveCriticalSection(&SccCritsec);
  if ( !v23 && v16 == 1 )
    SleepEx(0, 1);
  if ( v17 )
  {
    WaitForSingleObject(v17, 0x1D4C0u);
    CloseHandle(v17);
  }
  return v23;
}

```

## disassembly

```asm
0x18000b4f0  push    rbx
0x18000b4f2  push    rsi
0x18000b4f3  push    rdi
0x18000b4f4  push    r12
0x18000b4f6  push    r13
0x18000b4f8  push    r14
0x18000b4fa  push    r15
0x18000b4fc  sub     rsp, 40h
0x18000b500  mov     r15, rdx
0x18000b503  mov     r14, rcx
0x18000b506  mov     [rsp+78h+arg_8], 1
0x18000b511  mov     dword ptr [rdx], 0
0x18000b517  mov     rdi, [rcx]
0x18000b51a  test    rdi, rdi
0x18000b51d  jz      short loc_18000B559
0x18000b51f  lea     r12, off_180079780
0x18000b526  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b52d  call    cs:__imp_EnterCriticalSection
0x18000b533  mov     rbx, cs:off_180079780
0x18000b53a  cmp     rbx, r12
0x18000b53d  jnz     short loc_18000B56B
0x18000b53f  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b546  call    cs:__imp_LeaveCriticalSection
0x18000b54c  cmp     cs:?g_fNotificationInitialized@@3HA, 0; int g_fNotificationInitialized
0x18000b553  jnz     loc_18000B71C
0x18000b559  xor     eax, eax
0x18000b55b  add     rsp, 40h
0x18000b55f  pop     r15
0x18000b561  pop     r14
0x18000b563  pop     r13
0x18000b565  pop     r12
0x18000b567  pop     rdi
0x18000b568  pop     rsi
0x18000b569  pop     rbx
0x18000b56a  retn
0x18000b56b  lea     rsi, [rbx-8]
0x18000b56f  cmp     [rsi+28h], rdi
0x18000b573  jz      short loc_18000B57A
0x18000b575  mov     rbx, [rbx]
0x18000b578  jmp     short loc_18000B53A
0x18000b57a  mov     qword ptr [rsi+48h], 0
0x18000b582  cmp     dword ptr [rsi+80h], 0
0x18000b589  jnz     loc_18000B6B5
0x18000b58f  mov     rax, [rbx]
0x18000b592  cmp     [rax+8], rbx
0x18000b596  jnz     loc_18000B993
0x18000b59c  mov     rcx, [rbx+8]
0x18000b5a0  cmp     [rcx], rbx
0x18000b5a3  jnz     loc_18000B993
0x18000b5a9  mov     [rcx], rax
0x18000b5ac  mov     [rax+8], rcx
0x18000b5b0  mov     [rbx+8], rbx
0x18000b5b4  mov     [rbx], rbx
0x18000b5b7  mov     rbx, [rsi+18h]
0x18000b5bb  mov     qword ptr [rsi+18h], 0
0x18000b5c3  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b5ca  call    cs:__imp_LeaveCriticalSection
0x18000b5d0  test    rbx, rbx
0x18000b5d3  jnz     loc_18000B6FB
0x18000b5d9  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b5e0  call    cs:__imp_EnterCriticalSection
0x18000b5e6  mov     rcx, [rsi+38h]; hObject
0x18000b5ea  test    rcx, rcx
0x18000b5ed  jnz     loc_18000B709
0x18000b5f3  cmp     dword ptr [rsi+84h], 0
0x18000b5fa  jz      short loc_18000B60E
0x18000b5fc  mov     dword ptr [rsi+88h], 1
0x18000b606  mov     rbx, r12
0x18000b609  jmp     loc_18000B575
0x18000b60e  mov     rcx, rsi; hMem
0x18000b611  call    cs:__imp_LocalFree
0x18000b617  jmp     short loc_18000B606
0x18000b619  lea     rax, [rdi+10h]
0x18000b61d  mov     rcx, [rax]
0x18000b620  cmp     [rcx+8], rax
0x18000b624  jnz     loc_18000B993
0x18000b62a  mov     rdx, [rax+8]
0x18000b62e  cmp     [rdx], rax
0x18000b631  jnz     loc_18000B993
0x18000b637  mov     [rdx], rcx
0x18000b63a  mov     [rcx+8], rdx
0x18000b63e  mov     [rax+8], rax
0x18000b642  mov     [rax], rax
0x18000b645  mov     rcx, [rdi+38h]; hObject
0x18000b649  call    cs:__imp_CloseHandle
0x18000b64f  mov     rcx, rdi; hMem
0x18000b652  call    cs:__imp_LocalFree
0x18000b658  xor     edi, edi
0x18000b65a  test    rdi, rdi
0x18000b65d  jz      short loc_18000B672
0x18000b65f  test    byte ptr [rdi+4], 2
0x18000b663  jz      short loc_18000B672
0x18000b665  xor     r8d, r8d; SystemArgument2
0x18000b668  xor     edx, edx; SystemArgument1
0x18000b66a  mov     rcx, rdi; NormalContext
0x18000b66d  call    ?ScApcNotifyCallback@@YAXPEAX00@Z; ScApcNotifyCallback(void *,void *,void *)
0x18000b672  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b679  call    cs:__imp_LeaveCriticalSection
0x18000b67f  test    ebx, ebx
0x18000b681  jnz     short loc_18000B692
0x18000b683  cmp     esi, 1
0x18000b686  jnz     short loc_18000B692
0x18000b688  mov     edx, esi; bAlertable
0x18000b68a  xor     ecx, ecx; dwMilliseconds
0x18000b68c  call    cs:__imp_SleepEx
0x18000b692  test    r13, r13
0x18000b695  jz      short loc_18000B6AE
0x18000b697  mov     edx, 1D4C0h; dwMilliseconds
0x18000b69c  mov     rcx, r13; hHandle
0x18000b69f  call    cs:__imp_WaitForSingleObject
0x18000b6a5  mov     rcx, r13; hObject
0x18000b6a8  call    cs:__imp_CloseHandle
0x18000b6ae  mov     eax, ebx
0x18000b6b0  jmp     loc_18000B55B
0x18000b6b5  cmp     dword ptr [rsi+84h], 0
0x18000b6bc  jnz     loc_18000B58F
0x18000b6c2  xor     r8d, r8d; bAlertable
0x18000b6c5  xor     edx, edx; dwMilliseconds
0x18000b6c7  mov     rcx, [rsi+38h]; hHandle
0x18000b6cb  call    cs:__imp_WaitForSingleObjectEx
0x18000b6d1  test    eax, eax
0x18000b6d3  jz      loc_18000B58F
0x18000b6d9  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b6e0  call    cs:__imp_LeaveCriticalSection
0x18000b6e6  mov     edx, 1; bAlertable
0x18000b6eb  mov     ecx, 0FAh; dwMilliseconds
0x18000b6f0  call    cs:__imp_SleepEx
0x18000b6f6  jmp     loc_18000B526
0x18000b6fb  mov     rcx, rbx
0x18000b6fe  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000b704  jmp     loc_18000B5D9
0x18000b709  call    cs:__imp_CloseHandle
0x18000b70f  mov     qword ptr [rsi+38h], 0
0x18000b717  jmp     loc_18000B5F3
0x18000b71c  xor     edi, edi
0x18000b71e  mov     [rsp+78h+arg_10], rdi
0x18000b726  xor     esi, esi
0x18000b728  xor     r13d, r13d
0x18000b72b  mov     [rsp+78h+arg_18], r13
0x18000b733  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b73a  call    cs:__imp_EnterCriticalSection
0x18000b740  mov     r12, [r14]
0x18000b743  mov     rbx, cs:off_180079808
0x18000b74a  lea     rax, off_180079808
0x18000b751  cmp     rbx, rax
0x18000b754  jz      short loc_18000B78D
0x18000b756  cmp     [rbx+10h], r12
0x18000b75a  jnz     short loc_18000B76E
0x18000b75c  call    cs:__imp_GetCurrentThreadId
0x18000b762  cmp     [rbx+18h], eax
0x18000b765  jnz     short loc_18000B773
0x18000b767  lea     rax, off_180079808
0x18000b76e  mov     rbx, [rbx]
0x18000b771  jmp     short loc_18000B751
0x18000b773  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b77a  call    cs:__imp_LeaveCriticalSection
0x18000b780  mov     ecx, 0FAh; dwMilliseconds
0x18000b785  call    cs:__imp_Sleep
0x18000b78b  jmp     short loc_18000B733
0x18000b78d  mov     rcx, cs:off_1800797B8
0x18000b794  lea     rdx, off_1800797B8
0x18000b79b  cmp     rcx, rdx
0x18000b79e  jz      short loc_18000B7BF
0x18000b7a0  lea     rdi, [rcx-10h]
0x18000b7a4  mov     [rsp+78h+arg_10], rdi
0x18000b7ac  mov     rax, [r14]
0x18000b7af  cmp     [rdi+28h], rax
0x18000b7b3  jz      short loc_18000B7BA
0x18000b7b5  mov     rcx, [rcx]
0x18000b7b8  jmp     short loc_18000B79B
0x18000b7ba  mov     esi, 1
0x18000b7bf  mov     [rsp+78h+arg_0], esi
0x18000b7c6  test    esi, esi
0x18000b7c8  jnz     short loc_18000B816
0x18000b7ca  mov     rcx, cs:off_180079798
0x18000b7d1  lea     r9, off_180079798
0x18000b7d8  cmp     rcx, r9
0x18000b7db  jz      short loc_18000B80B
0x18000b7dd  lea     r8, [rcx-10h]
0x18000b7e1  mov     rdx, [r8]
0x18000b7e4  cmp     rdx, r8
0x18000b7e7  jz      short loc_18000B803
0x18000b7e9  lea     rdi, [rdx-10h]
0x18000b7ed  mov     [rsp+78h+arg_10], rdi
0x18000b7f5  mov     rax, [r14]
0x18000b7f8  cmp     [rdi+28h], rax
0x18000b7fc  jz      short loc_18000B816
0x18000b7fe  mov     rdx, [rdx]
0x18000b801  jmp     short loc_18000B7E4
0x18000b803  mov     rcx, [rcx]
0x18000b806  cmp     rcx, r9
0x18000b809  jnz     short loc_18000B7DD
0x18000b80b  test    esi, esi
0x18000b80d  jnz     short loc_18000B816
0x18000b80f  xor     ebx, ebx
0x18000b811  jmp     loc_18000B65A
0x18000b816  mov     dword ptr [r15], 1
0x18000b81d  lea     r15, [rdi+4]
0x18000b821  mov     [rsp+78h+var_50], r15
0x18000b826  or      dword ptr [r15], 1
0x18000b82a  mov     [rsp+78h+var_48], 0
0x18000b833  mov     r8, r14
0x18000b836  lea     rdx, byte_18005FFA2; pFormat
0x18000b83d  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000b844  call    cs:__imp_NdrClientCall2
0x18000b84a  mov     rbx, rax
0x18000b84d  mov     [rsp+78h+var_48], rax
0x18000b852  mov     [rsp+78h+var_58], eax
0x18000b856  jmp     short loc_18000B881
0x18000b858  mov     ecx, eax; unsigned int
0x18000b85a  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000b85f  mov     ebx, eax
0x18000b861  mov     [rsp+78h+var_58], eax
0x18000b865  mov     rdi, [rsp+78h+arg_10]
0x18000b86d  mov     r13, [rsp+78h+arg_18]
0x18000b875  mov     esi, [rsp+78h+arg_0]
0x18000b87c  mov     r15, [rsp+78h+var_50]
0x18000b881  xor     ecx, ecx
0x18000b883  xor     edx, edx
0x18000b885  mov     [rdi+8], rcx
0x18000b889  mov     [rdi+28h], rcx
0x18000b88d  mov     eax, ebx
0x18000b88f  and     eax, 0FFFF75F0h
0x18000b894  cmp     eax, 0FFFF75F0h
0x18000b899  jnz     short loc_18000B8BD
0x18000b89b  cmp     ebx, 0FFFF75FDh
0x18000b8a1  jnz     short loc_18000B8AA
0x18000b8a3  mov     edx, 1
0x18000b8a8  jmp     short loc_18000B8B7
0x18000b8aa  cmp     ebx, 0FFFF75FEh
0x18000b8b0  jnz     short loc_18000B8BD
0x18000b8b2  mov     ecx, 1
0x18000b8b7  xor     ebx, ebx
0x18000b8b9  mov     [rsp+78h+var_58], ebx
0x18000b8bd  and     dword ptr [r15], 0FFFFFFFEh
0x18000b8c1  test    ebx, ebx
0x18000b8c3  jnz     loc_18000B65A
0x18000b8c9  mov     r8, [rdi+20h]
0x18000b8cd  lea     r9, ?g_SccRemoteNotifyCompletedList@@3U_SCC_SERVER_NOTIFY_LIST@@A; "lstc"
0x18000b8d4  cmp     r8, r9
0x18000b8d7  jz      loc_18000B65A
0x18000b8dd  test    byte ptr [r8+3Ch], 1
0x18000b8e2  jnz     short loc_18000B91B
0x18000b8e4  cmp     edx, 1
0x18000b8e7  jnz     short loc_18000B902
0x18000b8e9  mov     r8d, [r8+38h]; dwThreadId
0x18000b8ed  xor     edx, edx; bInheritHandle
0x18000b8ef  mov     ecx, 100040h; dwDesiredAccess
0x18000b8f4  call    cs:__imp_OpenThread
0x18000b8fa  mov     r13, rax
0x18000b8fd  jmp     loc_18000B65A
0x18000b902  cmp     ecx, 1
0x18000b905  jnz     loc_18000B65A
0x18000b90b  cmp     qword ptr [rdi+30h], 0
0x18000b910  jnz     loc_18000B65A
0x18000b916  jmp     loc_18000B619
0x18000b91b  or      dword ptr [r15], 1
0x18000b91f  lea     rcx, [rdi+30h]
0x18000b923  lea     rdx, [rsp+78h+arg_8]
0x18000b92b  call    RCloseNotifyHandle
0x18000b930  mov     [rsp+78h+var_54], eax
0x18000b934  jmp     short loc_18000B961
0x18000b936  mov     ecx, eax; unsigned int
0x18000b938  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000b93d  mov     [rsp+78h+var_54], eax
0x18000b941  mov     ebx, [rsp+78h+var_58]
0x18000b945  mov     rdi, [rsp+78h+arg_10]
0x18000b94d  mov     r13, [rsp+78h+arg_18]
0x18000b955  mov     esi, [rsp+78h+arg_0]
0x18000b95c  mov     r15, [rsp+78h+var_50]
0x18000b961  and     dword ptr [r15], 0FFFFFFFEh
0x18000b965  test    eax, eax
0x18000b967  jz      short loc_18000B973
0x18000b969  lea     rcx, [rdi+30h]; ContextHandle
0x18000b96d  call    cs:__imp_RpcSmDestroyClientContext
0x18000b973  mov     qword ptr [rdi+30h], 0
0x18000b97b  cmp     [rsp+78h+arg_8], 0
0x18000b983  jz      loc_18000B619
0x18000b989  mov     esi, 1
0x18000b98e  jmp     loc_18000B65A
0x18000b993  mov     ecx, 3
0x18000b998  int     29h; Win8: RtlFailFast(ecx)
0x18004fc40  push    rbp
0x18004fc42  sub     rsp, 20h
0x18004fc46  mov     rbp, rdx
0x18004fc49  mov     rcx, [rcx]
0x18004fc4c  mov     ecx, [rcx]; ExceptionCode
0x18004fc4e  call    cs:__imp_I_RpcExceptionFilter
0x18004fc54  nop
0x18004fc55  add     rsp, 20h
0x18004fc59  pop     rbp
0x18004fc5a  retn
0x18004fc5c  push    rbp
0x18004fc5e  sub     rsp, 20h
0x18004fc62  mov     rbp, rdx
0x18004fc65  mov     rcx, [rcx]
0x18004fc68  mov     ecx, [rcx]; ExceptionCode
0x18004fc6a  call    cs:__imp_I_RpcExceptionFilter
0x18004fc70  nop
0x18004fc71  add     rsp, 20h
  ... truncated ...
```
