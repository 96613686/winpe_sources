# BinXmlWriter::Attribute(BinXmlString const &)

- ea: `0x18002e548`
- end: `0x18002e64c`
- name: `?Attribute@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z`
- size: `260`
- prototype: `void __fastcall(BinXmlWriter *__hidden this, const struct BinXmlString *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002e300`
- `0x18002ebac`

## callees

- `0x180003780`
- `0x180008b20`
- `0x180023548`
- `0x18002e548`
- `0x18002f81c`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlWriter::Attribute(BinXmlWriter *this, const struct BinXmlString *a2)
{
  bool v2; // zf
  __int64 v5; // rax
  WriteBuffer *v6; // rcx
  WriteBuffer *v7; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+30h] [rbp-28h]
  int v10; // [rsp+38h] [rbp-20h]
  int v11; // [rsp+3Ch] [rbp-1Ch]
  int v12; // [rsp+40h] [rbp-18h]
  char v13; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 19) == 0;
  *((_QWORD *)this + 10) = 0;
  if ( v2 )
  {
    v5 = *((_QWORD *)this + 7);
    if ( *((_QWORD *)this + 6) == v5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 13);
      }
      v9 = 0;
      v10 = 13;
      v11 = -1;
      pExceptionObject = 0;
      v12 = 638;
      throw (EvtException *)&pExceptionObject;
    }
    *(_BYTE *)(*(unsigned int *)(v5 - 8) + *(_QWORD *)(*(_QWORD *)this + 8LL)) |= 0x40u;
    v6 = *(WriteBuffer **)this;
    *((_DWORD *)this + 18) = *(_DWORD *)(*(_QWORD *)this + 16LL);
    WriteBuffer::SetCurrentIndex(v6, *((_DWORD *)v6 + 4) + 4);
  }
  else
  {
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + *((unsigned int *)this + 19)) |= 0x40u;
  }
  v7 = *(WriteBuffer **)this;
  *((_DWORD *)this + 19) = *(_DWORD *)(*(_QWORD *)this + 16LL);
  v13 = 6;
  WriteBuffer::Write(v7, &v13, 1u);
  BinXmlWriter::WriteName(this, a2);
}

```

## disassembly

```asm
0x18002e548  mov     [rsp+arg_8], rbx
0x18002e54d  push    rdi
0x18002e54e  sub     rsp, 50h
0x18002e552  cmp     dword ptr [rcx+4Ch], 0
0x18002e556  mov     rdi, rdx
0x18002e559  mov     rbx, rcx
0x18002e55c  mov     qword ptr [rcx+50h], 0
0x18002e564  jnz     loc_18002E60A
0x18002e56a  mov     rax, [rcx+38h]
0x18002e56e  cmp     [rcx+30h], rax
0x18002e572  jnz     short loc_18002E5E6
0x18002e574  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e57b  lea     rax, WPP_GLOBAL_Control
0x18002e582  mov     ebx, 0Dh
0x18002e587  cmp     rcx, rax
0x18002e58a  jz      short loc_18002E5AE
0x18002e58c  test    byte ptr [rcx+1Ch], 2
0x18002e590  jz      short loc_18002E5AE
0x18002e592  cmp     byte ptr [rcx+19h], 2
0x18002e596  jb      short loc_18002E5AE
0x18002e598  mov     rcx, [rcx+10h]
0x18002e59c  lea     edx, [rbx+8]
0x18002e59f  mov     r9d, ebx
0x18002e5a2  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002e5a9  call    WPP_SF_D
0x18002e5ae  xorps   xmm0, xmm0
0x18002e5b1  mov     [rsp+58h+var_28], 0
0x18002e5ba  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e5c1  mov     [rsp+58h+var_20], ebx
0x18002e5c5  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002e5ca  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x18002e5d2  movdqu  [rsp+58h+pExceptionObject], xmm0
0x18002e5d8  mov     [rsp+58h+var_18], 27Eh
0x18002e5e0  call    _CxxThrowException_0
0x18002e5e6  mov     edx, [rax-8]
0x18002e5e9  mov     rax, [rcx]
0x18002e5ec  mov     rcx, [rax+8]
0x18002e5f0  or      byte ptr [rdx+rcx], 40h
0x18002e5f4  mov     rcx, [rbx]; this
0x18002e5f7  mov     eax, [rcx+10h]
0x18002e5fa  mov     [rbx+48h], eax
0x18002e5fd  mov     edx, [rcx+10h]
0x18002e600  add     edx, 4; unsigned int
0x18002e603  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e608  jmp     short loc_18002E618
0x18002e60a  mov     rax, [rcx]
0x18002e60d  mov     edx, [rcx+4Ch]
0x18002e610  mov     rcx, [rax+8]
0x18002e614  or      byte ptr [rcx+rdx], 40h
0x18002e618  mov     rcx, [rbx]; this
0x18002e61b  lea     rdx, [rsp+58h+arg_0]; void *
0x18002e620  mov     r8d, 1; unsigned int
0x18002e626  mov     eax, [rcx+10h]
0x18002e629  mov     [rbx+4Ch], eax
0x18002e62c  mov     [rsp+58h+arg_0], 6
0x18002e631  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002e636  mov     rdx, rdi; struct BinXmlString *
0x18002e639  mov     rcx, rbx; this
0x18002e63c  call    ?WriteName@BinXmlWriter@@AEAAXAEBVBinXmlString@@@Z; BinXmlWriter::WriteName(BinXmlString const &)
0x18002e641  mov     rbx, [rsp+58h+arg_8]
0x18002e646  add     rsp, 50h
0x18002e64a  pop     rdi
0x18002e64b  retn
```
