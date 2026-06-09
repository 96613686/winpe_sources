# DataCleanupManager::CleanupVolatileDirectory(void)

- ea: `0x1800acc34`
- end: `0x1800acd5e`
- name: `?CleanupVolatileDirectory@DataCleanupManager@@QEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004038c`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180034760`
- `0x180035040`
- `0x180035c40`
- `0x180057c64`
- `0x18009e71c`
- `0x1800acc34`

## import_xrefs

- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800acc87`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800acc87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800acd18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800acd40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800acd18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800acd40`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800accac`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800accac`

## string_xrefs

- `0x1800acc52`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x1800acd03`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x1800acce0`: `\Comms\Volatile\`

## pseudocode

```c
__int64 __fastcall DataCleanupManager::CleanupVolatileDirectory(struct _RTL_CRITICAL_SECTION *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  PWSTR *v3; // rbx
  int v4; // eax
  const KNOWNFOLDERID *v5; // rcx
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned __int16 *v11[4]; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+18h] BYREF

  v1 = DataCleanupManager::FailIfShutdownOrDc(this);
  v2 = v1;
  if ( v1 >= 0 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
    pv = 0;
    v3 = (PWSTR *)tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
    v4 = IsCommsSystemService();
    v5 = &FOLDERID_SharedData;
    if ( !v4 )
      v5 = &FOLDERID_LocalAppData;
    v6 = SHGetKnownFolderPath(v5, 0x4000u, 0, v3);
    v2 = v6;
    if ( v6 < 0 )
    {
      v7 = 936;
LABEL_7:
      v8 = 1;
      v9 = (unsigned int)v6;
      goto LABEL_13;
    }
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            v11,
                            pv) )
    {
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              v11,
                              L"\\Comms\\Volatile\\") )
      {
        v6 = _RecursiveDeleteOldFiles(v11[0]);
        v2 = v6;
        if ( v6 >= 0 )
        {
          if ( pv )
            CoTaskMemFree(pv);
          v2 = 0;
          goto LABEL_20;
        }
        v7 = 944;
        goto LABEL_7;
      }
      v7 = 939;
    }
    else
    {
      v7 = 938;
    }
    v2 = -2147024882;
    v8 = 0;
    v9 = 2147942414LL;
LABEL_13:
    Log_HREvent(
      v9,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      v7);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_20:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v11);
    return v2;
  }
  Log_HREvent(
    (unsigned int)v1,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
    928);
  return v2;
}

```

## disassembly

```asm
0x1800acc34  mov     [rsp-8+arg_0], rbx
0x1800acc39  push    rbp
0x1800acc3a  mov     rbp, rsp
0x1800acc3d  sub     rsp, 50h
0x1800acc41  call    ?FailIfShutdownOrDc@DataCleanupManager@@AEAAJXZ; DataCleanupManager::FailIfShutdownOrDc(void)
0x1800acc46  mov     ebx, eax
0x1800acc48  test    eax, eax
0x1800acc4a  jns     short loc_1800ACC6A
0x1800acc4c  mov     r9d, 3A0h
0x1800acc52  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800acc59  mov     edx, 1
0x1800acc5e  mov     ecx, eax
0x1800acc60  call    Log_HREvent
0x1800acc65  jmp     loc_1800ACD51
0x1800acc6a  lea     rcx, [rbp+var_20]; void *
0x1800acc6e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800acc73  lea     rcx, [rbp+pv]
0x1800acc77  mov     [rbp+pv], 0
0x1800acc7f  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x1800acc84  mov     rbx, rax
0x1800acc87  call    cs:__imp_IsCommsSystemService
0x1800acc8d  lea     rdx, FOLDERID_LocalAppData
0x1800acc94  mov     r9, rbx; ppszPath
0x1800acc97  test    eax, eax
0x1800acc99  lea     rcx, ?FOLDERID_SharedData@@3U_GUID@@B; _GUID const FOLDERID_SharedData
0x1800acca0  cmovz   rcx, rdx; rfid
0x1800acca4  xor     r8d, r8d; hToken
0x1800acca7  mov     edx, 4000h; dwFlags
0x1800accac  call    cs:__imp_SHGetKnownFolderPath
0x1800accb2  mov     ebx, eax
0x1800accb4  test    eax, eax
0x1800accb6  jns     short loc_1800ACCC7
0x1800accb8  mov     r9d, 3A8h
0x1800accbe  mov     edx, 1
0x1800accc3  mov     ecx, eax
0x1800accc5  jmp     short loc_1800ACD03
0x1800accc7  mov     rdx, [rbp+pv]
0x1800acccb  lea     rcx, [rbp+var_20]
0x1800acccf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800accd4  test    al, al
0x1800accd6  jnz     short loc_1800ACCE0
0x1800accd8  mov     r9d, 3AAh
0x1800accde  jmp     short loc_1800ACCFA
0x1800acce0  lea     rdx, aCommsVolatile; "\\Comms\\Volatile\\"
0x1800acce7  lea     rcx, [rbp+var_20]
0x1800acceb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800accf0  test    al, al
0x1800accf2  jnz     short loc_1800ACD20
0x1800accf4  mov     r9d, 3ABh
0x1800accfa  mov     ebx, 8007000Eh
0x1800accff  xor     edx, edx
0x1800acd01  mov     ecx, ebx
0x1800acd03  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800acd0a  call    Log_HREvent
0x1800acd0f  mov     rcx, [rbp+pv]; pv
0x1800acd13  test    rcx, rcx
0x1800acd16  jz      short loc_1800ACD48
0x1800acd18  call    cs:__imp_CoTaskMemFree
0x1800acd1e  jmp     short loc_1800ACD48
0x1800acd20  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1800acd24  call    ?_RecursiveDeleteOldFiles@@YAJPEBG_K@Z; _RecursiveDeleteOldFiles(ushort const *,unsigned __int64)
0x1800acd29  mov     ebx, eax
0x1800acd2b  test    eax, eax
0x1800acd2d  jns     short loc_1800ACD37
0x1800acd2f  mov     r9d, 3B0h
0x1800acd35  jmp     short loc_1800ACCBE
0x1800acd37  mov     rcx, [rbp+pv]; pv
0x1800acd3b  test    rcx, rcx
0x1800acd3e  jz      short loc_1800ACD46
0x1800acd40  call    cs:__imp_CoTaskMemFree
0x1800acd46  xor     ebx, ebx
0x1800acd48  lea     rcx, [rbp+var_20]; void *
0x1800acd4c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800acd51  mov     eax, ebx
0x1800acd53  mov     rbx, [rsp+50h+arg_0]
0x1800acd58  add     rsp, 50h
0x1800acd5c  pop     rbp
0x1800acd5d  retn
```
