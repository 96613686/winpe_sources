# WriteFileView::WriteFileView(ulong,bool)

- ea: `0x180035338`
- end: `0x18003547a`
- name: `??0WriteFileView@@QEAA@K_N@Z`
- size: `322`
- prototype: `WriteFileView *__fastcall(WriteFileView *__hidden this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180030ed8`
- `0x1800315f8`
- `0x180033f34`

## callees

- `0x180023548`
- `0x180025514`
- `0x180034fa4`
- `0x180035338`
- `0x1800357f0`
- `0x180038fa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WriteFileView *__fastcall WriteFileView::WriteFileView(WriteFileView *this, unsigned int a2, bool a3)
{
  unsigned int v5; // ebx
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+38h] [rbp-20h]
  __int64 v9; // [rsp+3Ch] [rbp-1Ch]
  char v10; // [rsp+44h] [rbp-14h]

  *(_QWORD *)this = &BufferStream::`vftable';
  FileView::FileView((WriteFileView *)((char *)this + 8), a2, a3);
  *(_QWORD *)this = &WriteFileView::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = &WriterStringTable::`vftable';
  *((_QWORD *)this + 9) = 0;
  memset_0((char *)this + 80, 0, 0x100u);
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = &WriterTemplateTable::`vftable';
  *((_QWORD *)this + 44) = 0;
  memset_0((char *)this + 360, 0, 0x80u);
  *((_QWORD *)this + 61) = 0;
  if ( a3 )
  {
    v5 = WriteFileView::TryAllocIfNecessary(this);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3150d6ea63e53c8cf0faf274b57ac488_Traceguids, v5);
      }
      pExceptionObject[0] = &word_18004024A;
      pExceptionObject[1] = 0;
      pExceptionObject[2] = 0;
      v8 = v5;
      v9 = -1;
      v10 = 0;
      throw (EvtException *)pExceptionObject;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180035338  mov     [rsp+arg_8], rbx
0x18003533d  mov     [rsp+arg_0], rcx
0x180035342  push    rdi
0x180035343  sub     rsp, 50h
0x180035347  mov     bl, r8b
0x18003534a  mov     rdi, rcx
0x18003534d  lea     rax, ??_7BufferStream@@6B@; const BufferStream::`vftable'
0x180035354  mov     [rcx], rax
0x180035357  add     rcx, 8; this
0x18003535b  call    ??0FileView@@QEAA@K_N@Z; FileView::FileView(ulong,bool)
0x180035360  nop
0x180035361  lea     rax, ??_7WriteFileView@@6B@; const WriteFileView::`vftable'
0x180035368  mov     [rdi], rax
0x18003536b  mov     qword ptr [rdi+38h], 0
0x180035373  lea     rax, ??_7WriterStringTable@@6B@; const WriterStringTable::`vftable'
0x18003537a  mov     [rdi+40h], rax
0x18003537e  mov     qword ptr [rdi+48h], 0
0x180035386  lea     rcx, [rdi+50h]; void *
0x18003538a  xor     edx, edx; Val
0x18003538c  mov     r8d, 100h; Size
0x180035392  call    memset_0
0x180035397  mov     qword ptr [rdi+150h], 0
0x1800353a2  lea     rax, ??_7WriterTemplateTable@@6B@; const WriterTemplateTable::`vftable'
0x1800353a9  mov     [rdi+158h], rax
0x1800353b0  mov     qword ptr [rdi+160h], 0
0x1800353bb  lea     rcx, [rdi+168h]; void *
0x1800353c2  xor     edx, edx; Val
0x1800353c4  mov     r8d, 80h; Size
0x1800353ca  call    memset_0
0x1800353cf  mov     qword ptr [rdi+1E8h], 0
0x1800353da  test    bl, bl
0x1800353dc  jz      loc_18003546C
0x1800353e2  mov     rcx, rdi; this
0x1800353e5  call    ?TryAllocIfNecessary@WriteFileView@@QEAAKXZ; WriteFileView::TryAllocIfNecessary(void)
0x1800353ea  mov     ebx, eax
0x1800353ec  test    eax, eax
0x1800353ee  jz      short loc_18003546C
0x1800353f0  lea     rax, WPP_GLOBAL_Control
0x1800353f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353fe  cmp     rcx, rax
0x180035401  jz      short loc_18003542A
0x180035403  test    dword ptr [rcx+1Ch], 200h
0x18003540a  jz      short loc_18003542A
0x18003540c  cmp     byte ptr [rcx+19h], 2
0x180035410  jb      short loc_18003542A
0x180035412  mov     edx, 0Ah
0x180035417  mov     r9d, ebx
0x18003541a  lea     r8, WPP_3150d6ea63e53c8cf0faf274b57ac488_Traceguids
0x180035421  mov     rcx, [rcx+10h]
0x180035425  call    WPP_SF_D
0x18003542a  lea     rax, word_18004024A
0x180035431  mov     [rsp+58h+pExceptionObject], rax
0x180035436  mov     [rsp+58h+var_30], 0
0x18003543f  mov     [rsp+58h+var_28], 0
0x180035448  mov     [rsp+58h+var_20], ebx
0x18003544c  mov     [rsp+58h+var_1C], 0FFFFFFFFFFFFFFFFh
0x180035455  mov     [rsp+58h+var_14], 0
0x18003545a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180035461  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180035466  call    _CxxThrowException_0
0x18003546c  mov     rax, rdi
0x18003546f  mov     rbx, [rsp+58h+arg_8]
0x180035474  add     rsp, 50h
0x180035478  pop     rdi
0x180035479  retn
```
