# TaskXmlReader::ProcessAttributes(ITaskXmlHandler *,TaskXmlNodeId,bool &)

- ea: `0x180019b50`
- end: `0x18001a44c`
- name: `?ProcessAttributes@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@AEA_N@Z`
- size: `2300`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019730`

## callees

- `0x180009150`
- `0x1800145c0`
- `0x180014700`
- `0x180016930`
- `0x1800170a0`
- `0x180019b50`
- `0x18001aec0`
- `0x18001af18`
- `0x18003b514`
- `0x18003b74c`
- `0x18003c85c`
- `0x18004f508`
- `0x180052617`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001a29b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a2c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a29b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a2c5`

## string_xrefs

- `0x180019cf3`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskXmlReader::ProcessAttributes(__int64 a1, struct IErrorInfo *a2, int a3, _BYTE *a4)
{
  __int64 v4; // rdi
  unsigned int v6; // r12d
  __int64 v7; // rcx
  int v8; // eax
  struct IErrorInfo *v9; // rdx
  unsigned int v10; // r9d
  __int64 v11; // r11
  int v12; // r8d
  const struct SchemaEntry **v13; // rdx
  int v14; // ebx
  __int64 v15; // r10
  __int64 *v16; // rax
  __int64 result; // rax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64, __int64); // rbp
  BSTR *v20; // r15
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // edx
  int j; // r14d
  int v26; // edx
  int v27; // eax
  __int64 *v28; // rdx
  __int64 v29; // rbx
  int v30; // edx
  const struct SchemaEntry **v31; // r8
  int v32; // ebp
  struct XmlParserTempString *v33; // r8
  int v34; // edx
  __int64 *v35; // rdx
  size_t v36; // r8
  OLECHAR *v37; // rbp
  struct IErrorInfo *v38; // rdx
  const unsigned __int64 *v39; // r10
  unsigned __int64 v40; // rdx
  __int64 v41; // rax
  const unsigned __int64 near *v42; // r8
  __int64 v43; // rbx
  __int64 v44; // r14
  __int64 (__fastcall *v45)(__int64, _QWORD *, __int64); // r15
  _QWORD *v46; // rdx
  int v47; // eax
  int v48; // edx
  __int64 *v49; // rdx
  __int64 v50; // rcx
  unsigned int v51; // r12d
  __int64 i; // rcx
  const unsigned __int64 *v53; // r9
  unsigned __int64 v54; // r8
  const unsigned __int64 near *v55; // r9
  __int64 v56; // r10
  unsigned __int64 v57; // r8
  const unsigned __int64 near *v58; // r9
  __int64 v59; // r10
  unsigned __int64 v60; // r8
  const unsigned __int64 near *v61; // r9
  __int64 v62; // r10
  __int64 v63; // r9
  int Value; // ebp
  __int64 v65; // rdx
  int started; // eax
  unsigned int v67; // ecx
  _QWORD *v68; // [rsp+30h] [rbp-E8h] BYREF
  unsigned int v69; // [rsp+38h] [rbp-E0h]
  __int64 v70; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE *v71; // [rsp+48h] [rbp-D0h]
  struct IErrorInfo *v72; // [rsp+50h] [rbp-C8h]
  _DWORD v73[24]; // [rsp+60h] [rbp-B8h]

  v71 = a4;
  v4 = a3;
  v72 = a2;
  v6 = 0;
  v70 = 0;
  while ( 2 )
  {
    v69 = v6;
    while ( 1 )
    {
      v7 = *(_QWORD *)(a1 + 56);
      if ( !v7 )
        _com_raise_error(-2147467261, a2);
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 72LL))(v7);
      if ( v8 )
      {
        if ( v8 >= 0 )
        {
          v10 = 0;
          v11 = a1 + 1116;
          while ( 1 )
          {
            if ( v10 >= 0x16 )
              goto LABEL_151;
            v11 = a1 + 1116;
            v12 = *(_DWORD *)(a1 + 1116);
            if ( v12 == 65542 )
            {
LABEL_9:
              v13 = &(&Schema::schemaEntries)[(unsigned __int16)v12][16 * v4];
              v14 = v12 - 0x10000;
            }
            else
            {
              v14 = v12 - 0x10000;
              switch ( v12 )
              {
                case 65536:
                case 65537:
                  v39 = 0;
                  break;
                case 65538:
                case 65539:
                case 65540:
                case 65541:
                  goto LABEL_9;
                default:
                  goto LABEL_108;
              }
              while ( v39 < (&Schema::schemaEntriesCount)[(unsigned __int16)v12] )
              {
                v13 = &(&Schema::schemaEntries)[(unsigned __int16)v12][16 * (_QWORD)v39];
                if ( *(_DWORD *)v13 == (_DWORD)v4 )
                  goto LABEL_10;
                v39 = (const unsigned __int64 *)((char *)v39 + 1);
              }
LABEL_108:
              v13 = (const struct SchemaEntry **)&qword_180072DF0;
            }
LABEL_10:
            v15 = *((int *)v13 + (int)v10 + 10);
            if ( !(_DWORD)v15 )
              goto LABEL_151;
            if ( v12 == 65542 )
            {
LABEL_12:
              v16 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v12][16 * v15];
            }
            else
            {
              switch ( v14 )
              {
                case 0:
                case 1:
                  v40 = 0;
                  v41 = (unsigned __int16)v12;
                  v42 = (&Schema::schemaEntriesCount)[(unsigned __int16)v12];
                  v43 = 8 * v41 + 384824;
                  break;
                case 2:
                case 3:
                case 4:
                case 5:
                  goto LABEL_12;
                default:
                  goto LABEL_109;
              }
              while ( v40 < (unsigned __int64)v42 )
              {
                v16 = (__int64 *)((v40 << 7) + *(_QWORD *)((char *)&_ImageBase + v43));
                if ( *(_DWORD *)v16 == (_DWORD)v15 )
                  goto LABEL_13;
                ++v40;
              }
LABEL_109:
              v16 = &qword_180072DF0;
            }
LABEL_13:
            if ( *((_DWORD *)v16 + 6) != 2 )
            {
LABEL_151:
              if ( !*(_BYTE *)(a1 + 40)
                || (_DWORD)v4 == 1
                || v6
                || *(_DWORD *)(Schema::GetEntry(v11, (unsigned int)v4) + 28) )
              {
                return 0;
              }
              started = TaskXmlWriter::StartElement(*(_QWORD *)(a1 + 16), v65);
              v67 = 0;
              if ( started < 0 )
                return (unsigned int)started;
              return v67;
            }
            if ( *((_DWORD *)v16 + 8) )
              break;
LABEL_18:
            ++v10;
          }
          for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
          {
            if ( v73[i] == (_DWORD)v15 )
              goto LABEL_18;
          }
          return TaskXmlReader::SetErrorInfo(a1, 2147750681LL, (unsigned int)v15);
        }
        return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v8);
      }
      v18 = *(_QWORD *)(a1 + 56);
      if ( !v18 )
        _com_raise_error(-2147467261, v9);
      v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 112LL);
      v20 = (BSTR *)(a1 + 72);
      v68 = (_QWORD *)(a1 + 72);
      if ( (*(_BYTE *)(a1 + 1106) & 1) != 0 )
        SysFreeString(*v20);
      else
        v68 = (_QWORD *)(a1 + 72);
      *(_DWORD *)(a1 + 64) = 0;
      *v20 = 0;
      *(_BYTE *)(a1 + 1106) &= 0xFCu;
      *(_WORD *)(a1 + 80) = 0;
      v8 = v19(v18, a1 + 72, a1 + 64);
      if ( v8 < 0 )
        return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v8);
      v21 = *(_DWORD *)(a1 + 64);
      if ( v21 && (v21 != 5 || wcsncmp_0(*(const wchar_t **)(a1 + 72), L"xmlns", 5u)) )
      {
        v22 = *(_QWORD *)(a1 + 56);
        if ( !v22 )
          _com_raise_error(-2147467261, a2);
        v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v22 + 120LL))(v22, &v70, 0);
        if ( v8 < 0 )
          return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v8);
        if ( !v70 )
          break;
        v23 = 0;
        do
        {
          v24 = *(unsigned __int16 *)(v70 + 2 * v23++);
          a2 = (struct IErrorInfo *)(v24 - (unsigned int)aXmlns[v23 - 1]);
        }
        while ( !(_DWORD)a2 && v23 != 6 );
        if ( (_DWORD)a2 )
          break;
      }
    }
    for ( j = 0; ; ++j )
    {
      if ( (unsigned __int64)j >= 0x16 || !(_DWORD)v4 )
      {
LABEL_47:
        v33 = (struct XmlParserTempString *)(a1 + 64);
        v34 = -2147216618;
        return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, v34, v33);
      }
      v26 = *(_DWORD *)(a1 + 1116);
      if ( v26 == 65538 )
        goto LABEL_39;
      if ( v26 != 65542 )
      {
        if ( v26 != 0x10000 && v26 != 65537 )
        {
          switch ( v26 )
          {
            case 65539:
              v27 = 136;
              break;
            case 65540:
              v27 = 145;
              break;
            case 65541:
              v27 = 148;
              break;
            default:
              v27 = 0;
              break;
          }
          goto LABEL_40;
        }
LABEL_39:
        v27 = 131;
        goto LABEL_40;
      }
      v27 = 149;
