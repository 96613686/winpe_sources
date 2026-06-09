# GetTempFilePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800a0b40`
- end: `0x1800a0d66`
- name: `?GetTempFilePath@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18007fef0`
- `0x18008047c`

## callees

- `0x180008f0c`
- `0x180035040`
- `0x180035670`
- `0x180035c40`
- `0x180072cf0`
- `0x18007ee4c`
- `0x18009e71c`
- `0x1800a0b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0b64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0b64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0d14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0d14`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a0c83`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a0c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0cdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0d07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0cdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0d07`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800a0b9a`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800a0b9a`

## string_xrefs

- `0x1800a0c53`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a0cc1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a0d40`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a0c23`: `UserDataTempFiles`
- `0x1800a0bf1`: `Comms`

## pseudocode

```c
__int64 __fastcall GetTempFilePath(__int64 a1)
{
  PWSTR *v2; // rax
  int valid; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // r9
  LPVOID pv; // [rsp+68h] [rbp+30h] BYREF

  if ( !g_hasInitializedTempPath )
  {
    EnterCriticalSection(&g_tempFilePathLock);
    if ( !g_hasInitializedTempPath )
    {
      pv = 0;
      v2 = (PWSTR *)tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
      valid = SHGetKnownFolderPath(&rfid, 0x4000u, 0, v2);
      v4 = valid;
      if ( valid < 0 )
      {
        v5 = 2366;
        goto LABEL_25;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               &g_tempFilePath,
                               pv) )
      {
        v6 = 2368;
LABEL_17:
        Log_HREvent(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          v6);
        if ( pv )
          CoTaskMemFree(pv);
        v4 = -2147024882;
        goto LABEL_27;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &g_tempFilePath,
                               L"\\") )
      {
        v6 = 2369;
        goto LABEL_17;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &g_tempFilePath,
                               L"Comms") )
      {
        v6 = 2370;
        goto LABEL_17;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &g_tempFilePath,
                               L"\\") )
      {
        v6 = 2371;
        goto LABEL_17;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &g_tempFilePath,
                               L"UserDataTempFiles") )
      {
        v6 = 2372;
        goto LABEL_17;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &g_tempFilePath,
                               L"\\") )
      {
        v6 = 2373;
        goto LABEL_17;
      }
      if ( PathFileExistsW(g_tempFilePath) )
      {
        valid = wil::RemoveDirectoryRecursiveNoThrow(g_tempFilePath, 0, -1);
        v4 = valid;
        if ( valid < 0 )
        {
          v5 = 2377;
          goto LABEL_25;
        }
      }
      valid = EnsureValidSessionFolderPath(&g_tempFilePath);
      v4 = valid;
      if ( valid < 0 )
      {
        v5 = 2380;
LABEL_25:
        Log_HREvent(
          (unsigned int)valid,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          v5);
        if ( pv )
          CoTaskMemFree(pv);
LABEL_27:
        LeaveCriticalSection(&g_tempFilePathLock);
        return v4;
      }
      g_hasInitializedTempPath = 1;
      if ( pv )
        CoTaskMemFree(pv);
    }
    LeaveCriticalSection(&g_tempFilePathLock);
  }
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          a1,
                          g_tempFilePath,
                          (qword_18015D738 - (__int64)g_tempFilePath) >> 1) )
    return 0;
  Log_HREvent(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    2386);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800a0b40  push    rbp
0x1800a0b42  push    rbx
0x1800a0b43  push    rdi
0x1800a0b44  push    r14
0x1800a0b46  mov     rbp, rsp
0x1800a0b49  sub     rsp, 38h
0x1800a0b4d  cmp     cs:?g_hasInitializedTempPath@@3HA, 0; int g_hasInitializedTempPath
0x1800a0b54  mov     rdi, rcx
0x1800a0b57  jnz     loc_1800A0D1A
0x1800a0b5d  lea     rcx, ?g_tempFilePathLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800a0b64  call    cs:__imp_EnterCriticalSection
0x1800a0b6a  cmp     cs:?g_hasInitializedTempPath@@3HA, 0; int g_hasInitializedTempPath
0x1800a0b71  jnz     loc_1800A0D0D
0x1800a0b77  lea     rcx, [rbp+pv]
0x1800a0b7b  mov     [rbp+pv], 0
0x1800a0b83  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x1800a0b88  mov     r9, rax; ppszPath
0x1800a0b8b  lea     rcx, rfid; rfid
0x1800a0b92  xor     r8d, r8d; hToken
0x1800a0b95  mov     edx, 4000h; dwFlags
0x1800a0b9a  call    cs:__imp_SHGetKnownFolderPath
0x1800a0ba0  mov     ebx, eax
0x1800a0ba2  test    eax, eax
0x1800a0ba4  jns     short loc_1800A0BB1
0x1800a0ba6  mov     r9d, 93Eh
0x1800a0bac  jmp     loc_1800A0CC1
0x1800a0bb1  mov     rdx, [rbp+pv]
0x1800a0bb5  lea     r14, ?g_tempFilePath@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_tempFilePath
0x1800a0bbc  mov     rcx, r14
0x1800a0bbf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a0bc4  test    al, al
0x1800a0bc6  jnz     short loc_1800A0BD3
0x1800a0bc8  mov     r9d, 940h
0x1800a0bce  jmp     loc_1800A0C53
0x1800a0bd3  lea     rbx, asc_18013D0B8; "\\"
0x1800a0bda  mov     rcx, r14
0x1800a0bdd  mov     rdx, rbx
0x1800a0be0  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a0be5  test    al, al
0x1800a0be7  jnz     short loc_1800A0BF1
0x1800a0be9  mov     r9d, 941h
0x1800a0bef  jmp     short loc_1800A0C53
0x1800a0bf1  lea     rdx, ?gc_szCommsFolderName@@3QBGB; "Comms"
0x1800a0bf8  mov     rcx, r14
0x1800a0bfb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a0c00  test    al, al
0x1800a0c02  jnz     short loc_1800A0C0C
0x1800a0c04  mov     r9d, 942h
0x1800a0c0a  jmp     short loc_1800A0C53
0x1800a0c0c  mov     rdx, rbx
0x1800a0c0f  mov     rcx, r14
0x1800a0c12  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a0c17  test    al, al
0x1800a0c19  jnz     short loc_1800A0C23
0x1800a0c1b  mov     r9d, 943h
0x1800a0c21  jmp     short loc_1800A0C53
0x1800a0c23  lea     rdx, ?gc_szUserDataTempFileFolderName@@3QBGB; "UserDataTempFiles"
0x1800a0c2a  mov     rcx, r14
0x1800a0c2d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a0c32  test    al, al
0x1800a0c34  jnz     short loc_1800A0C3E
0x1800a0c36  mov     r9d, 944h
0x1800a0c3c  jmp     short loc_1800A0C53
0x1800a0c3e  mov     rdx, rbx
0x1800a0c41  mov     rcx, r14
0x1800a0c44  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a0c49  test    al, al
0x1800a0c4b  jnz     short loc_1800A0C7C
0x1800a0c4d  mov     r9d, 945h
0x1800a0c53  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a0c5a  xor     edx, edx
0x1800a0c5c  mov     ecx, 8007000Eh
0x1800a0c61  call    Log_HREvent
0x1800a0c66  mov     rcx, [rbp+pv]; pv
0x1800a0c6a  test    rcx, rcx
0x1800a0c6d  jz      short loc_1800A0C75
0x1800a0c6f  call    cs:__imp_CoTaskMemFree
0x1800a0c75  mov     ebx, 8007000Eh
0x1800a0c7a  jmp     short loc_1800A0CE3
0x1800a0c7c  mov     rcx, cs:?g_tempFilePath@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; pszPath
0x1800a0c83  call    cs:__imp_PathFileExistsW
0x1800a0c89  test    eax, eax
0x1800a0c8b  jz      short loc_1800A0CAD
0x1800a0c8d  mov     rcx, cs:?g_tempFilePath@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_tempFilePath
0x1800a0c94  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a0c98  xor     edx, edx
0x1800a0c9a  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x1800a0c9f  mov     ebx, eax
0x1800a0ca1  test    eax, eax
0x1800a0ca3  jns     short loc_1800A0CAD
0x1800a0ca5  mov     r9d, 949h
0x1800a0cab  jmp     short loc_1800A0CC1
0x1800a0cad  mov     rcx, r14
0x1800a0cb0  call    ?EnsureValidSessionFolderPath@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; EnsureValidSessionFolderPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800a0cb5  mov     ebx, eax
0x1800a0cb7  test    eax, eax
0x1800a0cb9  jns     short loc_1800A0CF4
0x1800a0cbb  mov     r9d, 94Ch
0x1800a0cc1  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a0cc8  mov     edx, 1
0x1800a0ccd  mov     ecx, eax
0x1800a0ccf  call    Log_HREvent
0x1800a0cd4  mov     rcx, [rbp+pv]; pv
0x1800a0cd8  test    rcx, rcx
0x1800a0cdb  jz      short loc_1800A0CE3
0x1800a0cdd  call    cs:__imp_CoTaskMemFree
0x1800a0ce3  lea     rcx, ?g_tempFilePathLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800a0cea  call    cs:__imp_LeaveCriticalSection
0x1800a0cf0  mov     eax, ebx
0x1800a0cf2  jmp     short loc_1800A0D5C
0x1800a0cf4  mov     rcx, [rbp+pv]; pv
0x1800a0cf8  mov     cs:?g_hasInitializedTempPath@@3HA, 1; int g_hasInitializedTempPath
0x1800a0d02  test    rcx, rcx
0x1800a0d05  jz      short loc_1800A0D0D
0x1800a0d07  call    cs:__imp_CoTaskMemFree
0x1800a0d0d  lea     rcx, ?g_tempFilePathLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800a0d14  call    cs:__imp_LeaveCriticalSection
0x1800a0d1a  mov     r8, cs:qword_18015D738
0x1800a0d21  mov     rcx, rdi
0x1800a0d24  mov     rdx, cs:?g_tempFilePath@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_tempFilePath
0x1800a0d2b  sub     r8, rdx
0x1800a0d2e  sar     r8, 1
0x1800a0d31  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a0d36  test    al, al
0x1800a0d38  jnz     short loc_1800A0D5A
0x1800a0d3a  mov     r9d, 952h
0x1800a0d40  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a0d47  xor     edx, edx
0x1800a0d49  mov     ecx, 8007000Eh
0x1800a0d4e  call    Log_HREvent
0x1800a0d53  mov     eax, 8007000Eh
0x1800a0d58  jmp     short loc_1800A0D5C
0x1800a0d5a  xor     eax, eax
0x1800a0d5c  add     rsp, 38h
0x1800a0d60  pop     r14
0x1800a0d62  pop     rdi
0x1800a0d63  pop     rbx
0x1800a0d64  pop     rbp
0x1800a0d65  retn
```
