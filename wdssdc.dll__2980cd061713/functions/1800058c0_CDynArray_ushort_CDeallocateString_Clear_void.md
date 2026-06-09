# CDynArray<ushort *,CDeallocateString>::Clear(void)

- ea: `0x1800058c0`
- end: `0x180005925`
- name: `?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005fe8`
- `0x180006ea8`
- `0x180006f00`

## callees

- `0x1800015d4`
- `0x1800058c0`

## pseudocode

```c
void __fastcall CDynArray<unsigned short *,CDeallocateString>::Clear(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  void *v4; // rcx

  if ( *(_DWORD *)(a1 + 12) )
  {
    v2 = *(unsigned int *)(a1 + 12);
    v3 = 0;
    do
    {
      v4 = *(void **)(v3 + *(_QWORD *)a1);
      if ( v4 )
        operator delete(v4);
      v3 += 8;
      --v2;
    }
    while ( v2 );
  }
  if ( *(_QWORD *)a1 )
  {
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800058c0  mov     [rsp+arg_0], rbx
0x1800058c5  mov     [rsp+arg_8], rsi
0x1800058ca  push    rdi
0x1800058cb  sub     rsp, 20h
0x1800058cf  cmp     dword ptr [rcx+0Ch], 0
0x1800058d3  mov     rbx, rcx
0x1800058d6  jbe     short loc_1800058F8
0x1800058d8  mov     esi, [rcx+0Ch]
0x1800058db  xor     edi, edi
0x1800058dd  mov     rax, [rbx]
0x1800058e0  mov     rcx, [rdi+rax]; Block
0x1800058e4  test    rcx, rcx
0x1800058e7  jz      short loc_1800058EE
0x1800058e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800058ee  add     rdi, 8
0x1800058f2  sub     rsi, 1
0x1800058f6  jnz     short loc_1800058DD
0x1800058f8  mov     rcx, [rbx]; Block
0x1800058fb  test    rcx, rcx
0x1800058fe  jz      short loc_180005914
0x180005900  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005905  mov     qword ptr [rbx], 0
0x18000590c  mov     qword ptr [rbx+8], 0
0x180005914  mov     rbx, [rsp+28h+arg_0]
0x180005919  mov     rsi, [rsp+28h+arg_8]
0x18000591e  add     rsp, 20h
0x180005922  pop     rdi
0x180005923  retn
```
