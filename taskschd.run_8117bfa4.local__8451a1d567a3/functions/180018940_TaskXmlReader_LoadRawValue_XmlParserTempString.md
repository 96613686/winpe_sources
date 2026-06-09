# TaskXmlReader::LoadRawValue(XmlParserTempString &)

- ea: `0x180018940`
- end: `0x180019221`
- name: `?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z`
- size: `2273`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this, struct XmlParserTempString *)`
- caller_count: `11`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800170a0`
- `0x18001a460`
- `0x180033438`
- `0x180035620`
- `0x1800370e8`
- `0x180037c2c`
- `0x18003bf68`
- `0x18004f180`
- `0x18004f1fc`
- `0x18004f508`
- `0x18004f55c`

## callees

- `0x180018940`
- `0x180019228`
- `0x18001b340`
- `0x180024300`
- `0x18002a6f0`
- `0x18003b514`
- `0x18003b74c`
- `0x18003e88c`
- `0x18005260b`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180018f63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001914e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180018f63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001914e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018fa7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019192`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018fa7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019192`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018f87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019172`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018f87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019172`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018dd0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018dd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180018d5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180018e12`
- `OLEAUT32!__imp_SysFreeString` at `0x180018e88`
- `OLEAUT32!__imp_SysFreeString` at `0x18001904d`
- `OLEAUT32!__imp_SysFreeString` at `0x180019085`
- `OLEAUT32!__imp_SysFreeString` at `0x1800191f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180018d5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180018e12`
- `OLEAUT32!__imp_SysFreeString` at `0x180018e88`
- `OLEAUT32!__imp_SysFreeString` at `0x18001904d`
- `OLEAUT32!__imp_SysFreeString` at `0x180019085`
- `OLEAUT32!__imp_SysFreeString` at `0x1800191f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall TaskXmlReader::LoadRawValue(TaskXmlReader *this, BSTR *a2)
{
  OLECHAR *v4; // r13
  __int64 **v5; // rsi
  __int64 v6; // rcx
  int v7; // eax
  struct IErrorInfo *v8; // rdx
  char v9; // r12
  int v10; // eax
  int v11; // r15d
  char v13; // r15
  struct IErrorInfo *v14; // rdx
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // r8d
  char v20; // dl
  _WORD *v21; // rax
  int v22; // r15d
  __int64 v23; // rcx
  BSTR v24; // r9
  OLECHAR *v25; // r8
  OLECHAR v26; // ax
  OLECHAR *v27; // rcx
  BSTR v28; // rax
  int v29; // eax
  int v30; // r15d
  int v31; // eax
  int v32; // ebx
  int v33; // eax
  __int64 v34; // rdx
  OLECHAR *v35; // r8
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rsi
  unsigned __int64 v39; // r9
  OLECHAR *v40; // rax
  __int64 v41; // rax
  __int64 i; // rcx
  UINT v43; // edi
  int StringW; // eax
  WCHAR *v45; // rdi
  unsigned int j; // eax
  __int64 v47; // rax
  __int64 m; // rcx
  UINT v49; // edi
  int v50; // eax
  WCHAR *v51; // rdi
  unsigned int n; // eax
  __int64 v53; // rax
  char k; // [rsp+30h] [rbp-D0h]
  int v55; // [rsp+34h] [rbp-CCh] BYREF
  BSTR v56; // [rsp+38h] [rbp-C8h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  char v58; // [rsp+48h] [rbp-B8h]
  __int64 *v59; // [rsp+50h] [rbp-B0h]
  __int64 v60; // [rsp+58h] [rbp-A8h]
  __int64 v61; // [rsp+60h] [rbp-A0h]
  int v62; // [rsp+68h] [rbp-98h]
  __int64 v63; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  __int16 v66; // [rsp+90h] [rbp-70h]
  unsigned __int8 v67; // [rsp+492h] [rbp+392h]
  WCHAR Buffer[256]; // [rsp+4A0h] [rbp+3A0h] BYREF

  if ( (*((_BYTE *)a2 + 1042) & 1) != 0 )
    SysFreeString(a2[1]);
  *(_DWORD *)a2 = 0;
  a2[1] = 0;
  *((_BYTE *)a2 + 1042) &= 0xFCu;
  v4 = (OLECHAR *)(a2 + 2);
  *((_WORD *)a2 + 8) = 0;
  v55 = 0;
  v5 = (__int64 **)((char *)this + 56);
  v6 = *((_QWORD *)this + 7);
  if ( !v6 )
    _com_raise_error(-2147467261, (struct IErrorInfo *)a2);
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 56LL))(v6, &v55);
  if ( v7 < 0 )
    return TaskXmlReader::SetErrorInfoXmlLite(this, v7);
  v9 = 0;
  if ( v55 )
  {
    if ( v55 == 1 )
    {
      if ( !*v5 )
        _com_raise_error(-2147467261, v8);
      if ( (*(unsigned int (__fastcall **)(__int64 *))(**v5 + 160))(*v5) )
        return 0;
      v9 = 1;
      *((_BYTE *)this + 1112) = 0;
      while ( 1 )
      {
LABEL_8:
        if ( !*v5 )
          _com_raise_error(-2147467261, v8);
        v10 = (*(__int64 (__fastcall **)(__int64 *, int *))(**v5 + 48))(*v5, &v55);
        v11 = v10;
        if ( v10 < 0 )
        {
          if ( v10 < -1072894464 || v10 > -1072893953 )
            return TaskXmlReader::SetErrorInfo(this, v10, 0, 0, 0, 0);
          memset_0(Buffer, 0, sizeof(Buffer));
          for ( i = 0; (unsigned int)i < 0x3C; i = (unsigned int)(i + 1) )
          {
            if ( v11 == dword_18007E850[2 * i] )
            {
              v43 = dword_18007E854[2 * i];
              v56 = 0;
              if ( GetModuleHandleExW(4u, &_ImageBase, (HMODULE *)&v56) )
              {
                StringW = LoadStringW((HINSTANCE)v56, v43, Buffer, 256);
                v45 = Buffer;
                if ( !StringW )
                  v45 = 0;
                FreeLibrary((HMODULE)v56);
                if ( v45 )
                {
LABEL_108:
                  v47 = -1;
                  do
                    ++v47;
                  while ( v45[v47] );
                  return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v45, v47);
                }
              }
              break;
            }
          }
          for ( j = 0; ; ++j )
          {
            if ( j >= 0x3C )
            {
              v45 = 0;
              goto LABEL_112;
            }
            if ( v11 == dword_180077870[4 * j] )
              break;
          }
          v45 = (&off_180077878)[2 * j];
          if ( v45 )
            goto LABEL_108;
LABEL_112:
          LODWORD(v47) = 0;
          return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v45, v47);
        }
        if ( (unsigned int)(v55 - 3) <= 1 )
          goto LABEL_13;
        if ( v55 == 15 )
          return 0;
        if ( v55 == 1 )
        {
          v41 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((char *)this + 56);
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v41 + 160LL))(v41) )
            return -2147216618;
        }
      }
    }
  }
  else
  {
    v9 = *((_BYTE *)this + 1112);
  }
  *((_BYTE *)this + 1112) = 0;
  if ( v9 )
    goto LABEL_8;
