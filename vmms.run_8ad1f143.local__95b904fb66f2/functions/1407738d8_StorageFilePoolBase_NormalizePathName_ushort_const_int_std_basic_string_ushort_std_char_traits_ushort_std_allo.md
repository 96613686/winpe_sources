# StorageFilePoolBase::NormalizePathName(ushort const *,int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,VmVirtualDiskPathType *,VmVirtualDiskFileType *)

- ea: `0x1407738d8`
- end: `0x140773bba`
- name: `?NormalizePathName@StorageFilePoolBase@@IEBAXPEBGHPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAW4VmVirtualDiskPathType@@PEAW4VmVirtualDiskFileType@@@Z`
- size: `738`
- prototype: `__int64 __usercall@<rax>(StorageFilePoolBase *this@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, loader_planting`

## callers

- `0x1403acf64`
- `0x140773dac`

## callees

- `0x140022640`
- `0x1400342a0`
- `0x14004bf10`
- `0x14004fd60`
- `0x14007a9d8`
- `0x1400ea77c`
- `0x1401c86a4`
- `0x1404828e0`
- `0x1407737e0`
- `0x1407738d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407739f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773a6c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773a8a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773aa8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773ac6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773ae0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773afa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773b14`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773b33`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407739f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773a6c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773a8a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773aa8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773ac6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773ae0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773afa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773b14`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140773b33`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x140773967`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x140773967`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x140773a43`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x140773a43`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x140773a26`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x140773a26`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1407739cb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1407739cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageFilePoolBase::NormalizePathName(
        StorageFilePoolBase *this,
        __int64 a2,
        int a3,
        __int64 a4,
        int *a5,
        int *a6)
{
  const unsigned __int16 *v9; // rdx
  int v10; // esi
  int v11; // ebx
  const WCHAR *v12; // rcx
  const WCHAR *v13; // rcx
  LPCWSTR *v14; // rcx
  WCHAR *v15; // rcx
  const WCHAR *v16; // rcx
  LPWSTR ExtensionW; // rax
  LPWSTR v18; // rdi
  LPCWSTR *v19; // rax
  __int64 v20; // rdx
  LPCWSTR pszPath[3]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  std::wstring::wstring(pszPath, a2);
  v9 = (const unsigned __int16 *)pszPath;
  if ( v23 > 7 )
    v9 = pszPath[0];
  if ( (unsigned int)StorageFilePoolBase::IsPrimordialDefaultBaseDirectory(this, v9) )
  {
    v10 = 2;
    v11 = 1;
  }
  else
  {
    v12 = (const WCHAR *)pszPath;
    if ( v23 > 7 )
      v12 = pszPath[0];
    v11 = 2;
    if ( PathIsRelativeW(v12) )
    {
      v10 = 3;
    }
    else
    {
      v10 = 2;
      if ( a3 )
      {
        ExpandEnvironmentVariables((LPCWSTR)pszPath);
        GetUncPathName((LPCWSTR)pszPath);
      }
      v13 = (const WCHAR *)pszPath;
      if ( v23 > 7 )
        v13 = pszPath[0];
      if ( GetFullPathNameW(v13, 0x104u, Buffer, 0) - 1 <= 0x102 )
      {
        v14 = pszPath;
        if ( v23 > 7 )
          v14 = (LPCWSTR *)pszPath[0];
        if ( (unsigned int)_o__wcsicmp(v14, Buffer) )
          std::wstring::assign(pszPath, Buffer);
      }
    }
    v15 = (WCHAR *)pszPath;
    if ( v23 > 7 )
      v15 = (WCHAR *)pszPath[0];
    PathRemoveBackslashW(v15);
    v16 = (const WCHAR *)pszPath;
    if ( v23 > 7 )
      v16 = pszPath[0];
    ExtensionW = PathFindExtensionW(v16);
    v18 = ExtensionW;
    if ( *ExtensionW )
    {
      if ( (unsigned int)_o__wcsicmp(ExtensionW, L".VHD")
        && (unsigned int)_o__wcsicmp(v18, L".AVHD")
        && (unsigned int)_o__wcsicmp(v18, L".VHDX")
        && (unsigned int)_o__wcsicmp(v18, L".AVHDX")
        && (unsigned int)_o__wcsicmp(v18, L".VHDS")
        && (unsigned int)_o__wcsicmp(v18, L".VHDPMEM") )
      {
        if ( (unsigned int)_o__wcsicmp(v18, L".ISO") )
          v11 = ((unsigned int)_o__wcsicmp(v18, L".VFD") != 0) + 4;
        else
          v11 = 3;
      }
    }
    else
    {
      v11 = 1;
    }
    v19 = pszPath;
    if ( v23 > 7 )
      v19 = (LPCWSTR *)pszPath[0];
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v19 + v20) );
    std::wstring::resize(pszPath);
  }
  std::wstring::swap(a4, pszPath);
  *a5 = v10;
  *a6 = v11;
  return std::wstring::_Tidy_deallocate(pszPath);
}

```

