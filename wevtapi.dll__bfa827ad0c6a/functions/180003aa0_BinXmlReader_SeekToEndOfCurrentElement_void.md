# BinXmlReader::SeekToEndOfCurrentElement(void)

- ea: `0x180003aa0`
- end: `0x180003d0c`
- name: `?SeekToEndOfCurrentElement@BinXmlReader@@QEAAXXZ`
- size: `620`
- prototype: `void __fastcall(BinXmlReader *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800049a0`
- `0x180007ae4`

## callees

- `0x180003aa0`
- `0x180003db4`
- `0x180004070`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlReader::SeekToEndOfCurrentElement(BinXmlReader *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  int v4; // ecx
  __int64 v5; // rax
  unsigned int v6; // ecx
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  int v8; // [rsp+38h] [rbp-20h]
  int v9; // [rsp+3Ch] [rbp-1Ch]
  int v10; // [rsp+40h] [rbp-18h]

  *((_DWORD *)this + 42) = 0;
  v2 = *((_QWORD *)this + 6);
  if ( *((_QWORD *)this + 5) == v2 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v8 = 13;
    v9 = -1;
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v10 = 2273;
    throw (EvtException *)pExceptionObject;
  }
  if ( *((BinXmlReader **)this + 2) == this )
  {
    if ( *(_DWORD *)(v2 - 4) == -1 )
      goto LABEL_4;
LABEL_9:
    *(_QWORD *)pExceptionObject = 0;
    *(_DWORD *)&pExceptionObject[8] = -1;
    *(_QWORD *)&pExceptionObject[12] = 0;
    pExceptionObject[20] = 0;
    BinXmlReader::NextToken(this, (struct BinXmlToken *)pExceptionObject, 1);
    if ( *(_DWORD *)&pExceptionObject[16] == 4 )
      return;
    goto LABEL_4;
  }
  if ( *(_DWORD *)(v2 - 4) != (unsigned int)((__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 5) )
    goto LABEL_9;
LABEL_4:
  v3 = *((_QWORD *)this + 6);
  if ( *((_QWORD *)this + 5) == v3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v8 = 13;
    v9 = -1;
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v10 = 2311;
    throw (EvtException *)pExceptionObject;
  }
  v4 = *(_DWORD *)(v3 - 12);
  v5 = *((_QWORD *)this + 2);
  v6 = v4 + 1;
  if ( *(_DWORD *)(v5 + 12) <= v6 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v8 = 13;
    v9 = -1;
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v10 = 2318;
    throw (EvtException *)pExceptionObject;
  }
  *(_DWORD *)(v5 + 8) = v6;
  if ( *((_QWORD *)this + 5) == *((_QWORD *)this + 6) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v8 = 13;
    v9 = -1;
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v10 = 1345;
    throw (EvtException *)pExceptionObject;
  }
  utl::vector<BinXmlReader::ElementInfo,utl::allocator<BinXmlReader::ElementInfo>>::pop_back((char *)this + 40);
}

```

## disassembly

```asm
0x180003aa0  push    rbp
0x180003aa2  push    rbx
0x180003aa3  push    rsi
0x180003aa4  push    rdi
0x180003aa5  mov     rbp, rsp
0x180003aa8  sub     rsp, 58h
0x180003aac  mov     rbx, rcx
0x180003aaf  xor     esi, esi
0x180003ab1  mov     [rcx+0A8h], esi
0x180003ab7  mov     rcx, [rcx+30h]
0x180003abb  cmp     [rbx+28h], rcx
0x180003abf  jz      loc_180003B4D
0x180003ac5  cmp     [rbx+10h], rbx
0x180003ac9  jz      loc_180003BB9
0x180003acf  mov     rax, [rbx+48h]
0x180003ad3  sub     rax, [rbx+40h]
0x180003ad7  sar     rax, 5
0x180003adb  cmp     [rcx-4], eax
0x180003ade  jnz     short loc_180003B23
0x180003ae0  mov     rax, [rbx+30h]
0x180003ae4  cmp     [rbx+28h], rax
0x180003ae8  jz      loc_180003BC8
0x180003aee  mov     ecx, [rax-0Ch]
0x180003af1  mov     rax, [rbx+10h]
0x180003af5  inc     ecx
0x180003af7  cmp     [rax+0Ch], ecx
0x180003afa  jbe     loc_180003C34
0x180003b00  mov     [rax+8], ecx
0x180003b03  mov     rax, [rbx+30h]
0x180003b07  cmp     [rbx+28h], rax
0x180003b0b  jz      loc_180003CA0
0x180003b11  lea     rcx, [rbx+28h]
0x180003b15  call    ?pop_back@?$vector@UElementInfo@BinXmlReader@@V?$allocator@UElementInfo@BinXmlReader@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlReader::ElementInfo,utl::allocator<BinXmlReader::ElementInfo>>::pop_back(void)
0x180003b1a  add     rsp, 58h
0x180003b1e  pop     rdi
0x180003b1f  pop     rsi
0x180003b20  pop     rbx
0x180003b21  pop     rbp
0x180003b22  retn
0x180003b23  mov     r8b, 1; bool
0x180003b26  mov     qword ptr [rbp+pExceptionObject], rsi
0x180003b2a  lea     rdx, [rbp+pExceptionObject]; struct BinXmlToken *
0x180003b2e  mov     dword ptr [rbp+pExceptionObject+8], 0FFFFFFFFh
0x180003b35  mov     rcx, rbx; this
0x180003b38  mov     qword ptr [rbp+pExceptionObject+0Ch], rsi
0x180003b3c  mov     [rbp+var_24], sil
0x180003b40  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x180003b45  cmp     dword ptr [rbp-28h], 4
0x180003b49  jz      short loc_180003B1A
0x180003b4b  jmp     short loc_180003AE0
0x180003b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b54  lea     rax, WPP_GLOBAL_Control
0x180003b5b  cmp     rcx, rax
0x180003b5e  jz      short loc_180003B87
0x180003b60  test    byte ptr [rcx+1Ch], 2
0x180003b64  jz      short loc_180003B87
0x180003b66  cmp     byte ptr [rcx+19h], 2
0x180003b6a  jb      short loc_180003B87
0x180003b6c  mov     rcx, [rcx+10h]
0x180003b70  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003b77  mov     edx, 30h ; '0'
0x180003b7c  mov     r9d, 0Dh
0x180003b82  call    WPP_SF_D
0x180003b87  xorps   xmm0, xmm0
0x180003b8a  mov     [rbp-28h], rsi
0x180003b8e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003b95  mov     [rbp+var_20], 0Dh
0x180003b9c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003ba0  mov     [rbp+var_1C], 0FFFFFFFFh
0x180003ba7  movdqu  [rbp+pExceptionObject], xmm0
0x180003bac  mov     [rbp+var_18], 8E1h
0x180003bb3  call    _CxxThrowException_0
0x180003bb9  cmp     dword ptr [rcx-4], 0FFFFFFFFh
0x180003bbd  jnz     loc_180003B23
0x180003bc3  jmp     loc_180003AE0
0x180003bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bcf  lea     rax, WPP_GLOBAL_Control
0x180003bd6  cmp     rcx, rax
0x180003bd9  jz      short loc_180003C02
0x180003bdb  test    byte ptr [rcx+1Ch], 2
0x180003bdf  jz      short loc_180003C02
0x180003be1  cmp     byte ptr [rcx+19h], 2
0x180003be5  jb      short loc_180003C02
0x180003be7  mov     rcx, [rcx+10h]
0x180003beb  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003bf2  mov     edx, 31h ; '1'
0x180003bf7  mov     r9d, 0Dh
0x180003bfd  call    WPP_SF_D
0x180003c02  xorps   xmm0, xmm0
0x180003c05  mov     [rbp-28h], rsi
0x180003c09  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003c10  mov     [rbp+var_20], 0Dh
0x180003c17  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003c1b  mov     [rbp+var_1C], 0FFFFFFFFh
0x180003c22  movdqu  [rbp+pExceptionObject], xmm0
0x180003c27  mov     [rbp+var_18], 907h
0x180003c2e  call    _CxxThrowException_0
0x180003c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c3b  lea     rax, WPP_GLOBAL_Control
0x180003c42  cmp     rcx, rax
0x180003c45  jz      short loc_180003C6E
0x180003c47  test    byte ptr [rcx+1Ch], 2
0x180003c4b  jz      short loc_180003C6E
0x180003c4d  cmp     byte ptr [rcx+19h], 2
0x180003c51  jb      short loc_180003C6E
0x180003c53  mov     rcx, [rcx+10h]
0x180003c57  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003c5e  mov     edx, 32h ; '2'
0x180003c63  mov     r9d, 0Dh
0x180003c69  call    WPP_SF_D
0x180003c6e  xorps   xmm0, xmm0
0x180003c71  mov     [rbp-28h], rsi
0x180003c75  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003c7c  mov     [rbp+var_20], 0Dh
0x180003c83  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003c87  mov     [rbp+var_1C], 0FFFFFFFFh
0x180003c8e  movdqu  [rbp+pExceptionObject], xmm0
0x180003c93  mov     [rbp+var_18], 90Eh
0x180003c9a  call    _CxxThrowException_0
0x180003ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ca7  lea     rax, WPP_GLOBAL_Control
0x180003cae  cmp     rcx, rax
0x180003cb1  jz      short loc_180003CDA
0x180003cb3  test    byte ptr [rcx+1Ch], 2
0x180003cb7  jz      short loc_180003CDA
0x180003cb9  cmp     byte ptr [rcx+19h], 2
0x180003cbd  jb      short loc_180003CDA
0x180003cbf  mov     rcx, [rcx+10h]
0x180003cc3  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003cca  mov     edx, 23h ; '#'
0x180003ccf  mov     r9d, 0Dh
0x180003cd5  call    WPP_SF_D
0x180003cda  xorps   xmm0, xmm0
0x180003cdd  mov     [rbp-28h], rsi
0x180003ce1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003ce8  mov     [rbp+var_20], 0Dh
0x180003cef  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003cf3  mov     [rbp+var_1C], 0FFFFFFFFh
0x180003cfa  movdqu  [rbp+pExceptionObject], xmm0
0x180003cff  mov     [rbp+var_18], 541h
0x180003d06  call    _CxxThrowException_0
```
