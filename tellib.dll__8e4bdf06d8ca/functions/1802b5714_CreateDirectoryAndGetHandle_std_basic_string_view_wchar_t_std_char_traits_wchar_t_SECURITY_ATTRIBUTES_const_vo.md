# CreateDirectoryAndGetHandle(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_SECURITY_ATTRIBUTES const *,void * *,ulong,ulong)

- ea: `0x1802b5714`
- end: `0x1802b592e`
- name: `?CreateDirectoryAndGetHandle@@YAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEBU_SECURITY_ATTRIBUTES@@PEAPEAXKK@Z`
- size: `538`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800aa970`
- `0x1801e0ba0`
- `0x18022d4bc`

## callees

- `0x18001d160`
- `0x180035698`
- `0x18012de40`
- `0x1802b5714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802b58f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802b58f7`
- `ntdll!RtlIsDosDeviceName_U` at `0x1802b58d1`
- `ntdll!RtlIsDosDeviceName_U` at `0x1802b58d1`
- `ntdll!RtlFreeHeap` at `0x1802b588c`
- `ntdll!RtlFreeHeap` at `0x1802b588c`
- `ntdll!RtlReleaseRelativeName` at `0x1802b586e`
- `ntdll!RtlReleaseRelativeName` at `0x1802b586e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1802b5793`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1802b5793`
- `ntdll!NtCreateFile` at `0x1802b585b`
- `ntdll!NtCreateFile` at `0x1802b585b`
- `ntdll!NtClose` at `0x1802b58b0`
- `ntdll!NtClose` at `0x1802b58b0`
- `ntdll!RtlNtStatusToDosError` at `0x1802b58e9`
- `ntdll!RtlNtStatusToDosError` at `0x1802b58e9`

## pseudocode

```c
__int64 __fastcall CreateDirectoryAndGetHandle(_QWORD *a1, __int64 a2, void **a3, int a4, ULONG ShareAccess)
{
  const WCHAR *v8; // rcx
  ULONG v9; // ecx
  PWSTR Buffer; // r14
  HANDLE ContainingDirectory; // rax
  int v12; // ebx
  unsigned int v13; // ebx
  const WCHAR *v14; // rcx
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+68h] [rbp-98h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+78h] [rbp-88h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  PCWSTR DosName[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v22; // [rsp+F0h] [rbp-10h]

  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  std::wstring::wstring((__int64)DosName, a1);
  v8 = (const WCHAR *)DosName;
  if ( v22 > 7 )
    v8 = DosName[0];
  if ( !RtlDosPathNameToRelativeNtPathName_U(v8, &NtName, 0, &RelativeName) )
  {
    v9 = 3;
LABEL_20:
    SetLastError(v9);
    v13 = 0;
    goto LABEL_21;
  }
  Buffer = NtName.Buffer;
  if ( RelativeName.RelativeName.Length )
  {
    NtName = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a2 )
    ObjectAttributes.SecurityDescriptor = *(PVOID *)(a2 + 8);
  v12 = NtCreateFile(
          &FileHandle,
          a4 | 0x100001,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          ShareAccess,
          2u,
          0x204021u,
          0,
          0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v12 < 0 )
  {
    v14 = (const WCHAR *)DosName;
    if ( v22 > 7 )
      v14 = DosName[0];
    if ( RtlIsDosDeviceName_U(v14) )
      v12 = -1073741565;
    v9 = RtlNtStatusToDosError(v12);
    goto LABEL_20;
  }
  if ( a3 )
    *a3 = FileHandle;
  else
    NtClose(FileHandle);
  v13 = 1;
LABEL_21:
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)DosName);
  return v13;
}

```

## disassembly

