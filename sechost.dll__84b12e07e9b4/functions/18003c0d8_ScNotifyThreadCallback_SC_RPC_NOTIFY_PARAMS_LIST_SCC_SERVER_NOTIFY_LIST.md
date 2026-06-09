# ScNotifyThreadCallback(_SC_RPC_NOTIFY_PARAMS_LIST *,_SCC_SERVER_NOTIFY_LIST *)

- ea: `0x18003c0d8`
- end: `0x18003c276`
- name: `?ScNotifyThreadCallback@@YAXPEAU_SC_RPC_NOTIFY_PARAMS_LIST@@PEAU_SCC_SERVER_NOTIFY_LIST@@@Z`
- size: `414`
- prototype: `void __fastcall(struct _SC_RPC_NOTIFY_PARAMS_LIST *, struct _SCC_SERVER_NOTIFY_LIST *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003be30`

## callees

- `0x18003b560`
- `0x18003c0d8`

## import_xrefs

- `ntdll!NtQueueApcThread` at `0x18003c1d5`
- `ntdll!NtQueueApcThread` at `0x18003c1d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c226`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c23c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c23c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c10e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c10e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c22f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c247`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c22f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c247`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c268`

## pseudocode

```c
void __fastcall ScNotifyThreadCallback(struct _SC_RPC_NOTIFY_PARAMS_LIST *a1, struct _SCC_SERVER_NOTIFY_LIST *a2)
{
  unsigned int v2; // r14d
  _QWORD **v4; // r15
  __int64 v5; // rbx
  _QWORD *i; // rdx
  _QWORD *v7; // rsi
  __int64 v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  _QWORD *v14; // rax
  void *v15; // rcx

  v2 = 0;
  if ( *(_DWORD *)a1 )
  {
    v4 = (_QWORD **)((char *)a2 + 8);
    do
    {
      v5 = *(_QWORD *)(*((_QWORD *)a1 + 2 * v2 + 2) + 28LL);
      EnterCriticalSection(&SccCritsec);
      for ( i = *v4; ; i = (_QWORD *)*i )
      {
        if ( i == v4 )
          goto LABEL_17;
        if ( i - 2 == (_QWORD *)v5 && *((_DWORD *)i + 12) == *(_DWORD *)(*((_QWORD *)a1 + 2 * v2 + 2) + 84LL) )
          break;
      }
      v7 = (_QWORD *)(v5 + 16);
      v8 = *(_QWORD *)(v5 + 16);
      if ( *(_QWORD *)(v8 + 8) != v5 + 16 || (v9 = *(_QWORD **)(v5 + 24), (_QWORD *)*v9 != v7) )
LABEL_19:
        __fastfail(3u);
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      *(_QWORD *)(v5 + 24) = v7;
      *v7 = v7;
      v10 = *(_QWORD *)(v5 + 8);
      if ( !v10 )
        goto LABEL_16;
      *(_DWORD *)(v10 + 24) = *(_DWORD *)(*((_QWORD *)a1 + 2 * v2 + 2) + 80LL);
      v11 = *((_QWORD *)a1 + 2 * v2 + 2);
      v12 = *(_QWORD *)(v5 + 8);
      *(_OWORD *)(v12 + 28) = *(_OWORD *)(v11 + 44);
      *(_OWORD *)(v12 + 44) = *(_OWORD *)(v11 + 60);
      *(_DWORD *)(v12 + 60) = *(_DWORD *)(v11 + 76);
      if ( *((_DWORD *)a1 + 4 * v2 + 2) == 2 )
      {
        v13 = *((_QWORD *)a1 + 2 * v2 + 2);
        ScAddCreatedDeletedServiceNames(
          (struct _SCC_NOTIFY_BLOCK *)v5,
          (unsigned __int16 **)(v13 + 96),
          *(_DWORD *)(v13 + 88));
      }
      if ( NtQueueApcThread(*(HANDLE *)(v5 + 56), ScApcNotifyCallback, (PVOID)v5, 0, 0) >= 0 )
      {
        v14 = off_1800797C0[0];
        if ( *(_UNKNOWN ***)off_1800797C0[0] != &off_1800797B8 )
          goto LABEL_19;
        *(_UNKNOWN ***)(v5 + 24) = off_1800797C0[0];
        *v7 = &off_1800797B8;
        *v14 = v7;
        off_1800797C0[0] = (_UNKNOWN **)(v5 + 16);
        v15 = *(void **)(v5 + 56);
        *(_QWORD *)(v5 + 32) = &g_SccRemoteNotifyCompletedList;
        CloseHandle(v15);
        *(_QWORD *)(v5 + 56) = 0;
      }
      else
      {
LABEL_16:
        CloseHandle(*(HANDLE *)(v5 + 56));
        LocalFree((HLOCAL)v5);
      }
LABEL_17:
      LeaveCriticalSection(&SccCritsec);
      LocalFree(*((HLOCAL *)a1 + 2 * v2++ + 2));
    }
    while ( v2 < *(_DWORD *)a1 );
  }
  LocalFree(a1);
}

