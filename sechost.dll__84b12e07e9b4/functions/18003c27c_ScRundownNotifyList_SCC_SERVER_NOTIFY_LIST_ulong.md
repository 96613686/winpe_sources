# ScRundownNotifyList(_SCC_SERVER_NOTIFY_LIST *,ulong)

- ea: `0x18003c27c`
- end: `0x18003c3c6`
- name: `?ScRundownNotifyList@@YAXPEAU_SCC_SERVER_NOTIFY_LIST@@K@Z`
- size: `330`
- prototype: `void __fastcall(struct _SCC_SERVER_NOTIFY_LIST *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003be30`

## callees

- `0x18003c27c`

## import_xrefs

- `ntdll!NtQueueApcThread` at `0x18003c308`
- `ntdll!NtQueueApcThread` at `0x18003c308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c356`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c356`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c3a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c3a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c298`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c35f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c35f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c3b8`

## pseudocode

```c
void __fastcall ScRundownNotifyList(struct _SCC_SERVER_NOTIFY_LIST *a1, int a2)
{
  _UNKNOWN **v4; // rbx
  _UNKNOWN ***v5; // rbp
  _QWORD *v6; // rax
  _UNKNOWN **v7; // rdi
  __int64 v8; // rax
  _QWORD *v9; // rax
  void *v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdx

  EnterCriticalSection(&SccCritsec);
  v4 = (_UNKNOWN **)*((_QWORD *)a1 + 1);
  if ( v4 != (_UNKNOWN **)((char *)a1 + 8) )
  {
    while ( 1 )
    {
      v5 = (_UNKNOWN ***)*v4;
      if ( *((_UNKNOWN ***)*v4 + 1) != v4 )
        break;
      v6 = v4[1];
      if ( (_UNKNOWN **)*v6 != v4 )
        break;
      *v6 = v5;
      v7 = v4 - 2;
      v5[1] = (_UNKNOWN **)v6;
      v4[1] = v4;
      *v4 = v4;
      v8 = (__int64)*(v4 - 1);
      if ( v8 && (*(_DWORD *)(v8 + 24) = a2, NtQueueApcThread(v7[7], ScApcNotifyCallback, v4 - 2, 0, 0) >= 0) )
      {
        v9 = off_1800797C0[0];
        if ( *(_UNKNOWN ***)off_1800797C0[0] != &off_1800797B8 )
          break;
        v4[1] = off_1800797C0[0];
        *v4 = &off_1800797B8;
        *v9 = v4;
        off_1800797C0[0] = v4;
        v10 = v7[7];
        v7[4] = &g_SccRemoteNotifyCompletedList;
        CloseHandle(v10);
        v7[7] = 0;
      }
      else
      {
        CloseHandle(v7[7]);
        LocalFree(v4 - 2);
      }
      v4 = (_UNKNOWN **)v5;
      if ( v5 == (_UNKNOWN ***)((char *)a1 + 8) )
        goto LABEL_10;
    }
LABEL_15:
    __fastfail(3u);
  }
LABEL_10:
  v11 = (_QWORD *)((char *)a1 + 24);
  v12 = *((_QWORD *)a1 + 3);
  if ( (struct _SCC_SERVER_NOTIFY_LIST *)v12 != (struct _SCC_SERVER_NOTIFY_LIST *)((char *)a1 + 24) )
  {
    if ( *(_QWORD **)(v12 + 8) != v11 )
      goto LABEL_15;
    v13 = (_QWORD *)*((_QWORD *)a1 + 4);
    if ( (_QWORD *)*v13 != v11 )
      goto LABEL_15;
    *v13 = v12;
    *(_QWORD *)(v12 + 8) = v13;
    *((_QWORD *)a1 + 4) = (char *)a1 + 24;
    *v11 = v11;
  }
  LeaveCriticalSection(&SccCritsec);
  LocalFree(a1);
}