```asm
0x1802b5714  push    rbp
0x1802b5716  push    rbx
0x1802b5717  push    rsi
0x1802b5718  push    rdi
0x1802b5719  push    r14
0x1802b571b  push    r15
0x1802b571d  lea     rbp, [rsp-8]
0x1802b5722  sub     rsp, 108h
0x1802b5729  mov     rax, cs:__security_cookie
0x1802b5730  xor     rax, rsp
0x1802b5733  mov     [rbp+30h+var_38], rax
0x1802b5737  xorps   xmm0, xmm0
0x1802b573a  mov     rbx, rdx
0x1802b573d  mov     rdx, rcx
0x1802b5740  xorps   xmm1, xmm1
0x1802b5743  xor     r15d, r15d
0x1802b5746  lea     rcx, [rbp+30h+DosName]
0x1802b574a  mov     esi, r9d
0x1802b574d  mov     [rsp+130h+FileHandle], r15
0x1802b5752  mov     rdi, r8
0x1802b5755  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x1802b5759  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x1802b575d  movups  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1802b5761  movups  xmmword ptr [rsp+130h+NtName.Length], xmm0
0x1802b5766  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm1
0x1802b576a  movups  xmmword ptr [rsp+130h+RelativeName.RelativeName.Length], xmm0
0x1802b576f  movups  xmmword ptr [rbp+30h+RelativeName.ContainingDirectory], xmm0
0x1802b5773  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1802b5778  cmp     [rbp+30h+var_40], 7
0x1802b577d  lea     rcx, [rbp+30h+DosName]
0x1802b5781  lea     r9, [rsp+130h+RelativeName]; RelativeName
0x1802b5786  cmova   rcx, [rbp+30h+DosName]; DosName
0x1802b578b  lea     rdx, [rsp+130h+NtName]; NtName
0x1802b5790  xor     r8d, r8d; PartName
0x1802b5793  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1802b579a  nop     dword ptr [rax+rax+00h]
0x1802b579f  test    al, al
0x1802b57a1  jnz     short loc_1802B57AC
0x1802b57a3  lea     ecx, [r15+3]
0x1802b57a7  jmp     loc_1802B58F7
0x1802b57ac  movzx   eax, [rsp+130h+RelativeName.RelativeName.Length]
0x1802b57b1  mov     r14, [rsp+130h+NtName.Buffer]
0x1802b57b6  test    ax, ax
0x1802b57b9  jz      short loc_1802B57E1
0x1802b57bb  mov     [rsp+130h+NtName.Length], ax
0x1802b57c0  mov     eax, dword ptr [rsp+130h+RelativeName.RelativeName.MaximumLength]
0x1802b57c4  mov     dword ptr [rsp+130h+NtName.MaximumLength], eax
0x1802b57c8  movzx   eax, word ptr [rsp+130h+RelativeName.RelativeName+6]
0x1802b57cd  mov     word ptr [rsp+130h+NtName+6], ax
0x1802b57d2  mov     rax, [rbp+30h+RelativeName.RelativeName.Buffer]
0x1802b57d6  mov     [rsp+130h+NtName.Buffer], rax
0x1802b57db  mov     rax, [rbp+30h+RelativeName.ContainingDirectory]
0x1802b57df  jmp     short loc_1802B57E8
0x1802b57e1  mov     rax, r15
0x1802b57e4  mov     [rbp+30h+RelativeName.ContainingDirectory], rax
0x1802b57e8  mov     [rbp+30h+ObjectAttributes.RootDirectory], rax
0x1802b57ec  lea     rax, [rsp+130h+NtName]
0x1802b57f1  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x1802b57f5  xorps   xmm0, xmm0
0x1802b57f8  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x1802b57ff  mov     [rbp+30h+ObjectAttributes.Attributes], 40h ; '@'
0x1802b5806  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1802b580b  test    rbx, rbx
0x1802b580e  jz      short loc_1802B5818
0x1802b5810  mov     rax, [rbx+8]
0x1802b5814  mov     [rbp+30h+ObjectAttributes.SecurityDescriptor], rax
0x1802b5818  mov     eax, [rbp+30h+arg_20]
0x1802b581b  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x1802b581f  mov     [rsp+130h+EaLength], r15d; EaLength
0x1802b5824  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x1802b5828  mov     [rsp+130h+EaBuffer], r15; EaBuffer
0x1802b582d  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x1802b5832  mov     [rsp+130h+CreateOptions], 204021h; CreateOptions
0x1802b583a  or      esi, 100001h
0x1802b5840  mov     [rsp+130h+CreateDisposition], 2; CreateDisposition
0x1802b5848  mov     edx, esi; DesiredAccess
0x1802b584a  mov     [rsp+130h+ShareAccess], eax; ShareAccess
0x1802b584e  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x1802b5856  mov     [rsp+130h+AllocationSize], r15; AllocationSize
0x1802b585b  call    cs:__imp_NtCreateFile
0x1802b5862  nop     dword ptr [rax+rax+00h]
0x1802b5867  lea     rcx, [rsp+130h+RelativeName]; RelativeName
0x1802b586c  mov     ebx, eax
0x1802b586e  call    cs:__imp_RtlReleaseRelativeName
0x1802b5875  nop     dword ptr [rax+rax+00h]
0x1802b587a  mov     rcx, gs:60h
0x1802b5883  mov     r8, r14; P
0x1802b5886  xor     edx, edx; Flags
0x1802b5888  mov     rcx, [rcx+30h]; HeapHandle
0x1802b588c  call    cs:__imp_RtlFreeHeap
0x1802b5893  nop     dword ptr [rax+rax+00h]
0x1802b5898  test    ebx, ebx
0x1802b589a  js      short loc_1802B58C3
0x1802b589c  test    rdi, rdi
0x1802b589f  jz      short loc_1802B58AB
0x1802b58a1  mov     rax, [rsp+130h+FileHandle]
0x1802b58a6  mov     [rdi], rax
0x1802b58a9  jmp     short loc_1802B58BC
0x1802b58ab  mov     rcx, [rsp+130h+FileHandle]; Handle
0x1802b58b0  call    cs:__imp_NtClose
0x1802b58b7  nop     dword ptr [rax+rax+00h]
0x1802b58bc  mov     ebx, 1
0x1802b58c1  jmp     short loc_1802B5906
0x1802b58c3  cmp     [rbp+30h+var_40], 7
0x1802b58c8  lea     rcx, [rbp+30h+DosName]
0x1802b58cc  cmova   rcx, [rbp+30h+DosName]; Name
0x1802b58d1  call    cs:__imp_RtlIsDosDeviceName_U
0x1802b58d8  nop     dword ptr [rax+rax+00h]
0x1802b58dd  mov     ecx, 0C0000103h
0x1802b58e2  test    eax, eax
0x1802b58e4  cmovnz  ebx, ecx
0x1802b58e7  mov     ecx, ebx; Status
0x1802b58e9  call    cs:__imp_RtlNtStatusToDosError
0x1802b58f0  nop     dword ptr [rax+rax+00h]
0x1802b58f5  mov     ecx, eax; dwErrCode
0x1802b58f7  call    cs:__imp_SetLastError
0x1802b58fe  nop     dword ptr [rax+rax+00h]
0x1802b5903  mov     ebx, r15d
0x1802b5906  lea     rcx, [rbp+30h+DosName]; this
0x1802b590a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802b590f  mov     eax, ebx
0x1802b5911  mov     rcx, [rbp+30h+var_38]
0x1802b5915  xor     rcx, rsp; StackCookie
0x1802b5918  call    __security_check_cookie
0x1802b591d  add     rsp, 108h
0x1802b5924  pop     r15
0x1802b5926  pop     r14
0x1802b5928  pop     rdi
0x1802b5929  pop     rsi
0x1802b592a  pop     rbx
0x1802b592b  pop     rbp
0x1802b592c  retn
```