## disassembly

```asm
0x1407738d8  mov     [rsp-8+arg_0], rbx
0x1407738dd  push    rbp
0x1407738de  push    rsi
0x1407738df  push    rdi
0x1407738e0  push    r12
0x1407738e2  push    r13
0x1407738e4  push    r14
0x1407738e6  push    r15
0x1407738e8  lea     rbp, [rsp-160h]
0x1407738f0  sub     rsp, 260h
0x1407738f7  mov     rax, cs:__security_cookie
0x1407738fe  xor     rax, rsp
0x140773901  mov     [rbp+190h+var_40], rax
0x140773908  mov     r14, r9
0x14077390b  mov     edi, r8d
0x14077390e  mov     rbx, rcx
0x140773911  mov     r15, [rbp+190h+arg_20]
0x140773918  mov     r12, [rbp+190h+arg_28]
0x14077391f  lea     rcx, [rsp+290h+pszPath]
0x140773924  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140773929  nop
0x14077392a  lea     rdx, [rsp+290h+pszPath]
0x14077392f  cmp     [rsp+290h+var_258], 7
0x140773935  cmova   rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x14077393b  mov     rcx, rbx; this
0x14077393e  call    ?IsPrimordialDefaultBaseDirectory@StorageFilePoolBase@@IEBAHPEBG@Z; StorageFilePoolBase::IsPrimordialDefaultBaseDirectory(ushort const *)
0x140773943  xor     r13d, r13d
0x140773946  test    eax, eax
0x140773948  jz      short loc_140773956
0x14077394a  lea     esi, [r13+2]
0x14077394e  lea     ebx, [rsi-1]
0x140773951  jmp     loc_140773B71
0x140773956  lea     rcx, [rsp+290h+pszPath]
0x14077395b  cmp     [rsp+290h+var_258], 7
0x140773961  cmova   rcx, [rsp+290h+pszPath]; pszPath
0x140773967  call    cs:__imp_PathIsRelativeW
0x14077396e  nop     dword ptr [rax+rax+00h]
0x140773973  mov     ebx, 2
0x140773978  test    eax, eax
0x14077397a  jz      short loc_140773984
0x14077397c  lea     esi, [rbx+1]
0x14077397f  jmp     loc_140773A15
0x140773984  mov     esi, ebx
0x140773986  test    edi, edi
0x140773988  jz      short loc_1407739AD
0x14077398a  lea     rdx, [rsp+290h+pszPath]
0x14077398f  lea     rcx, [rsp+290h+pszPath]; lpSrc
0x140773994  call    ?ExpandEnvironmentVariables@@YAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@K@Z; ExpandEnvironmentVariables(std::wstring const &,std::wstring &,ulong)
0x140773999  xor     r9d, r9d
0x14077399c  lea     r8, [rsp+290h+pszPath]
0x1407739a1  xor     edx, edx
0x1407739a3  lea     rcx, [rsp+290h+pszPath]; lpLocalPath
0x1407739a8  call    ?GetUncPathName@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@EAEAV12@PEAE@Z; GetUncPathName(std::wstring const &,uchar,std::wstring &,uchar *)
0x1407739ad  lea     rcx, [rsp+290h+pszPath]
0x1407739b2  cmp     [rsp+290h+var_258], 7
0x1407739b8  cmova   rcx, [rsp+290h+pszPath]; lpFileName
0x1407739be  xor     r9d, r9d; lpFilePart
0x1407739c1  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x1407739c6  mov     edx, 104h; nBufferLength
0x1407739cb  call    cs:__imp_GetFullPathNameW
0x1407739d2  nop     dword ptr [rax+rax+00h]
0x1407739d7  dec     eax
0x1407739d9  cmp     eax, 102h
0x1407739de  ja      short loc_140773A15
0x1407739e0  lea     rcx, [rsp+290h+pszPath]
0x1407739e5  cmp     [rsp+290h+var_258], 7
0x1407739eb  cmova   rcx, [rsp+290h+pszPath]
0x1407739f1  lea     rdx, [rsp+290h+Buffer]
0x1407739f6  call    cs:__imp__o__wcsicmp
0x1407739fd  nop     dword ptr [rax+rax+00h]
0x140773a02  test    eax, eax
0x140773a04  jz      short loc_140773A15
0x140773a06  lea     rdx, [rsp+290h+Buffer]
0x140773a0b  lea     rcx, [rsp+290h+pszPath]
0x140773a10  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140773a15  lea     rcx, [rsp+290h+pszPath]
0x140773a1a  cmp     [rsp+290h+var_258], 7
0x140773a20  cmova   rcx, [rsp+290h+pszPath]; pszPath
0x140773a26  call    cs:__imp_PathRemoveBackslashW
0x140773a2d  nop     dword ptr [rax+rax+00h]
0x140773a32  lea     rcx, [rsp+290h+pszPath]
0x140773a37  cmp     [rsp+290h+var_258], 7
0x140773a3d  cmova   rcx, [rsp+290h+pszPath]; pszPath
0x140773a43  call    cs:__imp_PathFindExtensionW
0x140773a4a  nop     dword ptr [rax+rax+00h]
0x140773a4f  mov     rdi, rax
0x140773a52  cmp     [rax], r13w
0x140773a56  jnz     short loc_140773A62
0x140773a58  mov     ebx, 1
0x140773a5d  jmp     loc_140773B48
0x140773a62  lea     rdx, aVhd; ".VHD"
0x140773a69  mov     rcx, rdi
0x140773a6c  call    cs:__imp__o__wcsicmp
0x140773a73  nop     dword ptr [rax+rax+00h]
0x140773a78  test    eax, eax
0x140773a7a  jz      loc_140773B48
0x140773a80  lea     rdx, aAvhd; ".AVHD"
0x140773a87  mov     rcx, rdi
0x140773a8a  call    cs:__imp__o__wcsicmp
0x140773a91  nop     dword ptr [rax+rax+00h]
0x140773a96  test    eax, eax
0x140773a98  jz      loc_140773B48
0x140773a9e  lea     rdx, aVhdx_0; ".VHDX"
0x140773aa5  mov     rcx, rdi
0x140773aa8  call    cs:__imp__o__wcsicmp
0x140773aaf  nop     dword ptr [rax+rax+00h]
0x140773ab4  test    eax, eax
0x140773ab6  jz      loc_140773B48
0x140773abc  lea     rdx, aAvhdx; ".AVHDX"
0x140773ac3  mov     rcx, rdi
0x140773ac6  call    cs:__imp__o__wcsicmp
0x140773acd  nop     dword ptr [rax+rax+00h]
0x140773ad2  test    eax, eax
0x140773ad4  jz      short loc_140773B48
0x140773ad6  lea     rdx, aVhds_0; ".VHDS"
0x140773add  mov     rcx, rdi
0x140773ae0  call    cs:__imp__o__wcsicmp
0x140773ae7  nop     dword ptr [rax+rax+00h]
0x140773aec  test    eax, eax
0x140773aee  jz      short loc_140773B48
0x140773af0  lea     rdx, aVhdpmem; ".VHDPMEM"
0x140773af7  mov     rcx, rdi
0x140773afa  call    cs:__imp__o__wcsicmp
0x140773b01  nop     dword ptr [rax+rax+00h]
0x140773b06  test    eax, eax
0x140773b08  jz      short loc_140773B48
0x140773b0a  lea     rdx, aIso_0; ".ISO"
0x140773b11  mov     rcx, rdi
0x140773b14  call    cs:__imp__o__wcsicmp
0x140773b1b  nop     dword ptr [rax+rax+00h]
0x140773b20  test    eax, eax
0x140773b22  jnz     short loc_140773B29
0x140773b24  lea     ebx, [rax+3]
0x140773b27  jmp     short loc_140773B48
0x140773b29  lea     rdx, aVfd_1; ".VFD"
0x140773b30  mov     rcx, rdi
0x140773b33  call    cs:__imp__o__wcsicmp
0x140773b3a  nop     dword ptr [rax+rax+00h]
0x140773b3f  neg     eax
0x140773b41  sbb     ebx, ebx
0x140773b43  neg     ebx
0x140773b45  add     ebx, 4
0x140773b48  lea     rax, [rsp+290h+pszPath]
0x140773b4d  cmp     [rsp+290h+var_258], 7
0x140773b53  cmova   rax, [rsp+290h+pszPath]
0x140773b59  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140773b5d  inc     rdx
0x140773b60  cmp     [rax+rdx*2], r13w
0x140773b65  jnz     short loc_140773B5D
0x140773b67  lea     rcx, [rsp+290h+pszPath]; Src
0x140773b6c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140773b71  lea     rdx, [rsp+290h+pszPath]
0x140773b76  mov     rcx, r14
0x140773b79  call    ?swap@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXAEAV12@@Z; std::wstring::swap(std::wstring &)
0x140773b7e  mov     [r15], esi
0x140773b81  mov     [r12], ebx
0x140773b85  lea     rcx, [rsp+290h+pszPath]
0x140773b8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140773b8f  mov     rcx, [rbp+190h+var_40]
0x140773b96  xor     rcx, rsp; StackCookie
0x140773b99  call    __security_check_cookie
0x140773b9e  mov     rbx, [rsp+290h+arg_0]
0x140773ba6  add     rsp, 260h
0x140773bad  pop     r15
0x140773baf  pop     r14
0x140773bb1  pop     r13
0x140773bb3  pop     r12
0x140773bb5  pop     rdi
0x140773bb6  pop     rsi
0x140773bb7  pop     rbp
0x140773bb8  retn
```
