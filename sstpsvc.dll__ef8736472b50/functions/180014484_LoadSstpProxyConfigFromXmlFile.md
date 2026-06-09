# LoadSstpProxyConfigFromXmlFile

- ea: `0x180014484`
- end: `0x1800148f2`
- name: `LoadSstpProxyConfigFromXmlFile`
- size: `1134`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005e30`
- `0x1800158c0`

## callees

- `0x180008404`
- `0x1800089dc`
- `0x180008b90`
- `0x18001052c`
- `0x180010998`
- `0x180010b08`
- `0x180011cd4`
- `0x1800134bc`
- `0x180013524`
- `0x1800137d4`
- `0x180013fe0`
- `0x180014484`
- `0x18001d1da`
- `0x18001d1e6`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800147f1`
- `msvcrt!wcscpy_s` at `0x1800147f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014510`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014510`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800145f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800145f4`
- `XmlLite!CreateXmlReader` at `0x180014561`
- `XmlLite!CreateXmlReader` at `0x180014561`

## string_xrefs

- `0x180014533`: `LoadSstpProxyConfigFromXmlFile: xml file is not opened`
- `0x180014582`: `LoadSstpProxyConfigFromXmlFile: CreateXmlReader failed with error %d`
- `0x180014657`: `LoadSstpProxyConfigFromXmlFile: SetInput method of IXmlReader object failed with error %d`
- `0x180014697`: `LoadSstpProxyConfigFromXmlFile: Failed to set the XmlReaderProperty_DtdProcessing of IXmlReader object. Error %d`
- `0x18001484c`: `LoadSstpProxyConfigFromXmlFile: GetLocalName method of IXmlReader object failed with error %d`
- `0x18001486e`: `LoadSstpProxyConfigFromXmlFile: GetValue method of IXmlReader object failed with error %d`

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
    if ( (byte_18002E903 & 8) != 0 )
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
      if ( (byte_18002E903 & 8) == 0 )
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
              if ( (byte_18002E903 & 8) == 0 )
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
              if ( (byte_18002E903 & 8) == 0 )
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
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_9;
      LOWORD(v21) = 0;
      FormatRRASErrorString(
        &v21,
        L"LoadSstpProxyConfigFromXmlFile: Failed to set the XmlReaderProperty_DtdProcessing of IXmlReader object. Error %d",
        v4);
    }