LABEL_40:
      if ( (int)v4 >= v27 )
        goto LABEL_47;
      if ( v26 == 65542 )
      {
LABEL_42:
        v28 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v26][16 * v4];
      }
      else
      {
        switch ( v26 )
        {
          case 65536:
          case 65537:
            v54 = 0;
            v55 = (&Schema::schemaEntriesCount)[(unsigned __int16)v26];
            v56 = 8LL * (unsigned __int16)v26 + 384824;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_42;
          default:
            goto LABEL_110;
        }
        while ( v54 < (unsigned __int64)v55 )
        {
          v28 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v56) + (v54 << 7));
          if ( *(_DWORD *)v28 == (_DWORD)v4 )
            goto LABEL_43;
          ++v54;
        }
LABEL_110:
        v28 = &qword_180072DF0;
      }
LABEL_43:
      v29 = *((int *)v28 + j + 10);
      if ( !(_DWORD)v29 )
        goto LABEL_47;
      v30 = *(_DWORD *)(a1 + 1116);
      if ( v30 == 65542 )
      {
LABEL_45:
        v31 = &(&Schema::schemaEntries)[(unsigned __int16)v30][16 * v29];
        v32 = v30 - 0x10000;
      }
      else
      {
        v32 = v30 - 0x10000;
        switch ( v30 )
        {
          case 65536:
          case 65537:
            v53 = 0;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_45;
          default:
            goto LABEL_101;
        }
        while ( v53 < (&Schema::schemaEntriesCount)[(unsigned __int16)v30] )
        {
          v31 = &(&Schema::schemaEntries)[(unsigned __int16)v30][16 * (_QWORD)v53];
          if ( *(_DWORD *)v31 == (_DWORD)v29 )
            goto LABEL_46;
          v53 = (const unsigned __int64 *)((char *)v53 + 1);
        }
LABEL_101:
        v31 = (const struct SchemaEntry **)&qword_180072DF0;
      }
