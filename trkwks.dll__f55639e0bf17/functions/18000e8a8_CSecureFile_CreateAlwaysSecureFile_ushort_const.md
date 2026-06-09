# CSecureFile::CreateAlwaysSecureFile(ushort const *)

- ea: `0x18000e8a8`
- end: `0x18000ea59`
- name: `?CreateAlwaysSecureFile@CSecureFile@@QEAAJPEBG@Z`
- size: `433`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e7c0`

## callees

- `0x180009ba4`
- `0x18000ad70`
- `0x18000af38`
- `0x18000af5c`
- `0x18000b4a0`
- `0x18000d038`
- `0x18000d1a0`
- `0x18000d440`
- `0x18000e8a8`
- `0x180011000`

## import_xrefs

- `msvcrt!wcschr` at `0x18000e9bc`
- `msvcrt!wcschr` at `0x18000e9bc`
- `ntdll!RtlFreeUnicodeString` at `0x18000ea04`
- `ntdll!RtlFreeUnicodeString` at `0x18000ea04`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18000e9f3`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18000e9f3`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000e9da`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000e9da`

## pseudocode

```c
__int64 __fastcall CSecureFile::CreateAlwaysSecureFile(void **this, const unsigned __int16 *a2)
{
  NTSTATUS v4; // ebx
  int i; // esi
  int v6; // eax
  struct _UNICODE_STRING NtPathName; // [rsp+50h] [rbp-2B8h] BYREF
  struct _SECURITY_ATTRIBUTES v9; // [rsp+60h] [rbp-2A8h] BYREF
  _BYTE v10[80]; // [rsp+80h] [rbp-288h] BYREF
  WCHAR DosPathName; // [rsp+D0h] [rbp-238h] BYREF
  wchar_t Str[260]; // [rsp+D8h] [rbp-230h] BYREF

  v4 = 0;
  CSystemSD::CSystemSD((CSystemSD *)v10);
  *(&v9.nLength + 1) = 0;
  *(&v9.bInheritHandle + 1) = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  CSystemSD::Initialize(v10);
  v9.nLength = 24;
  v9.bInheritHandle = 0;
  v9.lpSecurityDescriptor = (LPVOID)CSecDescriptor::operator void * const(v10);
  for ( i = 0; i < 2; ++i )
  {
    v6 = TrkCreateFile(a2, 1180063, 6u, 0, 0, 0, &v9, this);
    v4 = v6;
    if ( v6 >= 0 )
      break;
    *this = 0;
    if ( v6 != -1073741766 )
      break;
    NtPathName = 0;
    if ( (int)StringCchCopyW(&DosPathName, 0x104u, a2) < 0 )
      TrkRaiseWin32Error(-2147483643);
    *wcschr(Str, 0x5Cu) = 0;
    if ( !RtlDosPathNameToNtPathName_U(&DosPathName, &NtPathName, 0, 0) )
      TrkRaiseWin32Error(3);
    v4 = RtlCreateSystemVolumeInformationFolder(&NtPathName);
    RtlFreeUnicodeString(&NtPathName);
    if ( v4 < 0 )
      break;
  }
  CSystemSD::UnInitialize((CSystemSD *)v10);
  _InterlockedDecrement((volatile signed __int32 *)this + 2);
  CSystemSD::~CSystemSD((CSystemSD *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e8a8  mov     [rsp+arg_10], rbx
0x18000e8ad  push    rsi
0x18000e8ae  push    rdi
0x18000e8af  push    r14
0x18000e8b1  sub     rsp, 2F0h
0x18000e8b8  mov     rax, cs:__security_cookie
0x18000e8bf  xor     rax, rsp
0x18000e8c2  mov     [rsp+308h+var_28], rax
0x18000e8ca  mov     r14, rdx
0x18000e8cd  mov     rdi, rcx
0x18000e8d0  mov     [rsp+308h+var_2C0], rcx
0x18000e8d5  xor     ebx, ebx
0x18000e8d7  lea     rcx, [rsp+308h+var_288]; this
0x18000e8df  call    ??0CSystemSD@@QEAA@XZ; CSystemSD::CSystemSD(void)
0x18000e8e4  xorps   xmm2, xmm2
0x18000e8e7  xor     eax, eax
0x18000e8e9  movups  xmmword ptr [rsp+308h+var_2A8.nLength], xmm2
0x18000e8ee  mov     qword ptr [rsp+308h+var_2A8.bInheritHandle], rax
0x18000e8f3  lock inc dword ptr [rdi+8]
0x18000e8f7  lea     rcx, [rsp+308h+var_288]
0x18000e8ff  call    ?Initialize@CSystemSD@@QEAAXW4ESystemSD@1@@Z; CSystemSD::Initialize(CSystemSD::ESystemSD)
0x18000e904  mov     [rsp+308h+var_2A8.nLength], 18h
0x18000e90c  mov     [rsp+308h+var_2A8.bInheritHandle], ebx
0x18000e910  lea     rcx, [rsp+308h+var_288]
0x18000e918  call    ??BCSecDescriptor@@QEAAQEAXXZ; CSecDescriptor::operator void * const(void)
0x18000e91d  mov     [rsp+308h+var_2A8.lpSecurityDescriptor], rax
0x18000e922  xor     esi, esi
0x18000e924  mov     [rsp+308h+var_2C4], esi
0x18000e928  cmp     esi, 2
0x18000e92b  jge     loc_18000EA15
0x18000e931  mov     [rsp+308h+var_2D0], rdi; void **
0x18000e936  lea     rax, [rsp+308h+var_2A8]
0x18000e93b  mov     [rsp+308h+var_2D8], rax; struct _SECURITY_ATTRIBUTES *
0x18000e940  mov     [rsp+308h+var_2E0], 0; unsigned int
0x18000e948  mov     [rsp+308h+var_2E8], 0; unsigned int
0x18000e950  xor     r9d, r9d; unsigned int
0x18000e953  mov     edx, 12019Fh; unsigned int
0x18000e958  lea     r8d, [r9+6]; unsigned int
0x18000e95c  mov     rcx, r14; unsigned __int16 *
0x18000e95f  call    ?TrkCreateFile@@YAJPEBGKKKKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAX@Z; TrkCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *)
0x18000e964  mov     ebx, eax
0x18000e966  mov     [rsp+308h+var_2C8], eax
0x18000e96a  test    eax, eax
0x18000e96c  jns     loc_18000EA15
0x18000e972  mov     qword ptr [rdi], 0
0x18000e979  cmp     eax, 0C000003Ah
0x18000e97e  jnz     loc_18000EA15
0x18000e984  xorps   xmm0, xmm0
0x18000e987  movups  xmmword ptr [rsp+308h+NtPathName.Length], xmm0
0x18000e98c  mov     r8, r14; unsigned __int16 *
0x18000e98f  mov     edx, 104h; unsigned __int64
0x18000e994  lea     rcx, [rsp+308h+DosPathName]; unsigned __int16 *
0x18000e99c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e9a1  test    eax, eax
0x18000e9a3  jns     short loc_18000E9AF
0x18000e9a5  mov     ecx, 80000005h; int
0x18000e9aa  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000e9af  mov     edx, 5Ch ; '\'; Ch
0x18000e9b4  lea     rcx, [rsp+308h+Str]; Str
0x18000e9bc  call    cs:__imp_wcschr
0x18000e9c2  xor     ecx, ecx
0x18000e9c4  mov     [rax], cx
0x18000e9c7  xor     r9d, r9d; DirectoryInfo
0x18000e9ca  xor     r8d, r8d; NtFileNamePart
0x18000e9cd  lea     rdx, [rsp+308h+NtPathName]; NtPathName
0x18000e9d2  lea     rcx, [rsp+308h+DosPathName]; DosPathName
0x18000e9da  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000e9e0  test    al, al
0x18000e9e2  jnz     short loc_18000E9EE
0x18000e9e4  mov     ecx, 3; int
0x18000e9e9  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000e9ee  lea     rcx, [rsp+308h+NtPathName]; VolumeRootPath
0x18000e9f3  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x18000e9f9  mov     ebx, eax
0x18000e9fb  mov     [rsp+308h+var_2C8], eax
0x18000e9ff  lea     rcx, [rsp+308h+NtPathName]; UnicodeString
0x18000ea04  call    cs:__imp_RtlFreeUnicodeString
0x18000ea0a  test    ebx, ebx
0x18000ea0c  js      short loc_18000EA15
0x18000ea0e  inc     esi
0x18000ea10  jmp     loc_18000E924
0x18000ea15  lea     rcx, [rsp+308h+var_288]; this
0x18000ea1d  call    ?UnInitialize@CSystemSD@@QEAAXXZ; CSystemSD::UnInitialize(void)
0x18000ea22  lock dec dword ptr [rdi+8]
0x18000ea26  lea     rcx, [rsp+308h+var_288]; this
0x18000ea2e  call    ??1CSystemSD@@QEAA@XZ; CSystemSD::~CSystemSD(void)
0x18000ea33  mov     eax, ebx
0x18000ea35  mov     rcx, [rsp+308h+var_28]
0x18000ea3d  xor     rcx, rsp; StackCookie
0x18000ea40  call    __security_check_cookie
0x18000ea45  mov     rbx, [rsp+308h+arg_10]
0x18000ea4d  add     rsp, 2F0h
0x18000ea54  pop     r14
0x18000ea56  pop     rdi
0x18000ea57  pop     rsi
0x18000ea58  retn
0x180011c16  push    rbp
0x180011c18  sub     rsp, 40h
0x180011c1c  mov     rbp, rdx
0x180011c1f  lea     rcx, [rbp+80h]; this
0x180011c26  call    ?UnInitialize@CSystemSD@@QEAAXXZ; CSystemSD::UnInitialize(void)
0x180011c2b  mov     rax, [rbp+48h]
0x180011c2f  lock dec dword ptr [rax+8]
0x180011c33  add     rsp, 40h
0x180011c37  pop     rbp
0x180011c38  retn
```
