# _anonymous_namespace_::JsonStorageImpl::Enumerate

- ea: `0x140076644`
- end: `0x140076c0c`
- name: `_anonymous_namespace_::JsonStorageImpl::Enumerate`
- size: `1480`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x140076c34`
- `0x140076c74`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x140006338`
- `0x140009858`
- `0x140009c7c`
- `0x14000ccac`
- `0x140060f58`
- `0x14006c78c`
- `0x140074434`
- `0x140074608`
- `0x140075d4c`
- `0x140075d60`
- `0x140076644`
- `0x140078ba0`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140076a42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140076a42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400769be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400769be`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall anonymous_namespace_::JsonStorageImpl::Enumerate(__int64 a1, __int64 a2, char a3)
{
  HSTRING v5; // r14
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // r9
  __int64 v7; // rcx
  int v8; // eax
  HSTRING v9; // rdx
  int v10; // eax
  unsigned int v11; // esi
  char v12; // al
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _QWORD **); // rdi
  _QWORD *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rbx
  _QWORD *v19; // rdi
  int v20; // esi
  __int64 v21; // rdx
  int v22; // r15d
  _QWORD *v23; // rcx
  int v24; // eax
  int v25; // esi
  int v26; // edi
  _QWORD *v27; // rcx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v29; // r8
  _OWORD *v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  _QWORD *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  char v37; // [rsp+20h] [rbp-89h] BYREF
  char v38; // [rsp+21h] [rbp-88h] BYREF
  char v39; // [rsp+22h] [rbp-87h]
  _QWORD *v40; // [rsp+28h] [rbp-81h] BYREF
  unsigned int v41; // [rsp+30h] [rbp-79h]
  HSTRING string; // [rsp+38h] [rbp-71h] BYREF
  __int64 v43; // [rsp+40h] [rbp-69h] BYREF
  _QWORD *v44; // [rsp+48h] [rbp-61h] BYREF
  __int64 v45; // [rsp+50h] [rbp-59h] BYREF
  __int64 v46; // [rsp+58h] [rbp-51h] BYREF
  __int64 v47; // [rsp+60h] [rbp-49h] BYREF
  __int64 v48; // [rsp+68h] [rbp-41h]
  _QWORD *v49; // [rsp+70h] [rbp-39h]
  _QWORD *v50; // [rsp+78h] [rbp-31h]
  _QWORD *v51; // [rsp+80h] [rbp-29h]
  _QWORD v52[3]; // [rsp+88h] [rbp-21h] BYREF
  __int128 pExceptionObject; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v54; // [rsp+B0h] [rbp+7h]

  v39 = a3;
  v41 = 0;
  v5 = (HSTRING)operator new(0x28u);
  string = v5;
  *(_OWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 1;
  *((_DWORD *)v5 + 3) = 1;
  *(_QWORD *)v5 = &std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable';
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  v52[0] = v5 + 4;
  v52[1] = v5;
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*WinRT::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>,Windows::Data::Json::IJsonObject>(
                                                               (__int64 *)&string,
                                                               (_QWORD *)(a1 + 16));
  v7 = 0;
  v45 = 0;
  if ( v6 )
  {
    v8 = (**v6)(v6, &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099, &v45);
    if ( v8 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v8);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    v7 = v45;
  }
  v9 = string;
  if ( string )
  {
    string = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v9 + 16LL))(v9);
    v7 = v45;
  }
  v43 = 0;
  v44 = 0;
  if ( v7 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 48LL))(v7, &v43);
    if ( v10 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v10);
      throw (ErrorCodeException *)&pExceptionObject;
    }
  }
  v11 = 14;
  WinRT::iterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>::end(
    v7,
    &v47);
  while ( 1 )
  {
    v37 = 0;
    if ( v43 )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 56LL))(v43, &v37);
    v12 = 0;
    v38 = 0;
    v13 = v47;
    if ( v47 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v47 + 56LL))(v47, &v38);
      v13 = v47;
      v12 = v38;
    }
    if ( v37 == v12 )
      break;
    v14 = v43;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v43 + 48LL);
    v16 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    }
    v17 = v15(v14, &v44);
    if ( v17 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v17);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    v18 = v44;
    v52[2] = &v46;
    v19 = v44;
    v40 = v44;
    if ( v44 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v44 + 8LL))(v44);
      v19 = v40;
    }
    v50 = &v40;
    v46 = 0;
    v20 = v11 | 0x80;
    v41 = v20;
    v51 = v19;
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 8LL))(v19);
    v49 = v19;
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 8LL))(v19);
    v22 =  Windows::Data::Json::IJsonValue::`vcall'{56,{flat}}(v19, &v46);
    if ( v19 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
    if ( v22 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v22);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    v23 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
    }
    v41 = v20 & 0xFFFFFF7F;
    v11 = v20 & 0xFFFFFF1F | 0x60;
    v24 = WinRT::Call<Windows::Data::Json::IJsonValue,long (Windows::Data::Json::IJsonValue::*)(enum Windows::Data::Json::JsonValueType *),>(
            &v46,
            v21);
    if ( v39 == (v24 == 5) )
    {
      v40 = v18;
      if ( v18 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
        v18 = v40;
      }
      v49 = &v40;
      string = 0;
      v25 = v11 | 0x400;
      v41 = v25;
      v51 = v18;
      if ( v18 )
        (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
      v50 = v18;
      if ( v18 )
        (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
      v26 =  Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Data::Json::IJsonValue *>::`vcall'{48,{flat}}(
              v18,
              &string);
      if ( v18 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
      if ( v26 < 0 )
      {
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v26);
        throw (ErrorCodeException *)&pExceptionObject;
      }
      v27 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
      }
      v41 = v25 & 0xFFFFFBFF;
      v11 = v25 & 0xFFFFF8FF | 0x300;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      pExceptionObject = 0;
      v54 = 0u;
      v29 = -1;
      do
        ++v29;
      while ( StringRawBuffer[v29] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, StringRawBuffer, v29);
      v30 = (_OWORD *)*((_QWORD *)v5 + 3);
      if ( v30 == *((_OWORD **)v5 + 4) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v5 + 4, v30, &pExceptionObject);
      }
      else
      {
        *v30 = pExceptionObject;
        v30[1] = v54;
        *(_QWORD *)&v54 = 0;
        *((_QWORD *)&v54 + 1) = 7;
        LOWORD(pExceptionObject) = 0;
        *((_QWORD *)v5 + 3) += 32LL;
      }
      std::wstring::~wstring((char **)&pExceptionObject);
      if ( string )
        WindowsDeleteString(string);
    }
    v37 = 0;
    v31 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 64LL))(v43, &v37);
    if ( v31 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v31);
      throw (ErrorCodeException *)&pExceptionObject;
    }
  }
  v32 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v13 = v47;
  }
  if ( v13 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v33 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
  }
  v34 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  Collections::Enumerable<std::wstring>::Enumerable<std::wstring>(a2, v52);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(HSTRING))v5)(v5);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v5 + 8LL))(v5);
  }
  return a2;
}

```

## disassembly

```asm
0x140076644  mov     [rsp-8+arg_10], rbx
0x140076649  push    rbp
0x14007664a  push    rsi
0x14007664b  push    rdi
0x14007664c  push    r12
0x14007664e  push    r13
0x140076650  push    r14
0x140076652  push    r15
0x140076654  lea     rbp, [rsp-27h]
0x140076659  sub     rsp, 0D0h
0x140076660  mov     rax, cs:__security_cookie
0x140076667  xor     rax, rsp
0x14007666a  mov     [rbp+57h+var_38], rax
0x14007666e  mov     [rsp+100h+var_DE], r8b
0x140076673  mov     r13, rdx
0x140076676  mov     rbx, rcx
0x140076679  mov     [rbp+57h+string], rdx
0x14007667d  xor     r15d, r15d
0x140076680  mov     [rbp+57h+var_D0], r15d
0x140076684  lea     ecx, [r15+28h]; Size
0x140076688  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007668d  mov     r14, rax
0x140076690  mov     [rbp+57h+string], rax
0x140076694  xorps   xmm0, xmm0
0x140076697  movups  xmmword ptr [rax], xmm0
0x14007669a  lea     eax, [r15+1]
0x14007669e  mov     [r14+8], eax
0x1400766a2  mov     [r14+0Ch], eax
0x1400766a6  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable'
0x1400766ad  mov     [r14], rax
0x1400766b0  lea     r12, [r14+10h]
0x1400766b4  mov     [r12], r15
0x1400766b8  mov     [r12+8], r15
0x1400766bd  mov     [r12+10h], r15
0x1400766c2  mov     [rbp+57h+var_78], r12
0x1400766c6  mov     [rbp+57h+var_70], r14
0x1400766ca  lea     rdx, [rbx+10h]
0x1400766ce  lea     rcx, [rbp+57h+string]
0x1400766d2  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UIJsonObject@Json@Data@4@@WinRT@@YA?AV?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@23@PEAX@Z; WinRT::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>,Windows::Data::Json::IJsonObject>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,void *)
0x1400766d7  nop
0x1400766d8  mov     r9, [rax]
0x1400766db  mov     ecx, r15d
0x1400766de  mov     [rbp+57h+var_B0], rcx
0x1400766e2  test    r9, r9
0x1400766e5  jz      short loc_14007670C
0x1400766e7  mov     rax, [r9]
0x1400766ea  lea     r8, [rbp+57h+var_B0]
0x1400766ee  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x1400766f5  mov     rcx, r9
0x1400766f8  mov     rax, [rax]
0x1400766fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076700  test    eax, eax
0x140076702  js      loc_140076B9B
0x140076708  mov     rcx, [rbp+57h+var_B0]
0x14007670c  mov     rdx, [rbp+57h+string]
0x140076710  test    rdx, rdx
0x140076713  jz      short loc_14007672C
0x140076715  mov     [rbp+57h+string], r15
0x140076719  mov     rax, [rdx]
0x14007671c  mov     rcx, rdx
0x14007671f  mov     rax, [rax+10h]
0x140076723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076728  mov     rcx, [rbp+57h+var_B0]
0x14007672c  mov     [rbp+57h+var_C0], r15
0x140076730  mov     [rbp+57h+var_B8], r15
0x140076734  test    rcx, rcx
0x140076737  jz      short loc_140076751
0x140076739  mov     rax, [rcx]
0x14007673c  lea     rdx, [rbp+57h+var_C0]
0x140076740  mov     rax, [rax+30h]
0x140076744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076749  test    eax, eax
0x14007674b  js      loc_140076BB7
0x140076751  mov     esi, 0Eh
0x140076756  lea     rdx, [rbp+57h+var_A0]
0x14007675a  call    ?end@?$iterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WinRT@@QEBA?AViterator@12@XZ; WinRT::iterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>::end(void)
0x14007675f  nop
0x140076760  mov     [rsp+100h+var_E0], r15b
0x140076765  mov     rcx, [rbp+57h+var_C0]
0x140076769  test    rcx, rcx
0x14007676c  jz      short loc_14007677F
0x14007676e  mov     rax, [rcx]
0x140076771  lea     rdx, [rsp+100h+var_E0]
0x140076776  mov     rax, [rax+38h]
0x14007677a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007677f  mov     al, r15b
0x140076782  mov     [rsp+100h+var_DF], al
0x140076786  mov     rcx, [rbp+57h+var_A0]
0x14007678a  test    rcx, rcx
0x14007678d  jz      short loc_1400767A8
0x14007678f  mov     rax, [rcx]
0x140076792  lea     rdx, [rsp+100h+var_DF]
0x140076797  mov     rax, [rax+38h]
0x14007679b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400767a0  mov     rcx, [rbp+57h+var_A0]
0x1400767a4  mov     al, [rsp+100h+var_DF]
0x1400767a8  cmp     [rsp+100h+var_E0], al
0x1400767ac  jz      loc_140076A6F
0x1400767b2  mov     rbx, [rbp+57h+var_C0]
0x1400767b6  mov     rax, [rbx]
0x1400767b9  mov     rdi, [rax+30h]
0x1400767bd  mov     rcx, [rbp+57h+var_B8]
0x1400767c1  test    rcx, rcx
0x1400767c4  jz      short loc_1400767D7
0x1400767c6  mov     [rbp+57h+var_B8], r15
0x1400767ca  mov     rax, [rcx]
0x1400767cd  mov     rax, [rax+10h]
0x1400767d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400767d6  nop
0x1400767d7  lea     rdx, [rbp+57h+var_B8]
0x1400767db  mov     rcx, rbx
0x1400767de  mov     rax, rdi
0x1400767e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400767e6  test    eax, eax
0x1400767e8  js      loc_140076B63
0x1400767ee  mov     rbx, [rbp+57h+var_B8]
0x1400767f2  lea     rax, [rbp+57h+var_A8]
0x1400767f6  mov     [rbp+57h+var_68], rax
0x1400767fa  mov     rdi, rbx
0x1400767fd  mov     [rsp+100h+var_D8], rbx
0x140076802  test    rbx, rbx
0x140076805  jz      short loc_14007681B
0x140076807  mov     rax, [rbx]
0x14007680a  mov     rcx, rbx
0x14007680d  mov     rax, [rax+8]
0x140076811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076816  mov     rdi, [rsp+100h+var_D8]
0x14007681b  lea     rax, [rsp+100h+var_D8]
0x140076820  mov     [rbp+57h+var_88], rax
0x140076824  mov     [rbp+57h+var_A8], r15
0x140076828  bts     esi, 7
0x14007682c  mov     [rbp+57h+var_D0], esi
0x14007682f  mov     [rbp+57h+var_80], rdi
0x140076833  test    rdi, rdi
0x140076836  jz      short loc_140076848
0x140076838  mov     rax, [rdi]
0x14007683b  mov     rcx, rdi
0x14007683e  mov     rax, [rax+8]
0x140076842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076847  nop
0x140076848  mov     [rbp+57h+var_90], rdi
0x14007684c  test    rdi, rdi
0x14007684f  jz      short loc_140076861
0x140076851  mov     rax, [rdi]
0x140076854  mov     rcx, rdi
0x140076857  mov     rax, [rax+8]
0x14007685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076860  nop
0x140076861  lea     rdx, [rbp+57h+var_A8]
0x140076865  mov     rcx, rdi
0x140076868  call    ??_9IJsonValue@Json@Data@Windows@@$BDI@AA; [thunk]: Windows::Data::Json::IJsonValue::`vcall'{56,{flat}}
0x14007686d  mov     r15d, eax
0x140076870  test    rdi, rdi
0x140076873  jz      short loc_140076885
0x140076875  mov     rax, [rdi]
0x140076878  mov     rcx, rdi
0x14007687b  mov     rax, [rax+10h]
0x14007687f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076884  nop
0x140076885  test    rdi, rdi
0x140076888  jz      short loc_14007689A
0x14007688a  mov     rax, [rdi]
0x14007688d  mov     rcx, rdi
0x140076890  mov     rax, [rax+10h]
0x140076894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076899  nop
0x14007689a  test    r15d, r15d
0x14007689d  js      loc_140076BEF
0x1400768a3  mov     rcx, [rsp+100h+var_D8]
0x1400768a8  xor     r15d, r15d
0x1400768ab  test    rcx, rcx
0x1400768ae  jz      short loc_1400768C2
0x1400768b0  mov     [rsp+100h+var_D8], r15
0x1400768b5  mov     rax, [rcx]
0x1400768b8  mov     rax, [rax+10h]
0x1400768bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400768c1  nop
0x1400768c2  btr     esi, 7
0x1400768c6  mov     [rbp+57h+var_D0], esi
0x1400768c9  or      esi, 60h
0x1400768cc  lea     rcx, [rbp+57h+var_A8]
0x1400768d0  call    ??$Call@UIJsonValue@Json@Data@Windows@@P81234@EAAJPEAW4JsonValueType@234@@Z$$V@WinRT@@YA?AW4JsonValueType@Json@Data@Windows@@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@P8IJsonValue@234@EAAJPEAW41234@@Z@Z; WinRT::Call<Windows::Data::Json::IJsonValue,long (Windows::Data::Json::IJsonValue::*)(Windows::Data::Json::JsonValueType *),>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>,long (Windows::Data::Json::IJsonValue::*)(Windows::Data::Json::JsonValueType *))
0x1400768d5  mov     ecx, r15d
0x1400768d8  cmp     eax, 5
0x1400768db  setz    cl
0x1400768de  movzx   eax, [rsp+100h+var_DE]
0x1400768e3  cmp     eax, ecx
0x1400768e5  jnz     loc_140076A48
0x1400768eb  mov     [rsp+100h+var_D8], rbx
0x1400768f0  test    rbx, rbx
0x1400768f3  jz      short loc_140076909
0x1400768f5  mov     rax, [rbx]
0x1400768f8  mov     rcx, rbx
0x1400768fb  mov     rax, [rax+8]
0x1400768ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076904  mov     rbx, [rsp+100h+var_D8]
0x140076909  lea     rax, [rsp+100h+var_D8]
0x14007690e  mov     [rbp+57h+var_90], rax
0x140076912  mov     [rbp+57h+string], r15
0x140076916  bts     esi, 0Ah
0x14007691a  mov     [rbp+57h+var_D0], esi
0x14007691d  mov     [rbp+57h+var_80], rbx
0x140076921  test    rbx, rbx
0x140076924  jz      short loc_140076936
0x140076926  mov     rax, [rbx]
0x140076929  mov     rcx, rbx
0x14007692c  mov     rax, [rax+8]
0x140076930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076935  nop
0x140076936  mov     [rbp+57h+var_88], rbx
0x14007693a  test    rbx, rbx
0x14007693d  jz      short loc_14007694F
0x14007693f  mov     rax, [rbx]
0x140076942  mov     rcx, rbx
0x140076945  mov     rax, [rax+8]
0x140076949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007694e  nop
0x14007694f  lea     rdx, [rbp+57h+string]
0x140076953  mov     rcx, rbx
0x140076956  call    ??_9?$IKeyValuePair_impl@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@$BDA@AA; [thunk]: Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Data::Json::IJsonValue *>::`vcall'{48,{flat}}
0x14007695b  mov     edi, eax
0x14007695d  test    rbx, rbx
0x140076960  jz      short loc_140076972
0x140076962  mov     rax, [rbx]
0x140076965  mov     rcx, rbx
0x140076968  mov     rax, [rax+10h]
0x14007696c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076971  nop
0x140076972  test    rbx, rbx
0x140076975  jz      short loc_140076987
0x140076977  mov     rax, [rbx]
0x14007697a  mov     rcx, rbx
0x14007697d  mov     rax, [rax+10h]
0x140076981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076986  nop
0x140076987  test    edi, edi
0x140076989  js      loc_140076BD3
0x14007698f  mov     rcx, [rsp+100h+var_D8]
0x140076994  test    rcx, rcx
0x140076997  jz      short loc_1400769AB
0x140076999  mov     [rsp+100h+var_D8], r15
0x14007699e  mov     rax, [rcx]
0x1400769a1  mov     rax, [rax+10h]
0x1400769a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400769aa  nop
0x1400769ab  btr     esi, 0Ah
0x1400769af  mov     [rbp+57h+var_D0], esi
0x1400769b2  or      esi, 300h
0x1400769b8  xor     edx, edx; length
0x1400769ba  mov     rcx, [rbp+57h+string]; string
0x1400769be  call    cs:__imp_WindowsGetStringRawBuffer
0x1400769c4  xorps   xmm0, xmm0
0x1400769c7  movups  [rbp+57h+pExceptionObject], xmm0
0x1400769cb  mov     qword ptr [rbp+57h+var_50], r15
0x1400769cf  mov     qword ptr [rbp+57h+var_50+8], r15
0x1400769d3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400769d7  inc     r8
0x1400769da  cmp     [rax+r8*2], r15w
0x1400769df  jnz     short loc_1400769D7
0x1400769e1  mov     rdx, rax
0x1400769e4  lea     rcx, [rbp+57h+pExceptionObject]
0x1400769e8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400769ed  nop
0x1400769ee  mov     rdx, [r12+8]
0x1400769f3  cmp     rdx, [r12+10h]
0x1400769f8  jz      short loc_140076A22
0x1400769fa  movups  xmm0, [rbp+57h+pExceptionObject]
0x1400769fe  movups  xmmword ptr [rdx], xmm0
0x140076a01  movups  xmm1, [rbp+57h+var_50]
0x140076a05  movups  xmmword ptr [rdx+10h], xmm1
0x140076a09  mov     qword ptr [rbp+57h+var_50], r15
0x140076a0d  mov     qword ptr [rbp+57h+var_50+8], 7
0x140076a15  mov     word ptr [rbp+57h+pExceptionObject], r15w
0x140076a1a  add     qword ptr [r12+8], 20h ; ' '
0x140076a20  jmp     short loc_140076A2F
0x140076a22  lea     r8, [rbp+57h+pExceptionObject]
0x140076a26  mov     rcx, r12
0x140076a29  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x140076a2e  nop
0x140076a2f  lea     rcx, [rbp+57h+pExceptionObject]
0x140076a33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140076a38  nop
0x140076a39  mov     rcx, [rbp+57h+string]; string
0x140076a3d  test    rcx, rcx
0x140076a40  jz      short loc_140076A48
0x140076a42  call    cs:__imp_WindowsDeleteString
0x140076a48  mov     [rsp+100h+var_E0], r15b
0x140076a4d  mov     rcx, [rbp+57h+var_C0]
0x140076a51  mov     rax, [rcx]
0x140076a54  lea     rdx, [rsp+100h+var_E0]
0x140076a59  mov     rax, [rax+40h]
0x140076a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076a62  test    eax, eax
0x140076a64  js      loc_140076B7F
0x140076a6a  jmp     loc_140076760
0x140076a6f  mov     rdx, [rbp+57h+var_98]
0x140076a73  test    rdx, rdx
0x140076a76  jz      short loc_140076A8F
0x140076a78  mov     [rbp+57h+var_98], r15
0x140076a7c  mov     rax, [rdx]
  ... truncated ...
```
