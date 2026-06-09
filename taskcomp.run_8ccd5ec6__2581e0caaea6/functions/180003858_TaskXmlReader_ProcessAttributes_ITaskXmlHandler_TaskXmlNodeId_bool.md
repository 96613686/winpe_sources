# TaskXmlReader::ProcessAttributes(ITaskXmlHandler *,TaskXmlNodeId,bool &)

- ea: `0x180003858`
- end: `0x180003b97`
- name: `?ProcessAttributes@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@AEA_N@Z`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800207d4`

## callees

- `0x1800033d0`
- `0x180003858`
- `0x180003f7c`
- `0x1800050d0`
- `0x180005284`
- `0x18001da84`
- `0x18001e37c`
- `0x18001e400`
- `0x18001e550`
- `0x18001ea3c`
- `0x18001ea5c`
- `0x18001ed88`
- `0x18002096c`
- `0x180021904`
- `0x180021aec`
- `0x180021bc8`
- `0x180021fa8`
- `0x1800306ce`
- `0x180030700`
- `0x180033010`

## string_xrefs

- `0x1800038fe`: `xmlns`
- `0x180003945`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskXmlReader::ProcessAttributes(__int64 a1, __int64 a2, unsigned int a3, _BYTE *a4)
{
  __int64 v6; // r15
  __int64 v7; // r13
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, const unsigned __int16 **, __int64); // rbx
  bool v12; // dl
  const unsigned __int16 **PString; // rax
  __int64 v14; // rax
  int i; // ebx
  unsigned int v16; // eax
  unsigned int v17; // edi
  __int64 Entry; // rax
  __int64 result; // rax
  int RawValue; // eax
  __int64 Copy; // rax
  __int64 v22; // r9
  int started; // ebx
  __int64 j; // rcx
  int v25; // edx
  unsigned int v26; // edi
  __int64 v27; // rbx
  unsigned int v28; // r14d
  __int64 v29; // rax
  unsigned int k; // ecx
  int v31; // eax
  unsigned int v32; // ecx
  __int64 *v33; // [rsp+30h] [rbp-89h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v35[8]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE *v36; // [rsp+48h] [rbp-71h]
  __int64 v37; // [rsp+50h] [rbp-69h]
  _DWORD v38[24]; // [rsp+60h] [rbp-59h]

  v36 = a4;
  v37 = a2;
  v6 = 0;
  String1 = 0;
  v7 = a1 + 56;
  while ( 1 )
  {
    v8 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(v7);
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 72LL))(v8);
    if ( v9 )
      break;
    v10 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(v7);
    v11 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 **, __int64))(*(_QWORD *)v10 + 112LL);
    PString = XmlParserTempString::GetPString((XmlParserTempString *)(a1 + 64), v12);
    v9 = v11(v10, PString, a1 + 64);
    if ( v9 < 0 )
      return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v9);
    if ( *(_DWORD *)(a1 + 64) && !XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"xmlns", 5u) )
    {
      v14 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(v7);
      v9 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v14 + 120LL))(v14, &String1, 0);
      if ( v9 < 0 )
        return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v9);
      if ( !String1 || wcscmp_0(String1, L"xmlns") )
      {
        for ( i = 0; ; ++i )
        {
          if ( (unsigned __int64)i >= 0x16
            || (v16 = Schema::ChildId(a1 + 1116, a3), (v17 = v16) == 0)
            || (Entry = Schema::GetEntry(a1 + 1116, v16), *(_DWORD *)(Entry + 24) != 2) )
          {
            v25 = -2147216618;
            return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, v25, (struct XmlParserTempString *)(a1 + 64));
          }
          if ( XmlParserTempString::IsEqualTo(
                 (XmlParserTempString *)(a1 + 64),
                 *(const unsigned __int16 **)(Entry + 8),
                 *(unsigned int *)(Entry + 16)) )
          {
            break;
          }
        }
        result = TaskXmlReader::ValidateNamespace(a1, v17);
        if ( (int)result < 0 )
          return result;
        if ( *(_BYTE *)(a1 + 40) && a3 != 1 )
        {
          v33 = 0;
          RawValue = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( RawValue < 0 )
          {
            started = RawValue;
          }
          else
          {
            Copy = XmlParserTempString::GetCopy(a1 + 64, v35);
            _bstr_t::operator=(&v33, Copy);
            _bstr_t::~_bstr_t((_bstr_t *)v35);
            if ( v33 )
              v22 = *v33;
            else
              v22 = 0;
            started = TaskXmlWriter::StartElementWithAttribute(*(_QWORD *)(a1 + 16), a3, v17, v22);
            if ( started >= 0 )
            {
              _bstr_t::~_bstr_t((_bstr_t *)&v33);
              goto LABEL_24;
            }
          }
          _bstr_t::~_bstr_t((_bstr_t *)&v33);
          return (unsigned int)started;
        }
LABEL_24:
        result = TaskXmlReader::ProcessSimpleContent(a1, v37, v17, 0, v36);
        if ( (int)result < 0 )
          return result;
        for ( j = 0; (unsigned int)j < (unsigned int)v6; j = (unsigned int)(j + 1) )
        {
          if ( v38[j] == v17 )
            goto LABEL_33;
        }
        if ( (unsigned int)v6 < 0x16 )
        {
          v38[v6] = v17;
          v6 = (unsigned int)(v6 + 1);
          v7 = a1 + 56;
          continue;
        }
LABEL_33:
        v25 = -2147216611;
        return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, v25, (struct XmlParserTempString *)(a1 + 64));
      }
    }
  }
  if ( v9 < 0 )
    return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v9);
  v26 = 0;
  v27 = a1 + 1116;
  while ( 1 )
  {
    if ( v26 >= 0x16
      || (v27 = a1 + 1116, (v28 = *(_DWORD *)(Schema::GetEntry(a1 + 1116, a3) + 4LL * (int)v26 + 40)) == 0)
      || (v29 = Schema::GetEntry(a1 + 1116, v28), *(_DWORD *)(v29 + 24) != 2) )
    {
      if ( !*(_BYTE *)(a1 + 40) || a3 == 1 || (_DWORD)v6 || *(_DWORD *)(Schema::GetEntry(v27, a3) + 28) )
        return 0;
      v31 = TaskXmlWriter::StartElement(*(_QWORD *)(a1 + 16), a3);
      v32 = 0;
      if ( v31 < 0 )
        return (unsigned int)v31;
      return v32;
    }
    if ( *(_DWORD *)(v29 + 32) )
      break;
LABEL_47:
    ++v26;
  }
  for ( k = 0; k < (unsigned int)v6; ++k )
  {
    if ( v38[k] == v28 )
      goto LABEL_47;
  }
  return TaskXmlReader::SetErrorInfo(a1, 2147750681LL, v28);
}

```

