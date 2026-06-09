# _FreeExSessionEnumData

- ea: `0x180004720`
- end: `0x1800047d5`
- name: `_FreeExSessionEnumData`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003920`
- `0x180003a50`
- `0x180008720`

## callees

- `0x180004720`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000475e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004778`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004788`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000475e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004778`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004788`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047cd`

## pseudocode

```c
HLOCAL __fastcall FreeExSessionEnumData(_QWORD *a1, unsigned int a2)
{
  unsigned int v3; // edi
  __int64 v5; // rsi
  __int64 v6; // rbx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  HLOCAL result; // rax

  if ( a1 )
  {
    v3 = 0;
    if ( a2 )
    {
      v5 = 0;
      do
      {
        v6 = 7 * v5;
        v7 = (void *)a1[7 * v5 + 2];
        if ( v7 )
          LocalFree(v7);
        v8 = (void *)a1[v6 + 3];
        if ( v8 )
          LocalFree(v8);
        v9 = (void *)a1[v6 + 4];
        if ( v9 )
          LocalFree(v9);
        v10 = (void *)a1[v6 + 5];
        if ( v10 )
          LocalFree(v10);
        v11 = (void *)a1[v6 + 6];
        if ( v11 )
          LocalFree(v11);
        ++v3;
        ++v5;
      }
      while ( v3 < a2 );
    }
    return LocalFree(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180004720  test    rcx, rcx
0x180004723  jnz     short loc_180004726
0x180004725  retn
0x180004726  mov     [rsp+arg_18], rbp
0x18000472b  push    r14
0x18000472d  sub     rsp, 20h
0x180004731  mov     [rsp+28h+arg_10], rdi
0x180004736  mov     ebp, edx
0x180004738  xor     edi, edi
0x18000473a  mov     r14, rcx
0x18000473d  test    edx, edx
0x18000473f  jz      short loc_1800047AB
0x180004741  mov     [rsp+28h+arg_0], rbx
0x180004746  mov     [rsp+28h+arg_8], rsi
0x18000474b  xor     esi, esi
0x18000474d  nop     dword ptr [rax]
0x180004750  imul    rbx, rsi, 38h ; '8'
0x180004754  mov     rcx, [rbx+r14+10h]; hMem
0x180004759  test    rcx, rcx
0x18000475c  jz      short loc_180004764
0x18000475e  call    cs:__imp_LocalFree
0x180004764  mov     rcx, [rbx+r14+18h]; hMem
0x180004769  test    rcx, rcx
0x18000476c  jnz     short loc_1800047C5
0x18000476e  mov     rcx, [rbx+r14+20h]; hMem
0x180004773  test    rcx, rcx
0x180004776  jz      short loc_18000477E
0x180004778  call    cs:__imp_LocalFree
0x18000477e  mov     rcx, [rbx+r14+28h]; hMem
0x180004783  test    rcx, rcx
0x180004786  jz      short loc_18000478E
0x180004788  call    cs:__imp_LocalFree
0x18000478e  mov     rcx, [rbx+r14+30h]; hMem
0x180004793  test    rcx, rcx
0x180004796  jnz     short loc_1800047CD
0x180004798  inc     edi
0x18000479a  inc     rsi
0x18000479d  cmp     edi, ebp
0x18000479f  jb      short loc_180004750
0x1800047a1  mov     rsi, [rsp+28h+arg_8]
0x1800047a6  mov     rbx, [rsp+28h+arg_0]
0x1800047ab  mov     rcx, r14
0x1800047ae  mov     rdi, [rsp+28h+arg_10]
0x1800047b3  mov     rbp, [rsp+28h+arg_18]
0x1800047b8  add     rsp, 20h
0x1800047bc  pop     r14
0x1800047be  jmp     cs:__imp_LocalFree
0x1800047c5  call    cs:__imp_LocalFree
0x1800047cb  jmp     short loc_18000476E
0x1800047cd  call    cs:__imp_LocalFree
0x1800047d3  jmp     short loc_180004798
```
