# LoadICSLibrary(void)

- ea: `0x18005b450`
- end: `0x18005b672`
- name: `?LoadICSLibrary@@YAPEAUHINSTANCE__@@XZ`
- size: `546`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005b418`

## callees

- `0x18001a2b8`
- `0x18005b450`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18005b64c`
- `ntdll!RtlSetLastWin32Error` at `0x18005b64c`
- `ntdll!NtQueryValueKey` at `0x18005b578`
- `ntdll!NtQueryValueKey` at `0x18005b578`
- `ntdll!NtClose` at `0x18005b598`
- `ntdll!NtClose` at `0x18005b657`
- `ntdll!NtClose` at `0x18005b598`
- `ntdll!NtClose` at `0x18005b657`
- `ntdll!NtOpenKey` at `0x18005b52c`
- `ntdll!NtOpenKey` at `0x18005b52c`
- `ntdll!RtlInitUnicodeString` at `0x18005b4eb`
- `ntdll!RtlInitUnicodeString` at `0x18005b551`
- `ntdll!RtlInitUnicodeString` at `0x18005b4eb`
- `ntdll!RtlInitUnicodeString` at `0x18005b551`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005b5f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005b5f8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b63f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b667`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b63f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b667`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005b610`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005b610`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b4ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b4ba`

## string_xrefs

- `0x18005b4d6`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Windows`
- `0x18005b53c`: `IconServiceLib`

## pseudocode

```c
HINSTANCE LoadICSLibrary(void)
{
  UINT SystemDirectoryW; // eax
  UINT v1; // r14d
  int v2; // esi
  ULONG Length; // edi
  WCHAR *v4; // rbx
  NTSTATUS v5; // eax
  HMODULE Library; // rdi
  int v8; // eax
  WCHAR *v9; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE KeyValueInformation[64]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR LibFileName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(KeyValueInformation, 0, sizeof(KeyValueInformation));
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  if ( !SystemDirectoryW )
    return 0;
  if ( SystemDirectoryW > 0x105 )
    Buffer[0] = 0;
  v1 = 0;
  if ( SystemDirectoryW <= 0x105 )
    v1 = SystemDirectoryW;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 0;
  v2 = 0;
  Length = 64;
  v4 = (WCHAR *)KeyValueInformation;
  RtlInitUnicodeString(&DestinationString, L"IconServiceLib");
  while ( 1 )
  {
    v5 = NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v4, Length, &ResultLength);
    if ( v5 != -2147483643 )
      break;
    if ( v2 )
      GlobalFree(v4);
    v4 = (WCHAR *)GlobalAlloc(0x40u, ResultLength);
    if ( !v4 )
    {
      RtlSetLastWin32Error(0xEu);
      NtClose(KeyHandle);
      return 0;
    }
    Length = ResultLength;
    v2 = 1;
  }
  Library = 0;
  if ( v5 >= 0 )
  {
    if ( !v1 || (v8 = StringCchPrintfW(LibFileName, 0x105u, L"%ws\\%ws", Buffer, v4 + 6), v9 = LibFileName, v8 < 0) )
      v9 = v4 + 6;
    Library = LoadLibraryExW(v9, 0, 0);
  }
  if ( v2 )
    GlobalFree(v4);
  NtClose(KeyHandle);
  return Library;
}

```

## disassembly

