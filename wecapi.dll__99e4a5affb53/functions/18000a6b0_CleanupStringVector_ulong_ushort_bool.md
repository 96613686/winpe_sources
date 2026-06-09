# CleanupStringVector(ulong,ushort * *,bool)

- ea: `0x18000a6b0`
- end: `0x18000a724`
- name: `?CleanupStringVector@@YAXKPEAPEAG_N@Z`
- size: `116`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800054c0`
- `0x180006818`
- `0x18000b2b0`

## callees

- `0x1800026c0`
- `0x18000a6b0`

## pseudocode

```c
void __fastcall CleanupStringVector(unsigned int a1, unsigned __int16 **a2, char a3)
{
  unsigned int i; // ebx
  unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  __int64 j; // rax

  if ( a2 )
  {
    for ( i = 0; i < a1; ++i )
    {
      if ( a3 )
      {
        v7 = a2[i];
        if ( v7 )
        {
          v8 = -1;
          do
            ++v8;
          while ( v7[v8] );
          for ( j = 2 * v8; j; --j )
          {
            *(_BYTE *)v7 = 0;
            v7 = (unsigned __int16 *)((char *)v7 + 1);
          }
        }
      }
      operator delete(a2[i]);
    }
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18000a6b0  test    rdx, rdx
0x18000a6b3  jz      short locret_18000A723
0x18000a6b5  push    rbx
0x18000a6b6  push    rbp
0x18000a6b7  push    rsi
0x18000a6b8  push    rdi
0x18000a6b9  push    r14
0x18000a6bb  sub     rsp, 20h
0x18000a6bf  xor     r14d, r14d
0x18000a6c2  mov     bpl, r8b
0x18000a6c5  mov     rdi, rdx
0x18000a6c8  mov     esi, ecx
0x18000a6ca  mov     ebx, r14d
0x18000a6cd  test    ecx, ecx
0x18000a6cf  jz      short loc_18000A711
0x18000a6d1  test    bpl, bpl
0x18000a6d4  jz      short loc_18000A700
0x18000a6d6  mov     eax, ebx
0x18000a6d8  mov     rcx, [rdi+rax*8]
0x18000a6dc  test    rcx, rcx
0x18000a6df  jz      short loc_18000A700
0x18000a6e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a6e5  inc     rax
0x18000a6e8  cmp     [rcx+rax*2], r14w
0x18000a6ed  jnz     short loc_18000A6E5
0x18000a6ef  add     rax, rax
0x18000a6f2  jz      short loc_18000A700
0x18000a6f4  mov     [rcx], r14b
0x18000a6f7  inc     rcx
0x18000a6fa  sub     rax, 1
0x18000a6fe  jnz     short loc_18000A6F4
0x18000a700  mov     ecx, ebx
0x18000a702  mov     rcx, [rdi+rcx*8]; void *
0x18000a706  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a70b  inc     ebx
0x18000a70d  cmp     ebx, esi
0x18000a70f  jb      short loc_18000A6D1
0x18000a711  mov     rcx, rdi; void *
0x18000a714  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a719  add     rsp, 20h
0x18000a71d  pop     r14
0x18000a71f  pop     rdi
0x18000a720  pop     rsi
0x18000a721  pop     rbp
0x18000a722  pop     rbx
0x18000a723  retn
```
