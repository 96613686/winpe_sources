# IsCleanMgrPresent(bool *)

- ea: `0x18001b3b0`
- end: `0x18001b5c3`
- name: `?IsCleanMgrPresent@@YAJPEA_N@Z`
- size: `531`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ab90`
- `0x18002ad0c`
- `0x1800301c4`
- `0x18003037c`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180012734`
- `0x180019d70`
- `0x180019d94`
- `0x18001b3b0`
- `0x18001c3d8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001b554`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001b554`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18001b4f8`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18001b4f8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001b49d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001b49d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001b435`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001b435`

## string_xrefs

- `0x18001b44b`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`
- `0x18001b4b3`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`
- `0x18001b50e`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall IsCleanMgrPresent(bool *a1)
{
  unsigned int v2; // ebx
  HRESULT v3; // eax
  bool v4; // di
  HRESULT v5; // eax
  HRESULT v6; // eax
  PWSTR v8; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-D8h] BYREF
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE FirstFileW; // [rsp+38h] [rbp-C8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  ppszPath = 0;
  ppszPathOut = 0;
  v8 = 0;
  if ( a1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPath,
      0);
    v3 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &ppszPath);
    v2 = v3;
    if ( v3 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPathOut,
        0);
      v4 = 1;
      v5 = PathAllocCombine(ppszPath, L"cleanmgr.exe", 1u, &ppszPathOut);
      v2 = v5;
      if ( v5 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v8,
          0);
        v6 = PathAllocCanonicalize(ppszPathOut, 1u, &v8);
        v2 = v6;
        if ( v6 >= 0 )
        {
          memset_0(&FindFileData, 0, sizeof(FindFileData));
          FirstFileW = FindFirstFileW(v8, &FindFileData);
          if ( FirstFileW == (HANDLE)-1LL
            || FindFileData.dwFileAttributes == -1
            || (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            v4 = 0;
          }
          *a1 = v4;
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFileW);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v2 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x878,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
            (const char *)(unsigned int)v6,
            (int)v8);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x877,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
          (const char *)(unsigned int)v5,
          (int)v8);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x876,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
        (const char *)(unsigned int)v3,
        (int)v8);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    v2 = -2147024809;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  return v2;
}

