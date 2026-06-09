# CShellPropertyThunk::GetItemIDFromObjectID(ushort const *,ushort * *,ushort * *)

- ea: `0x140081c6c`
- end: `0x140081d6b`
- name: `?GetItemIDFromObjectID@CShellPropertyThunk@@SAJPEBGPEAPEAG1@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14007752c`
- `0x14007bab0`
- `0x140082150`
- `0x140082280`

## callees

- `0x1400282b0`
- `0x140081c6c`
- `0x1400826b8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140081d47`
- `ole32!CoTaskMemFree` at `0x140081d53`
- `ole32!CoTaskMemFree` at `0x140081d47`
- `ole32!CoTaskMemFree` at `0x140081d53`
- `ole32!CoTaskMemAlloc` at `0x140081ccf`
- `ole32!CoTaskMemAlloc` at `0x140081d0b`
- `ole32!CoTaskMemAlloc` at `0x140081ccf`
- `ole32!CoTaskMemAlloc` at `0x140081d0b`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::GetItemIDFromObjectID(unsigned __int16 *a1, LPVOID *a2, LPVOID *a3)
{
  unsigned __int16 v6; // cx
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // rdi
  const unsigned __int16 *v9; // rax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  int v12; // ebx
  __int64 v13; // rbx
  unsigned __int16 *v14; // rax

  *a2 = 0;
  *a3 = 0;
  v6 = *a1;
  if ( !v6 )
    goto LABEL_17;
  v7 = a1;
  v8 = 0;
  do
  {
    v9 = v7;
    if ( v6 != 45 )
      v9 = v8;
    ++v7;
    v8 = v9;
    v6 = *v7;
  }
  while ( *v7 );
  if ( !v9 )
  {
LABEL_17:
    v12 = -2147220635;
    goto LABEL_18;
  }
  v10 = v9 - a1;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10 + 2);
  *a2 = v11;
  if ( !v11 )
  {
    v12 = -2147024882;
LABEL_18:
    CoTaskMemFree(*a2);
    *a2 = 0;
    CoTaskMemFree(*a3);
    *a3 = 0;
    return (unsigned int)v12;
  }
  v12 = StringCchCopyNW(v11, v10 + 1, a1, v10);
  if ( v12 < 0 )
    goto LABEL_18;
  v13 = -1;
  do
    ++v13;
  while ( v8[v13 + 1] );
  v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13 + 2);
  *a3 = v14;
  v12 = v14 ? StringCchCopyW(v14, v13 + 1, v8 + 1) : -2147024882;
  if ( v12 < 0 )
    goto LABEL_18;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140081c6c  push    rbx
0x140081c6e  push    rbp
0x140081c6f  push    rsi
0x140081c70  push    rdi
0x140081c71  push    r14
0x140081c73  push    r15
0x140081c75  sub     rsp, 28h
0x140081c79  xor     ebp, ebp
0x140081c7b  mov     rsi, rcx
0x140081c7e  mov     [rdx], rbp
0x140081c81  mov     r14, r8
0x140081c84  mov     [r8], rbp
0x140081c87  mov     r15, rdx
0x140081c8a  movzx   ecx, word ptr [rcx]
0x140081c8d  test    cx, cx
0x140081c90  jz      loc_140081D3F
0x140081c96  mov     rdx, rsi
0x140081c99  mov     edi, ebp
0x140081c9b  cmp     cx, 2Dh ; '-'
0x140081c9f  mov     rax, rdx
0x140081ca2  cmovnz  rax, rdi
0x140081ca6  add     rdx, 2
0x140081caa  mov     rdi, rax
0x140081cad  movzx   ecx, word ptr [rdx]
0x140081cb0  test    cx, cx
0x140081cb3  jnz     short loc_140081C9B
0x140081cb5  test    rax, rax
0x140081cb8  jz      loc_140081D3F
0x140081cbe  mov     rbx, rax
0x140081cc1  sub     rbx, rsi
0x140081cc4  sar     rbx, 1
0x140081cc7  lea     rcx, ds:2[rbx*2]; cb
0x140081ccf  call    cs:__imp_CoTaskMemAlloc
0x140081cd5  mov     [r15], rax
0x140081cd8  test    rax, rax
0x140081cdb  jz      short loc_140081D38
0x140081cdd  lea     rdx, [rbx+1]; unsigned __int64
0x140081ce1  mov     r9, rbx; unsigned __int64
0x140081ce4  mov     r8, rsi; unsigned __int16 *
0x140081ce7  mov     rcx, rax; unsigned __int16 *
0x140081cea  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140081cef  mov     ebx, eax
0x140081cf1  test    eax, eax
0x140081cf3  js      short loc_140081D44
0x140081cf5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140081cf9  inc     rbx
0x140081cfc  cmp     [rdi+rbx*2+2], bp
0x140081d01  jnz     short loc_140081CF9
0x140081d03  lea     rcx, ds:2[rbx*2]; cb
0x140081d0b  call    cs:__imp_CoTaskMemAlloc
0x140081d11  mov     [r14], rax
0x140081d14  test    rax, rax
0x140081d17  jz      short loc_140081D2D
0x140081d19  lea     rdx, [rbx+1]; unsigned __int64
0x140081d1d  mov     rcx, rax; unsigned __int16 *
0x140081d20  lea     r8, [rdi+2]; unsigned __int16 *
0x140081d24  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140081d29  mov     ebx, eax
0x140081d2b  jmp     short loc_140081D32
0x140081d2d  mov     ebx, 8007000Eh
0x140081d32  test    ebx, ebx
0x140081d34  jns     short loc_140081D5C
0x140081d36  jmp     short loc_140081D44
0x140081d38  mov     ebx, 8007000Eh
0x140081d3d  jmp     short loc_140081D44
0x140081d3f  mov     ebx, 80040365h
0x140081d44  mov     rcx, [r15]; pv
0x140081d47  call    cs:__imp_CoTaskMemFree
0x140081d4d  mov     [r15], rbp
0x140081d50  mov     rcx, [r14]; pv
0x140081d53  call    cs:__imp_CoTaskMemFree
0x140081d59  mov     [r14], rbp
0x140081d5c  mov     eax, ebx
0x140081d5e  add     rsp, 28h
0x140081d62  pop     r15
0x140081d64  pop     r14
0x140081d66  pop     rdi
0x140081d67  pop     rsi
0x140081d68  pop     rbp
0x140081d69  pop     rbx
0x140081d6a  retn
```
