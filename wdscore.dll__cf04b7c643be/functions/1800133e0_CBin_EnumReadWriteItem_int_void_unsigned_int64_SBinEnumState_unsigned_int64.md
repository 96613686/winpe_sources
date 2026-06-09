# CBin::EnumReadWriteItem(int,void *,unsigned __int64,SBinEnumState *,unsigned __int64)

- ea: `0x1800133e0`
- end: `0x180013478`
- name: `?EnumReadWriteItem@CBin@@QEAAHHPEAX_KPEAUSBinEnumState@@1@Z`
- size: `152`
- prototype: `__int64 __fastcall(CBin *__hidden this, int, void *, unsigned __int64, struct SBinEnumState *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013b28`
- `0x1800142c8`

## callees

- `0x1800132f8`
- `0x1800133e0`
- `0x1800134ec`

## pseudocode

```c
_BOOL8 __fastcall CBin::EnumReadWriteItem(
        CBin *this,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        struct SBinEnumState *a5,
        unsigned __int64 a6)
{
  _BOOL8 result; // rax
  unsigned __int64 v11; // [rsp+80h] [rbp+18h] BYREF

  result = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( (unsigned int)CBin::EnumRestoreState(this, (CBin *)((char *)this + 296)) )
      {
        a5 = 0;
        v11 = 0;
        if ( (unsigned int)CBin::EnumReadWrite(this, a2, a3, a4, (void **)&a5, &v11, a6 + 16) )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800133e0  push    rbx
0x1800133e2  push    rbp
0x1800133e3  push    rsi
0x1800133e4  push    rdi
0x1800133e5  sub     rsp, 48h
0x1800133e9  mov     rdi, r9
0x1800133ec  mov     rsi, r8
0x1800133ef  mov     ebp, edx
0x1800133f1  mov     rbx, rcx
0x1800133f4  test    r8, r8
0x1800133f7  jz      short loc_18001346C
0x1800133f9  test    r9, r9
0x1800133fc  jz      short loc_18001346C
0x1800133fe  lea     rdx, [rcx+128h]; struct SBinEnumState *
0x180013405  call    ?EnumRestoreState@CBin@@QEAAHAEAUSBinEnumState@@@Z; CBin::EnumRestoreState(SBinEnumState &)
0x18001340a  test    eax, eax
0x18001340c  jz      short loc_18001346C
0x18001340e  mov     rax, [rsp+68h+arg_28]
0x180013416  mov     r9, rdi; unsigned __int64
0x180013419  add     rax, 10h
0x18001341d  mov     [rsp+68h+arg_20], 0
0x180013429  mov     [rsp+68h+var_38], rax; unsigned __int64
0x18001342e  mov     r8, rsi; void *
0x180013431  lea     rax, [rsp+68h+arg_10]
0x180013439  mov     [rsp+68h+arg_10], 0
0x180013445  mov     [rsp+68h+var_40], rax; unsigned __int64 *
0x18001344a  mov     edx, ebp; int
0x18001344c  lea     rax, [rsp+68h+arg_20]
0x180013454  mov     rcx, rbx; this
0x180013457  mov     [rsp+68h+var_48], rax; void **
0x18001345c  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x180013461  test    eax, eax
0x180013463  jz      short loc_18001346C
0x180013465  mov     eax, 1
0x18001346a  jmp     short loc_18001346E
0x18001346c  xor     eax, eax
0x18001346e  add     rsp, 48h
0x180013472  pop     rdi
0x180013473  pop     rsi
0x180013474  pop     rbp
0x180013475  pop     rbx
0x180013476  retn
```
