# DumperConfig::CreateConfigFile(wchar_t const *,wchar_t const *,int,wchar_t *,ushort)

- ea: `0x100444610`
- end: `0x100444867`
- name: `?CreateConfigFile@DumperConfig@@SA_NPEB_W0HPEA_WG@Z`
- size: `599`
- prototype: `bool __usercall@<al>(LPCWSTR lpFileName@<rcx>, const wchar_t *@<rdx>, int@<r8d>, wchar_t *@<r9>, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x100443390`

## callees

- `0x100401580`
- `0x100404060`
- `0x100404a30`
- `0x100444610`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1004446cc`
- `KERNEL32!CreateFileW` at `0x1004446cc`
- `KERNEL32!WriteFile` at `0x1004447a2`
- `KERNEL32!WriteFile` at `0x1004447a2`
- `KERNEL32!CloseHandle` at `0x100444805`
- `KERNEL32!CloseHandle` at `0x100444835`
- `KERNEL32!CloseHandle` at `0x100444805`
- `KERNEL32!CloseHandle` at `0x100444835`
- `KERNEL32!GetLastError` at `0x10044467a`
- `KERNEL32!GetLastError` at `0x1004446db`
- `KERNEL32!GetLastError` at `0x1004447ac`
- `KERNEL32!GetLastError` at `0x1004447d6`
- `KERNEL32!GetLastError` at `0x10044467a`
- `KERNEL32!GetLastError` at `0x1004446db`
- `KERNEL32!GetLastError` at `0x1004447ac`
- `KERNEL32!GetLastError` at `0x1004447d6`
- `KERNEL32!DeleteFileW` at `0x100444812`
- `KERNEL32!DeleteFileW` at `0x100444812`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x100444663`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x100444663`

## string_xrefs

- `0x1004446e4`: `CreateFile failed: %ls, error: %d`
- `0x100444680`: `CreateConfigFile: Failed to generate security descriptor, error: %d`
- `0x1004447e0`: `WriteFile failed: %ls, error: %d, bytes written: %d (expected: %d)`
- `0x1004447b5`: `Unable to write to file: %ls, error: %d`
- `0x10044476b`: `StringCchPrintfExW failed to construct default dumper config file content, error: 0x%x`
- `0x10044471c`: `<?xml version="1.0"?><SqlDumper><%ls>%d</%ls></SqlDumper>`
- `0x100444820`: `%ls created successfully.`

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
0x100444610  push    rbx
0x100444612  push    rbp
0x100444613  push    rsi
0x100444614  push    rdi
0x100444615  push    r12
0x100444617  push    r13
0x100444619  push    r14
0x10044461b  sub     rsp, 2B0h
0x100444622  mov     rax, cs:__security_cookie
0x100444629  xor     rax, rsp
0x10044462c  mov     [rsp+2E8h+var_58], rax
0x100444634  xor     r13d, r13d
0x100444637  mov     [rsp+2E8h+SecurityAttributes.nLength], 18h
0x10044463f  mov     rsi, r9
0x100444642  mov     [rsp+2E8h+SecurityAttributes.bInheritHandle], r13d
0x100444647  mov     r12d, r8d
0x10044464a  mov     r14, rdx
0x10044464d  mov     rdi, rcx
0x100444650  lea     r8, [rsp+2E8h+SecurityAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x100444655  lea     edx, [r13+1]; StringSDRevision
0x100444659  xor     r9d, r9d; SecurityDescriptorSize
0x10044465c  lea     rcx, StringSecurityDescriptor; "D:AI(A;;FA;;;BU)(A;ID;FA;;;SY)(A;ID;FA;"...
0x100444663  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x100444669  movzx   ebp, [rsp+2E8h+arg_20]
0x100444671  test    eax, eax
0x100444673  setnz   bl
0x100444676  test    eax, eax
0x100444678  jnz     short loc_10044469C
0x10044467a  call    cs:__imp_GetLastError
0x100444680  lea     r8, aCreateconfigfi; "CreateConfigFile: Failed to generate se"...
0x100444687  mov     edx, ebp; unsigned __int64
0x100444689  mov     r9d, eax
0x10044468c  mov     rcx, rsi; Buffer
0x10044468f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444694  movzx   eax, bl
0x100444697  jmp     loc_100444845
0x10044469c  mov     [rsp+2E8h+hTemplateFile], r13; hTemplateFile
0x1004446a1  lea     r9, [rsp+2E8h+SecurityAttributes]; lpSecurityAttributes
0x1004446a6  mov     [rsp+2E8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1004446ae  mov     edx, 40000000h; dwDesiredAccess
0x1004446b3  mov     r8d, 1; dwShareMode
0x1004446b9  mov     [rsp+2E8h+dwCreationDisposition], 1; dwCreationDisposition
0x1004446c1  mov     rcx, rdi; lpFileName
0x1004446c4  mov     [rsp+2E8h+var_40], r15
0x1004446cc  call    cs:__imp_CreateFileW
0x1004446d2  mov     r15, rax
0x1004446d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1004446d9  jnz     short loc_100444702
0x1004446db  call    cs:__imp_GetLastError
0x1004446e1  mov     r9, rdi
0x1004446e4  lea     r8, aCreatefileFail; "CreateFile failed: %ls, error: %d"
0x1004446eb  mov     rdx, rbp; unsigned __int64
0x1004446ee  mov     [rsp+2E8h+dwCreationDisposition], eax
0x1004446f2  mov     rcx, rsi; Buffer
0x1004446f5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004446fa  movzx   eax, bl
0x1004446fd  jmp     loc_10044483D
0x100444702  xor     edx, edx; Val
0x100444704  lea     rcx, [rsp+2E8h+Buffer]; void *
0x10044470c  mov     r8d, 208h; Size
0x100444712  call    memset_0
0x100444717  mov     [rsp+2E8h+var_2A8], r14
0x10044471c  lea     rax, aXmlVersion10Sq; "<?xml version=\"1.0\"?><SqlDumper><%ls>"...
0x100444723  mov     [rsp+2E8h+var_2B0], r12d
0x100444728  lea     r9, [rsp+2E8h+var_290]; unsigned __int64 *
0x10044472d  mov     [rsp+2E8h+hTemplateFile], r14
0x100444732  lea     r8, [rsp+2E8h+var_270]; wchar_t **
0x100444737  mov     qword ptr [rsp+2E8h+dwFlagsAndAttributes], rax; wchar_t *
0x10044473c  lea     rcx, [rsp+2E8h+Buffer]; wchar_t *
0x100444744  mov     r14d, 104h
0x10044474a  mov     [rsp+2E8h+NumberOfBytesWritten], r13d
0x10044474f  mov     edx, r14d; unsigned __int64
0x100444752  mov     [rsp+2E8h+var_290], r13
0x100444757  mov     qword ptr [rsp+2E8h+dwCreationDisposition], r13; unsigned int
0x10044475c  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x100444761  test    eax, eax
0x100444763  jns     short loc_100444782
0x100444765  lfence
0x100444768  mov     r9d, eax
0x10044476b  lea     r8, aStringcchprint; "StringCchPrintfExW failed to construct "...
0x100444772  mov     rdx, rbp; unsigned __int64
0x100444775  mov     rcx, rsi; Buffer
0x100444778  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10044477d  jmp     loc_100444802
0x100444782  sub     r14, [rsp+2E8h+var_290]
0x100444787  lea     r9, [rsp+2E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x10044478c  add     r14, r14
0x10044478f  mov     qword ptr [rsp+2E8h+dwCreationDisposition], r13; lpOverlapped
0x100444794  mov     r8d, r14d; nNumberOfBytesToWrite
0x100444797  lea     rdx, [rsp+2E8h+Buffer]; lpBuffer
0x10044479f  mov     rcx, r15; hFile
0x1004447a2  call    cs:__imp_WriteFile
0x1004447a8  test    eax, eax
0x1004447aa  jnz     short loc_1004447CD
0x1004447ac  call    cs:__imp_GetLastError
0x1004447b2  mov     r9, rdi
0x1004447b5  lea     r8, aUnableToWriteT; "Unable to write to file: %ls, error: %d"
0x1004447bc  mov     rdx, rbp; unsigned __int64
0x1004447bf  mov     [rsp+2E8h+dwCreationDisposition], eax
0x1004447c3  mov     rcx, rsi; Buffer
0x1004447c6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004447cb  jmp     short loc_100444802
0x1004447cd  mov     eax, [rsp+2E8h+NumberOfBytesWritten]
0x1004447d1  cmp     rax, r14
0x1004447d4  jz      short loc_10044481D
0x1004447d6  call    cs:__imp_GetLastError
0x1004447dc  mov     ecx, [rsp+2E8h+NumberOfBytesWritten]
0x1004447e0  lea     r8, aWritefileFaile; "WriteFile failed: %ls, error: %d, bytes"...
0x1004447e7  mov     [rsp+2E8h+hTemplateFile], r14
0x1004447ec  mov     r9, rdi
0x1004447ef  mov     [rsp+2E8h+dwFlagsAndAttributes], ecx
0x1004447f3  mov     rdx, rbp; unsigned __int64
0x1004447f6  mov     rcx, rsi; Buffer
0x1004447f9  mov     [rsp+2E8h+dwCreationDisposition], eax
0x1004447fd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444802  mov     rcx, r15; hObject
0x100444805  call    cs:__imp_CloseHandle
0x10044480b  test    bl, bl
0x10044480d  jnz     short loc_100444818
0x10044480f  mov     rcx, rdi; lpFileName
0x100444812  call    cs:__imp_DeleteFileW
0x100444818  movzx   eax, bl
0x10044481b  jmp     short loc_10044483D
0x10044481d  mov     r9, rdi
0x100444820  lea     r8, aLsCreatedSucce; "%ls created successfully."
0x100444827  mov     rdx, rbp; unsigned __int64
0x10044482a  mov     rcx, rsi; Buffer
0x10044482d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444832  mov     rcx, r15; hObject
0x100444835  call    cs:__imp_CloseHandle
0x10044483b  mov     al, 1
0x10044483d  mov     r15, [rsp+2E8h+var_40]
0x100444845  mov     rcx, [rsp+2E8h+var_58]
0x10044484d  xor     rcx, rsp; StackCookie
0x100444850  call    __security_check_cookie
0x100444855  add     rsp, 2B0h
0x10044485c  pop     r14
0x10044485e  pop     r13
0x100444860  pop     r12
0x100444862  pop     rdi
0x100444863  pop     rsi
0x100444864  pop     rbp
0x100444865  pop     rbx
0x100444866  retn
```
