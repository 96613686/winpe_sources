# HrMakeIsapiExtensionDirectory(void)

- ea: `0x18001e790`
- end: `0x18001e9b3`
- name: `?HrMakeIsapiExtensionDirectory@@YAJXZ`
- size: `547`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e5c0`

## callees

- `0x18001347c`
- `0x180013544`
- `0x180015d90`
- `0x18001ab90`
- `0x18001ca98`
- `0x18001d048`
- `0x18001e790`
- `0x180020544`
- `0x18002072c`
- `0x1800311bc`
- `0x180038ce4`
- `0x18003a560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e8c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e987`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e990`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e8c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e987`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e990`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e942`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e942`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e7cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e7cd`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001e8ab`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001e8ab`

## string_xrefs

- `0x18001e808`: `udhisapi.dll`
- `0x18001e87a`: `udhisapi.dll`

## pseudocode

```c
__int64 HrMakeIsapiExtensionDirectory(void)
{
  void *v0; // rbx
  WCHAR *v1; // rdi
  int UPnPHostPath; // esi
  int Win32Error; // eax
  bool v4; // zf
  unsigned int v5; // r8d
  unsigned int v6; // r9d
  int Key; // eax
  struct _SECURITY_ATTRIBUTES *pbCancel; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpNewFileName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v11; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v0 = 0;
  v1 = 0;
  v11 = 0;
  lpNewFileName = 0;
  if ( GetSystemDirectoryW(Buffer, 0x105u) - 1 > 0x102 )
  {
    Win32Error = HrFromLastWin32Error();
  }
  else
  {
    UPnPHostPath = CUString::HrAssign((CUString *)&lpNewFileName, Buffer);
    if ( UPnPHostPath < 0 || (UPnPHostPath = CUString::HrAppend((CUString *)&lpNewFileName, L"\\"), UPnPHostPath < 0) )
    {
      v1 = (WCHAR *)lpNewFileName;
LABEL_21:
      v4 = UPnPHostPath == 0;
      goto LABEL_22;
    }
    Win32Error = CUString::HrAppend((CUString *)&lpNewFileName, L"udhisapi.dll");
    v1 = (WCHAR *)lpNewFileName;
  }
  UPnPHostPath = Win32Error;
  v4 = Win32Error == 0;
  if ( Win32Error >= 0 )
  {
    lpNewFileName = 0;
    UPnPHostPath = HrGetUPnPHostPath((struct CUString *)&v11);
    if ( UPnPHostPath >= 0 )
    {
      UPnPHostPath = HrAddDirectoryToPath((struct CUString *)&v11, L"upnphost");
      if ( UPnPHostPath >= 0 )
      {
        UPnPHostPath = CUString::HrAssign((CUString *)&lpNewFileName, (const struct CUString *)&v11);
        if ( UPnPHostPath < 0
          || (UPnPHostPath = CUString::HrAppend((CUString *)&lpNewFileName, L"udhisapi.dll"), UPnPHostPath < 0) )
        {
          v0 = (void *)lpNewFileName;
        }
        else
        {
          v0 = (void *)lpNewFileName;
          if ( !CopyFileExW(v1, lpNewFileName, 0, 0, 0, 0) )
            UPnPHostPath = HrFromLastWin32Error();
        }
      }
    }
    free(v0);
    if ( UPnPHostPath < 0
      || (hKey = 0, lpNewFileName = 0, UPnPHostPath = HrCreateOrOpenVRootsKey(&hKey), UPnPHostPath < 0) )
    {
      v0 = v11;
    }
    else
    {
      Key = HrRegCreateKeyEx(hKey, L"/upnphost", v5, v6, pbCancel, (HKEY *)&lpNewFileName, 0);
      v0 = v11;
      UPnPHostPath = Key;
      if ( Key >= 0 )
      {
        UPnPHostPath = HrRegSetSz((HKEY)lpNewFileName, 0, v11);
        RegCloseKey((HKEY)lpNewFileName);
      }
      RegCloseKey(hKey);
    }
    goto LABEL_21;
  }
LABEL_22:
  if ( !v4 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_cd0457ca62d634003859bdcf9006b616_Traceguids,
      (unsigned int)UPnPHostPath);
  free(v1);
  free(v0);
  return (unsigned int)UPnPHostPath;
}

