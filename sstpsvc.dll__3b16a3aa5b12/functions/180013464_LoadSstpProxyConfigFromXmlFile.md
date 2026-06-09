# LoadSstpProxyConfigFromXmlFile

- ea: `0x180013464`
- end: `0x1800138b2`
- name: `LoadSstpProxyConfigFromXmlFile`
- size: `1102`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005920`
- `0x180014840`

## callees

- `0x180007c34`
- `0x18000827c`
- `0x180008360`
- `0x18000f77c`
- `0x18000fbb0`
- `0x18000fd1c`
- `0x180010e30`
- `0x1800124fc`
- `0x180012560`
- `0x180012808`
- `0x180013000`
- `0x180013464`
- `0x18001bcba`
- `0x18001bcc6`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800137b7`
- `msvcrt!wcscpy_s` at `0x1800137b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800134f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800134f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800135c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800135c5`
- `XmlLite!CreateXmlReader` at `0x180013538`
- `XmlLite!CreateXmlReader` at `0x180013538`

## string_xrefs

- `0x18001350d`: `LoadSstpProxyConfigFromXmlFile: xml file is not opened`
- `0x180013553`: `LoadSstpProxyConfigFromXmlFile: CreateXmlReader failed with error %d`
- `0x180013621`: `LoadSstpProxyConfigFromXmlFile: SetInput method of IXmlReader object failed with error %d`
- `0x180013661`: `LoadSstpProxyConfigFromXmlFile: Failed to set the XmlReaderProperty_DtdProcessing of IXmlReader object. Error %d`
- `0x18001380c`: `LoadSstpProxyConfigFromXmlFile: GetLocalName method of IXmlReader object failed with error %d`
- `0x18001382e`: `LoadSstpProxyConfigFromXmlFile: GetValue method of IXmlReader object failed with error %d`

## pseudocode

