# BinXmlWriter::OpenStartElementTag(BinXmlString const &)

- ea: `0x18002e9a8`
- end: `0x18002eb12`
- name: `?OpenStartElementTag@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z`
- size: `362`
- prototype: `void __fastcall(BinXmlWriter *__hidden this, const struct BinXmlString *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002e300`
- `0x18002ebac`

## callees

- `0x180003780`
- `0x180008b20`
- `0x180021478`
- `0x180023548`
- `0x18002e9a8`
- `0x18002f758`
- `0x18002f81c`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlWriter::OpenStartElementTag(BinXmlWriter *this, const struct BinXmlString *a2)
{
  WriteBuffer *v4; // rcx
  __int64 *v5; // rbx
  __int64 v6; // rax
  WriteBuffer *v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rdi
  __int64 *v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h]
  int v14; // [rsp+40h] [rbp-18h]
  int v15; // [rsp+44h] [rbp-14h]
  int v16; // [rsp+48h] [rbp-10h]
  __int16 v17; // [rsp+80h] [rbp+28h] BYREF

  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 104) = 1;
  BinXmlWriter::WriteHeaderTokenIfNecessary(this);
  v4 = *(WriteBuffer **)this;
  v5 = (__int64 *)((char *)this + 48);
  v11 = 0;
  LODWORD(v11) = *((_DWORD *)v4 + 4);
  if ( *((_QWORD *)this + 6) == *((_QWORD *)this + 7)
    || (v6 = *((_QWORD *)this + 7), BYTE4(v11) = 1, !*(_BYTE *)(v6 - 4)) )
  {
    BYTE4(v11) = 0;
  }
  WriteBuffer::Write(v4, &qword_180042C38, 1u);
  if ( *((_BYTE *)this + 105) )
  {
    v7 = *(WriteBuffer **)this;
    v17 = -1;
    WriteBuffer::Write(v7, &v17, 2u);
  }
  WriteBuffer::SetCurrentIndex(*(WriteBuffer **)this, *(_DWORD *)(*(_QWORD *)this + 16LL) + 4);
  BinXmlWriter::WriteName(this, a2);
  v8 = (_QWORD *)*((_QWORD *)this + 7);
  if ( v8 == *((_QWORD **)this + 8) )
  {
    v9 = *v5;
    if ( !utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::_Grow((__int64)v5) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 14);
      }
      v13 = 0;
      v14 = 14;
      v15 = -1;
      pExceptionObject = 0;
      v16 = 614;
      throw (EvtException *)&pExceptionObject;
    }
    v10 = &v11;
    if ( (unsigned __int64)&v11 - v9 < v5[1] - *v5 )
      v10 = (__int64 *)((char *)&v11 + *v5 - v9);
    *(_QWORD *)v5[1] = *v10;
  }
  else
  {
    *v8 = v11;
  }
  v5[1] += 8;
}

