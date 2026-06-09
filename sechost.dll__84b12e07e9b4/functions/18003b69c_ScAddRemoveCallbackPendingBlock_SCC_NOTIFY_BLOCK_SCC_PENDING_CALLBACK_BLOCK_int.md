# ScAddRemoveCallbackPendingBlock(_SCC_NOTIFY_BLOCK *,_SCC_PENDING_CALLBACK_BLOCK * *,int)

- ea: `0x18003b69c`
- end: `0x18003b75c`
- name: `?ScAddRemoveCallbackPendingBlock@@YAHPEAU_SCC_NOTIFY_BLOCK@@PEAPEAU_SCC_PENDING_CALLBACK_BLOCK@@H@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct _SCC_NOTIFY_BLOCK *, struct _SCC_PENDING_CALLBACK_BLOCK **, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b8a4`

## callees

- `0x18003b69c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b70e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b70e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b6ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b6ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b74b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b74b`

## pseudocode

```c
__int64 __fastcall ScAddRemoveCallbackPendingBlock(
        struct _SCC_NOTIFY_BLOCK *a1,
        struct _SCC_PENDING_CALLBACK_BLOCK **a2,
        int a3)
{
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // r8
  _QWORD *v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  _QWORD *v12; // rax

  v5 = 1;
  if ( a3 )
  {
    v10 = LocalAlloc(0, 0x28u);
    v11 = v10;
    if ( !v10 )
    {
      v6 = 0;
      v5 = 0;
      goto LABEL_10;
    }
    *(_DWORD *)v10 = 1802265200;
    v10[3] = *((_QWORD *)a1 + 5);
    *((_DWORD *)v10 + 8) = GetCurrentThreadId();
    v12 = off_180079810;
    if ( *off_180079810 == (_UNKNOWN *)&off_180079808 )
    {
      v11[1] = &off_180079808;
      v11[2] = v12;
      *v12 = v11 + 1;
      off_180079810 = (_UNKNOWN **)(v11 + 1);
      v6 = 0;
      *a2 = (struct _SCC_PENDING_CALLBACK_BLOCK *)v11;
      goto LABEL_10;
    }
LABEL_8:
    __fastfail(3u);
  }
  v6 = *a2;
  v7 = (_QWORD *)((char *)*a2 + 8);
  v8 = *v7;
  if ( *(_QWORD **)(*v7 + 8LL) != v7 )
    goto LABEL_8;
  v9 = (_QWORD *)*((_QWORD *)*a2 + 2);
  if ( (_QWORD *)*v9 != v7 )
    goto LABEL_8;
  *v9 = v8;
  *(_QWORD *)(v8 + 8) = v9;
  v7[1] = v7;
  *v7 = v7;
  *a2 = 0;
LABEL_10:
  LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x18003b69c  push    rbx
0x18003b69e  push    rbp
0x18003b69f  push    rsi
0x18003b6a0  push    rdi
0x18003b6a1  sub     rsp, 28h
0x18003b6a5  mov     rsi, rdx
0x18003b6a8  mov     rbp, rcx
0x18003b6ab  mov     edi, 1
0x18003b6b0  test    r8d, r8d
0x18003b6b3  jnz     short loc_18003B6E5
0x18003b6b5  mov     rcx, [rdx]
0x18003b6b8  lea     rax, [rcx+8]
0x18003b6bc  mov     r8, [rax]
0x18003b6bf  cmp     [r8+8], rax
0x18003b6c3  jnz     short loc_18003B72A
0x18003b6c5  mov     rdx, [rax+8]
0x18003b6c9  cmp     [rdx], rax
0x18003b6cc  jnz     short loc_18003B72A
0x18003b6ce  mov     [rdx], r8
0x18003b6d1  mov     [r8+8], rdx
0x18003b6d5  mov     [rax+8], rax
0x18003b6d9  mov     [rax], rax
0x18003b6dc  mov     qword ptr [rsi], 0
0x18003b6e3  jmp     short loc_18003B74B
0x18003b6e5  mov     edx, 28h ; '('; uBytes
0x18003b6ea  xor     ecx, ecx; uFlags
0x18003b6ec  call    cs:__imp_LocalAlloc
0x18003b6f2  mov     rbx, rax
0x18003b6f5  test    rax, rax
0x18003b6f8  jnz     short loc_18003B700
0x18003b6fa  xor     ecx, ecx
0x18003b6fc  xor     edi, edi
0x18003b6fe  jmp     short loc_18003B74B
0x18003b700  mov     dword ptr [rax], 6B6C6270h
0x18003b706  mov     rax, [rbp+28h]
0x18003b70a  mov     [rbx+18h], rax
0x18003b70e  call    cs:__imp_GetCurrentThreadId
0x18003b714  mov     [rbx+20h], eax
0x18003b717  lea     rdx, off_180079808
0x18003b71e  mov     rax, cs:off_180079810
0x18003b725  cmp     [rax], rdx
0x18003b728  jz      short loc_18003B731
0x18003b72a  mov     ecx, 3
0x18003b72f  int     29h; Win8: RtlFailFast(ecx)
0x18003b731  lea     rcx, [rbx+8]
0x18003b735  mov     [rcx], rdx
0x18003b738  mov     [rcx+8], rax
0x18003b73c  mov     [rax], rcx
0x18003b73f  mov     cs:off_180079810, rcx
0x18003b746  xor     ecx, ecx; hMem
0x18003b748  mov     [rsi], rbx
0x18003b74b  call    cs:__imp_LocalFree
0x18003b751  mov     eax, edi
0x18003b753  add     rsp, 28h
0x18003b757  pop     rdi
0x18003b758  pop     rsi
0x18003b759  pop     rbp
0x18003b75a  pop     rbx
0x18003b75b  retn
```
