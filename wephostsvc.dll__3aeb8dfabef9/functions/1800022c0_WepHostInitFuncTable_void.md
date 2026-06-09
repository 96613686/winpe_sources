# WepHostInitFuncTable(void)

- ea: `0x1800022c0`
- end: `0x180002483`
- name: `?WepHostInitFuncTable@@YAJXZ`
- size: `451`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800030b8`

## callees

- `0x180001af4`
- `0x180001c94`
- `0x180001e04`
- `0x180001e44`
- `0x1800022c0`
- `0x180003ba6`
- `0x180003bb2`
- `0x180003be0`
- `0x180003c70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002416`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002416`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002443`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000244b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000244b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002376`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002376`

## string_xrefs

- `0x180002345`: `ThirdPartyEncryptionProviderPath`

## pseudocode

```c
__int64 WepHostInitFuncTable(void)
{
  int ValueW; // ebx
  int v1; // r8d
  HMODULE Library; // rdi
  HINSTANCE *v3; // rdx
  struct _tagPluginAPITable *v4; // r8
  DWORD pcbData[4]; // [rsp+40h] [rbp-1028h] BYREF
  WCHAR LibFileName[1024]; // [rsp+50h] [rbp-1018h] BYREF
  _BYTE Src[2048]; // [rsp+850h] [rbp-818h] BYREF

  memset_0(LibFileName, 0, sizeof(LibFileName));
  qword_180008738 = 0;
  g_Table = 0;
  g_hInstance = 0;
  xmmword_180008718 = 0;
  xmmword_180008728 = 0;
  memset_0(Src, 0, sizeof(Src));
  pcbData[0] = 1024;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\EAS",
             L"ThirdPartyEncryptionProviderPath",
             2u,
             0,
             Src,
             pcbData);
  if ( ValueW )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_0a8a2aca17d93ada2ba29531c7708c53_Traceguids,
        (unsigned int)ValueW);
  }
  else
  {
    memcpy_0(LibFileName, Src, sizeof(LibFileName));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v1, 0, (__int64)LibFileName);
    Library = LoadLibraryExW(LibFileName, 0, 0x1160u);
    if ( Library )
    {
      ValueW = ValidateSigning(LibFileName);
      if ( !ValueW )
        ValueW = ValidateInterfaces(LibFileName, v3, v4);
      FreeLibrary(Library);
    }
    else
    {
      ValueW = GetLastError();
    }
  }
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800022c0  mov     [rsp+arg_0], rbx
0x1800022c5  push    rdi
0x1800022c6  mov     eax, 1060h
0x1800022cb  call    _alloca_probe
0x1800022d0  sub     rsp, rax
0x1800022d3  mov     rax, cs:__security_cookie
0x1800022da  xor     rax, rsp
0x1800022dd  mov     [rsp+1068h+var_18], rax
0x1800022e5  mov     edi, 800h
0x1800022ea  lea     rcx, [rsp+1068h+LibFileName]; void *
0x1800022ef  mov     r8d, edi; Size
0x1800022f2  xor     edx, edx; Val
0x1800022f4  call    memset_0
0x1800022f9  xorps   xmm0, xmm0
0x1800022fc  lea     rcx, [rsp+1068h+Src]; void *
0x180002304  xor     eax, eax
0x180002306  mov     r8d, edi; Size
0x180002309  xor     edx, edx; Val
0x18000230b  mov     cs:qword_180008738, rax
0x180002312  movups  cs:?g_Table@@3U_tagPluginAPITable@@A, xmm0; _tagPluginAPITable g_Table
0x180002319  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstance
0x180002320  movups  cs:xmmword_180008718, xmm0
0x180002327  movups  cs:xmmword_180008728, xmm0
0x18000232e  call    memset_0
0x180002333  lea     rax, [rsp+1068h+var_1028]
0x180002338  mov     [rsp+1068h+var_1028], 400h
0x180002340  mov     [rsp+1068h+pcbData], rax; pcbData
0x180002345  lea     r8, Value; "ThirdPartyEncryptionProviderPath"
0x18000234c  lea     rax, [rsp+1068h+Src]
0x180002354  mov     r9d, 2; dwFlags
0x18000235a  mov     [rsp+1068h+pvData], rax; pvData
0x18000235f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\EAS"
0x180002366  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000236d  mov     [rsp+1068h+pdwType], 0; pdwType
0x180002376  call    cs:__imp_RegGetValueW
0x18000237c  mov     ebx, eax
0x18000237e  test    eax, eax
0x180002380  jz      short loc_1800023C0
0x180002382  mov     rcx, cs:WPP_GLOBAL_Control
0x180002389  lea     rax, WPP_GLOBAL_Control
0x180002390  cmp     rcx, rax
0x180002393  jz      loc_180002453
0x180002399  test    byte ptr [rcx+1Ch], 1
0x18000239d  jz      loc_180002453
0x1800023a3  mov     rcx, [rcx+10h]
0x1800023a7  lea     r8, WPP_0a8a2aca17d93ada2ba29531c7708c53_Traceguids
0x1800023ae  mov     edx, 0Ch
0x1800023b3  mov     r9d, ebx
0x1800023b6  call    WPP_SF_D
0x1800023bb  jmp     loc_180002453
0x1800023c0  lea     rcx, [rsp+1068h+LibFileName]; void *
0x1800023c5  mov     r8, rdi; Size
0x1800023c8  lea     rdx, [rsp+1068h+Src]; Src
0x1800023d0  call    memcpy_0
0x1800023d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023dc  lea     rax, WPP_GLOBAL_Control
0x1800023e3  cmp     rcx, rax
0x1800023e6  jz      short loc_180002409
0x1800023e8  test    byte ptr [rcx+1Ch], 1
0x1800023ec  jz      short loc_180002409
0x1800023ee  mov     rcx, [rcx+10h]
0x1800023f2  lea     rax, [rsp+1068h+LibFileName]
0x1800023f7  mov     edx, 0Dh
0x1800023fc  mov     [rsp+1068h+pdwType], rax
0x180002401  xor     r9d, r9d
0x180002404  call    WPP_SF_DS
0x180002409  xor     edx, edx; hFile
0x18000240b  lea     rcx, [rsp+1068h+LibFileName]; lpLibFileName
0x180002410  mov     r8d, 1160h; dwFlags
0x180002416  call    cs:__imp_LoadLibraryExW
0x18000241c  mov     rdi, rax
0x18000241f  test    rax, rax
0x180002422  jz      short loc_18000244B
0x180002424  lea     rcx, [rsp+1068h+LibFileName]; unsigned __int16 *
0x180002429  call    ?ValidateSigning@@YAKPEBG@Z; ValidateSigning(ushort const *)
0x18000242e  mov     ebx, eax
0x180002430  test    eax, eax
0x180002432  jnz     short loc_180002440
0x180002434  lea     rcx, [rsp+1068h+LibFileName]; unsigned __int16 *
0x180002439  call    ?ValidateInterfaces@@YAKPEBGAEAPEAUHINSTANCE__@@AEAU_tagPluginAPITable@@@Z; ValidateInterfaces(ushort const *,HINSTANCE__ * &,_tagPluginAPITable &)
0x18000243e  mov     ebx, eax
0x180002440  mov     rcx, rdi; hLibModule
0x180002443  call    cs:__imp_FreeLibrary
0x180002449  jmp     short loc_180002453
0x18000244b  call    cs:__imp_GetLastError
0x180002451  mov     ebx, eax
0x180002453  test    ebx, ebx
0x180002455  jle     short loc_180002460
0x180002457  movzx   ebx, bx
0x18000245a  or      ebx, 80070000h
0x180002460  mov     eax, ebx
0x180002462  mov     rcx, [rsp+1068h+var_18]
0x18000246a  xor     rcx, rsp; StackCookie
0x18000246d  call    __security_check_cookie
0x180002472  mov     rbx, [rsp+1068h+arg_0]
0x18000247a  add     rsp, 1060h
0x180002481  pop     rdi
0x180002482  retn
```
