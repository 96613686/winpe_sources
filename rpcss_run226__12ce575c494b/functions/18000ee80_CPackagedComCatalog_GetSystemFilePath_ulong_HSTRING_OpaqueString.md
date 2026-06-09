# CPackagedComCatalog::GetSystemFilePath(ulong,HSTRING__ *,OpaqueString &)

- ea: `0x18000ee80`
- end: `0x18000f017`
- name: `?GetSystemFilePath@CPackagedComCatalog@@CAJKPEAUHSTRING__@@AEAVOpaqueString@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(int, HSTRING, HSTRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c674`
- `0x18000ebf4`

## callees

- `0x18000bbe8`
- `0x18000d0dc`
- `0x18000ee80`
- `0x18000f1b8`
- `0x18002ba28`
- `0x1800a2004`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000eedb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000eedb`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18000f00c`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18000f00c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ef58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ef58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000eefb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000eefb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000ef7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000efeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000ef7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000efeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18000ef27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18000ef27`

## string_xrefs

- `0x18000efa8`: `Failed call to GetSystemDirectory/GetSystemWow64Directory2. desiredSystemArchitecture=%u`
- `0x18000efaf`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18000efcd`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetSystemFilePath(int a1, HSTRING a2, HSTRING *a3)
{
  UINT SystemDirectoryW; // eax
  UINT v7; // edi
  PCWSTR StringRawBuffer; // rax
  UINT32 v9; // edi
  PCWSTR v10; // r14
  HRESULT v11; // eax
  unsigned int v12; // ebx
  char *v14; // [rsp+20h] [rbp-E0h]
  UINT32 length; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR *charBuffer; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  memset_0(Buffer, 0, 0x208u);
  if ( a1 == GetNativeArchitecture() || a1 == 1 )
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  else
    SystemDirectoryW = GetSystemWow64Directory2W(Buffer, 260, (unsigned __int16)a1);
  v7 = SystemDirectoryW;
  if ( SystemDirectoryW )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
    v9 = length + v7;
    charBuffer = 0;
    v10 = StringRawBuffer;
    bufferHandle = 0;
    v11 = WindowsPreallocateStringBuffer(v9 + 1, &charBuffer, &bufferHandle);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1933,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)v11,
        (int)v14);
      if ( bufferHandle )
        WindowsDeleteStringBuffer(bufferHandle);
      return v12;
    }
    else
    {
      StringCchPrintfW(charBuffer, v9 + 2, L"%s\\%s", Buffer, v10);
      WindowsDeleteString(*a3);
      *a3 = 0;
      wil::make_hstring_from_buffer_nothrow(&bufferHandle, a3);
      if ( bufferHandle )
        WindowsDeleteStringBuffer(bufferHandle);
      return 0;
    }
  }
  else
  {
    LODWORD(v14) = a1;
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x1922,
             (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
             "Failed call to GetSystemDirectory/GetSystemWow64Directory2. desiredSystemArchitecture=%u",
             v14);
  }
}

