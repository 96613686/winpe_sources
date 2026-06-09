# RegistryDefaultLogFolder::RegistryDefaultLogFolder(void)

- ea: `0x1800be7d0`
- end: `0x1800bed28`
- name: `??0RegistryDefaultLogFolder@@QEAA@XZ`
- size: `1368`
- prototype: `RegistryDefaultLogFolder *__fastcall(RegistryDefaultLogFolder *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180028bbc`

## callees

- `0x180006770`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x18002afa8`
- `0x18002c6f4`
- `0x18002d204`
- `0x18002d6dc`
- `0x18003420c`
- `0x180077ad0`
- `0x180083f2c`
- `0x18008d8a8`
- `0x180092008`
- `0x180098c50`
- `0x1800be7d0`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be8e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beb5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beb5b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800be9ea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800be9ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800beb0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800beb0b`

## string_xrefs

- `0x1800beac7`: `access_check`
- `0x1800becd6`: `%SystemRoot%\System32\Winevt\Logs\`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
RegistryDefaultLogFolder *__fastcall RegistryDefaultLogFolder::RegistryDefaultLogFolder(RegistryDefaultLogFolder *this)
{
  RegistryDefaultLogFolder *v1; // rbx
  const wchar_t **v2; // r14
  __int64 *v3; // r15
  __int64 v4; // rcx
  unsigned int EventlogServiceRegPath; // eax
  unsigned int v6; // esi
  HKEY *phkResult; // rax
  int StringValueNoThrow; // eax
  LPCWSTR v9; // rcx
  __int64 v10; // rax
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  LPCWSTR v15; // rcx
  DWORD v16; // r9d
  LPCWSTR v17; // rcx
  const wchar_t *v18; // rcx
  __int64 v19; // rax
  _WORD *v21; // rax
  __int64 *v22; // [rsp+40h] [rbp-F8h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-F0h] BYREF
  unsigned int v24; // [rsp+60h] [rbp-D8h]
  __int64 v25; // [rsp+64h] [rbp-D4h]
  char v26; // [rsp+6Ch] [rbp-CCh]
  __int128 v27; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+80h] [rbp-B8h]
  int v29; // [rsp+88h] [rbp-B0h]
  int v30; // [rsp+8Ch] [rbp-ACh]
  int v31; // [rsp+90h] [rbp-A8h]
  __int128 v32; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-90h]
  int v34; // [rsp+B0h] [rbp-88h]
  int v35; // [rsp+B4h] [rbp-84h]
  int v36; // [rsp+B8h] [rbp-80h]
  LPCWSTR lpFileName[4]; // [rsp+C0h] [rbp-78h] BYREF
  LPCWSTR lpSubKey[11]; // [rsp+E0h] [rbp-58h] BYREF
  HKEY v40; // [rsp+148h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+150h] [rbp+18h] BYREF
  const wchar_t **v42; // [rsp+158h] [rbp+20h]

  v1 = this;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(this);
  v2 = (const wchar_t **)((char *)v1 + 32);
  v42 = (const wchar_t **)((char *)v1 + 32);
  *((_QWORD *)v1 + 4) = 0;
  v3 = (__int64 *)((char *)v1 + 40);
  v22 = (__int64 *)((char *)v1 + 40);
  *((_QWORD *)v1 + 5) = 0;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(v4, &hKey, lpSubKey);
  try
  {
    v6 = EventlogServiceRegPath;
    if ( EventlogServiceRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids,
          EventlogServiceRegPath);
      }
      pExceptionObject[0] = &byte_1800EC961;
      pExceptionObject[1] = 0;
      pExceptionObject[2] = 0;
      v24 = v6;
      v25 = -1;
      v26 = 0;
      throw (EvtException *)pExceptionObject;
    }
    v40 = 0;
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v40);
    if ( !RegOpenKeyExW(hKey, lpSubKey[0], 0, 0x20019u, phkResult) )
    {
      StringValueNoThrow = RegReadStringValueNoThrow(v40);
      v9 = *(LPCWSTR *)v1;
      if ( StringValueNoThrow )
      {
        *((_QWORD *)v1 + 1) = v9;
        *v9 = 0;
      }
      else
      {
        v10 = (__int64)(*((_QWORD *)v1 + 1) - (_QWORD)v9) >> 1;
        if ( v10
          && v9[v10 - 1] != 92
          && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 v1,
                                 92) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids, 14);
          }
          v27 = 0;
          v28 = 0;
          v29 = 14;
          v30 = -1;
          v31 = 75;
          throw (EvtException *)&v27;
        }
      }
    }
    if ( byte_18010F220 || !((__int64)(*((_QWORD *)v1 + 1) - *(_QWORD *)v1) >> 1) )
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
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids,
            LastError,
            *(_QWORD *)v1);
        }
        goto LABEL_32;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 12;
LABEL_27:
        WPP_SF_S(v13[2], v14, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids, *(_QWORD *)v1);
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
          || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpFileName) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids, 14);
          }
          v32 = 0;
          v33 = 0;
          v34 = 14;
          v35 = -1;
          v36 = 111;
          throw (EvtException *)&v32;
        }
        hKey = (HKEY)CreateFileW(lpFileName[0], 0x40000000u, 0, 0, 2u, 0x4000100u, 0);
        if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL || (HKEY)((char *)hKey + 1) == (HKEY)1 )
        {
          v16 = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids,
              v16,
              *(_QWORD *)v1);
          }
          v17 = *(LPCWSTR *)v1;
          *((_QWORD *)v1 + 1) = *(_QWORD *)v1;
          *v17 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids,
            *(_QWORD *)v1);
        }
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hKey);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
        goto LABEL_56;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 17;
        goto LABEL_27;
      }
    }
LABEL_32:
    v15 = *(LPCWSTR *)v1;
    *((_QWORD *)v1 + 1) = *(_QWORD *)v1;
    *v15 = 0;
LABEL_56:
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v40);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  }
  catch ( ... )
  {
    v21 = *(_WORD **)this;
    *((_QWORD *)this + 1) = *(_QWORD *)this;
    *v21 = 0;
    v1 = this;
    v2 = v42;
    v3 = v22;
  }
  v18 = *(const wchar_t **)v1;
  v19 = (__int64)(*((_QWORD *)v1 + 1) - *(_QWORD *)v1) >> 1;
  if ( !v19 )
  {
    v19 = 34;
    v18 = L"%SystemRoot%\\System32\\Winevt\\Logs\\";
  }
  *v2 = v18;
  *v3 = v19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids, v2);
  }
  return v1;
}

```

