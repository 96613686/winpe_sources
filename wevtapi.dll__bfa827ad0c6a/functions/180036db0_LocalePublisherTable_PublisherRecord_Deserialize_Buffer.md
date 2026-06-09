# LocalePublisherTable::_PublisherRecord::Deserialize(Buffer &)

- ea: `0x180036db0`
- end: `0x180037325`
- name: `?Deserialize@_PublisherRecord@LocalePublisherTable@@QEAAXAEAVBuffer@@@Z`
- size: `1397`
- prototype: `void(LocalePublisherTable::_PublisherRecord *__hidden this, struct Buffer *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180037500`
- `0x180038354`

## callees

- `0x180009e80`
- `0x180013790`
- `0x18001ec1c`
- `0x180023548`
- `0x18003077c`
- `0x1800364f8`
- `0x180036db0`
- `0x180038fa4`

## pseudocode

```c
void __fastcall LocalePublisherTable::_PublisherRecord::Deserialize(
        LocalePublisherTable::_PublisherRecord *this,
        struct Buffer *a2)
{
  unsigned int i; // edi
  unsigned int j; // edi
  unsigned int k; // edi
  unsigned int m; // edi
  UserBuffer *v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int64 v10; // [rsp+28h] [rbp-38h]
  __int128 pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-20h]
  int v13; // [rsp+48h] [rbp-18h]
  int v14; // [rsp+4Ch] [rbp-14h]
  int v15; // [rsp+50h] [rbp-10h]
  unsigned int v16; // [rsp+A0h] [rbp+40h] BYREF
  int v17; // [rsp+A8h] [rbp+48h] BYREF
  int v18; // [rsp+B0h] [rbp+50h] BYREF

  v16 = 0;
  v18 = 0;
  v17 = 0;
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 32);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( i = 0; i < v16; ++i )
  {
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 32,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 867;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 872;
      throw (EvtException *)&pExceptionObject;
    }
  }
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 64);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( j = 0; j < v16; ++j )
  {
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 64,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 886;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 891;
      throw (EvtException *)&pExceptionObject;
    }
  }
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 96);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( k = 0; k < v16; ++k )
  {
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 96,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 905;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 910;
      throw (EvtException *)&pExceptionObject;
    }
  }
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 128);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( m = 0; ; ++m )
  {
    v8 = (struct Buffer *)((char *)a2 + 8);
    if ( m >= v16 )
      break;
    UserBuffer::Read(v8, &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 128,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 924;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 929;
      throw (EvtException *)&pExceptionObject;
    }
  }
  v16 = 0;
  UserBuffer::Read(v8, &v16, 4u);
  v9 = *((_QWORD *)a2 + 1) + *((unsigned int *)a2 + 4);
  v10 = (unsigned __int64)v16 >> 1;
  AssignOrThrowOOM(this, &v9);
  Buffer::Advance(a2, v16);
}

```

## disassembly

