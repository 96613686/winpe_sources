# BinXmlReader::EndElementTag(void)

- ea: `0x180003d20`
- end: `0x180003dae`
- name: `?EndElementTag@BinXmlReader@@AEAAXXZ`
- size: `142`
- prototype: `void __fastcall(BinXmlReader *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004070`
- `0x1800181a0`

## callees

- `0x180003d20`
- `0x180003db4`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlReader::EndElementTag(BinXmlReader *this)
{
  __int64 v1; // rax
  _QWORD *v2; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v4; // [rsp+30h] [rbp-28h]
  int v5; // [rsp+38h] [rbp-20h]
  int v6; // [rsp+3Ch] [rbp-1Ch]
  int v7; // [rsp+40h] [rbp-18h]

  v1 = *((_QWORD *)this + 6);
  v2 = (_QWORD *)((char *)this + 40);
  if ( *v2 == v1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v5 = 13;
    v6 = -1;
    v4 = 0;
    v7 = 1345;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  utl::vector<BinXmlReader::ElementInfo,utl::allocator<BinXmlReader::ElementInfo>>::pop_back(v2);
}

```

## disassembly

```asm
0x180003d20  sub     rsp, 58h
0x180003d24  mov     rax, [rcx+30h]
0x180003d28  add     rcx, 28h ; '('
0x180003d2c  cmp     [rcx], rax
0x180003d2f  jz      short loc_180003D3A
0x180003d31  add     rsp, 58h
0x180003d35  jmp     ?pop_back@?$vector@UElementInfo@BinXmlReader@@V?$allocator@UElementInfo@BinXmlReader@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlReader::ElementInfo,utl::allocator<BinXmlReader::ElementInfo>>::pop_back(void)
0x180003d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d41  lea     rax, WPP_GLOBAL_Control
0x180003d48  cmp     rcx, rax
0x180003d4b  jz      short loc_180003D74
0x180003d4d  test    byte ptr [rcx+1Ch], 2
0x180003d51  jz      short loc_180003D74
0x180003d53  cmp     byte ptr [rcx+19h], 2
0x180003d57  jb      short loc_180003D74
0x180003d59  mov     rcx, [rcx+10h]
0x180003d5d  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003d64  mov     edx, 23h ; '#'
0x180003d69  mov     r9d, 0Dh
0x180003d6f  call    WPP_SF_D
0x180003d74  xorps   xmm0, xmm0
0x180003d77  mov     [rsp+58h+var_20], 0Dh
0x180003d7f  xor     eax, eax
0x180003d81  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x180003d89  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003d90  mov     [rsp+58h+var_28], rax
0x180003d95  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180003d9a  mov     [rsp+58h+var_18], 541h
0x180003da2  movdqu  [rsp+58h+pExceptionObject], xmm0
0x180003da8  call    _CxxThrowException_0
```
