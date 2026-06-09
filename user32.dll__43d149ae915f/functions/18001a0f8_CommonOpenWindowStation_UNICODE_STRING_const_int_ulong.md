# CommonOpenWindowStation(_UNICODE_STRING const *,int,ulong)

- ea: `0x18001a0f8`
- end: `0x18001a2b0`
- name: `?CommonOpenWindowStation@@YAPEAUHWINSTA__@@PEBU_UNICODE_STRING@@HK@Z`
- size: `440`
- prototype: `HWINSTA __fastcall(const struct _UNICODE_STRING *, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a0b0`
- `0x180094320`

## callees

- `0x18001a0f8`
- `0x18001a2b8`
- `0x180020e80`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserOpenWindowStation` at `0x18001a223`
- `win32u!NtUserOpenWindowStation` at `0x18001a223`
- `ntdll!NtOpenDirectoryObject` at `0x18001a1dd`
- `ntdll!NtOpenDirectoryObject` at `0x18001a1dd`
- `ntdll!NtClose` at `0x18001a231`
- `ntdll!NtClose` at `0x18001a231`
- `ntdll!RtlInitUnicodeString` at `0x18001a1a1`
- `ntdll!RtlInitUnicodeString` at `0x18001a2a0`
- `ntdll!RtlInitUnicodeString` at `0x18001a1a1`
- `ntdll!RtlInitUnicodeString` at `0x18001a2a0`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001a162`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001a162`

## string_xrefs

- `0x18001a26b`: `Service-0x00000000-00000000$`

## pseudocode

```c
__int64 __fastcall CommonOpenWindowStation(struct _UNICODE_STRING *a1, int a2, unsigned int a3)
{
  ULONG SessionId; // edi
  int v7; // eax
  WCHAR *v8; // rdx
  ULONG v9; // edi
  NTSTATUS v10; // eax
  __int64 v11; // rbx
  void *FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v16; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v17[4]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SourceString[256]; // [rsp+D0h] [rbp-30h] BYREF

  v16 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FileHandle = 0;
  DestinationString = 0;
  SessionId = NtCurrentPeb()->SessionId;
  v7 = WTSGetServiceSessionId();
  v8 = L"\\Windows\\WindowStations";
  if ( SessionId != v7 )
  {
    StringCchPrintfW(SourceString, 0x100u, L"%ws\\%ld%ws", L"\\Sessions", SessionId, L"\\Windows\\WindowStations");
    v8 = SourceString;
  }
  RtlInitUnicodeString(&DestinationString, v8);
  v9 = 64;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenDirectoryObject(&FileHandle, 2u, &ObjectAttributes);
  if ( v10 < 0 )
  {
    SetLastNtError((unsigned int)v10);
    return 0;
  }
  else
  {
    if ( !a1->Length )
    {
      wcscpy((wchar_t *)v17, L"Service-0x00000000000000$");
      RtlInitUnicodeString(&v16, (PCWSTR)v17);
      a1 = &v16;
    }
    ObjectAttributes.RootDirectory = FileHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = a1;
    if ( a2 )
      v9 = 66;
    ObjectAttributes.Attributes = v9;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtUserOpenWindowStation(&ObjectAttributes, a3);
    NtClose(FileHandle);
    return v11;
  }
}

