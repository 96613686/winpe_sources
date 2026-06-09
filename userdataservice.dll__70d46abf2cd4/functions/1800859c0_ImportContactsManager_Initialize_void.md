# ImportContactsManager::Initialize(void)

- ea: `0x1800859c0`
- end: `0x180085ce1`
- name: `?Initialize@ImportContactsManager@@QEAAJXZ`
- size: `801`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ee80`

## callees

- `0x180059de0`
- `0x18007ba48`
- `0x18007be90`
- `0x1800859c0`
- `0x180085ce8`
- `0x180089248`
- `0x1800977a0`
- `0x1800977b8`
- `0x180098534`
- `0x18009e71c`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085bdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085bdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085ca2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c75`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x180085c07`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x180085c07`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x180085bed`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x180085bed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085c99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085c99`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085c5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085c5a`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180085b5f`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180085b5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085a76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085a76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085cb2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180085a4e`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180085a4e`

## string_xrefs

- `0x180085bb9`: `cellebrite.contacts.xml`

## pseudocode

```c
__int64 __fastcall ImportContactsManager::Initialize(LPCRITICAL_SECTION lpCriticalSection)
{
  void **v2; // rax
  int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned __int64 v8; // r11
  unsigned __int64 v9; // rsi
  const WCHAR *v10; // rax
  LPCWSTR v11; // rcx
  const WCHAR *v12; // rbx
  int v13; // eax
  struct _RTL_CRITICAL_SECTION_DEBUG *v14; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  signed int LastError; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v20; // rcx
  signed int v21; // eax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  KNOWNFOLDERID rfid; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !(unsigned __int8)IsCreateTokenFromChamberSidPresent() || !(unsigned __int8)IsCreateTokenFromChamberSidPresent() )
    return 0;
  rfid.Data1 = -2103880039;
  *(_DWORD *)&rfid.Data2 = 1160410058;
  *(_DWORD *)rfid.Data4 = -1554896466;
  *(_DWORD *)&rfid.Data4[4] = -154931697;
  pv = 0;
  v2 = tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
  v3 = SHGetKnownFolderPath(&rfid, 0x4000u, 0, (PWSTR *)v2);
  if ( v3 >= 0 )
  {
    v3 = StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)pv);
    if ( v3 < 0 )
    {
      v5 = 58;
      goto LABEL_5;
    }
    v3 = StringCchCatW(pszPath, v8, L"\\Users\\Public\\");
    if ( v3 < 0 )
    {
      v5 = 59;
      goto LABEL_5;
    }
    v23 = 0;
    v3 = StringCchLengthW(pszPath, 0x7FFFFFFFu, &v23);
    if ( v3 < 0 )
    {
      v5 = 62;
      goto LABEL_5;
    }
    v9 = v23 + 24;
    v10 = (const WCHAR *)operator new[](saturated_mul(v23 + 24, 2u));
    v11 = g_contactsImportFullFilename;
    v12 = v10;
    if ( v10 != g_contactsImportFullFilename )
    {
      if ( g_contactsImportFullFilename )
        operator delete((void *)g_contactsImportFullFilename);
      v11 = v12;
      g_contactsImportFullFilename = v12;
    }
    if ( !v11 )
    {
      v6 = 0;
      v5 = 68;
      v3 = -2147024882;
      goto LABEL_6;
    }
    v13 = SHCreateDirectoryExW(0, pszPath, 0);
    v3 = v13;
    if ( v13 != 80 && v13 != 183 && v13 )
    {
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
      v6 = 0;
      v5 = 77;
      goto LABEL_6;
    }
    v3 = StringCchCopyW((unsigned __int16 *)g_contactsImportFullFilename, v9, pszPath);
    if ( v3 < 0 )
    {
      v5 = 80;
      goto LABEL_5;
    }
    v3 = StringCchCatW((unsigned __int16 *)g_contactsImportFullFilename, v9, L"cellebrite.contacts.xml");
    if ( v3 < 0 )
    {
      v5 = 81;
      goto LABEL_5;
    }
    EnterCriticalSection(lpCriticalSection);
    v14 = (struct _RTL_CRITICAL_SECTION_DEBUG *)FindFirstChangeNotificationW(pszPath, 0, 1u);
    DebugInfo = lpCriticalSection[1].DebugInfo;
    if ( v14 == DebugInfo )
    {
      v14 = lpCriticalSection[1].DebugInfo;
    }
    else
    {
      if ( DebugInfo != (PRTL_CRITICAL_SECTION_DEBUG)-1LL )
        FindCloseChangeNotification(lpCriticalSection[1].DebugInfo);
      lpCriticalSection[1].DebugInfo = v14;
    }
    if ( v14 == (struct _RTL_CRITICAL_SECTION_DEBUG *)-1LL )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v18 = 89;
LABEL_41:
      Log_HREvent_35((unsigned int)v3, 0, v17, v18);
      LeaveCriticalSection(lpCriticalSection);
      goto LABEL_7;
    }
    ThreadpoolWait = CreateThreadpoolWait(ImportContactsManager::ImportContactsCallback, lpCriticalSection, 0);
    tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>::reset(
      &lpCriticalSection[1].LockCount,
      ThreadpoolWait);
    v20 = *(struct _TP_WAIT **)&lpCriticalSection[1].LockCount;
    if ( !v20 )
    {
      v21 = GetLastError();
      v3 = v21;
      if ( v21 > 0 )
        v3 = (unsigned __int16)v21 | 0x80070000;
      v18 = 93;
      goto LABEL_41;
    }
    SetThreadpoolWait(v20, lpCriticalSection[1].DebugInfo, 0);
    LeaveCriticalSection(lpCriticalSection);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  v5 = 55;
LABEL_5:
  v6 = 1;
LABEL_6:
  Log_HREvent_35((unsigned int)v3, v6, v4, v5);
LABEL_7:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800859c0  mov     [rsp-8+arg_8], rbx
0x1800859c5  mov     [rsp-8+arg_10], rsi
0x1800859ca  push    rbp
0x1800859cb  push    rdi
0x1800859cc  push    r14
0x1800859ce  lea     rbp, [rsp-170h]
0x1800859d6  sub     rsp, 270h
0x1800859dd  mov     rax, cs:__security_cookie
0x1800859e4  xor     rax, rsp
0x1800859e7  mov     [rbp+180h+var_20], rax
0x1800859ee  mov     rdi, rcx
0x1800859f1  call    IsCreateTokenFromChamberSidPresent
0x1800859f6  test    al, al
0x1800859f8  jz      loc_180085CB8
0x1800859fe  call    IsCreateTokenFromChamberSidPresent
0x180085a03  test    al, al
0x180085a05  jz      loc_180085CB8
0x180085a0b  lea     rcx, [rsp+280h+pv]
0x180085a10  mov     [rsp+280h+rfid.Data1], 82995699h
0x180085a18  mov     dword ptr [rsp+280h+rfid.Data2], 452A73CAh
0x180085a20  mov     dword ptr [rsp+280h+rfid.Data4], 0A35229AEh
0x180085a28  mov     dword ptr [rsp+280h+rfid.Data4+4], 0F6C3EE0Fh
0x180085a30  mov     [rsp+280h+pv], 0
0x180085a39  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x180085a3e  mov     r9, rax; ppszPath
0x180085a41  lea     rcx, [rsp+280h+rfid]; rfid
0x180085a46  xor     r8d, r8d; hToken
0x180085a49  mov     edx, 4000h; dwFlags
0x180085a4e  call    cs:__imp_SHGetKnownFolderPath
0x180085a54  mov     ebx, eax
0x180085a56  test    eax, eax
0x180085a58  jns     short loc_180085A83
0x180085a5a  mov     r9d, 37h ; '7'
0x180085a60  mov     edx, 1
0x180085a65  mov     ecx, ebx
0x180085a67  call    Log_HREvent_35
0x180085a6c  mov     rcx, [rsp+280h+pv]; pv
0x180085a71  test    rcx, rcx
0x180085a74  jz      short loc_180085A7C
0x180085a76  call    cs:__imp_CoTaskMemFree
0x180085a7c  mov     eax, ebx
0x180085a7e  jmp     loc_180085CBA
0x180085a83  mov     r8, [rsp+280h+pv]; unsigned __int16 *
0x180085a88  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x180085a8d  mov     r11d, 104h
0x180085a93  mov     edx, r11d; unsigned __int64
0x180085a96  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180085a9b  mov     ebx, eax
0x180085a9d  test    eax, eax
0x180085a9f  jns     short loc_180085AA9
0x180085aa1  mov     r9d, 3Ah ; ':'
0x180085aa7  jmp     short loc_180085A60
0x180085aa9  lea     r8, aUsersPublic; "\\Users\\Public\\"
0x180085ab0  mov     rdx, r11; unsigned __int64
0x180085ab3  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x180085ab8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180085abd  mov     ebx, eax
0x180085abf  test    eax, eax
0x180085ac1  jns     short loc_180085ACB
0x180085ac3  mov     r9d, 3Bh ; ';'
0x180085ac9  jmp     short loc_180085A60
0x180085acb  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180085ad0  mov     [rsp+280h+var_248], 0
0x180085ad9  mov     edx, 7FFFFFFFh; unsigned __int64
0x180085ade  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x180085ae3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180085ae8  mov     ebx, eax
0x180085aea  test    eax, eax
0x180085aec  jns     short loc_180085AF9
0x180085aee  mov     r9d, 3Eh ; '>'
0x180085af4  jmp     loc_180085A60
0x180085af9  mov     rsi, [rsp+280h+var_248]
0x180085afe  mov     eax, 2
0x180085b03  add     rsi, 18h
0x180085b07  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180085b0e  mul     rsi
0x180085b11  cmovb   rax, r14
0x180085b15  mov     rcx, rax; unsigned __int64
0x180085b18  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180085b1d  mov     rcx, cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A; Block
0x180085b24  mov     rbx, rax
0x180085b27  cmp     rax, rcx
0x180085b2a  jz      short loc_180085B40
0x180085b2c  test    rcx, rcx
0x180085b2f  jz      short loc_180085B36
0x180085b31  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180085b36  mov     rcx, rbx
0x180085b39  mov     cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A, rbx; tlx::auto_ptr<ushort,&tlx::_delete<ushort>(ushort *)> g_contactsImportFullFilename
0x180085b40  test    rcx, rcx
0x180085b43  jnz     short loc_180085B55
0x180085b45  xor     edx, edx
0x180085b47  lea     r9d, [rcx+44h]
0x180085b4b  mov     ebx, 8007000Eh
0x180085b50  jmp     loc_180085A65
0x180085b55  xor     r8d, r8d; psa
0x180085b58  lea     rdx, [rsp+280h+pszPath]; pszPath
0x180085b5d  xor     ecx, ecx; hwnd
0x180085b5f  call    cs:__imp_SHCreateDirectoryExW
0x180085b65  mov     ebx, eax
0x180085b67  cmp     eax, 50h ; 'P'
0x180085b6a  jz      short loc_180085B8D
0x180085b6c  cmp     eax, 0B7h
0x180085b71  jz      short loc_180085B8D
0x180085b73  test    eax, eax
0x180085b75  jz      short loc_180085B8D
0x180085b77  jle     short loc_180085B82
0x180085b79  movzx   ebx, ax
0x180085b7c  or      ebx, 80070000h
0x180085b82  xor     edx, edx
0x180085b84  lea     r9d, [rdx+4Dh]
0x180085b88  jmp     loc_180085A65
0x180085b8d  mov     rcx, cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A; unsigned __int16 *
0x180085b94  lea     r8, [rsp+280h+pszPath]; unsigned __int16 *
0x180085b99  mov     rdx, rsi; unsigned __int64
0x180085b9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180085ba1  mov     ebx, eax
0x180085ba3  test    eax, eax
0x180085ba5  jns     short loc_180085BB2
0x180085ba7  mov     r9d, 50h ; 'P'
0x180085bad  jmp     loc_180085A60
0x180085bb2  mov     rcx, cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A; unsigned __int16 *
0x180085bb9  lea     r8, aCellebriteCont; "cellebrite.contacts.xml"
0x180085bc0  mov     rdx, rsi; unsigned __int64
0x180085bc3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180085bc8  mov     ebx, eax
0x180085bca  test    eax, eax
0x180085bcc  jns     short loc_180085BD9
0x180085bce  mov     r9d, 51h ; 'Q'
0x180085bd4  jmp     loc_180085A60
0x180085bd9  mov     rcx, rdi; lpCriticalSection
0x180085bdc  call    cs:__imp_EnterCriticalSection
0x180085be2  xor     edx, edx; bWatchSubtree
0x180085be4  lea     rcx, [rsp+280h+pszPath]; lpPathName
0x180085be9  lea     r8d, [rdx+1]; dwNotifyFilter
0x180085bed  call    cs:__imp_FindFirstChangeNotificationW
0x180085bf3  mov     rbx, rax
0x180085bf6  mov     rax, [rdi+28h]
0x180085bfa  cmp     rbx, rax
0x180085bfd  jz      short loc_180085C13
0x180085bff  cmp     rax, r14
0x180085c02  jz      short loc_180085C0D
0x180085c04  mov     rcx, rax; hChangeHandle
0x180085c07  call    cs:__imp_FindCloseChangeNotification
0x180085c0d  mov     [rdi+28h], rbx
0x180085c11  jmp     short loc_180085C16
0x180085c13  mov     rbx, rax
0x180085c16  cmp     rbx, r14
0x180085c19  jnz     short loc_180085C4D
0x180085c1b  call    cs:__imp_GetLastError
0x180085c21  mov     ebx, eax
0x180085c23  test    eax, eax
0x180085c25  jle     short loc_180085C30
0x180085c27  movzx   ebx, ax
0x180085c2a  or      ebx, 80070000h
0x180085c30  mov     r9d, 59h ; 'Y'
0x180085c36  xor     edx, edx
0x180085c38  mov     ecx, ebx
0x180085c3a  call    Log_HREvent_35
0x180085c3f  mov     rcx, rdi; lpCriticalSection
0x180085c42  call    cs:__imp_LeaveCriticalSection
0x180085c48  jmp     loc_180085A6C
0x180085c4d  xor     r8d, r8d; pcbe
0x180085c50  lea     rcx, ?ImportContactsCallback@ImportContactsManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180085c57  mov     rdx, rdi; pv
0x180085c5a  call    cs:__imp_CreateThreadpoolWait
0x180085c60  mov     rdx, rax
0x180085c63  lea     rcx, [rdi+30h]
0x180085c67  call    ?reset@?$auto_xxx@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@QEAAXPEAU_TP_WAIT@@@Z; tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>::reset(_TP_WAIT *)
0x180085c6c  mov     rcx, [rdi+30h]; pwa
0x180085c70  test    rcx, rcx
0x180085c73  jnz     short loc_180085C92
0x180085c75  call    cs:__imp_GetLastError
0x180085c7b  mov     ebx, eax
0x180085c7d  test    eax, eax
0x180085c7f  jle     short loc_180085C8A
0x180085c81  movzx   ebx, ax
0x180085c84  or      ebx, 80070000h
0x180085c8a  mov     r9d, 5Dh ; ']'
0x180085c90  jmp     short loc_180085C36
0x180085c92  mov     rdx, [rdi+28h]; h
0x180085c96  xor     r8d, r8d; pftTimeout
0x180085c99  call    cs:__imp_SetThreadpoolWait
0x180085c9f  mov     rcx, rdi; lpCriticalSection
0x180085ca2  call    cs:__imp_LeaveCriticalSection
0x180085ca8  mov     rcx, [rsp+280h+pv]; pv
0x180085cad  test    rcx, rcx
0x180085cb0  jz      short loc_180085CB8
0x180085cb2  call    cs:__imp_CoTaskMemFree
0x180085cb8  xor     eax, eax
0x180085cba  mov     rcx, [rbp+180h+var_20]
0x180085cc1  xor     rcx, rsp; StackCookie
0x180085cc4  call    __security_check_cookie
0x180085cc9  lea     r11, [rsp+280h+var_10]
0x180085cd1  mov     rbx, [r11+28h]
0x180085cd5  mov     rsi, [r11+30h]
0x180085cd9  mov     rsp, r11
0x180085cdc  pop     r14
0x180085cde  pop     rdi
0x180085cdf  pop     rbp
0x180085ce0  retn
```
