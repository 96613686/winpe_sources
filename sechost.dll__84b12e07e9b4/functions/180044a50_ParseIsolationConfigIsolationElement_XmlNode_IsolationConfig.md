# ParseIsolationConfigIsolationElement(XmlNode *,IsolationConfig *)

- ea: `0x180044a50`
- end: `0x180044e4c`
- name: `?ParseIsolationConfigIsolationElement@@YAHPEAVXmlNode@@PEAVIsolationConfig@@@Z`
- size: `1020`
- prototype: `int(struct XmlNode *, struct IsolationConfig *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042ec8`

## callees

- `0x180016a88`
- `0x1800192a8`
- `0x180042e98`
- `0x180043700`
- `0x18004413c`
- `0x180044a50`
- `0x180045868`
- `0x180045990`
- `0x180045ad8`
- `0x180045b14`
- `0x180047148`
- `0x1800480f0`
- `0x18004ecbc`
- `0x18004ece0`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044dfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044dfe`

## pseudocode

```c
__int64 __fastcall ParseIsolationConfigIsolationElement(struct XmlNode *a1, IsolationContainer **a2)
{
  __int64 v4; // rax
  char v5; // bl
  unsigned int v6; // esi
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v10; // r15d
  __int64 v11; // rax
  XmlNodeSet *v12; // rax
  struct XmlNode *i; // rax
  struct XmlNode *v14; // r14
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  char v18; // al
  __int64 v19; // rdx
  char v20; // bl
  __int64 v21; // rdx
  char v22; // al
  __int64 v23; // rdx
  char v24; // bl
  char v25; // al
  __int64 v26; // rdx
  char v27; // bl
  bool v28; // al
  IsolationContainer *v29; // rcx
  signed __int64 v30; // rbx
  const struct IsolationContainer *v31; // rdx
  XmlNodeSet *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rdx
  void *v35; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v36[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v37[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v38[256]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v39[256]; // [rsp+180h] [rbp+80h] BYREF

  std::wstring::wstring(v37, L"isolation");
  v4 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 40LL))(a1);
  std::wstring::wstring(v36, v4);
  v5 = Compare(v36, v37);
  v6 = 1;
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v36, v7, 0);
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v37, v8, 0);
  if ( !v5 )
    return 0;
  IsolationContainer::IsolationContainer((IsolationContainer *)v38);
  v10 = 0;