```

## disassembly

```asm
0x18001a0f8  mov     [rsp-8+arg_8], rbx
0x18001a0fd  push    rbp
0x18001a0fe  push    rsi
0x18001a0ff  push    rdi
0x18001a100  push    r14
0x18001a102  push    r15
0x18001a104  lea     rbp, [rsp-1E0h]
0x18001a10c  sub     rsp, 2E0h
0x18001a113  mov     rax, cs:__security_cookie
0x18001a11a  xor     rax, rsp
0x18001a11d  mov     [rbp+200h+var_30], rax
0x18001a124  xorps   xmm1, xmm1
0x18001a127  xorps   xmm0, xmm0
0x18001a12a  movups  xmmword ptr [rsp+300h+var_288.Length], xmm0
0x18001a12f  xor     r15d, r15d
0x18001a132  mov     r14d, r8d
0x18001a135  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm1
0x18001a13a  mov     [rsp+300h+FileHandle], r15
0x18001a13f  mov     esi, edx
0x18001a141  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm1
0x18001a146  mov     rbx, rcx
0x18001a149  movups  xmmword ptr [rsp+300h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001a14e  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm0
0x18001a153  mov     rax, gs:60h
0x18001a15c  mov     edi, [rax+2C0h]
0x18001a162  call    cs:__imp_WTSGetServiceSessionId
0x18001a168  lea     rdx, aWindowsWindows; "\\Windows\\WindowStations"
0x18001a16f  cmp     edi, eax
0x18001a171  jz      short loc_18001A19C
0x18001a173  mov     [rsp+300h+var_2D8], rdx
0x18001a178  lea     r9, aSessions; "\\Sessions"
0x18001a17f  mov     edx, 100h; unsigned __int64
0x18001a184  mov     [rsp+300h+var_2E0], edi
0x18001a188  lea     r8, aWsLdWs; "%ws\\%ld%ws"
0x18001a18f  lea     rcx, [rbp+200h+SourceString]; unsigned __int16 *
0x18001a193  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a198  lea     rdx, [rbp+200h+SourceString]; SourceString
0x18001a19c  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x18001a1a1  call    cs:__imp_RtlInitUnicodeString
0x18001a1a7  mov     edi, 40h ; '@'
0x18001a1ac  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x18001a1b4  lea     rax, [rsp+300h+DestinationString]
0x18001a1b9  mov     [rsp+300h+ObjectAttributes.RootDirectory], r15
0x18001a1be  xorps   xmm0, xmm0
0x18001a1c1  mov     [rsp+300h+ObjectAttributes.Attributes], edi
0x18001a1c5  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x18001a1ca  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x18001a1cf  lea     edx, [rdi-3Eh]; DesiredAccess
0x18001a1d2  lea     rcx, [rsp+300h+FileHandle]; FileHandle
0x18001a1d7  movdqu  xmmword ptr [rsp+300h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001a1dd  call    cs:__imp_NtOpenDirectoryObject
0x18001a1e3  test    eax, eax
0x18001a1e5  js      short loc_18001A260
0x18001a1e7  cmp     [rbx], r15w
0x18001a1eb  jz      short loc_18001A26B
0x18001a1ed  mov     rax, [rsp+300h+FileHandle]
0x18001a1f2  lea     rcx, [rsp+300h+ObjectAttributes]
0x18001a1f7  mov     [rsp+300h+ObjectAttributes.RootDirectory], rax
0x18001a1fc  xorps   xmm0, xmm0
0x18001a1ff  mov     eax, 42h ; 'B'
0x18001a204  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x18001a20c  test    esi, esi
0x18001a20e  mov     [rsp+300h+ObjectAttributes.ObjectName], rbx
0x18001a213  mov     edx, r14d
0x18001a216  cmovnz  edi, eax
0x18001a219  mov     [rsp+300h+ObjectAttributes.Attributes], edi
0x18001a21d  movdqu  xmmword ptr [rsp+300h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001a223  call    cs:__imp_NtUserOpenWindowStation
0x18001a229  mov     rcx, [rsp+300h+FileHandle]; Handle
0x18001a22e  mov     rbx, rax
0x18001a231  call    cs:__imp_NtClose
0x18001a237  mov     rax, rbx
0x18001a23a  mov     rcx, [rbp+200h+var_30]
0x18001a241  xor     rcx, rsp; StackCookie
0x18001a244  call    __security_check_cookie
0x18001a249  mov     rbx, [rsp+300h+arg_8]
0x18001a251  add     rsp, 2E0h
0x18001a258  pop     r15
0x18001a25a  pop     r14
0x18001a25c  pop     rdi
0x18001a25d  pop     rsi
0x18001a25e  pop     rbp
0x18001a25f  retn
0x18001a260  mov     ecx, eax
0x18001a262  call    SetLastNtError
0x18001a267  xor     eax, eax
0x18001a269  jmp     short loc_18001A23A
0x18001a26b  movups  xmm0, xmmword ptr cs:aService0x00000; "Service-0x00000000-00000000$"
0x18001a272  lea     rdx, [rbp+200h+var_278]; SourceString
0x18001a276  movups  xmm1, xmmword ptr cs:aService0x00000+10h; "0x00000000-00000000$"
0x18001a27d  lea     rcx, [rsp+300h+var_288]; DestinationString
0x18001a282  movups  xmmword ptr [rbp+200h+var_278], xmm0
0x18001a286  movups  xmm0, xmmword ptr cs:aService0x00000+20h; "00-00000000$"
0x18001a28d  movups  xmmword ptr [rbp+200h+var_278+10h], xmm1
0x18001a291  movups  xmm1, xmmword ptr cs:aService0x00000+2Ah; "000000$"
0x18001a298  movups  [rbp+200h+var_258], xmm0
0x18001a29c  movups  [rbp+200h+var_258+0Ah], xmm1
0x18001a2a0  call    cs:__imp_RtlInitUnicodeString
0x18001a2a6  lea     rbx, [rsp+300h+var_288]
0x18001a2ab  jmp     loc_18001A1ED
```
