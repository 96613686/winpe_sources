# CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180020bd0`
- end: `0x180020cb6`
- name: `?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z`
- size: `230`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002c70`
- `0x180006bc4`
- `0x180006e48`
- `0x1800070ac`
- `0x180021d80`

## callees

- `0x18001a9a8`
- `0x18002048c`
- `0x180020bd0`
- `0x1800244bc`

## import_xrefs

- `WDSCSL!WdsCpParameterValidate` at `0x180020c45`
- `WDSCSL!WdsCpParameterValidate` at `0x180020c45`
- `WDSCSL!WdsCpParameterQuery` at `0x180020c6e`
- `WDSCSL!WdsCpParameterQuery` at `0x180020c6e`

## pseudocode

```c
__int64 __fastcall CControlPacket::GetString(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 **a5)
{
  unsigned __int16 *v5; // rbx
  int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+30h] [rbp-28h]
  __int64 v13; // [rsp+38h] [rbp-20h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-10h] BYREF

  v15 = 0;
  v5 = a2;
  v14 = 0;
  if ( a4 != -1 || a3 )
  {
    v7 = 1;
    v8 = CControlPacket::ConstructName(this, a2, a3, a4, &v14, v11, v12, v13, (__int64)v14);
    v5 = v14;
    v9 = v8;
    if ( v8 )
    {
LABEL_8:
      if ( v5 )
        operator delete(v5);
      goto LABEL_10;
    }
  }
  else
  {
    v7 = 0;
  }
  v9 = WdsCpParameterValidate(*((_QWORD *)this + 1), v5, 32, 2, -2, 0, 0);
  if ( !v9 )
    v9 = WdsCpParameterQuery(*((_QWORD *)this + 1), v5, 0, 0, 0, &v15);
  if ( v7 )
    goto LABEL_8;
LABEL_10:
  if ( !v9 )
    return (unsigned int)DuplicateStringW(v15, a5);
  return v9;
}

```

## disassembly

```asm
0x180020bd0  mov     rax, rsp
0x180020bd3  mov     [rax+8], rbx
0x180020bd7  mov     [rax+10h], rbp
0x180020bdb  mov     [rax+18h], rsi
0x180020bdf  push    rdi
0x180020be0  sub     rsp, 50h
0x180020be4  and     qword ptr [rax-10h], 0
0x180020be9  mov     rbx, rdx
0x180020bec  and     qword ptr [rax-18h], 0
0x180020bf1  mov     rbp, rcx
0x180020bf4  cmp     r9d, 0FFFFFFFFh
0x180020bf8  jnz     short loc_180020C03
0x180020bfa  test    r8, r8
0x180020bfd  jnz     short loc_180020C03
0x180020bff  xor     esi, esi
0x180020c01  jmp     short loc_180020C22
0x180020c03  lea     rax, [rsp+58h+var_18]
0x180020c08  mov     esi, 1
0x180020c0d  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x180020c12  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180020c17  mov     rbx, [rsp+58h+var_18]
0x180020c1c  mov     edi, eax
0x180020c1e  test    eax, eax
0x180020c20  jnz     short loc_180020C7A
0x180020c22  and     dword ptr [rsp+58h+var_28], 0
0x180020c27  mov     r9d, 2
0x180020c2d  and     dword ptr [rsp+58h+var_30], 0
0x180020c32  mov     rdx, rbx
0x180020c35  mov     rcx, [rbp+8]
0x180020c39  mov     dword ptr [rsp+58h+var_38], 0FFFFFFFEh
0x180020c41  lea     r8d, [r9+1Eh]
0x180020c45  call    cs:__imp_WdsCpParameterValidate
0x180020c4b  mov     edi, eax
0x180020c4d  test    eax, eax
0x180020c4f  jnz     short loc_180020C76
0x180020c51  mov     rcx, [rbp+8]
0x180020c55  lea     rax, [rsp+58h+var_10]
0x180020c5a  mov     [rsp+58h+var_30], rax
0x180020c5f  xor     r9d, r9d
0x180020c62  and     [rsp+58h+var_38], 0
0x180020c68  xor     r8d, r8d
0x180020c6b  mov     rdx, rbx
0x180020c6e  call    cs:__imp_WdsCpParameterQuery
0x180020c74  mov     edi, eax
0x180020c76  test    esi, esi
0x180020c78  jz      short loc_180020C87
0x180020c7a  test    rbx, rbx
0x180020c7d  jz      short loc_180020C87
0x180020c7f  mov     rcx, rbx; void *
0x180020c82  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020c87  test    edi, edi
0x180020c89  jnz     short loc_180020C9F
0x180020c8b  mov     rdx, [rsp+58h+arg_20]; unsigned __int16 **
0x180020c93  mov     rcx, [rsp+58h+var_10]; unsigned __int16 *
0x180020c98  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180020c9d  mov     edi, eax
0x180020c9f  mov     rbx, [rsp+58h+arg_0]
0x180020ca4  mov     eax, edi
0x180020ca6  mov     rbp, [rsp+58h+arg_8]
0x180020cab  mov     rsi, [rsp+58h+arg_10]
0x180020cb0  add     rsp, 50h
0x180020cb4  pop     rdi
0x180020cb5  retn
```
