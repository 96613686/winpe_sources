# Windows::Security::Biometrics::FaceSharedUtilites::FaceSensorUtility::UpdateDeviceInterfacePathVectorFromCategoryGuid(_GUID * const &,std::vector<Microsoft::WRL::Wrappers::HString,std::allocator<Microsoft::WRL::Wrappers::HString>> *)

- ea: `0x180087240`
- end: `0x180087459`
- name: `?UpdateDeviceInterfacePathVectorFromCategoryGuid@FaceSensorUtility@FaceSharedUtilites@Biometrics@Security@Windows@@SAJAEBQEAU_GUID@@PEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180086eb8`

## callees

- `0x18005388c`
- `0x180069cc8`
- `0x18006af9c`
- `0x180083760`
- `0x180085774`
- `0x180087240`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800873a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800873f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800873a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800873f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800873ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800873ba`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180087299`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180087299`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180087335`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180087335`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800872a6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180087342`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800872a6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180087342`

## string_xrefs

- `0x18008726b`: `onecore\ds\security\biometrics\credprov\inc\FaceSharedUtilities.h`
- `0x1800872c7`: `onecore\ds\security\biometrics\credprov\inc\FaceSharedUtilities.h`
- `0x180087363`: `onecore\ds\security\biometrics\credprov\inc\FaceSharedUtilities.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Windows::Security::Biometrics::FaceSharedUtilites::FaceSensorUtility::UpdateDeviceInterfacePathVectorFromCategoryGuid(
        LPGUID *a1,
        __int64 a2)
{
  CONFIGRET Device_Interface_List_SizeW; // eax
  signed int v6; // eax
  unsigned int v7; // edi
  HRESULT v8; // r15d
  unsigned __int64 v9; // rax
  _WORD *v10; // rdi
  CONFIGRET Device_Interface_ListW; // eax
  signed int v12; // eax
  signed int v13; // esi
  ULONG v14; // esi
  __int64 v15; // r15
  HSTRING *v16; // rdx
  ULONG ulFlags; // [rsp+20h] [rbp-38h]
  ULONG ulFlagsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  ULONG pulLen; // [rsp+68h] [rbp+10h] BYREF
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF
  _WORD *v22; // [rsp+78h] [rbp+20h] BYREF

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\inc\\FaceSharedUtilities.h",
      (const char *)0x80070057LL,
      ulFlags);
    return 2147942487LL;
  }
  pulLen = 0;
  v22 = 0;
  Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(&pulLen, *a1, 0, 0);
  v6 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0xDu);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( (v7 & 0x80000000) == 0 )
  {
    v8 = 0;
    if ( pulLen > 1 )
    {
      v9 = 2LL * pulLen;
      if ( !is_mul_ok(pulLen, 2u) )
        v9 = -1;
      try
      {
        v10 = operator new[](v9);
        v22 = v10;
        memset_0(v10, 0, 2LL * pulLen);
        Device_Interface_ListW = CM_Get_Device_Interface_ListW(*a1, 0, v10, pulLen, 0);
        v12 = CM_MapCrToWin32Err(Device_Interface_ListW, 0xDu);
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
      }
      catch ( std::bad_alloc )
      {
        v7 = -2147024882;
        goto LABEL_29;
      }
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9E,
          (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\inc\\FaceSharedUtilities.h",
          (const char *)(unsigned int)v13,
          ulFlagsa);
        v7 = v13;
        goto LABEL_29;
      }
      v14 = 0;
      while ( *v10 && v14 < pulLen )
      {
        string = 0;
        v15 = -1;
        do
          ++v15;
        while ( v10[v15] );
        WindowsDeleteString(0);
        string = 0;
        v8 = WindowsCreateString(v10, v15, &string);
        if ( v8 >= 0 )
        {
          v16 = *(HSTRING **)(a2 + 8);
          if ( v16 == *(HSTRING **)(a2 + 16) )
          {
            std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(
              a2,
              v16,
              &string);
          }
          else
          {
            *v16 = string;
            string = 0;
            *(_QWORD *)(a2 + 8) += 8LL;
          }
        }
        while ( *v10 )
        {
          ++v14;
          ++v10;
        }
        if ( v14 < pulLen )
        {
          ++v14;
          ++v10;
        }
        WindowsDeleteString(string);
      }
    }
    v7 = v8;
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x88,
    (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\inc\\FaceSharedUtilities.h",
    (const char *)v7,
    ulFlags);
