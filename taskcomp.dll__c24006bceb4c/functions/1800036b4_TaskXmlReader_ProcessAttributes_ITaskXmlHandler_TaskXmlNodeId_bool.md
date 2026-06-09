# TaskXmlReader::ProcessAttributes(ITaskXmlHandler *,TaskXmlNodeId,bool &)

- ea: `0x1800036b4`
- end: `0x1800039f2`
- name: `?ProcessAttributes@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@AEA_N@Z`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f1e8`

## callees

- `0x180003250`
- `0x1800036b4`
- `0x180003dac`
- `0x180004e50`
- `0x180004fe4`
- `0x18001c534`
- `0x18001ce0c`
- `0x18001ce90`
- `0x18001cfe0`
- `0x18001d4a4`
- `0x18001d4c4`
- `0x18001d7dc`
- `0x18001f380`
- `0x18002030c`
- `0x1800204f0`
- `0x1800205cc`
- `0x180020988`
- `0x18002e57e`
- `0x18002e5b0`
- `0x180031010`

## string_xrefs

- `0x18000375a`: `xmlns`
- `0x1800037a1`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskXmlReader::ProcessAttributes(__int64 a1, _BOOL8 a2, unsigned int a3, _BYTE *a4)
{
  __int64 v6; // r15
  __int64 *v7; // r13
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, BSTR *, __int64); // rbx
  BSTR *PString; // rax
  __int64 v13; // rax
  int i; // ebx
  int v15; // eax
  unsigned int v16; // edi
  __int64 *Entry; // rax
  __int64 result; // rax
  int RawValue; // eax
  _bstr_t *Copy; // rax
  __int64 v21; // r9
  int started; // ebx
  __int64 j; // rcx
  int v24; // edx
  unsigned int v25; // edi
  int *v26; // rbx
  unsigned int v27; // r14d
  __int64 *v28; // rax
  unsigned int k; // ecx
  int v30; // eax
  unsigned int v31; // ecx
  __int64 *v32; // [rsp+30h] [rbp-89h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v34[8]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE *v35; // [rsp+48h] [rbp-71h]
  _BOOL8 v36; // [rsp+50h] [rbp-69h]
  _DWORD v37[24]; // [rsp+60h] [rbp-59h]

  v35 = a4;
  v36 = a2;
  v6 = 0;
  String1 = 0;
  v7 = (__int64 *)(a1 + 56);
  while ( 1 )
  {
    v8 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(v7);
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 72LL))(v8);
    if ( v9 )
      break;
    v10 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(v7);
    v11 = *(__int64 (__fastcall **)(__int64, BSTR *, __int64))(*(_QWORD *)v10 + 112LL);
    PString = XmlParserTempString::GetPString((BSTR *)(a1 + 64));
    v9 = v11(v10, PString, a1 + 64);
    if ( v9 < 0 )
      return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v9);
    if ( *(_DWORD *)(a1 + 64) && !XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"xmlns", 5u) )
    {
      v13 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(v7);
      v9 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v13 + 120LL))(v13, &String1, 0);
      if ( v9 < 0 )
        return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v9);
      if ( !String1 || wcscmp_0(String1, L"xmlns") )
      {
        for ( i = 0; ; ++i )
        {
          if ( (unsigned __int64)i >= 0x16
            || (v15 = Schema::ChildId(a1 + 1116, a3, i), (v16 = v15) == 0)
            || (Entry = Schema::GetEntry((int *)(a1 + 1116), v15), *((_DWORD *)Entry + 6) != 2) )
          {
            v24 = -2147216618;
            return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, v24, (struct XmlParserTempString *)(a1 + 64));
          }
          if ( XmlParserTempString::IsEqualTo(
                 (XmlParserTempString *)(a1 + 64),
                 (const unsigned __int16 *)Entry[1],
                 *((unsigned int *)Entry + 4)) )
          {
            break;
          }
        }
        result = TaskXmlReader::ValidateNamespace(a1, v16);
        if ( (int)result < 0 )
          return result;
        if ( *(_BYTE *)(a1 + 40) && a3 != 1 )
        {
          v32 = 0;
          RawValue = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( RawValue < 0 )
          {
            started = RawValue;
          }
          else
          {
            Copy = XmlParserTempString::GetCopy((const OLECHAR **)(a1 + 64), (_bstr_t *)v34);
            _bstr_t::operator=((_bstr_t *)&v32, (__int64)Copy);
            _bstr_t::~_bstr_t((_bstr_t *)v34);
            if ( v32 )
              v21 = *v32;
            else
              v21 = 0;
            started = TaskXmlWriter::StartElementWithAttribute(*(_QWORD *)(a1 + 16), a3, v16, v21);
            if ( started >= 0 )
            {
              _bstr_t::~_bstr_t((_bstr_t *)&v32);
              goto LABEL_24;
            }
          }
          _bstr_t::~_bstr_t((_bstr_t *)&v32);
          return (unsigned int)started;
        }
LABEL_24:
        result = TaskXmlReader::ProcessSimpleContent(a1, v36, v16, 0, v35);
        if ( (int)result < 0 )
          return result;
        for ( j = 0; (unsigned int)j < (unsigned int)v6; j = (unsigned int)(j + 1) )
        {
          if ( v37[j] == v16 )
            goto LABEL_33;
        }
        if ( (unsigned int)v6 < 0x16 )
        {
          v37[v6] = v16;
          v6 = (unsigned int)(v6 + 1);
          v7 = (__int64 *)(a1 + 56);
          continue;
        }
LABEL_33:
        v24 = -2147216611;
        return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, v24, (struct XmlParserTempString *)(a1 + 64));
      }
    }
  }
  if ( v9 < 0 )
    return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v9);
  v25 = 0;
  v26 = (int *)(a1 + 1116);
  while ( 1 )
  {
    if ( v25 >= 0x16
      || (v26 = (int *)(a1 + 1116), (v27 = *((_DWORD *)Schema::GetEntry((int *)(a1 + 1116), a3) + (int)v25 + 10)) == 0)
      || (v28 = Schema::GetEntry((int *)(a1 + 1116), v27), *((_DWORD *)v28 + 6) != 2) )
    {
      if ( !*(_BYTE *)(a1 + 40) || a3 == 1 || (_DWORD)v6 || *((_DWORD *)Schema::GetEntry(v26, a3) + 7) )
        return 0;
      v30 = TaskXmlWriter::StartElement(*(_QWORD *)(a1 + 16), a3);
      v31 = 0;
      if ( v30 < 0 )
        return (unsigned int)v30;
      return v31;
    }
    if ( *((_DWORD *)v28 + 8) )
      break;
LABEL_47:
    ++v25;
  }
  for ( k = 0; k < (unsigned int)v6; ++k )
  {
    if ( v37[k] == v27 )
      goto LABEL_47;
  }
  return TaskXmlReader::SetErrorInfo(a1, 2147750681LL, v27);
}

```

