# TaskXmlReader::LoadRawValue(XmlParserTempString &)

- ea: `0x180017860`
- end: `0x1800180ea`
- name: `?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z`
- size: `2186`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this, struct XmlParserTempString *)`
- caller_count: `10`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015f60`
- `0x1800192f0`
- `0x180032908`
- `0x180034310`
- `0x180034d98`
- `0x180038e58`
- `0x18004b588`
- `0x18004b600`
- `0x18004b8e8`
- `0x18004b93c`

## callees

- `0x180017860`
- `0x1800180f0`
- `0x18001a170`
- `0x1800226d0`
- `0x180028a80`
- `0x180038404`
- `0x18003843c`
- `0x18003b51c`
- `0x18004e90f`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180017e66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001802f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180017e66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001802f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017e9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018067`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017e9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018067`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017e84`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001804d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017e84`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001804d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180017ce9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180017ce9`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180017d25`
- `OLEAUT32!__imp_SysFreeString` at `0x180017d95`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f70`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180c7`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180017d25`
- `OLEAUT32!__imp_SysFreeString` at `0x180017d95`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f70`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180c7`

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
            if ( v11 == dword_18007A870[2 * i] )
            {
              v43 = dword_18007A874[2 * i];
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
            if ( v11 == dword_180073890[4 * j] )
              break;
          }
          v45 = (&off_180073898)[2 * j];
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
            if ( v30 == dword_18007A870[2 * m] )
            {
              v49 = dword_18007A874[2 * m];
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
            if ( v30 == dword_180073890[4 * n] )
              break;
          }
          v51 = (&off_180073898)[2 * n];
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
    v59 = &qword_180077320;
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
0x180017860  mov     [rsp-8+arg_10], rbx
0x180017865  push    rbp
0x180017866  push    rsi
0x180017867  push    rdi
0x180017868  push    r12
0x18001786a  push    r13
0x18001786c  push    r14
0x18001786e  push    r15
0x180017870  lea     rbp, [rsp-5B0h]
0x180017878  sub     rsp, 6B0h
0x18001787f  mov     rax, cs:__security_cookie
0x180017886  xor     rax, rsp
0x180017889  mov     [rbp+5E0h+var_40], rax
0x180017890  mov     rbx, rdx
0x180017893  mov     r14, rcx
0x180017896  test    byte ptr [rdx+412h], 1
0x18001789d  jnz     loc_180017D91
0x1800178a3  xor     ecx, ecx
0x1800178a5  mov     [rbx], ecx
0x1800178a7  mov     [rbx+8], rcx
0x1800178ab  and     byte ptr [rbx+412h], 0FCh
0x1800178b2  lea     r13, [rbx+10h]
0x1800178b6  mov     [r13+0], cx
0x1800178bb  mov     [rsp+6E0h+var_6AC], ecx
0x1800178bf  lea     rsi, [r14+38h]
0x1800178c3  mov     rcx, [rsi]
0x1800178c6  test    rcx, rcx
0x1800178c9  jz      loc_180017DA0
0x1800178cf  mov     rax, [rcx]
0x1800178d2  lea     rdx, [rsp+6E0h+var_6AC]
0x1800178d7  mov     rax, [rax+38h]
0x1800178db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178e0  test    eax, eax
0x1800178e2  js      loc_180017D2D
0x1800178e8  xor     r12b, r12b
0x1800178eb  mov     ecx, [rsp+6E0h+var_6AC]
0x1800178ef  test    ecx, ecx
0x1800178f1  jz      loc_180017DB6
0x1800178f7  cmp     ecx, 1
0x1800178fa  jz      loc_180017BDD
0x180017900  mov     byte ptr [r14+458h], 0
0x180017908  test    r12b, r12b
0x18001790b  jz      loc_180017996
0x180017911  mov     rcx, [rsi]
0x180017914  test    rcx, rcx
0x180017917  jz      loc_180017EFA
0x18001791d  mov     rax, [rcx]
0x180017920  lea     rdx, [rsp+6E0h+var_6AC]
0x180017925  mov     rax, [rax+30h]
0x180017929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001792e  mov     r15d, eax
0x180017931  test    eax, eax
0x180017933  jns     short loc_180017986
0x180017935  cmp     eax, 0C00CEE00h
0x18001793a  jge     loc_180017E04
0x180017940  xor     eax, eax
0x180017942  mov     [rsp+6E0h+var_6B8], eax; unsigned int
0x180017946  mov     [rsp+6E0h+var_6C0], rax; unsigned __int16 *
0x18001794b  mov     edx, r15d; int
0x18001794e  xor     r9d, r9d; unsigned int
0x180017951  xor     r8d, r8d; unsigned __int16 *
0x180017954  mov     rcx, r14; this
0x180017957  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x18001795c  mov     rcx, [rbp+5E0h+var_40]
0x180017963  xor     rcx, rsp; StackCookie
0x180017966  call    __security_check_cookie
0x18001796b  mov     rbx, [rsp+6E0h+arg_10]
0x180017973  add     rsp, 6B0h
0x18001797a  pop     r15
0x18001797c  pop     r14
0x18001797e  pop     r13
0x180017980  pop     r12
0x180017982  pop     rdi
0x180017983  pop     rsi
0x180017984  pop     rbp
0x180017985  retn
0x180017986  mov     ecx, [rsp+6E0h+var_6AC]
0x18001798a  lea     eax, [rcx-3]
0x18001798d  cmp     eax, 1
0x180017990  ja      loc_180017DC3
0x180017996  mov     r15b, 1
0x180017999  mov     [rsp+6E0h+var_6B0], r15b
0x18001799e  movzx   edx, [rbp+5E0h+var_24E]
0x1800179a5  and     dl, 0FCh; struct IErrorInfo *
0x1800179a8  mov     [rbp+5E0h+var_24E], dl
0x1800179ae  xor     r8d, r8d
0x1800179b1  mov     dword ptr [rbp+5E0h+var_660], r8d
0x1800179b5  mov     [rbp+5E0h+bstrString], r8
0x1800179b9  mov     [rbp+5E0h+var_650], r8w
0x1800179be  mov     rcx, [rsi]
0x1800179c1  test    rcx, rcx
0x1800179c4  jz      loc_1800180DF
0x1800179ca  mov     rax, [rcx]
0x1800179cd  mov     dword ptr [rbp+5E0h+var_660], r8d
0x1800179d1  mov     [rbp+5E0h+bstrString], r8
0x1800179d5  and     dl, 0FCh
0x1800179d8  mov     [rbp+5E0h+var_24E], dl
0x1800179de  mov     [rbp+5E0h+var_650], r8w
0x1800179e3  lea     r8, [rbp+5E0h+var_660]
0x1800179e7  lea     rdx, [rbp+5E0h+bstrString]
0x1800179eb  mov     rax, [rax+80h]
0x1800179f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179f7  test    eax, eax
0x1800179f9  js      loc_180017C61
0x1800179ff  mov     r8d, dword ptr [rbp+5E0h+var_660]
0x180017a03  test    r15b, r15b
0x180017a06  jz      short loc_180017A53
0x180017a08  test    r8d, r8d
0x180017a0b  jz      loc_180017B31
0x180017a11  cmp     [rbp+5E0h+bstrString], 0
0x180017a16  jz      short loc_180017A53
0x180017a18  movzx   eax, [rbp+5E0h+var_24E]
0x180017a1f  test    al, 1
0x180017a21  jnz     loc_180017CB8
0x180017a27  test    al, 2
0x180017a29  jnz     loc_180017CB8
0x180017a2f  xor     edx, edx
0x180017a31  test    r8d, r8d
0x180017a34  jnz     loc_180017C89
0x180017a3a  sub     r8d, edx
0x180017a3d  mov     dword ptr [rbp+5E0h+var_660], r8d
0x180017a41  jz      loc_180017C0B
0x180017a47  mov     rax, [rbp+5E0h+bstrString]
0x180017a4b  lea     rcx, [rax+rdx*2]
0x180017a4f  mov     [rbp+5E0h+bstrString], rcx
0x180017a53  test    r8d, r8d
0x180017a56  jz      loc_180017B31
0x180017a5c  movzx   edx, byte ptr [rbx+412h]
0x180017a63  test    dl, 1
0x180017a66  jnz     loc_180017CE2
0x180017a6c  mov     ecx, [rbx]
0x180017a6e  lea     eax, [r8+rcx]
0x180017a72  cmp     eax, 200h
0x180017a77  jnb     loc_180017CE2
0x180017a7d  test    ecx, ecx
0x180017a7f  jnz     loc_180017F05
0x180017a85  mov     edx, 200h
0x180017a8a  mov     rax, r13
0x180017a8d  cmp     word ptr [rax], 0
0x180017a91  jnz     loc_180017BCA
0x180017a97  xor     eax, eax
0x180017a99  mov     r15d, 80070057h
0x180017a9f  test    rdx, rdx
0x180017aa2  cmovnz  r15d, eax
0x180017aa6  jz      loc_180017CD1
0x180017aac  mov     ecx, r8d
0x180017aaf  cmp     rcx, 7FFFFFFEh
0x180017ab6  ja      loc_180017CCB
0x180017abc  mov     r9, [rbp+5E0h+bstrString]
0x180017ac0  mov     eax, 200h
0x180017ac5  sub     rax, rdx
0x180017ac8  lea     r8, ds:0[rax*2]
0x180017ad0  add     r8, r13
0x180017ad3  test    rcx, rcx
0x180017ad6  jz      short loc_180017AF6
0x180017ad8  movzx   eax, word ptr [r9]
0x180017adc  test    ax, ax
0x180017adf  jz      short loc_180017AF6
0x180017ae1  add     r9, 2
0x180017ae5  mov     [r8], ax
0x180017ae9  add     r8, 2
0x180017aed  dec     rcx
0x180017af0  sub     rdx, 1; struct IErrorInfo *
0x180017af4  jnz     short loc_180017AD3
0x180017af6  xor     eax, eax
0x180017af8  mov     r15d, 8007007Ah
0x180017afe  test    rdx, rdx
0x180017b01  cmovnz  r15d, eax
0x180017b05  lea     rcx, [r8-2]
0x180017b09  cmovnz  rcx, r8
0x180017b0d  mov     [rcx], ax
0x180017b10  jz      loc_180017CD1
0x180017b16  mov     eax, dword ptr [rbp+5E0h+var_660]
0x180017b19  add     [rbx], eax
0x180017b1b  or      byte ptr [rbx+412h], 2
0x180017b22  mov     rax, r13
0x180017b25  lea     rcx, [rbx+8]
0x180017b29  mov     [rcx], rax
0x180017b2c  mov     [rsp+6E0h+var_6B0], 0
0x180017b31  test    r12b, r12b
0x180017b34  jz      short loc_180017BA7
0x180017b36  mov     rcx, [rsi]
0x180017b39  test    rcx, rcx
0x180017b3c  jz      loc_1800180D4
0x180017b42  mov     rax, [rcx]
0x180017b45  lea     rdx, [rsp+6E0h+var_6AC]
0x180017b4a  mov     rax, [rax+30h]
0x180017b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b53  mov     r15d, eax
0x180017b56  test    eax, eax
0x180017b58  jns     short loc_180017B97
0x180017b5a  cmp     eax, 0C00CEE00h
0x180017b5f  jge     loc_180017FCD
0x180017b65  xor     eax, eax
0x180017b67  mov     [rsp+6E0h+var_6B8], eax; unsigned int
0x180017b6b  mov     [rsp+6E0h+var_6C0], rax; unsigned __int16 *
0x180017b70  mov     edx, r15d; int
0x180017b73  xor     r9d, r9d; unsigned int
0x180017b76  xor     r8d, r8d; unsigned __int16 *
0x180017b79  mov     rcx, r14; this
0x180017b7c  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180017b81  mov     ebx, eax
0x180017b83  test    [rbp+5E0h+var_24E], 1
0x180017b8a  jnz     loc_1800180C3
0x180017b90  mov     eax, ebx
0x180017b92  jmp     loc_18001795C
0x180017b97  mov     ecx, [rsp+6E0h+var_6AC]
0x180017b9b  cmp     ecx, 0Fh
0x180017b9e  jnz     loc_180017F49
0x180017ba4  xor     r12b, r12b
0x180017ba7  test    [rbp+5E0h+var_24E], 1
0x180017bae  jnz     loc_180017F6C
0x180017bb4  test    r12b, r12b
0x180017bb7  jnz     loc_180017C56
0x180017bbd  mov     eax, [rbx]
0x180017bbf  test    eax, eax
0x180017bc1  jnz     short loc_180017C18
0x180017bc3  xor     eax, eax
0x180017bc5  jmp     loc_18001795C
0x180017bca  add     rax, 2
0x180017bce  sub     rdx, 1
0x180017bd2  jnz     loc_180017A8D
0x180017bd8  jmp     loc_180017A97
0x180017bdd  mov     rcx, [rsi]
0x180017be0  test    rcx, rcx
0x180017be3  jz      loc_180017DAB
0x180017be9  mov     rax, [rcx]
0x180017bec  mov     rax, [rax+0A0h]
0x180017bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bf8  test    eax, eax
0x180017bfa  jnz     short loc_180017BC3
0x180017bfc  mov     r12b, 1
0x180017bff  mov     [r14+458h], al
0x180017c06  jmp     loc_180017911
0x180017c0b  mov     [rbp+5E0h+bstrString], 0
0x180017c13  jmp     loc_180017A53
0x180017c18  cmp     qword ptr [rbx+8], 0
0x180017c1d  jz      short loc_180017BC3
0x180017c1f  lea     edx, [rax-1]
0x180017c22  mov     rax, [rbx+8]
0x180017c26  lea     r8, [rax+rdx*2]
0x180017c2a  movzx   eax, word ptr [r8]
0x180017c2e  cmp     eax, 20h ; ' '
0x180017c31  ja      short loc_180017BC3
0x180017c33  mov     rcx, 100002600h
0x180017c3d  bt      rcx, rax
0x180017c41  jnb     short loc_180017BC3
0x180017c43  mov     [rbx], edx
0x180017c45  xor     eax, eax
0x180017c47  mov     [r8], ax
0x180017c4b  mov     eax, [rbx]
0x180017c4d  test    eax, eax
0x180017c4f  jnz     short loc_180017C1F
0x180017c51  jmp     loc_180017BC3
0x180017c56  movzx   r15d, [rsp+6E0h+var_6B0]
0x180017c5c  jmp     loc_18001799E
0x180017c61  mov     edx, eax; int
0x180017c63  mov     rcx, r14; this
0x180017c66  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x180017c6b  mov     ebx, eax
0x180017c6d  test    [rbp+5E0h+var_24E], 1
0x180017c74  jz      loc_180017B90
0x180017c7a  mov     rcx, [rbp+5E0h+bstrString]; bstrString
0x180017c7e  call    cs:__imp_SysFreeString
0x180017c84  jmp     loc_180017B90
0x180017c89  mov     rsi, 100002600h
0x180017c93  mov     rax, [rbp+5E0h+bstrString]
0x180017c97  movzx   r9d, word ptr [rax+rdx*2]
0x180017c9c  cmp     r9d, 20h ; ' '
0x180017ca0  ja      short loc_180017CAF
0x180017ca2  bt      rsi, r9
0x180017ca6  jnb     short loc_180017CAF
0x180017ca8  inc     edx
0x180017caa  cmp     edx, r8d
0x180017cad  jb      short loc_180017C93
0x180017caf  lea     rsi, [r14+38h]
0x180017cb3  jmp     loc_180017A3A
0x180017cb8  lea     rcx, [rbp+5E0h+var_660]; this
0x180017cbc  call    ??1XmlParserTempString@@QEAA@XZ; XmlParserTempString::~XmlParserTempString(void)
0x180017cc1  mov     eax, 8000FFFFh
0x180017cc6  jmp     loc_18001795C
0x180017ccb  mov     r15d, 80070057h
0x180017cd1  lea     rcx, [rbp+5E0h+var_660]; this
0x180017cd5  call    ??1XmlParserTempString@@QEAA@XZ; XmlParserTempString::~XmlParserTempString(void)
0x180017cda  mov     eax, r15d
0x180017cdd  jmp     loc_18001795C
0x180017ce2  mov     edx, [rbx]
0x180017ce4  add     edx, r8d; ui
0x180017ce7  xor     ecx, ecx; strIn
0x180017ce9  call    cs:__imp_SysAllocStringLen
0x180017cef  mov     [rsp+6E0h+var_6A8], rax
0x180017cf4  test    rax, rax
0x180017cf7  jz      loc_180017F7B
0x180017cfd  mov     edx, [rbx]
0x180017cff  test    edx, edx
0x180017d01  jz      short loc_180017D3C
0x180017d03  mov     r9d, edx; unsigned __int64
0x180017d06  mov     ecx, dword ptr [rbp+5E0h+var_660]
0x180017d09  inc     ecx
0x180017d0b  add     edx, ecx; unsigned __int64
  ... truncated ...
```