LABEL_29:
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v22);
  return v7;
}

```

## disassembly

```asm
0x180087240  mov     [rsp+arg_0], rbx
0x180087245  push    rsi
0x180087246  push    rdi
0x180087247  push    r13
0x180087249  push    r14
0x18008724b  push    r15
0x18008724d  sub     rsp, 30h
0x180087251  mov     r14, rdx
0x180087254  mov     rsi, rcx
0x180087257  xor     ebx, ebx
0x180087259  test    rdx, rdx
0x18008725c  jnz     short loc_180087282
0x18008725e  mov     rcx, [rsp+58h]; this
0x180087263  mov     ebx, 80070057h
0x180087268  mov     r9d, ebx; char *
0x18008726b  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\biometrics\\cred"...
0x180087272  lea     edx, [r14+7Eh]; void *
0x180087276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008727b  mov     eax, ebx
0x18008727d  jmp     loc_180087447
0x180087282  mov     [rsp+58h+pulLen], ebx
0x180087286  mov     [rsp+58h+arg_18], rbx
0x18008728b  xor     r9d, r9d; ulFlags
0x18008728e  xor     r8d, r8d; pDeviceID
0x180087291  mov     rdx, [rcx]; InterfaceClassGuid
0x180087294  lea     rcx, [rsp+58h+pulLen]; pulLen
0x180087299  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x18008729f  mov     edx, 0Dh; DefaultErr
0x1800872a4  mov     ecx, eax; CmReturnCode
0x1800872a6  call    cs:__imp_CM_MapCrToWin32Err
0x1800872ac  mov     edi, eax
0x1800872ae  test    eax, eax
0x1800872b0  jle     short loc_1800872BB
0x1800872b2  movzx   edi, ax
0x1800872b5  or      edi, 80070000h
0x1800872bb  test    edi, edi
0x1800872bd  jns     short loc_1800872DD
0x1800872bf  mov     rcx, [rsp+58h]; this
0x1800872c4  mov     r9d, edi; char *
0x1800872c7  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\biometrics\\cred"...
0x1800872ce  mov     edx, 88h; void *
0x1800872d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800872d8  jmp     loc_18008743B
0x1800872dd  mov     r15d, ebx
0x1800872e0  cmp     [rsp+58h+pulLen], 1
0x1800872e5  jbe     loc_180087438
0x1800872eb  mov     ecx, [rsp+58h+pulLen]
0x1800872ef  mov     eax, 2
0x1800872f4  mul     rcx
0x1800872f7  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800872fe  cmovb   rax, r13
0x180087302  mov     rcx, rax; unsigned __int64
0x180087305  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008730a  mov     rdi, rax
0x18008730d  mov     [rsp+58h+arg_18], rax
0x180087312  mov     r8d, [rsp+58h+pulLen]
0x180087317  add     r8, r8; Size
0x18008731a  xor     edx, edx; Val
0x18008731c  mov     rcx, rdi; void *
0x18008731f  call    memset_0
0x180087324  mov     [rsp+58h+ulFlags], ebx; int
0x180087328  mov     r9d, [rsp+58h+pulLen]; BufferLen
0x18008732d  mov     r8, rdi; Buffer
0x180087330  xor     edx, edx; pDeviceID
0x180087332  mov     rcx, [rsi]; InterfaceClassGuid
0x180087335  call    cs:__imp_CM_Get_Device_Interface_ListW
0x18008733b  mov     edx, 0Dh; DefaultErr
0x180087340  mov     ecx, eax; CmReturnCode
0x180087342  call    cs:__imp_CM_MapCrToWin32Err
0x180087348  mov     esi, eax
0x18008734a  test    eax, eax
0x18008734c  jle     short loc_180087357
0x18008734e  movzx   esi, ax
0x180087351  or      esi, 80070000h
0x180087357  test    esi, esi
0x180087359  jns     short loc_18008737B
0x18008735b  mov     rcx, [rsp+58h]; this
0x180087360  mov     r9d, esi; char *
0x180087363  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\biometrics\\cred"...
0x18008736a  mov     edx, 9Eh; void *
0x18008736f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087374  mov     edi, esi
0x180087376  jmp     loc_18008743B
0x18008737b  mov     esi, ebx
0x18008737d  cmp     [rdi], bx
0x180087380  jz      loc_180087438
0x180087386  cmp     esi, [rsp+58h+pulLen]
0x18008738a  jnb     loc_180087438
0x180087390  mov     [rsp+58h+string], rbx
0x180087395  mov     r15, r13
0x180087398  inc     r15
0x18008739b  cmp     [rdi+r15*2], bx
0x1800873a0  jnz     short loc_180087398
0x1800873a2  xor     ecx, ecx; string
0x1800873a4  call    cs:__imp_WindowsDeleteString
0x1800873aa  mov     [rsp+58h+string], rbx
0x1800873af  lea     r8, [rsp+58h+string]; string
0x1800873b4  mov     edx, r15d; length
0x1800873b7  mov     rcx, rdi; sourceString
0x1800873ba  call    cs:__imp_WindowsCreateString
0x1800873c0  mov     r15d, eax
0x1800873c3  test    eax, eax
0x1800873c5  js      short loc_180087408
0x1800873c7  mov     rdx, [r14+8]
0x1800873cb  cmp     rdx, [r14+10h]
0x1800873cf  jz      short loc_1800873E5
0x1800873d1  mov     rcx, [rsp+58h+string]
0x1800873d6  mov     [rdx], rcx
0x1800873d9  mov     [rsp+58h+string], rbx
0x1800873de  add     qword ptr [r14+8], 8
0x1800873e3  jmp     short loc_1800873F2
0x1800873e5  lea     r8, [rsp+58h+string]
0x1800873ea  mov     rcx, r14
0x1800873ed  call    ??$_Emplace_reallocate@VHString@Wrappers@WRL@Microsoft@@@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAPEAVHString@Wrappers@WRL@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString * const,Microsoft::WRL::Wrappers::HString &&)
0x1800873f2  jmp     short loc_180087408
0x1800873f4  mov     rcx, [rsp+58h+string]; string
0x1800873f9  call    cs:__imp_WindowsDeleteString
0x1800873ff  xor     ebx, ebx
0x180087401  mov     [rsp+58h+string], rbx
0x180087406  jmp     short loc_180087431
0x180087408  jmp     short loc_180087410
0x18008740a  inc     esi
0x18008740c  add     rdi, 2
0x180087410  cmp     [rdi], bx
0x180087413  jnz     short loc_18008740A
0x180087415  cmp     esi, [rsp+58h+pulLen]
0x180087419  jnb     short loc_180087421
0x18008741b  inc     esi
0x18008741d  add     rdi, 2
0x180087421  mov     rcx, [rsp+58h+string]; string
0x180087426  call    cs:__imp_WindowsDeleteString
0x18008742c  jmp     loc_18008737D
0x180087431  mov     edi, 8007000Eh
0x180087436  jmp     short loc_18008743B
0x180087438  mov     edi, r15d
0x18008743b  lea     rcx, [rsp+58h+arg_18]
0x180087440  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180087445  mov     eax, edi
0x180087447  mov     rbx, [rsp+58h+arg_0]
0x18008744c  add     rsp, 30h
0x180087450  pop     r15
0x180087452  pop     r14
0x180087454  pop     r13
0x180087456  pop     rdi
0x180087457  pop     rsi
0x180087458  retn
```
