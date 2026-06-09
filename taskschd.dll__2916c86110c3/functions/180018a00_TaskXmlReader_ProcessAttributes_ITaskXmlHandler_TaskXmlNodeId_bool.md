# TaskXmlReader::ProcessAttributes(ITaskXmlHandler *,TaskXmlNodeId,bool &)

- ea: `0x180018a00`
- end: `0x1800192dc`
- name: `?ProcessAttributes@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@AEA_N@Z`
- size: `2268`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800185f0`

## callees

- `0x180008d30`
- `0x1800136e0`
- `0x1800138e0`
- `0x180015810`
- `0x180015f60`
- `0x180018a00`
- `0x180019d10`
- `0x180019d68`
- `0x180038404`
- `0x18003843c`
- `0x180039708`
- `0x18004b8e8`
- `0x18004e91b`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180019137`
- `OLEAUT32!__imp_SysFreeString` at `0x18001915b`
- `OLEAUT32!__imp_SysFreeString` at `0x180019137`
- `OLEAUT32!__imp_SysFreeString` at `0x18001915b`

## string_xrefs

- `0x180018ba2`: `xmlns`

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
              v13 = (const struct SchemaEntry **)&qword_18006EE10;
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
                  v43 = 8 * v41 + 368464;
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
              v16 = &qword_18006EE10;
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
            v56 = 8LL * (unsigned __int16)v26 + 368464;
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
        v28 = &qword_18006EE10;
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
        v31 = (const struct SchemaEntry **)&qword_18006EE10;
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
            v59 = 8LL * (unsigned __int16)v30 + 368464;
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
        v35 = &qword_18006EE10;
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
          v62 = 8LL * (unsigned __int16)v48 + 368464;
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
      v49 = &qword_18006EE10;
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
0x180018a00  push    rbx
0x180018a02  push    rbp
0x180018a03  push    rsi
0x180018a04  push    rdi
0x180018a05  push    r12
0x180018a07  push    r13
0x180018a09  push    r14
0x180018a0b  push    r15
0x180018a0d  sub     rsp, 0D8h
0x180018a14  mov     rax, cs:__security_cookie
0x180018a1b  xor     rax, rsp
0x180018a1e  mov     [rsp+118h+var_58], rax
0x180018a26  mov     [rsp+118h+var_D0], r9
0x180018a2b  movsxd  rdi, r8d
0x180018a2e  mov     [rsp+118h+var_C8], rdx
0x180018a33  mov     rsi, rcx
0x180018a36  xor     r12d, r12d
0x180018a39  mov     [rsp+118h+var_D8], r12
0x180018a3e  lea     r14, __ImageBase
0x180018a45  mov     [rsp+118h+var_E0], r12d
0x180018a4a  mov     rcx, [rsi+38h]
0x180018a4e  test    rcx, rcx
0x180018a51  jz      loc_18001923E
0x180018a57  mov     rax, [rcx]
0x180018a5a  mov     rax, [rax+48h]
0x180018a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a63  test    eax, eax
0x180018a65  jz      loc_180018B33
0x180018a6b  js      loc_1800191E7
0x180018a71  xor     r9d, r9d
0x180018a74  lea     r11, [rsi+45Ch]
0x180018a7b  nop     dword ptr [rax+rax+00h]
0x180018a80  cmp     r9d, 16h
0x180018a84  jnb     short loc_180018AF1
0x180018a86  lea     r11, [rsi+45Ch]
0x180018a8d  mov     r8d, [r11]
0x180018a90  cmp     r8d, 10006h
0x180018a97  jnz     loc_180018D56
0x180018a9d  movzx   eax, r8w; jumptable 0000000180018D74 cases 65538-65541
0x180018aa1  mov     rdx, rdi
0x180018aa4  shl     rdx, 7
0x180018aa8  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180018ab0  lea     ebx, [r8-10000h]
0x180018ab7  movsxd  rax, r9d
0x180018aba  movsxd  r10, dword ptr [rdx+rax*4+28h]
0x180018abf  test    r10d, r10d
0x180018ac2  jz      short loc_180018AF1
0x180018ac4  lea     r14, __ImageBase
0x180018acb  cmp     r8d, 10006h
0x180018ad2  jnz     loc_180018DB0
0x180018ad8  movzx   ecx, r8w; jumptable 0000000180018DC7 cases 2-5
0x180018adc  mov     rax, r10
0x180018adf  shl     rax, 7
0x180018ae3  add     rax, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180018aeb  cmp     dword ptr [rax+18h], 2
0x180018aef  jz      short loc_180018B21
0x180018af1  cmp     byte ptr [rsi+28h], 0
0x180018af5  jnz     loc_180019201
0x180018afb  xor     eax, eax
0x180018afd  mov     rcx, [rsp+118h+var_58]
0x180018b05  xor     rcx, rsp; StackCookie
0x180018b08  call    __security_check_cookie
0x180018b0d  add     rsp, 0D8h
0x180018b14  pop     r15
0x180018b16  pop     r14
0x180018b18  pop     r13
0x180018b1a  pop     r12
0x180018b1c  pop     rdi
0x180018b1d  pop     rsi
0x180018b1e  pop     rbp
0x180018b1f  pop     rbx
0x180018b20  retn
0x180018b21  cmp     dword ptr [rax+20h], 0
0x180018b25  jnz     loc_180018F0C
0x180018b2b  inc     r9d
0x180018b2e  jmp     loc_180018A80
0x180018b33  mov     rbx, [rsi+38h]
0x180018b37  test    rbx, rbx
0x180018b3a  jz      loc_1800191F6
0x180018b40  mov     rax, [rbx]
0x180018b43  mov     rbp, [rax+70h]
0x180018b47  lea     r15, [rsi+48h]
0x180018b4b  mov     [rsp+118h+var_E8], r15
0x180018b50  test    byte ptr [rsi+452h], 1
0x180018b57  jnz     loc_180019134
0x180018b5d  mov     [rsp+118h+var_E8], r15
0x180018b62  mov     dword ptr [rsi+40h], 0
0x180018b69  mov     qword ptr [r15], 0
0x180018b70  and     byte ptr [rsi+452h], 0FCh
0x180018b77  xor     ecx, ecx
0x180018b79  mov     [rsi+50h], cx
0x180018b7d  lea     r8, [rsi+40h]
0x180018b81  mov     rdx, r15
0x180018b84  mov     rcx, rbx
0x180018b87  mov     rax, rbp
0x180018b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b8f  test    eax, eax
0x180018b91  js      loc_1800191E7
0x180018b97  mov     eax, [rsi+40h]
0x180018b9a  test    eax, eax
0x180018b9c  jz      loc_180018A4A
0x180018ba2  lea     rbx, aXmlns; "xmlns"
0x180018ba9  cmp     eax, 5
0x180018bac  jnz     short loc_180018BC5
0x180018bae  mov     r8d, eax; MaxCount
0x180018bb1  mov     rdx, rbx; String2
0x180018bb4  mov     rcx, [rsi+48h]; String1
0x180018bb8  call    wcsncmp_0
0x180018bbd  test    eax, eax
0x180018bbf  jz      loc_180018A4A
0x180018bc5  mov     rcx, [rsi+38h]
0x180018bc9  test    rcx, rcx
0x180018bcc  jz      loc_1800191DC
0x180018bd2  mov     rax, [rcx]
0x180018bd5  xor     r8d, r8d
0x180018bd8  lea     rdx, [rsp+118h+var_D8]
0x180018bdd  mov     rax, [rax+78h]
0x180018be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018be6  test    eax, eax
0x180018be8  js      loc_1800191E7
0x180018bee  mov     r8, [rsp+118h+var_D8]
0x180018bf3  test    r8, r8
0x180018bf6  jz      short loc_180018C1F
0x180018bf8  xor     ecx, ecx
0x180018bfa  nop     word ptr [rax+rax+00h]
0x180018c00  movzx   edx, word ptr [r8+rcx*2]
0x180018c05  inc     rcx
0x180018c08  movzx   eax, word ptr [rbx+rcx*2-2]
0x180018c0d  sub     edx, eax
0x180018c0f  jnz     short loc_180018C17
0x180018c11  cmp     rcx, 6
0x180018c15  jnz     short loc_180018C00
0x180018c17  test    edx, edx
0x180018c19  jz      loc_180018A4A
0x180018c1f  xor     r14d, r14d
0x180018c22  movsxd  rbx, r14d
0x180018c25  cmp     rbx, 16h
0x180018c29  jnb     loc_180018CC0
0x180018c2f  test    edi, edi
0x180018c31  jz      loc_180018CC0
0x180018c37  mov     edx, [rsi+45Ch]
0x180018c3d  cmp     edx, 10002h
0x180018c43  jz      short loc_180018C58
0x180018c45  cmp     edx, 10006h
0x180018c4b  jnz     loc_180018D1D
0x180018c51  mov     eax, 95h
0x180018c56  jmp     short loc_180018C5D
0x180018c58  mov     eax, 83h
0x180018c5d  cmp     edi, eax
0x180018c5f  jge     short loc_180018CC0
0x180018c61  lea     r11, __ImageBase
0x180018c68  cmp     edx, 10006h
0x180018c6e  jnz     loc_180018F9E
0x180018c74  movzx   eax, dx; jumptable 0000000180018FBA cases 65538-65541
0x180018c77  mov     rdx, rdi
0x180018c7a  shl     rdx, 7
0x180018c7e  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180018c86  movsxd  rbx, dword ptr [rdx+rbx*4+28h]
0x180018c8b  test    ebx, ebx
0x180018c8d  jz      short loc_180018CC0
0x180018c8f  mov     edx, [rsi+45Ch]
0x180018c95  cmp     edx, 10006h
0x180018c9b  jnz     loc_180018F4D
0x180018ca1  movzx   eax, dx; jumptable 0000000180018F6A cases 65538-65541
0x180018ca4  mov     r8, rbx
0x180018ca7  shl     r8, 7
0x180018cab  add     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180018cb3  lea     ebp, [rdx-10000h]
0x180018cb9  cmp     dword ptr [r8+18h], 2
0x180018cbe  jz      short loc_180018CD6
0x180018cc0  lea     r8, [rsi+40h]; struct XmlParserTempString *
0x180018cc4  mov     edx, 80041316h; int
0x180018cc9  mov     rcx, rsi; this
0x180018ccc  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJAEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,XmlParserTempString &)
0x180018cd1  jmp     loc_180018AFD
0x180018cd6  cmp     edx, 10006h
0x180018cdc  jnz     loc_180019006
0x180018ce2  movzx   eax, dx; jumptable 0000000180019019 cases 2-5
0x180018ce5  mov     rdx, rbx
0x180018ce8  shl     rdx, 7
0x180018cec  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180018cf4  mov     r8d, [rdx+10h]; MaxCount
0x180018cf8  cmp     [rsi+40h], r8d
0x180018cfc  jnz     short loc_180018D15
0x180018cfe  mov     rbp, [r15]
0x180018d01  mov     rdx, [rdx+8]; String2
0x180018d05  mov     rcx, rbp; String1
0x180018d08  call    wcsncmp_0
0x180018d0d  test    eax, eax
0x180018d0f  jz      loc_180018E05
0x180018d15  inc     r14d
0x180018d18  jmp     loc_180018C22
0x180018d1d  mov     ecx, edx
0x180018d1f  sub     ecx, 10000h
0x180018d25  jz      loc_180018C58
0x180018d2b  sub     ecx, 1
0x180018d2e  jz      loc_180018C58
0x180018d34  sub     ecx, 2
0x180018d37  jz      short loc_180018D4C
0x180018d39  sub     ecx, 1
0x180018d3c  jnz     loc_180019142
0x180018d42  mov     eax, 91h
0x180018d47  jmp     loc_180018C5D
0x180018d4c  mov     eax, 88h
0x180018d51  jmp     loc_180018C5D
0x180018d56  lea     ebx, [r8-10000h]; switch 6 cases
0x180018d5d  cmp     ebx, 5
0x180018d60  ja      def_180018D74; jumptable 0000000180018D74 default case
0x180018d66  movsxd  rax, ebx
0x180018d69  mov     ecx, ds:(jpt_180018D74 - 180000000h)[r14+rax*4]
0x180018d71  add     rcx, r14
0x180018d74  jmp     rcx; switch jump
0x180018d76  xor     r10d, r10d; jumptable 0000000180018D74 cases 65536,65537
0x180018d79  movzx   eax, r8w
0x180018d7d  mov     rbp, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180018d85  lea     r14, [r14+rax*8]
0x180018d89  lea     r14, [r14+59F50h]
0x180018d90  cmp     r10, rbp
0x180018d93  jnb     def_180018D74; jumptable 0000000180018D74 default case
0x180018d99  mov     rdx, r10
0x180018d9c  shl     rdx, 7
0x180018da0  add     rdx, [r14]
0x180018da3  cmp     [rdx], edi
0x180018da5  jz      loc_180018AB7
0x180018dab  inc     r10
0x180018dae  jmp     short loc_180018D90
0x180018db0  cmp     ebx, 5; switch 6 cases
0x180018db3  ja      def_180018DC7; jumptable 0000000180018DC7 default case
0x180018db9  movsxd  rax, ebx
0x180018dbc  mov     ecx, ds:(jpt_180018DC7 - 180000000h)[r14+rax*4]
0x180018dc4  add     rcx, r14
0x180018dc7  jmp     rcx; switch jump
0x180018dc9  xor     edx, edx; jumptable 0000000180018DC7 cases 0,1
0x180018dcb  movzx   eax, r8w
0x180018dcf  mov     r8, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180018dd7  lea     rbx, ds:59F50h[rax*8]
0x180018ddf  nop
0x180018de0  cmp     rdx, r8
0x180018de3  jnb     def_180018DC7; jumptable 0000000180018DC7 default case
0x180018de9  mov     rcx, rdx
0x180018dec  shl     rcx, 7
0x180018df0  mov     rax, [rbx+r14]
0x180018df4  add     rax, rcx
0x180018df7  cmp     [rax], r10d
0x180018dfa  jz      loc_180018AEB
0x180018e00  inc     rdx
0x180018e03  jmp     short loc_180018DE0
0x180018e05  mov     r14, [rsi+38h]
0x180018e09  test    r14, r14
0x180018e0c  jz      loc_1800191D1
0x180018e12  mov     rax, [r14]
0x180018e15  mov     r15, [rax+68h]
0x180018e19  test    byte ptr [rsi+452h], 1
0x180018e20  jnz     loc_180019158
0x180018e26  mov     dword ptr [rsi+40h], 0
0x180018e2d  mov     rdx, [rsp+118h+var_E8]
0x180018e32  mov     qword ptr [rdx], 0
0x180018e39  and     byte ptr [rsi+452h], 0FCh
0x180018e40  xor     ecx, ecx
0x180018e42  mov     [rsi+50h], cx
0x180018e46  lea     r8, [rsi+40h]
0x180018e4a  mov     rcx, r14
0x180018e4d  mov     rax, r15
0x180018e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e55  test    eax, eax
0x180018e57  js      loc_180019166
0x180018e5d  mov     edx, [rsi+45Ch]
0x180018e63  lea     r14, __ImageBase
0x180018e6a  cmp     edx, 10006h
0x180018e70  jnz     loc_18001908D
0x180018e76  movzx   eax, dx; jumptable 00000001800190A5 cases 65538-65541
0x180018e79  mov     rdx, rbx
0x180018e7c  shl     rdx, 7
0x180018e80  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180018e88  cmp     dword ptr [rdx+18h], 2
0x180018e8c  jz      loc_18001907E
0x180018e92  cmp     dword ptr [rsi+40h], 35h ; '5'
0x180018e96  jnz     loc_180018F2C
0x180018e9c  mov     r8d, 35h ; '5'; MaxCount
0x180018ea2  mov     rdx, cs:?namespaceUri@Schema@@0UConstString@@B; String2
0x180018ea9  mov     rcx, [rsi+48h]; String1
0x180018ead  call    wcsncmp_0
0x180018eb2  test    eax, eax
0x180018eb4  jnz     short loc_180018F2C
0x180018eb6  cmp     byte ptr [rsi+28h], 0
0x180018eba  jnz     loc_18001917C
0x180018ec0  mov     rax, [rsp+118h+var_D0]
0x180018ec5  mov     [rsp+118h+var_F8], rax
0x180018eca  xor     r9d, r9d
0x180018ecd  mov     r8d, ebx
0x180018ed0  mov     rdx, [rsp+118h+var_C8]
0x180018ed5  mov     rcx, rsi
0x180018ed8  call    ?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z; TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)
0x180018edd  test    eax, eax
0x180018edf  js      loc_180018AFD
0x180018ee5  xor     ecx, ecx
0x180018ee7  mov     r12d, [rsp+118h+var_E0]
0x180018eec  cmp     ecx, r12d
0x180018eef  jb      loc_1800191B6
0x180018ef5  cmp     r12d, 16h
  ... truncated ...
```
