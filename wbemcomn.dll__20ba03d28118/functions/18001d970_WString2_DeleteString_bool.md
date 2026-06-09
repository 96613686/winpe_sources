# WString2::DeleteString(bool)

- ea: `0x18001d970`
- end: `0x18001d9d8`
- name: `?DeleteString@WString2@@AEAAX_N@Z`
- size: `104`
- prototype: `void __fastcall(WString2 *this, char)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016f0`
- `0x180001f50`
- `0x1800024f0`
- `0x180011600`
- `0x1800388a0`
- `0x180038c20`
- `0x180040950`
- `0x1800409a0`
- `0x180040ae0`

## callees

- `0x18001d970`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9aa`

## pseudocode

```c
void __fastcall WString2::DeleteString(WString2 *this, char a2)
{
  _WORD *v2; // r8

  v2 = *(_WORD **)this;
  if ( *(char **)this != byte_180070020 )
  {
    if ( a2 )
    {
      if ( hHeap )
      {
        if ( v2 )
          HeapFree(hHeap, 0, v2);
      }
      *((_QWORD *)this + 1) = 0;
      *(_QWORD *)this = byte_180070020;
    }
    else if ( *((_QWORD *)this + 1) > 2u )
    {
      *v2 = 0;
    }
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18001d970  mov     [rsp+arg_8], rbx
0x18001d975  push    rsi
0x18001d976  sub     rsp, 20h
0x18001d97a  mov     r8, [rcx]; lpMem
0x18001d97d  lea     rsi, byte_180070020
0x18001d984  mov     rbx, rcx
0x18001d987  cmp     r8, rsi
0x18001d98a  jz      short loc_18001D9C0
0x18001d98c  mov     [rsp+28h+arg_0], rdi
0x18001d991  xor     edi, edi
0x18001d993  test    dl, dl
0x18001d995  jz      short loc_18001D9CB
0x18001d997  mov     rcx, cs:hHeap; hHeap
0x18001d99e  test    rcx, rcx
0x18001d9a1  jz      short loc_18001D9B0
0x18001d9a3  test    r8, r8
0x18001d9a6  jz      short loc_18001D9B0
0x18001d9a8  xor     edx, edx; dwFlags
0x18001d9aa  call    cs:__imp_HeapFree
0x18001d9b0  mov     [rbx+8], rdi
0x18001d9b4  mov     [rbx], rsi
0x18001d9b7  mov     [rbx+10h], rdi
0x18001d9bb  mov     rdi, [rsp+28h+arg_0]
0x18001d9c0  mov     rbx, [rsp+28h+arg_8]
0x18001d9c5  add     rsp, 20h
0x18001d9c9  pop     rsi
0x18001d9ca  retn
0x18001d9cb  cmp     qword ptr [rcx+8], 2
0x18001d9d0  jbe     short loc_18001D9B7
0x18001d9d2  mov     [r8], di
0x18001d9d6  jmp     short loc_18001D9B7
```