```

## disassembly

```asm
0x18001b3b0  push    rbp
0x18001b3b2  push    rbx
0x18001b3b3  push    rsi
0x18001b3b4  push    rdi
0x18001b3b5  lea     rbp, [rsp-1A8h]
0x18001b3bd  sub     rsp, 2A8h
0x18001b3c4  mov     rax, cs:__security_cookie
0x18001b3cb  xor     rax, rsp
0x18001b3ce  mov     [rbp+1C0h+var_30], rax
0x18001b3d5  mov     rsi, rcx
0x18001b3d8  mov     [rsp+2C0h+ppszPath], 0
0x18001b3e1  mov     [rsp+2C0h+ppszPathOut], 0
0x18001b3ea  mov     [rsp+2C0h+var_2A0], 0; int
0x18001b3f3  test    rcx, rcx
0x18001b3f6  jnz     short loc_18001B418
0x18001b3f8  lea     rcx, [rsp+2C0h+var_2A0]
0x18001b3fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b402  nop
0x18001b403  lea     rcx, [rsp+2C0h+ppszPathOut]
0x18001b408  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b40d  nop
0x18001b40e  mov     ebx, 80070057h
0x18001b413  jmp     loc_18001B59C
0x18001b418  xor     edx, edx
0x18001b41a  lea     rcx, [rsp+2C0h+ppszPath]
0x18001b41f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b424  lea     r9, [rsp+2C0h+ppszPath]; ppszPath
0x18001b429  xor     r8d, r8d; hToken
0x18001b42c  xor     edx, edx; dwFlags
0x18001b42e  lea     rcx, FOLDERID_System; rfid
0x18001b435  call    cs:__imp_SHGetKnownFolderPath
0x18001b43b  mov     ebx, eax
0x18001b43d  test    eax, eax
0x18001b43f  jns     short loc_18001B478
0x18001b441  mov     rcx, [rbp+1C8h]; this
0x18001b448  mov     r9d, eax; char *
0x18001b44b  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001b452  mov     edx, 876h; void *
0x18001b457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b45c  nop
0x18001b45d  lea     rcx, [rsp+2C0h+var_2A0]
0x18001b462  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b467  nop
0x18001b468  lea     rcx, [rsp+2C0h+ppszPathOut]
0x18001b46d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b472  nop
0x18001b473  jmp     loc_18001B59C
0x18001b478  xor     edx, edx
0x18001b47a  lea     rcx, [rsp+2C0h+ppszPathOut]
0x18001b47f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b484  lea     r9, [rsp+2C0h+ppszPathOut]; ppszPathOut
0x18001b489  mov     edi, 1
0x18001b48e  mov     r8d, edi; dwFlags
0x18001b491  lea     rdx, pszMore; "cleanmgr.exe"
0x18001b498  mov     rcx, [rsp+2C0h+ppszPath]; pszPathIn
0x18001b49d  call    cs:__imp_PathAllocCombine
0x18001b4a3  mov     ebx, eax
0x18001b4a5  test    eax, eax
0x18001b4a7  jns     short loc_18001B4E0
0x18001b4a9  mov     rcx, [rbp+1C8h]; this
0x18001b4b0  mov     r9d, eax; char *
0x18001b4b3  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001b4ba  mov     edx, 877h; void *
0x18001b4bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4c4  nop
0x18001b4c5  lea     rcx, [rsp+2C0h+var_2A0]
0x18001b4ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b4cf  nop
0x18001b4d0  lea     rcx, [rsp+2C0h+ppszPathOut]
0x18001b4d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b4da  nop
0x18001b4db  jmp     loc_18001B59C
0x18001b4e0  xor     edx, edx
0x18001b4e2  lea     rcx, [rsp+2C0h+var_2A0]
0x18001b4e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b4ec  lea     r8, [rsp+2C0h+var_2A0]; ppszPathOut
0x18001b4f1  mov     edx, edi; dwFlags
0x18001b4f3  mov     rcx, [rsp+2C0h+ppszPathOut]; pszPathIn
0x18001b4f8  call    cs:__imp_PathAllocCanonicalize
0x18001b4fe  mov     ebx, eax
0x18001b500  test    eax, eax
0x18001b502  jns     short loc_18001B538
0x18001b504  mov     rcx, [rbp+1C8h]; this
0x18001b50b  mov     r9d, eax; char *
0x18001b50e  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001b515  mov     edx, 878h; void *
0x18001b51a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b51f  nop
0x18001b520  lea     rcx, [rsp+2C0h+var_2A0]
0x18001b525  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b52a  nop
0x18001b52b  lea     rcx, [rsp+2C0h+ppszPathOut]
0x18001b530  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b535  nop
0x18001b536  jmp     short loc_18001B59C
0x18001b538  xor     edx, edx; Val
0x18001b53a  mov     r8d, 250h; Size
0x18001b540  lea     rcx, [rsp+2C0h+FindFileData]; void *
0x18001b545  call    memset_0
0x18001b54a  lea     rdx, [rsp+2C0h+FindFileData]; lpFindFileData
0x18001b54f  mov     rcx, [rsp+2C0h+var_2A0]; lpFileName
0x18001b554  call    cs:__imp_FindFirstFileW
0x18001b55a  mov     [rsp+2C0h+var_288], rax
0x18001b55f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b563  jz      short loc_18001B573
0x18001b565  cmp     [rsp+2C0h+FindFileData.dwFileAttributes], 0FFFFFFFFh
0x18001b56a  jz      short loc_18001B573
0x18001b56c  test    byte ptr [rsp+2C0h+FindFileData.dwFileAttributes], 10h
0x18001b571  jz      short loc_18001B576
0x18001b573  xor     dil, dil
0x18001b576  mov     [rsi], dil
0x18001b579  lea     rcx, [rsp+2C0h+var_288]
0x18001b57e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18001b583  nop
0x18001b584  lea     rcx, [rsp+2C0h+var_2A0]
0x18001b589  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b58e  nop
0x18001b58f  lea     rcx, [rsp+2C0h+ppszPathOut]
0x18001b594  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b599  nop
0x18001b59a  xor     ebx, ebx
0x18001b59c  lea     rcx, [rsp+2C0h+ppszPath]
0x18001b5a1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b5a6  mov     eax, ebx
0x18001b5a8  mov     rcx, [rbp+1C0h+var_30]
0x18001b5af  xor     rcx, rsp; StackCookie
0x18001b5b2  call    __security_check_cookie
0x18001b5b7  add     rsp, 2A8h
0x18001b5be  pop     rdi
0x18001b5bf  pop     rsi
0x18001b5c0  pop     rbx
0x18001b5c1  pop     rbp
0x18001b5c2  retn
```