LABEL_7:
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v21);
    goto LABEL_9;
  }
  if ( (byte_18002E903 & 8) != 0 )
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
0x180014484  push    rbp
0x180014486  push    rbx
0x180014487  push    rsi
0x180014488  push    rdi
0x180014489  push    r12
0x18001448b  push    r14
0x18001448d  push    r15
0x18001448f  lea     rbp, [rsp-0BA0h]
0x180014497  sub     rsp, 0CA0h
0x18001449e  mov     rax, cs:__security_cookie
0x1800144a5  xor     rax, rsp
0x1800144a8  mov     [rbp+0BD0h+var_40], rax
0x1800144af  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x1800144b4  mov     rcx, rax; this
0x1800144b7  mov     r15, rax
0x1800144ba  call    ?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ; TenantGatewayMap::GetFileStream(void)
0x1800144bf  xor     ecx, ecx
0x1800144c1  mov     [rsp+0CD0h+ppvObject], 0
0x1800144ca  mov     [rbp+0BD0h+var_C40], ecx
0x1800144cd  xorps   xmm0, xmm0
0x1800144d0  lea     rcx, [rbp+0BD0h+var_C3C]; void *
0x1800144d4  mov     [rsp+0CD0h+var_CA8], 0
0x1800144dc  xor     edx, edx; Val
0x1800144de  mov     [rsp+0CD0h+String1], 0
0x1800144e7  mov     r8d, 7FCh; Size
0x1800144ed  mov     [rsp+0CD0h+Source], 0
0x1800144f6  mov     rdi, rax
0x1800144f9  mov     [rsp+0CD0h+var_C78], 0
0x180014502  movdqu  [rsp+0CD0h+var_C88], xmm0
0x180014508  call    memset_0
0x18001450d  mov     rcx, r15; SRWLock
0x180014510  call    cs:__imp_AcquireSRWLockExclusive
0x180014517  nop     dword ptr [rax+rax+00h]
0x18001451c  test    rdi, rdi
0x18001451f  jnz     short loc_180014552
0x180014521  test    cs:byte_18002E903, 8
0x180014528  mov     edi, 2
0x18001452d  jz      loc_1800145D2
0x180014533  lea     r8, aLoadsstpproxyc_1; "LoadSstpProxyConfigFromXmlFile: xml fil"...
0x18001453a  lea     rdx, RasSSTPSvcTraceError
0x180014541  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014548  call    McTemplateU0z_EventWriteTransfer
0x18001454d  jmp     loc_1800145D2
0x180014552  xor     r8d, r8d; pMalloc
0x180014555  lea     rdx, [rsp+0CD0h+ppvObject]; ppvObject
0x18001455a  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180014561  call    cs:__imp_CreateXmlReader
0x180014568  nop     dword ptr [rax+rax+00h]
0x18001456d  mov     ebx, eax
0x18001456f  test    eax, eax
0x180014571  jz      loc_18001462E
0x180014577  test    cs:byte_18002E903, 8
0x18001457e  jz      short loc_1800145B9
0x180014580  xor     ecx, ecx
0x180014582  lea     rdx, aLoadsstpproxyc_4; "LoadSstpProxyConfigFromXmlFile: CreateX"...
0x180014589  mov     word ptr [rbp+0BD0h+var_C40], cx
0x18001458d  mov     r8d, eax
0x180014590  lea     rcx, [rbp+0BD0h+var_C40]
0x180014594  call    FormatRRASErrorString
0x180014599  test    cs:byte_18002E903, 8
0x1800145a0  jz      short loc_1800145B9
0x1800145a2  lea     r8, [rbp+0BD0h+var_C40]
0x1800145a6  lea     rdx, RasSSTPSvcTraceError
0x1800145ad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800145b4  call    McTemplateU0z_EventWriteTransfer
0x1800145b9  xor     edi, edi
0x1800145bb  test    ebx, ebx
0x1800145bd  jns     short loc_1800145D2
0x1800145bf  mov     eax, ebx
0x1800145c1  movzx   edi, bx
0x1800145c4  and     eax, 1FFF0000h
0x1800145c9  cmp     eax, 70000h
0x1800145ce  jz      short loc_1800145D2
0x1800145d0  mov     edi, ebx
0x1800145d2  mov     rcx, [rsp+0CD0h+ppvObject]
0x1800145d7  test    rcx, rcx
0x1800145da  jz      short loc_1800145E8
0x1800145dc  mov     rdx, [rcx]
0x1800145df  mov     rax, [rdx+10h]
0x1800145e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145e8  mov     rcx, r15; SRWLock
0x1800145eb  mov     [rsp+0CD0h+ppvObject], 0
0x1800145f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800145fb  nop     dword ptr [rax+rax+00h]
0x180014600  lea     rcx, [rsp+0CD0h+var_C88]
0x180014605  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001460a  mov     eax, edi
0x18001460c  mov     rcx, [rbp+0BD0h+var_40]
0x180014613  xor     rcx, rsp; StackCookie
0x180014616  call    __security_check_cookie
0x18001461b  add     rsp, 0CA0h
0x180014622  pop     r15
0x180014624  pop     r14
0x180014626  pop     r12
0x180014628  pop     rdi
0x180014629  pop     rsi
0x18001462a  pop     rbx
0x18001462b  pop     rbp
0x18001462c  retn
0x18001462e  mov     rcx, [rsp+0CD0h+ppvObject]
0x180014633  mov     rdx, rdi
0x180014636  mov     rax, [rcx]
0x180014639  mov     rax, [rax+18h]
0x18001463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014642  mov     ebx, eax
0x180014644  test    eax, eax
0x180014646  jz      short loc_18001466A
0x180014648  test    cs:byte_18002E903, 8
0x18001464f  jz      loc_1800145B9
0x180014655  xor     eax, eax
0x180014657  lea     rdx, aLoadsstpproxyc_2; "LoadSstpProxyConfigFromXmlFile: SetInpu"...
0x18001465e  mov     word ptr [rbp+0BD0h+var_C40], ax
0x180014662  mov     r8d, ebx
0x180014665  jmp     loc_180014590
0x18001466a  mov     rcx, [rsp+0CD0h+ppvObject]
0x18001466f  xor     r8d, r8d
0x180014672  mov     rax, [rcx]
0x180014675  lea     edx, [r8+4]
0x180014679  mov     rax, [rax+28h]
0x18001467d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014682  mov     ebx, eax
0x180014684  test    eax, eax
0x180014686  jz      short loc_1800146AA
0x180014688  test    cs:byte_18002E903, 8
0x18001468f  jz      loc_1800145B9
0x180014695  xor     eax, eax
0x180014697  lea     rdx, aLoadsstpproxyc; "LoadSstpProxyConfigFromXmlFile: Failed "...
0x18001469e  mov     word ptr [rbp+0BD0h+var_C40], ax
0x1800146a2  mov     r8d, ebx
0x1800146a5  jmp     loc_180014590
0x1800146aa  xor     r14b, r14b
0x1800146ad  xor     dil, dil
0x1800146b0  xor     sil, sil
0x1800146b3  mov     rcx, [rsp+0CD0h+ppvObject]
0x1800146b8  lea     rdx, [rsp+0CD0h+var_CA8]
0x1800146bd  mov     rax, [rcx]
0x1800146c0  mov     rax, [rax+30h]
0x1800146c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c9  mov     ebx, eax
0x1800146cb  test    eax, eax
0x1800146cd  jnz     loc_180014881
0x1800146d3  cmp     [rsp+0CD0h+var_CA8], 1
0x1800146d8  jnz     loc_1800147AA
0x1800146de  mov     rcx, [rsp+0CD0h+ppvObject]
0x1800146e3  lea     rdx, [rsp+0CD0h+String1]
0x1800146e8  xor     r8d, r8d
0x1800146eb  mov     rax, [rcx]
0x1800146ee  mov     rax, [rax+70h]
0x1800146f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146f7  mov     ebx, eax
0x1800146f9  test    eax, eax
0x1800146fb  jnz     loc_18001483D
0x180014701  mov     rcx, [rsp+0CD0h+String1]; String1
0x180014706  lea     rdx, aTenant; "Tenant"
0x18001470d  call    wcscmp_0
0x180014712  test    eax, eax
0x180014714  jnz     short loc_180014781
0x180014716  test    r14b, r14b
0x180014719  jz      short loc_180014776
0x18001471b  lea     rdx, [rbp+0BD0h+Destination]
0x180014722  lea     rcx, [rsp+0CD0h+var_C68]
0x180014727  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001472c  lea     rdx, [rsp+0CD0h+var_C68]
0x180014731  lea     rcx, [r15+8]
0x180014735  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](std::wstring &&)
0x18001473a  mov     rcx, rax
0x18001473d  lea     rdx, [rsp+0CD0h+var_C88]
0x180014742  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x180014747  xor     r8d, r8d
0x18001474a  lea     rcx, [rsp+0CD0h+var_C68]
0x18001474f  mov     dl, 1
0x180014751  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014756  lea     rcx, [rsp+0CD0h+var_C88]
0x18001475b  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180014760  xor     edx, edx; Val
0x180014762  lea     rcx, [rbp+0BD0h+Destination]; void *
0x180014769  mov     r8d, 400h; Size
0x18001476f  call    memset_0
0x180014774  jmp     short loc_180014779
0x180014776  mov     r14b, 1
0x180014779  mov     dil, 1
0x18001477c  xor     sil, sil
0x18001477f  jmp     short loc_18001479C
0x180014781  mov     rcx, [rsp+0CD0h+String1]; String1
0x180014786  lea     rdx, aGateway; "Gateway"
0x18001478d  call    wcscmp_0
0x180014792  test    eax, eax
0x180014794  jnz     short loc_18001479C
0x180014796  xor     dil, dil
0x180014799  mov     sil, 1
0x18001479c  mov     [rsp+0CD0h+String1], 0
0x1800147a5  jmp     loc_1800146B3
0x1800147aa  cmp     [rsp+0CD0h+var_CA8], 3
0x1800147af  jnz     loc_1800146AD
0x1800147b5  mov     rcx, [rsp+0CD0h+ppvObject]
0x1800147ba  lea     rdx, [rsp+0CD0h+Source]
0x1800147bf  xor     r8d, r8d
0x1800147c2  mov     rax, [rcx]
0x1800147c5  mov     rax, [rax+80h]
0x1800147cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147d1  mov     ebx, eax
0x1800147d3  test    eax, eax
0x1800147d5  jnz     loc_18001485F
0x1800147db  test    dil, dil
0x1800147de  jz      short loc_180014802
0x1800147e0  mov     r8, [rsp+0CD0h+Source]; Source
0x1800147e5  lea     rcx, [rbp+0BD0h+Destination]; Destination
0x1800147ec  mov     edx, 200h; SizeInWords
0x1800147f1  call    cs:__imp_wcscpy_s
0x1800147f8  nop     dword ptr [rax+rax+00h]
0x1800147fd  jmp     loc_1800146B3
0x180014802  test    sil, sil
0x180014805  jz      loc_1800146B3
0x18001480b  mov     rdx, [rsp+0CD0h+Source]
0x180014810  lea     rcx, [rsp+0CD0h+var_C68]
0x180014815  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001481a  lea     rdx, [rsp+0CD0h+var_C68]
0x18001481f  lea     rcx, [rsp+0CD0h+var_C88]
0x180014824  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180014829  xor     r8d, r8d
0x18001482c  lea     rcx, [rsp+0CD0h+var_C68]
0x180014831  mov     dl, 1
0x180014833  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014838  jmp     loc_1800146B3
0x18001483d  test    cs:byte_18002E903, 8
0x180014844  jz      loc_1800145B9
0x18001484a  xor     eax, eax
0x18001484c  lea     rdx, aLoadsstpproxyc_0; "LoadSstpProxyConfigFromXmlFile: GetLoca"...
0x180014853  mov     word ptr [rbp+0BD0h+var_C40], ax
0x180014857  mov     r8d, ebx
0x18001485a  jmp     loc_180014590
0x18001485f  test    cs:byte_18002E903, 8
0x180014866  jz      loc_1800145B9
0x18001486c  xor     eax, eax
0x18001486e  lea     rdx, aLoadsstpproxyc_3; "LoadSstpProxyConfigFromXmlFile: GetValu"...
0x180014875  mov     word ptr [rbp+0BD0h+var_C40], ax
0x180014879  mov     r8d, ebx
0x18001487c  jmp     loc_180014590
0x180014881  test    r14b, r14b
0x180014884  jz      short loc_1800148DF
0x180014886  lea     rdx, [rbp+0BD0h+Destination]
0x18001488d  lea     rcx, [rsp+0CD0h+var_C68]
0x180014892  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014897  lea     rdx, [rsp+0CD0h+var_C68]
0x18001489c  lea     rcx, [r15+8]
0x1800148a0  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](std::wstring &&)
0x1800148a5  mov     rcx, rax
0x1800148a8  lea     rdx, [rsp+0CD0h+var_C88]
0x1800148ad  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x1800148b2  xor     r8d, r8d
0x1800148b5  lea     rcx, [rsp+0CD0h+var_C68]
0x1800148ba  mov     dl, 1
0x1800148bc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800148c1  lea     rcx, [rsp+0CD0h+var_C88]
0x1800148c6  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x1800148cb  xor     edx, edx; Val
0x1800148cd  lea     rcx, [rbp+0BD0h+Destination]; void *
0x1800148d4  mov     r8d, 400h; Size
0x1800148da  call    memset_0
0x1800148df  cmp     ebx, 0C00CEE3Ah
0x1800148e5  jnz     loc_1800145B9
0x1800148eb  xor     edi, edi
0x1800148ed  jmp     loc_1800145D2
```