LABEL_13:
  v13 = 1;
  for ( k = 1; ; v13 = k )
  {
    v14 = (struct IErrorInfo *)v67;
    LOBYTE(v14) = v67 & 0xFC;
    v67 &= 0xFCu;
    LODWORD(v64) = 0;
    bstrString = 0;
    v66 = 0;
    v15 = *v5;
    if ( !*v5 )
      _com_raise_error(-2147467261, v14);
    v16 = *v15;
    LODWORD(v64) = 0;
    bstrString = 0;
    v67 = (unsigned __int8)v14 & 0xFC;
    v66 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64 *, BSTR *, unsigned __int64 *))(v16 + 128))(v15, &bstrString, &v64);
    if ( v17 < 0 )
    {
      v32 = TaskXmlReader::SetErrorInfoXmlLite(this, v17);
      if ( (v67 & 1) != 0 )
        SysFreeString(bstrString);
      return v32;
    }
    v19 = v64;
    if ( v13 )
    {
      if ( !(_DWORD)v64 )
        goto LABEL_43;
      if ( bstrString )
      {
        if ( (v67 & 1) != 0 || (v67 & 2) != 0 )
        {
          XmlParserTempString::~XmlParserTempString((XmlParserTempString *)&v64);
          return -2147418113;
        }
        v18 = 0;
        v38 = 0x100002600LL;
        do
        {
          v39 = bstrString[v18];
          if ( (unsigned int)v39 > 0x20 )
            break;
          if ( !_bittest64(&v38, v39) )
            break;
          v18 = (unsigned int)(v18 + 1);
        }
        while ( (unsigned int)v18 < (unsigned int)v64 );
        v5 = (__int64 **)((char *)this + 56);
        v19 = v64 - v18;
        LODWORD(v64) = v19;
        if ( v19 )
          bstrString += v18;
        else
          bstrString = 0;
      }
    }
    if ( v19 )
      break;
