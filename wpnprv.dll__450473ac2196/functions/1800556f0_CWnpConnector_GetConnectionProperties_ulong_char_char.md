# CWnpConnector::GetConnectionProperties(ulong *,char * *,char * *)

- ea: `0x1800556f0`
- end: `0x1800559f3`
- name: `?GetConnectionProperties@CWnpConnector@@QEAAJPEAKPEAPEAD1@Z`
- size: `771`
- prototype: `__int64 __fastcall(CWnpConnector *__hidden this, unsigned int *, char **, char **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180064c90`

## callees

- `0x18000af1c`
- `0x18000fe0c`
- `0x18001c06c`
- `0x18001c594`
- `0x180033910`
- `0x180045004`
- `0x18004fef4`
- `0x180050d9c`
- `0x1800556f0`
- `0x180056538`
- `0x18005edec`

## string_xrefs

- `0x1800559aa`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800559bc`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800559ce`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800559e0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall CWnpConnector::GetConnectionProperties(CWnpConnector *this, unsigned int *a2, char **a3, char **a4)
{
  __int64 v8; // rdi
  int MbnProfile; // eax
  char IsEnabled; // al
  char *v11; // rdx
  __int64 v12; // rax
  char **v13; // rax
  __int64 v14; // r8
  const char *v15; // r9
  const char *v16; // r9
  void *v17; // rcx
  char *v18; // rdx
  char **v19; // rax
  __int64 v20; // r8
  const char *v21; // r9
  const char *v22; // r9
  char **v23; // rax
  __int64 v24; // r8
  const char *v25; // r9
  const char *v26; // r9
  void *v27; // rcx
  char **v28; // rax
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  void *v32; // rcx
  bool v33; // zf
  __int64 result; // rax
  __int64 v35; // [rsp+20h] [rbp-58h] BYREF
  struct _GUID v36; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    if ( !a2 )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    if ( !a3 )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    if ( !a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    *a2 = 1024;
    *a3 = 0;
    *a4 = 0;
    if ( *((_DWORD *)this + 22) != 7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)0x880403EDLL,
        v35);
    *a2 = *((_DWORD *)this + 100);
    if ( *((_DWORD *)this + 100) != 1027 )
      goto LABEL_32;
    v8 = -1;
    if ( *((_QWORD *)this + 10) == -1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(retaddr);
    MbnProfile = CWnpConnector::GetMbnProfile(&v36, a3, a4);
    if ( MbnProfile < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)(unsigned int)MbnProfile,
        v35);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PNH004>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PNH004>::GetImpl'::`2'::impl);
    v11 = *a3;
    if ( IsEnabled )
    {
      if ( v11 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        if ( v12 )
        {
          v13 = (char **)ConvertUtf8ToUtf16(&v36, v11);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v35,
            *v13,
            v14,
            v15);
          if ( !v35 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0xFF8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
              v16);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            (char *)this + 416,
            &v35);
          wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v35);
          v17 = *(void **)&v36.Data1;
          *(_QWORD *)&v36.Data1 = 0;
          if ( v17 )
            MemoryFree(v17);
        }
      }
      v18 = *a4;
      if ( !*a4 )
        goto LABEL_32;
      do
        ++v8;
      while ( v18[v8] );
      if ( !v8 )
        goto LABEL_32;
      v19 = (char **)ConvertUtf8ToUtf16(&v36, v18);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v35,
        *v19,
        v20,
        v21);
      if ( !v35 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v22);
    }
    else
    {
      v23 = (char **)ConvertUtf8ToUtf16(&v36, v11);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v35,
        *v23,
        v24,
        v25);
      if ( !v35 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v26);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)this + 416,
        &v35);
      wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v35);
      v27 = *(void **)&v36.Data1;
      *(_QWORD *)&v36.Data1 = 0;
      if ( v27 )
        MemoryFree(v27);
      v28 = (char **)ConvertUtf8ToUtf16(&v36, *a4);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v35,
        *v28,
        v29,
        v30);
      if ( !v35 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v31);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      (char *)this + 424,
      &v35);
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v35);
    v32 = *(void **)&v36.Data1;
    v33 = *(_QWORD *)&v36.Data1 == 0;
    *(_QWORD *)&v36.Data1 = 0;
    if ( !v33 )
      MemoryFree(v32);
LABEL_32:
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3C9,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
                           (const char *)a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800556f0  mov     rax, rsp
