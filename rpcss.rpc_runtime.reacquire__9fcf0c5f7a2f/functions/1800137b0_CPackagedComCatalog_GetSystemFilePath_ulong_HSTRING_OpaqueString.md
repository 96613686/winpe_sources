# CPackagedComCatalog::GetSystemFilePath(ulong,HSTRING__ *,OpaqueString &)

- ea: `0x1800137b0`
- end: `0x180013972`
- name: `?GetSystemFilePath@CPackagedComCatalog@@CAJKPEAUHSTRING__@@AEAVOpaqueString@@@Z`
- size: `450`
- prototype: `static int(unsigned int, HSTRING, struct OpaqueString *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012430`
- `0x180027538`

## callees

- `0x18001037c`
- `0x180013080`
- `0x1800137b0`
- `0x180013b18`
- `0x1800210f8`
- `0x1800a778c`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001380b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001380b`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180013961`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180013961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001389a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001389a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800138c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18001393a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800138c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18001393a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180013863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180013863`

## string_xrefs

- `0x1800138f7`: `Failed call to GetSystemDirectory/GetSystemWow64Directory2. desiredSystemArchitecture=%u`
- `0x1800138fe`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18001391c`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
0x1800137b0  push    rbp
0x1800137b2  push    rbx
0x1800137b3  push    rsi
0x1800137b4  push    rdi
0x1800137b5  push    r14
0x1800137b7  lea     rbp, [rsp-170h]
0x1800137bf  sub     rsp, 270h
0x1800137c6  mov     rax, cs:__security_cookie
0x1800137cd  xor     rax, rsp
0x1800137d0  mov     [rbp+190h+var_30], rax
0x1800137d7  mov     rsi, r8
0x1800137da  mov     r14, rdx
0x1800137dd  mov     ebx, ecx
0x1800137df  xor     edx, edx; Val
0x1800137e1  mov     r8d, 208h; Size
0x1800137e7  lea     rcx, [rsp+290h+Buffer]; void *
0x1800137ec  call    memset_0
0x1800137f1  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x1800137f6  movzx   eax, ax
0x1800137f9  cmp     ebx, eax
0x1800137fb  jnz     loc_18001394A
0x180013801  mov     edx, 104h; uSize
0x180013806  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x18001380b  call    cs:__imp_GetSystemDirectoryW
0x180013812  nop     dword ptr [rax+rax+00h]
0x180013817  mov     edi, eax
0x180013819  test    eax, eax
0x18001381b  jz      loc_1800138F0
0x180013821  lea     rdx, [rsp+290h+length]; length
0x180013826  mov     [rsp+290h+length], 0
0x18001382e  mov     rcx, r14; string
0x180013831  call    cs:__imp_WindowsGetStringRawBuffer
0x180013838  nop     dword ptr [rax+rax+00h]
0x18001383d  add     edi, [rsp+290h+length]
0x180013841  lea     r8, [rsp+290h+bufferHandle]; bufferHandle
0x180013846  lea     rdx, [rsp+290h+charBuffer]; charBuffer
0x18001384b  mov     [rsp+290h+charBuffer], 0
0x180013854  mov     r14, rax
0x180013857  mov     [rsp+290h+bufferHandle], 0
0x180013860  lea     ecx, [rdi+1]; length
0x180013863  call    cs:__imp_WindowsPreallocateStringBuffer
0x18001386a  nop     dword ptr [rax+rax+00h]
0x18001386f  mov     ebx, eax
0x180013871  test    eax, eax
0x180013873  js      loc_180013915
0x180013879  mov     rcx, [rsp+290h+charBuffer]; unsigned __int16 *
0x18001387e  lea     edx, [rdi+2]; unsigned __int64
0x180013881  lea     r9, [rsp+290h+Buffer]
0x180013886  mov     [rsp+290h+var_270], r14
0x18001388b  lea     r8, aSS; "%s\\%s"
0x180013892  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013897  mov     rcx, [rsi]; string
0x18001389a  call    cs:__imp_WindowsDeleteString
0x1800138a1  nop     dword ptr [rax+rax+00h]
0x1800138a6  mov     rdx, rsi
0x1800138a9  mov     qword ptr [rsi], 0
0x1800138b0  lea     rcx, [rsp+290h+bufferHandle]
0x1800138b5  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1800138ba  mov     rcx, [rsp+290h+bufferHandle]; bufferHandle
0x1800138bf  test    rcx, rcx
0x1800138c2  jz      short loc_1800138D0
0x1800138c4  call    cs:__imp_WindowsDeleteStringBuffer
0x1800138cb  nop     dword ptr [rax+rax+00h]
0x1800138d0  xor     eax, eax
0x1800138d2  mov     rcx, [rbp+190h+var_30]
0x1800138d9  xor     rcx, rsp; StackCookie
0x1800138dc  call    __security_check_cookie
0x1800138e1  add     rsp, 270h
0x1800138e8  pop     r14
0x1800138ea  pop     rdi
0x1800138eb  pop     rsi
0x1800138ec  pop     rbx
0x1800138ed  pop     rbp
0x1800138ee  retn
0x1800138f0  mov     rcx, [rbp+198h]; this
0x1800138f7  lea     r9, aFailedCallToGe_0; "Failed call to GetSystemDirectory/GetSy"...
0x1800138fe  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180013905  mov     dword ptr [rsp+290h+var_270], ebx; char *
0x180013909  mov     edx, 1922h; void *
0x18001390e  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180013913  jmp     short loc_1800138D2
0x180013915  mov     rcx, [rbp+198h]; this
0x18001391c  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180013923  mov     r9d, ebx; char *
0x180013926  mov     edx, 1933h; void *
0x18001392b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013930  mov     rcx, [rsp+290h+bufferHandle]; bufferHandle
0x180013935  test    rcx, rcx
0x180013938  jz      short loc_180013946
0x18001393a  call    cs:__imp_WindowsDeleteStringBuffer
0x180013941  nop     dword ptr [rax+rax+00h]
0x180013946  mov     eax, ebx
0x180013948  jmp     short loc_1800138D2
0x18001394a  cmp     ebx, 1
0x18001394d  jz      loc_180013801
0x180013953  movzx   r8d, bx
0x180013957  lea     rcx, [rsp+290h+Buffer]
0x18001395c  mov     edx, 104h
0x180013961  call    cs:__imp_GetSystemWow64Directory2W
0x180013968  nop     dword ptr [rax+rax+00h]
0x18001396d  jmp     loc_180013817
```
