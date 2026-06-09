# ManifestProcessor::InstallImportedChannel(AbstractDomElement &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)

- ea: `0x14002ab70`
- end: `0x14002b102`
- name: `?InstallImportedChannel@ManifestProcessor@@AEAAXAEAVAbstractDomElement@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBV34@@Z`
- size: `1426`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140017618`

## callees

- `0x140003480`
- `0x140004ae0`
- `0x140005600`
- `0x140006cd0`
- `0x140006db0`
- `0x140007db0`
- `0x14000a4d8`
- `0x14000cc80`
- `0x14000d6e8`
- `0x140019094`
- `0x140019348`
- `0x14001a9b8`
- `0x140021b00`
- `0x140022510`
- `0x140022cec`
- `0x14002ab70`
- `0x14002ba80`
- `0x14002f6c8`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002aef4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002aef4`
- `ntdll!RtlGetVersion` at `0x14002adb3`
- `ntdll!RtlGetVersion` at `0x14002adb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b090`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b090`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002af37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002afde`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002af37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002afde`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ManifestProcessor::InstallImportedChannel(_QWORD *a1, __int64 a2, __int64 *a3, __int64 a4)
{
  const char *v6; // r8
  __int64 v7; // rax
  HKEY v8; // r15
  __int64 v9; // rbx
  __int64 v11; // rcx
  unsigned int LegacyChannelRegPath; // eax
  unsigned int v13; // ebx
  const char *v14; // r8
  void *v15; // rbx
  HKEY *v16; // rax
  unsigned int RegKey; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  unsigned int v22; // ebx
  __int16 *pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  unsigned int v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+5Ch] [rbp-A4h]
  char v28; // [rsp+64h] [rbp-9Ch]
  unsigned int v29; // [rsp+68h] [rbp-98h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  HKEY v32[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h]
  wchar_t *v34[5]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v35[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v36[4]; // [rsp+D0h] [rbp-30h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-10h] BYREF

  v33 = a4;
  (*(void (__fastcall **)(__int64, __int64 *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(a2, &v31, L"name");
  if ( !v31 )
  {
    eventlog::ai::WarningMessage((eventlog::ai *)0x49, *a3, a1[6]);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, v6, 475);
    throw (EvtException *)&pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v8 = (HKEY)v7;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v7 + 2 * v9) );
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
      v7,
      *a3);
  }
  v32[0] = v8;
  v32[1] = (HKEY)v9;
  if ( (unsigned __int8)IsCoreChannel(v32) )
  {
    v32[0] = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
    v35[0] = v8;
    v35[1] = v9;
    LegacyChannelRegPath = RegistryPaths::GetLegacyChannelRegPath(v11, v35, v32, v36);
    v13 = LegacyChannelRegPath;
    if ( LegacyChannelRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
          LegacyChannelRegPath);
      }
      pExceptionObject = word_14003838A;
      v24 = 0;
      v25 = 0;
      v26 = v13;
      v27 = -1;
      v28 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    v29 = 131078;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( RtlGetVersion(&VersionInformation) >= 0
      && (VersionInformation.dwMajorVersion > 6
       || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion) )
    {
      v29 = 131334;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(v34, 48);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v34,
                             v36[0],
                             (__int64)(v36[1] - v36[0]) >> 1)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             v34,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             v34,
                             a1[6],
                             (__int64)(a1[7] - a1[6]) >> 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v14, 518);
      throw (EvtException *)&pExceptionObject;
    }
    hKey = 0;
    v15 = (void *)a1[1];
    v16 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    RegKey = CreateRegKey(v32[0], v34[0], v29, 0, v16, 0, v15);
    v18 = RegKey;
    if ( RegKey )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, RegKey);
      }
      pExceptionObject = word_14003838A;
      v24 = 0;
      v25 = 0;
      v26 = v18;
      v27 = -1;
      v28 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( (unsigned int)_o__wcsicmp(a1[6], L"ntfs") )
    {
      v19 = RegSetValueExW(hKey, L"ProviderGuid", 0, 1u, (const BYTE *)*a3, 2 * ((a3[1] - *a3) >> 1) + 2);
      v20 = v19;
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v19);
        }
        pExceptionObject = word_14003838A;
        v24 = 0;
        v25 = 0;
        v26 = v20;
        v27 = -1;
        v28 = 0;
        throw (EvtException *)&pExceptionObject;
      }
    }
    v21 = RegSetValueExW(
            hKey,
            L"EventMessageFile",
            0,
            2u,
            *(const BYTE **)v33,
            2 * ((__int64)(*(_QWORD *)(v33 + 8) - *(_QWORD *)v33) >> 1) + 2);
    v22 = v21;
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v21);
      }
      pExceptionObject = word_14003838A;
      v24 = 0;
      v25 = 0;
      v26 = v22;
      v27 = -1;
      v28 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
        (_DWORD)v8,
        *a3);
    }
    if ( hKey )
      RegCloseKey(hKey);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
  }
  else
  {
    eventlog::ai::WarningMessage((eventlog::ai *)0x5E, a1[6], v8);
  }
  return wmi::AutoRef<AbstractDomAttribute>::Release(&v31);
}

```