```c
__int64 LoadSstpProxyConfigFromXmlFile()
{
  TenantGatewayMap *Instance; // r15
  struct IStream *FileStream; // rdi
  unsigned int v2; // edi
  unsigned int v3; // eax
  unsigned int v4; // ebx
  char v6; // r14
  char v7; // di
  char v8; // si
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  void *ppvObject; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *String1; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Source; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h]
  _BYTE v20[40]; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[2044]; // [rsp+94h] [rbp-6Ch] BYREF
  wchar_t Destination[512]; // [rsp+890h] [rbp+790h] BYREF

  Instance = TenantGatewayMap::GetInstance();
  ppvObject = 0;
  v21 = 0;
  v15 = 0;
  String1 = 0;
  Source = 0;
  FileStream = TenantGatewayMap::GetFileStream(Instance);
  v19 = 0;
  v18 = 0;
  memset_0(v22, 0, sizeof(v22));
  AcquireSRWLockExclusive((PSRWLOCK)Instance);
  if ( !FileStream )
  {
    v2 = 2;
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceError,
        L"LoadSstpProxyConfigFromXmlFile: xml file is not opened");
    goto LABEL_12;
  }
  v3 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v4 = v3;
  if ( !v3 )
  {
    v4 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, FileStream);
    if ( v4 )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_9;
      LOWORD(v21) = 0;
      FormatRRASErrorString(
        &v21,
        L"LoadSstpProxyConfigFromXmlFile: SetInput method of IXmlReader object failed with error %d",
        v4);
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
      if ( !v4 )
      {
        v6 = 0;
LABEL_22:
        v7 = 0;
        v8 = 0;
        while ( 1 )
        {
          v4 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v15);
          if ( v4 )
            break;
          if ( v15 == 1 )
          {
            v4 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                   ppvObject,
                   &String1,
                   0);
            if ( v4 )
            {
              if ( (byte_18002D803 & 8) == 0 )
                goto LABEL_9;
              LOWORD(v21) = 0;
              FormatRRASErrorString(
                &v21,
                L"LoadSstpProxyConfigFromXmlFile: GetLocalName method of IXmlReader object failed with error %d",
                v4);
              goto LABEL_7;
            }
            if ( !wcscmp_0(String1, L"Tenant") )
            {
              if ( v6 )
              {
                std::wstring::wstring(v20, Destination);
                v9 = std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](
                       (char *)Instance + 8,
                       v20);
                std::vector<std::wstring>::operator=(v9, &v18);
                LOBYTE(v10) = 1;
                std::wstring::_Tidy(v20, v10, 0);
                std::vector<std::wstring>::clear(&v18);
                memset_0(Destination, 0, sizeof(Destination));
              }
              else
              {
                v6 = 1;
              }
              v7 = 1;
              v8 = 0;
            }
            else if ( !wcscmp_0(String1, L"Gateway") )
            {
              v7 = 0;
              v8 = 1;
            }
            String1 = 0;
          }
          else
          {
            if ( v15 != 3 )
              goto LABEL_22;
            v4 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                   ppvObject,
                   &Source,
                   0);
            if ( v4 )
            {
              if ( (byte_18002D803 & 8) == 0 )
                goto LABEL_9;
              LOWORD(v21) = 0;
              FormatRRASErrorString(
                &v21,
                L"LoadSstpProxyConfigFromXmlFile: GetValue method of IXmlReader object failed with error %d",
                v4);
              goto LABEL_7;
            }
            if ( v7 )
            {
              wcscpy_s(Destination, 0x200u, Source);
            }
            else if ( v8 )
            {
              std::wstring::wstring(v20, Source);
              std::vector<std::wstring>::push_back(&v18, v20);
              LOBYTE(v11) = 1;
              std::wstring::_Tidy(v20, v11, 0);
            }
          }
        }
        if ( v6 )
        {
          std::wstring::wstring(v20, Destination);
          v12 = std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](
                  (char *)Instance + 8,
                  v20);
          std::vector<std::wstring>::operator=(v12, &v18);
          LOBYTE(v13) = 1;
          std::wstring::_Tidy(v20, v13, 0);
          std::vector<std::wstring>::clear(&v18);
          memset_0(Destination, 0, sizeof(Destination));
        }
        if ( v4 == -1072894406 )
        {
          v2 = 0;
          goto LABEL_12;
        }
        goto LABEL_9;
      }
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_9;
      LOWORD(v21) = 0;
      FormatRRASErrorString(
        &v21,
        L"LoadSstpProxyConfigFromXmlFile: Failed to set the XmlReaderProperty_DtdProcessing of IXmlReader object. Error %d",
        v4);
    }
LABEL_7:
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v21);
    goto LABEL_9;
  }
  if ( (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"LoadSstpProxyConfigFromXmlFile: CreateXmlReader failed with error %d", v3);
    goto LABEL_7;
  }
LABEL_9:
  v2 = 0;
  if ( (v4 & 0x80000000) != 0 )
  {
    v2 = (unsigned __int16)v4;
    if ( (v4 & 0x1FFF0000) != 0x70000 )
      v2 = v4;
  }
LABEL_12:
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  ppvObject = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)Instance);
  std::vector<std::wstring>::_Tidy(&v18);
  return v2;
}

```

## disassembly