0x1800556f3  push    rbx
0x1800556f4  push    rsi
0x1800556f5  push    rdi
0x1800556f6  push    r12
0x1800556f8  push    r14
0x1800556fa  push    r15
0x1800556fc  sub     rsp, 48h
0x180055700  mov     r14, r9
0x180055703  mov     rsi, r8
0x180055706  mov     rdi, rdx
0x180055709  mov     rbx, rcx
0x18005570c  xor     r12d, r12d
0x18005570f  mov     r15d, r12d
0x180055712  mov     [rax+10h], r12d
0x180055716  test    rdx, rdx
0x180055719  jnz     short loc_180055720
0x18005571b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180055720  test    rsi, rsi
0x180055723  jnz     short loc_18005572A
0x180055725  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005572a  test    r14, r14
0x18005572d  jnz     short loc_180055734
0x18005572f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180055734  mov     dword ptr [rdi], 400h
0x18005573a  mov     [rsi], r12
0x18005573d  mov     [r14], r12
0x180055740  mov     rcx, [rsp+78h]; this
0x180055745  cmp     dword ptr [rbx+58h], 7
0x180055749  jnz     loc_18005597E
0x18005574f  mov     eax, [rbx+190h]
0x180055755  mov     [rdi], eax
0x180055757  cmp     dword ptr [rbx+190h], 403h
0x180055761  jnz     loc_180055965
0x180055767  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005576b  cmp     [rbx+50h], rdi
0x18005576f  jnz     short loc_180055776
0x180055771  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180055776  mov     r8, r14; char **
0x180055779  mov     rdx, rsi; char **
0x18005577c  lea     rcx, [rsp+78h+var_50]; struct _GUID *
0x180055781  call    ?GetMbnProfile@CWnpConnector@@CAJPEAU_GUID@@PEAPEAD1@Z; CWnpConnector::GetMbnProfile(_GUID *,char * *,char * *)
0x180055786  mov     rcx, [rsp+78h]; this
0x18005578b  test    eax, eax
0x18005578d  js      loc_180055995
0x180055793  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PNH004@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PNH004@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PNH004> `wil::Feature<__WilFeatureTraits_Feature_PNH004>::GetImpl(void)'::`2'::impl
0x18005579a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PNH004@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PNH004>::__private_IsEnabled(void)
0x18005579f  mov     rdx, [rsi]
0x1800557a2  test    al, al
0x1800557a4  jz      loc_18005589C
0x1800557aa  test    rdx, rdx
0x1800557ad  jz      short loc_180055829
0x1800557af  mov     rax, rdi
0x1800557b2  inc     rax
0x1800557b5  cmp     [rdx+rax], r12b
0x1800557b9  jnz     short loc_1800557B2
0x1800557bb  test    rax, rax
0x1800557be  jz      short loc_180055829
0x1800557c0  lea     rcx, [rsp+78h+var_50]
0x1800557c5  call    ?ConvertUtf8ToUtf16@@YA?AV?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@PEBD@Z; ConvertUtf8ToUtf16(char const *)
0x1800557ca  nop
0x1800557cb  mov     rdx, [rax]
0x1800557ce  lea     rcx, [rsp+78h+var_58]
0x1800557d3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800557d8  mov     [rsp+78h+arg_8], 2
0x1800557e3  mov     rcx, [rsp+78h]; this
0x1800557e8  cmp     [rsp+78h+var_58], r12
0x1800557ed  jz      loc_1800559AA
0x1800557f3  mov     r15d, 1
0x1800557f9  lea     rcx, [rbx+1A0h]
0x180055800  lea     rdx, [rsp+78h+var_58]
0x180055805  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18005580a  lea     rcx, [rsp+78h+var_58]
0x18005580f  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180055814  nop
0x180055815  mov     rcx, qword ptr [rsp+78h+var_50.Data1]; void *
0x18005581a  mov     qword ptr [rsp+78h+var_50.Data1], r12
0x18005581f  test    rcx, rcx
0x180055822  jz      short loc_180055829
0x180055824  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180055829  mov     rdx, [r14]
0x18005582c  test    rdx, rdx
0x18005582f  jz      loc_180055965
0x180055835  inc     rdi
0x180055838  cmp     [rdx+rdi], r12b
0x18005583c  jnz     short loc_180055835
0x18005583e  test    rdi, rdi
0x180055841  jz      loc_180055965
0x180055847  lea     rcx, [rsp+78h+var_50]
0x18005584c  call    ?ConvertUtf8ToUtf16@@YA?AV?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@PEBD@Z; ConvertUtf8ToUtf16(char const *)
0x180055851  nop
0x180055852  mov     rdx, [rax]
0x180055855  lea     rcx, [rsp+78h+var_58]
0x18005585a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005585f  or      r15d, 8
0x180055863  mov     [rsp+78h+arg_8], r15d
0x18005586b  mov     rcx, [rsp+78h]; this
0x180055870  cmp     [rsp+78h+var_58], r12
0x180055875  jz      loc_1800559BC
0x18005587b  lea     rcx, [rbx+1A8h]
0x180055882  lea     rdx, [rsp+78h+var_58]
0x180055887  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18005588c  lea     rcx, [rsp+78h+var_58]
0x180055891  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180055896  nop
0x180055897  jmp     loc_180055951
0x18005589c  lea     rcx, [rsp+78h+var_50]
0x1800558a1  call    ?ConvertUtf8ToUtf16@@YA?AV?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@PEBD@Z; ConvertUtf8ToUtf16(char const *)
0x1800558a6  nop
0x1800558a7  mov     rdx, [rax]
0x1800558aa  lea     rcx, [rsp+78h+var_58]
0x1800558af  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800558b4  mov     [rsp+78h+arg_8], 20h ; ' '
0x1800558bf  mov     rcx, [rsp+78h]; this
0x1800558c4  cmp     [rsp+78h+var_58], r12
0x1800558c9  jz      loc_1800559CE
0x1800558cf  lea     rcx, [rbx+1A0h]
0x1800558d6  lea     rdx, [rsp+78h+var_58]
0x1800558db  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800558e0  lea     rcx, [rsp+78h+var_58]
0x1800558e5  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1800558ea  nop
0x1800558eb  mov     rcx, qword ptr [rsp+78h+var_50.Data1]; void *
0x1800558f0  mov     qword ptr [rsp+78h+var_50.Data1], r12
0x1800558f5  test    rcx, rcx
0x1800558f8  jz      short loc_1800558FF
0x1800558fa  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800558ff  mov     rdx, [r14]
0x180055902  lea     rcx, [rsp+78h+var_50]
0x180055907  call    ?ConvertUtf8ToUtf16@@YA?AV?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@PEBD@Z; ConvertUtf8ToUtf16(char const *)
0x18005590c  nop
0x18005590d  mov     rdx, [rax]
0x180055910  lea     rcx, [rsp+78h+var_58]
0x180055915  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005591a  mov     [rsp+78h+arg_8], 90h
0x180055925  mov     rcx, [rsp+78h]; this
0x18005592a  cmp     [rsp+78h+var_58], r12
0x18005592f  jz      loc_1800559E0
0x180055935  lea     rcx, [rbx+1A8h]
0x18005593c  lea     rdx, [rsp+78h+var_58]
0x180055941  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180055946  lea     rcx, [rsp+78h+var_58]
0x18005594b  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180055950  nop
0x180055951  mov     rcx, qword ptr [rsp+78h+var_50.Data1]; void *
0x180055956  test    rcx, rcx
0x180055959  mov     qword ptr [rsp+78h+var_50.Data1], r12
0x18005595e  jz      short loc_180055965
0x180055960  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180055965  xor     eax, eax
0x180055967  jmp     short loc_180055970
0x180055969  mov     eax, [rsp+78h+arg_8]
0x180055970  add     rsp, 48h
0x180055974  pop     r15
0x180055976  pop     r14
0x180055978  pop     r12
0x18005597a  pop     rdi
0x18005597b  pop     rsi
0x18005597c  pop     rbx
0x18005597d  retn
0x18005597e  mov     r9d, 880403EDh; char *
0x180055984  lea     r8, aOnecoreuapBase_32; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005598b  mov     edx, 3A7h; void *
0x180055990  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055995  mov     r9d, eax; char *
0x180055998  lea     r8, aOnecoreuapBase_32; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005599f  mov     edx, 3B2h; void *
0x1800559a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800559aa  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800559b1  mov     edx, 0FF8h; void *
0x1800559b6  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800559bc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800559c3  mov     edx, 0FF8h; void *
0x1800559c8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800559ce  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800559d5  mov     edx, 0FF8h; void *
0x1800559da  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800559e0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800559e7  mov     edx, 0FF8h; void *
0x1800559ec  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