```

## disassembly

```asm
0x18000ee80  push    rbp
0x18000ee82  push    rbx
0x18000ee83  push    rsi
0x18000ee84  push    rdi
0x18000ee85  push    r14
0x18000ee87  lea     rbp, [rsp-170h]
0x18000ee8f  sub     rsp, 270h
0x18000ee96  mov     rax, cs:__security_cookie
0x18000ee9d  xor     rax, rsp
0x18000eea0  mov     [rbp+190h+var_30], rax
0x18000eea7  mov     rsi, r8
0x18000eeaa  mov     r14, rdx
0x18000eead  mov     ebx, ecx
0x18000eeaf  xor     edx, edx; Val
0x18000eeb1  mov     r8d, 208h; Size
0x18000eeb7  lea     rcx, [rsp+290h+Buffer]; void *
0x18000eebc  call    memset_0
0x18000eec1  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x18000eec6  movzx   eax, ax
0x18000eec9  cmp     ebx, eax
0x18000eecb  jnz     loc_18000EFF5
0x18000eed1  mov     edx, 104h; uSize
0x18000eed6  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x18000eedb  call    cs:__imp_GetSystemDirectoryW
0x18000eee1  mov     edi, eax
0x18000eee3  test    eax, eax
0x18000eee5  jz      loc_18000EFA1
0x18000eeeb  lea     rdx, [rsp+290h+length]; length
0x18000eef0  mov     [rsp+290h+length], 0
0x18000eef8  mov     rcx, r14; string
0x18000eefb  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ef01  add     edi, [rsp+290h+length]
0x18000ef05  lea     r8, [rsp+290h+bufferHandle]; bufferHandle
0x18000ef0a  lea     rdx, [rsp+290h+charBuffer]; charBuffer
0x18000ef0f  mov     [rsp+290h+charBuffer], 0
0x18000ef18  mov     r14, rax
0x18000ef1b  mov     [rsp+290h+bufferHandle], 0
0x18000ef24  lea     ecx, [rdi+1]; length
0x18000ef27  call    cs:__imp_WindowsPreallocateStringBuffer
0x18000ef2d  mov     ebx, eax
0x18000ef2f  test    eax, eax
0x18000ef31  js      loc_18000EFC6
0x18000ef37  mov     rcx, [rsp+290h+charBuffer]; unsigned __int16 *
0x18000ef3c  lea     edx, [rdi+2]; unsigned __int64
0x18000ef3f  lea     r9, [rsp+290h+Buffer]
0x18000ef44  mov     [rsp+290h+var_270], r14
0x18000ef49  lea     r8, aSS; "%s\\%s"
0x18000ef50  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ef55  mov     rcx, [rsi]; string
0x18000ef58  call    cs:__imp_WindowsDeleteString
0x18000ef5e  mov     rdx, rsi
0x18000ef61  mov     qword ptr [rsi], 0
0x18000ef68  lea     rcx, [rsp+290h+bufferHandle]
0x18000ef6d  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x18000ef72  mov     rcx, [rsp+290h+bufferHandle]; bufferHandle
0x18000ef77  test    rcx, rcx
0x18000ef7a  jz      short loc_18000EF82
0x18000ef7c  call    cs:__imp_WindowsDeleteStringBuffer
0x18000ef82  xor     eax, eax
0x18000ef84  mov     rcx, [rbp+190h+var_30]
0x18000ef8b  xor     rcx, rsp; StackCookie
0x18000ef8e  call    __security_check_cookie
0x18000ef93  add     rsp, 270h
0x18000ef9a  pop     r14
0x18000ef9c  pop     rdi
0x18000ef9d  pop     rsi
0x18000ef9e  pop     rbx
0x18000ef9f  pop     rbp
0x18000efa0  retn
0x18000efa1  mov     rcx, [rbp+198h]; this
0x18000efa8  lea     r9, aFailedCallToGe_0; "Failed call to GetSystemDirectory/GetSy"...
0x18000efaf  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18000efb6  mov     dword ptr [rsp+290h+var_270], ebx; char *
0x18000efba  mov     edx, 1922h; void *
0x18000efbf  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000efc4  jmp     short loc_18000EF84
0x18000efc6  mov     rcx, [rbp+198h]; this
0x18000efcd  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18000efd4  mov     r9d, ebx; char *
0x18000efd7  mov     edx, 1933h; void *
0x18000efdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000efe1  mov     rcx, [rsp+290h+bufferHandle]; bufferHandle
0x18000efe6  test    rcx, rcx
0x18000efe9  jz      short loc_18000EFF1
0x18000efeb  call    cs:__imp_WindowsDeleteStringBuffer
0x18000eff1  mov     eax, ebx
0x18000eff3  jmp     short loc_18000EF84
0x18000eff5  cmp     ebx, 1
0x18000eff8  jz      loc_18000EED1
0x18000effe  movzx   r8d, bx
0x18000f002  lea     rcx, [rsp+290h+Buffer]
0x18000f007  mov     edx, 104h
0x18000f00c  call    cs:__imp_GetSystemWow64Directory2W
0x18000f012  jmp     loc_18000EEE1
```
