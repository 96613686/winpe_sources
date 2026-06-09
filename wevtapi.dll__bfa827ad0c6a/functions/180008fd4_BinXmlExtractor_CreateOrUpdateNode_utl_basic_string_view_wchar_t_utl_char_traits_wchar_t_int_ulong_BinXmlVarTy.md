# BinXmlExtractor::CreateOrUpdateNode(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,int,ulong,BinXmlVarType,bool)

- ea: `0x180008fd4`
- end: `0x180009cf1`
- name: `?CreateOrUpdateNode@BinXmlExtractor@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@HKW4BinXmlVarType@@_N@Z`
- size: `3357`
- prototype: `__int64(_QWORD *, __int128 *, int, int, unsigned int, char, ...)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008bb8`
- `0x18001a0d8`
- `0x18001ae0c`
- `0x18001e1e0`

## callees

- `0x1800017cc`
- `0x180007180`
- `0x180008fd4`
- `0x18000a0d0`
- `0x18000a4b4`
- `0x180012f00`
- `0x1800139d0`
- `0x180019570`
- `0x18001fb4c`
- `0x18001ff14`
- `0x1800200d4`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
__int64 BinXmlExtractor::CreateOrUpdateNode(_QWORD *a1, __int128 *a2, int a3, int a4, unsigned int a5, char a6, ...)
{
  __int128 v6; // xmm0
  unsigned int v8; // r12d
  int v9; // eax
  char v10; // r13
  __int64 *i; // rdi
  __int64 result; // rax
  __int64 *v13; // rbx
  __int64 v14; // rsi
  _WORD *v15; // r14
  _QWORD *v16; // rax
  int v17; // r12d
  char v18; // bl
  int v19; // eax
  __int16 v20; // r14
  __m128i v21; // xmm6
  __int64 *v22; // rdi
  unsigned __int64 v23; // r10
  int v24; // r12d
  int v25; // edi
  _QWORD *v26; // rax
  __m128i *v27; // rdx
  char v28; // si
  void *v29; // rdi
  __m128i *v30; // rax
  unsigned __int64 v31; // xmm1_8
  int v32; // eax
  __m128i v33; // [rsp+28h] [rbp-69h] BYREF
  __m128i pExceptionObject; // [rsp+38h] [rbp-59h] BYREF
  unsigned __int64 v35; // [rsp+48h] [rbp-49h]
  int v36; // [rsp+50h] [rbp-41h]
  int v37; // [rsp+54h] [rbp-3Dh]
  int v38; // [rsp+58h] [rbp-39h]
  __int128 v39; // [rsp+68h] [rbp-29h] BYREF
  const wchar_t *v40; // [rsp+78h] [rbp-19h]
  __int64 v41; // [rsp+80h] [rbp-11h]
  __int64 v42; // [rsp+88h] [rbp-9h]
  char v43; // [rsp+90h] [rbp-1h]
  void *v44; // [rsp+F0h] [rbp+5Fh] BYREF
  int v45; // [rsp+F8h] [rbp+67h]
  int v46; // [rsp+100h] [rbp+6Fh]

  v46 = a4;
  v45 = a3;
  LODWORD(v44) = 0;
  v6 = *a2;
  v40 = L"/@[]=\"'";
  v41 = 7;
  v39 = v6;
  v8 = 0;
  v42 = 0;
  v43 = 1;
  v33 = 0u;
  v9 = StringTokenizer::NextToken(&v39, &v33);
  if ( !v9 )
  {
    if ( *(_WORD *)v33.m128i_i64[0] != 47 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
      }
      v35 = 0;
      v36 = 15001;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 127;
      throw (EvtException *)&pExceptionObject;
    }
    v9 = StringTokenizer::NextToken(&v39, &v33);
  }
  if ( v9 != 1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
    }
    v35 = 0;
    v36 = 15001;
    v37 = -1;
    pExceptionObject = 0;
    v38 = 135;
    throw (EvtException *)&pExceptionObject;
  }
  v10 = 1;
  for ( i = a1 + 9; ; i = v13 )
  {
    result = 64;
    if ( (*((_BYTE *)i + 52) & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 50);
      }
      v35 = 0;
      v36 = 50;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 159;
      throw (EvtException *)&pExceptionObject;
    }
    v13 = (__int64 *)*i;
    v14 = v33.m128i_i64[1];
    v15 = (_WORD *)v33.m128i_i64[0];
    if ( *i )
    {
      do
      {
        if ( v13[5] == v14 && !(unsigned int)utl::_Char16TraitsBase<wchar_t>::compare(v13[4], v15, v14) )
          break;
        v13 = (__int64 *)v13[3];
      }
      while ( v13 );
      if ( v13 )
        goto LABEL_22;
      result = 64;
    }
    if ( a6 )
      return result;
    v16 = MIDL_user_allocate(0x40u);
    if ( v16 )
    {
      *v16 = 0;
      v16[1] = 0;
      v16[2] = 0;
      v16[3] = 0;
      v16[4] = v15;
      v16[5] = v14;
      *((_DWORD *)v16 + 12) = -1;
      *(_QWORD *)((char *)v16 + 52) = 0;
      *((_BYTE *)v16 + 60) = 0;
      if ( v14 && *v15 == 42 )
        *((_BYTE *)v16 + 60) = 1;
    }
    else
    {
      v16 = 0;
    }
    v44 = v16;
    v17 = v8 | 1;
    if ( !(unsigned __int8)utl::vector<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>>>::emplace_back<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>,0>(
                             a1 + 3,
                             &v44)
      || (v18 = 0, !*(_QWORD *)(a1[4] - 8LL)) )
    {
      v18 = 1;
    }
    v8 = v17 & 0xFFFFFFFE;
    if ( v44 )
      operator delete(v44, 0x40u);
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 14);
      }
      v35 = 0;
      v36 = 14;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 190;
      throw (EvtException *)&pExceptionObject;
    }
    v10 = 0;
    v13 = *(__int64 **)(a1[4] - 8LL);
    v13[2] = (__int64)i;
    v13[3] = *i;
    *i = (__int64)v13;