LABEL_46:
      if ( *((_DWORD *)v31 + 6) != 2 )
        goto LABEL_47;
      if ( v30 == 65542 )
      {
LABEL_50:
        v35 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v30][16 * v29];
      }
      else
      {
        switch ( v32 )
        {
          case 0:
          case 1:
            v57 = 0;
            v58 = (&Schema::schemaEntriesCount)[(unsigned __int16)v30];
            v59 = 8LL * (unsigned __int16)v30 + 384824;
            break;
          case 2:
          case 3:
          case 4:
          case 5:
            goto LABEL_50;
          default:
            goto LABEL_111;
        }
        while ( v57 < (unsigned __int64)v58 )
        {
          v35 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v59) + (v57 << 7));
          if ( *(_DWORD *)v35 == (_DWORD)v29 )
            goto LABEL_51;
          ++v57;
        }
LABEL_111:
        v35 = &qword_180072DF0;
      }
LABEL_51:
      v36 = *((unsigned int *)v35 + 4);
      if ( *(_DWORD *)(a1 + 64) == (_DWORD)v36 )
      {
        v37 = *v20;
        if ( !wcsncmp_0(*v20, (const wchar_t *)v35[1], v36) )
          break;
      }
    }
    v44 = *(_QWORD *)(a1 + 56);
    if ( !v44 )
      _com_raise_error(-2147467261, v38);
    v45 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v44 + 104LL);
    if ( (*(_BYTE *)(a1 + 1106) & 1) != 0 )
      SysFreeString(v37);
    *(_DWORD *)(a1 + 64) = 0;
    v46 = v68;
    *v68 = 0;
    *(_BYTE *)(a1 + 1106) &= 0xFCu;
    *(_WORD *)(a1 + 80) = 0;
    v47 = v45(v44, v46, a1 + 64);
    if ( v47 < 0 )
    {
      result = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v47);