## disassembly

```asm
0x1800036b4  push    rbp
0x1800036b6  push    rbx
0x1800036b7  push    rsi
0x1800036b8  push    rdi
0x1800036b9  push    r12
0x1800036bb  push    r13
0x1800036bd  push    r14
0x1800036bf  push    r15
0x1800036c1  lea     rbp, [rsp-1Fh]
0x1800036c6  sub     rsp, 0D8h
0x1800036cd  mov     rax, cs:__security_cookie
0x1800036d4  xor     rax, rsp
0x1800036d7  mov     [rbp+57h+var_50], rax
0x1800036db  mov     [rbp+57h+var_C8], r9
0x1800036df  mov     r12d, r8d
0x1800036e2  mov     [rbp+57h+var_C0], rdx
0x1800036e6  mov     rsi, rcx
0x1800036e9  xor     r15d, r15d
0x1800036ec  mov     [rsp+110h+String1], r15
0x1800036f1  lea     r13, [rcx+38h]
0x1800036f5  mov     rcx, r13
0x1800036f8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x1800036fd  mov     rdx, rax
0x180003700  mov     rcx, [rax]
0x180003703  mov     rax, [rcx+48h]
0x180003707  mov     rcx, rdx
0x18000370a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370f  test    eax, eax
0x180003711  jnz     loc_180003922
0x180003717  mov     rcx, r13
0x18000371a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18000371f  mov     rdi, rax
0x180003722  mov     rcx, [rax]
0x180003725  mov     rbx, [rcx+70h]
0x180003729  lea     r14, [rsi+40h]
0x18000372d  mov     rcx, r14; this
0x180003730  call    ?GetPString@XmlParserTempString@@QEAAPEAPEBG_N@Z; XmlParserTempString::GetPString(bool)
0x180003735  mov     r8, r14
0x180003738  mov     rdx, rax
0x18000373b  mov     rcx, rdi
0x18000373e  mov     rax, rbx
0x180003741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003746  test    eax, eax
0x180003748  js      loc_180003913
0x18000374e  cmp     dword ptr [r14], 0
0x180003752  jz      short loc_1800036F5
0x180003754  mov     r8d, 5; unsigned __int64
0x18000375a  lea     rdx, aXmlns; "xmlns"
0x180003761  mov     rcx, r14; this
0x180003764  call    ?IsEqualTo@XmlParserTempString@@QEBA_NPEBG_K@Z; XmlParserTempString::IsEqualTo(ushort const *,unsigned __int64)
0x180003769  test    al, al
0x18000376b  jnz     short loc_1800036F5
0x18000376d  mov     rcx, r13
0x180003770  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180003775  mov     r9, rax
0x180003778  mov     rcx, [rax]
0x18000377b  mov     rax, [rcx+78h]
0x18000377f  xor     r8d, r8d
0x180003782  lea     rdx, [rsp+110h+String1]
0x180003787  mov     rcx, r9
0x18000378a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378f  test    eax, eax
0x180003791  js      loc_180003913
0x180003797  mov     rcx, [rsp+110h+String1]; String1
0x18000379c  test    rcx, rcx
0x18000379f  jz      short loc_1800037B5
0x1800037a1  lea     rdx, aXmlns; "xmlns"
0x1800037a8  call    wcscmp_0
0x1800037ad  test    eax, eax
0x1800037af  jz      loc_1800036F5
0x1800037b5  xor     ebx, ebx
0x1800037b7  movsxd  r8, ebx
0x1800037ba  cmp     r8, 16h
0x1800037be  jnb     loc_18000390C
0x1800037c4  lea     r13, [rsi+45Ch]
0x1800037cb  mov     edx, r12d
0x1800037ce  mov     rcx, r13
0x1800037d1  call    ?ChildId@Schema@@QEBA?AW4TaskXmlNodeId@@W42@_K@Z; Schema::ChildId(TaskXmlNodeId,unsigned __int64)
0x1800037d6  mov     edi, eax
0x1800037d8  test    eax, eax
0x1800037da  jz      loc_18000390C
0x1800037e0  mov     edx, eax
0x1800037e2  mov     rcx, r13
0x1800037e5  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x1800037ea  cmp     dword ptr [rax+18h], 2
0x1800037ee  jnz     loc_18000390C
0x1800037f4  mov     r8d, [rax+10h]; unsigned __int64
0x1800037f8  mov     rdx, [rax+8]; unsigned __int16 *
0x1800037fc  mov     rcx, r14; this
0x1800037ff  call    ?IsEqualTo@XmlParserTempString@@QEBA_NPEBG_K@Z; XmlParserTempString::IsEqualTo(ushort const *,unsigned __int64)
0x180003804  test    al, al
0x180003806  jnz     short loc_18000380C
0x180003808  inc     ebx
0x18000380a  jmp     short loc_1800037B7
0x18000380c  mov     edx, edi
0x18000380e  mov     rcx, rsi
0x180003811  call    ?ValidateNamespace@TaskXmlReader@@AEAAJW4TaskXmlNodeId@@@Z; TaskXmlReader::ValidateNamespace(TaskXmlNodeId)
0x180003816  test    eax, eax
0x180003818  js      loc_1800039D2
0x18000381e  cmp     byte ptr [rsi+28h], 0
0x180003822  jz      short loc_180003899
0x180003824  cmp     r12d, 1
0x180003828  jz      short loc_180003899
0x18000382a  mov     [rsp+110h+var_E0], 0
0x180003833  mov     rdx, r14; struct XmlParserTempString *
0x180003836  mov     rcx, rsi; this
0x180003839  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x18000383e  test    eax, eax
0x180003840  js      loc_1800038E4
0x180003846  lea     rdx, [rbp+57h+var_D0]
0x18000384a  mov     rcx, r14
0x18000384d  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180003852  mov     rdx, rax
0x180003855  lea     rcx, [rsp+110h+var_E0]
0x18000385a  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18000385f  lea     rcx, [rbp+57h+var_D0]; this
0x180003863  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003868  mov     rax, [rsp+110h+var_E0]
0x18000386d  test    rax, rax
0x180003870  jz      short loc_180003877
0x180003872  mov     r9, [rax]
0x180003875  jmp     short loc_18000387A
0x180003877  xor     r9d, r9d
0x18000387a  mov     r8d, edi
0x18000387d  mov     edx, r12d
0x180003880  mov     rcx, [rsi+10h]
0x180003884  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180003889  mov     ebx, eax
0x18000388b  test    eax, eax
0x18000388d  js      short loc_1800038E6
0x18000388f  lea     rcx, [rsp+110h+var_E0]; this
0x180003894  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003899  mov     rax, [rbp+57h+var_C8]
0x18000389d  mov     [rsp+110h+var_F0], rax
0x1800038a2  xor     r9d, r9d
0x1800038a5  mov     r8d, edi
0x1800038a8  mov     rdx, [rbp+57h+var_C0]
0x1800038ac  mov     rcx, rsi
0x1800038af  call    ?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z; TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)
0x1800038b4  test    eax, eax
0x1800038b6  js      loc_1800039D2
0x1800038bc  xor     ecx, ecx
0x1800038be  cmp     ecx, r15d
0x1800038c1  jnb     short loc_1800038CD
0x1800038c3  cmp     [rbp+rcx*4+57h+var_B0], edi
0x1800038c7  jz      short loc_1800038F7
0x1800038c9  inc     ecx
0x1800038cb  jmp     short loc_1800038BE
0x1800038cd  cmp     r15d, 16h
0x1800038d1  jnb     short loc_1800038F7
0x1800038d3  mov     [rbp+r15*4+57h+var_B0], edi
0x1800038d8  inc     r15d
0x1800038db  lea     r13, [rsi+38h]
0x1800038df  jmp     loc_1800036F5
0x1800038e4  mov     ebx, eax
0x1800038e6  lea     rcx, [rsp+110h+var_E0]; this
0x1800038eb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800038f0  mov     eax, ebx
0x1800038f2  jmp     loc_1800039D2
0x1800038f7  mov     edx, 8004131Dh; int
0x1800038fc  mov     r8, r14; struct XmlParserTempString *
0x1800038ff  mov     rcx, rsi; this
0x180003902  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJAEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,XmlParserTempString &)
0x180003907  jmp     loc_1800039D2
0x18000390c  mov     edx, 80041316h
0x180003911  jmp     short loc_1800038FC
0x180003913  mov     edx, eax; int
0x180003915  mov     rcx, rsi; this
0x180003918  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18000391d  jmp     loc_1800039D2
0x180003922  js      short loc_180003913
0x180003924  xor     edi, edi
0x180003926  lea     rbx, [rsi+45Ch]
0x18000392d  xor     r13d, r13d
0x180003930  cmp     edi, 16h
0x180003933  jnb     short loc_180003996
0x180003935  lea     rbx, [rsi+45Ch]
0x18000393c  mov     edx, r12d
0x18000393f  mov     rcx, rbx
0x180003942  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180003947  movsxd  rcx, edi
0x18000394a  mov     r14d, [rax+rcx*4+28h]
0x18000394f  test    r14d, r14d
0x180003952  jz      short loc_180003996
0x180003954  mov     edx, r14d
0x180003957  mov     rcx, rbx
0x18000395a  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18000395f  cmp     dword ptr [rax+18h], 2
0x180003963  jnz     short loc_180003996
0x180003965  cmp     [rax+20h], r13d
0x180003969  jz      short loc_180003980
0x18000396b  mov     ecx, r13d
0x18000396e  cmp     ecx, r15d
0x180003971  jnb     short loc_180003984
0x180003973  mov     eax, ecx
0x180003975  cmp     [rbp+rax*4+57h+var_B0], r14d
0x18000397a  jz      short loc_180003980
0x18000397c  inc     ecx
0x18000397e  jmp     short loc_18000396E
0x180003980  inc     edi
0x180003982  jmp     short loc_180003930
0x180003984  mov     r8d, r14d
0x180003987  mov     edx, 80041319h
0x18000398c  mov     rcx, rsi
0x18000398f  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x180003994  jmp     short loc_1800039D2
0x180003996  cmp     [rsi+28h], r13b
0x18000399a  jz      short loc_1800039D0
0x18000399c  cmp     r12d, 1
0x1800039a0  jz      short loc_1800039D0
0x1800039a2  test    r15d, r15d
0x1800039a5  jnz     short loc_1800039D0
0x1800039a7  mov     edx, r12d
0x1800039aa  mov     rcx, rbx
0x1800039ad  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x1800039b2  cmp     [rax+1Ch], r13d
0x1800039b6  jnz     short loc_1800039D0
0x1800039b8  mov     edx, r12d
0x1800039bb  mov     rcx, [rsi+10h]
0x1800039bf  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x1800039c4  mov     ecx, r13d
0x1800039c7  test    eax, eax
0x1800039c9  cmovs   ecx, eax
0x1800039cc  mov     eax, ecx
0x1800039ce  jmp     short loc_1800039D2
0x1800039d0  xor     eax, eax
0x1800039d2  mov     rcx, [rbp+57h+var_50]
0x1800039d6  xor     rcx, rsp; StackCookie
0x1800039d9  call    __security_check_cookie
0x1800039de  add     rsp, 0D8h
0x1800039e5  pop     r15
0x1800039e7  pop     r14
0x1800039e9  pop     r13
0x1800039eb  pop     r12
0x1800039ed  pop     rdi
0x1800039ee  pop     rsi
0x1800039ef  pop     rbx
0x1800039f0  pop     rbp
0x1800039f1  retn
```