```asm
0x180013464  push    rbp
0x180013466  push    rbx
0x180013467  push    rsi
0x180013468  push    rdi
0x180013469  push    r12
0x18001346b  push    r14
0x18001346d  push    r15
0x18001346f  lea     rbp, [rsp-0BA0h]
0x180013477  sub     rsp, 0CA0h
0x18001347e  mov     rax, cs:__security_cookie
0x180013485  xor     rax, rsp
0x180013488  mov     [rbp+0BD0h+var_40], rax
0x18001348f  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180013494  mov     rcx, rax; this
0x180013497  mov     r15, rax
0x18001349a  call    ?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ; TenantGatewayMap::GetFileStream(void)
0x18001349f  xor     ecx, ecx
0x1800134a1  mov     [rsp+0CD0h+ppvObject], 0
0x1800134aa  mov     [rbp+0BD0h+var_C40], ecx
0x1800134ad  xorps   xmm0, xmm0
0x1800134b0  lea     rcx, [rbp+0BD0h+var_C3C]; void *
0x1800134b4  mov     [rsp+0CD0h+var_CA8], 0
0x1800134bc  xor     edx, edx; Val
0x1800134be  mov     [rsp+0CD0h+String1], 0
0x1800134c7  mov     r8d, 7FCh; Size
0x1800134cd  mov     [rsp+0CD0h+Source], 0
0x1800134d6  mov     rdi, rax
0x1800134d9  mov     [rsp+0CD0h+var_C78], 0
0x1800134e2  movdqu  [rsp+0CD0h+var_C88], xmm0
0x1800134e8  call    memset_0
0x1800134ed  mov     rcx, r15; SRWLock
0x1800134f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800134f6  test    rdi, rdi
0x1800134f9  jnz     short loc_180013529
0x1800134fb  test    cs:byte_18002D803, 8
0x180013502  mov     edi, 2
0x180013507  jz      loc_1800135A3
0x18001350d  lea     r8, aLoadsstpproxyc_1; "LoadSstpProxyConfigFromXmlFile: xml fil"...
0x180013514  lea     rdx, RasSSTPSvcTraceError
0x18001351b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013522  call    McTemplateU0z_EventWriteTransfer
0x180013527  jmp     short loc_1800135A3
0x180013529  xor     r8d, r8d; pMalloc
0x18001352c  lea     rdx, [rsp+0CD0h+ppvObject]; ppvObject
0x180013531  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180013538  call    cs:__imp_CreateXmlReader
0x18001353e  mov     ebx, eax
0x180013540  test    eax, eax
0x180013542  jz      loc_1800135F8
0x180013548  test    cs:byte_18002D803, 8
0x18001354f  jz      short loc_18001358A
0x180013551  xor     ecx, ecx
0x180013553  lea     rdx, aLoadsstpproxyc_4; "LoadSstpProxyConfigFromXmlFile: CreateX"...
0x18001355a  mov     word ptr [rbp+0BD0h+var_C40], cx
0x18001355e  mov     r8d, eax
0x180013561  lea     rcx, [rbp+0BD0h+var_C40]
0x180013565  call    FormatRRASErrorString
0x18001356a  test    cs:byte_18002D803, 8
0x180013571  jz      short loc_18001358A
0x180013573  lea     r8, [rbp+0BD0h+var_C40]
0x180013577  lea     rdx, RasSSTPSvcTraceError
0x18001357e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013585  call    McTemplateU0z_EventWriteTransfer
0x18001358a  xor     edi, edi
0x18001358c  test    ebx, ebx
0x18001358e  jns     short loc_1800135A3
0x180013590  mov     eax, ebx
0x180013592  movzx   edi, bx
0x180013595  and     eax, 1FFF0000h
0x18001359a  cmp     eax, 70000h
0x18001359f  jz      short loc_1800135A3
0x1800135a1  mov     edi, ebx
0x1800135a3  mov     rcx, [rsp+0CD0h+ppvObject]
0x1800135a8  test    rcx, rcx
0x1800135ab  jz      short loc_1800135B9
0x1800135ad  mov     rdx, [rcx]
0x1800135b0  mov     rax, [rdx+10h]
0x1800135b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135b9  mov     rcx, r15; SRWLock
0x1800135bc  mov     [rsp+0CD0h+ppvObject], 0
0x1800135c5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800135cb  lea     rcx, [rsp+0CD0h+var_C88]
0x1800135d0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800135d5  mov     eax, edi
0x1800135d7  mov     rcx, [rbp+0BD0h+var_40]
0x1800135de  xor     rcx, rsp; StackCookie
0x1800135e1  call    __security_check_cookie
0x1800135e6  add     rsp, 0CA0h
0x1800135ed  pop     r15
0x1800135ef  pop     r14
0x1800135f1  pop     r12
0x1800135f3  pop     rdi
0x1800135f4  pop     rsi
0x1800135f5  pop     rbx
0x1800135f6  pop     rbp
0x1800135f7  retn
0x1800135f8  mov     rcx, [rsp+0CD0h+ppvObject]
0x1800135fd  mov     rdx, rdi
0x180013600  mov     rax, [rcx]
0x180013603  mov     rax, [rax+18h]
0x180013607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001360c  mov     ebx, eax
0x18001360e  test    eax, eax
0x180013610  jz      short loc_180013634
0x180013612  test    cs:byte_18002D803, 8
0x180013619  jz      loc_18001358A
0x18001361f  xor     eax, eax
0x180013621  lea     rdx, aLoadsstpproxyc_2; "LoadSstpProxyConfigFromXmlFile: SetInpu"...
0x180013628  mov     word ptr [rbp+0BD0h+var_C40], ax
0x18001362c  mov     r8d, ebx
0x18001362f  jmp     loc_180013561
0x180013634  mov     rcx, [rsp+0CD0h+ppvObject]
0x180013639  xor     r8d, r8d
0x18001363c  mov     rax, [rcx]
0x18001363f  lea     edx, [r8+4]
0x180013643  mov     rax, [rax+28h]
0x180013647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001364c  mov     ebx, eax
0x18001364e  test    eax, eax
0x180013650  jz      short loc_180013674
0x180013652  test    cs:byte_18002D803, 8
0x180013659  jz      loc_18001358A
0x18001365f  xor     eax, eax
0x180013661  lea     rdx, aLoadsstpproxyc; "LoadSstpProxyConfigFromXmlFile: Failed "...
0x180013668  mov     word ptr [rbp+0BD0h+var_C40], ax
0x18001366c  mov     r8d, ebx
0x18001366f  jmp     loc_180013561
0x180013674  xor     r14b, r14b
0x180013677  xor     dil, dil
0x18001367a  xor     sil, sil
0x18001367d  mov     rcx, [rsp+0CD0h+ppvObject]
0x180013682  lea     rdx, [rsp+0CD0h+var_CA8]
0x180013687  mov     rax, [rcx]
0x18001368a  mov     rax, [rax+30h]
0x18001368e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013693  mov     ebx, eax
0x180013695  test    eax, eax
0x180013697  jnz     loc_180013841
0x18001369d  cmp     [rsp+0CD0h+var_CA8], 1
0x1800136a2  jnz     loc_180013774
0x1800136a8  mov     rcx, [rsp+0CD0h+ppvObject]
0x1800136ad  lea     rdx, [rsp+0CD0h+String1]
0x1800136b2  xor     r8d, r8d
0x1800136b5  mov     rax, [rcx]
0x1800136b8  mov     rax, [rax+70h]
0x1800136bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136c1  mov     ebx, eax
0x1800136c3  test    eax, eax
0x1800136c5  jnz     loc_1800137FD
0x1800136cb  mov     rcx, [rsp+0CD0h+String1]; String1
0x1800136d0  lea     rdx, aTenant; "Tenant"
0x1800136d7  call    wcscmp_0
0x1800136dc  test    eax, eax
0x1800136de  jnz     short loc_18001374B
0x1800136e0  test    r14b, r14b
0x1800136e3  jz      short loc_180013740
0x1800136e5  lea     rdx, [rbp+0BD0h+Destination]
0x1800136ec  lea     rcx, [rsp+0CD0h+var_C68]
0x1800136f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800136f6  lea     rdx, [rsp+0CD0h+var_C68]
0x1800136fb  lea     rcx, [r15+8]
0x1800136ff  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](std::wstring &&)
0x180013704  mov     rcx, rax
0x180013707  lea     rdx, [rsp+0CD0h+var_C88]
0x18001370c  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x180013711  xor     r8d, r8d
0x180013714  lea     rcx, [rsp+0CD0h+var_C68]
0x180013719  mov     dl, 1
0x18001371b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013720  lea     rcx, [rsp+0CD0h+var_C88]
0x180013725  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18001372a  xor     edx, edx; Val
0x18001372c  lea     rcx, [rbp+0BD0h+Destination]; void *
0x180013733  mov     r8d, 400h; Size
0x180013739  call    memset_0
0x18001373e  jmp     short loc_180013743
0x180013740  mov     r14b, 1
0x180013743  mov     dil, 1
0x180013746  xor     sil, sil
0x180013749  jmp     short loc_180013766
0x18001374b  mov     rcx, [rsp+0CD0h+String1]; String1
0x180013750  lea     rdx, aGateway; "Gateway"
0x180013757  call    wcscmp_0
0x18001375c  test    eax, eax
0x18001375e  jnz     short loc_180013766
0x180013760  xor     dil, dil
0x180013763  mov     sil, 1
0x180013766  mov     [rsp+0CD0h+String1], 0
0x18001376f  jmp     loc_18001367D
0x180013774  cmp     [rsp+0CD0h+var_CA8], 3
0x180013779  jnz     loc_180013677
0x18001377f  mov     rcx, [rsp+0CD0h+ppvObject]
0x180013784  lea     rdx, [rsp+0CD0h+Source]
0x180013789  xor     r8d, r8d
0x18001378c  mov     rax, [rcx]
0x18001378f  mov     rax, [rax+80h]
0x180013796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001379b  mov     ebx, eax
0x18001379d  test    eax, eax
0x18001379f  jnz     short loc_18001381F
0x1800137a1  test    dil, dil
0x1800137a4  jz      short loc_1800137C2
0x1800137a6  mov     r8, [rsp+0CD0h+Source]; Source
0x1800137ab  lea     rcx, [rbp+0BD0h+Destination]; Destination
0x1800137b2  mov     edx, 200h; SizeInWords
0x1800137b7  call    cs:__imp_wcscpy_s
0x1800137bd  jmp     loc_18001367D
0x1800137c2  test    sil, sil
0x1800137c5  jz      loc_18001367D
0x1800137cb  mov     rdx, [rsp+0CD0h+Source]
0x1800137d0  lea     rcx, [rsp+0CD0h+var_C68]
0x1800137d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800137da  lea     rdx, [rsp+0CD0h+var_C68]
0x1800137df  lea     rcx, [rsp+0CD0h+var_C88]
0x1800137e4  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800137e9  xor     r8d, r8d
0x1800137ec  lea     rcx, [rsp+0CD0h+var_C68]
0x1800137f1  mov     dl, 1
0x1800137f3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800137f8  jmp     loc_18001367D
0x1800137fd  test    cs:byte_18002D803, 8
0x180013804  jz      loc_18001358A
0x18001380a  xor     eax, eax
0x18001380c  lea     rdx, aLoadsstpproxyc_0; "LoadSstpProxyConfigFromXmlFile: GetLoca"...
0x180013813  mov     word ptr [rbp+0BD0h+var_C40], ax
0x180013817  mov     r8d, ebx
0x18001381a  jmp     loc_180013561
0x18001381f  test    cs:byte_18002D803, 8
0x180013826  jz      loc_18001358A
0x18001382c  xor     eax, eax
0x18001382e  lea     rdx, aLoadsstpproxyc_3; "LoadSstpProxyConfigFromXmlFile: GetValu"...
0x180013835  mov     word ptr [rbp+0BD0h+var_C40], ax
0x180013839  mov     r8d, ebx
0x18001383c  jmp     loc_180013561
0x180013841  test    r14b, r14b
0x180013844  jz      short loc_18001389F
0x180013846  lea     rdx, [rbp+0BD0h+Destination]
0x18001384d  lea     rcx, [rsp+0CD0h+var_C68]
0x180013852  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013857  lea     rdx, [rsp+0CD0h+var_C68]
0x18001385c  lea     rcx, [r15+8]
0x180013860  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](std::wstring &&)
0x180013865  mov     rcx, rax
0x180013868  lea     rdx, [rsp+0CD0h+var_C88]
0x18001386d  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x180013872  xor     r8d, r8d
0x180013875  lea     rcx, [rsp+0CD0h+var_C68]
0x18001387a  mov     dl, 1
0x18001387c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013881  lea     rcx, [rsp+0CD0h+var_C88]
0x180013886  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18001388b  xor     edx, edx; Val
0x18001388d  lea     rcx, [rbp+0BD0h+Destination]; void *
0x180013894  mov     r8d, 400h; Size
0x18001389a  call    memset_0
0x18001389f  cmp     ebx, 0C00CEE3Ah
0x1800138a5  jnz     loc_18001358A
0x1800138ab  xor     edi, edi
0x1800138ad  jmp     loc_1800135A3
```