## disassembly

```asm
0x14002ab70  push    rbp
0x14002ab72  push    rbx
0x14002ab73  push    rsi
0x14002ab74  push    rdi
0x14002ab75  push    r12
0x14002ab77  push    r13
0x14002ab79  push    r14
0x14002ab7b  push    r15
0x14002ab7d  lea     rbp, [rsp-128h]
0x14002ab85  sub     rsp, 228h
0x14002ab8c  mov     rax, cs:__security_cookie
0x14002ab93  xor     rax, rsp
0x14002ab96  mov     [rbp+160h+var_50], rax
0x14002ab9d  mov     [rbp+160h+var_1D0], r9
0x14002aba1  mov     r12, r8
0x14002aba4  mov     r10, rdx
0x14002aba7  mov     r13, rcx
0x14002abaa  mov     rax, [rdx]
0x14002abad  lea     r8, aName_0; "name"
0x14002abb4  lea     rdx, [rsp+260h+var_1E8]
0x14002abb9  mov     rcx, r10
0x14002abbc  mov     rax, [rax+28h]
0x14002abc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002abc5  nop
0x14002abc6  mov     rcx, [rsp+260h+var_1E8]
0x14002abcb  xor     edi, edi
0x14002abcd  test    rcx, rcx
0x14002abd0  jnz     short loc_14002AC41
0x14002abd2  mov     r8, [r13+30h]
0x14002abd6  mov     rdx, [r12]; unsigned int
0x14002abda  lea     ecx, [rdi+49h]; this
0x14002abdd  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x14002abe2  lea     rsi, WPP_GLOBAL_Control
0x14002abe9  lea     ebx, [rdi+0Dh]
0x14002abec  mov     rcx, cs:WPP_GLOBAL_Control
0x14002abf3  cmp     rcx, rsi
0x14002abf6  jz      short loc_14002AC1D
0x14002abf8  mov     dil, 4
0x14002abfb  test    [rcx+1Ch], dil
0x14002abff  jz      short loc_14002AC1D
0x14002ac01  cmp     byte ptr [rcx+19h], 2
0x14002ac05  jb      short loc_14002AC1D
0x14002ac07  lea     edx, [rbx+12h]
0x14002ac0a  mov     r9d, ebx
0x14002ac0d  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14002ac14  mov     rcx, [rcx+10h]
0x14002ac18  call    WPP_SF_d
0x14002ac1d  mov     r9d, 1DBh; int
0x14002ac23  mov     edx, ebx; unsigned int
0x14002ac25  lea     rcx, [rsp+260h+pExceptionObject]; this
0x14002ac2a  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002ac2f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002ac36  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x14002ac3b  call    _CxxThrowException_0
0x14002ac41  mov     rax, [rcx]
0x14002ac44  mov     rax, [rax+10h]
0x14002ac48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac4d  mov     r15, rax
0x14002ac50  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002ac54  inc     rbx
0x14002ac57  cmp     [rax+rbx*2], di
0x14002ac5b  jnz     short loc_14002AC54
0x14002ac5d  lea     rsi, WPP_GLOBAL_Control
0x14002ac64  lea     r14, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14002ac6b  mov     dil, 4
0x14002ac6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ac75  cmp     rcx, rsi
0x14002ac78  jz      short loc_14002ACA3
0x14002ac7a  test    [rcx+1Ch], dil
0x14002ac7e  jz      short loc_14002ACA3
0x14002ac80  cmp     byte ptr [rcx+19h], 5
0x14002ac84  jb      short loc_14002ACA3
0x14002ac86  mov     edx, 20h ; ' '
0x14002ac8b  mov     rax, [r12]
0x14002ac8f  mov     [rsp+260h+lpData], rax
0x14002ac94  mov     r9, r15
0x14002ac97  mov     r8, r14
0x14002ac9a  mov     rcx, [rcx+10h]
0x14002ac9e  call    WPP_SF_SS
0x14002aca3  mov     [rbp+160h+var_1E0], r15
0x14002aca7  mov     [rbp+160h+var_1D8], rbx
0x14002acab  lea     rcx, [rbp+160h+var_1E0]
0x14002acaf  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002acb4  test    al, al
0x14002acb6  jnz     short loc_14002ACF7
0x14002acb8  mov     r8, r15
0x14002acbb  mov     rdx, [r13+30h]; unsigned int
0x14002acbf  mov     ecx, 5Eh ; '^'; this
0x14002acc4  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x14002acc9  nop
0x14002acca  lea     rcx, [rsp+260h+var_1E8]
0x14002accf  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x14002acd4  mov     rcx, [rbp+160h+var_50]
0x14002acdb  xor     rcx, rsp; StackCookie
0x14002acde  call    __security_check_cookie
0x14002ace3  add     rsp, 228h
0x14002acea  pop     r15
0x14002acec  pop     r14
0x14002acee  pop     r13
0x14002acf0  pop     r12
0x14002acf2  pop     rdi
0x14002acf3  pop     rsi
0x14002acf4  pop     rbx
0x14002acf5  pop     rbp
0x14002acf6  retn
0x14002acf7  mov     [rbp+160h+var_1E0], 0
0x14002acff  lea     rcx, [rbp+160h+var_190]
0x14002ad03  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ad08  nop
0x14002ad09  mov     [rbp+160h+var_1A0], r15
0x14002ad0d  mov     [rbp+160h+var_198], rbx
0x14002ad11  lea     r9, [rbp+160h+var_190]
0x14002ad15  lea     r8, [rbp+160h+var_1E0]
0x14002ad19  lea     rdx, [rbp+160h+var_1A0]
0x14002ad1d  call    ?GetLegacyChannelRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z; RegistryPaths::GetLegacyChannelRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002ad22  mov     ebx, eax
0x14002ad24  test    eax, eax
0x14002ad26  jz      short loc_14002AD8F
0x14002ad28  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad2f  cmp     rcx, rsi
0x14002ad32  jz      short loc_14002AD54
0x14002ad34  test    [rcx+1Ch], dil
0x14002ad38  jz      short loc_14002AD54
0x14002ad3a  cmp     byte ptr [rcx+19h], 2
0x14002ad3e  jb      short loc_14002AD54
0x14002ad40  mov     edx, 21h ; '!'
0x14002ad45  mov     r9d, eax
0x14002ad48  mov     r8, r14
0x14002ad4b  mov     rcx, [rcx+10h]
0x14002ad4f  call    WPP_SF_d
0x14002ad54  lea     rax, word_14003838A
0x14002ad5b  mov     [rsp+260h+pExceptionObject], rax
0x14002ad60  xor     eax, eax
0x14002ad62  mov     [rsp+260h+var_218], rax
0x14002ad67  mov     [rsp+260h+var_210], rax
0x14002ad6c  mov     [rsp+260h+var_208], ebx
0x14002ad70  mov     [rsp+260h+var_204], 0FFFFFFFFFFFFFFFFh
0x14002ad79  mov     [rsp+260h+var_1FC], al
0x14002ad7d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002ad84  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x14002ad89  call    _CxxThrowException_0
0x14002ad8f  mov     [rsp+260h+var_1F8], 20006h
0x14002ad97  xor     edx, edx; Val
0x14002ad99  mov     r8d, 110h; Size
0x14002ad9f  lea     rcx, [rbp+160h+VersionInformation.dwMajorVersion]; void *
0x14002ada3  call    memset_0
0x14002ada8  mov     [rbp+160h+VersionInformation.dwOSVersionInfoSize], 114h
0x14002adaf  lea     rcx, [rbp+160h+VersionInformation]; lpVersionInformation
0x14002adb3  call    cs:__imp_RtlGetVersion
0x14002adb9  xor     ebx, ebx
0x14002adbb  test    eax, eax
0x14002adbd  js      short loc_14002ADD5
0x14002adbf  cmp     [rbp+160h+VersionInformation.dwMajorVersion], 6
0x14002adc3  ja      short loc_14002ADCD
0x14002adc5  jnz     short loc_14002ADD5
0x14002adc7  cmp     [rbp+160h+VersionInformation.dwMinorVersion], 1
0x14002adcb  jb      short loc_14002ADD5
0x14002adcd  mov     [rsp+260h+var_1F8], 20106h
0x14002add5  lea     rcx, [rbp+160h+var_1C8]
0x14002add9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002adde  nop
0x14002addf  mov     edx, 30h ; '0'
0x14002ade4  lea     rcx, [rbp+160h+var_1C8]
0x14002ade8  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x14002aded  mov     r8, [rbp+160h+var_188]
0x14002adf1  mov     rdx, [rbp+160h+var_190]
0x14002adf5  sub     r8, rdx
0x14002adf8  sar     r8, 1
0x14002adfb  lea     rcx, [rbp+160h+var_1C8]
0x14002adff  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14002ae04  test    al, al
0x14002ae06  jz      loc_14002B0AF
0x14002ae0c  mov     edx, 5Ch ; '\'
0x14002ae11  lea     rcx, [rbp+160h+var_1C8]
0x14002ae15  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002ae1a  test    al, al
0x14002ae1c  jz      loc_14002B0AF
0x14002ae22  mov     rdx, [r13+30h]
0x14002ae26  mov     r8, [r13+38h]
0x14002ae2a  sub     r8, rdx
0x14002ae2d  sar     r8, 1
0x14002ae30  lea     rcx, [rbp+160h+var_1C8]
0x14002ae34  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002ae39  test    al, al
0x14002ae3b  jz      loc_14002B0AF
0x14002ae41  mov     [rsp+260h+hKey], rbx
0x14002ae46  mov     rbx, [r13+8]
0x14002ae4a  lea     rcx, [rsp+260h+hKey]
0x14002ae4f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002ae54  mov     [rsp+260h+var_230], rbx; void *
0x14002ae59  mov     qword ptr [rsp+260h+cbData], 0; unsigned int *
0x14002ae62  mov     [rsp+260h+lpData], rax; HKEY *
0x14002ae67  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x14002ae6a  mov     r8d, [rsp+260h+var_1F8]; unsigned int
0x14002ae6f  mov     rdx, [rbp+160h+var_1C8]; wchar_t *
0x14002ae73  mov     rcx, [rbp+160h+var_1E0]; HKEY
0x14002ae77  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x14002ae7c  mov     ebx, eax
0x14002ae7e  test    eax, eax
0x14002ae80  jz      short loc_14002AEE9
0x14002ae82  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ae89  cmp     rcx, rsi
0x14002ae8c  jz      short loc_14002AEAE
0x14002ae8e  test    [rcx+1Ch], dil
0x14002ae92  jz      short loc_14002AEAE
0x14002ae94  cmp     byte ptr [rcx+19h], 2
0x14002ae98  jb      short loc_14002AEAE
0x14002ae9a  mov     edx, 23h ; '#'
0x14002ae9f  mov     r9d, eax
0x14002aea2  mov     r8, r14
0x14002aea5  mov     rcx, [rcx+10h]
0x14002aea9  call    WPP_SF_d
0x14002aeae  lea     rax, word_14003838A
0x14002aeb5  mov     [rsp+260h+pExceptionObject], rax
0x14002aeba  xor     eax, eax
0x14002aebc  mov     [rsp+260h+var_218], rax
0x14002aec1  mov     [rsp+260h+var_210], rax
0x14002aec6  mov     [rsp+260h+var_208], ebx
0x14002aeca  mov     [rsp+260h+var_204], 0FFFFFFFFFFFFFFFFh
0x14002aed3  mov     [rsp+260h+var_1FC], al
0x14002aed7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002aede  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x14002aee3  call    _CxxThrowException_0
0x14002aee9  lea     rdx, aNtfs; "ntfs"
0x14002aef0  mov     rcx, [r13+30h]
0x14002aef4  call    cs:__imp__o__wcsicmp
0x14002aefa  xor     r13d, r13d
0x14002aefd  test    eax, eax
0x14002aeff  jz      loc_14002AFA8
0x14002af05  mov     rdx, [r12]
0x14002af09  mov     rax, [r12+8]
0x14002af0e  sub     rax, rdx
0x14002af11  sar     rax, 1
0x14002af14  lea     eax, ds:2[rax*2]
0x14002af1b  mov     [rsp+260h+cbData], eax; cbData
0x14002af1f  mov     [rsp+260h+lpData], rdx; lpData
0x14002af24  lea     r9d, [r13+1]; dwType
0x14002af28  xor     r8d, r8d; Reserved
0x14002af2b  lea     rdx, aProviderguid; "ProviderGuid"
0x14002af32  mov     rcx, [rsp+260h+hKey]; hKey
0x14002af37  call    cs:__imp_RegSetValueExW
0x14002af3d  mov     ebx, eax
0x14002af3f  test    eax, eax
0x14002af41  jz      short loc_14002AFA8
0x14002af43  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af4a  cmp     rcx, rsi
0x14002af4d  jz      short loc_14002AF6E
0x14002af4f  test    [rcx+1Ch], dil
0x14002af53  jz      short loc_14002AF6E
0x14002af55  cmp     byte ptr [rcx+19h], 2
0x14002af59  jb      short loc_14002AF6E
0x14002af5b  lea     edx, [r13+24h]
0x14002af5f  mov     r9d, eax
0x14002af62  mov     r8, r14
0x14002af65  mov     rcx, [rcx+10h]
0x14002af69  call    WPP_SF_d
0x14002af6e  lea     rax, word_14003838A
0x14002af75  mov     [rsp+260h+pExceptionObject], rax
0x14002af7a  mov     [rsp+260h+var_218], r13
0x14002af7f  mov     [rsp+260h+var_210], r13
0x14002af84  mov     [rsp+260h+var_208], ebx
0x14002af88  mov     [rsp+260h+var_204], 0FFFFFFFFFFFFFFFFh
0x14002af91  mov     [rsp+260h+var_1FC], r13b
0x14002af96  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002af9d  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x14002afa2  call    _CxxThrowException_0
0x14002afa8  mov     rax, [rbp+160h+var_1D0]
0x14002afac  mov     rdx, [rax]
0x14002afaf  mov     rax, [rax+8]
0x14002afb3  sub     rax, rdx
0x14002afb6  sar     rax, 1
0x14002afb9  lea     eax, ds:2[rax*2]
0x14002afc0  mov     [rsp+260h+cbData], eax; cbData
0x14002afc4  mov     [rsp+260h+lpData], rdx; lpData
0x14002afc9  mov     r9d, 2; dwType
0x14002afcf  xor     r8d, r8d; Reserved
0x14002afd2  lea     rdx, aEventmessagefi; "EventMessageFile"
0x14002afd9  mov     rcx, [rsp+260h+hKey]; hKey
0x14002afde  call    cs:__imp_RegSetValueExW
0x14002afe4  mov     ebx, eax
0x14002afe6  test    eax, eax
0x14002afe8  jz      short loc_14002B050
0x14002afea  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aff1  cmp     rcx, rsi
0x14002aff4  jz      short loc_14002B016
0x14002aff6  test    [rcx+1Ch], dil
0x14002affa  jz      short loc_14002B016
0x14002affc  cmp     byte ptr [rcx+19h], 2
0x14002b000  jb      short loc_14002B016
0x14002b002  mov     edx, 25h ; '%'
0x14002b007  mov     r9d, eax
0x14002b00a  mov     r8, r14
0x14002b00d  mov     rcx, [rcx+10h]
0x14002b011  call    WPP_SF_d
0x14002b016  lea     rax, word_14003838A
0x14002b01d  mov     [rsp+260h+pExceptionObject], rax
0x14002b022  mov     [rsp+260h+var_218], r13
0x14002b027  mov     [rsp+260h+var_210], r13
0x14002b02c  mov     [rsp+260h+var_208], ebx
0x14002b030  mov     [rsp+260h+var_204], 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
