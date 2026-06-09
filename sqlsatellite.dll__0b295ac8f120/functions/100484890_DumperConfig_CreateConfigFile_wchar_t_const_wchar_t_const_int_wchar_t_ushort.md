# DumperConfig::CreateConfigFile(wchar_t const *,wchar_t const *,int,wchar_t *,ushort)

- ea: `0x100484890`
- end: `0x100484ae7`
- name: `?CreateConfigFile@DumperConfig@@SA_NPEB_W0HPEA_WG@Z`
- size: `599`
- prototype: `bool __usercall@<al>(LPCWSTR lpFileName@<rcx>, const wchar_t *@<rdx>, int@<r8d>, wchar_t *@<r9>, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x100483630`

## callees

- `0x10040d8a0`
- `0x100467bf0`
- `0x100484890`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x100484a92`
- `KERNEL32!DeleteFileW` at `0x100484a92`
- `KERNEL32!WriteFile` at `0x100484a22`
- `KERNEL32!WriteFile` at `0x100484a22`
- `KERNEL32!CloseHandle` at `0x100484a85`
- `KERNEL32!CloseHandle` at `0x100484ab5`
- `KERNEL32!CloseHandle` at `0x100484a85`
- `KERNEL32!CloseHandle` at `0x100484ab5`
- `KERNEL32!GetLastError` at `0x1004848fa`
- `KERNEL32!GetLastError` at `0x10048495b`
- `KERNEL32!GetLastError` at `0x100484a2c`
- `KERNEL32!GetLastError` at `0x100484a56`
- `KERNEL32!GetLastError` at `0x1004848fa`
- `KERNEL32!GetLastError` at `0x10048495b`
- `KERNEL32!GetLastError` at `0x100484a2c`
- `KERNEL32!GetLastError` at `0x100484a56`
- `KERNEL32!CreateFileW` at `0x10048494c`
- `KERNEL32!CreateFileW` at `0x10048494c`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1004848e3`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1004848e3`

## string_xrefs

- `0x100484900`: `CreateConfigFile: Failed to generate security descriptor, error: %d`
- `0x100484964`: `CreateFile failed: %ls, error: %d`
- `0x100484aa0`: `%ls created successfully.`
- `0x10048499c`: `<?xml version="1.0"?><SqlDumper><%ls>%d</%ls></SqlDumper>`
- `0x1004849eb`: `StringCchPrintfExW failed to construct default dumper config file content, error: 0x%x`
- `0x100484a35`: `Unable to write to file: %ls, error: %d`
- `0x100484a60`: `WriteFile failed: %ls, error: %d, bytes written: %d (expected: %d)`

## pseudocode

```c
char __fastcall DumperConfig::CreateConfigFile(
        LPCWSTR lpFileName,
        const wchar_t *a2,
        int a3,
        wchar_t *a4,
        unsigned __int16 a5)
{
  BOOL v9; // eax
  bool v10; // bl
  DWORD LastError; // eax
  HANDLE v13; // r15
  int v14; // eax
  unsigned __int64 v15; // r14
  DWORD v16; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-2C8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-2C8h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-2C0h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-298h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-290h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-288h] BYREF
  wchar_t *v23; // [rsp+78h] [rbp-270h] BYREF
  wchar_t Buffer[264]; // [rsp+80h] [rbp-268h] BYREF

  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  v9 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:AI(A;;FA;;;BU)(A;ID;FA;;;SY)(A;ID;FA;;;BA)",
         1u,
         &SecurityAttributes.lpSecurityDescriptor,
         0);
  v10 = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    StringCchPrintfW(a4, a5, L"CreateConfigFile: Failed to generate security descriptor, error: %d", LastError);
    return v10;
  }
  v13 = CreateFileW(lpFileName, 0x40000000u, 1u, &SecurityAttributes, 1u, 0x80u, 0);
  if ( v13 == (HANDLE)-1LL )
  {
    dwCreationDisposition[0] = GetLastError();
    StringCchPrintfW(a4, a5, L"CreateFile failed: %ls, error: %d", lpFileName, *(_QWORD *)dwCreationDisposition);
    return v10;
  }
  memset_0(Buffer, 0, 0x208u);
  NumberOfBytesWritten = 0;
  v21 = 0;
  v14 = StringCchPrintfExW(
          Buffer,
          0x104u,
          &v23,
          &v21,
          0,
          L"<?xml version=\"1.0\"?><SqlDumper><%ls>%d</%ls></SqlDumper>",
          a2,
          a3,
          a2);
  if ( v14 >= 0 )
  {
    v15 = 2 * (260 - v21);
    if ( WriteFile(v13, Buffer, 2 * (260 - v21), &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten == v15 )
      {
        StringCchPrintfW(a4, a5, L"%ls created successfully.", lpFileName);
        CloseHandle(v13);
        return 1;
      }
      v16 = GetLastError();
      dwFlagsAndAttributes[0] = NumberOfBytesWritten;
      dwCreationDispositiona[0] = v16;
      StringCchPrintfW(
        a4,
        a5,
        L"WriteFile failed: %ls, error: %d, bytes written: %d (expected: %d)",
        lpFileName,
        *(_QWORD *)dwCreationDispositiona,
        *(_QWORD *)dwFlagsAndAttributes,
        v15);
    }
    else
    {
      dwCreationDispositiona[0] = GetLastError();
      StringCchPrintfW(
        a4,
        a5,
        L"Unable to write to file: %ls, error: %d",
        lpFileName,
        *(_QWORD *)dwCreationDispositiona);
    }
  }
  else
  {
    _mm_lfence();
    StringCchPrintfW(
      a4,
      a5,
      L"StringCchPrintfExW failed to construct default dumper config file content, error: 0x%x",
      (unsigned int)v14);
  }
  CloseHandle(v13);
  if ( !v10 )
    DeleteFileW(lpFileName);
  return v10;
}