LABEL_89:
      if ( (int)result >= 0 )
        goto LABEL_79;
      return result;
    }
    v48 = *(_DWORD *)(a1 + 1116);
    if ( v48 == 65542 )
    {
LABEL_75:
      v49 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v48][16 * v29];
    }
    else
    {
      switch ( v48 )
      {
        case 65536:
        case 65537:
          v60 = 0;
          v61 = (&Schema::schemaEntriesCount)[(unsigned __int16)v48];
          v62 = 8LL * (unsigned __int16)v48 + 384824;
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_75;
        default:
          goto LABEL_119;
      }
      while ( v60 < (unsigned __int64)v61 )
      {
        v49 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v62) + (v60 << 7));
        if ( *(_DWORD *)v49 == (_DWORD)v29 )
          goto LABEL_76;
        ++v60;
      }
LABEL_119:
      v49 = &qword_180072DF0;
    }
LABEL_76:
    if ( (*((_DWORD *)v49 + 6) != 2 || *(_DWORD *)(a1 + 64))
      && (*(_DWORD *)(a1 + 64) != 53 || wcsncmp_0(*(const wchar_t **)(a1 + 72), Schema::namespaceUri, 0x35u)) )
    {
      result = TaskXmlReader::SetErrorInfo(a1, 2147750679LL, (unsigned int)v29, a1 + 64);
      goto LABEL_89;
    }
LABEL_79:
    if ( !*(_BYTE *)(a1 + 40) || (_DWORD)v4 == 1 )
    {
LABEL_80:
      result = TaskXmlReader::ProcessSimpleContent(a1, (__int64)v72, v29, 0, v71);
      if ( (int)result < 0 )
        return result;
      v50 = 0;
      v51 = v69;
      while ( (unsigned int)v50 < v69 )
      {
        if ( v73[v50] == (_DWORD)v29 )
          goto LABEL_137;
        v50 = (unsigned int)(v50 + 1);
      }
      if ( v69 < 0x16 )
      {
        v73[v69] = v29;
        v6 = v51 + 1;
        continue;
      }
LABEL_137:
      v33 = (struct XmlParserTempString *)(a1 + 64);
      v34 = -2147216611;
      return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, v34, v33);
    }
    break;
  }
  v68 = 0;
  Value = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (struct _bstr_t *)&v68);
  if ( Value >= 0 )
  {
    v63 = v68 ? *v68 : 0LL;
    Value = TaskXmlWriter::StartElementWithAttribute(*(_QWORD *)(a1 + 16), (unsigned int)v4, (unsigned int)v29, v63);
    if ( Value >= 0 )
    {
      _bstr_t::_Free((_bstr_t *)&v68);
      goto LABEL_80;
    }
  }
  _bstr_t::_Free((_bstr_t *)&v68);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180019b50  push    rbx
