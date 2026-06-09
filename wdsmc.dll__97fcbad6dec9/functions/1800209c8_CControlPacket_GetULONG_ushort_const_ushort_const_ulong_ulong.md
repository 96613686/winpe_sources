# CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)

- ea: `0x1800209c8`
- end: `0x180020aa7`
- name: `?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z`
- size: `223`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002c70`
- `0x1800067f0`
- `0x180006bc4`
- `0x1800077b0`
- `0x18001bd40`
- `0x180020dc8`
- `0x180021d80`

## callees

- `0x18001a9a8`
- `0x18002048c`
- `0x1800209c8`

## import_xrefs

- `WDSCSL!WdsCpParameterValidate` at `0x180020a39`
- `WDSCSL!WdsCpParameterValidate` at `0x180020a39`
- `WDSCSL!WdsCpParameterQuery` at `0x180020a62`
- `WDSCSL!WdsCpParameterQuery` at `0x180020a62`

## pseudocode

```c
__int64 __fastcall CControlPacket::GetULONG(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int *a5)
{
  unsigned __int16 *v5; // rbx
  int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+30h] [rbp-28h]
  __int64 v13; // [rsp+38h] [rbp-20h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-18h] BYREF
  unsigned int *v15; // [rsp+48h] [rbp-10h] BYREF

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
  v9 = WdsCpParameterValidate(*((_QWORD *)this + 1), v5, 4, 4, 4, 0, 0);
  if ( !v9 )
    v9 = WdsCpParameterQuery(*((_QWORD *)this + 1), v5, 0, 0, 0, &v15);
  if ( v7 )
    goto LABEL_8;
LABEL_10:
  if ( !v9 )
    *a5 = *v15;
  return v9;
}

```

## disassembly

```asm
0x1800209c8  mov     rax, rsp
0x1800209cb  mov     [rax+8], rbx
0x1800209cf  mov     [rax+10h], rbp
0x1800209d3  mov     [rax+18h], rsi
0x1800209d7  push    rdi
0x1800209d8  sub     rsp, 50h
0x1800209dc  and     qword ptr [rax-10h], 0
0x1800209e1  mov     rbx, rdx
0x1800209e4  and     qword ptr [rax-18h], 0
0x1800209e9  mov     rbp, rcx
0x1800209ec  cmp     r9d, 0FFFFFFFFh
0x1800209f0  jnz     short loc_1800209FB
0x1800209f2  test    r8, r8
0x1800209f5  jnz     short loc_1800209FB
0x1800209f7  xor     esi, esi
0x1800209f9  jmp     short loc_180020A1A
0x1800209fb  lea     rax, [rsp+58h+var_18]
0x180020a00  mov     esi, 1
0x180020a05  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x180020a0a  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180020a0f  mov     rbx, [rsp+58h+var_18]
0x180020a14  mov     edi, eax
0x180020a16  test    eax, eax
0x180020a18  jnz     short loc_180020A6E
0x180020a1a  and     dword ptr [rsp+58h+var_28], 0
0x180020a1f  mov     r8d, 4
0x180020a25  and     dword ptr [rsp+58h+var_30], 0
0x180020a2a  mov     r9d, r8d
0x180020a2d  mov     rcx, [rbp+8]
0x180020a31  mov     rdx, rbx
0x180020a34  mov     dword ptr [rsp+58h+var_38], r8d
0x180020a39  call    cs:__imp_WdsCpParameterValidate
0x180020a3f  mov     edi, eax
0x180020a41  test    eax, eax
0x180020a43  jnz     short loc_180020A6A
0x180020a45  mov     rcx, [rbp+8]
0x180020a49  lea     rax, [rsp+58h+var_10]
0x180020a4e  mov     [rsp+58h+var_30], rax
0x180020a53  xor     r9d, r9d
0x180020a56  and     [rsp+58h+var_38], 0
0x180020a5c  xor     r8d, r8d
0x180020a5f  mov     rdx, rbx
0x180020a62  call    cs:__imp_WdsCpParameterQuery
0x180020a68  mov     edi, eax
0x180020a6a  test    esi, esi
0x180020a6c  jz      short loc_180020A7B
0x180020a6e  test    rbx, rbx
0x180020a71  jz      short loc_180020A7B
0x180020a73  mov     rcx, rbx; void *
0x180020a76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020a7b  test    edi, edi
0x180020a7d  jnz     short loc_180020A90
0x180020a7f  mov     rax, [rsp+58h+var_10]
0x180020a84  mov     ecx, [rax]
0x180020a86  mov     rax, [rsp+58h+arg_20]
0x180020a8e  mov     [rax], ecx
0x180020a90  mov     rbx, [rsp+58h+arg_0]
0x180020a95  mov     eax, edi
0x180020a97  mov     rbp, [rsp+58h+arg_8]
0x180020a9c  mov     rsi, [rsp+58h+arg_10]
0x180020aa1  add     rsp, 50h
0x180020aa5  pop     rdi
0x180020aa6  retn
```
