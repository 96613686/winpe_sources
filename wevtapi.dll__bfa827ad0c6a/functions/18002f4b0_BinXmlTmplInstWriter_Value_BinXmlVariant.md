# BinXmlTmplInstWriter::Value(BinXmlVariant &)

- ea: `0x18002f4b0`
- end: `0x18002f55f`
- name: `?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z`
- size: `175`
- prototype: `void __fastcall(BinXmlTmplInstWriter *__hidden this, struct BinXmlVariant *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180024428`
- `0x180026e90`

## callees

- `0x180023548`
- `0x18002e4dc`
- `0x18002f4b0`
- `0x18002f92c`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlTmplInstWriter::Value(BinXmlTmplInstWriter *this, struct BinXmlVariant *a2)
{
  WriteBuffer *v4; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+3Ch] [rbp-1Ch]
  int v9; // [rsp+40h] [rbp-18h]

  if ( *((_DWORD *)this + 4) >= *((_DWORD *)this + 3) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 13);
    }
    v6 = 0;
    v7 = 13;
    v8 = -1;
    pExceptionObject = 0;
    v9 = 270;
    throw (EvtException *)&pExceptionObject;
  }
  v4 = *(WriteBuffer **)this;
  *((_DWORD *)this + 5) = *((_DWORD *)v4 + 4);
  WriteVariantValueData(v4, a2, 0);
  BinXmlTmplInstWriter::AdjustValueSpec(this, *((_DWORD *)a2 + 3));
}

```

## disassembly

```asm
0x18002f4b0  mov     [rsp+arg_0], rbx
0x18002f4b5  push    rdi
0x18002f4b6  sub     rsp, 50h
0x18002f4ba  mov     eax, [rcx+0Ch]
0x18002f4bd  mov     rdi, rdx
0x18002f4c0  mov     rbx, rcx
0x18002f4c3  cmp     [rcx+10h], eax
0x18002f4c6  jb      short loc_18002F539
0x18002f4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4cf  lea     rax, WPP_GLOBAL_Control
0x18002f4d6  mov     ebx, 0Dh
0x18002f4db  cmp     rcx, rax
0x18002f4de  jz      short loc_18002F501
0x18002f4e0  test    byte ptr [rcx+1Ch], 2
0x18002f4e4  jz      short loc_18002F501
0x18002f4e6  cmp     byte ptr [rcx+19h], 2
0x18002f4ea  jb      short loc_18002F501
0x18002f4ec  mov     rcx, [rcx+10h]
0x18002f4f0  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002f4f7  mov     edx, ebx
0x18002f4f9  mov     r9d, ebx
0x18002f4fc  call    WPP_SF_D
0x18002f501  xorps   xmm0, xmm0
0x18002f504  mov     [rsp+58h+var_28], 0
0x18002f50d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f514  mov     [rsp+58h+var_20], ebx
0x18002f518  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002f51d  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x18002f525  movdqu  [rsp+58h+pExceptionObject], xmm0
0x18002f52b  mov     [rsp+58h+var_18], 10Eh
0x18002f533  call    _CxxThrowException_0
0x18002f539  mov     rcx, [rcx]; this
0x18002f53c  xor     r8d, r8d
0x18002f53f  mov     eax, [rcx+10h]
0x18002f542  mov     [rbx+14h], eax
0x18002f545  call    WriteVariantValueData
0x18002f54a  mov     edx, [rdi+0Ch]; unsigned int
0x18002f54d  mov     rcx, rbx; this
0x18002f550  mov     rbx, [rsp+58h+arg_0]
0x18002f555  add     rsp, 50h
0x18002f559  pop     rdi
0x18002f55a  jmp     ?AdjustValueSpec@BinXmlTmplInstWriter@@AEAAXK@Z; BinXmlTmplInstWriter::AdjustValueSpec(ulong)
```