0x180019b52  push    rbp
0x180019b53  push    rsi
0x180019b54  push    rdi
0x180019b55  push    r12
0x180019b57  push    r13
0x180019b59  push    r14
0x180019b5b  push    r15
0x180019b5d  sub     rsp, 0D8h
0x180019b64  mov     rax, cs:__security_cookie
0x180019b6b  xor     rax, rsp
0x180019b6e  mov     [rsp+118h+var_58], rax
0x180019b76  mov     [rsp+118h+var_D0], r9
0x180019b7b  movsxd  rdi, r8d
0x180019b7e  mov     [rsp+118h+var_C8], rdx
0x180019b83  mov     rsi, rcx
0x180019b86  xor     r12d, r12d
0x180019b89  mov     [rsp+118h+var_D8], r12
0x180019b8e  lea     r14, __ImageBase
0x180019b95  mov     [rsp+118h+var_E0], r12d
0x180019b9a  mov     rcx, [rsi+38h]
0x180019b9e  test    rcx, rcx
0x180019ba1  jz      loc_18001A3AE
0x180019ba7  mov     rax, [rcx]
0x180019baa  mov     rax, [rax+48h]
0x180019bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bb3  test    eax, eax
0x180019bb5  jz      loc_180019C84
0x180019bbb  js      loc_18001A357
0x180019bc1  xor     r9d, r9d
0x180019bc4  lea     r11, [rsi+45Ch]
0x180019bcb  nop     dword ptr [rax+rax+00h]
0x180019bd0  cmp     r9d, 16h
0x180019bd4  jnb     short loc_180019C41
0x180019bd6  lea     r11, [rsi+45Ch]
0x180019bdd  mov     r8d, [r11]
0x180019be0  cmp     r8d, 10006h
0x180019be7  jnz     loc_180019EA6
0x180019bed  movzx   eax, r8w; jumptable 0000000180019EC4 cases 65538-65541
0x180019bf1  mov     rdx, rdi
0x180019bf4  shl     rdx, 7
0x180019bf8  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019c00  lea     ebx, [r8-10000h]
0x180019c07  movsxd  rax, r9d
0x180019c0a  movsxd  r10, dword ptr [rdx+rax*4+28h]
0x180019c0f  test    r10d, r10d
0x180019c12  jz      short loc_180019C41
0x180019c14  lea     r14, __ImageBase
0x180019c1b  cmp     r8d, 10006h
0x180019c22  jnz     loc_180019F04
0x180019c28  movzx   ecx, r8w; jumptable 0000000180019F1B cases 2-5
0x180019c2c  mov     rax, r10
0x180019c2f  shl     rax, 7
0x180019c33  add     rax, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019c3b  cmp     dword ptr [rax+18h], 2
0x180019c3f  jz      short loc_180019C72
0x180019c41  cmp     byte ptr [rsi+28h], 0
0x180019c45  jnz     loc_18001A371
0x180019c4b  xor     eax, eax
0x180019c4d  mov     rcx, [rsp+118h+var_58]
0x180019c55  xor     rcx, rsp; StackCookie
0x180019c58  call    __security_check_cookie
0x180019c5d  add     rsp, 0D8h
0x180019c64  pop     r15
0x180019c66  pop     r14
0x180019c68  pop     r13
0x180019c6a  pop     r12
0x180019c6c  pop     rdi
0x180019c6d  pop     rsi
0x180019c6e  pop     rbp
0x180019c6f  pop     rbx
0x180019c70  retn
0x180019c72  cmp     dword ptr [rax+20h], 0
0x180019c76  jnz     loc_18001A063
0x180019c7c  inc     r9d
0x180019c7f  jmp     loc_180019BD0
0x180019c84  mov     rbx, [rsi+38h]
0x180019c88  test    rbx, rbx
0x180019c8b  jz      loc_18001A366
0x180019c91  mov     rax, [rbx]
0x180019c94  mov     rbp, [rax+70h]
0x180019c98  lea     r15, [rsi+48h]
0x180019c9c  mov     [rsp+118h+var_E8], r15
0x180019ca1  test    byte ptr [rsi+452h], 1
0x180019ca8  jnz     loc_18001A298
0x180019cae  mov     [rsp+118h+var_E8], r15
0x180019cb3  mov     dword ptr [rsi+40h], 0
0x180019cba  mov     qword ptr [r15], 0
0x180019cc1  and     byte ptr [rsi+452h], 0FCh
0x180019cc8  xor     ecx, ecx
0x180019cca  mov     [rsi+50h], cx
0x180019cce  lea     r8, [rsi+40h]
0x180019cd2  mov     rdx, r15
0x180019cd5  mov     rcx, rbx
0x180019cd8  mov     rax, rbp
0x180019cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ce0  test    eax, eax
0x180019ce2  js      loc_18001A357
0x180019ce8  mov     eax, [rsi+40h]
0x180019ceb  test    eax, eax
0x180019ced  jz      loc_180019B9A
0x180019cf3  lea     rbx, aXmlns; "xmlns"
0x180019cfa  cmp     eax, 5
0x180019cfd  jnz     short loc_180019D16
0x180019cff  mov     r8d, eax; MaxCount
0x180019d02  mov     rdx, rbx; String2
0x180019d05  mov     rcx, [rsi+48h]; String1
0x180019d09  call    wcsncmp_0
0x180019d0e  test    eax, eax
0x180019d10  jz      loc_180019B9A
0x180019d16  mov     rcx, [rsi+38h]
0x180019d1a  test    rcx, rcx
0x180019d1d  jz      loc_18001A34C
0x180019d23  mov     rax, [rcx]
0x180019d26  xor     r8d, r8d
0x180019d29  lea     rdx, [rsp+118h+var_D8]
0x180019d2e  mov     rax, [rax+78h]
0x180019d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d37  test    eax, eax
0x180019d39  js      loc_18001A357
0x180019d3f  mov     r8, [rsp+118h+var_D8]
0x180019d44  test    r8, r8
0x180019d47  jz      short loc_180019D6F
0x180019d49  xor     ecx, ecx
0x180019d4b  nop     dword ptr [rax+rax+00h]
0x180019d50  movzx   edx, word ptr [r8+rcx*2]
0x180019d55  inc     rcx
0x180019d58  movzx   eax, word ptr [rbx+rcx*2-2]
0x180019d5d  sub     edx, eax
0x180019d5f  jnz     short loc_180019D67
0x180019d61  cmp     rcx, 6
0x180019d65  jnz     short loc_180019D50
0x180019d67  test    edx, edx
0x180019d69  jz      loc_180019B9A
0x180019d6f  xor     r14d, r14d
0x180019d72  movsxd  rbx, r14d
0x180019d75  cmp     rbx, 16h
0x180019d79  jnb     loc_180019E10
0x180019d7f  test    edi, edi
0x180019d81  jz      loc_180019E10
0x180019d87  mov     edx, [rsi+45Ch]
0x180019d8d  cmp     edx, 10002h
0x180019d93  jz      short loc_180019DA8
0x180019d95  cmp     edx, 10006h
0x180019d9b  jnz     loc_180019E6D
0x180019da1  mov     eax, 95h
0x180019da6  jmp     short loc_180019DAD
0x180019da8  mov     eax, 83h
0x180019dad  cmp     edi, eax
0x180019daf  jge     short loc_180019E10
0x180019db1  lea     r11, __ImageBase
0x180019db8  cmp     edx, 10006h
0x180019dbe  jnz     loc_18001A0F9
0x180019dc4  movzx   eax, dx; jumptable 000000018001A115 cases 65538-65541
0x180019dc7  mov     rdx, rdi
0x180019dca  shl     rdx, 7
0x180019dce  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019dd6  movsxd  rbx, dword ptr [rdx+rbx*4+28h]
0x180019ddb  test    ebx, ebx
0x180019ddd  jz      short loc_180019E10
0x180019ddf  mov     edx, [rsi+45Ch]
0x180019de5  cmp     edx, 10006h
0x180019deb  jnz     loc_18001A0A4
0x180019df1  movzx   eax, dx; jumptable 000000018001A0C1 cases 65538-65541
0x180019df4  mov     r8, rbx
0x180019df7  shl     r8, 7
0x180019dfb  add     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019e03  lea     ebp, [rdx-10000h]
0x180019e09  cmp     dword ptr [r8+18h], 2
0x180019e0e  jz      short loc_180019E26
0x180019e10  lea     r8, [rsi+40h]; struct XmlParserTempString *
0x180019e14  mov     edx, 80041316h; int
0x180019e19  mov     rcx, rsi; this
0x180019e1c  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJAEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,XmlParserTempString &)
0x180019e21  jmp     loc_180019C4D
0x180019e26  cmp     edx, 10006h
0x180019e2c  jnz     loc_18001A165
0x180019e32  movzx   eax, dx; jumptable 000000018001A178 cases 2-5
0x180019e35  mov     rdx, rbx
0x180019e38  shl     rdx, 7
0x180019e3c  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019e44  mov     r8d, [rdx+10h]; MaxCount
0x180019e48  cmp     [rsi+40h], r8d
0x180019e4c  jnz     short loc_180019E65
0x180019e4e  mov     rbp, [r15]
0x180019e51  mov     rdx, [rdx+8]; String2
0x180019e55  mov     rcx, rbp; String1
0x180019e58  call    wcsncmp_0
0x180019e5d  test    eax, eax
0x180019e5f  jz      loc_180019F5C
0x180019e65  inc     r14d
0x180019e68  jmp     loc_180019D72
0x180019e6d  mov     ecx, edx
0x180019e6f  sub     ecx, 10000h
0x180019e75  jz      loc_180019DA8
0x180019e7b  sub     ecx, 1
0x180019e7e  jz      loc_180019DA8
0x180019e84  sub     ecx, 2
0x180019e87  jz      short loc_180019E9C
0x180019e89  sub     ecx, 1
0x180019e8c  jnz     loc_18001A2AC
0x180019e92  mov     eax, 91h
0x180019e97  jmp     loc_180019DAD
0x180019e9c  mov     eax, 88h
0x180019ea1  jmp     loc_180019DAD
0x180019ea6  lea     ebx, [r8-10000h]; switch 6 cases
0x180019ead  cmp     ebx, 5
0x180019eb0  ja      def_180019EC4; jumptable 0000000180019EC4 default case
0x180019eb6  movsxd  rax, ebx
0x180019eb9  mov     ecx, ds:(jpt_180019EC4 - 180000000h)[r14+rax*4]
0x180019ec1  add     rcx, r14
0x180019ec4  jmp     rcx; switch jump
0x180019eca  xor     r10d, r10d; jumptable 0000000180019EC4 cases 65536,65537
0x180019ecd  movzx   eax, r8w
0x180019ed1  mov     rbp, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180019ed9  lea     r14, [r14+rax*8]
0x180019edd  lea     r14, [r14+5DF38h]
0x180019ee4  cmp     r10, rbp
0x180019ee7  jnb     def_180019EC4; jumptable 0000000180019EC4 default case
0x180019eed  mov     rdx, r10
0x180019ef0  shl     rdx, 7
0x180019ef4  add     rdx, [r14]
0x180019ef7  cmp     [rdx], edi
0x180019ef9  jz      loc_180019C07
0x180019eff  inc     r10
0x180019f02  jmp     short loc_180019EE4
0x180019f04  cmp     ebx, 5; switch 6 cases
0x180019f07  ja      def_180019F1B; jumptable 0000000180019F1B default case
0x180019f0d  movsxd  rax, ebx
0x180019f10  mov     ecx, ds:(jpt_180019F1B - 180000000h)[r14+rax*4]
0x180019f18  add     rcx, r14
0x180019f1b  jmp     rcx; switch jump
0x180019f21  xor     edx, edx; jumptable 0000000180019F1B cases 0,1
0x180019f23  movzx   eax, r8w
0x180019f27  mov     r8, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180019f2f  lea     rbx, ds:5DF38h[rax*8]
0x180019f37  cmp     rdx, r8
0x180019f3a  jnb     def_180019F1B; jumptable 0000000180019F1B default case
0x180019f40  mov     rcx, rdx
0x180019f43  shl     rcx, 7
0x180019f47  mov     rax, [rbx+r14]
0x180019f4b  add     rax, rcx
0x180019f4e  cmp     [rax], r10d
0x180019f51  jz      loc_180019C3B
0x180019f57  inc     rdx
0x180019f5a  jmp     short loc_180019F37
0x180019f5c  mov     r14, [rsi+38h]
0x180019f60  test    r14, r14
0x180019f63  jz      loc_18001A341
0x180019f69  mov     rax, [r14]
0x180019f6c  mov     r15, [rax+68h]
0x180019f70  test    byte ptr [rsi+452h], 1
0x180019f77  jnz     loc_18001A2C2
0x180019f7d  mov     dword ptr [rsi+40h], 0
0x180019f84  mov     rdx, [rsp+118h+var_E8]
0x180019f89  mov     qword ptr [rdx], 0
0x180019f90  and     byte ptr [rsi+452h], 0FCh
0x180019f97  xor     ecx, ecx
0x180019f99  mov     [rsi+50h], cx
0x180019f9d  lea     r8, [rsi+40h]
0x180019fa1  mov     rcx, r14
0x180019fa4  mov     rax, r15
0x180019fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fac  test    eax, eax
0x180019fae  js      loc_18001A2D6
0x180019fb4  mov     edx, [rsi+45Ch]
0x180019fba  lea     r14, __ImageBase
0x180019fc1  cmp     edx, 10006h
0x180019fc7  jnz     loc_18001A1F0
0x180019fcd  movzx   eax, dx; jumptable 000000018001A208 cases 65538-65541
0x180019fd0  mov     rdx, rbx
0x180019fd3  shl     rdx, 7
0x180019fd7  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019fdf  cmp     dword ptr [rdx+18h], 2
0x180019fe3  jz      loc_18001A1E1
0x180019fe9  cmp     dword ptr [rsi+40h], 35h ; '5'
0x180019fed  jnz     loc_18001A083
0x180019ff3  mov     r8d, 35h ; '5'; MaxCount
0x180019ff9  mov     rdx, cs:?namespaceUri@Schema@@0UConstString@@B; String2
0x18001a000  mov     rcx, [rsi+48h]; String1
0x18001a004  call    wcsncmp_0
0x18001a009  test    eax, eax
0x18001a00b  jnz     short loc_18001A083
0x18001a00d  cmp     byte ptr [rsi+28h], 0
0x18001a011  jnz     loc_18001A2EC
0x18001a017  mov     rax, [rsp+118h+var_D0]
0x18001a01c  mov     [rsp+118h+var_F8], rax
0x18001a021  xor     r9d, r9d
0x18001a024  mov     r8d, ebx
0x18001a027  mov     rdx, [rsp+118h+var_C8]
0x18001a02c  mov     rcx, rsi
0x18001a02f  call    ?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z; TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)
0x18001a034  test    eax, eax
0x18001a036  js      loc_180019C4D
0x18001a03c  xor     ecx, ecx
0x18001a03e  mov     r12d, [rsp+118h+var_E0]
0x18001a043  cmp     ecx, r12d
0x18001a046  jb      loc_18001A326
0x18001a04c  cmp     r12d, 16h
0x18001a050  jnb     loc_18001A333
  ... truncated ...
```