```

## disassembly

```asm
0x100484890  push    rbx
0x100484892  push    rbp
0x100484893  push    rsi
0x100484894  push    rdi
0x100484895  push    r12
0x100484897  push    r13
0x100484899  push    r14
0x10048489b  sub     rsp, 2B0h
0x1004848a2  mov     rax, cs:__security_cookie
0x1004848a9  xor     rax, rsp
0x1004848ac  mov     [rsp+2E8h+var_58], rax
0x1004848b4  xor     r13d, r13d
0x1004848b7  mov     [rsp+2E8h+SecurityAttributes.nLength], 18h
0x1004848bf  mov     rsi, r9
0x1004848c2  mov     [rsp+2E8h+SecurityAttributes.bInheritHandle], r13d
0x1004848c7  mov     r12d, r8d
0x1004848ca  mov     r14, rdx
0x1004848cd  mov     rdi, rcx
0x1004848d0  lea     r8, [rsp+2E8h+SecurityAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x1004848d5  lea     edx, [r13+1]; StringSDRevision
0x1004848d9  xor     r9d, r9d; SecurityDescriptorSize
0x1004848dc  lea     rcx, StringSecurityDescriptor; "D:AI(A;;FA;;;BU)(A;ID;FA;;;SY)(A;ID;FA;"...
0x1004848e3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1004848e9  movzx   ebp, [rsp+2E8h+arg_20]
0x1004848f1  test    eax, eax
0x1004848f3  setnz   bl
0x1004848f6  test    eax, eax
0x1004848f8  jnz     short loc_10048491C
0x1004848fa  call    cs:__imp_GetLastError
0x100484900  lea     r8, aCreateconfigfi; "CreateConfigFile: Failed to generate se"...
0x100484907  mov     edx, ebp; unsigned __int64
0x100484909  mov     r9d, eax
0x10048490c  mov     rcx, rsi; Buffer
0x10048490f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484914  movzx   eax, bl
0x100484917  jmp     loc_100484AC5
0x10048491c  mov     [rsp+2E8h+hTemplateFile], r13; hTemplateFile
0x100484921  lea     r9, [rsp+2E8h+SecurityAttributes]; lpSecurityAttributes
0x100484926  mov     [rsp+2E8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x10048492e  mov     edx, 40000000h; dwDesiredAccess
0x100484933  mov     r8d, 1; dwShareMode
0x100484939  mov     [rsp+2E8h+dwCreationDisposition], 1; dwCreationDisposition
0x100484941  mov     rcx, rdi; lpFileName
0x100484944  mov     [rsp+2E8h+var_40], r15
0x10048494c  call    cs:__imp_CreateFileW
0x100484952  mov     r15, rax
0x100484955  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100484959  jnz     short loc_100484982
0x10048495b  call    cs:__imp_GetLastError
0x100484961  mov     r9, rdi
0x100484964  lea     r8, aCreatefileFail; "CreateFile failed: %ls, error: %d"
0x10048496b  mov     rdx, rbp; unsigned __int64
0x10048496e  mov     [rsp+2E8h+dwCreationDisposition], eax
0x100484972  mov     rcx, rsi; Buffer
0x100484975  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10048497a  movzx   eax, bl
0x10048497d  jmp     loc_100484ABD
0x100484982  xor     edx, edx; Val
0x100484984  lea     rcx, [rsp+2E8h+Buffer]; void *
0x10048498c  mov     r8d, 208h; Size
0x100484992  call    memset_0
0x100484997  mov     [rsp+2E8h+var_2A8], r14
0x10048499c  lea     rax, aXmlVersion10Sq; "<?xml version=\"1.0\"?><SqlDumper><%ls>"...
0x1004849a3  mov     [rsp+2E8h+var_2B0], r12d
0x1004849a8  lea     r9, [rsp+2E8h+var_290]; unsigned __int64 *
0x1004849ad  mov     [rsp+2E8h+hTemplateFile], r14
0x1004849b2  lea     r8, [rsp+2E8h+var_270]; wchar_t **
0x1004849b7  mov     qword ptr [rsp+2E8h+dwFlagsAndAttributes], rax; wchar_t *
0x1004849bc  lea     rcx, [rsp+2E8h+Buffer]; wchar_t *
0x1004849c4  mov     r14d, 104h
0x1004849ca  mov     [rsp+2E8h+NumberOfBytesWritten], r13d
0x1004849cf  mov     edx, r14d; unsigned __int64
0x1004849d2  mov     [rsp+2E8h+var_290], r13
0x1004849d7  mov     qword ptr [rsp+2E8h+dwCreationDisposition], r13; unsigned int
0x1004849dc  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x1004849e1  test    eax, eax
0x1004849e3  jns     short loc_100484A02
0x1004849e5  lfence
0x1004849e8  mov     r9d, eax
0x1004849eb  lea     r8, aStringcchprint; "StringCchPrintfExW failed to construct "...
0x1004849f2  mov     rdx, rbp; unsigned __int64
0x1004849f5  mov     rcx, rsi; Buffer
0x1004849f8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004849fd  jmp     loc_100484A82
0x100484a02  sub     r14, [rsp+2E8h+var_290]
0x100484a07  lea     r9, [rsp+2E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100484a0c  add     r14, r14
0x100484a0f  mov     qword ptr [rsp+2E8h+dwCreationDisposition], r13; lpOverlapped
0x100484a14  mov     r8d, r14d; nNumberOfBytesToWrite
0x100484a17  lea     rdx, [rsp+2E8h+Buffer]; lpBuffer
0x100484a1f  mov     rcx, r15; hFile
0x100484a22  call    cs:__imp_WriteFile
0x100484a28  test    eax, eax
0x100484a2a  jnz     short loc_100484A4D
0x100484a2c  call    cs:__imp_GetLastError
0x100484a32  mov     r9, rdi
0x100484a35  lea     r8, aUnableToWriteT; "Unable to write to file: %ls, error: %d"
0x100484a3c  mov     rdx, rbp; unsigned __int64
0x100484a3f  mov     [rsp+2E8h+dwCreationDisposition], eax
0x100484a43  mov     rcx, rsi; Buffer
0x100484a46  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484a4b  jmp     short loc_100484A82
0x100484a4d  mov     eax, [rsp+2E8h+NumberOfBytesWritten]
0x100484a51  cmp     rax, r14
0x100484a54  jz      short loc_100484A9D
0x100484a56  call    cs:__imp_GetLastError
0x100484a5c  mov     ecx, [rsp+2E8h+NumberOfBytesWritten]
0x100484a60  lea     r8, aWritefileFaile; "WriteFile failed: %ls, error: %d, bytes"...
0x100484a67  mov     [rsp+2E8h+hTemplateFile], r14
0x100484a6c  mov     r9, rdi
0x100484a6f  mov     [rsp+2E8h+dwFlagsAndAttributes], ecx
0x100484a73  mov     rdx, rbp; unsigned __int64
0x100484a76  mov     rcx, rsi; Buffer
0x100484a79  mov     [rsp+2E8h+dwCreationDisposition], eax
0x100484a7d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484a82  mov     rcx, r15; hObject
0x100484a85  call    cs:__imp_CloseHandle
0x100484a8b  test    bl, bl
0x100484a8d  jnz     short loc_100484A98
0x100484a8f  mov     rcx, rdi; lpFileName
0x100484a92  call    cs:__imp_DeleteFileW
0x100484a98  movzx   eax, bl
0x100484a9b  jmp     short loc_100484ABD
0x100484a9d  mov     r9, rdi
0x100484aa0  lea     r8, aLsCreatedSucce; "%ls created successfully."
0x100484aa7  mov     rdx, rbp; unsigned __int64
0x100484aaa  mov     rcx, rsi; Buffer
0x100484aad  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484ab2  mov     rcx, r15; hObject
0x100484ab5  call    cs:__imp_CloseHandle
0x100484abb  mov     al, 1
0x100484abd  mov     r15, [rsp+2E8h+var_40]
0x100484ac5  mov     rcx, [rsp+2E8h+var_58]
0x100484acd  xor     rcx, rsp; StackCookie
0x100484ad0  call    __security_check_cookie
0x100484ad5  add     rsp, 2B0h
0x100484adc  pop     r14
0x100484ade  pop     r13
0x100484ae0  pop     r12
0x100484ae2  pop     rdi
0x100484ae3  pop     rsi
0x100484ae4  pop     rbp
0x100484ae5  pop     rbx
0x100484ae6  retn
```