```asm
0x180036db0  push    rbp
0x180036db2  push    rbx
0x180036db3  push    rsi
0x180036db4  push    rdi
0x180036db5  push    r12
0x180036db7  push    r14
0x180036db9  push    r15
0x180036dbb  mov     rbp, rsp
0x180036dbe  sub     rsp, 60h
0x180036dc2  xor     r12d, r12d
0x180036dc5  mov     rsi, rcx
0x180036dc8  add     rcx, 20h ; ' '
0x180036dcc  mov     [rbp+arg_0], r12d
0x180036dd0  mov     [rbp+arg_10], r12d
0x180036dd4  mov     r15, rdx
0x180036dd7  mov     [rbp+arg_8], r12d
0x180036ddb  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x180036de0  lea     rbx, [r15+8]
0x180036de4  mov     rcx, rbx; this
0x180036de7  lea     r8d, [r12+4]; unsigned int
0x180036dec  lea     rdx, [rbp+arg_0]; void *
0x180036df0  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036df5  mov     edi, r12d
0x180036df8  cmp     edi, [rbp+arg_0]
0x180036dfb  jnb     loc_180036F1A
0x180036e01  mov     r8d, 4; unsigned int
0x180036e07  lea     rdx, [rbp+arg_10]; void *
0x180036e0b  mov     rcx, rbx; this
0x180036e0e  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036e13  mov     r8d, 4; unsigned int
0x180036e19  lea     rdx, [rbp+arg_8]; void *
0x180036e1d  mov     rcx, rbx; this
0x180036e20  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036e25  lea     r9, [rbp+arg_8]
0x180036e29  lea     r8, [rbp+arg_10]
0x180036e2d  lea     rdx, [rbp+var_40]
0x180036e31  lea     rcx, [rsi+20h]
0x180036e35  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x180036e3a  cmp     [rbp+var_40], r12
0x180036e3e  jz      short loc_180036EB2
0x180036e40  cmp     byte ptr [rbp+var_38], r12b
0x180036e44  jz      short loc_180036E4A
0x180036e46  inc     edi
0x180036e48  jmp     short loc_180036DF8
0x180036e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e51  lea     rax, WPP_GLOBAL_Control
0x180036e58  mov     ebx, 0Dh
0x180036e5d  cmp     rcx, rax
0x180036e60  jz      short loc_180036E84
0x180036e62  test    byte ptr [rcx+1Ch], 1
0x180036e66  jz      short loc_180036E84
0x180036e68  cmp     byte ptr [rcx+19h], 2
0x180036e6c  jb      short loc_180036E84
0x180036e6e  mov     rcx, [rcx+10h]
0x180036e72  lea     edx, [rbx+19h]
0x180036e75  mov     r9d, ebx
0x180036e78  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180036e7f  call    WPP_SF_D
0x180036e84  xorps   xmm0, xmm0
0x180036e87  mov     [rbp+var_20], r12
0x180036e8b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180036e92  mov     [rbp+var_18], ebx
0x180036e95  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180036e99  mov     [rbp+var_14], 0FFFFFFFFh
0x180036ea0  movdqu  [rbp+pExceptionObject], xmm0
0x180036ea5  mov     [rbp+var_10], 368h
0x180036eac  call    _CxxThrowException_0
0x180036eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180036eb9  lea     rax, WPP_GLOBAL_Control
0x180036ec0  mov     ebx, 0Eh
0x180036ec5  cmp     rcx, rax
0x180036ec8  jz      short loc_180036EEC
0x180036eca  test    byte ptr [rcx+1Ch], 1
0x180036ece  jz      short loc_180036EEC
0x180036ed0  cmp     byte ptr [rcx+19h], 2
0x180036ed4  jb      short loc_180036EEC
0x180036ed6  mov     rcx, [rcx+10h]
0x180036eda  lea     edx, [rbx+17h]
0x180036edd  mov     r9d, ebx
0x180036ee0  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180036ee7  call    WPP_SF_D
0x180036eec  xorps   xmm0, xmm0
0x180036eef  mov     [rbp+var_20], r12
0x180036ef3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180036efa  mov     [rbp+var_18], ebx
0x180036efd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180036f01  mov     [rbp+var_14], 0FFFFFFFFh
0x180036f08  movdqu  [rbp+pExceptionObject], xmm0
0x180036f0d  mov     [rbp+var_10], 363h
0x180036f14  call    _CxxThrowException_0
0x180036f1a  lea     rcx, [rsi+40h]
0x180036f1e  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x180036f23  mov     r8d, 4; unsigned int
0x180036f29  lea     rdx, [rbp+arg_0]; void *
0x180036f2d  mov     rcx, rbx; this
0x180036f30  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036f35  mov     edi, r12d
0x180036f38  cmp     edi, [rbp+arg_0]
0x180036f3b  jnb     loc_18003705A
0x180036f41  mov     r8d, 4; unsigned int
0x180036f47  lea     rdx, [rbp+arg_10]; void *
0x180036f4b  mov     rcx, rbx; this
0x180036f4e  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036f53  mov     r8d, 4; unsigned int
0x180036f59  lea     rdx, [rbp+arg_8]; void *
0x180036f5d  mov     rcx, rbx; this
0x180036f60  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036f65  lea     r9, [rbp+arg_8]
0x180036f69  lea     r8, [rbp+arg_10]
0x180036f6d  lea     rdx, [rbp+var_40]
0x180036f71  lea     rcx, [rsi+40h]
0x180036f75  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x180036f7a  cmp     [rbp+var_40], r12
0x180036f7e  jz      short loc_180036FF2
0x180036f80  cmp     byte ptr [rbp+var_38], r12b
0x180036f84  jz      short loc_180036F8A
0x180036f86  inc     edi
0x180036f88  jmp     short loc_180036F38
0x180036f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f91  lea     rax, WPP_GLOBAL_Control
0x180036f98  mov     ebx, 0Dh
0x180036f9d  cmp     rcx, rax
0x180036fa0  jz      short loc_180036FC4
0x180036fa2  test    byte ptr [rcx+1Ch], 1
0x180036fa6  jz      short loc_180036FC4
0x180036fa8  cmp     byte ptr [rcx+19h], 2
0x180036fac  jb      short loc_180036FC4
0x180036fae  mov     rcx, [rcx+10h]
0x180036fb2  lea     edx, [rbx+1Bh]
0x180036fb5  mov     r9d, ebx
0x180036fb8  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180036fbf  call    WPP_SF_D
0x180036fc4  xorps   xmm0, xmm0
0x180036fc7  mov     [rbp+var_20], r12
0x180036fcb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180036fd2  mov     [rbp+var_18], ebx
0x180036fd5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180036fd9  mov     [rbp+var_14], 0FFFFFFFFh
0x180036fe0  movdqu  [rbp+pExceptionObject], xmm0
0x180036fe5  mov     [rbp+var_10], 37Bh
0x180036fec  call    _CxxThrowException_0
0x180036ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ff9  lea     rax, WPP_GLOBAL_Control
0x180037000  mov     ebx, 0Eh
0x180037005  cmp     rcx, rax
0x180037008  jz      short loc_18003702C
0x18003700a  test    byte ptr [rcx+1Ch], 1
0x18003700e  jz      short loc_18003702C
0x180037010  cmp     byte ptr [rcx+19h], 2
0x180037014  jb      short loc_18003702C
0x180037016  mov     rcx, [rcx+10h]
0x18003701a  lea     edx, [rbx+19h]
0x18003701d  mov     r9d, ebx
0x180037020  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037027  call    WPP_SF_D
0x18003702c  xorps   xmm0, xmm0
0x18003702f  mov     [rbp+var_20], r12
0x180037033  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003703a  mov     [rbp+var_18], ebx
0x18003703d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037041  mov     [rbp+var_14], 0FFFFFFFFh
0x180037048  movdqu  [rbp+pExceptionObject], xmm0
0x18003704d  mov     [rbp+var_10], 376h
0x180037054  call    _CxxThrowException_0
0x18003705a  lea     rcx, [rsi+60h]
0x18003705e  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x180037063  mov     r8d, 4; unsigned int
0x180037069  lea     rdx, [rbp+arg_0]; void *
0x18003706d  mov     rcx, rbx; this
0x180037070  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180037075  mov     edi, r12d
0x180037078  cmp     edi, [rbp+arg_0]
0x18003707b  jnb     loc_18003719A
0x180037081  mov     r8d, 4; unsigned int
0x180037087  lea     rdx, [rbp+arg_10]; void *
0x18003708b  mov     rcx, rbx; this
0x18003708e  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180037093  mov     r8d, 4; unsigned int
0x180037099  lea     rdx, [rbp+arg_8]; void *
0x18003709d  mov     rcx, rbx; this
0x1800370a0  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800370a5  lea     r9, [rbp+arg_8]
0x1800370a9  lea     r8, [rbp+arg_10]
0x1800370ad  lea     rdx, [rbp+var_40]
0x1800370b1  lea     rcx, [rsi+60h]
0x1800370b5  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x1800370ba  cmp     [rbp+var_40], r12
0x1800370be  jz      short loc_180037132
0x1800370c0  cmp     byte ptr [rbp+var_38], r12b
0x1800370c4  jz      short loc_1800370CA
0x1800370c6  inc     edi
0x1800370c8  jmp     short loc_180037078
0x1800370ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370d1  lea     rax, WPP_GLOBAL_Control
0x1800370d8  mov     ebx, 0Dh
0x1800370dd  cmp     rcx, rax
0x1800370e0  jz      short loc_180037104
0x1800370e2  test    byte ptr [rcx+1Ch], 1
0x1800370e6  jz      short loc_180037104
0x1800370e8  cmp     byte ptr [rcx+19h], 2
0x1800370ec  jb      short loc_180037104
0x1800370ee  mov     rcx, [rcx+10h]
0x1800370f2  lea     edx, [rbx+1Dh]
0x1800370f5  mov     r9d, ebx
0x1800370f8  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800370ff  call    WPP_SF_D
0x180037104  xorps   xmm0, xmm0
0x180037107  mov     [rbp+var_20], r12
0x18003710b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037112  mov     [rbp+var_18], ebx
0x180037115  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037119  mov     [rbp+var_14], 0FFFFFFFFh
0x180037120  movdqu  [rbp+pExceptionObject], xmm0
0x180037125  mov     [rbp+var_10], 38Eh
0x18003712c  call    _CxxThrowException_0
0x180037132  mov     rcx, cs:WPP_GLOBAL_Control
0x180037139  lea     rax, WPP_GLOBAL_Control
0x180037140  mov     ebx, 0Eh
0x180037145  cmp     rcx, rax
0x180037148  jz      short loc_18003716C
0x18003714a  test    byte ptr [rcx+1Ch], 1
0x18003714e  jz      short loc_18003716C
0x180037150  cmp     byte ptr [rcx+19h], 2
0x180037154  jb      short loc_18003716C
0x180037156  mov     rcx, [rcx+10h]
0x18003715a  lea     edx, [rbx+1Bh]
0x18003715d  mov     r9d, ebx
0x180037160  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037167  call    WPP_SF_D
0x18003716c  xorps   xmm0, xmm0
0x18003716f  mov     [rbp+var_20], r12
0x180037173  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003717a  mov     [rbp+var_18], ebx
0x18003717d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037181  mov     [rbp+var_14], 0FFFFFFFFh
0x180037188  movdqu  [rbp+pExceptionObject], xmm0
0x18003718d  mov     [rbp+var_10], 389h
0x180037194  call    _CxxThrowException_0
0x18003719a  lea     r14, [rsi+80h]
0x1800371a1  mov     rcx, r14
0x1800371a4  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x1800371a9  mov     r8d, 4; unsigned int
0x1800371af  lea     rdx, [rbp+arg_0]; void *
0x1800371b3  mov     rcx, rbx; this
0x1800371b6  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800371bb  mov     edi, r12d
0x1800371be  mov     r8d, 4; unsigned int
0x1800371c4  mov     rcx, rbx; this
0x1800371c7  cmp     edi, [rbp+arg_0]
0x1800371ca  jnb     loc_1800372DF
0x1800371d0  lea     rdx, [rbp+arg_10]; void *
0x1800371d4  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800371d9  mov     r8d, 4; unsigned int
0x1800371df  lea     rdx, [rbp+arg_8]; void *
0x1800371e3  mov     rcx, rbx; this
0x1800371e6  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800371eb  lea     r9, [rbp+arg_8]
0x1800371ef  mov     rcx, r14
0x1800371f2  lea     r8, [rbp+arg_10]
0x1800371f6  lea     rdx, [rbp+var_40]
0x1800371fa  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x1800371ff  cmp     [rbp+var_40], r12
0x180037203  jz      short loc_180037277
0x180037205  cmp     byte ptr [rbp+var_38], r12b
0x180037209  jz      short loc_18003720F
0x18003720b  inc     edi
0x18003720d  jmp     short loc_1800371BE
0x18003720f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037216  lea     rax, WPP_GLOBAL_Control
0x18003721d  mov     ebx, 0Dh
0x180037222  cmp     rcx, rax
0x180037225  jz      short loc_180037249
0x180037227  test    byte ptr [rcx+1Ch], 1
0x18003722b  jz      short loc_180037249
0x18003722d  cmp     byte ptr [rcx+19h], 2
0x180037231  jb      short loc_180037249
0x180037233  mov     rcx, [rcx+10h]
0x180037237  lea     edx, [rbx+1Fh]
0x18003723a  mov     r9d, ebx
0x18003723d  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037244  call    WPP_SF_D
0x180037249  xorps   xmm0, xmm0
0x18003724c  mov     [rbp+var_20], r12
0x180037250  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037257  mov     [rbp+var_18], ebx
0x18003725a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003725e  mov     [rbp+var_14], 0FFFFFFFFh
0x180037265  movdqu  [rbp+pExceptionObject], xmm0
0x18003726a  mov     [rbp+var_10], 3A1h
0x180037271  call    _CxxThrowException_0
0x180037277  mov     rcx, cs:WPP_GLOBAL_Control
0x18003727e  lea     rax, WPP_GLOBAL_Control
0x180037285  mov     ebx, 0Eh
0x18003728a  cmp     rcx, rax
0x18003728d  jz      short loc_1800372B1
0x18003728f  test    byte ptr [rcx+1Ch], 1
0x180037293  jz      short loc_1800372B1
0x180037295  cmp     byte ptr [rcx+19h], 2
0x180037299  jb      short loc_1800372B1
0x18003729b  mov     rcx, [rcx+10h]
  ... truncated ...
```
