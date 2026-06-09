# BinXmlReader::NextValue(UserBuffer &,BinXmlVariant &)

- ea: `0x180004db0`
- end: `0x180004e5f`
- name: `?NextValue@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@@Z`
- size: `175`
- prototype: `void __fastcall(BinXmlReader *__hidden this, struct UserBuffer *, struct BinXmlVariant *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004070`

## callees

- `0x180004db0`
- `0x180004e70`
- `0x1800231d0`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlReader::NextValue(BinXmlReader *this, struct UserBuffer *a2, struct BinXmlVariant *a3)
{
  __int64 v3; // r11
  int v4; // r10d
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+3Ch] [rbp-1Ch]
  int v9; // [rsp+40h] [rbp-18h]

  v3 = *((unsigned int *)a2 + 2);
  if ( (unsigned int)v3 >= *((_DWORD *)a2 + 3) )
    UserBuffer::ThrowUnexpectedEOFException();
  v4 = *(unsigned __int8 *)(v3 + *(_QWORD *)a2);
  *((_DWORD *)a2 + 2) = v3 + 1;
  *((_DWORD *)a3 + 3) = v4;
  if ( (v4 & 0x80u) != 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v7 = 13;
    v8 = -1;
    v6 = 0;
    v9 = 1118;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  BinXmlReader::NextValueData(this, a2, a3, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180004db0  sub     rsp, 58h
0x180004db4  mov     r11d, [rdx+8]
0x180004db8  cmp     r11d, [rdx+0Ch]
0x180004dbc  jnb     short loc_180004DE5
0x180004dbe  mov     rax, [rdx]
0x180004dc1  movzx   r10d, byte ptr [r11+rax]
0x180004dc6  lea     eax, [r11+1]
0x180004dca  mov     [rdx+8], eax
0x180004dcd  mov     [r8+0Ch], r10d
0x180004dd1  test    r10b, r10b
0x180004dd4  js      short loc_180004DEB
0x180004dd6  mov     r9d, 0FFFFFFFFh; unsigned int
0x180004ddc  add     rsp, 58h
0x180004de0  jmp     ?NextValueData@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@K@Z; BinXmlReader::NextValueData(UserBuffer &,BinXmlVariant &,ulong)
0x180004de5  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x180004deb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004df2  lea     rax, WPP_GLOBAL_Control
0x180004df9  cmp     rcx, rax
0x180004dfc  jz      short loc_180004E25
0x180004dfe  test    byte ptr [rcx+1Ch], 2
0x180004e02  jz      short loc_180004E25
0x180004e04  cmp     byte ptr [rcx+19h], 2
0x180004e08  jb      short loc_180004E25
0x180004e0a  mov     rcx, [rcx+10h]
0x180004e0e  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180004e15  mov     edx, 1Fh
0x180004e1a  mov     r9d, 0Dh
0x180004e20  call    WPP_SF_D
0x180004e25  xorps   xmm0, xmm0
0x180004e28  mov     [rsp+58h+var_20], 0Dh
0x180004e30  xor     eax, eax
0x180004e32  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x180004e3a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180004e41  mov     [rsp+58h+var_28], rax
0x180004e46  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180004e4b  mov     [rsp+58h+var_18], 45Eh
0x180004e53  movdqu  [rsp+58h+pExceptionObject], xmm0
0x180004e59  call    _CxxThrowException_0
```
