# CSafeArray::CSafeArray(tagSAFEARRAY *,int,int,int)

- ea: `0x180005980`
- end: `0x180005a71`
- name: `??0CSafeArray@@QEAA@PEAUtagSAFEARRAY@@HHH@Z`
- size: `241`
- prototype: `CSafeArray *(CSafeArray *__hidden this, struct tagSAFEARRAY *, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800061e0`

## callees

- `0x1800056c0`
- `0x180005980`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800059b3`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800059b3`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180005a11`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180005a11`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800059e0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800059e0`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180005a36`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180005a36`

## pseudocode

```c
CSafeArray *__fastcall CSafeArray::CSafeArray(CSafeArray *this, struct tagSAFEARRAY *a2, int a3, char a4, int a5)
{
  SAFEARRAY **v5; // rdi
  SAFEARRAY *v10; // rcx
  LONG v11; // edx
  SAFEARRAY *v12; // rcx
  HRESULT v14; // eax
  LONG plUbound; // [rsp+58h] [rbp+20h] BYREF

  v5 = (SAFEARRAY **)((char *)this + 32);
  *((_DWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  if ( SafeArrayGetDim(a2) != 1 )
    *((_DWORD *)this + 3) = 1;
  if ( (a4 & 4) != 0 )
  {
    *v5 = a2;
  }
  else
  {
    v14 = SafeArrayCopy(a2, v5);
    if ( v14 == -2147024882 )
      _ThrowMemoryException_();
    if ( v14 )
      *((_DWORD *)this + 3) = 1;
  }
  v10 = *v5;
  plUbound = 0;
  if ( SafeArrayGetUBound(v10, 1u, &plUbound) )
    *((_DWORD *)this + 3) = 1;
  v11 = plUbound;
  v12 = *v5;
  *((_DWORD *)this + 7) = 0;
  *(_DWORD *)this = v11;
  *((_DWORD *)this + 4) = a3;
  *((_DWORD *)this + 6) = v11 + 1;
  *((_DWORD *)this + 2) = a5;
  *((_DWORD *)this + 1) = a4 & 3;
  *((_DWORD *)this + 5) = SafeArrayGetElemsize(v12);
  return this;
}

```

## disassembly

```asm
0x180005980  mov     [rsp+arg_0], rbx
0x180005985  mov     [rsp+arg_8], rbp
0x18000598a  push    rsi
0x18000598b  push    rdi
0x18000598c  push    r14
0x18000598e  sub     rsp, 20h
0x180005992  lea     rdi, [rcx+20h]
0x180005996  mov     dword ptr [rcx+0Ch], 0
0x18000599d  mov     rbx, rcx
0x1800059a0  mov     qword ptr [rdi], 0
0x1800059a7  mov     rcx, rdx; psa
0x1800059aa  mov     esi, r9d
0x1800059ad  mov     r14d, r8d
0x1800059b0  mov     rbp, rdx
0x1800059b3  call    cs:__imp_SafeArrayGetDim
0x1800059b9  cmp     eax, 1
0x1800059bc  jnz     loc_180005A53
0x1800059c2  test    sil, 4
0x1800059c6  jz      short loc_180005A30
0x1800059c8  mov     [rdi], rbp
0x1800059cb  mov     rcx, [rdi]; psa
0x1800059ce  lea     r8, [rsp+38h+plUbound]; plUbound
0x1800059d3  mov     edx, 1; nDim
0x1800059d8  mov     [rsp+38h+plUbound], 0
0x1800059e0  call    cs:__imp_SafeArrayGetUBound
0x1800059e6  test    eax, eax
0x1800059e8  jnz     short loc_180005A65
0x1800059ea  mov     edx, [rsp+38h+plUbound]
0x1800059ee  and     esi, 3
0x1800059f1  mov     rcx, [rdi]; psa
0x1800059f4  mov     dword ptr [rbx+1Ch], 0
0x1800059fb  mov     [rbx], edx
0x1800059fd  lea     eax, [rdx+1]
0x180005a00  mov     [rbx+10h], r14d
0x180005a04  mov     [rbx+18h], eax
0x180005a07  mov     eax, [rsp+38h+arg_20]
0x180005a0b  mov     [rbx+8], eax
0x180005a0e  mov     [rbx+4], esi
0x180005a11  call    cs:__imp_SafeArrayGetElemsize
0x180005a17  mov     rbp, [rsp+38h+arg_8]
0x180005a1c  mov     [rbx+14h], eax
0x180005a1f  mov     rax, rbx
0x180005a22  mov     rbx, [rsp+38h+arg_0]
0x180005a27  add     rsp, 20h
0x180005a2b  pop     r14
0x180005a2d  pop     rdi
0x180005a2e  pop     rsi
0x180005a2f  retn
0x180005a30  mov     rdx, rdi; ppsaOut
0x180005a33  mov     rcx, rbp; psa
0x180005a36  call    cs:__imp_SafeArrayCopy
0x180005a3c  cmp     eax, 8007000Eh
0x180005a41  jz      short loc_180005A5F
0x180005a43  test    eax, eax
0x180005a45  jz      short loc_1800059CB
0x180005a47  mov     dword ptr [rbx+0Ch], 1
0x180005a4e  jmp     loc_1800059CB
0x180005a53  mov     dword ptr [rbx+0Ch], 1
0x180005a5a  jmp     loc_1800059C2
0x180005a5f  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x180005a65  mov     dword ptr [rbx+0Ch], 1
0x180005a6c  jmp     loc_1800059EA
```
