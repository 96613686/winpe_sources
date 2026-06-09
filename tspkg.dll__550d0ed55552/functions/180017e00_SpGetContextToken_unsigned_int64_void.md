# SpGetContextToken(unsigned __int64,void * *)

- ea: `0x180017e00`
- end: `0x180017e57`
- name: `?SpGetContextToken@@YAJ_KPEAPEAX@Z`
- size: `87`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003e00`
- `0x180007f00`
- `0x180017e00`

## pseudocode

```c
__int64 __fastcall SpGetContextToken(unsigned __int64 a1, void **a2)
{
  int v3; // ebx
  struct _TS_CONTEXT *v4; // rcx
  void *v5; // rax
  struct _TS_CONTEXT *v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v3 = TSContextTableLookup(a1, &v7);
  if ( v3 < 0 )
  {
    return (unsigned int)-2146893045;
  }
  else
  {
    v4 = v7;
    v5 = (void *)*((_QWORD *)v7 + 5);
    if ( v5 )
      *a2 = v5;
    else
      v3 = -2146893045;
    TSDereferenceContext(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017e00  mov     [rsp+arg_0], rbx
0x180017e05  push    rdi
0x180017e06  sub     rsp, 20h
0x180017e0a  mov     rdi, rdx
0x180017e0d  mov     [rsp+28h+arg_10], 0
0x180017e16  lea     rdx, [rsp+28h+arg_10]; struct _TS_CONTEXT **
0x180017e1b  call    ?TSContextTableLookup@@YAJ_KPEAPEAU_TS_CONTEXT@@@Z; TSContextTableLookup(unsigned __int64,_TS_CONTEXT * *)
0x180017e20  mov     ebx, eax
0x180017e22  test    eax, eax
0x180017e24  js      short loc_180017E45
0x180017e26  mov     rcx, [rsp+28h+arg_10]; struct _TS_CONTEXT *
0x180017e2b  mov     rax, [rcx+28h]
0x180017e2f  test    rax, rax
0x180017e32  jnz     short loc_180017E3B
0x180017e34  mov     ebx, 8009030Bh
0x180017e39  jmp     short loc_180017E3E
0x180017e3b  mov     [rdi], rax
0x180017e3e  call    ?TSDereferenceContext@@YAXPEAU_TS_CONTEXT@@@Z; TSDereferenceContext(_TS_CONTEXT *)
0x180017e43  jmp     short loc_180017E4A
0x180017e45  mov     ebx, 8009030Bh
0x180017e4a  mov     eax, ebx
0x180017e4c  mov     rbx, [rsp+28h+arg_0]
0x180017e51  add     rsp, 20h
0x180017e55  pop     rdi
0x180017e56  retn
```