```

## disassembly

```asm
0x18002e9a8  push    rbp
0x18002e9aa  push    rbx
0x18002e9ab  push    rsi
0x18002e9ac  push    rdi
0x18002e9ad  mov     rbp, rsp
0x18002e9b0  sub     rsp, 58h
0x18002e9b4  mov     rsi, rdx
0x18002e9b7  mov     qword ptr [rcx+50h], 0
0x18002e9bf  mov     rdi, rcx
0x18002e9c2  mov     qword ptr [rcx+48h], 0
0x18002e9ca  mov     byte ptr [rcx+68h], 1
0x18002e9ce  call    ?WriteHeaderTokenIfNecessary@BinXmlWriter@@AEAAXXZ; BinXmlWriter::WriteHeaderTokenIfNecessary(void)
0x18002e9d3  mov     rcx, [rdi]; this
0x18002e9d6  lea     rbx, [rdi+30h]
0x18002e9da  mov     [rbp+var_38], 0
0x18002e9e2  mov     eax, [rcx+10h]
0x18002e9e5  mov     dword ptr [rbp+var_38], eax
0x18002e9e8  mov     rax, [rbx+8]
0x18002e9ec  cmp     [rbx], rax
0x18002e9ef  jz      short loc_18002E9FF
0x18002e9f1  mov     rax, [rdi+38h]
0x18002e9f5  mov     byte ptr [rbp+var_38+4], 1
0x18002e9f9  cmp     byte ptr [rax-4], 0
0x18002e9fd  jnz     short loc_18002EA03
0x18002e9ff  mov     byte ptr [rbp+var_38+4], 0
0x18002ea03  mov     r8d, 1; unsigned int
0x18002ea09  lea     rdx, qword_180042C38; void *
0x18002ea10  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002ea15  cmp     byte ptr [rdi+69h], 0
0x18002ea19  jz      short loc_18002EA36
0x18002ea1b  mov     rcx, [rdi]; this
0x18002ea1e  lea     rdx, [rbp+arg_0]; void *
0x18002ea22  mov     eax, 0FFFFh
0x18002ea27  mov     r8d, 2; unsigned int
0x18002ea2d  mov     [rbp+arg_0], ax
0x18002ea31  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002ea36  mov     rcx, [rdi]; this
0x18002ea39  mov     edx, [rcx+10h]
0x18002ea3c  add     edx, 4; unsigned int
0x18002ea3f  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002ea44  mov     rdx, rsi; struct BinXmlString *
0x18002ea47  mov     rcx, rdi; this
0x18002ea4a  call    ?WriteName@BinXmlWriter@@AEAAXAEBVBinXmlString@@@Z; BinXmlWriter::WriteName(BinXmlString const &)
0x18002ea4f  mov     rcx, [rbx+8]
0x18002ea53  cmp     rcx, [rbx+10h]
0x18002ea57  jz      short loc_18002EA6E
0x18002ea59  mov     rax, [rbp+var_38]
0x18002ea5d  mov     [rcx], rax
0x18002ea60  add     qword ptr [rbx+8], 8
0x18002ea65  add     rsp, 58h
0x18002ea69  pop     rdi
0x18002ea6a  pop     rsi
0x18002ea6b  pop     rbx
0x18002ea6c  pop     rbp
0x18002ea6d  retn
0x18002ea6e  mov     rdi, [rbx]
0x18002ea71  mov     rcx, rbx
0x18002ea74  call    ?_Grow@?$vector@UElementInfo@BinXmlWriter@@V?$allocator@UElementInfo@BinXmlWriter@@@utl@@@utl@@AEAA_NXZ; utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::_Grow(void)
0x18002ea79  test    al, al
0x18002ea7b  jz      short loc_18002EAA6
0x18002ea7d  mov     r9, [rbx+8]
0x18002ea81  lea     rcx, [rbp+var_38]
0x18002ea85  mov     r8, [rbx]
0x18002ea88  lea     rdx, [rbp+var_38]
0x18002ea8c  mov     rax, r9
0x18002ea8f  sub     rcx, rdi
0x18002ea92  sub     rax, r8
0x18002ea95  cmp     rcx, rax
0x18002ea98  jnb     short loc_18002EA9E
0x18002ea9a  lea     rdx, [rcx+r8]
0x18002ea9e  mov     rax, [rdx]
0x18002eaa1  mov     [r9], rax
0x18002eaa4  jmp     short loc_18002EA60
0x18002eaa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eaad  lea     rax, WPP_GLOBAL_Control
0x18002eab4  mov     ebx, 0Eh
0x18002eab9  cmp     rcx, rax
0x18002eabc  jz      short loc_18002EAE0
0x18002eabe  test    byte ptr [rcx+1Ch], 2
0x18002eac2  jz      short loc_18002EAE0
0x18002eac4  cmp     byte ptr [rcx+19h], 2
0x18002eac8  jb      short loc_18002EAE0
0x18002eaca  mov     rcx, [rcx+10h]
0x18002eace  lea     edx, [rbx+6]
0x18002ead1  mov     r9d, ebx
0x18002ead4  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002eadb  call    WPP_SF_D
0x18002eae0  xorps   xmm0, xmm0
0x18002eae3  mov     [rbp+var_20], 0
0x18002eaeb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002eaf2  mov     [rbp+var_18], ebx
0x18002eaf5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002eaf9  mov     [rbp+var_14], 0FFFFFFFFh
0x18002eb00  movdqu  [rbp+pExceptionObject], xmm0
0x18002eb05  mov     [rbp+var_10], 266h
0x18002eb0c  call    _CxxThrowException_0
```
