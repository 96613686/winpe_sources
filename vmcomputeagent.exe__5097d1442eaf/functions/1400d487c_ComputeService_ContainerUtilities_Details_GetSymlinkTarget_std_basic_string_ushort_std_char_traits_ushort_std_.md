# ComputeService::ContainerUtilities::Details::GetSymlinkTarget(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400d487c`
- end: `0x1400d4af3`
- name: `?GetSymlinkTarget@Details@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z`
- size: `631`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d33f4`
- `0x1400d5124`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x140006098`
- `0x1400068e0`
- `0x140008760`
- `0x14001e4f4`
- `0x14002dd18`
- `0x14004161c`
- `0x1400d487c`
- `0x1400d5b0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d497e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d497e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d496b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d496b`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d4999`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d4999`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1400d4a2d`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1400d4a2d`
- `ntdll!RtlInitUnicodeString` at `0x1400d4927`
- `ntdll!RtlInitUnicodeString` at `0x1400d4927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4ab8`

## string_xrefs

- `0x1400d49b7`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d4a64`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d49a8`: `Symlink: %ws`
- `0x1400d4a55`: `Symlink: %ws Status: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ComputeService::ContainerUtilities::Details::GetSymlinkTarget(__int64 a1)
{
  void *v2; // rbx
  ULONG v3; // esi
  __int64 v4; // rax
  const WCHAR *v5; // rdx
  PCWSTR *v6; // r12
  HANDLE v7; // r15
  DWORD LastError; // edi
  unsigned int v9; // eax
  unsigned __int64 v10; // rdi
  void *v11; // r15
  unsigned __int64 v12; // rdx
  void *v13; // rcx
  unsigned int v14; // eax
  PCWSTR *v15; // rdx
  unsigned __int64 v16; // rdx
  _BYTE v18[32]; // [rsp+50h] [rbp-79h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+70h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-49h] BYREF
  ULONG DataWritten; // [rsp+B0h] [rbp-19h] BYREF
  HANDLE hObject; // [rsp+B8h] [rbp-11h] BYREF
  PCWSTR SourceString[2]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v24; // [rsp+D0h] [rbp+7h]
  unsigned __int64 v25; // [rsp+D8h] [rbp+Fh]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  *(_OWORD *)SourceString = 0;
  v24 = 0;
  v25 = 7;
  LOWORD(SourceString[0]) = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  hObject = 0;
  v2 = 0;
  v3 = 200;
  DataWritten = 0;
  LinkTarget = 0;
  v4 = ComputeService::ContainerUtilities::Details::SubstituteGlobalPrefix(v18);
  std::wstring::operator=(SourceString, v4);
  std::wstring::~wstring(v18);
  v5 = (const WCHAR *)SourceString;
  if ( v25 > 7 )
    v5 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v5);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = SourceString;
  if ( v25 > 7 )
    v6 = (PCWSTR *)SourceString[0];
  v7 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v7);
    SetLastError(LastError);
  }
  hObject = 0;
  v9 = NtOpenSymbolicLinkObject(&hObject, 1u, &ObjectAttributes);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x12D,
    (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
    (const char *)v9,
    (int)"Symlink: %ws",
    (const char *)v6);
  do
  {
    v10 = saturated_mul(v3, 2u);
    v11 = operator new[](v10);
    memset_0(v11, 0, v10);
    v13 = v2;
    v2 = v11;
    if ( v13 )
      operator delete(v13, v12);
    v3 *= 2;
    DataWritten = v3;
    *(_QWORD *)&LinkTarget.Length = 0;
    LinkTarget.MaximumLength = v3;
    LinkTarget.Buffer = (PWSTR)v11;
    v14 = NtQuerySymbolicLinkObject(hObject, &LinkTarget, &DataWritten);
  }
  while ( v14 == -1073741789 );
  v15 = SourceString;
  if ( v25 > 7 )
    v15 = (PCWSTR *)SourceString[0];
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x140,
    (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
    (const char *)v14,
    (int)"Symlink: %ws Status: %x",
    (const char *)v15,
    v14);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>(a1, LinkTarget.Buffer, (unsigned __int64)LinkTarget.Length >> 1);
  operator delete(v11, v16);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  std::wstring::~wstring(SourceString);
  return a1;
}

```