LABEL_4:
  if ( v10 < 2 )
  {
    v11 = *(_QWORD *)a1;
    v35 = 0;
    v12 = (XmlNodeSet *)(*(__int64 (__fastcall **)(struct XmlNode *))(v11 + 32))(a1);
    for ( i = XmlNodeSet::iteratorReset(v12, &v35); ; i = XmlNodeSet::iteratorNext(v32, &v35) )
    {
      v14 = i;
      if ( !i )
      {
        ++v10;
        goto LABEL_4;
      }
      v15 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)i + 24LL))(i) - 2;
      if ( v15 )
      {
        if ( v15 == 1 )
        {
          v16 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v14 + 40LL))(v14);
          IsolationPolicy::TelemetryHelper::LogFormatError(3, L"isolation", v16, &Options, &Options, 0);
          SetLastError(0x57u);
          goto LABEL_10;
        }
      }
      else
      {
        v17 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v14 + 40LL))(v14);
        std::wstring::wstring(v36, v17);
        std::wstring::wstring(v37, L"default");
        v18 = Compare(v36, v37);
        LOBYTE(v19) = 1;
        v20 = v18;
        std::wstring::_Tidy(v37, v19, 0);
        if ( v20 )
        {
          if ( v10 != 1 )
          {
            if ( !(unsigned int)ParseIsolationConfigContainerElement(v14, (struct IsolationContainer *)v38) )
              goto LABEL_18;
            IsolationContainer::operator=(a2 + 3, v38);
          }
        }
        else
        {
          std::wstring::wstring(v37, L"containergroup");
          v22 = Compare(v36, v37);
          LOBYTE(v23) = 1;
          v24 = v22;
          std::wstring::_Tidy(v37, v23, 0);
          if ( v24 )
          {
            if ( v10
              && !(unsigned int)ParseIsolationConfigContainerGroupElement(
                                  v14,
                                  (struct IsolationConfig *)a2,
                                  (const struct IsolationContainer *)v38) )
            {
              goto LABEL_18;
            }
          }
          else
          {
            std::wstring::wstring(v37, L"container");
            v25 = Compare(v36, v37);
            LOBYTE(v26) = 1;
            v27 = v25;
            std::wstring::_Tidy(v37, v26, 0);
            if ( !v27 )
            {
              v33 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v14 + 40LL))(v14);
              IsolationPolicy::TelemetryHelper::LogFormatError(0, L"isolation", v33, &Options, &Options, 0);
              SetLastError(0x57u);
              LOBYTE(v34) = 1;
              std::wstring::_Tidy(v36, v34, 0);
              v6 = 0;
              break;
            }
            if ( v10 )
            {
              IsolationContainer::IsolationContainer((IsolationContainer *)v39, (const struct IsolationContainer *)v38);
              if ( !(unsigned int)ParseIsolationConfigContainerElement(v14, (struct IsolationContainer *)v39) )
              {
                IsolationContainer::~IsolationContainer((IsolationContainer *)v39);
LABEL_18:
                LOBYTE(v21) = 1;
                std::wstring::_Tidy(v36, v21, 0);
LABEL_10:
                IsolationContainer::~IsolationContainer((IsolationContainer *)v38);
                return 0;
              }
              v28 = v39 < (_BYTE *)a2[1] && *a2 <= (IsolationContainer *)v39;
              v29 = a2[2];
              if ( v28 )
              {
                v30 = v39 - (_BYTE *)*a2;
                if ( a2[1] == v29 )
                  std::vector<IsolationContainer>::_Reserve(a2);
                v31 = (IsolationContainer *)((char *)*a2 + (v30 & 0xFFFFFFFFFFFFFF00uLL));
              }
              else
              {
                if ( a2[1] == v29 )
                  std::vector<IsolationContainer>::_Reserve(a2);
                v31 = (const struct IsolationContainer *)v39;
              }
              IsolationContainer::IsolationContainer(a2[1], v31);
              a2[1] = (IsolationContainer *)((char *)a2[1] + 256);
              IsolationContainer::~IsolationContainer((IsolationContainer *)v39);
            }
          }
        }
        LOBYTE(v21) = 1;
        std::wstring::_Tidy(v36, v21, 0);
      }
      (*(void (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 32LL))(a1);
    }
  }
  IsolationContainer::~IsolationContainer((IsolationContainer *)v38);
  return v6;
}

