# LoadHttpHelperLibrary

- ea: `0x180090c5c`
- end: `0x180090d43`
- name: `LoadHttpHelperLibrary`
- size: `231`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18008f66c`
- `0x180093a00`

## callees

- `0x18000ec54`
- `0x18000ece0`
- `0x18001a008`
- `0x180090c5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090cd5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180090c73`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180090c73`

## string_xrefs

- `0x180090d12`: `Failed to load TSWorkspace.dll`
- `0x180090c6c`: `TSWorkspace.dll`

## pseudocode

```c
__int64 LoadHttpHelperLibrary()
{
  unsigned int ActivityIdPrefix; // eax
  signed int v1; // ebx
  signed int LastError; // eax
  int v4; // eax

  if ( g_hClaimsAuthHelperDll )
    return 0;
  g_hClaimsAuthHelperDll = LoadLibraryW(L"TSWorkspace.dll");
  if ( g_hClaimsAuthHelperDll )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
        ActivityIdPrefix);
    }
    return 0;
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
      v4,
      (__int64)"Failed to load TSWorkspace.dll",
      v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180090c5c  push    rbx
0x180090c5e  sub     rsp, 30h
0x180090c62  cmp     cs:?g_hClaimsAuthHelperDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hClaimsAuthHelperDll
0x180090c6a  jnz     short loc_180090CCB
0x180090c6c  lea     rcx, aTsworkspaceDll_0; "TSWorkspace.dll"
0x180090c73  call    cs:__imp_LoadLibraryW
0x180090c79  mov     cs:?g_hClaimsAuthHelperDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hClaimsAuthHelperDll
0x180090c80  test    rax, rax
0x180090c83  jz      short loc_180090CD5
0x180090c85  mov     rax, cs:WPP_GLOBAL_Control
0x180090c8c  lea     rcx, WPP_GLOBAL_Control
0x180090c93  cmp     rax, rcx
0x180090c96  jz      short loc_180090CCB
0x180090c98  test    dword ptr [rax+1Ch], 10000h
0x180090c9f  jz      short loc_180090CCB
0x180090ca1  cmp     byte ptr [rax+19h], 5
0x180090ca5  jb      short loc_180090CCB
0x180090ca7  call    RdpX_GetActivityIdPrefix
0x180090cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180090cb3  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180090cba  mov     edx, 12h
0x180090cbf  mov     r9d, eax
0x180090cc2  mov     rcx, [rcx+10h]
0x180090cc6  call    WPP_SF_D
0x180090ccb  xor     ebx, ebx
0x180090ccd  mov     eax, ebx
0x180090ccf  add     rsp, 30h
0x180090cd3  pop     rbx
0x180090cd4  retn
0x180090cd5  call    cs:__imp_GetLastError
0x180090cdb  mov     ebx, eax
0x180090cdd  test    eax, eax
0x180090cdf  jle     short loc_180090CEA
0x180090ce1  movzx   ebx, ax
0x180090ce4  or      ebx, 80070000h
0x180090cea  test    ebx, ebx
0x180090cec  jns     short loc_180090CCB
0x180090cee  mov     rax, cs:WPP_GLOBAL_Control
0x180090cf5  lea     rcx, WPP_GLOBAL_Control
0x180090cfc  cmp     rax, rcx
0x180090cff  jz      short loc_180090CCD
0x180090d01  test    byte ptr [rax+1Ch], 8
0x180090d05  jz      short loc_180090CCD
0x180090d07  cmp     byte ptr [rax+19h], 2
0x180090d0b  jb      short loc_180090CCD
0x180090d0d  call    RdpX_GetActivityIdPrefix
0x180090d12  lea     rcx, aFailedToLoadTs; "Failed to load TSWorkspace.dll"
0x180090d19  mov     [rsp+38h+var_10], ebx
0x180090d1d  mov     [rsp+38h+var_18], rcx
0x180090d22  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180090d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180090d30  mov     edx, 13h
0x180090d35  mov     r9d, eax
0x180090d38  mov     rcx, [rcx+10h]
0x180090d3c  call    WPP_SF_DsD
0x180090d41  jmp     short loc_180090CCD
```
