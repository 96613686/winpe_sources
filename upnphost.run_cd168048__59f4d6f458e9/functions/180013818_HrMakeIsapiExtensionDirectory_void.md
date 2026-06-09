# HrMakeIsapiExtensionDirectory(void)

- ea: `0x180013818`
- end: `0x180013a6a`
- name: `?HrMakeIsapiExtensionDirectory@@YAJXZ`
- size: `594`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001363c`

## callees

- `0x1800074dc`
- `0x1800075ac`
- `0x18000a060`
- `0x18000f8a0`
- `0x18001197c`
- `0x180012c40`
- `0x180013818`
- `0x180015794`
- `0x18002a030`
- `0x180032c6c`
- `0x18003b1cc`
- `0x18003cb60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001395a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013a31`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013a40`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001395a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013a31`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013a40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180013855`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180013855`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180013939`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180013939`

## string_xrefs

- `0x180013896`: `udhisapi.dll`
- `0x180013908`: `udhisapi.dll`

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
0x180013818  push    rbp
0x18001381a  push    rbx
0x18001381b  push    rsi
0x18001381c  push    rdi
0x18001381d  lea     rbp, [rsp-188h]
0x180013825  sub     rsp, 288h
0x18001382c  mov     rax, cs:__security_cookie
0x180013833  xor     rax, rsp
0x180013836  mov     [rbp+1A0h+var_30], rax
0x18001383d  xor     ebx, ebx
0x18001383f  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180013844  xor     edi, edi
0x180013846  mov     [rsp+2A0h+var_258], rbx
0x18001384b  mov     edx, 105h; uSize
0x180013850  mov     [rsp+2A0h+lpNewFileName], rdi
0x180013855  call    cs:__imp_GetSystemDirectoryW
0x18001385c  nop     dword ptr [rax+rax+00h]
0x180013861  dec     eax
0x180013863  cmp     eax, 102h
0x180013868  ja      short loc_1800138B8
0x18001386a  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001386f  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x180013874  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180013879  mov     esi, eax
0x18001387b  test    eax, eax
0x18001387d  js      short loc_1800138AE
0x18001387f  lea     rdx, asc_180063924; "\\"
0x180013886  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x18001388b  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180013890  mov     esi, eax
0x180013892  test    eax, eax
0x180013894  js      short loc_1800138AE
0x180013896  lea     rdx, aUdhisapiDll_0; "udhisapi.dll"
0x18001389d  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x1800138a2  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800138a7  mov     rdi, [rsp+2A0h+lpNewFileName]
0x1800138ac  jmp     short loc_1800138BD
0x1800138ae  mov     rdi, [rsp+2A0h+lpNewFileName]
0x1800138b3  jmp     loc_1800139F9
0x1800138b8  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800138bd  mov     esi, eax
0x1800138bf  test    eax, eax
0x1800138c1  js      loc_1800139FB
0x1800138c7  lea     rcx, [rsp+2A0h+var_258]; struct CUString *
0x1800138cc  mov     [rsp+2A0h+lpNewFileName], rbx
0x1800138d1  call    ?HrGetUPnPHostPath@@YAJAEAVCUString@@@Z; HrGetUPnPHostPath(CUString &)
0x1800138d6  mov     esi, eax
0x1800138d8  test    eax, eax
0x1800138da  js      short loc_180013957
0x1800138dc  lea     rdx, aUpnphost_2; "upnphost"
0x1800138e3  lea     rcx, [rsp+2A0h+var_258]; struct CUString *
0x1800138e8  call    ?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z; HrAddDirectoryToPath(CUString &,ushort const *)
0x1800138ed  mov     esi, eax
0x1800138ef  test    eax, eax
0x1800138f1  js      short loc_180013957
0x1800138f3  lea     rdx, [rsp+2A0h+var_258]; struct CUString *
0x1800138f8  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x1800138fd  call    ?HrAssign@CUString@@QEAAJAEBV1@@Z; CUString::HrAssign(CUString const &)
0x180013902  mov     esi, eax
0x180013904  test    eax, eax
0x180013906  js      short loc_180013952
0x180013908  lea     rdx, aUdhisapiDll_0; "udhisapi.dll"
0x18001390f  lea     rcx, [rsp+2A0h+lpNewFileName]; this
0x180013914  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180013919  mov     esi, eax
0x18001391b  test    eax, eax
0x18001391d  js      short loc_180013952
0x18001391f  mov     [rsp+2A0h+dwCopyFlags], ebx; dwCopyFlags
0x180013923  xor     r9d, r9d; lpData
0x180013926  mov     [rsp+2A0h+pbCancel], rbx; pbCancel
0x18001392b  xor     r8d, r8d; lpProgressRoutine
0x18001392e  mov     rbx, [rsp+2A0h+lpNewFileName]
0x180013933  mov     rcx, rdi; lpExistingFileName
0x180013936  mov     rdx, rbx; lpNewFileName
0x180013939  call    cs:__imp_CopyFileExW
0x180013940  nop     dword ptr [rax+rax+00h]
0x180013945  test    eax, eax
0x180013947  jnz     short loc_180013957
0x180013949  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001394e  mov     esi, eax
0x180013950  jmp     short loc_180013957
0x180013952  mov     rbx, [rsp+2A0h+lpNewFileName]
0x180013957  mov     rcx, rbx; Block
0x18001395a  call    cs:__imp_free
0x180013961  nop     dword ptr [rax+rax+00h]
0x180013966  test    esi, esi
0x180013968  js      loc_1800139F4
0x18001396e  lea     rcx, [rsp+2A0h+hKey]; HKEY *
0x180013973  mov     [rsp+2A0h+hKey], 0
0x18001397c  mov     [rsp+2A0h+lpNewFileName], 0
0x180013985  call    ?HrCreateOrOpenVRootsKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenVRootsKey(HKEY__ * *)
0x18001398a  mov     esi, eax
0x18001398c  test    eax, eax
0x18001398e  js      short loc_1800139F4
0x180013990  mov     rcx, [rsp+2A0h+hKey]; HKEY
0x180013995  lea     rax, [rsp+2A0h+lpNewFileName]
0x18001399a  mov     [rsp+2A0h+var_270], 0; unsigned int *
0x1800139a3  lea     rdx, aUpnphost_3; "/upnphost"
0x1800139aa  mov     qword ptr [rsp+2A0h+dwCopyFlags], rax; HKEY *
0x1800139af  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1800139b4  mov     rbx, [rsp+2A0h+var_258]
0x1800139b9  mov     esi, eax
0x1800139bb  test    eax, eax
0x1800139bd  js      short loc_1800139E1
0x1800139bf  mov     rcx, [rsp+2A0h+lpNewFileName]; HKEY
0x1800139c4  mov     r8, rbx; unsigned __int16 *
0x1800139c7  xor     edx, edx; unsigned __int16 *
0x1800139c9  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x1800139ce  mov     rcx, [rsp+2A0h+lpNewFileName]; hKey
0x1800139d3  mov     esi, eax
0x1800139d5  call    cs:__imp_RegCloseKey
0x1800139dc  nop     dword ptr [rax+rax+00h]
0x1800139e1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800139e6  call    cs:__imp_RegCloseKey
0x1800139ed  nop     dword ptr [rax+rax+00h]
0x1800139f2  jmp     short loc_1800139F9
0x1800139f4  mov     rbx, [rsp+2A0h+var_258]
0x1800139f9  test    esi, esi
0x1800139fb  jz      short loc_180013A2E
0x1800139fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a04  lea     rax, WPP_GLOBAL_Control
0x180013a0b  cmp     rcx, rax
0x180013a0e  jz      short loc_180013A2E
0x180013a10  test    byte ptr [rcx+1Ch], 1
0x180013a14  jz      short loc_180013A2E
0x180013a16  mov     rcx, [rcx+10h]
0x180013a1a  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x180013a21  mov     edx, 18h
0x180013a26  mov     r9d, esi
0x180013a29  call    WPP_SF_d
0x180013a2e  mov     rcx, rdi; Block
0x180013a31  call    cs:__imp_free
0x180013a38  nop     dword ptr [rax+rax+00h]
0x180013a3d  mov     rcx, rbx; Block
0x180013a40  call    cs:__imp_free
0x180013a47  nop     dword ptr [rax+rax+00h]
0x180013a4c  mov     eax, esi
0x180013a4e  mov     rcx, [rbp+1A0h+var_30]
0x180013a55  xor     rcx, rsp; StackCookie
0x180013a58  call    __security_check_cookie
0x180013a5d  add     rsp, 288h
0x180013a64  pop     rdi
0x180013a65  pop     rsi
0x180013a66  pop     rbx
0x180013a67  pop     rbp
0x180013a68  retn
```