```asm
0x18005b450  push    rbp
0x18005b452  push    rbx
0x18005b453  push    rsi
0x18005b454  push    rdi
0x18005b455  push    r14
0x18005b457  lea     rbp, [rsp-3F0h]
0x18005b45f  sub     rsp, 4F0h
0x18005b466  mov     rax, cs:__security_cookie
0x18005b46d  xor     rax, rsp
0x18005b470  mov     [rbp+410h+var_30], rax
0x18005b477  xorps   xmm1, xmm1
0x18005b47a  mov     [rsp+510h+KeyHandle], 0
0x18005b483  xor     edx, edx; Val
0x18005b485  mov     [rsp+510h+var_4E0], 0
0x18005b48d  xorps   xmm0, xmm0
0x18005b490  lea     rcx, [rbp+410h+KeyValueInformation]; void *
0x18005b494  movups  xmmword ptr [rsp+510h+DestinationString.Length], xmm0
0x18005b499  lea     r8d, [rdx+40h]; Size
0x18005b49d  movups  xmmword ptr [rsp+510h+ObjectAttributes.Length], xmm1
0x18005b4a2  movups  xmmword ptr [rsp+510h+ObjectAttributes.ObjectName], xmm1
0x18005b4a7  movups  xmmword ptr [rsp+510h+ObjectAttributes.SecurityDescriptor], xmm1
0x18005b4ac  call    memset_0
0x18005b4b1  mov     edx, 105h; uSize
0x18005b4b6  lea     rcx, [rbp+410h+Buffer]; lpBuffer
0x18005b4ba  call    cs:__imp_GetSystemDirectoryW
0x18005b4c0  test    eax, eax
0x18005b4c2  jz      loc_18005B65D
0x18005b4c8  cmp     eax, 105h
0x18005b4cd  ja      loc_18005B631
0x18005b4d3  xor     r14d, r14d
0x18005b4d6  lea     rdx, ?szWindowsKey@@3QBGB; "\\Registry\\Machine\\Software\\Microsof"...
0x18005b4dd  cmp     eax, 105h
0x18005b4e2  lea     rcx, [rsp+510h+DestinationString]; DestinationString
0x18005b4e7  cmovbe  r14d, eax
0x18005b4eb  call    cs:__imp_RtlInitUnicodeString
0x18005b4f1  lea     rax, [rsp+510h+DestinationString]
0x18005b4f6  mov     [rsp+510h+ObjectAttributes.Length], 30h ; '0'
0x18005b4fe  xorps   xmm0, xmm0
0x18005b501  mov     [rsp+510h+ObjectAttributes.ObjectName], rax
0x18005b506  lea     r8, [rsp+510h+ObjectAttributes]; ObjectAttributes
0x18005b50b  mov     [rsp+510h+ObjectAttributes.RootDirectory], 0
0x18005b514  mov     edx, 20019h; DesiredAccess
0x18005b519  mov     [rsp+510h+ObjectAttributes.Attributes], 40h ; '@'
0x18005b521  lea     rcx, [rsp+510h+KeyHandle]; KeyHandle
0x18005b526  movdqu  xmmword ptr [rsp+510h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005b52c  call    cs:__imp_NtOpenKey
0x18005b532  test    eax, eax
0x18005b534  js      loc_18005B65D
0x18005b53a  xor     esi, esi
0x18005b53c  lea     rdx, aIconservicelib; "IconServiceLib"
0x18005b543  lea     rcx, [rsp+510h+DestinationString]; DestinationString
0x18005b548  mov     edi, 40h ; '@'
0x18005b54d  lea     rbx, [rbp+410h+KeyValueInformation]
0x18005b551  call    cs:__imp_RtlInitUnicodeString
0x18005b557  mov     rcx, [rsp+510h+KeyHandle]; KeyHandle
0x18005b55c  lea     rax, [rsp+510h+var_4E0]
0x18005b561  mov     [rsp+510h+ResultLength], rax; ResultLength
0x18005b566  lea     rdx, [rsp+510h+DestinationString]; ValueName
0x18005b56b  mov     r9, rbx; KeyValueInformation
0x18005b56e  mov     [rsp+510h+Length], edi; Length
0x18005b572  mov     r8d, 2; KeyValueInformationClass
0x18005b578  call    cs:__imp_NtQueryValueKey
0x18005b57e  cmp     eax, 80000005h
0x18005b583  jz      short loc_18005B603
0x18005b585  xor     edi, edi
0x18005b587  test    eax, eax
0x18005b589  jns     short loc_18005B5BE
0x18005b58b  test    esi, esi
0x18005b58d  jnz     loc_18005B664
0x18005b593  mov     rcx, [rsp+510h+KeyHandle]; Handle
0x18005b598  call    cs:__imp_NtClose
0x18005b59e  mov     rax, rdi
0x18005b5a1  mov     rcx, [rbp+410h+var_30]
0x18005b5a8  xor     rcx, rsp; StackCookie
0x18005b5ab  call    __security_check_cookie
0x18005b5b0  add     rsp, 4F0h
0x18005b5b7  pop     r14
0x18005b5b9  pop     rdi
0x18005b5ba  pop     rsi
0x18005b5bb  pop     rbx
0x18005b5bc  pop     rbp
0x18005b5bd  retn
0x18005b5be  lea     rdi, [rbx+0Ch]
0x18005b5c2  test    r14d, r14d
0x18005b5c5  jz      short loc_18005B62C
0x18005b5c7  lea     r9, [rbp+410h+Buffer]
0x18005b5cb  mov     qword ptr [rsp+510h+Length], rdi
0x18005b5d0  lea     r8, aWsWs; "%ws\\%ws"
0x18005b5d7  mov     edx, 105h; unsigned __int64
0x18005b5dc  lea     rcx, [rbp+410h+LibFileName]; unsigned __int16 *
0x18005b5e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b5e8  lea     rcx, [rbp+410h+LibFileName]; lpLibFileName
0x18005b5ef  test    eax, eax
0x18005b5f1  js      short loc_18005B62C
0x18005b5f3  xor     r8d, r8d; dwFlags
0x18005b5f6  xor     edx, edx; hFile
0x18005b5f8  call    cs:__imp_LoadLibraryExW
0x18005b5fe  mov     rdi, rax
0x18005b601  jmp     short loc_18005B58B
0x18005b603  test    esi, esi
0x18005b605  jnz     short loc_18005B63C
0x18005b607  mov     edx, [rsp+510h+var_4E0]; dwBytes
0x18005b60b  mov     ecx, 40h ; '@'; uFlags
0x18005b610  call    cs:__imp_GlobalAlloc
0x18005b616  mov     rbx, rax
0x18005b619  test    rax, rax
0x18005b61c  jz      short loc_18005B647
0x18005b61e  mov     edi, [rsp+510h+var_4E0]
0x18005b622  mov     esi, 1
0x18005b627  jmp     loc_18005B557
0x18005b62c  mov     rcx, rdi
0x18005b62f  jmp     short loc_18005B5F3
0x18005b631  xor     ecx, ecx
0x18005b633  mov     [rbp+410h+Buffer], cx
0x18005b637  jmp     loc_18005B4D3
0x18005b63c  mov     rcx, rbx; hMem
0x18005b63f  call    cs:__imp_GlobalFree
0x18005b645  jmp     short loc_18005B607
0x18005b647  mov     ecx, 0Eh; LastError
0x18005b64c  call    cs:__imp_RtlSetLastWin32Error
0x18005b652  mov     rcx, [rsp+510h+KeyHandle]; Handle
0x18005b657  call    cs:__imp_NtClose
0x18005b65d  xor     eax, eax
0x18005b65f  jmp     loc_18005B5A1
0x18005b664  mov     rcx, rbx; hMem
0x18005b667  call    cs:__imp_GlobalFree
0x18005b66d  jmp     loc_18005B593
```