```

## disassembly

```asm
0x18001e790  push    rbp
0x18001e792  push    rbx
0x18001e793  push    rsi
0x18001e794  push    rdi
0x18001e795  lea     rbp, [rsp-188h]
0x18001e79d  sub     rsp, 288h
0x18001e7a4  mov     rax, cs:__security_cookie
0x18001e7ab  xor     rax, rsp
0x18001e7ae  mov     [rbp+1A0h+var_30], rax
0x18001e7b5  xor     ebx, ebx
0x18001e7b7  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18001e7bc  xor     edi, edi
0x18001e7be  mov     [rsp+2A0h+var_258], rbx
0x18001e7c3  mov     edx, 105h; uSize
0x18001e7c8  mov     [rsp+2A0h+lpNewFileName], rdi
0x18001e7cd  call    cs:__imp_GetSystemDirectoryW
0x18001e7d3  dec     eax
0x18001e7d5  cmp     eax, 102h
0x18001e7da  ja      short loc_18001E82A
0x18001e7dc  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001e7e1  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x18001e7e6  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18001e7eb  mov     esi, eax
0x18001e7ed  test    eax, eax
0x18001e7ef  js      short loc_18001E820
0x18001e7f1  lea     rdx, asc_180060164; "\\"
0x18001e7f8  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x18001e7fd  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18001e802  mov     esi, eax
0x18001e804  test    eax, eax
0x18001e806  js      short loc_18001E820
0x18001e808  lea     rdx, aUdhisapiDll_0; "udhisapi.dll"
0x18001e80f  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x18001e814  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18001e819  mov     rdi, [rsp+2A0h+lpNewFileName]
0x18001e81e  jmp     short loc_18001E82F
0x18001e820  mov     rdi, [rsp+2A0h+lpNewFileName]
0x18001e825  jmp     loc_18001E94F
0x18001e82a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001e82f  mov     esi, eax
0x18001e831  test    eax, eax
0x18001e833  js      loc_18001E951
0x18001e839  lea     rcx, [rsp+2A0h+var_258]; struct CUString *
0x18001e83e  mov     [rsp+2A0h+lpNewFileName], rbx
0x18001e843  call    ?HrGetUPnPHostPath@@YAJAEAVCUString@@@Z; HrGetUPnPHostPath(CUString &)
0x18001e848  mov     esi, eax
0x18001e84a  test    eax, eax
0x18001e84c  js      short loc_18001E8C3
0x18001e84e  lea     rdx, aUpnphost_2; "upnphost"
0x18001e855  lea     rcx, [rsp+2A0h+var_258]; struct CUString *
0x18001e85a  call    ?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z; HrAddDirectoryToPath(CUString &,ushort const *)
0x18001e85f  mov     esi, eax
0x18001e861  test    eax, eax
0x18001e863  js      short loc_18001E8C3
0x18001e865  lea     rdx, [rsp+2A0h+var_258]; struct CUString *
0x18001e86a  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x18001e86f  call    ?HrAssign@CUString@@QEAAJAEBV1@@Z; CUString::HrAssign(CUString const &)
0x18001e874  mov     esi, eax
0x18001e876  test    eax, eax
0x18001e878  js      short loc_18001E8BE
0x18001e87a  lea     rdx, aUdhisapiDll_0; "udhisapi.dll"
0x18001e881  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x18001e886  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18001e88b  mov     esi, eax
0x18001e88d  test    eax, eax
0x18001e88f  js      short loc_18001E8BE
0x18001e891  mov     [rsp+2A0h+dwCopyFlags], ebx; dwCopyFlags
0x18001e895  xor     r9d, r9d; lpData
0x18001e898  mov     [rsp+2A0h+pbCancel], rbx; pbCancel
0x18001e89d  xor     r8d, r8d; lpProgressRoutine
0x18001e8a0  mov     rbx, [rsp+2A0h+lpNewFileName]
0x18001e8a5  mov     rcx, rdi; lpExistingFileName
0x18001e8a8  mov     rdx, rbx; lpNewFileName
0x18001e8ab  call    cs:__imp_CopyFileExW
0x18001e8b1  test    eax, eax
0x18001e8b3  jnz     short loc_18001E8C3
0x18001e8b5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001e8ba  mov     esi, eax
0x18001e8bc  jmp     short loc_18001E8C3
0x18001e8be  mov     rbx, [rsp+2A0h+lpNewFileName]
0x18001e8c3  mov     rcx, rbx; Block
0x18001e8c6  call    cs:__imp_free
0x18001e8cc  test    esi, esi
0x18001e8ce  js      short loc_18001E94A
0x18001e8d0  lea     rcx, [rsp+2A0h+hKey]; HKEY *
0x18001e8d5  mov     [rsp+2A0h+hKey], 0
0x18001e8de  mov     [rsp+2A0h+lpNewFileName], 0
0x18001e8e7  call    ?HrCreateOrOpenVRootsKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenVRootsKey(HKEY__ * *)
0x18001e8ec  mov     esi, eax
0x18001e8ee  test    eax, eax
0x18001e8f0  js      short loc_18001E94A
0x18001e8f2  mov     rcx, [rsp+2A0h+hKey]; HKEY
0x18001e8f7  lea     rax, [rsp+2A0h+lpNewFileName]
0x18001e8fc  mov     [rsp+2A0h+var_270], 0; unsigned int *
0x18001e905  lea     rdx, aUpnphost_3; "/upnphost"
0x18001e90c  mov     qword ptr [rsp+2A0h+dwCopyFlags], rax; HKEY *
0x18001e911  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18001e916  mov     rbx, [rsp+2A0h+var_258]
0x18001e91b  mov     esi, eax
0x18001e91d  test    eax, eax
0x18001e91f  js      short loc_18001E93D
0x18001e921  mov     rcx, [rsp+2A0h+lpNewFileName]; HKEY
0x18001e926  mov     r8, rbx; unsigned __int16 *
0x18001e929  xor     edx, edx; unsigned __int16 *
0x18001e92b  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18001e930  mov     rcx, [rsp+2A0h+lpNewFileName]; hKey
0x18001e935  mov     esi, eax
0x18001e937  call    cs:__imp_RegCloseKey
0x18001e93d  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001e942  call    cs:__imp_RegCloseKey
0x18001e948  jmp     short loc_18001E94F
0x18001e94a  mov     rbx, [rsp+2A0h+var_258]
0x18001e94f  test    esi, esi
0x18001e951  jz      short loc_18001E984
0x18001e953  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e95a  lea     rax, WPP_GLOBAL_Control
0x18001e961  cmp     rcx, rax
0x18001e964  jz      short loc_18001E984
0x18001e966  test    byte ptr [rcx+1Ch], 1
0x18001e96a  jz      short loc_18001E984
0x18001e96c  mov     rcx, [rcx+10h]
0x18001e970  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x18001e977  mov     edx, 18h
0x18001e97c  mov     r9d, esi
0x18001e97f  call    WPP_SF_d
0x18001e984  mov     rcx, rdi; Block
0x18001e987  call    cs:__imp_free
0x18001e98d  mov     rcx, rbx; Block
0x18001e990  call    cs:__imp_free
0x18001e996  mov     eax, esi
0x18001e998  mov     rcx, [rbp+1A0h+var_30]
0x18001e99f  xor     rcx, rsp; StackCookie
0x18001e9a2  call    __security_check_cookie
0x18001e9a7  add     rsp, 288h
0x18001e9ae  pop     rdi
0x18001e9af  pop     rsi
0x18001e9b0  pop     rbx
0x18001e9b1  pop     rbp
0x18001e9b2  retn
```