## disassembly

```asm
0x1400d487c  mov     [rsp-8+arg_10], rbx
0x1400d4881  mov     [rsp-8+arg_18], rsi
0x1400d4886  push    rbp
0x1400d4887  push    rdi
0x1400d4888  push    r12
0x1400d488a  push    r14
0x1400d488c  push    r15
0x1400d488e  lea     rbp, [rsp-37h]
0x1400d4893  sub     rsp, 100h
0x1400d489a  mov     rax, cs:__security_cookie
0x1400d48a1  xor     rax, rsp
0x1400d48a4  mov     [rbp+57h+var_30], rax
0x1400d48a8  mov     r14, rcx
0x1400d48ab  mov     [rsp+120h+var_E0], rcx
0x1400d48b0  xorps   xmm0, xmm0
0x1400d48b3  movups  xmmword ptr [rbp+57h+SourceString], xmm0
0x1400d48b7  mov     [rbp+57h+var_50], 0
0x1400d48bf  mov     [rbp+57h+var_48], 7
0x1400d48c7  xor     eax, eax
0x1400d48c9  mov     word ptr [rbp+57h+SourceString], ax
0x1400d48cd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d48d1  xorps   xmm1, xmm1
0x1400d48d4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400d48d8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400d48dc  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400d48e0  mov     [rbp+57h+hObject], rax
0x1400d48e4  xor     ebx, ebx
0x1400d48e6  mov     [rsp+120h+var_E0], rbx
0x1400d48eb  mov     esi, 0C8h
0x1400d48f0  mov     [rbp+57h+DataWritten], ebx
0x1400d48f3  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x1400d48f7  lea     rcx, [rbp+57h+var_D0]
0x1400d48fb  call    ?SubstituteGlobalPrefix@Details@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; ComputeService::ContainerUtilities::Details::SubstituteGlobalPrefix(std::wstring const &)
0x1400d4900  mov     rdx, rax
0x1400d4903  lea     rcx, [rbp+57h+SourceString]
0x1400d4907  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d490c  lea     rcx, [rbp+57h+var_D0]; void *
0x1400d4910  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d4915  lea     rdx, [rbp+57h+SourceString]
0x1400d4919  cmp     [rbp+57h+var_48], 7
0x1400d491e  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x1400d4923  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d4927  call    cs:__imp_RtlInitUnicodeString
0x1400d492d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d4934  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400d4938  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1400d493f  lea     rax, [rbp+57h+DestinationString]
0x1400d4943  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d4947  xorps   xmm0, xmm0
0x1400d494a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d494f  lea     r12, [rbp+57h+SourceString]
0x1400d4953  cmp     [rbp+57h+var_48], 7
0x1400d4958  cmova   r12, [rbp+57h+SourceString]
0x1400d495d  mov     r15, [rbp+57h+hObject]
0x1400d4961  lea     rax, [r15-1]
0x1400d4965  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d4969  ja      short loc_1400D4984
0x1400d496b  call    cs:__imp_GetLastError
0x1400d4971  mov     edi, eax
0x1400d4973  mov     rcx, r15; hObject
0x1400d4976  call    cs:__imp_CloseHandle
0x1400d497c  mov     ecx, edi; dwErrCode
0x1400d497e  call    cs:__imp_SetLastError
0x1400d4984  mov     [rbp+57h+hObject], 0
0x1400d498c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d4990  mov     edx, 1; DesiredAccess
0x1400d4995  lea     rcx, [rbp+57h+hObject]; SymbolicLinkHandle
0x1400d4999  call    cs:__imp_NtOpenSymbolicLinkObject
0x1400d499f  mov     rcx, [rbp+5Fh]; this
0x1400d49a3  mov     [rsp+120h+var_F8], r12; char *
0x1400d49a8  lea     rdx, aSymlinkWs; "Symlink: %ws"
0x1400d49af  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1400d49b4  mov     r9d, eax; char *
0x1400d49b7  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d49be  mov     edx, 12Dh; void *
0x1400d49c3  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400d49c8  mov     ecx, esi
0x1400d49ca  mov     eax, 2
0x1400d49cf  mul     rcx
0x1400d49d2  mov     rdi, rax
0x1400d49d5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400d49dc  cmovb   rdi, rax
0x1400d49e0  mov     rcx, rdi; unsigned __int64
0x1400d49e3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400d49e8  mov     r15, rax
0x1400d49eb  mov     r8, rdi; Size
0x1400d49ee  xor     edx, edx; Val
0x1400d49f0  mov     rcx, rax; void *
0x1400d49f3  call    memset_0
0x1400d49f8  mov     rcx, rbx; void *
0x1400d49fb  mov     rbx, r15
0x1400d49fe  mov     [rsp+120h+var_E0], rbx
0x1400d4a03  test    rcx, rcx
0x1400d4a06  jz      short loc_1400D4A0D
0x1400d4a08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d4a0d  add     esi, esi
0x1400d4a0f  mov     [rbp+57h+DataWritten], esi
0x1400d4a12  xorps   xmm0, xmm0
0x1400d4a15  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x1400d4a19  mov     [rbp+57h+LinkTarget.MaximumLength], si
0x1400d4a1d  mov     [rbp+57h+LinkTarget.Buffer], r15
0x1400d4a21  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x1400d4a25  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x1400d4a29  mov     rcx, [rbp+57h+hObject]; SymLinkObjHandle
0x1400d4a2d  call    cs:__imp_NtQuerySymbolicLinkObject
0x1400d4a33  cmp     eax, 0C0000023h
0x1400d4a38  jz      short loc_1400D49C8
0x1400d4a3a  lea     rdx, [rbp+57h+SourceString]
0x1400d4a3e  cmp     [rbp+57h+var_48], 7
0x1400d4a43  cmova   rdx, [rbp+57h+SourceString]
0x1400d4a48  mov     rcx, [rbp+5Fh]; this
0x1400d4a4c  mov     [rsp+120h+var_F0], eax
0x1400d4a50  mov     [rsp+120h+var_F8], rdx; char *
0x1400d4a55  lea     rdx, aSymlinkWsStatu; "Symlink: %ws Status: %x"
0x1400d4a5c  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1400d4a61  mov     r9d, eax; char *
0x1400d4a64  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d4a6b  mov     edx, 140h; void *
0x1400d4a70  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400d4a75  xorps   xmm0, xmm0
0x1400d4a78  movups  xmmword ptr [r14], xmm0
0x1400d4a7c  mov     qword ptr [r14+10h], 0
0x1400d4a84  mov     qword ptr [r14+18h], 0
0x1400d4a8c  movzx   r8d, [rbp+57h+LinkTarget.Length]
0x1400d4a91  shr     r8, 1
0x1400d4a94  mov     rdx, [rbp+57h+LinkTarget.Buffer]
0x1400d4a98  mov     rcx, r14
0x1400d4a9b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400d4aa0  nop
0x1400d4aa1  mov     rcx, r15; void *
0x1400d4aa4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d4aa9  nop
0x1400d4aaa  mov     rcx, [rbp+57h+hObject]; hObject
0x1400d4aae  lea     rdx, [rcx-1]
0x1400d4ab2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400d4ab6  ja      short loc_1400D4ABF
0x1400d4ab8  call    cs:__imp_CloseHandle
0x1400d4abe  nop
0x1400d4abf  lea     rcx, [rbp+57h+SourceString]; void *
0x1400d4ac3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d4ac8  mov     rax, r14
0x1400d4acb  mov     rcx, [rbp+57h+var_30]
0x1400d4acf  xor     rcx, rsp; StackCookie
0x1400d4ad2  call    __security_check_cookie
0x1400d4ad7  lea     r11, [rsp+120h+var_20]
0x1400d4adf  mov     rbx, [r11+40h]
0x1400d4ae3  mov     rsi, [r11+48h]
0x1400d4ae7  mov     rsp, r11
0x1400d4aea  pop     r15
0x1400d4aec  pop     r14
0x1400d4aee  pop     r12
0x1400d4af0  pop     rdi
0x1400d4af1  pop     rbp
0x1400d4af2  retn
```
