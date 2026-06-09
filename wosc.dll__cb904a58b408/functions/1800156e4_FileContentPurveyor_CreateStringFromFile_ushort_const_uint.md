# FileContentPurveyor::CreateStringFromFile(ushort const *,uint)

- ea: `0x1800156e4`
- end: `0x180015a44`
- name: `?CreateStringFromFile@FileContentPurveyor@@SAPEAUHSTRING__@@PEBGI@Z`
- size: `864`
- prototype: `HSTRING __fastcall(LPCWSTR lpSrc, int)`
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017714`
- `0x1800197a8`
- `0x18003e300`
- `0x18003e470`
- `0x18003e4c0`
- `0x18003e6c0`

## callees

- `0x18000a1f0`
- `0x18000a250`
- `0x1800101e0`
- `0x1800101fc`
- `0x180011acc`
- `0x1800146dc`
- `0x180014d60`
- `0x180014d84`
- `0x1800156e4`
- `0x180015a4c`
- `0x180019ed8`
- `0x18001a664`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001589d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001589d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18001590e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18001590e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015939`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015939`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180015843`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180015843`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001580f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001580f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800157b6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015987`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800157b6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015987`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001576d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001576d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001570a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015729`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001570a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015729`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HSTRING __fastcall FileContentPurveyor::CreateStringFromFile(LPCWSTR lpSrc, int a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdx
  const char *v5; // r9
  unsigned int v6; // edi
  char v7; // r15
  HANDLE FileW; // rax
  const char *v9; // r9
  void *v10; // rsi
  const char *v11; // r9
  UINT v12; // r14d
  const char *v13; // r9
  const char *v14; // r9
  DWORD v15; // ebx
  HRESULT v16; // eax
  HSTRING StringFromMultiByte; // rbx
  const CHAR *v18; // rdi
  HRESULT v19; // eax
  void *v20; // rdx
  LPVOID v21; // rax
  const char *v22; // r9
  const char *v23; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-50h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-50h]
  HSTRING_BUFFER bufferHandle; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR lpDst; // [rsp+50h] [rbp-20h] BYREF
  WCHAR *charBuffer; // [rsp+58h] [rbp-18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp-10h] BYREF
  HANDLE v32; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int Buffer; // [rsp+B8h] [rbp+48h] BYREF
  DWORD NumberOfBytesRead; // [rsp+C0h] [rbp+50h] BYREF
  DWORD v36; // [rsp+C8h] [rbp+58h] BYREF

  Buffer = a2;
  v3 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpDst,
    v4,
    v3);
  if ( !ExpandEnvironmentStringsW(lpSrc, lpDst, v3) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      v5);
  v6 = 3;
  v7 = 1;
  FileW = CreateFileW(lpDst, 0x120089u, 1u, 0, 3u, 0, 0);
  v10 = FileW;
  v32 = FileW;
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      v9);
  Buffer = 0;
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileW, &Buffer, 4u, &NumberOfBytesRead, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      v11);
  if ( (Buffer & 0xFFFFFF) != 0xBFBBEF )
  {
    if ( (_WORD)Buffer == 0xFEFF )
    {
      v6 = 2;
      v12 = -1;
      goto LABEL_11;
    }
    v6 = 0;
  }
  v12 = 65001;
LABEL_11:
  if ( NumberOfBytesRead != v6 && !SetFilePointerEx(v10, (LARGE_INTEGER)v6, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      v13);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v10, &FileSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      v14);
  if ( FileSize.QuadPart >= 0xFFFFFFFFLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      (const char *)0x80070216LL,
      dwCreationDisposition);
  v15 = FileSize.LowPart - v6;
  string = 0;
  if ( FileSize.LowPart == v6 )
  {
    v16 = WindowsCreateString(0, 0, &string);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
        (const char *)(unsigned int)v16,
        dwCreationDisposition);
    StringFromMultiByte = string;
  }
  else
  {
    v18 = 0;
    bufferHandle = 0;
    if ( v12 == -1 )
    {
      if ( (v15 & 1) != 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB2,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
          (const char *)0x8000FFFFLL,
          dwCreationDisposition);
      charBuffer = 0;
      bufferHandle = 0;
      v19 = WindowsPreallocateStringBuffer(v15 >> 1, &charBuffer, &bufferHandle);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
          (const char *)(unsigned int)v19,
          dwCreationDisposition);
      v20 = charBuffer;
    }
    else
    {
      v21 = CoTaskMemAlloc(v15);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &string,
        v21);
      v18 = (const CHAR *)string;
      if ( !string )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
          v22);
      v7 = 0;
      v20 = string;
    }
    v36 = 0;
    if ( !ReadFile(v10, v20, v15, &v36, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
        v23);
    if ( v15 != v36 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
        (const char *)0x8000FFFFLL,
        dwCreationDispositiona);
    if ( v7 )
    {
      wil::make_hstring_from_buffer((HSTRING *)&charBuffer);
      StringFromMultiByte = (HSTRING)charBuffer;
      charBuffer = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&charBuffer);
    }
    else
    {
      StringFromMultiByte = FileContentPurveyor::CreateStringFromMultiByte(v12, v18, v15);
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&string);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpDst);
  return StringFromMultiByte;
}

```