## disassembly

```asm
0x180003858  push    rbp
0x18000385a  push    rbx
0x18000385b  push    rsi
0x18000385c  push    rdi
0x18000385d  push    r12
0x18000385f  push    r13
0x180003861  push    r14
0x180003863  push    r15
0x180003865  lea     rbp, [rsp-1Fh]
0x18000386a  sub     rsp, 0D8h
0x180003871  mov     rax, cs:__security_cookie
0x180003878  xor     rax, rsp
0x18000387b  mov     [rbp+57h+var_50], rax
0x18000387f  mov     [rbp+57h+var_C8], r9
0x180003883  mov     r12d, r8d
0x180003886  mov     [rbp+57h+var_C0], rdx
0x18000388a  mov     rsi, rcx
0x18000388d  xor     r15d, r15d
0x180003890  mov     [rsp+110h+String1], r15
0x180003895  lea     r13, [rcx+38h]
0x180003899  mov     rcx, r13
0x18000389c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x1800038a1  mov     rdx, rax
0x1800038a4  mov     rcx, [rax]
0x1800038a7  mov     rax, [rcx+48h]
0x1800038ab  mov     rcx, rdx
0x1800038ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b3  test    eax, eax
0x1800038b5  jnz     loc_180003AC6
0x1800038bb  mov     rcx, r13
0x1800038be  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x1800038c3  mov     rdi, rax
0x1800038c6  mov     rcx, [rax]
0x1800038c9  mov     rbx, [rcx+70h]
0x1800038cd  lea     r14, [rsi+40h]
0x1800038d1  mov     rcx, r14; this
0x1800038d4  call    ?GetPString@XmlParserTempString@@QEAAPEAPEBG_N@Z; XmlParserTempString::GetPString(bool)
0x1800038d9  mov     r8, r14
0x1800038dc  mov     rdx, rax
0x1800038df  mov     rcx, rdi
0x1800038e2  mov     rax, rbx
0x1800038e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ea  test    eax, eax
0x1800038ec  js      loc_180003AB7
0x1800038f2  cmp     dword ptr [r14], 0
0x1800038f6  jz      short loc_180003899
0x1800038f8  mov     r8d, 5; unsigned __int64
0x1800038fe  lea     rdx, aXmlns; "xmlns"
0x180003905  mov     rcx, r14; this
0x180003908  call    ?IsEqualTo@XmlParserTempString@@QEBA_NPEBG_K@Z; XmlParserTempString::IsEqualTo(ushort const *,unsigned __int64)
0x18000390d  test    al, al
0x18000390f  jnz     short loc_180003899
0x180003911  mov     rcx, r13
0x180003914  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180003919  mov     r9, rax
0x18000391c  mov     rcx, [rax]
0x18000391f  mov     rax, [rcx+78h]
0x180003923  xor     r8d, r8d
0x180003926  lea     rdx, [rsp+110h+String1]
0x18000392b  mov     rcx, r9
0x18000392e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003933  test    eax, eax
0x180003935  js      loc_180003AB7
0x18000393b  mov     rcx, [rsp+110h+String1]; String1
0x180003940  test    rcx, rcx
0x180003943  jz      short loc_180003959
0x180003945  lea     rdx, aXmlns; "xmlns"
0x18000394c  call    wcscmp_0
0x180003951  test    eax, eax
0x180003953  jz      loc_180003899
0x180003959  xor     ebx, ebx
0x18000395b  movsxd  r8, ebx
0x18000395e  cmp     r8, 16h
0x180003962  jnb     loc_180003AB0
0x180003968  lea     r13, [rsi+45Ch]
0x18000396f  mov     edx, r12d
0x180003972  mov     rcx, r13
0x180003975  call    ?ChildId@Schema@@QEBA?AW4TaskXmlNodeId@@W42@_K@Z; Schema::ChildId(TaskXmlNodeId,unsigned __int64)
0x18000397a  mov     edi, eax
0x18000397c  test    eax, eax
0x18000397e  jz      loc_180003AB0
0x180003984  mov     edx, eax
0x180003986  mov     rcx, r13
0x180003989  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18000398e  cmp     dword ptr [rax+18h], 2
0x180003992  jnz     loc_180003AB0
0x180003998  mov     r8d, [rax+10h]; unsigned __int64
0x18000399c  mov     rdx, [rax+8]; unsigned __int16 *
0x1800039a0  mov     rcx, r14; this
0x1800039a3  call    ?IsEqualTo@XmlParserTempString@@QEBA_NPEBG_K@Z; XmlParserTempString::IsEqualTo(ushort const *,unsigned __int64)
0x1800039a8  test    al, al
0x1800039aa  jnz     short loc_1800039B0
0x1800039ac  inc     ebx
0x1800039ae  jmp     short loc_18000395B
0x1800039b0  mov     edx, edi
0x1800039b2  mov     rcx, rsi
0x1800039b5  call    ?ValidateNamespace@TaskXmlReader@@AEAAJW4TaskXmlNodeId@@@Z; TaskXmlReader::ValidateNamespace(TaskXmlNodeId)
0x1800039ba  test    eax, eax
0x1800039bc  js      loc_180003B76
0x1800039c2  cmp     byte ptr [rsi+28h], 0
0x1800039c6  jz      short loc_180003A3D
0x1800039c8  cmp     r12d, 1
0x1800039cc  jz      short loc_180003A3D
0x1800039ce  mov     [rsp+110h+var_E0], 0
0x1800039d7  mov     rdx, r14; struct XmlParserTempString *
0x1800039da  mov     rcx, rsi; this
0x1800039dd  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x1800039e2  test    eax, eax
0x1800039e4  js      loc_180003A88
0x1800039ea  lea     rdx, [rbp+57h+var_D0]
0x1800039ee  mov     rcx, r14
0x1800039f1  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800039f6  mov     rdx, rax
0x1800039f9  lea     rcx, [rsp+110h+var_E0]
0x1800039fe  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003a03  lea     rcx, [rbp+57h+var_D0]; this
0x180003a07  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003a0c  mov     rax, [rsp+110h+var_E0]
0x180003a11  test    rax, rax
0x180003a14  jz      short loc_180003A1B
0x180003a16  mov     r9, [rax]
0x180003a19  jmp     short loc_180003A1E
0x180003a1b  xor     r9d, r9d
0x180003a1e  mov     r8d, edi
0x180003a21  mov     edx, r12d
0x180003a24  mov     rcx, [rsi+10h]
0x180003a28  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180003a2d  mov     ebx, eax
0x180003a2f  test    eax, eax
0x180003a31  js      short loc_180003A8A
0x180003a33  lea     rcx, [rsp+110h+var_E0]; this
0x180003a38  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003a3d  mov     rax, [rbp+57h+var_C8]
0x180003a41  mov     [rsp+110h+var_F0], rax
0x180003a46  xor     r9d, r9d
0x180003a49  mov     r8d, edi
0x180003a4c  mov     rdx, [rbp+57h+var_C0]
0x180003a50  mov     rcx, rsi
0x180003a53  call    ?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z; TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)
0x180003a58  test    eax, eax
0x180003a5a  js      loc_180003B76
0x180003a60  xor     ecx, ecx
0x180003a62  cmp     ecx, r15d
0x180003a65  jnb     short loc_180003A71
0x180003a67  cmp     [rbp+rcx*4+57h+var_B0], edi
0x180003a6b  jz      short loc_180003A9B
0x180003a6d  inc     ecx
0x180003a6f  jmp     short loc_180003A62
0x180003a71  cmp     r15d, 16h
0x180003a75  jnb     short loc_180003A9B
0x180003a77  mov     [rbp+r15*4+57h+var_B0], edi
0x180003a7c  inc     r15d
0x180003a7f  lea     r13, [rsi+38h]
0x180003a83  jmp     loc_180003899
0x180003a88  mov     ebx, eax
0x180003a8a  lea     rcx, [rsp+110h+var_E0]; this
0x180003a8f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003a94  mov     eax, ebx
0x180003a96  jmp     loc_180003B76
0x180003a9b  mov     edx, 8004131Dh; int
0x180003aa0  mov     r8, r14; struct XmlParserTempString *
0x180003aa3  mov     rcx, rsi; this
0x180003aa6  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJAEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,XmlParserTempString &)
0x180003aab  jmp     loc_180003B76
0x180003ab0  mov     edx, 80041316h
0x180003ab5  jmp     short loc_180003AA0
0x180003ab7  mov     edx, eax; int
0x180003ab9  mov     rcx, rsi; this
0x180003abc  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x180003ac1  jmp     loc_180003B76
0x180003ac6  js      short loc_180003AB7
0x180003ac8  xor     edi, edi
0x180003aca  lea     rbx, [rsi+45Ch]
0x180003ad1  xor     r13d, r13d
0x180003ad4  cmp     edi, 16h
0x180003ad7  jnb     short loc_180003B3A
0x180003ad9  lea     rbx, [rsi+45Ch]
0x180003ae0  mov     edx, r12d
0x180003ae3  mov     rcx, rbx
0x180003ae6  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180003aeb  movsxd  rcx, edi
0x180003aee  mov     r14d, [rax+rcx*4+28h]
0x180003af3  test    r14d, r14d
0x180003af6  jz      short loc_180003B3A
0x180003af8  mov     edx, r14d
0x180003afb  mov     rcx, rbx
0x180003afe  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180003b03  cmp     dword ptr [rax+18h], 2
0x180003b07  jnz     short loc_180003B3A
0x180003b09  cmp     [rax+20h], r13d
0x180003b0d  jz      short loc_180003B24
0x180003b0f  mov     ecx, r13d
0x180003b12  cmp     ecx, r15d
0x180003b15  jnb     short loc_180003B28
0x180003b17  mov     eax, ecx
0x180003b19  cmp     [rbp+rax*4+57h+var_B0], r14d
0x180003b1e  jz      short loc_180003B24
0x180003b20  inc     ecx
0x180003b22  jmp     short loc_180003B12
0x180003b24  inc     edi
0x180003b26  jmp     short loc_180003AD4
0x180003b28  mov     r8d, r14d
0x180003b2b  mov     edx, 80041319h
0x180003b30  mov     rcx, rsi
0x180003b33  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x180003b38  jmp     short loc_180003B76
0x180003b3a  cmp     [rsi+28h], r13b
0x180003b3e  jz      short loc_180003B74
0x180003b40  cmp     r12d, 1
0x180003b44  jz      short loc_180003B74
0x180003b46  test    r15d, r15d
0x180003b49  jnz     short loc_180003B74
0x180003b4b  mov     edx, r12d
0x180003b4e  mov     rcx, rbx
0x180003b51  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180003b56  cmp     [rax+1Ch], r13d
0x180003b5a  jnz     short loc_180003B74
0x180003b5c  mov     edx, r12d
0x180003b5f  mov     rcx, [rsi+10h]
0x180003b63  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180003b68  mov     ecx, r13d
0x180003b6b  test    eax, eax
0x180003b6d  cmovs   ecx, eax
0x180003b70  mov     eax, ecx
0x180003b72  jmp     short loc_180003B76
0x180003b74  xor     eax, eax
0x180003b76  mov     rcx, [rbp+57h+var_50]
0x180003b7a  xor     rcx, rsp; StackCookie
0x180003b7d  call    __security_check_cookie
0x180003b82  add     rsp, 0D8h
0x180003b89  pop     r15
0x180003b8b  pop     r14
0x180003b8d  pop     r13
0x180003b8f  pop     r12
0x180003b91  pop     rdi
0x180003b92  pop     rsi
0x180003b93  pop     rbx
0x180003b94  pop     rbp
0x180003b95  retn
```