## disassembly

```asm
0x1800be7d0  mov     [rsp+arg_0], rcx
0x1800be7d5  push    rbx
0x1800be7d6  push    rsi
0x1800be7d7  push    rdi
0x1800be7d8  push    r12
0x1800be7da  push    r14
0x1800be7dc  push    r15
0x1800be7de  sub     rsp, 108h
0x1800be7e5  mov     rbx, rcx
0x1800be7e8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800be7ed  nop
0x1800be7ee  lea     r14, [rbx+20h]
0x1800be7f2  mov     [rsp+138h+arg_18], r14
0x1800be7fa  xor     r12d, r12d
0x1800be7fd  mov     [r14], r12
0x1800be800  lea     r15, [r14+8]
0x1800be804  mov     [rsp+138h+var_F8], r15
0x1800be809  mov     [r15], r12
0x1800be80c  mov     [rsp+138h+hKey], r12
0x1800be814  lea     rcx, [rsp+138h+lpSubKey]; void *
0x1800be81c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800be821  nop
0x1800be822  lea     r8, [rsp+138h+lpSubKey]
0x1800be82a  lea     rdx, [rsp+138h+hKey]
0x1800be832  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800be837  mov     esi, eax
0x1800be839  test    eax, eax
0x1800be83b  jz      short loc_1800BE8AD
0x1800be83d  lea     rdi, WPP_GLOBAL_Control
0x1800be844  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be84b  cmp     rcx, rdi
0x1800be84e  jz      short loc_1800BE874
0x1800be850  test    byte ptr [rcx+1Ch], 4
0x1800be854  jz      short loc_1800BE874
0x1800be856  cmp     byte ptr [rcx+19h], 2
0x1800be85a  jb      short loc_1800BE874
0x1800be85c  lea     edx, [r12+0Ah]
0x1800be861  mov     r9d, eax
0x1800be864  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800be86b  mov     rcx, [rcx+10h]
0x1800be86f  call    WPP_SF_d
0x1800be874  lea     rax, byte_1800EC961
0x1800be87b  mov     [rsp+138h+pExceptionObject], rax
0x1800be880  mov     [rsp+138h+var_E8], r12
0x1800be885  mov     [rsp+138h+var_E0], r12
0x1800be88a  mov     [rsp+138h+var_D8], esi
0x1800be88e  mov     [rsp+138h+var_D4], 0FFFFFFFFFFFFFFFFh
0x1800be897  mov     [rsp+138h+var_CC], r12b
0x1800be89c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800be8a3  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x1800be8a8  call    _CxxThrowException_0
0x1800be8ad  mov     [rsp+138h+arg_8], r12
0x1800be8b5  lea     rcx, [rsp+138h+arg_8]
0x1800be8bd  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800be8c2  mov     [rsp+138h+phkResult], rax; phkResult
0x1800be8c7  mov     r9d, 20019h; samDesired
0x1800be8cd  xor     r8d, r8d; ulOptions
0x1800be8d0  mov     rdx, [rsp+138h+lpSubKey]; lpSubKey
0x1800be8d8  mov     rcx, [rsp+138h+hKey]; hKey
0x1800be8e0  call    cs:__imp_RegOpenKeyExW
0x1800be8e6  test    eax, eax
0x1800be8e8  jnz     loc_1800BE9CA
0x1800be8ee  mov     r9, rbx
0x1800be8f1  lea     r8, aDefaultlogfold; "DefaultLogFolder"
0x1800be8f8  lea     rdx, pszFormat
0x1800be8ff  mov     rcx, [rsp+138h+arg_8]; hKey
0x1800be907  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800be90c  mov     rcx, [rbx]
0x1800be90f  test    eax, eax
0x1800be911  jnz     loc_1800BE9C2
0x1800be917  mov     rax, [rbx+8]
0x1800be91b  sub     rax, rcx
0x1800be91e  sar     rax, 1
0x1800be921  jz      loc_1800BE9CA
0x1800be927  mov     edx, 5Ch ; '\'
0x1800be92c  cmp     [rcx+rax*2-2], dx
0x1800be931  jz      loc_1800BE9CA
0x1800be937  mov     rcx, rbx
0x1800be93a  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800be93f  test    al, al
0x1800be941  jnz     loc_1800BE9CA
0x1800be947  lea     rdi, WPP_GLOBAL_Control
0x1800be94e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be955  cmp     rcx, rdi
0x1800be958  jz      short loc_1800BE97F
0x1800be95a  test    byte ptr [rcx+1Ch], 4
0x1800be95e  jz      short loc_1800BE97F
0x1800be960  cmp     byte ptr [rcx+19h], 2
0x1800be964  jb      short loc_1800BE97F
0x1800be966  mov     edx, 0Bh
0x1800be96b  lea     r9d, [rdx+3]
0x1800be96f  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800be976  mov     rcx, [rcx+10h]
0x1800be97a  call    WPP_SF_d
0x1800be97f  xorps   xmm0, xmm0
0x1800be982  movdqu  [rsp+138h+var_C8], xmm0
0x1800be988  mov     [rsp+138h+var_B8], r12
0x1800be990  mov     [rsp+138h+var_B0], 0Eh
0x1800be99b  mov     [rsp+138h+var_AC], 0FFFFFFFFh
0x1800be9a6  mov     [rsp+138h+var_A8], 4Bh ; 'K'
0x1800be9b1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800be9b8  lea     rcx, [rsp+138h+var_C8]; pExceptionObject
0x1800be9bd  call    _CxxThrowException_0
0x1800be9c2  mov     [rbx+8], rcx
0x1800be9c6  mov     [rcx], r12w
0x1800be9ca  cmp     cs:byte_18010F220, r12b
0x1800be9d1  jnz     loc_1800BEC81
0x1800be9d7  mov     rax, [rbx+8]
0x1800be9db  sub     rax, [rbx]
0x1800be9de  sar     rax, 1
0x1800be9e1  jz      loc_1800BEC81
0x1800be9e7  mov     rcx, [rbx]; lpFileName
0x1800be9ea  call    cs:__imp_GetFileAttributesW
0x1800be9f0  cmp     eax, 0FFFFFFFFh
0x1800be9f3  jnz     loc_1800BEA89
0x1800be9f9  call    cs:__imp_GetLastError
0x1800be9ff  mov     r9d, eax
0x1800bea02  cmp     eax, 2
0x1800bea05  jnz     short loc_1800BEA3D
0x1800bea07  lea     rdi, WPP_GLOBAL_Control
0x1800bea0e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bea15  cmp     rcx, rdi
0x1800bea18  jz      short loc_1800BEA79
0x1800bea1a  test    byte ptr [rcx+1Ch], 8
0x1800bea1e  jz      short loc_1800BEA79
0x1800bea20  cmp     [rcx+19h], al
0x1800bea23  jb      short loc_1800BEA79
0x1800bea25  lea     edx, [rax+0Ah]
0x1800bea28  mov     r9, [rbx]
0x1800bea2b  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800bea32  mov     rcx, [rcx+10h]
0x1800bea36  call    WPP_SF_S
0x1800bea3b  jmp     short loc_1800BEA79
0x1800bea3d  lea     rdi, WPP_GLOBAL_Control
0x1800bea44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bea4b  cmp     rcx, rdi
0x1800bea4e  jz      short loc_1800BEA79
0x1800bea50  test    byte ptr [rcx+1Ch], 8
0x1800bea54  jz      short loc_1800BEA79
0x1800bea56  cmp     byte ptr [rcx+19h], 2
0x1800bea5a  jb      short loc_1800BEA79
0x1800bea5c  mov     edx, 0Dh
0x1800bea61  mov     rax, [rbx]
0x1800bea64  mov     [rsp+138h+phkResult], rax
0x1800bea69  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800bea70  mov     rcx, [rcx+10h]
0x1800bea74  call    WPP_SF_dS
0x1800bea79  mov     rcx, [rbx]
0x1800bea7c  mov     [rbx+8], rcx
0x1800bea80  mov     [rcx], r12w
0x1800bea84  jmp     loc_1800BEC88
0x1800bea89  test    al, 10h
0x1800bea8b  jz      loc_1800BEC4C
0x1800bea91  lea     rcx, [rsp+138h+lpFileName]; void *
0x1800bea99  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bea9e  nop
0x1800bea9f  mov     r8, [rbx+8]
0x1800beaa3  sub     r8, [rbx]
0x1800beaa6  sar     r8, 1
0x1800beaa9  mov     rdx, [rbx]
0x1800beaac  lea     rcx, [rsp+138h+lpFileName]
0x1800beab4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800beab9  test    al, al
0x1800beabb  jz      loc_1800BEBCB
0x1800beac1  mov     r8d, 0Ch
0x1800beac7  lea     rdx, aAccessCheck; "access_check"
0x1800beace  lea     rcx, [rsp+138h+lpFileName]
0x1800bead6  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800beadb  test    al, al
0x1800beadd  jz      loc_1800BEBCB
0x1800beae3  mov     [rsp+138h+hTemplateFile], r12; hTemplateFile
0x1800beae8  mov     [rsp+138h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x1800beaf0  mov     dword ptr [rsp+138h+phkResult], 2; dwCreationDisposition
0x1800beaf8  xor     r9d, r9d; lpSecurityAttributes
0x1800beafb  xor     r8d, r8d; dwShareMode
0x1800beafe  mov     edx, 40000000h; dwDesiredAccess
0x1800beb03  mov     rcx, [rsp+138h+lpFileName]; lpFileName
0x1800beb0b  call    cs:__imp_CreateFileW
0x1800beb11  mov     [rsp+138h+hKey], rax
0x1800beb19  inc     rax
0x1800beb1c  cmp     rax, 1
0x1800beb20  jbe     short loc_1800BEB5B
0x1800beb22  lea     rdi, WPP_GLOBAL_Control
0x1800beb29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beb30  cmp     rcx, rdi
0x1800beb33  jz      short loc_1800BEBAB
0x1800beb35  test    byte ptr [rcx+1Ch], 8
0x1800beb39  jz      short loc_1800BEBAB
0x1800beb3b  cmp     byte ptr [rcx+19h], 4
0x1800beb3f  jb      short loc_1800BEBAB
0x1800beb41  mov     edx, 0Fh
0x1800beb46  mov     r9, [rbx]
0x1800beb49  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800beb50  mov     rcx, [rcx+10h]
0x1800beb54  call    WPP_SF_S
0x1800beb59  jmp     short loc_1800BEBAB
0x1800beb5b  call    cs:__imp_GetLastError
0x1800beb61  mov     r9d, eax
0x1800beb64  lea     rdi, WPP_GLOBAL_Control
0x1800beb6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beb72  cmp     rcx, rdi
0x1800beb75  jz      short loc_1800BEBA0
0x1800beb77  test    byte ptr [rcx+1Ch], 8
0x1800beb7b  jz      short loc_1800BEBA0
0x1800beb7d  cmp     byte ptr [rcx+19h], 2
0x1800beb81  jb      short loc_1800BEBA0
0x1800beb83  mov     edx, 10h
0x1800beb88  mov     rax, [rbx]
0x1800beb8b  mov     [rsp+138h+phkResult], rax
0x1800beb90  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800beb97  mov     rcx, [rcx+10h]
0x1800beb9b  call    WPP_SF_dS
0x1800beba0  mov     rcx, [rbx]
0x1800beba3  mov     [rbx+8], rcx
0x1800beba7  mov     [rcx], r12w
0x1800bebab  lea     rcx, [rsp+138h+hKey]
0x1800bebb3  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800bebb8  nop
0x1800bebb9  lea     rcx, [rsp+138h+lpFileName]; void *
0x1800bebc1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800bebc6  jmp     loc_1800BEC88
0x1800bebcb  lea     rdi, WPP_GLOBAL_Control
0x1800bebd2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bebd9  cmp     rcx, rdi
0x1800bebdc  jz      short loc_1800BEC02
0x1800bebde  test    byte ptr [rcx+1Ch], 4
0x1800bebe2  jz      short loc_1800BEC02
0x1800bebe4  cmp     byte ptr [rcx+19h], 2
0x1800bebe8  jb      short loc_1800BEC02
0x1800bebea  mov     edx, 0Eh
0x1800bebef  mov     r9d, edx
0x1800bebf2  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800bebf9  mov     rcx, [rcx+10h]
0x1800bebfd  call    WPP_SF_d
0x1800bec02  xorps   xmm0, xmm0
0x1800bec05  movdqu  [rsp+138h+var_A0], xmm0
0x1800bec0e  mov     [rsp+138h+var_90], r12
0x1800bec16  mov     [rsp+138h+var_88], 0Eh
0x1800bec21  mov     [rsp+138h+var_84], 0FFFFFFFFh
0x1800bec2c  mov     [rsp+138h+var_80], 6Fh ; 'o'
0x1800bec37  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bec3e  lea     rcx, [rsp+138h+var_A0]; pExceptionObject
0x1800bec46  call    _CxxThrowException_0
0x1800bec4c  lea     rdi, WPP_GLOBAL_Control
0x1800bec53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bec5a  cmp     rcx, rdi
0x1800bec5d  jz      loc_1800BEA79
0x1800bec63  test    byte ptr [rcx+1Ch], 8
0x1800bec67  jz      loc_1800BEA79
0x1800bec6d  cmp     byte ptr [rcx+19h], 2
0x1800bec71  jb      loc_1800BEA79
0x1800bec77  mov     edx, 11h
0x1800bec7c  jmp     loc_1800BEA28
0x1800bec81  lea     rdi, WPP_GLOBAL_Control
0x1800bec88  lea     rcx, [rsp+138h+arg_8]
0x1800bec90  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800bec95  nop
0x1800bec96  lea     rcx, [rsp+138h+lpSubKey]; void *
0x1800bec9e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800beca3  nop
0x1800beca4  jmp     short loc_1800BECC2
0x1800beca6  lea     rdi, WPP_GLOBAL_Control
0x1800becad  mov     rbx, [rsp+138h+arg_0]
0x1800becb5  mov     r14, [rsp+138h+arg_18]
0x1800becbd  mov     r15, [rsp+138h+var_F8]
0x1800becc2  mov     rcx, [rbx]
0x1800becc5  mov     rax, [rbx+8]
0x1800becc9  sub     rax, rcx
0x1800beccc  sar     rax, 1
0x1800beccf  jnz     short loc_1800BECDD
0x1800becd1  mov     eax, 22h ; '"'
0x1800becd6  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\System32\\Winevt\\Logs\\"
0x1800becdd  mov     [r14], rcx
0x1800bece0  mov     [r15], rax
0x1800bece3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800becea  cmp     rcx, rdi
0x1800beced  jz      short loc_1800BED14
0x1800becef  test    byte ptr [rcx+1Ch], 8
0x1800becf3  jz      short loc_1800BED14
0x1800becf5  cmp     byte ptr [rcx+19h], 4
0x1800becf9  jb      short loc_1800BED14
0x1800becfb  mov     edx, 12h
0x1800bed00  mov     r9, r14
0x1800bed03  lea     r8, WPP_2208c48054a4333c020c2e49d0c4b10a_Traceguids
0x1800bed0a  mov     rcx, [rcx+10h]
0x1800bed0e  call    WPP_SF__utlwsv_
0x1800bed13  nop
0x1800bed14  mov     rax, rbx
0x1800bed17  add     rsp, 108h
0x1800bed1e  pop     r15
0x1800bed20  pop     r14
0x1800bed22  pop     r12
0x1800bed24  pop     rdi
0x1800bed25  pop     rsi
0x1800bed26  pop     rbx
0x1800bed27  retn
```
