# CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180012ac8`
- end: `0x180012bae`
- name: `?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z`
- size: `230`
- prototype: `__int64 __fastcall(CControlPacket *this, unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002bd8`
- `0x18000dde4`
- `0x18000defc`
- `0x18000dfa0`
- `0x1800115e4`

## callees

- `0x180012780`
- `0x180012ac8`
- `0x180013dcc`
- `0x1800150b8`

## import_xrefs

- `WDSCSL!WdsCpParameterQuery` at `0x180012b66`
- `WDSCSL!WdsCpParameterQuery` at `0x180012b66`
- `WDSCSL!WdsCpParameterValidate` at `0x180012b3d`
- `WDSCSL!WdsCpParameterValidate` at `0x180012b3d`

## pseudocode

```c
__int64 __fastcall CControlPacket::GetString(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 **a5)
{
  unsigned __int16 *v5; // rbx
  int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  void *Block; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v12; // [rsp+48h] [rbp-10h] BYREF

  v12 = 0;
  v5 = a2;
  Block = 0;
  if ( a4 != -1 || a3 )
  {
    v7 = 1;
    v8 = CControlPacket::ConstructName(this, a2, a3, a4, (unsigned __int16 **)&Block);
    v5 = (unsigned __int16 *)Block;
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
  v9 = WdsCpParameterValidate(*((_QWORD *)this + 1), v5, 32);
  if ( !v9 )
    v9 = WdsCpParameterQuery(*((_QWORD *)this + 1), v5, 0, 0, 0, &v12);
  if ( v7 )
    goto LABEL_8;
LABEL_10:
  if ( !v9 )
    return DuplicateStringW(v12, a5);
  return v9;
}

```

## disassembly

```asm
0x180012ac8  mov     rax, rsp
0x180012acb  mov     [rax+8], rbx
0x180012acf  mov     [rax+10h], rbp
0x180012ad3  mov     [rax+18h], rsi
0x180012ad7  push    rdi
0x180012ad8  sub     rsp, 50h
0x180012adc  and     qword ptr [rax-10h], 0
0x180012ae1  mov     rbx, rdx
0x180012ae4  and     qword ptr [rax-18h], 0
0x180012ae9  mov     rbp, rcx
0x180012aec  cmp     r9d, 0FFFFFFFFh
0x180012af0  jnz     short loc_180012AFB
0x180012af2  test    r8, r8
0x180012af5  jnz     short loc_180012AFB
0x180012af7  xor     esi, esi
0x180012af9  jmp     short loc_180012B1A
0x180012afb  lea     rax, [rsp+58h+Block]
0x180012b00  mov     esi, 1
0x180012b05  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x180012b0a  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180012b0f  mov     rbx, [rsp+58h+Block]
0x180012b14  mov     edi, eax
0x180012b16  test    eax, eax
0x180012b18  jnz     short loc_180012B72
0x180012b1a  and     [rsp+58h+var_28], 0
0x180012b1f  mov     r9d, 2
0x180012b25  and     dword ptr [rsp+58h+var_30], 0
0x180012b2a  mov     rdx, rbx
0x180012b2d  mov     rcx, [rbp+8]
0x180012b31  mov     dword ptr [rsp+58h+var_38], 0FFFFFFFEh
0x180012b39  lea     r8d, [r9+1Eh]
0x180012b3d  call    cs:__imp_WdsCpParameterValidate
0x180012b43  mov     edi, eax
0x180012b45  test    eax, eax
0x180012b47  jnz     short loc_180012B6E
0x180012b49  mov     rcx, [rbp+8]
0x180012b4d  lea     rax, [rsp+58h+var_10]
0x180012b52  mov     [rsp+58h+var_30], rax
0x180012b57  xor     r9d, r9d
0x180012b5a  and     [rsp+58h+var_38], 0
0x180012b60  xor     r8d, r8d
0x180012b63  mov     rdx, rbx
0x180012b66  call    cs:__imp_WdsCpParameterQuery
0x180012b6c  mov     edi, eax
0x180012b6e  test    esi, esi
0x180012b70  jz      short loc_180012B7F
0x180012b72  test    rbx, rbx
0x180012b75  jz      short loc_180012B7F
0x180012b77  mov     rcx, rbx; Block
0x180012b7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b7f  test    edi, edi
0x180012b81  jnz     short loc_180012B97
0x180012b83  mov     rdx, [rsp+58h+arg_20]; unsigned __int16 **
0x180012b8b  mov     rcx, [rsp+58h+var_10]; unsigned __int16 *
0x180012b90  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180012b95  mov     edi, eax
0x180012b97  mov     rbx, [rsp+58h+arg_0]
0x180012b9c  mov     eax, edi
0x180012b9e  mov     rbp, [rsp+58h+arg_8]
0x180012ba3  mov     rsi, [rsp+58h+arg_10]
0x180012ba8  add     rsp, 50h
0x180012bac  pop     rdi
0x180012bad  retn
```
