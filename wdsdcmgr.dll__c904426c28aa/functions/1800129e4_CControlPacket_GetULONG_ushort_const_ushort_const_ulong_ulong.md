# CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)

- ea: `0x1800129e4`
- end: `0x180012ac1`
- name: `?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z`
- size: `221`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002bd8`
- `0x18000d7bc`
- `0x18000dde4`
- `0x18000df40`
- `0x18000dfa0`
- `0x1800115e4`

## callees

- `0x180012780`
- `0x1800129e4`
- `0x1800150b8`

## import_xrefs

- `WDSCSL!WdsCpParameterQuery` at `0x180012a7c`
- `WDSCSL!WdsCpParameterQuery` at `0x180012a7c`
- `WDSCSL!WdsCpParameterValidate` at `0x180012a53`
- `WDSCSL!WdsCpParameterValidate` at `0x180012a53`

## pseudocode

```c
__int64 __fastcall CControlPacket::GetULONG(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int *a5)
{
  unsigned __int16 *v5; // rbx
  int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+30h] [rbp-28h]
  __int64 v13; // [rsp+38h] [rbp-20h]
  void *Block; // [rsp+40h] [rbp-18h] BYREF
  unsigned int *v15; // [rsp+48h] [rbp-10h] BYREF

  v15 = 0;
  v5 = a2;
  Block = 0;
  if ( a3 )
  {
    v7 = 1;
    v8 = CControlPacket::ConstructName(this, a2, a3, -1, (unsigned __int16 **)&Block, v11, v12, v13, (__int64)Block);
    v5 = (unsigned __int16 *)Block;
    v9 = v8;
    if ( v8 )
    {
LABEL_7:
      if ( v5 )
        operator delete(v5);
      goto LABEL_9;
    }
  }
  else
  {
    v7 = 0;
  }
  v9 = WdsCpParameterValidate(*((_QWORD *)this + 1), v5, 4);
  if ( !v9 )
    v9 = WdsCpParameterQuery(*((_QWORD *)this + 1), v5, 0, 0, 0, &v15);
  if ( v7 )
    goto LABEL_7;
LABEL_9:
  if ( !v9 )
    *a5 = *v15;
  return v9;
}

```

## disassembly

```asm
0x1800129e4  mov     rax, rsp
0x1800129e7  mov     [rax+8], rbx
0x1800129eb  mov     [rax+10h], rbp
0x1800129ef  mov     [rax+18h], rsi
0x1800129f3  push    rdi
0x1800129f4  sub     rsp, 50h
0x1800129f8  and     qword ptr [rax-10h], 0
0x1800129fd  mov     rbx, rdx
0x180012a00  and     qword ptr [rax-18h], 0
0x180012a05  mov     rbp, rcx
0x180012a08  test    r8, r8
0x180012a0b  jnz     short loc_180012A11
0x180012a0d  xor     esi, esi
0x180012a0f  jmp     short loc_180012A34
0x180012a11  lea     rax, [rsp+58h+Block]
0x180012a16  or      r9d, 0FFFFFFFFh; unsigned int
0x180012a1a  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x180012a1f  mov     esi, 1
0x180012a24  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180012a29  mov     rbx, [rsp+58h+Block]
0x180012a2e  mov     edi, eax
0x180012a30  test    eax, eax
0x180012a32  jnz     short loc_180012A88
0x180012a34  and     dword ptr [rsp+58h+var_28], 0
0x180012a39  mov     r8d, 4
0x180012a3f  and     dword ptr [rsp+58h+var_30], 0
0x180012a44  mov     r9d, r8d
0x180012a47  mov     rcx, [rbp+8]
0x180012a4b  mov     rdx, rbx
0x180012a4e  mov     dword ptr [rsp+58h+var_38], r8d
0x180012a53  call    cs:__imp_WdsCpParameterValidate
0x180012a59  mov     edi, eax
0x180012a5b  test    eax, eax
0x180012a5d  jnz     short loc_180012A84
0x180012a5f  mov     rcx, [rbp+8]
0x180012a63  lea     rax, [rsp+58h+var_10]
0x180012a68  mov     [rsp+58h+var_30], rax
0x180012a6d  xor     r9d, r9d
0x180012a70  and     [rsp+58h+var_38], 0
0x180012a76  xor     r8d, r8d
0x180012a79  mov     rdx, rbx
0x180012a7c  call    cs:__imp_WdsCpParameterQuery
0x180012a82  mov     edi, eax
0x180012a84  test    esi, esi
0x180012a86  jz      short loc_180012A95
0x180012a88  test    rbx, rbx
0x180012a8b  jz      short loc_180012A95
0x180012a8d  mov     rcx, rbx; Block
0x180012a90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012a95  test    edi, edi
0x180012a97  jnz     short loc_180012AAA
0x180012a99  mov     rax, [rsp+58h+var_10]
0x180012a9e  mov     ecx, [rax]
0x180012aa0  mov     rax, [rsp+58h+arg_20]
0x180012aa8  mov     [rax], ecx
0x180012aaa  mov     rbx, [rsp+58h+arg_0]
0x180012aaf  mov     eax, edi
0x180012ab1  mov     rbp, [rsp+58h+arg_8]
0x180012ab6  mov     rsi, [rsp+58h+arg_10]
0x180012abb  add     rsp, 50h
0x180012abf  pop     rdi
0x180012ac0  retn
```