LABEL_43:
    if ( v9 )
    {
      if ( !*v5 )
        _com_raise_error(-2147467261, (struct IErrorInfo *)v18);
      v29 = (*(__int64 (__fastcall **)(__int64 *, int *))(**v5 + 48))(*v5, &v55);
      v30 = v29;
      if ( v29 < 0 )
      {
        if ( v29 < -1072894464 || v29 > -1072893953 )
        {
          v31 = TaskXmlReader::SetErrorInfo(this, v29, 0, 0, 0, 0);
        }
        else
        {
          memset_0(Buffer, 0, sizeof(Buffer));
          for ( m = 0; (unsigned int)m < 0x3C; m = (unsigned int)(m + 1) )
          {
            if ( v30 == dword_18007E850[2 * m] )
            {
              v49 = dword_18007E854[2 * m];
              v56 = 0;
              if ( GetModuleHandleExW(4u, &_ImageBase, (HMODULE *)&v56) )
              {
                v50 = LoadStringW((HINSTANCE)v56, v49, Buffer, 256);
                v51 = Buffer;
                if ( !v50 )
                  v51 = 0;
                FreeLibrary((HMODULE)v56);
                if ( v51 )
                {
LABEL_136:
                  v53 = -1;
                  do
                    ++v53;
                  while ( v51[v53] );
                  goto LABEL_141;
                }
              }
              break;
            }
          }
          for ( n = 0; ; ++n )
          {
            if ( n >= 0x3C )
            {
              v51 = 0;
              goto LABEL_140;
            }
            if ( v30 == dword_180077870[4 * n] )
              break;
          }
          v51 = (&off_180077878)[2 * n];
          if ( v51 )
            goto LABEL_136;
LABEL_140:
          LODWORD(v53) = 0;
LABEL_141:
          v31 = TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v51, v53);
        }
        v32 = v31;
        if ( (v67 & 1) != 0 )
        {
          SysFreeString(bstrString);
          return v32;
        }
        return v32;
      }
      if ( v55 == 15 )
      {
        v9 = 0;
      }
      else if ( (unsigned int)(v55 - 3) > 1 && v55 != 13 )
      {
        XmlParserTempString::~XmlParserTempString((XmlParserTempString *)&v64);
        return -2147216618;
      }
    }
    if ( (v67 & 1) != 0 )
      SysFreeString(bstrString);
    if ( !v9 )
    {
      v33 = *(_DWORD *)a2;
      if ( *(_DWORD *)a2 && a2[1] )
      {
        do
        {
          v34 = (unsigned int)(v33 - 1);
          v35 = &a2[1][v34];
          v36 = *v35;
          if ( (unsigned int)v36 > 0x20 )
            break;
          v37 = 0x100002600LL;
          if ( !_bittest64(&v37, v36) )
            break;
          *(_DWORD *)a2 = v34;
          *v35 = 0;
          v33 = *(_DWORD *)a2;
        }
        while ( *(_DWORD *)a2 );
      }
      return 0;
    }
  }
  v20 = *((_BYTE *)a2 + 1042);
  if ( (v20 & 1) == 0 && v19 + *(_DWORD *)a2 < 0x200 )
  {
    if ( *(_DWORD *)a2 && (v20 & 2) == 0 )
    {
      v22 = StringCchCopyNW((unsigned __int16 *)a2 + 8, 0x200u, a2[1], *(unsigned int *)a2);
      if ( v22 < 0 )
        goto LABEL_77;
      a2[1] = v4;
      v19 = v64;
    }
    v18 = 512;
    v21 = a2 + 2;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v18;
    }
    while ( v18 );
    v22 = -2147024809;
    if ( !v18 )
      goto LABEL_77;
    v23 = v19;
    if ( v19 > 0x7FFFFFFEuLL )
    {
      v22 = -2147024809;
      goto LABEL_77;
    }
    v24 = bstrString;
    v25 = &v4[512 - v18];
    do
    {
      if ( !v23 )
        break;
      v26 = *v24;
      if ( !*v24 )
        break;
      ++v24;
      *v25++ = v26;
      --v23;
      --v18;
    }
    while ( v18 );
    v22 = -2147024774;
    if ( v18 )
      v22 = 0;
    v27 = v25 - 1;
    if ( v18 )
      v27 = v25;
    *v27 = 0;
    if ( !v18 )
      goto LABEL_77;
    *(_DWORD *)a2 += v64;
    *((_BYTE *)a2 + 1042) |= 2u;
    v28 = (BSTR)(a2 + 2);
    goto LABEL_42;
  }
  v40 = SysAllocStringLen(0, v19 + *(_DWORD *)a2);
  v56 = v40;
  if ( !v40 )
  {
    v58 = 0;
    v59 = &qword_18007B2F0;
    v60 = 0;
    v61 = 0;
    v62 = 14;
    v63 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( !*(_DWORD *)a2
    || (v22 = StringCchCopyNW(v40, (unsigned int)(v64 + 1 + *(_DWORD *)a2), a2[1], *(unsigned int *)a2), v22 >= 0) )
  {
    v22 = StringCchCopyNW(&v56[*(unsigned int *)a2], (unsigned int)(v64 + 1), bstrString, (unsigned int)v64);
    if ( v22 >= 0 )
    {
      if ( (*((_BYTE *)a2 + 1042) & 1) != 0 )
        SysFreeString(a2[1]);
      *v4 = 0;
      *(_DWORD *)a2 += v64;
      *((_BYTE *)a2 + 1042) &= ~2u;
      *((_BYTE *)a2 + 1042) |= 1u;
      v28 = v56;
LABEL_42:
      a2[1] = v28;
      k = 0;
      goto LABEL_43;
    }
  }
  SysFreeString(v56);
LABEL_77:
  XmlParserTempString::~XmlParserTempString((XmlParserTempString *)&v64);
  return v22;
}

