# SetAllParameters

- ea: `0x18001765c`
- end: `0x1800176e1`
- name: `SetAllParameters`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180016fc0`
- `0x180017130`
- `0x1800172c8`
- `0x18001746c`

## callees

- `0x18001d1da`

## import_xrefs

- `NSI!NsiSetAllParametersEx` at `0x1800176c6`
- `NSI!NsiSetAllParametersEx` at `0x1800176c6`

## pseudocode

```c
__int64 __fastcall SetAllParameters(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6, int a7, int a8)
{
  _BYTE v11[16]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+38h] [rbp-40h]
  int v14; // [rsp+40h] [rbp-38h]
  int v15; // [rsp+44h] [rbp-34h]
  __int64 v16; // [rsp+48h] [rbp-30h]
  int v17; // [rsp+50h] [rbp-28h]
  __int64 v18; // [rsp+58h] [rbp-20h]
  int v19; // [rsp+60h] [rbp-18h]

  memset_0(v11, 0, 0x48u);
  v15 = a8;
  v17 = a5;
  v18 = a6;
  v12 = a2;
  v13 = 16;
  v14 = 1;
  v16 = a4;
  v19 = 32;
  return NsiSetAllParametersEx(v11);
}

```

## disassembly

```asm
0x18001765c  mov     [rsp+arg_0], rbx
0x180017661  push    rdi
0x180017662  sub     rsp, 70h
0x180017666  mov     rbx, rdx
0x180017669  lea     rcx, [rsp+78h+var_58]; void *
0x18001766e  xor     edx, edx; Val
0x180017670  mov     rdi, r9
0x180017673  lea     r8d, [rdx+48h]; Size
0x180017677  call    memset_0
0x18001767c  mov     eax, [rsp+78h+arg_38]
0x180017683  lea     rcx, [rsp+78h+var_58]
0x180017688  mov     [rsp+78h+var_34], eax
0x18001768c  mov     eax, [rsp+78h+arg_20]
0x180017693  mov     [rsp+78h+var_28], eax
0x180017697  mov     rax, [rsp+78h+arg_28]
0x18001769f  mov     [rsp+78h+var_20], rax
0x1800176a4  mov     [rsp+78h+var_48], rbx
0x1800176a9  mov     [rsp+78h+var_40], 10h
0x1800176b1  mov     [rsp+78h+var_38], 1
0x1800176b9  mov     [rsp+78h+var_30], rdi
0x1800176be  mov     [rsp+78h+var_18], 20h ; ' '
0x1800176c6  call    cs:__imp_NsiSetAllParametersEx
0x1800176cd  nop     dword ptr [rax+rax+00h]
0x1800176d2  mov     rbx, [rsp+78h+arg_0]
0x1800176da  add     rsp, 70h
0x1800176de  pop     rdi
0x1800176df  retn
```