```

## disassembly

```asm
0x180044a50  mov     [rsp-8+arg_10], rbx
0x180044a55  mov     [rsp-8+arg_18], rsi
0x180044a5a  push    rbp
0x180044a5b  push    rdi
0x180044a5c  push    r12
0x180044a5e  push    r14
0x180044a60  push    r15
0x180044a62  lea     rbp, [rsp-190h]
0x180044a6a  sub     rsp, 290h
0x180044a71  mov     rax, cs:__security_cookie
0x180044a78  xor     rax, rsp
0x180044a7b  mov     [rbp+1B0h+var_30], rax
0x180044a82  mov     rdi, rdx
0x180044a85  mov     r12, rcx
0x180044a88  lea     rdx, aIsolation; "isolation"
0x180044a8f  lea     rcx, [rsp+2B0h+var_258]
0x180044a94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044a99  mov     rax, [r12]
0x180044a9d  mov     rcx, r12
0x180044aa0  mov     rax, [rax+28h]
0x180044aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044aa9  mov     rdx, rax
0x180044aac  lea     rcx, [rsp+2B0h+var_278]
0x180044ab1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044ab6  lea     rdx, [rsp+2B0h+var_258]
0x180044abb  lea     rcx, [rsp+2B0h+var_278]
0x180044ac0  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044ac5  xor     r8d, r8d
0x180044ac8  lea     rcx, [rsp+2B0h+var_278]
0x180044acd  mov     bl, al
0x180044acf  lea     esi, [r8+1]
0x180044ad3  mov     dl, sil
0x180044ad6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044adb  xor     r8d, r8d
0x180044ade  lea     rcx, [rsp+2B0h+var_258]
0x180044ae3  mov     dl, sil
0x180044ae6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044aeb  test    bl, bl
0x180044aed  jnz     short loc_180044AF6
0x180044aef  xor     eax, eax
0x180044af1  jmp     loc_180044E21
0x180044af6  lea     rcx, [rbp+1B0h+var_230]; this
0x180044afa  call    ??0IsolationContainer@@QEAA@XZ; IsolationContainer::IsolationContainer(void)
0x180044aff  xor     r15d, r15d
0x180044b02  cmp     r15d, 2
0x180044b06  jge     loc_180044E16
0x180044b0c  mov     rax, [r12]
0x180044b10  mov     rcx, r12
0x180044b13  mov     [rsp+2B0h+var_280], 0
0x180044b1c  mov     rax, [rax+20h]
0x180044b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b25  lea     rdx, [rsp+2B0h+var_280]; void **
0x180044b2a  mov     rcx, rax; this
0x180044b2d  call    ?iteratorReset@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorReset(void * *)
0x180044b32  mov     r14, rax
0x180044b35  test    rax, rax
0x180044b38  jz      loc_180044DAC
0x180044b3e  mov     rcx, [rax]
0x180044b41  mov     rax, [rcx+18h]
0x180044b45  mov     rcx, r14
0x180044b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b4d  sub     eax, 2
0x180044b50  jz      short loc_180044BAA
0x180044b52  cmp     eax, esi
0x180044b54  jnz     loc_180044D8D
0x180044b5a  mov     rax, [r14]
0x180044b5d  mov     rcx, r14
0x180044b60  mov     rax, [rax+28h]
0x180044b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b69  lea     r9, Options
0x180044b70  mov     [rsp+2B0h+var_288], 0
0x180044b78  mov     r8, rax
0x180044b7b  mov     [rsp+2B0h+var_290], r9
0x180044b80  lea     rdx, aIsolation; "isolation"
0x180044b87  mov     ecx, 3
0x180044b8c  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x180044b91  mov     ecx, 57h ; 'W'; dwErrCode
0x180044b96  call    cs:__imp_SetLastError
0x180044b9c  lea     rcx, [rbp+1B0h+var_230]; this
0x180044ba0  call    ??1IsolationContainer@@QEAA@XZ; IsolationContainer::~IsolationContainer(void)
0x180044ba5  jmp     loc_180044AEF
0x180044baa  mov     rax, [r14]
0x180044bad  mov     rcx, r14
0x180044bb0  mov     rax, [rax+28h]
0x180044bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bb9  mov     rdx, rax
0x180044bbc  lea     rcx, [rsp+2B0h+var_278]
0x180044bc1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044bc6  lea     rdx, aDefault; "default"
0x180044bcd  lea     rcx, [rsp+2B0h+var_258]
0x180044bd2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044bd7  lea     rdx, [rsp+2B0h+var_258]
0x180044bdc  lea     rcx, [rsp+2B0h+var_278]
0x180044be1  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044be6  xor     r8d, r8d
0x180044be9  lea     rcx, [rsp+2B0h+var_258]
0x180044bee  mov     dl, sil
0x180044bf1  mov     bl, al
0x180044bf3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044bf8  test    bl, bl
0x180044bfa  jz      short loc_180044C27
0x180044bfc  cmp     r15d, esi
0x180044bff  jz      loc_180044D7D
0x180044c05  lea     rdx, [rbp+1B0h+var_230]; struct IsolationContainer *
0x180044c09  mov     rcx, r14; struct XmlNode *
0x180044c0c  call    ?ParseIsolationConfigContainerElement@@YAHPEAVXmlNode@@PEAVIsolationContainer@@@Z; ParseIsolationConfigContainerElement(XmlNode *,IsolationContainer *)
0x180044c11  test    eax, eax
0x180044c13  jz      short loc_180044C7D
0x180044c15  lea     rcx, [rdi+18h]
0x180044c19  lea     rdx, [rbp+1B0h+var_230]
0x180044c1d  call    ??4IsolationContainer@@QEAAAEAV0@AEBV0@@Z; IsolationContainer::operator=(IsolationContainer const &)
0x180044c22  jmp     loc_180044D7D
0x180044c27  lea     rdx, aContainergroup; "containergroup"
0x180044c2e  lea     rcx, [rsp+2B0h+var_258]
0x180044c33  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044c38  lea     rdx, [rsp+2B0h+var_258]
0x180044c3d  lea     rcx, [rsp+2B0h+var_278]
0x180044c42  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044c47  xor     r8d, r8d
0x180044c4a  lea     rcx, [rsp+2B0h+var_258]
0x180044c4f  mov     dl, sil
0x180044c52  mov     bl, al
0x180044c54  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044c59  test    bl, bl
0x180044c5b  jz      short loc_180044C92
0x180044c5d  test    r15d, r15d
0x180044c60  jz      loc_180044D7D
0x180044c66  lea     r8, [rbp+1B0h+var_230]; struct IsolationContainer *
0x180044c6a  mov     rdx, rdi; struct IsolationConfig *
0x180044c6d  mov     rcx, r14; struct XmlNode *
0x180044c70  call    ?ParseIsolationConfigContainerGroupElement@@YAHPEAVXmlNode@@PEAVIsolationConfig@@PEBVIsolationContainer@@@Z; ParseIsolationConfigContainerGroupElement(XmlNode *,IsolationConfig *,IsolationContainer const *)
0x180044c75  test    eax, eax
0x180044c77  jnz     loc_180044D7D
0x180044c7d  xor     r8d, r8d
0x180044c80  lea     rcx, [rsp+2B0h+var_278]
0x180044c85  mov     dl, sil
0x180044c88  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044c8d  jmp     loc_180044B9C
0x180044c92  lea     rdx, aContainer; "container"
0x180044c99  lea     rcx, [rsp+2B0h+var_258]
0x180044c9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044ca3  lea     rdx, [rsp+2B0h+var_258]
0x180044ca8  lea     rcx, [rsp+2B0h+var_278]
0x180044cad  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044cb2  xor     r8d, r8d
0x180044cb5  lea     rcx, [rsp+2B0h+var_258]
0x180044cba  mov     dl, sil
0x180044cbd  mov     bl, al
0x180044cbf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044cc4  test    bl, bl
0x180044cc6  jz      loc_180044DC5
0x180044ccc  test    r15d, r15d
0x180044ccf  jz      loc_180044D7D
0x180044cd5  lea     rdx, [rbp+1B0h+var_230]; struct IsolationContainer *
0x180044cd9  lea     rcx, [rbp+1B0h+var_130]; this
0x180044ce0  call    ??0IsolationContainer@@QEAA@AEBV0@@Z; IsolationContainer::IsolationContainer(IsolationContainer const &)
0x180044ce5  lea     rdx, [rbp+1B0h+var_130]; struct IsolationContainer *
0x180044cec  mov     rcx, r14; struct XmlNode *
0x180044cef  call    ?ParseIsolationConfigContainerElement@@YAHPEAVXmlNode@@PEAVIsolationContainer@@@Z; ParseIsolationConfigContainerElement(XmlNode *,IsolationContainer *)
0x180044cf4  test    eax, eax
0x180044cf6  jz      loc_180044DB4
0x180044cfc  lea     rax, [rbp+1B0h+var_130]
0x180044d03  cmp     rax, [rdi+8]
0x180044d07  jnb     short loc_180044D1A
0x180044d09  lea     rax, [rbp+1B0h+var_130]
0x180044d10  cmp     [rdi], rax
0x180044d13  ja      short loc_180044D1A
0x180044d15  mov     al, sil
0x180044d18  jmp     short loc_180044D1C
0x180044d1a  xor     al, al
0x180044d1c  mov     rcx, [rdi+10h]
0x180044d20  test    al, al
0x180044d22  jz      short loc_180044D4B
0x180044d24  lea     rbx, [rbp+1B0h+var_130]
0x180044d2b  sub     rbx, [rdi]
0x180044d2e  cmp     [rdi+8], rcx
0x180044d32  jnz     short loc_180044D3C
0x180044d34  mov     rcx, rdi
0x180044d37  call    ?_Reserve@?$vector@VIsolationContainer@@V?$allocator@VIsolationContainer@@@std@@@std@@IEAAX_K@Z; std::vector<IsolationContainer>::_Reserve(unsigned __int64)
0x180044d3c  and     rbx, 0FFFFFFFFFFFFFF00h
0x180044d43  add     rbx, [rdi]
0x180044d46  mov     rdx, rbx
0x180044d49  jmp     short loc_180044D60
0x180044d4b  cmp     [rdi+8], rcx
0x180044d4f  jnz     short loc_180044D59
0x180044d51  mov     rcx, rdi
0x180044d54  call    ?_Reserve@?$vector@VIsolationContainer@@V?$allocator@VIsolationContainer@@@std@@@std@@IEAAX_K@Z; std::vector<IsolationContainer>::_Reserve(unsigned __int64)
0x180044d59  lea     rdx, [rbp+1B0h+var_130]; struct IsolationContainer *
0x180044d60  mov     rcx, [rdi+8]; this
0x180044d64  call    ??0IsolationContainer@@QEAA@AEBV0@@Z; IsolationContainer::IsolationContainer(IsolationContainer const &)
0x180044d69  add     qword ptr [rdi+8], 100h
0x180044d71  lea     rcx, [rbp+1B0h+var_130]; this
0x180044d78  call    ??1IsolationContainer@@QEAA@XZ; IsolationContainer::~IsolationContainer(void)
0x180044d7d  xor     r8d, r8d
0x180044d80  lea     rcx, [rsp+2B0h+var_278]
0x180044d85  mov     dl, sil
0x180044d88  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044d8d  mov     rax, [r12]
0x180044d91  mov     rcx, r12
0x180044d94  mov     rax, [rax+20h]
0x180044d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d9d  lea     rdx, [rsp+2B0h+var_280]; void **
0x180044da2  call    ?iteratorNext@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorNext(void * *)
0x180044da7  jmp     loc_180044B32
0x180044dac  add     r15d, esi
0x180044daf  jmp     loc_180044B02
0x180044db4  lea     rcx, [rbp+1B0h+var_130]; this
0x180044dbb  call    ??1IsolationContainer@@QEAA@XZ; IsolationContainer::~IsolationContainer(void)
0x180044dc0  jmp     loc_180044C7D
0x180044dc5  mov     rax, [r14]
0x180044dc8  mov     rcx, r14
0x180044dcb  mov     rax, [rax+28h]
0x180044dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044dd4  lea     r9, Options
0x180044ddb  mov     [rsp+2B0h+var_288], 0
0x180044de3  mov     r8, rax
0x180044de6  mov     [rsp+2B0h+var_290], r9
0x180044deb  lea     rdx, aIsolation; "isolation"
0x180044df2  xor     ecx, ecx
0x180044df4  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x180044df9  mov     ecx, 57h ; 'W'; dwErrCode
0x180044dfe  call    cs:__imp_SetLastError
0x180044e04  xor     r8d, r8d
0x180044e07  lea     rcx, [rsp+2B0h+var_278]
0x180044e0c  mov     dl, sil
0x180044e0f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044e14  xor     esi, esi
0x180044e16  lea     rcx, [rbp+1B0h+var_230]; this
0x180044e1a  call    ??1IsolationContainer@@QEAA@XZ; IsolationContainer::~IsolationContainer(void)
0x180044e1f  mov     eax, esi
0x180044e21  mov     rcx, [rbp+1B0h+var_30]
0x180044e28  xor     rcx, rsp; StackCookie
0x180044e2b  call    __security_check_cookie
0x180044e30  lea     r11, [rsp+2B0h+var_20]
0x180044e38  mov     rbx, [r11+40h]
0x180044e3c  mov     rsi, [r11+48h]
0x180044e40  mov     rsp, r11
0x180044e43  pop     r15
0x180044e45  pop     r14
0x180044e47  pop     r12
0x180044e49  pop     rdi
0x180044e4a  pop     rbp
0x180044e4b  retn
```