```

## disassembly

```asm
0x180018940  mov     [rsp-8+arg_10], rbx
0x180018945  push    rbp
0x180018946  push    rsi
0x180018947  push    rdi
0x180018948  push    r12
0x18001894a  push    r13
0x18001894c  push    r14
0x18001894e  push    r15
0x180018950  lea     rbp, [rsp-5B0h]
0x180018958  sub     rsp, 6B0h
0x18001895f  mov     rax, cs:__security_cookie
0x180018966  xor     rax, rsp
0x180018969  mov     [rbp+5E0h+var_40], rax
0x180018970  mov     rbx, rdx
0x180018973  mov     r14, rcx
0x180018976  test    byte ptr [rdx+412h], 1
0x18001897d  jnz     loc_180018E84
0x180018983  xor     ecx, ecx
0x180018985  mov     [rbx], ecx
0x180018987  mov     [rbx+8], rcx
0x18001898b  and     byte ptr [rbx+412h], 0FCh
0x180018992  lea     r13, [rbx+10h]
0x180018996  mov     [r13+0], cx
0x18001899b  mov     [rsp+6E0h+var_6AC], ecx
0x18001899f  lea     rsi, [r14+38h]
0x1800189a3  mov     rcx, [rsi]
0x1800189a6  test    rcx, rcx
0x1800189a9  jz      loc_180018E99
0x1800189af  mov     rax, [rcx]
0x1800189b2  lea     rdx, [rsp+6E0h+var_6AC]
0x1800189b7  mov     rax, [rax+38h]
0x1800189bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c0  test    eax, eax
0x1800189c2  js      loc_180018E20
0x1800189c8  xor     r12b, r12b
0x1800189cb  mov     ecx, [rsp+6E0h+var_6AC]
0x1800189cf  test    ecx, ecx
0x1800189d1  jz      loc_180018EAF
0x1800189d7  cmp     ecx, 1
0x1800189da  jz      loc_180018CBE
0x1800189e0  mov     byte ptr [r14+458h], 0
0x1800189e8  test    r12b, r12b
0x1800189eb  jz      loc_180018A77
0x1800189f1  mov     rcx, [rsi]
0x1800189f4  test    rcx, rcx
0x1800189f7  jz      loc_180019009
0x1800189fd  mov     rax, [rcx]
0x180018a00  lea     rdx, [rsp+6E0h+var_6AC]
0x180018a05  mov     rax, [rax+30h]
0x180018a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a0e  mov     r15d, eax
0x180018a11  test    eax, eax
0x180018a13  jns     short loc_180018A67
0x180018a15  cmp     eax, 0C00CEE00h
0x180018a1a  jge     loc_180018EFD
0x180018a20  xor     eax, eax
0x180018a22  mov     [rsp+6E0h+var_6B8], eax; unsigned int
0x180018a26  mov     [rsp+6E0h+var_6C0], rax; unsigned __int16 *
0x180018a2b  mov     edx, r15d; int
0x180018a2e  xor     r9d, r9d; unsigned int
0x180018a31  xor     r8d, r8d; unsigned __int16 *
0x180018a34  mov     rcx, r14; this
0x180018a37  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180018a3c  mov     rcx, [rbp+5E0h+var_40]
0x180018a43  xor     rcx, rsp; StackCookie
0x180018a46  call    __security_check_cookie
0x180018a4b  mov     rbx, [rsp+6E0h+arg_10]
0x180018a53  add     rsp, 6B0h
0x180018a5a  pop     r15
0x180018a5c  pop     r14
0x180018a5e  pop     r13
0x180018a60  pop     r12
0x180018a62  pop     rdi
0x180018a63  pop     rsi
0x180018a64  pop     rbp
0x180018a65  retn
0x180018a67  mov     ecx, [rsp+6E0h+var_6AC]
0x180018a6b  lea     eax, [rcx-3]
0x180018a6e  cmp     eax, 1
0x180018a71  ja      loc_180018EBC
0x180018a77  mov     r15b, 1
0x180018a7a  mov     [rsp+6E0h+var_6B0], r15b
0x180018a7f  movzx   edx, [rbp+5E0h+var_24E]
0x180018a86  and     dl, 0FCh; struct IErrorInfo *
0x180018a89  mov     [rbp+5E0h+var_24E], dl
0x180018a8f  xor     r8d, r8d
0x180018a92  mov     dword ptr [rbp+5E0h+var_660], r8d
0x180018a96  mov     [rbp+5E0h+bstrString], r8
0x180018a9a  mov     [rbp+5E0h+var_650], r8w
0x180018a9f  mov     rcx, [rsi]
0x180018aa2  test    rcx, rcx
0x180018aa5  jz      loc_180019216
0x180018aab  mov     rax, [rcx]
0x180018aae  mov     dword ptr [rbp+5E0h+var_660], r8d
0x180018ab2  mov     [rbp+5E0h+bstrString], r8
0x180018ab6  and     dl, 0FCh
0x180018ab9  mov     [rbp+5E0h+var_24E], dl
0x180018abf  mov     [rbp+5E0h+var_650], r8w
0x180018ac4  lea     r8, [rbp+5E0h+var_660]
0x180018ac8  lea     rdx, [rbp+5E0h+bstrString]
0x180018acc  mov     rax, [rax+80h]
0x180018ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ad8  test    eax, eax
0x180018ada  js      loc_180018D42
0x180018ae0  mov     r8d, dword ptr [rbp+5E0h+var_660]
0x180018ae4  test    r15b, r15b
0x180018ae7  jz      short loc_180018B34
0x180018ae9  test    r8d, r8d
0x180018aec  jz      loc_180018C12
0x180018af2  cmp     [rbp+5E0h+bstrString], 0
0x180018af7  jz      short loc_180018B34
0x180018af9  movzx   eax, [rbp+5E0h+var_24E]
0x180018b00  test    al, 1
0x180018b02  jnz     loc_180018D9F
0x180018b08  test    al, 2
0x180018b0a  jnz     loc_180018D9F
0x180018b10  xor     edx, edx
0x180018b12  test    r8d, r8d
0x180018b15  jnz     loc_180018D70
0x180018b1b  sub     r8d, edx
0x180018b1e  mov     dword ptr [rbp+5E0h+var_660], r8d
0x180018b22  jz      loc_180018CEC
0x180018b28  mov     rax, [rbp+5E0h+bstrString]
0x180018b2c  lea     rcx, [rax+rdx*2]
0x180018b30  mov     [rbp+5E0h+bstrString], rcx
0x180018b34  test    r8d, r8d
0x180018b37  jz      loc_180018C12
0x180018b3d  movzx   edx, byte ptr [rbx+412h]
0x180018b44  test    dl, 1
0x180018b47  jnz     loc_180018DC9
0x180018b4d  mov     ecx, [rbx]
0x180018b4f  lea     eax, [r8+rcx]
0x180018b53  cmp     eax, 200h
0x180018b58  jnb     loc_180018DC9
0x180018b5e  test    ecx, ecx
0x180018b60  jnz     loc_180019014
0x180018b66  mov     edx, 200h
0x180018b6b  mov     rax, r13
0x180018b6e  cmp     word ptr [rax], 0
0x180018b72  jnz     loc_180018CAB
0x180018b78  xor     eax, eax
0x180018b7a  mov     r15d, 80070057h
0x180018b80  test    rdx, rdx
0x180018b83  cmovnz  r15d, eax
0x180018b87  jz      loc_180018DB8
0x180018b8d  mov     ecx, r8d
0x180018b90  cmp     rcx, 7FFFFFFEh
0x180018b97  ja      loc_180018DB2
0x180018b9d  mov     r9, [rbp+5E0h+bstrString]
0x180018ba1  mov     eax, 200h
0x180018ba6  sub     rax, rdx
0x180018ba9  lea     r8, ds:0[rax*2]
0x180018bb1  add     r8, r13
0x180018bb4  test    rcx, rcx
0x180018bb7  jz      short loc_180018BD7
0x180018bb9  movzx   eax, word ptr [r9]
0x180018bbd  test    ax, ax
0x180018bc0  jz      short loc_180018BD7
0x180018bc2  add     r9, 2
0x180018bc6  mov     [r8], ax
0x180018bca  add     r8, 2
0x180018bce  dec     rcx
0x180018bd1  sub     rdx, 1; struct IErrorInfo *
0x180018bd5  jnz     short loc_180018BB4
0x180018bd7  xor     eax, eax
0x180018bd9  mov     r15d, 8007007Ah
0x180018bdf  test    rdx, rdx
0x180018be2  cmovnz  r15d, eax
0x180018be6  lea     rcx, [r8-2]
0x180018bea  cmovnz  rcx, r8
0x180018bee  mov     [rcx], ax
0x180018bf1  jz      loc_180018DB8
0x180018bf7  mov     eax, dword ptr [rbp+5E0h+var_660]
0x180018bfa  add     [rbx], eax
0x180018bfc  or      byte ptr [rbx+412h], 2
0x180018c03  mov     rax, r13
0x180018c06  lea     rcx, [rbx+8]
0x180018c0a  mov     [rcx], rax
0x180018c0d  mov     [rsp+6E0h+var_6B0], 0
0x180018c12  test    r12b, r12b
0x180018c15  jz      short loc_180018C88
0x180018c17  mov     rcx, [rsi]
0x180018c1a  test    rcx, rcx
0x180018c1d  jz      loc_18001920B
0x180018c23  mov     rax, [rcx]
0x180018c26  lea     rdx, [rsp+6E0h+var_6AC]
0x180018c2b  mov     rax, [rax+30h]
0x180018c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c34  mov     r15d, eax
0x180018c37  test    eax, eax
0x180018c39  jns     short loc_180018C78
0x180018c3b  cmp     eax, 0C00CEE00h
0x180018c40  jge     loc_1800190E8
0x180018c46  xor     eax, eax
0x180018c48  mov     [rsp+6E0h+var_6B8], eax; unsigned int
0x180018c4c  mov     [rsp+6E0h+var_6C0], rax; unsigned __int16 *
0x180018c51  mov     edx, r15d; int
0x180018c54  xor     r9d, r9d; unsigned int
0x180018c57  xor     r8d, r8d; unsigned __int16 *
0x180018c5a  mov     rcx, r14; this
0x180018c5d  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180018c62  mov     ebx, eax
0x180018c64  test    [rbp+5E0h+var_24E], 1
0x180018c6b  jnz     loc_1800191F4
0x180018c71  mov     eax, ebx
0x180018c73  jmp     loc_180018A3C
0x180018c78  mov     ecx, [rsp+6E0h+var_6AC]
0x180018c7c  cmp     ecx, 0Fh
0x180018c7f  jnz     loc_18001905E
0x180018c85  xor     r12b, r12b
0x180018c88  test    [rbp+5E0h+var_24E], 1
0x180018c8f  jnz     loc_180019081
0x180018c95  test    r12b, r12b
0x180018c98  jnz     loc_180018D37
0x180018c9e  mov     eax, [rbx]
0x180018ca0  test    eax, eax
0x180018ca2  jnz     short loc_180018CF9
0x180018ca4  xor     eax, eax
0x180018ca6  jmp     loc_180018A3C
0x180018cab  add     rax, 2
0x180018caf  sub     rdx, 1
0x180018cb3  jnz     loc_180018B6E
0x180018cb9  jmp     loc_180018B78
0x180018cbe  mov     rcx, [rsi]
0x180018cc1  test    rcx, rcx
0x180018cc4  jz      loc_180018EA4
0x180018cca  mov     rax, [rcx]
0x180018ccd  mov     rax, [rax+0A0h]
0x180018cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cd9  test    eax, eax
0x180018cdb  jnz     short loc_180018CA4
0x180018cdd  mov     r12b, 1
0x180018ce0  mov     [r14+458h], al
0x180018ce7  jmp     loc_1800189F1
0x180018cec  mov     [rbp+5E0h+bstrString], 0
0x180018cf4  jmp     loc_180018B34
0x180018cf9  cmp     qword ptr [rbx+8], 0
0x180018cfe  jz      short loc_180018CA4
0x180018d00  lea     edx, [rax-1]
0x180018d03  mov     rax, [rbx+8]
0x180018d07  lea     r8, [rax+rdx*2]
0x180018d0b  movzx   eax, word ptr [r8]
0x180018d0f  cmp     eax, 20h ; ' '
0x180018d12  ja      short loc_180018CA4
0x180018d14  mov     rcx, 100002600h
0x180018d1e  bt      rcx, rax
0x180018d22  jnb     short loc_180018CA4
0x180018d24  mov     [rbx], edx
0x180018d26  xor     eax, eax
0x180018d28  mov     [r8], ax
0x180018d2c  mov     eax, [rbx]
0x180018d2e  test    eax, eax
0x180018d30  jnz     short loc_180018D00
0x180018d32  jmp     loc_180018CA4
0x180018d37  movzx   r15d, [rsp+6E0h+var_6B0]
0x180018d3d  jmp     loc_180018A7F
0x180018d42  mov     edx, eax; int
0x180018d44  mov     rcx, r14; this
0x180018d47  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x180018d4c  mov     ebx, eax
0x180018d4e  test    [rbp+5E0h+var_24E], 1
0x180018d55  jz      loc_180018C71
0x180018d5b  mov     rcx, [rbp+5E0h+bstrString]; bstrString
0x180018d5f  call    cs:__imp_SysFreeString
0x180018d66  nop     dword ptr [rax+rax+00h]
0x180018d6b  jmp     loc_180018C71
0x180018d70  mov     rsi, 100002600h
0x180018d7a  mov     rax, [rbp+5E0h+bstrString]
0x180018d7e  movzx   r9d, word ptr [rax+rdx*2]
0x180018d83  cmp     r9d, 20h ; ' '
0x180018d87  ja      short loc_180018D96
0x180018d89  bt      rsi, r9
0x180018d8d  jnb     short loc_180018D96
0x180018d8f  inc     edx
0x180018d91  cmp     edx, r8d
0x180018d94  jb      short loc_180018D7A
0x180018d96  lea     rsi, [r14+38h]
0x180018d9a  jmp     loc_180018B1B
0x180018d9f  lea     rcx, [rbp+5E0h+var_660]; this
0x180018da3  call    ??1XmlParserTempString@@QEAA@XZ; XmlParserTempString::~XmlParserTempString(void)
0x180018da8  mov     eax, 8000FFFFh
0x180018dad  jmp     loc_180018A3C
0x180018db2  mov     r15d, 80070057h
0x180018db8  lea     rcx, [rbp+5E0h+var_660]; this
0x180018dbc  call    ??1XmlParserTempString@@QEAA@XZ; XmlParserTempString::~XmlParserTempString(void)
0x180018dc1  mov     eax, r15d
0x180018dc4  jmp     loc_180018A3C
0x180018dc9  mov     edx, [rbx]
0x180018dcb  add     edx, r8d; ui
0x180018dce  xor     ecx, ecx; strIn
0x180018dd0  call    cs:__imp_SysAllocStringLen
0x180018dd7  nop     dword ptr [rax+rax+00h]
0x180018ddc  mov     [rsp+6E0h+var_6A8], rax
0x180018de1  test    rax, rax
0x180018de4  jz      loc_180019096
0x180018dea  mov     edx, [rbx]
0x180018dec  test    edx, edx
0x180018dee  jz      short loc_180018E2F
0x180018df0  mov     r9d, edx; unsigned __int64
0x180018df3  mov     ecx, dword ptr [rbp+5E0h+var_660]
  ... truncated ...
```