LABEL_22:
    v19 = StringTokenizer::NextToken(&v39, &v33);
    if ( !v19 )
    {
      v20 = *(_WORD *)v33.m128i_i64[0];
      if ( *(_WORD *)v33.m128i_i64[0] != 91 && v20 != 47 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
        }
        v35 = 0;
        v36 = 15001;
        v37 = -1;
        pExceptionObject = 0;
        v38 = 219;
        throw (EvtException *)&pExceptionObject;
      }
      v19 = StringTokenizer::NextToken(&v39, &v33);
      if ( !v19 )
        break;
    }
    if ( v19 != 1 )
    {
      if ( v19 != 2 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
        }
        v35 = 0;
        v36 = 15001;
        v37 = -1;
        pExceptionObject = 0;
        v38 = 356;
        throw (EvtException *)&pExceptionObject;
      }
      if ( !a6 )
      {
        if ( v10 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 87);
          }
          v35 = 0;
          v36 = 87;
          v37 = -1;
          pExceptionObject = 0;
          v38 = 363;
          throw (EvtException *)&pExceptionObject;
        }
        v32 = v46;
        *((_DWORD *)v13 + 12) = v45;
        *((_DWORD *)v13 + 13) = v32;
      }
      result = a5;
      *((_DWORD *)v13 + 14) = a5;
      return result;
    }
  }
  if ( *(_WORD *)v33.m128i_i64[0] != 64 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
    }
    v35 = 0;
    v36 = 15001;
    v37 = -1;
    pExceptionObject = 0;
    v38 = 228;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (unsigned int)StringTokenizer::NextToken(&v39, &v33) != 1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
    }
    v35 = 0;
    v36 = 15001;
    v37 = -1;
    pExceptionObject = 0;
    v38 = 235;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (v46 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 87);
    }
    v35 = 0;
    v36 = 87;
    v37 = -1;
    pExceptionObject = 0;
    v38 = 240;
    throw (EvtException *)&pExceptionObject;
  }
  v21 = v33;
  pExceptionObject = v33;
  result = IsQName(&pExceptionObject);
  if ( !(_BYTE)result )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 87);
    }
    v35 = 0;
    v36 = 87;
    v37 = -1;
    pExceptionObject = 0;
    v38 = 245;
    throw (EvtException *)&pExceptionObject;
  }
  v22 = (__int64 *)v13[1];
  if ( !v22 )
    goto LABEL_52;
  v23 = _mm_srli_si128(v21, 8).m128i_u64[0];
  do
  {
    if ( v22[5] == v23 )
    {
      result = utl::_Char16TraitsBase<wchar_t>::compare(v22[4], v21.m128i_i64[0], v23);
      if ( !(_DWORD)result )
        break;
    }
    v22 = (__int64 *)*v22;
  }
  while ( v22 );
  if ( v22 )
  {
    v24 = v45;
  }
  else
  {
LABEL_52:
    if ( a6 )
      return result;
    v24 = v45;
    v25 = v45;
    if ( v20 == 91 )
      v25 = -1;
    v26 = MIDL_user_allocate(0x38u);
    if ( v26 )
    {
      *v26 = 0;
      utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(
        v26 + 1,
        v26);
      v27[2] = v21;
      v27[3].m128i_i32[0] = v25;
      v27[3].m128i_i32[1] = 0;
    }
    else
    {
      v27 = 0;
    }
    v44 = v27;
    if ( !(unsigned __int8)utl::vector<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>>>::emplace_back<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>,0>(
                             a1 + 6,
                             &v44)
      || (v28 = 0, !*(_QWORD *)(a1[7] - 8LL)) )
    {
      v28 = 1;
    }
    v29 = v44;
    if ( v44 )
    {
      utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit((char *)v44 + 8);
      operator delete(v29, 0x38u);
    }
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 14);
      }
      v35 = 0;
      v36 = 14;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 275;
      throw (EvtException *)&pExceptionObject;
    }
    v22 = *(__int64 **)(a1[7] - 8LL);
    *v22 = v13[1];
    v13[1] = (__int64)v22;
  }
  if ( v20 == 91 )
  {
    if ( (unsigned int)StringTokenizer::NextToken(&v39, &v33) || *(_WORD *)v33.m128i_i64[0] != 61 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
      }
      v35 = 0;
      v36 = 15001;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 291;
      throw (EvtException *)&pExceptionObject;
    }
    if ( (unsigned int)StringTokenizer::NextToken(&v39, &v33)
      || *(_WORD *)v33.m128i_i64[0] != 39 && *(_WORD *)v33.m128i_i64[0] != 34 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
      }
      v35 = 0;
      v36 = 15001;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 300;
      throw (EvtException *)&pExceptionObject;
    }
    if ( (unsigned int)StringTokenizer::NextToken(&v39, &v33) != 1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
      }
      v35 = 0;
      v36 = 15001;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 307;
      throw (EvtException *)&pExceptionObject;
    }
    pExceptionObject = v33;
    v30 = (__m128i *)v22[2];
    v35 = __PAIR64__(a5, v24);
    if ( v30 == (__m128i *)v22[3] )
    {
      if ( !(unsigned __int8)utl::vector<BinXmlExtractor::AttributeConstraint,utl::allocator<BinXmlExtractor::AttributeConstraint>>::_PushBackOne2<BinXmlExtractor::AttributeConstraint const &>(
                               v22 + 1,
                               &pExceptionObject) )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 14);
        }
        v35 = 0;
        v36 = 14;
        v37 = -1;
        pExceptionObject = 0;
        v38 = 317;
        throw (EvtException *)&pExceptionObject;
      }
    }
    else
    {
      v31 = v35;
      *v30 = pExceptionObject;
      v30[1].m128i_i64[0] = v31;
      v22[2] += 24;
    }
    if ( (unsigned int)StringTokenizer::NextToken(&v39, &v33)
      || *(_WORD *)v33.m128i_i64[0] != 39 && *(_WORD *)v33.m128i_i64[0] != 34 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
      }
      v35 = 0;
      v36 = 15001;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 326;
      throw (EvtException *)&pExceptionObject;
    }
    if ( (unsigned int)StringTokenizer::NextToken(&v39, &v33) || *(_WORD *)v33.m128i_i64[0] != 93 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
      }
      v35 = 0;
      v36 = 15001;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 334;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    *((_DWORD *)v22 + 13) = a5;
  }
  result = StringTokenizer::NextToken(&v39, &v33);
  if ( (_DWORD)result != 2 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 15001);
    }
    v35 = 0;
    v36 = 15001;
    v37 = -1;
    pExceptionObject = 0;
    v38 = 346;
    throw (EvtException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180008fd4  mov     rax, rsp
0x180008fd7  mov     [rax+8], rbx
0x180008fdb  mov     [rax+20h], r9d
0x180008fdf  mov     [rax+18h], r8d
0x180008fe3  push    rbp
0x180008fe4  push    rsi
0x180008fe5  push    rdi
0x180008fe6  push    r12
0x180008fe8  push    r13
0x180008fea  push    r14
0x180008fec  push    r15
0x180008fee  lea     rbp, [rax-4Fh]
0x180008ff2  sub     rsp, 0A0h
0x180008ff9  xor     esi, esi
0x180008ffb  movaps  xmmword ptr [rax-48h], xmm6
0x180008fff  mov     dword ptr [rbp+47h+arg_8], esi
0x180009002  lea     rax, asc_180040728; "/@[]=\"'"
0x180009009  movaps  xmm0, xmmword ptr [rdx]
0x18000900c  mov     r15, rcx
0x18000900f  lea     rdx, [rbp+47h+var_B0]
0x180009013  mov     [rbp+47h+var_60], rax
0x180009017  lea     rcx, [rbp+47h+var_70]
0x18000901b  mov     [rbp+47h+var_58], 7
0x180009023  movdqu  [rbp+47h+var_70], xmm0
0x180009028  mov     r12d, esi
0x18000902b  mov     [rbp+47h+var_50], rsi
0x18000902f  mov     [rbp+47h+var_48], 1
0x180009033  mov     qword ptr [rbp+47h+var_B0], rsi
0x180009037  mov     qword ptr [rbp+47h+var_B0+8], rsi
0x18000903b  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x180009040  test    eax, eax
0x180009042  jz      loc_180009683
0x180009048  cmp     eax, 1
0x18000904b  jnz     loc_180009709
0x180009051  mov     r13b, al
0x180009054  lea     rdi, [r15+48h]
0x180009058  test    byte ptr [rdi+34h], 1
0x18000905c  mov     eax, 40h ; '@'
0x180009061  jnz     loc_18000959C
0x180009067  mov     rbx, [rdi]
0x18000906a  mov     rsi, qword ptr [rbp+47h+var_B0+8]
0x18000906e  mov     r14, qword ptr [rbp+47h+var_B0]
0x180009072  test    rbx, rbx
0x180009075  jz      short loc_1800090A5
0x180009077  cmp     [rbx+28h], rsi
0x18000907b  jnz     short loc_180009090
0x18000907d  mov     rcx, [rbx+20h]
0x180009081  mov     r8, rsi
0x180009084  mov     rdx, r14
0x180009087  call    ?compare@?$_Char16TraitsBase@_W@utl@@SAHPEB_W0_K@Z; utl::_Char16TraitsBase<wchar_t>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x18000908c  test    eax, eax
0x18000908e  jz      short loc_180009099
0x180009090  mov     rbx, [rbx+18h]
0x180009094  test    rbx, rbx
0x180009097  jnz     short loc_180009077
0x180009099  test    rbx, rbx
0x18000909c  jnz     loc_1800093B0
0x1800090a2  lea     eax, [rbx+40h]
0x1800090a5  xor     r13d, r13d
0x1800090a8  cmp     [rbp+47h+arg_28], r13b
0x1800090ac  jnz     loc_1800092DE
0x1800090b2  mov     rcx, rax; size
0x1800090b5  call    MIDL_user_allocate
0x1800090ba  test    rax, rax
0x1800090bd  jz      loc_180009314
0x1800090c3  mov     [rax], r13
0x1800090c6  mov     [rax+8], r13
0x1800090ca  mov     [rax+10h], r13
0x1800090ce  mov     [rax+18h], r13
0x1800090d2  mov     [rax+20h], r14
0x1800090d6  mov     [rax+28h], rsi
0x1800090da  mov     dword ptr [rax+30h], 0FFFFFFFFh
0x1800090e1  mov     [rax+34h], r13
0x1800090e5  mov     [rax+3Ch], r13b
0x1800090e9  test    rsi, rsi
0x1800090ec  jz      short loc_1800090F9
0x1800090ee  cmp     word ptr [r14], 2Ah ; '*'
0x1800090f3  jnz     short loc_1800090F9
0x1800090f5  mov     byte ptr [rax+3Ch], 1
0x1800090f9  xor     esi, esi
0x1800090fb  lea     rdx, [rbp+47h+arg_8]
0x1800090ff  mov     [rbp+47h+arg_8], rax
0x180009103  lea     rcx, [r15+18h]
0x180009107  or      r12d, 1
0x18000910b  call    ??$emplace_back@V?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@utl@@$0A@@?$vector@V?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@1@@Z; utl::vector<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>>>::emplace_back<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>,0>(utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>> &&)
0x180009110  test    al, al
0x180009112  jnz     loc_1800092FE
0x180009118  mov     bl, 1
0x18000911a  mov     rcx, [rbp+47h+arg_8]; void *
0x18000911e  and     r12d, 0FFFFFFFEh
0x180009122  test    rcx, rcx
0x180009125  jz      short loc_180009131
0x180009127  mov     edx, 40h ; '@'; unsigned __int64
0x18000912c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009131  test    bl, bl
0x180009133  jnz     loc_180009C58
0x180009139  mov     rax, [r15+20h]
0x18000913d  mov     r13b, sil
0x180009140  mov     rbx, [rax-8]
0x180009144  mov     [rbx+10h], rdi
0x180009148  mov     rax, [rdi]
0x18000914b  mov     [rbx+18h], rax
0x18000914f  mov     [rdi], rbx
0x180009152  lea     rdx, [rbp+47h+var_B0]
0x180009156  lea     rcx, [rbp+47h+var_70]
0x18000915a  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x18000915f  test    eax, eax
0x180009161  jnz     loc_1800092BC
0x180009167  mov     rax, qword ptr [rbp+47h+var_B0]
0x18000916b  movzx   r14d, word ptr [rax]
0x18000916f  cmp     r14w, 5Bh ; '['
0x180009174  jnz     loc_1800093B7
0x18000917a  lea     rdx, [rbp+47h+var_B0]
0x18000917e  lea     rcx, [rbp+47h+var_70]
0x180009182  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x180009187  test    eax, eax
0x180009189  jnz     loc_1800092BC
0x18000918f  mov     rax, qword ptr [rbp+47h+var_B0]
0x180009193  mov     ecx, 40h ; '@'
0x180009198  cmp     [rax], cx
0x18000919b  jnz     loc_18000977B
0x1800091a1  lea     rdx, [rbp+47h+var_B0]
0x1800091a5  lea     rcx, [rbp+47h+var_70]
0x1800091a9  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x1800091ae  cmp     eax, 1
0x1800091b1  jnz     loc_1800097E9
0x1800091b7  mov     eax, [rbp+47h+arg_18]
0x1800091ba  test    al, 1
0x1800091bc  jnz     loc_180009857
0x1800091c2  movaps  xmm6, [rbp+47h+var_B0]
0x1800091c6  lea     rcx, [rbp+47h+pExceptionObject]
0x1800091ca  movdqa  [rbp+47h+pExceptionObject], xmm6
0x1800091cf  call    IsQName
0x1800091d4  test    al, al
0x1800091d6  jz      loc_1800098C3
0x1800091dc  mov     rdi, [rbx+8]
0x1800091e0  test    rdi, rdi
0x1800091e3  jz      loc_18000931D
0x1800091e9  movdqa  xmm0, xmm6
0x1800091ed  psrldq  xmm0, 8
0x1800091f2  movq    r10, xmm0
0x1800091f7  cmp     [rdi+28h], r10
0x1800091fb  jnz     short loc_180009212
0x1800091fd  mov     rcx, [rdi+20h]
0x180009201  mov     r8, r10
0x180009204  movq    rdx, xmm6
0x180009209  call    ?compare@?$_Char16TraitsBase@_W@utl@@SAHPEB_W0_K@Z; utl::_Char16TraitsBase<wchar_t>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x18000920e  test    eax, eax
0x180009210  jz      short loc_18000921A
0x180009212  mov     rdi, [rdi]
0x180009215  test    rdi, rdi
0x180009218  jnz     short loc_1800091F7
0x18000921a  test    rdi, rdi
0x18000921d  jz      loc_18000931D
0x180009223  mov     r12d, [rbp+47h+arg_10]
0x180009227  cmp     r14w, 5Bh ; '['
0x18000922c  jz      loc_180009430
0x180009232  mov     eax, [rbp+47h+arg_20]
0x180009235  mov     [rdi+34h], eax
0x180009238  lea     rdx, [rbp+47h+var_B0]
0x18000923c  lea     rcx, [rbp+47h+var_70]
0x180009240  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x180009245  cmp     eax, 2
0x180009248  jz      loc_1800092DE
0x18000924e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009255  lea     rax, WPP_GLOBAL_Control
0x18000925c  mov     ebx, 3A99h
0x180009261  cmp     rcx, rax
0x180009264  jz      short loc_18000928A
0x180009266  test    byte ptr [rcx+1Ch], 2
0x18000926a  jz      short loc_18000928A
0x18000926c  cmp     byte ptr [rcx+19h], 2
0x180009270  jb      short loc_18000928A
0x180009272  mov     rcx, [rcx+10h]
0x180009276  lea     r8, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids
0x18000927d  mov     edx, 1Ch
0x180009282  mov     r9d, ebx
0x180009285  call    WPP_SF_D
0x18000928a  xorps   xmm0, xmm0
0x18000928d  mov     [rbp+47h+var_90], 0
0x180009295  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000929c  mov     [rbp+47h+var_88], ebx
0x18000929f  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x1800092a3  mov     [rbp+47h+var_84], 0FFFFFFFFh
0x1800092aa  movdqu  [rbp+47h+pExceptionObject], xmm0
0x1800092af  mov     [rbp+47h+var_80], 15Ah
0x1800092b6  call    _CxxThrowException_0
0x1800092bc  cmp     eax, 1
0x1800092bf  jz      loc_180009773
0x1800092c5  cmp     eax, 2
0x1800092c8  jnz     loc_180009B7E
0x1800092ce  cmp     [rbp+47h+arg_28], sil
0x1800092d2  jz      loc_1800095EA
0x1800092d8  mov     eax, [rbp+47h+arg_20]
0x1800092db  mov     [rbx+38h], eax
0x1800092de  lea     r11, [rsp+0D0h+var_30]
0x1800092e6  mov     rbx, [r11+40h]
0x1800092ea  movaps  xmm6, xmmword ptr [r11-10h]
0x1800092ef  mov     rsp, r11
0x1800092f2  pop     r15
0x1800092f4  pop     r14
0x1800092f6  pop     r13
0x1800092f8  pop     r12
0x1800092fa  pop     rdi
0x1800092fb  pop     rsi
0x1800092fc  pop     rbp
0x1800092fd  retn
0x1800092fe  mov     rax, [r15+20h]
0x180009302  mov     bl, sil
0x180009305  cmp     [rax-8], rsi
0x180009309  jnz     loc_18000911A
0x18000930f  jmp     loc_180009118
0x180009314  xor     esi, esi
0x180009316  mov     eax, esi
0x180009318  jmp     loc_1800090FB
0x18000931d  cmp     [rbp+47h+arg_28], sil
0x180009321  jnz     short loc_1800092DE
0x180009323  mov     r12d, [rbp+47h+arg_10]
0x180009327  mov     eax, 0FFFFFFFFh
0x18000932c  cmp     r14w, 5Bh ; '['
0x180009331  mov     edi, r12d
0x180009334  cmovz   edi, eax
0x180009337  lea     ecx, [rax+39h]; size
0x18000933a  call    MIDL_user_allocate
0x18000933f  xor     r13d, r13d
0x180009342  mov     rdx, rax
0x180009345  test    rax, rax
0x180009348  jz      loc_180009594
0x18000934e  lea     rcx, [rax+8]
0x180009352  mov     [rax], r13
0x180009355  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18000935a  movdqu  xmmword ptr [rdx+20h], xmm6
0x18000935f  mov     [rdx+30h], edi
0x180009362  mov     [rdx+34h], r13d
0x180009366  mov     [rbp+47h+arg_8], rdx
0x18000936a  lea     rcx, [r15+30h]
0x18000936e  lea     rdx, [rbp+47h+arg_8]
0x180009372  call    ??$emplace_back@V?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@utl@@$0A@@?$vector@V?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@1@@Z; utl::vector<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>>>::emplace_back<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>,0>(utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>> &&)
0x180009377  test    al, al
0x180009379  jnz     loc_18000957E
0x18000937f  mov     sil, 1
0x180009382  mov     rdi, [rbp+47h+arg_8]
0x180009386  test    rdi, rdi
0x180009389  jnz     loc_18000992F
0x18000938f  test    sil, sil
0x180009392  jnz     loc_18000994A
0x180009398  mov     rax, [r15+38h]
0x18000939c  mov     rdi, [rax-8]
0x1800093a0  mov     rax, [rbx+8]
0x1800093a4  mov     [rdi], rax
0x1800093a7  mov     [rbx+8], rdi
0x1800093ab  jmp     loc_180009227
0x1800093b0  xor     esi, esi
0x1800093b2  jmp     loc_180009152
0x1800093b7  cmp     r14w, 2Fh ; '/'
0x1800093bc  jz      loc_18000917A
0x1800093c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093c9  lea     rax, WPP_GLOBAL_Control
0x1800093d0  mov     ebx, 3A99h
0x1800093d5  cmp     rcx, rax
0x1800093d8  jz      short loc_1800093FE
0x1800093da  test    byte ptr [rcx+1Ch], 2
0x1800093de  jz      short loc_1800093FE
0x1800093e0  cmp     byte ptr [rcx+19h], 2
0x1800093e4  jb      short loc_1800093FE
0x1800093e6  mov     rcx, [rcx+10h]
0x1800093ea  lea     r8, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids
0x1800093f1  mov     edx, 10h
0x1800093f6  mov     r9d, ebx
0x1800093f9  call    WPP_SF_D
0x1800093fe  xorps   xmm0, xmm0
0x180009401  mov     [rbp+47h+var_90], 0
0x180009409  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180009410  mov     [rbp+47h+var_88], ebx
0x180009413  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180009417  mov     [rbp+47h+var_84], 0FFFFFFFFh
0x18000941e  movdqu  [rbp+47h+pExceptionObject], xmm0
0x180009423  mov     [rbp+47h+var_80], 0DBh
0x18000942a  call    _CxxThrowException_0
0x180009430  lea     rdx, [rbp+47h+var_B0]
0x180009434  lea     rcx, [rbp+47h+var_70]
0x180009438  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x18000943d  test    eax, eax
0x18000943f  jnz     loc_180009B10
0x180009445  mov     rax, qword ptr [rbp+47h+var_B0]
0x180009449  cmp     word ptr [rax], 3Dh ; '='
0x18000944d  jnz     loc_180009B10
0x180009453  lea     rdx, [rbp+47h+var_B0]
0x180009457  lea     rcx, [rbp+47h+var_70]
0x18000945b  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x180009460  test    eax, eax
0x180009462  jnz     loc_1800099BC
0x180009468  mov     rax, qword ptr [rbp+47h+var_B0]
0x18000946c  cmp     word ptr [rax], 27h ; '''
0x180009470  jnz     loc_1800099B2
0x180009476  lea     rdx, [rbp+47h+var_B0]
0x18000947a  lea     rcx, [rbp+47h+var_70]
0x18000947e  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; StringTokenizer::NextToken(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x180009483  cmp     eax, 1
0x180009486  jnz     loc_180009A2A
  ... truncated ...
```