## disassembly

```asm
0x1800156e4  mov     [rsp-38h+arg_0], rbx
0x1800156e9  mov     [rsp-38h+Buffer], edx
0x1800156ed  push    rbp
0x1800156ee  push    rsi
0x1800156ef  push    rdi
0x1800156f0  push    r12
0x1800156f2  push    r13
0x1800156f4  push    r14
0x1800156f6  push    r15
0x1800156f8  mov     rbp, rsp
0x1800156fb  sub     rsp, 70h
0x1800156ff  mov     rdi, rcx
0x180015702  xor     r13d, r13d
0x180015705  xor     r8d, r8d; nSize
0x180015708  xor     edx, edx; lpDst
0x18001570a  call    cs:__imp_ExpandEnvironmentStringsW
0x180015710  mov     ebx, eax
0x180015712  mov     r8d, eax
0x180015715  lea     rcx, [rbp+lpDst]
0x180015719  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001571e  nop
0x18001571f  mov     r8d, ebx; nSize
0x180015722  mov     rdx, [rbp+lpDst]; lpDst
0x180015726  mov     rcx, rdi; lpSrc
0x180015729  call    cs:__imp_ExpandEnvironmentStringsW
0x18001572f  test    eax, eax
0x180015731  jnz     short loc_180015747
0x180015733  mov     rcx, [rbp+38h]; this
0x180015737  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x18001573e  lea     edx, [rax+71h]; void *
0x180015741  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015747  mov     [rsp+70h+hTemplateFile], r13; hTemplateFile
0x18001574c  mov     [rsp+70h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180015751  mov     edi, 3
0x180015756  mov     [rsp+70h+dwCreationDisposition], edi; dwCreationDisposition
0x18001575a  xor     r9d, r9d; lpSecurityAttributes
0x18001575d  lea     r15d, [rdi-2]
0x180015761  mov     r8d, r15d; dwShareMode
0x180015764  mov     edx, 120089h; dwDesiredAccess
0x180015769  mov     rcx, [rbp+lpDst]; lpFileName
0x18001576d  call    cs:__imp_CreateFileW
0x180015773  mov     rsi, rax
0x180015776  mov     [rbp+var_8], rax
0x18001577a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001577e  jnz     short loc_180015794
0x180015780  mov     rcx, [rbp+38h]; this
0x180015784  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x18001578b  lea     edx, [rdi+78h]; void *
0x18001578e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015794  mov     [rbp+Buffer], r13d
0x180015798  mov     [rbp+NumberOfBytesRead], r13d
0x18001579c  mov     rbx, [rbp+38h]
0x1800157a0  mov     qword ptr [rsp+70h+dwCreationDisposition], r13; int
0x1800157a5  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800157a9  mov     r8d, 4; nNumberOfBytesToRead
0x1800157af  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800157b3  mov     rcx, rsi; hFile
0x1800157b6  call    cs:__imp_ReadFile
0x1800157bc  test    eax, eax
0x1800157be  jnz     short loc_1800157D5
0x1800157c0  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x1800157c7  mov     edx, 87h; void *
0x1800157cc  mov     rcx, rbx; this
0x1800157cf  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800157d5  mov     eax, [rbp+Buffer]
0x1800157d8  and     eax, 0FFFFFFh
0x1800157dd  mov     r12d, 0FFFFFFFFh
0x1800157e3  cmp     eax, 0BFBBEFh
0x1800157e8  jz      short loc_1800157F5
0x1800157ea  cmp     word ptr [rbp+Buffer], 0FEFFh
0x1800157f0  jz      short loc_18001582E
0x1800157f2  mov     edi, r13d
0x1800157f5  mov     r14d, 0FDE9h
0x1800157fb  cmp     [rbp+NumberOfBytesRead], edi
0x1800157fe  jz      short loc_180015838
0x180015800  mov     edx, edi; liDistanceToMove
0x180015802  mov     rbx, [rbp+38h]
0x180015806  xor     r9d, r9d; dwMoveMethod
0x180015809  xor     r8d, r8d; lpNewFilePointer
0x18001580c  mov     rcx, rsi; hFile
0x18001580f  call    cs:__imp_SetFilePointerEx
0x180015815  test    eax, eax
0x180015817  jnz     short loc_180015838
0x180015819  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015820  mov     edx, 92h; void *
0x180015825  mov     rcx, rbx; this
0x180015828  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001582e  mov     edi, 2
0x180015833  mov     r14d, r12d
0x180015836  jmp     short loc_1800157FB
0x180015838  mov     qword ptr [rbp+FileSize], r13
0x18001583c  lea     rdx, [rbp+FileSize]; lpFileSize
0x180015840  mov     rcx, rsi; hFile
0x180015843  call    cs:__imp_GetFileSizeEx
0x180015849  mov     rcx, [rbp+38h]; this
0x18001584d  test    eax, eax
0x18001584f  jnz     short loc_180015863
0x180015851  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015858  mov     edx, 96h; void *
0x18001585d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015863  mov     rbx, qword ptr [rbp+FileSize]
0x180015867  cmp     rbx, r12
0x18001586a  setl    al
0x18001586d  mov     rcx, [rbp+38h]; this
0x180015871  test    al, al
0x180015873  jnz     short loc_18001588D
0x180015875  mov     r9d, 80070216h; char *
0x18001587b  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015882  mov     edx, 97h; void *
0x180015887  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001588d  sub     ebx, edi
0x18001588f  mov     [rbp+string], r13
0x180015893  jnz     short loc_1800158C9
0x180015895  lea     r8, [rbp+string]; string
0x180015899  xor     edx, edx; length
0x18001589b  xor     ecx, ecx; sourceString
0x18001589d  call    cs:__imp_WindowsCreateString
0x1800158a3  mov     rcx, [rbp+38h]; this
0x1800158a7  test    eax, eax
0x1800158a9  jns     short loc_1800158C0
0x1800158ab  mov     r9d, eax; char *
0x1800158ae  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x1800158b5  mov     edx, 9Fh; void *
0x1800158ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800158c0  mov     rbx, [rbp+string]
0x1800158c4  jmp     loc_180015A16
0x1800158c9  mov     rdi, r13
0x1800158cc  mov     [rbp+bufferHandle], r13
0x1800158d0  cmp     r14d, r12d
0x1800158d3  jnz     short loc_180015937
0x1800158d5  mov     rcx, [rbp+38h]; this
0x1800158d9  mov     al, bl
0x1800158db  not     al
0x1800158dd  test    r15b, al
0x1800158e0  jnz     short loc_1800158FA
0x1800158e2  mov     r9d, 8000FFFFh; char *
0x1800158e8  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x1800158ef  mov     edx, 0B2h; void *
0x1800158f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800158fa  mov     [rbp+charBuffer], r13
0x1800158fe  mov     [rbp+bufferHandle], r13
0x180015902  mov     ecx, ebx
0x180015904  shr     ecx, 1; length
0x180015906  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18001590a  lea     rdx, [rbp+charBuffer]; charBuffer
0x18001590e  call    cs:__imp_WindowsPreallocateStringBuffer
0x180015914  mov     rcx, [rbp+38h]; this
0x180015918  test    eax, eax
0x18001591a  jns     short loc_180015931
0x18001591c  mov     r9d, eax; char *
0x18001591f  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015926  mov     edx, 0B7h; void *
0x18001592b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015931  mov     rdx, [rbp+charBuffer]
0x180015935  jmp     short loc_180015970
0x180015937  mov     ecx, ebx; cb
0x180015939  call    cs:__imp_CoTaskMemAlloc
0x18001593f  mov     rdx, rax
0x180015942  lea     rcx, [rbp+string]
0x180015946  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001594b  mov     rcx, [rbp+38h]; this
0x18001594f  mov     rdi, [rbp+string]
0x180015953  test    rdi, rdi
0x180015956  jnz     short loc_18001596A
0x180015958  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x18001595f  mov     edx, 0BEh; void *
0x180015964  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001596a  mov     r15b, r13b
0x18001596d  mov     rdx, rdi; lpBuffer
0x180015970  mov     [rbp+arg_18], r13d
0x180015974  mov     r12, [rbp+38h]
0x180015978  mov     qword ptr [rsp+70h+dwCreationDisposition], r13; int
0x18001597d  lea     r9, [rbp+arg_18]; lpNumberOfBytesRead
0x180015981  mov     r8d, ebx; nNumberOfBytesToRead
0x180015984  mov     rcx, rsi; hFile
0x180015987  call    cs:__imp_ReadFile
0x18001598d  test    eax, eax
0x18001598f  jnz     short loc_1800159A6
0x180015991  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015998  mov     edx, 0C9h; void *
0x18001599d  mov     rcx, r12; this
0x1800159a0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800159a6  cmp     ebx, [rbp+arg_18]
0x1800159a9  setz    al
0x1800159ac  mov     rcx, [rbp+38h]; this
0x1800159b0  test    al, al
0x1800159b2  jnz     short loc_1800159CC
0x1800159b4  mov     r9d, 8000FFFFh; char *
0x1800159ba  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x1800159c1  mov     edx, 0CDh; void *
0x1800159c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800159cc  test    r15b, r15b
0x1800159cf  jz      short loc_1800159F1
0x1800159d1  lea     rdx, [rbp+bufferHandle]
0x1800159d5  lea     rcx, [rbp+charBuffer]; string
0x1800159d9  call    ?make_hstring_from_buffer@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::make_hstring_from_buffer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&)
0x1800159de  mov     rbx, [rbp+charBuffer]
0x1800159e2  mov     [rbp+charBuffer], r13
0x1800159e6  lea     rcx, [rbp+charBuffer]
0x1800159ea  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800159ef  jmp     short loc_180015A02
0x1800159f1  mov     r8d, ebx; cbMultiByte
0x1800159f4  mov     rdx, rdi; lpMultiByteStr
0x1800159f7  mov     ecx, r14d; CodePage
0x1800159fa  call    ?CreateStringFromMultiByte@FileContentPurveyor@@SAPEAUHSTRING__@@IPEBDH@Z; FileContentPurveyor::CreateStringFromMultiByte(uint,char const *,int)
0x1800159ff  mov     rbx, rax
0x180015a02  lea     rcx, [rbp+bufferHandle]
0x180015a06  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x180015a0b  nop
0x180015a0c  lea     rcx, [rbp+string]
0x180015a10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015a15  nop
0x180015a16  lea     rcx, [rbp+var_8]
0x180015a1a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180015a1f  nop
0x180015a20  lea     rcx, [rbp+lpDst]
0x180015a24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015a29  mov     rax, rbx
0x180015a2c  mov     rbx, [rsp+70h+arg_0]
0x180015a34  add     rsp, 70h
0x180015a38  pop     r15
0x180015a3a  pop     r14
0x180015a3c  pop     r13
0x180015a3e  pop     r12
0x180015a40  pop     rdi
0x180015a41  pop     rsi
0x180015a42  pop     rbp
0x180015a43  retn
```
