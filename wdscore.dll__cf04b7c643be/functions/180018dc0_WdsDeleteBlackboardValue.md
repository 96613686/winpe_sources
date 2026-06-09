# WdsDeleteBlackboardValue

- ea: `0x180018dc0`
- end: `0x180018e89`
- name: `WdsDeleteBlackboardValue`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000f73c`
- `0x180011c4c`
- `0x180017ab4`
- `0x180018dc0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall WdsDeleteBlackboardValue(unsigned __int64 a1, size_t *a2, const unsigned __int16 *a3)
{
  __int64 v5; // rdx
  CBlackboardFactory *v6; // rbx
  unsigned __int64 v7; // rdi
  CBlackboard **v8; // rdi
  CBlackboard *v9; // rbx
  int v10; // r8d

  if ( a2 )
  {
    v6 = Block;
    if ( Block )
    {
      if ( a1 < 0x64 )
        goto LABEL_15;
      v7 = a1 - 100;
      if ( *((_QWORD *)Block + 2) <= a1 - 100 )
        goto LABEL_15;
      AcquireReadAccess((volatile int *)Block);
      v8 = (CBlackboard **)(*((_QWORD *)v6 + 1) + 16 * v7);
      if ( v8 && *v8 )
        AcquireReadAccess((volatile int *)*v8 + 32);
      ReleaseAccess((volatile int *)v6);
      if ( v8 && (v9 = *v8) != 0 )
      {
        CBlackboard::DeleteKey(*v8, a2, a3);
        ReleaseAccess((volatile int *)v9 + 32);
        if ( v10 )
          return 1;
        v5 = 1168;
      }
      else
      {
LABEL_15:
        v5 = 6;
      }
    }
    else
    {
      v5 = 21;
    }
  }
  else
  {
    v5 = 87;
  }
  (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 8LL))(g_Kernel32, v5);
  return 0;
}

```

## disassembly

```asm
0x180018dc0  push    rbx
0x180018dc2  push    rbp
0x180018dc3  push    rsi
0x180018dc4  push    rdi
0x180018dc5  sub     rsp, 28h
0x180018dc9  mov     rbp, r8
0x180018dcc  mov     rsi, rdx
0x180018dcf  test    rdx, rdx
0x180018dd2  jnz     short loc_180018DDC
0x180018dd4  lea     edx, [rsi+57h]
0x180018dd7  jmp     loc_180018E6A
0x180018ddc  mov     rbx, cs:Block
0x180018de3  test    rbx, rbx
0x180018de6  jnz     short loc_180018DED
0x180018de8  lea     edx, [rbx+15h]
0x180018deb  jmp     short loc_180018E6A
0x180018ded  cmp     rcx, 64h ; 'd'
0x180018df1  jb      short loc_180018E65
0x180018df3  lea     rdi, [rcx-64h]
0x180018df7  cmp     [rbx+10h], rdi
0x180018dfb  jbe     short loc_180018E65
0x180018dfd  mov     rcx, rbx; volatile int *
0x180018e00  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x180018e05  shl     rdi, 4
0x180018e09  add     rdi, [rbx+8]
0x180018e0d  jz      short loc_180018E20
0x180018e0f  mov     rcx, [rdi]
0x180018e12  test    rcx, rcx
0x180018e15  jz      short loc_180018E20
0x180018e17  sub     rcx, 0FFFFFFFFFFFFFF80h; volatile int *
0x180018e1b  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x180018e20  mov     rcx, rbx; volatile int *
0x180018e23  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180018e28  test    rdi, rdi
0x180018e2b  jz      short loc_180018E65
0x180018e2d  mov     rbx, [rdi]
0x180018e30  test    rbx, rbx
0x180018e33  jz      short loc_180018E65
0x180018e35  mov     r8, rbp; unsigned __int16 *
0x180018e38  mov     rdx, rsi; unsigned __int16 *
0x180018e3b  mov     rcx, rbx; this
0x180018e3e  call    ?DeleteKey@CBlackboard@@QEAAHPEBG0@Z; CBlackboard::DeleteKey(ushort const *,ushort const *)
0x180018e43  lea     rcx, [rbx+80h]; volatile int *
0x180018e4a  mov     r8d, eax
0x180018e4d  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180018e52  test    r8d, r8d
0x180018e55  jnz     short loc_180018E5E
0x180018e57  mov     edx, 490h
0x180018e5c  jmp     short loc_180018E6A
0x180018e5e  mov     eax, 1
0x180018e63  jmp     short loc_180018E7F
0x180018e65  mov     edx, 6
0x180018e6a  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180018e71  mov     rax, [rcx]
0x180018e74  mov     rax, [rax+8]
0x180018e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e7d  xor     eax, eax
0x180018e7f  add     rsp, 28h
0x180018e83  pop     rdi
0x180018e84  pop     rsi
0x180018e85  pop     rbp
0x180018e86  pop     rbx
0x180018e87  retn
```
