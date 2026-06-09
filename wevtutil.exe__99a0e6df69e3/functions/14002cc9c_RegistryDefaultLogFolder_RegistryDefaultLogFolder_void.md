# RegistryDefaultLogFolder::RegistryDefaultLogFolder(void)

- ea: `0x14002cc9c`
- end: `0x14002d1b7`
- name: `??0RegistryDefaultLogFolder@@QEAA@XZ`
- size: `1307`
- prototype: `RegistryDefaultLogFolder *__fastcall(RegistryDefaultLogFolder *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x14002d5f8`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140005620`
- `0x140006cd0`
- `0x140006db0`
- `0x14000d6e8`
- `0x14001915c`
- `0x14001a9b8`
- `0x14001c368`
- `0x140022cec`
- `0x140023c6c`
- `0x14002c664`
- `0x14002caf8`
- `0x14002cc9c`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ceb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ceb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d013`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14002cea9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14002cea9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002cfc3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002cfc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cdbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cdbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002d12c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002d12c`

## string_xrefs

- `0x14002cf81`: `access_check`
- `0x14002d173`: `%SystemRoot%\System32\Winevt\Logs\`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
RegistryDefaultLogFolder *__fastcall RegistryDefaultLogFolder::RegistryDefaultLogFolder(RegistryDefaultLogFolder *this)
{
  RegistryDefaultLogFolder *v1; // rbx
  __int64 v2; // rcx
  const wchar_t **v3; // r14
  __int64 *v4; // r15
  __int64 v5; // rcx
  unsigned int EventlogServiceRegPath; // eax
  unsigned int v7; // esi
  HKEY *phkResult; // rax
  int StringValueNoThrow; // eax
  LPCWSTR v10; // rcx
  __int64 v11; // rax
  const char *v12; // r8
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  LPCWSTR v17; // rcx
  const char *v18; // r8
  DWORD v19; // r9d
  LPCWSTR v20; // rcx
  __int64 *v21; // rdx
  __int64 v22; // r8
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  _WORD *v26; // rax
  __int64 v27; // [rsp+0h] [rbp-128h] BYREF
  __int64 *v28; // [rsp+40h] [rbp-E8h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-E0h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-C8h]
  __int64 v31; // [rsp+64h] [rbp-C4h]
  char v32; // [rsp+6Ch] [rbp-BCh]
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v35[40]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v36[80]; // [rsp+D8h] [rbp-50h] BYREF
  HKEY v38; // [rsp+138h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+140h] [rbp+18h] BYREF
  const wchar_t **v40; // [rsp+148h] [rbp+20h]

  v1 = this;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(this);
  v3 = (const wchar_t **)(v2 + 32);
  v40 = (const wchar_t **)(v2 + 32);
  *(_QWORD *)(v2 + 32) = 0;
  v4 = (__int64 *)(v2 + 40);
  v28 = (__int64 *)(v2 + 40);
  *(_QWORD *)(v2 + 40) = 0;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(v5, &hKey, lpSubKey);
  try
  {
    v7 = EventlogServiceRegPath;
    if ( EventlogServiceRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_e943c25bf51636622b146f078f7404e1_Traceguids,
          EventlogServiceRegPath);
      }
      pExceptionObject[0] = word_14003838A;
      pExceptionObject[1] = 0;
      pExceptionObject[2] = 0;
      v30 = v7;
      v31 = -1;
      v32 = 0;
      throw (EvtException *)pExceptionObject;
    }
    v38 = 0;
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v38);
    if ( !RegOpenKeyExW(hKey, lpSubKey[0], 0, 0x20019u, phkResult) )
    {
      StringValueNoThrow = RegReadStringValueNoThrow(v38);
      v10 = *(LPCWSTR *)v1;
      if ( StringValueNoThrow )
      {
        *((_QWORD *)v1 + 1) = v10;
        *v10 = 0;
      }
      else
      {
        v11 = (__int64)(*((_QWORD *)v1 + 1) - (_QWORD)v10) >> 1;
        if ( v11
          && v10[v11 - 1] != 92
          && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 v1,
                                 92) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)v35, 0xEu, v12, 75);
          throw (EvtException *)v35;
        }
      }
    }
    if ( byte_140042230 || !((__int64)(*((_QWORD *)v1 + 1) - *(_QWORD *)v1) >> 1) )
      goto LABEL_56;
    FileAttributesW = GetFileAttributesW(*(LPCWSTR *)v1);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      if ( LastError != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)&WPP_e943c25bf51636622b146f078f7404e1_Traceguids,
            LastError,
            *(_QWORD *)v1);
        }
        goto LABEL_32;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 12;
LABEL_27:
        WPP_SF_S(v15[2], v16, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids);
      }
    }
    else
    {
      if ( (FileAttributesW & 0x10) != 0 )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 lpFileName,
                                 *(_QWORD *)v1,
                                 (__int64)(*((_QWORD *)v1 + 1) - *(_QWORD *)v1) >> 1)
          || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpFileName,
                                 L"access_check",
                                 12) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)v36, 0xEu, v18, 111);
          throw (EvtException *)v36;
        }
        hKey = (HKEY)CreateFileW(lpFileName[0], 0x40000000u, 0, 0, 2u, 0x4000100u, 0);
        if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL || (HKEY)((char *)hKey + 1) == (HKEY)1 )
        {
          v19 = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)&WPP_e943c25bf51636622b146f078f7404e1_Traceguids,
              v19,
              *(_QWORD *)v1);
          }
          v20 = *(LPCWSTR *)v1;
          *((_QWORD *)v1 + 1) = *(_QWORD *)v1;
          *v20 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids);
        }
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hKey);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
        goto LABEL_56;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 17;
        goto LABEL_27;
      }
    }
LABEL_32:
    v17 = *(LPCWSTR *)v1;
    *((_QWORD *)v1 + 1) = *(_QWORD *)v1;
    *v17 = 0;
LABEL_56:
    if ( v38 )
      RegCloseKey(v38);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  }
  catch ( ... )
  {
    v21 = &v27;
    v26 = *(_WORD **)this;
    *((_QWORD *)this + 1) = *(_QWORD *)this;
    *v26 = 0;
    v1 = this;
    v3 = v40;
    v4 = v28;
  }
  v23 = *(const wchar_t **)v1;
  v24 = (__int64)(*((_QWORD *)v1 + 1) - *(_QWORD *)v1) >> 1;
  if ( !v24 )
  {
    v24 = 34;
    v23 = L"%SystemRoot%\\System32\\Winevt\\Logs\\";
  }
  *v3 = v23;
  *v4 = v24;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v3);
  }
  return v1;
}

```

