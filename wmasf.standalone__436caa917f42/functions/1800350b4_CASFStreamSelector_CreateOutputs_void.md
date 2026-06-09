# CASFStreamSelector::CreateOutputs(void)

- ea: `0x1800350b4`
- end: `0x1800354e7`
- name: `?CreateOutputs@CASFStreamSelector@@IEAAJXZ`
- size: `1075`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180039510`

## callees

- `0x180001174`
- `0x1800049b8`
- `0x180033438`
- `0x1800338fc`
- `0x180033968`
- `0x180033a40`
- `0x180033ad8`
- `0x180033d00`
- `0x180033da0`
- `0x1800350b4`
- `0x180036234`
- `0x18003947c`
- `0x180039b64`
- `0x18003b038`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::CreateOutputs(CASFStreamSelector *this)
{
  unsigned int i; // ebp
  _DWORD *v3; // rax
  _DWORD *v4; // rdi
  __int64 v5; // rax
  char *v6; // rsi
  unsigned int v7; // r15d
  struct CASFStreamSelector::STREAM_INFO *v8; // r14
  unsigned int v9; // edx
  unsigned int v10; // edi
  unsigned int j; // ebx
  CASFStreamSelector::OUTPUT *v12; // rax
  unsigned int v13; // edx
  __int64 result; // rax
  unsigned int v15; // ebp
  unsigned int v16; // edi
  char *v17; // rsi
  __int64 v18; // rax
  unsigned int v19; // r14d
  __int64 v20; // r12
  CASFStreamSelector::STREAM_GROUP *v21; // rax
  unsigned int v22; // r15d
  char *v23; // r12
  unsigned int v24; // r13d
  struct CASFStreamSelector::STREAM_INFO *v25; // rax
  unsigned int k; // edi
  struct CASFStreamSelector::MULTI_GROUP *v27; // rbp
  unsigned int m; // esi
  struct CASFStreamSelector::OUTPUT *v29; // r14
  CASFStreamSelector *v30; // rcx
  CASFStreamSelector::OUTPUT *v31; // r13
  unsigned int v32; // edi
  struct CASFStreamSelector::STREAM_INFO *v33; // rax
  unsigned int v34; // edi
  unsigned int v35; // r15d
  __int64 v36; // r13
  __int64 v37; // rax
  unsigned int v38; // edx
  int v39; // edi
  unsigned int n; // edi
  __int64 v41; // rbp
  unsigned int ii; // esi
  struct CASFStreamSelector::STREAM_INFO *v43; // rax
  struct CASFStreamSelector::STREAM_INFO *v44; // [rsp+20h] [rbp-58h]
  __int64 v45; // [rsp+28h] [rbp-50h]
  __int16 v46; // [rsp+88h] [rbp+10h]
  CASFStreamSelector::OUTPUT *v47; // [rsp+90h] [rbp+18h]
  CASFStreamSelector::STREAM_GROUP *v48; // [rsp+98h] [rbp+20h]

  for ( i = 0; i < *((_DWORD *)this + 70); ++i )
  {
    v3 = operator new(0x2C8u);
    v4 = v3;
    if ( !v3 )
      return 2147942414LL;
    *((_QWORD *)v3 + 1) = 0;
    *((_WORD *)v3 + 12) = 0;
    *((_BYTE *)v3 + 26) = 0;
    *(_QWORD *)v3 = &CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable';
    *((_QWORD *)v3 + 24) = 0;
    *((_QWORD *)v3 + 25) = v3;
    v3[52] = 0;
    v3[54] = 0;
    CASFStreamSelector::STREAM_GROUP::STREAM_GROUP((CASFStreamSelector::STREAM_GROUP *)(v3 + 56));
    CASFStreamSelector::STREAM_GROUP::STREAM_GROUP((CASFStreamSelector::STREAM_GROUP *)(v4 + 116));
    v4[176] = 1000;
    v4[177] = 1000;
    v5 = CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[]((char *)this + 64, i);
    v6 = (char *)this + 736;
    v7 = *((_DWORD *)this + 238);
    v8 = (struct CASFStreamSelector::STREAM_INFO *)v5;
    if ( (int)CTSparseBlock<unsigned long,CASFStreamSelector::OUTPUT *,20,0>::SetValue((char *)this + 736, v7, v4) < 0 )
    {
      CASFStreamSelector::OUTPUT::`scalar deleting destructor'((CASFStreamSelector::OUTPUT *)v4, v9);
      v10 = *((_DWORD *)this + 238);
      for ( j = 0; j < v10; ++j )
      {
        v12 = (CASFStreamSelector::OUTPUT *)CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](v6, j);
        if ( v12 )
          CASFStreamSelector::OUTPUT::`scalar deleting destructor'(v12, v13);
      }
      CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList(v6);
      result = 2147500037LL;
      *((_DWORD *)v6 + 54) = 0;
      return result;
    }
    ++*((_DWORD *)this + 238);
    *((_WORD *)v8 + 14) = v7;
    CASFStreamSelector::STREAM_GROUP::Add((CASFStreamSelector::STREAM_GROUP *)(v4 + 116), v8);
  }
LABEL_12:
  v15 = *((_DWORD *)this + 238);
  if ( !v15 )
    return 3222079458LL;
  v16 = 0;
  if ( v15 != 1 )
  {
    v17 = (char *)this + 736;
    while ( 2 )
    {
      v46 = v16;
      v18 = CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[]((char *)this + 736, v16++);
      v45 = v18;
      v19 = v16;
      v20 = v18;
      while ( v19 < v15 )
      {
        v47 = (CASFStreamSelector::OUTPUT *)CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](
                                              (char *)this + 736,
                                              v19);
        v21 = (CASFStreamSelector::STREAM_GROUP *)(v20 + 464);
        v22 = 0;
        v48 = (CASFStreamSelector::STREAM_GROUP *)(v20 + 464);
        v23 = (char *)v47 + 464;
LABEL_18:
        if ( v22 >= *((_DWORD *)v21 + 54) )
        {
          v31 = v47;
          v32 = 0;
          if ( *((_DWORD *)v47 + 170) )
          {
            do
            {
              v33 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                                v23,
                                                                v32);
              *((_WORD *)v33 + 14) = v46;
              CASFStreamSelector::STREAM_GROUP::Add(v48, v33);
              ++v32;
            }
            while ( v32 < *((_DWORD *)v47 + 170) );
            v17 = (char *)this + 736;
          }
          v34 = v19 + 1;
          if ( v19 + 1 < v15 )
          {
            do
            {
              v35 = 0;
              v36 = CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](v17, v34);
              if ( *(_DWORD *)(v36 + 680) )
              {
                do
                {
                  v37 = CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](v36 + 464, v35++);
                  --*(_WORD *)(v37 + 28);
                }
                while ( v35 < *(_DWORD *)(v36 + 680) );
                v17 = (char *)this + 736;
              }
              ++v34;
            }
            while ( v34 < v15 );
            v31 = v47;
          }
          CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList(v23);
          *((_DWORD *)v23 + 54) = 0;
          if ( v19 + 1 <= *((_DWORD *)v17 + 54) )
          {
            v39 = 0;
            do
            {
              if ( (int)CTSparseBlock<unsigned long,CASFStreamSelector::OUTPUT *,20,0>::RemoveValue(v17, v19) < 0 )
                break;
              --*((_DWORD *)v17 + 54);
              ++v39;
            }
            while ( !v39 );
          }
          CASFStreamSelector::OUTPUT::`scalar deleting destructor'(v31, v38);
          goto LABEL_12;
        }
        v24 = 0;
        v23 = (char *)v47 + 464;
        v44 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                          v21,
                                                          v22);
        while ( 1 )
        {
          if ( v24 >= *((_DWORD *)v47 + 170) )
          {
            v21 = v48;
            ++v22;
            goto LABEL_18;
          }
          v25 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                            v23,
                                                            v24);
          if ( !(unsigned int)CASFStreamSelector::ExclusiveStreams(this, v44, v25) )
            break;
          ++v24;
        }
        v20 = v45;
        ++v19;
      }
      if ( v16 < v15 - 1 )
        continue;
      break;
    }
  }
  for ( k = 0; k < *((_DWORD *)this + 126); ++k )
  {
    v27 = (struct CASFStreamSelector::MULTI_GROUP *)CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::operator[](
                                                      (char *)this + 288,
                                                      k);
    for ( m = 0; m < *((_DWORD *)this + 238); ++m )
    {
      v29 = (struct CASFStreamSelector::OUTPUT *)CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](
                                                   (char *)this + 736,
                                                   m);
      if ( (unsigned int)CASFStreamSelector::OutputContainsMultiGroup(v30, v29, v27) )
      {
        CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add(v29, v27, 0);
        break;
      }
    }
  }
  for ( n = 0; n < *((_DWORD *)this + 238); ++n )
  {
    v41 = CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[]((char *)this + 736, n);
    for ( ii = 0; ii < *(_DWORD *)(v41 + 680); ++ii )
    {
      v43 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                        v41 + 464,
                                                        ii);
      if ( !*((_DWORD *)v43 + 4) )
        CASFStreamSelector::STREAM_GROUP::Add((CASFStreamSelector::STREAM_GROUP *)(v41 + 224), v43);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800350b4  push    rbx
0x1800350b6  push    rbp
0x1800350b7  push    rsi
0x1800350b8  push    rdi
0x1800350b9  push    r12
0x1800350bb  push    r13
0x1800350bd  push    r14
0x1800350bf  push    r15
0x1800350c1  sub     rsp, 38h
0x1800350c5  xor     r12d, r12d
0x1800350c8  mov     rbx, rcx
0x1800350cb  mov     ebp, r12d
0x1800350ce  mov     r13d, 3E8h
0x1800350d4  cmp     ebp, [rbx+118h]
0x1800350da  jnb     loc_1800351F3
0x1800350e0  mov     ecx, 2C8h; Size
0x1800350e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800350ea  mov     rdi, rax
0x1800350ed  test    rax, rax
0x1800350f0  jz      loc_1800351E9
0x1800350f6  mov     [rax+8], r12
0x1800350fa  lea     rcx, [rdi+0E0h]; this
0x180035101  xor     eax, eax
0x180035103  mov     [rdi+18h], ax
0x180035107  mov     [rdi+1Ah], al
0x18003510a  lea     rax, ??_7?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@6B@; const CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable'
0x180035111  mov     [rdi], rax
0x180035114  mov     [rdi+0C0h], r12
0x18003511b  mov     [rdi+0C8h], rdi
0x180035122  mov     [rdi+0D0h], r12d
0x180035129  mov     [rdi+0D8h], r12d
0x180035130  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x180035135  lea     rcx, [rdi+1D0h]; this
0x18003513c  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x180035141  mov     edx, ebp
0x180035143  mov     [rdi+2C0h], r13d
0x18003514a  lea     rcx, [rbx+40h]
0x18003514e  mov     [rdi+2C4h], r13d
0x180035155  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x18003515a  lea     rsi, [rbx+2E0h]
0x180035161  mov     r8, rdi
0x180035164  mov     r15d, [rsi+0D8h]
0x18003516b  mov     rcx, rsi
0x18003516e  mov     edx, r15d
0x180035171  mov     r14, rax
0x180035174  call    ?SetValue@?$CTSparseBlock@KPEAUOUTPUT@CASFStreamSelector@@$0BE@$0A@@@QEAAJKPEAUOUTPUT@CASFStreamSelector@@@Z; CTSparseBlock<ulong,CASFStreamSelector::OUTPUT *,20,0>::SetValue(ulong,CASFStreamSelector::OUTPUT *)
0x180035179  test    eax, eax
0x18003517b  js      short loc_18003519E
0x18003517d  inc     dword ptr [rsi+0D8h]
0x180035183  lea     rcx, [rdi+1D0h]; this
0x18003518a  mov     rdx, r14; struct CASFStreamSelector::STREAM_INFO *
0x18003518d  mov     [r14+1Ch], r15w
0x180035192  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x180035197  inc     ebp
0x180035199  jmp     loc_1800350D4
0x18003519e  mov     rcx, rdi; this
0x1800351a1  call    ??_GOUTPUT@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::OUTPUT::`scalar deleting destructor'(uint)
0x1800351a6  mov     edi, [rbx+3B8h]
0x1800351ac  mov     ebx, r12d
0x1800351af  test    edi, edi
0x1800351b1  jz      short loc_1800351D0
0x1800351b3  mov     edx, ebx
0x1800351b5  mov     rcx, rsi
0x1800351b8  call    ??A?$CTDynArray@PEAUOUTPUT@CASFStreamSelector@@$0BE@@@QEBAPEAUOUTPUT@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](ulong)
0x1800351bd  test    rax, rax
0x1800351c0  jz      short loc_1800351CA
0x1800351c2  mov     rcx, rax; this
0x1800351c5  call    ??_GOUTPUT@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::OUTPUT::`scalar deleting destructor'(uint)
0x1800351ca  inc     ebx
0x1800351cc  cmp     ebx, edi
0x1800351ce  jb      short loc_1800351B3
0x1800351d0  mov     rcx, rsi
0x1800351d3  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x1800351d8  mov     eax, 80004005h
0x1800351dd  mov     [rsi+0D8h], r12d
0x1800351e4  jmp     loc_1800354CF
0x1800351e9  mov     eax, 8007000Eh
0x1800351ee  jmp     loc_1800354CF
0x1800351f3  mov     [rsp+78h+arg_0], r12d
0x1800351fb  mov     ebp, [rbx+3B8h]
0x180035201  test    ebp, ebp
0x180035203  jz      loc_1800354E0
0x180035209  lea     r15d, [rbp-1]
0x18003520d  mov     edi, r12d
0x180035210  test    r15d, r15d
0x180035213  jz      loc_1800352FC
0x180035219  lea     rsi, [rbx+2E0h]
0x180035220  mov     edx, edi
0x180035222  mov     [rsp+78h+arg_8], edi
0x180035229  mov     rcx, rsi
0x18003522c  call    ??A?$CTDynArray@PEAUOUTPUT@CASFStreamSelector@@$0BE@@@QEBAPEAUOUTPUT@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](ulong)
0x180035231  inc     edi
0x180035233  mov     [rsp+78h+var_50], rax
0x180035238  mov     r14d, edi
0x18003523b  mov     r12, rax
0x18003523e  cmp     r14d, ebp
0x180035241  jnb     loc_1800352EE
0x180035247  mov     edx, r14d
0x18003524a  mov     rcx, rsi
0x18003524d  call    ??A?$CTDynArray@PEAUOUTPUT@CASFStreamSelector@@$0BE@@@QEBAPEAUOUTPUT@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](ulong)
0x180035252  mov     r13, rax
0x180035255  mov     [rsp+78h+arg_10], rax
0x18003525d  lea     rax, [r12+1D0h]
0x180035265  xor     r15d, r15d
0x180035268  mov     [rsp+78h+arg_18], rax
0x180035270  lea     r12, [r13+1D0h]
0x180035277  cmp     r15d, [rax+0D8h]
0x18003527e  jnb     loc_180035354
0x180035284  mov     edx, r15d
0x180035287  mov     rcx, rax
0x18003528a  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x18003528f  mov     r12, [rsp+78h+arg_10]
0x180035297  xor     r13d, r13d
0x18003529a  add     r12, 1D0h
0x1800352a1  mov     [rsp+78h+var_58], rax
0x1800352a6  cmp     r13d, [r12+0D8h]
0x1800352ae  jnb     short loc_1800352D4
0x1800352b0  mov     edx, r13d
0x1800352b3  mov     rcx, r12
0x1800352b6  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x1800352bb  mov     rdx, [rsp+78h+var_58]; struct CASFStreamSelector::STREAM_INFO *
0x1800352c0  mov     r8, rax; struct CASFStreamSelector::STREAM_INFO *
0x1800352c3  mov     rcx, rbx; this
0x1800352c6  call    ?ExclusiveStreams@CASFStreamSelector@@IEAAHPEAUSTREAM_INFO@1@0@Z; CASFStreamSelector::ExclusiveStreams(CASFStreamSelector::STREAM_INFO *,CASFStreamSelector::STREAM_INFO *)
0x1800352cb  test    eax, eax
0x1800352cd  jz      short loc_1800352E1
0x1800352cf  inc     r13d
0x1800352d2  jmp     short loc_1800352A6
0x1800352d4  mov     rax, [rsp+78h+arg_18]
0x1800352dc  inc     r15d
0x1800352df  jmp     short loc_180035277
0x1800352e1  mov     r12, [rsp+78h+var_50]
0x1800352e6  inc     r14d
0x1800352e9  jmp     loc_18003523E
0x1800352ee  lea     eax, [rbp-1]
0x1800352f1  cmp     edi, eax
0x1800352f3  jb      loc_180035220
0x1800352f9  xor     r12d, r12d
0x1800352fc  mov     edi, r12d
0x1800352ff  cmp     [rbx+1F8h], r12d
0x180035306  jbe     loc_180035468
0x18003530c  mov     edx, edi
0x18003530e  lea     rcx, [rbx+120h]
0x180035315  call    ??A?$CTDynArray@PEAUMULTI_GROUP@CASFStreamSelector@@$0BE@@@QEBAPEAUMULTI_GROUP@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::operator[](ulong)
0x18003531a  mov     rbp, rax
0x18003531d  mov     esi, r12d
0x180035320  cmp     esi, [rbx+3B8h]
0x180035326  jnb     loc_18003545A
0x18003532c  lea     rcx, [rbx+2E0h]
0x180035333  mov     edx, esi
0x180035335  call    ??A?$CTDynArray@PEAUOUTPUT@CASFStreamSelector@@$0BE@@@QEBAPEAUOUTPUT@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](ulong)
0x18003533a  mov     r8, rbp; struct CASFStreamSelector::MULTI_GROUP *
0x18003533d  mov     rdx, rax; struct CASFStreamSelector::OUTPUT *
0x180035340  mov     r14, rax
0x180035343  call    ?OutputContainsMultiGroup@CASFStreamSelector@@IEAAHPEAUOUTPUT@1@PEAUMULTI_GROUP@1@@Z; CASFStreamSelector::OutputContainsMultiGroup(CASFStreamSelector::OUTPUT *,CASFStreamSelector::MULTI_GROUP *)
0x180035348  test    eax, eax
0x18003534a  jnz     loc_18003544C
0x180035350  inc     esi
0x180035352  jmp     short loc_180035320
0x180035354  mov     r13, [rsp+78h+arg_10]
0x18003535c  xor     edi, edi
0x18003535e  cmp     [r13+2A8h], edi
0x180035365  jbe     short loc_1800353A1
0x180035367  mov     r15, [rsp+78h+arg_18]
0x18003536f  mov     esi, [rsp+78h+arg_8]
0x180035376  mov     edx, edi
0x180035378  mov     rcx, r12
0x18003537b  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x180035380  mov     rdx, rax; struct CASFStreamSelector::STREAM_INFO *
0x180035383  mov     rcx, r15; this
0x180035386  mov     [rax+1Ch], si
0x18003538a  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x18003538f  inc     edi
0x180035391  cmp     edi, [r13+2A8h]
0x180035398  jb      short loc_180035376
0x18003539a  lea     rsi, [rbx+2E0h]
0x1800353a1  lea     eax, [r14+1]
0x1800353a5  mov     edi, eax
0x1800353a7  cmp     eax, ebp
0x1800353a9  jnb     short loc_1800353FD
0x1800353ab  mov     edx, edi
0x1800353ad  mov     rcx, rsi
0x1800353b0  call    ??A?$CTDynArray@PEAUOUTPUT@CASFStreamSelector@@$0BE@@@QEBAPEAUOUTPUT@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](ulong)
0x1800353b5  xor     r15d, r15d
0x1800353b8  mov     r13, rax
0x1800353bb  cmp     [rax+2A8h], r15d
0x1800353c2  jbe     short loc_1800353EF
0x1800353c4  mov     edx, r15d
0x1800353c7  lea     rcx, [r13+1D0h]
0x1800353ce  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x1800353d3  mov     ecx, 0FFFFh
0x1800353d8  inc     r15d
0x1800353db  add     [rax+1Ch], cx
0x1800353df  cmp     r15d, [r13+2A8h]
0x1800353e6  jb      short loc_1800353C4
0x1800353e8  lea     rsi, [rbx+2E0h]
0x1800353ef  inc     edi
0x1800353f1  cmp     edi, ebp
0x1800353f3  jb      short loc_1800353AB
0x1800353f5  mov     r13, [rsp+78h+arg_10]
0x1800353fd  mov     rcx, r12
0x180035400  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x180035405  mov     dword ptr [r12+0D8h], 0
0x180035411  lea     eax, [r14+1]
0x180035415  xor     r12d, r12d
0x180035418  cmp     eax, [rsi+0D8h]
0x18003541e  ja      short loc_18003543F
0x180035420  mov     edi, r12d
0x180035423  mov     edx, r14d
0x180035426  mov     rcx, rsi
0x180035429  call    ?RemoveValue@?$CTSparseBlock@KPEAUOUTPUT@CASFStreamSelector@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFStreamSelector::OUTPUT *,20,0>::RemoveValue(ulong)
0x18003542e  test    eax, eax
0x180035430  js      short loc_18003543F
0x180035432  dec     dword ptr [rsi+0D8h]
0x180035438  inc     edi
0x18003543a  cmp     edi, 1
0x18003543d  jb      short loc_180035423
0x18003543f  mov     rcx, r13; this
0x180035442  call    ??_GOUTPUT@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::OUTPUT::`scalar deleting destructor'(uint)
0x180035447  jmp     loc_1800351FB
0x18003544c  xor     r8d, r8d
0x18003544f  mov     rdx, rbp
0x180035452  mov     rcx, r14
0x180035455  call    ?Add@?$CTDynArray@PEAUMULTI_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUMULTI_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add(CASFStreamSelector::MULTI_GROUP *,ulong *)
0x18003545a  inc     edi
0x18003545c  cmp     edi, [rbx+1F8h]
0x180035462  jb      loc_18003530C
0x180035468  mov     edi, r12d
0x18003546b  cmp     [rbx+3B8h], r12d
0x180035472  jbe     short loc_1800354C8
0x180035474  mov     edx, edi
0x180035476  lea     rcx, [rbx+2E0h]
0x18003547d  call    ??A?$CTDynArray@PEAUOUTPUT@CASFStreamSelector@@$0BE@@@QEBAPEAUOUTPUT@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::OUTPUT *,20>::operator[](ulong)
0x180035482  mov     rbp, rax
0x180035485  mov     esi, r12d
0x180035488  cmp     [rax+2A8h], r12d
0x18003548f  jbe     short loc_1800354BE
0x180035491  mov     edx, esi
0x180035493  lea     rcx, [rbp+1D0h]
0x18003549a  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x18003549f  cmp     [rax+10h], r12d
0x1800354a3  jnz     short loc_1800354B4
0x1800354a5  lea     rcx, [rbp+0E0h]; this
0x1800354ac  mov     rdx, rax; struct CASFStreamSelector::STREAM_INFO *
0x1800354af  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x1800354b4  inc     esi
0x1800354b6  cmp     esi, [rbp+2A8h]
0x1800354bc  jb      short loc_180035491
0x1800354be  inc     edi
0x1800354c0  cmp     edi, [rbx+3B8h]
0x1800354c6  jb      short loc_180035474
0x1800354c8  mov     eax, [rsp+78h+arg_0]
0x1800354cf  add     rsp, 38h
0x1800354d3  pop     r15
0x1800354d5  pop     r14
0x1800354d7  pop     r13
0x1800354d9  pop     r12
0x1800354db  pop     rdi
0x1800354dc  pop     rsi
0x1800354dd  pop     rbp
0x1800354de  pop     rbx
0x1800354df  retn
0x1800354e0  mov     eax, 0C00D07E2h
0x1800354e5  jmp     short loc_1800354CF
```