```

## disassembly

```asm
0x18003c0d8  push    rbx
0x18003c0da  push    rbp
0x18003c0db  push    rsi
0x18003c0dc  push    rdi
0x18003c0dd  push    r14
0x18003c0df  push    r15
0x18003c0e1  sub     rsp, 38h
0x18003c0e5  xor     r14d, r14d
0x18003c0e8  mov     rdi, rcx
0x18003c0eb  cmp     [rcx], r14d
0x18003c0ee  jbe     loc_18003C259
0x18003c0f4  lea     r15, [rdx+8]
0x18003c0f8  mov     ebp, r14d
0x18003c0fb  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003c102  add     rbp, rbp
0x18003c105  mov     rax, [rdi+rbp*8+10h]
0x18003c10a  mov     rbx, [rax+1Ch]
0x18003c10e  call    cs:__imp_EnterCriticalSection
0x18003c114  mov     rdx, [r15]
0x18003c117  cmp     rdx, r15
0x18003c11a  jz      loc_18003C235
0x18003c120  lea     r8, [rdx-10h]
0x18003c124  cmp     r8, rbx
0x18003c127  jnz     short loc_18003C137
0x18003c129  mov     rax, [rdi+rbp*8+10h]
0x18003c12e  mov     ecx, [rax+54h]
0x18003c131  cmp     [r8+40h], ecx
0x18003c135  jz      short loc_18003C13C
0x18003c137  mov     rdx, [rdx]
0x18003c13a  jmp     short loc_18003C117
0x18003c13c  lea     rsi, [rbx+10h]
0x18003c140  mov     rax, [rsi]
0x18003c143  cmp     [rax+8], rsi
0x18003c147  jnz     loc_18003C26F
0x18003c14d  mov     rcx, [rbx+18h]
0x18003c151  cmp     [rcx], rsi
0x18003c154  jnz     loc_18003C26F
0x18003c15a  mov     [rcx], rax
0x18003c15d  mov     [rax+8], rcx
0x18003c161  mov     [rbx+18h], rsi
0x18003c165  mov     [rsi], rsi
0x18003c168  mov     rdx, [rbx+8]
0x18003c16c  test    rdx, rdx
0x18003c16f  jz      loc_18003C222
0x18003c175  mov     rax, [rdi+rbp*8+10h]
0x18003c17a  mov     ecx, [rax+50h]
0x18003c17d  mov     [rdx+18h], ecx
0x18003c180  mov     rax, [rdi+rbp*8+10h]
0x18003c185  mov     rcx, [rbx+8]
0x18003c189  movups  xmm0, xmmword ptr [rax+2Ch]
0x18003c18d  movups  xmmword ptr [rcx+1Ch], xmm0
0x18003c191  movups  xmm1, xmmword ptr [rax+3Ch]
0x18003c195  movups  xmmword ptr [rcx+2Ch], xmm1
0x18003c199  mov     eax, [rax+4Ch]
0x18003c19c  mov     [rcx+3Ch], eax
0x18003c19f  cmp     dword ptr [rdi+rbp*8+8], 2
0x18003c1a4  jnz     short loc_18003C1BB
0x18003c1a6  mov     r8, [rdi+rbp*8+10h]
0x18003c1ab  mov     rcx, rbx; struct _SCC_NOTIFY_BLOCK *
0x18003c1ae  lea     rdx, [r8+60h]; unsigned __int16 **
0x18003c1b2  mov     r8d, [r8+58h]; unsigned int
0x18003c1b6  call    ?ScAddCreatedDeletedServiceNames@@YAXPEAU_SCC_NOTIFY_BLOCK@@PEAPEAGK@Z; ScAddCreatedDeletedServiceNames(_SCC_NOTIFY_BLOCK *,ushort * *,ulong)
0x18003c1bb  mov     rcx, [rbx+38h]; ThreadHandle
0x18003c1bf  lea     rdx, ?ScApcNotifyCallback@@YAXPEAX00@Z; ApcRoutine
0x18003c1c6  xor     r9d, r9d; SystemArgument1
0x18003c1c9  mov     [rsp+68h+SystemArgument2], 0; SystemArgument2
0x18003c1d2  mov     r8, rbx; NormalContext
0x18003c1d5  call    cs:__imp_NtQueueApcThread
0x18003c1db  test    eax, eax
0x18003c1dd  js      short loc_18003C222
0x18003c1df  mov     rax, cs:off_1800797C0
0x18003c1e6  lea     rcx, off_1800797B8
0x18003c1ed  cmp     [rax], rcx
0x18003c1f0  jnz     short loc_18003C26F
0x18003c1f2  mov     [rsi+8], rax
0x18003c1f6  mov     [rsi], rcx
0x18003c1f9  mov     [rax], rsi
0x18003c1fc  lea     rax, ?g_SccRemoteNotifyCompletedList@@3U_SCC_SERVER_NOTIFY_LIST@@A; "lstc"
0x18003c203  mov     cs:off_1800797C0, rsi
0x18003c20a  mov     rcx, [rbx+38h]; hObject
0x18003c20e  mov     [rbx+20h], rax
0x18003c212  call    cs:__imp_CloseHandle
0x18003c218  mov     qword ptr [rbx+38h], 0
0x18003c220  jmp     short loc_18003C235
0x18003c222  mov     rcx, [rbx+38h]; hObject
0x18003c226  call    cs:__imp_CloseHandle
0x18003c22c  mov     rcx, rbx; hMem
0x18003c22f  call    cs:__imp_LocalFree
0x18003c235  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003c23c  call    cs:__imp_LeaveCriticalSection
0x18003c242  mov     rcx, [rdi+rbp*8+10h]; hMem
0x18003c247  call    cs:__imp_LocalFree
0x18003c24d  inc     r14d
0x18003c250  cmp     r14d, [rdi]
0x18003c253  jb      loc_18003C0F8
0x18003c259  mov     rcx, rdi
0x18003c25c  add     rsp, 38h
0x18003c260  pop     r15
0x18003c262  pop     r14
0x18003c264  pop     rdi
0x18003c265  pop     rsi
0x18003c266  pop     rbp
0x18003c267  pop     rbx
0x18003c268  jmp     cs:__imp_LocalFree
0x18003c26f  mov     ecx, 3
0x18003c274  int     29h; Win8: RtlFailFast(ecx)
```