## disassembly

```asm
0x14002cc9c  mov     [rsp+arg_0], rcx
0x14002cca1  push    rbx
0x14002cca2  push    rsi
0x14002cca3  push    rdi
0x14002cca4  push    r14
0x14002cca6  push    r15
0x14002cca8  sub     rsp, 100h
0x14002ccaf  mov     rbx, rcx
0x14002ccb2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ccb7  nop
0x14002ccb8  lea     r14, [rcx+20h]
0x14002ccbc  mov     [rsp+128h+arg_18], r14
0x14002ccc4  mov     qword ptr [r14], 0
0x14002cccb  lea     r15, [r14+8]
0x14002cccf  mov     [rsp+128h+var_E8], r15
0x14002ccd4  mov     qword ptr [r15], 0
0x14002ccdb  mov     [rsp+128h+hKey], 0
0x14002cce7  lea     rcx, [rsp+128h+lpSubKey]
0x14002ccef  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ccf4  nop
0x14002ccf5  lea     r8, [rsp+128h+lpSubKey]
0x14002ccfd  lea     rdx, [rsp+128h+hKey]
0x14002cd05  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002cd0a  mov     esi, eax
0x14002cd0c  test    eax, eax
0x14002cd0e  jz      short loc_14002CD88
0x14002cd10  lea     rdi, WPP_GLOBAL_Control
0x14002cd17  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cd1e  cmp     rcx, rdi
0x14002cd21  jz      short loc_14002CD47
0x14002cd23  test    byte ptr [rcx+1Ch], 4
0x14002cd27  jz      short loc_14002CD47
0x14002cd29  cmp     byte ptr [rcx+19h], 2
0x14002cd2d  jb      short loc_14002CD47
0x14002cd2f  mov     edx, 0Ah
0x14002cd34  mov     r9d, eax
0x14002cd37  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002cd3e  mov     rcx, [rcx+10h]
0x14002cd42  call    WPP_SF_d
0x14002cd47  lea     rax, word_14003838A
0x14002cd4e  mov     [rsp+128h+pExceptionObject], rax
0x14002cd53  mov     [rsp+128h+var_D8], 0
0x14002cd5c  mov     [rsp+128h+var_D0], 0
0x14002cd65  mov     [rsp+128h+var_C8], esi
0x14002cd69  mov     [rsp+128h+var_C4], 0FFFFFFFFFFFFFFFFh
0x14002cd72  mov     [rsp+128h+var_BC], 0
0x14002cd77  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002cd7e  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x14002cd83  call    _CxxThrowException_0
0x14002cd88  mov     [rsp+128h+arg_8], 0
0x14002cd94  lea     rcx, [rsp+128h+arg_8]
0x14002cd9c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002cda1  mov     [rsp+128h+phkResult], rax; phkResult
0x14002cda6  mov     r9d, 20019h; samDesired
0x14002cdac  xor     r8d, r8d; ulOptions
0x14002cdaf  mov     rdx, [rsp+128h+lpSubKey]; lpSubKey
0x14002cdb7  mov     rcx, [rsp+128h+hKey]; hKey
0x14002cdbf  call    cs:__imp_RegOpenKeyExW
0x14002cdc5  test    eax, eax
0x14002cdc7  jnz     loc_14002CE89
0x14002cdcd  mov     r9, rbx
0x14002cdd0  lea     r8, aDefaultlogfold; "DefaultLogFolder"
0x14002cdd7  lea     rdx, ValueName
0x14002cdde  mov     rcx, [rsp+128h+arg_8]; hKey
0x14002cde6  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002cdeb  mov     rcx, [rbx]
0x14002cdee  test    eax, eax
0x14002cdf0  jnz     loc_14002CE80
0x14002cdf6  mov     rax, [rbx+8]
0x14002cdfa  sub     rax, rcx
0x14002cdfd  sar     rax, 1
0x14002ce00  jz      loc_14002CE89
0x14002ce06  mov     edx, 5Ch ; '\'
0x14002ce0b  cmp     [rcx+rax*2-2], dx
0x14002ce10  jz      short loc_14002CE89
0x14002ce12  mov     rcx, rbx
0x14002ce15  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002ce1a  test    al, al
0x14002ce1c  jnz     short loc_14002CE89
0x14002ce1e  lea     rdi, WPP_GLOBAL_Control
0x14002ce25  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ce2c  cmp     rcx, rdi
0x14002ce2f  jz      short loc_14002CE56
0x14002ce31  test    byte ptr [rcx+1Ch], 4
0x14002ce35  jz      short loc_14002CE56
0x14002ce37  cmp     byte ptr [rcx+19h], 2
0x14002ce3b  jb      short loc_14002CE56
0x14002ce3d  mov     edx, 0Bh
0x14002ce42  lea     r9d, [rdx+3]
0x14002ce46  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002ce4d  mov     rcx, [rcx+10h]
0x14002ce51  call    WPP_SF_d
0x14002ce56  mov     edx, 0Eh; unsigned int
0x14002ce5b  lea     r9d, [rdx+3Dh]; int
0x14002ce5f  lea     rcx, [rsp+128h+var_78]; this
0x14002ce67  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002ce6c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002ce73  lea     rcx, [rsp+128h+var_78]; pExceptionObject
0x14002ce7b  call    _CxxThrowException_0
0x14002ce80  mov     [rbx+8], rcx
0x14002ce84  xor     eax, eax
0x14002ce86  mov     [rcx], ax
0x14002ce89  cmp     cs:byte_140042230, 0
0x14002ce90  jnz     loc_14002D118
0x14002ce96  mov     rax, [rbx+8]
0x14002ce9a  sub     rax, [rbx]
0x14002ce9d  sar     rax, 1
0x14002cea0  jz      loc_14002D118
0x14002cea6  mov     rcx, [rbx]; lpFileName
0x14002cea9  call    cs:__imp_GetFileAttributesW
0x14002ceaf  cmp     eax, 0FFFFFFFFh
0x14002ceb2  jnz     loc_14002CF49
0x14002ceb8  call    cs:__imp_GetLastError
0x14002cebe  mov     r9d, eax
0x14002cec1  cmp     eax, 2
0x14002cec4  jnz     short loc_14002CEFC
0x14002cec6  lea     rdi, WPP_GLOBAL_Control
0x14002cecd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ced4  cmp     rcx, rdi
0x14002ced7  jz      short loc_14002CF38
0x14002ced9  test    byte ptr [rcx+1Ch], 8
0x14002cedd  jz      short loc_14002CF38
0x14002cedf  cmp     [rcx+19h], al
0x14002cee2  jb      short loc_14002CF38
0x14002cee4  lea     edx, [rax+0Ah]
0x14002cee7  mov     r9, [rbx]
0x14002ceea  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002cef1  mov     rcx, [rcx+10h]
0x14002cef5  call    WPP_SF_S
0x14002cefa  jmp     short loc_14002CF38
0x14002cefc  lea     rdi, WPP_GLOBAL_Control
0x14002cf03  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf0a  cmp     rcx, rdi
0x14002cf0d  jz      short loc_14002CF38
0x14002cf0f  test    byte ptr [rcx+1Ch], 8
0x14002cf13  jz      short loc_14002CF38
0x14002cf15  cmp     byte ptr [rcx+19h], 2
0x14002cf19  jb      short loc_14002CF38
0x14002cf1b  mov     edx, 0Dh
0x14002cf20  mov     rax, [rbx]
0x14002cf23  mov     [rsp+128h+phkResult], rax
0x14002cf28  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002cf2f  mov     rcx, [rcx+10h]
0x14002cf33  call    WPP_SF_DS
0x14002cf38  mov     rcx, [rbx]
0x14002cf3b  mov     [rbx+8], rcx
0x14002cf3f  xor     eax, eax
0x14002cf41  mov     [rcx], ax
0x14002cf44  jmp     loc_14002D11F
0x14002cf49  test    al, 10h
0x14002cf4b  jz      loc_14002D0E3
0x14002cf51  lea     rcx, [rsp+128h+lpFileName]
0x14002cf56  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002cf5b  nop
0x14002cf5c  mov     r8, [rbx+8]
0x14002cf60  sub     r8, [rbx]
0x14002cf63  sar     r8, 1
0x14002cf66  mov     rdx, [rbx]
0x14002cf69  lea     rcx, [rsp+128h+lpFileName]
0x14002cf6e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14002cf73  test    al, al
0x14002cf75  jz      loc_14002D081
0x14002cf7b  mov     r8d, 0Ch
0x14002cf81  lea     rdx, aAccessCheck; "access_check"
0x14002cf88  lea     rcx, [rsp+128h+lpFileName]
0x14002cf8d  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002cf92  test    al, al
0x14002cf94  jz      loc_14002D081
0x14002cf9a  mov     [rsp+128h+hTemplateFile], 0; hTemplateFile
0x14002cfa3  mov     [rsp+128h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x14002cfab  mov     dword ptr [rsp+128h+phkResult], 2; dwCreationDisposition
0x14002cfb3  xor     r9d, r9d; lpSecurityAttributes
0x14002cfb6  xor     r8d, r8d; dwShareMode
0x14002cfb9  mov     edx, 40000000h; dwDesiredAccess
0x14002cfbe  mov     rcx, [rsp+128h+lpFileName]; lpFileName
0x14002cfc3  call    cs:__imp_CreateFileW
0x14002cfc9  mov     [rsp+128h+hKey], rax
0x14002cfd1  inc     rax
0x14002cfd4  cmp     rax, 1
0x14002cfd8  jbe     short loc_14002D013
0x14002cfda  lea     rdi, WPP_GLOBAL_Control
0x14002cfe1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cfe8  cmp     rcx, rdi
0x14002cfeb  jz      short loc_14002D064
0x14002cfed  test    byte ptr [rcx+1Ch], 8
0x14002cff1  jz      short loc_14002D064
0x14002cff3  cmp     byte ptr [rcx+19h], 4
0x14002cff7  jb      short loc_14002D064
0x14002cff9  mov     edx, 0Fh
0x14002cffe  mov     r9, [rbx]
0x14002d001  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d008  mov     rcx, [rcx+10h]
0x14002d00c  call    WPP_SF_S
0x14002d011  jmp     short loc_14002D064
0x14002d013  call    cs:__imp_GetLastError
0x14002d019  mov     r9d, eax
0x14002d01c  lea     rdi, WPP_GLOBAL_Control
0x14002d023  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d02a  cmp     rcx, rdi
0x14002d02d  jz      short loc_14002D058
0x14002d02f  test    byte ptr [rcx+1Ch], 8
0x14002d033  jz      short loc_14002D058
0x14002d035  cmp     byte ptr [rcx+19h], 2
0x14002d039  jb      short loc_14002D058
0x14002d03b  mov     edx, 10h
0x14002d040  mov     rax, [rbx]
0x14002d043  mov     [rsp+128h+phkResult], rax
0x14002d048  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d04f  mov     rcx, [rcx+10h]
0x14002d053  call    WPP_SF_DS
0x14002d058  mov     rcx, [rbx]
0x14002d05b  mov     [rbx+8], rcx
0x14002d05f  xor     eax, eax
0x14002d061  mov     [rcx], ax
0x14002d064  lea     rcx, [rsp+128h+hKey]
0x14002d06c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x14002d071  nop
0x14002d072  lea     rcx, [rsp+128h+lpFileName]
0x14002d077  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002d07c  jmp     loc_14002D11F
0x14002d081  lea     rdi, WPP_GLOBAL_Control
0x14002d088  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d08f  cmp     rcx, rdi
0x14002d092  jz      short loc_14002D0B8
0x14002d094  test    byte ptr [rcx+1Ch], 4
0x14002d098  jz      short loc_14002D0B8
0x14002d09a  cmp     byte ptr [rcx+19h], 2
0x14002d09e  jb      short loc_14002D0B8
0x14002d0a0  mov     edx, 0Eh
0x14002d0a5  mov     r9d, edx
0x14002d0a8  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d0af  mov     rcx, [rcx+10h]
0x14002d0b3  call    WPP_SF_d
0x14002d0b8  mov     edx, 0Eh; unsigned int
0x14002d0bd  lea     r9d, [rdx+61h]; int
0x14002d0c1  lea     rcx, [rsp+128h+var_50]; this
0x14002d0c9  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d0ce  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d0d5  lea     rcx, [rsp+128h+var_50]; pExceptionObject
0x14002d0dd  call    _CxxThrowException_0
0x14002d0e3  lea     rdi, WPP_GLOBAL_Control
0x14002d0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d0f1  cmp     rcx, rdi
0x14002d0f4  jz      loc_14002CF38
0x14002d0fa  test    byte ptr [rcx+1Ch], 8
0x14002d0fe  jz      loc_14002CF38
0x14002d104  cmp     byte ptr [rcx+19h], 2
0x14002d108  jb      loc_14002CF38
0x14002d10e  mov     edx, 11h
0x14002d113  jmp     loc_14002CEE7
0x14002d118  lea     rdi, WPP_GLOBAL_Control
0x14002d11f  mov     rcx, [rsp+128h+arg_8]; hKey
0x14002d127  test    rcx, rcx
0x14002d12a  jz      short loc_14002D133
0x14002d12c  call    cs:__imp_RegCloseKey
0x14002d132  nop
0x14002d133  lea     rcx, [rsp+128h+lpSubKey]
0x14002d13b  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002d140  nop
0x14002d141  jmp     short loc_14002D15F
0x14002d143  lea     rdi, WPP_GLOBAL_Control
0x14002d14a  mov     rbx, [rsp+128h+arg_0]
0x14002d152  mov     r14, [rsp+128h+arg_18]
0x14002d15a  mov     r15, [rsp+128h+var_E8]
0x14002d15f  mov     rcx, [rbx]
0x14002d162  mov     rax, [rbx+8]
0x14002d166  sub     rax, rcx
0x14002d169  sar     rax, 1
0x14002d16c  jnz     short loc_14002D17A
0x14002d16e  mov     eax, 22h ; '"'
0x14002d173  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\Winevt\\Logs\\"
0x14002d17a  mov     [r14], rcx
0x14002d17d  mov     [r15], rax
0x14002d180  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d187  cmp     rcx, rdi
0x14002d18a  jz      short loc_14002D1A5
0x14002d18c  test    byte ptr [rcx+1Ch], 8
0x14002d190  jz      short loc_14002D1A5
0x14002d192  cmp     byte ptr [rcx+19h], 4
0x14002d196  jb      short loc_14002D1A5
0x14002d198  mov     r9, r14
0x14002d19b  mov     rcx, [rcx+10h]
0x14002d19f  call    WPP_SF__utlwsv_
0x14002d1a4  nop
0x14002d1a5  mov     rax, rbx
0x14002d1a8  add     rsp, 100h
0x14002d1af  pop     r15
0x14002d1b1  pop     r14
0x14002d1b3  pop     rdi
0x14002d1b4  pop     rsi
0x14002d1b5  pop     rbx
0x14002d1b6  retn
```