```

## disassembly

```asm
0x18003c27c  push    rbx
0x18003c27e  push    rbp
0x18003c27f  push    rsi
0x18003c280  push    rdi
0x18003c281  push    r12
0x18003c283  push    r14
0x18003c285  push    r15
0x18003c287  sub     rsp, 30h
0x18003c28b  mov     rsi, rcx
0x18003c28e  mov     r15d, edx
0x18003c291  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003c298  call    cs:__imp_EnterCriticalSection
0x18003c29e  lea     r14, [rsi+8]
0x18003c2a2  mov     rbx, [r14]
0x18003c2a5  cmp     rbx, r14
0x18003c2a8  jz      loc_18003C371
0x18003c2ae  lea     r12, off_1800797B8
0x18003c2b5  mov     rbp, [rbx]
0x18003c2b8  cmp     [rbp+8], rbx
0x18003c2bc  jnz     loc_18003C3BF
0x18003c2c2  mov     rax, [rbx+8]
0x18003c2c6  cmp     [rax], rbx
0x18003c2c9  jnz     loc_18003C3BF
0x18003c2cf  mov     [rax], rbp
0x18003c2d2  lea     rdi, [rbx-10h]
0x18003c2d6  mov     [rbp+8], rax
0x18003c2da  mov     [rbx+8], rbx
0x18003c2de  mov     [rbx], rbx
0x18003c2e1  mov     rax, [rdi+8]
0x18003c2e5  test    rax, rax
0x18003c2e8  jz      short loc_18003C352
0x18003c2ea  mov     [rax+18h], r15d
0x18003c2ee  lea     rdx, ?ScApcNotifyCallback@@YAXPEAX00@Z; ApcRoutine
0x18003c2f5  mov     rcx, [rdi+38h]; ThreadHandle
0x18003c2f9  xor     r9d, r9d; SystemArgument1
0x18003c2fc  mov     r8, rdi; NormalContext
0x18003c2ff  mov     [rsp+68h+SystemArgument2], 0; SystemArgument2
0x18003c308  call    cs:__imp_NtQueueApcThread
0x18003c30e  test    eax, eax
0x18003c310  js      short loc_18003C352
0x18003c312  mov     rax, cs:off_1800797C0
0x18003c319  cmp     [rax], r12
0x18003c31c  jnz     loc_18003C3BF
0x18003c322  mov     [rbx+8], rax
0x18003c326  mov     [rbx], r12
0x18003c329  mov     [rax], rbx
0x18003c32c  lea     rax, ?g_SccRemoteNotifyCompletedList@@3U_SCC_SERVER_NOTIFY_LIST@@A; "lstc"
0x18003c333  mov     cs:off_1800797C0, rbx
0x18003c33a  mov     rcx, [rdi+38h]; hObject
0x18003c33e  mov     [rdi+20h], rax
0x18003c342  call    cs:__imp_CloseHandle
0x18003c348  mov     qword ptr [rdi+38h], 0
0x18003c350  jmp     short loc_18003C365
0x18003c352  mov     rcx, [rdi+38h]; hObject
0x18003c356  call    cs:__imp_CloseHandle
0x18003c35c  mov     rcx, rdi; hMem
0x18003c35f  call    cs:__imp_LocalFree
0x18003c365  mov     rbx, rbp
0x18003c368  cmp     rbp, r14
0x18003c36b  jnz     loc_18003C2B5
0x18003c371  lea     rax, [rsi+18h]
0x18003c375  mov     rcx, [rax]
0x18003c378  cmp     rcx, rax
0x18003c37b  jz      short loc_18003C39A
0x18003c37d  cmp     [rcx+8], rax
0x18003c381  jnz     short loc_18003C3BF
0x18003c383  mov     rdx, [rax+8]
0x18003c387  cmp     [rdx], rax
0x18003c38a  jnz     short loc_18003C3BF
0x18003c38c  mov     [rdx], rcx
0x18003c38f  mov     [rcx+8], rdx
0x18003c393  mov     [rax+8], rax
0x18003c397  mov     [rax], rax
0x18003c39a  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003c3a1  call    cs:__imp_LeaveCriticalSection
0x18003c3a7  mov     rcx, rsi
0x18003c3aa  add     rsp, 30h
0x18003c3ae  pop     r15
0x18003c3b0  pop     r14
0x18003c3b2  pop     r12
0x18003c3b4  pop     rdi
0x18003c3b5  pop     rsi
0x18003c3b6  pop     rbp
0x18003c3b7  pop     rbx
0x18003c3b8  jmp     cs:__imp_LocalFree
0x18003c3bf  mov     ecx, 3
0x18003c3c4  int     29h; Win8: RtlFailFast(ecx)
```
