# CBrokeredLauncher::CLaunchHelper::_IsFileOwnedByTrustedInstaller(ushort const *)

- ea: `0x18007e6c0`
- end: `0x18007e8ee`
- name: `?_IsFileOwnedByTrustedInstaller@CLaunchHelper@CBrokeredLauncher@@CA_NPEBG@Z`
- size: `558`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180056460`

## callees

- `0x18000f194`
- `0x180041fc8`
- `0x18007e6c0`
- `0x18007e8f4`
- `0x18007e918`
- `0x1800ea2fc`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x18007e72f`
- `ntdll!NtQuerySecurityObject` at `0x18007e7ba`
- `ntdll!NtQuerySecurityObject` at `0x18007e72f`
- `ntdll!NtQuerySecurityObject` at `0x18007e7ba`
- `ntdll!RtlEqualSid` at `0x18007e8bc`
- `ntdll!RtlEqualSid` at `0x18007e8bc`
- `ntdll!RtlCreateServiceSid` at `0x18007e88a`
- `ntdll!RtlCreateServiceSid` at `0x18007e88a`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18007e7fc`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18007e7fc`
- `ntdll!RtlLengthRequiredSid` at `0x18007e833`
- `ntdll!RtlLengthRequiredSid` at `0x18007e833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e8ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e8ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e6f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e6f0`

## string_xrefs

- `0x18007e750`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007e792`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007e7d2`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007e814`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007e859`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007e8a2`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007e873`: `TrustedInstaller`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CBrokeredLauncher::CLaunchHelper::_IsFileOwnedByTrustedInstaller(const unsigned __int16 *a1)
{
  HANDLE FileW; // rdi
  bool v2; // bl
  NTSTATUS v3; // eax
  int v4; // eax
  int v5; // eax
  NTSTATUS v6; // eax
  int v7; // eax
  NTSTATUS OwnerSecurityDescriptor; // eax
  int v9; // eax
  void *v10; // rcx
  int v11; // eax
  NTSTATUS v12; // eax
  int v13; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-50h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-50h]
  PSID ServiceSid; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  PSID Owner; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING ServiceName; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  unsigned __int8 OwnerDefaulted; // [rsp+98h] [rbp+28h] BYREF
  ULONG LengthNeeded; // [rsp+A0h] [rbp+30h] BYREF
  ULONG ServiceSidLength; // [rsp+A8h] [rbp+38h] BYREF

  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL && (int)ResultFromLastError() < 0 )
    return 1;
  LengthNeeded = 0;
  v3 = NtQuerySecurityObject(FileW, 1u, 0, 0, &LengthNeeded);
  if ( v3 < 0 )
  {
    if ( v3 == -1073741789 )
    {
      v4 = 0;
      goto LABEL_7;
    }
  }
  else
  {
    v3 = -1073741823;
  }
  v4 = ResultFromWin32FromStatus(v3);
LABEL_7:
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC82,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
  SecurityDescriptor = 0;
  v5 = CTLocalAllocPolicy::Alloc(retaddr, 0x40u, LengthNeeded, &SecurityDescriptor);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC85,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
  v6 = NtQuerySecurityObject(FileW, 1u, SecurityDescriptor, LengthNeeded, &LengthNeeded);
  v7 = ResultFromWin32FromStatus(v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC87,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDispositiona);
  Owner = 0;
  OwnerDefaulted = 0;
  OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  v9 = ResultFromWin32FromStatus(OwnerSecurityDescriptor);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC8B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v9,
      dwCreationDispositiona);
  ServiceSid = 0;
  ServiceSidLength = RtlLengthRequiredSid(6u);
  v11 = CTLocalAllocPolicy::Alloc(v10, 0x40u, ServiceSidLength, &ServiceSid);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC91,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v11,
      dwCreationDispositiona);
  *(_QWORD *)&ServiceName.Length = 2228256;
  ServiceName.Buffer = L"TrustedInstaller";
  v12 = RtlCreateServiceSid(&ServiceName, ServiceSid, &ServiceSidLength);
  v13 = ResultFromWin32FromStatus(v12);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC94,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v13,
      dwCreationDispositiona);
  v2 = RtlEqualSid(Owner, ServiceSid) != 0;
  CloseHandle(FileW);
  CLocalMemPtr<void>::~CLocalMemPtr<void>(&ServiceSid);
  CLocalMemPtr<void>::~CLocalMemPtr<void>(&SecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x18007e6c0  push    rbp
0x18007e6c2  push    rbx
0x18007e6c3  push    rdi
0x18007e6c4  mov     rbp, rsp
0x18007e6c7  sub     rsp, 70h
0x18007e6cb  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18007e6d4  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18007e6dc  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18007e6e4  xor     r9d, r9d; lpSecurityAttributes
0x18007e6e7  mov     edx, 80000000h; dwDesiredAccess
0x18007e6ec  lea     r8d, [r9+7]; dwShareMode
0x18007e6f0  call    cs:__imp_CreateFileW
0x18007e6f6  mov     rdi, rax
0x18007e6f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007e6fd  jnz     short loc_18007E710
0x18007e6ff  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18007e704  test    eax, eax
0x18007e706  jns     short loc_18007E710
0x18007e708  lea     ebx, [rdi+2]
0x18007e70b  jmp     loc_18007E8E4
0x18007e710  mov     [rbp+LengthNeeded], 0
0x18007e717  lea     rax, [rbp+LengthNeeded]
0x18007e71b  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x18007e720  xor     r9d, r9d; Length
0x18007e723  xor     r8d, r8d; SecurityDescriptor
0x18007e726  lea     ebx, [r9+1]
0x18007e72a  mov     edx, ebx; SecurityInformation
0x18007e72c  mov     rcx, rdi; Handle
0x18007e72f  call    cs:__imp_NtQuerySecurityObject
0x18007e735  test    eax, eax
0x18007e737  js      short loc_18007E762
0x18007e739  mov     eax, 0C0000001h
0x18007e73e  mov     ecx, eax; int
0x18007e740  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18007e745  mov     rcx, [rbp+18h]; void *
0x18007e749  test    eax, eax
0x18007e74b  jns     short loc_18007E76D
0x18007e74d  mov     r9d, eax; char *
0x18007e750  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007e757  mov     edx, 0C82h; void *
0x18007e75c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e762  cmp     eax, 0C0000023h
0x18007e767  jnz     short loc_18007E73E
0x18007e769  xor     eax, eax
0x18007e76b  jmp     short loc_18007E745
0x18007e76d  mov     [rbp+SecurityDescriptor], 0
0x18007e775  mov     r8d, [rbp+LengthNeeded]; unsigned __int64
0x18007e779  lea     r9, [rbp+SecurityDescriptor]; void **
0x18007e77d  mov     edx, 40h ; '@'; unsigned int
0x18007e782  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18007e787  mov     rcx, [rbp+18h]; this
0x18007e78b  test    eax, eax
0x18007e78d  jns     short loc_18007E7A4
0x18007e78f  mov     r9d, eax; char *
0x18007e792  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007e799  mov     edx, 0C85h; void *
0x18007e79e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e7a4  lea     rax, [rbp+LengthNeeded]
0x18007e7a8  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x18007e7ad  mov     r9d, [rbp+LengthNeeded]; Length
0x18007e7b1  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18007e7b5  mov     edx, ebx; SecurityInformation
0x18007e7b7  mov     rcx, rdi; Handle
0x18007e7ba  call    cs:__imp_NtQuerySecurityObject
0x18007e7c0  mov     ecx, eax; int
0x18007e7c2  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18007e7c7  mov     rcx, [rbp+18h]; this
0x18007e7cb  test    eax, eax
0x18007e7cd  jns     short loc_18007E7E4
0x18007e7cf  mov     r9d, eax; char *
0x18007e7d2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007e7d9  mov     edx, 0C87h; void *
0x18007e7de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e7e4  mov     [rbp+Owner], 0
0x18007e7ec  mov     [rbp+OwnerDefaulted], 0
0x18007e7f0  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x18007e7f4  lea     rdx, [rbp+Owner]; Owner
0x18007e7f8  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18007e7fc  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18007e802  mov     ecx, eax; int
0x18007e804  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18007e809  mov     rcx, [rbp+18h]; this
0x18007e80d  test    eax, eax
0x18007e80f  jns     short loc_18007E826
0x18007e811  mov     r9d, eax; char *
0x18007e814  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007e81b  mov     edx, 0C8Bh; void *
0x18007e820  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e826  mov     [rbp+ServiceSid], 0
0x18007e82e  mov     ecx, 6; SubAuthorityCount
0x18007e833  call    cs:__imp_RtlLengthRequiredSid
0x18007e839  mov     r8d, eax; unsigned __int64
0x18007e83c  mov     [rbp+ServiceSidLength], r8d
0x18007e840  lea     r9, [rbp+ServiceSid]; void **
0x18007e844  mov     edx, 40h ; '@'; unsigned int
0x18007e849  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18007e84e  mov     rcx, [rbp+18h]; this
0x18007e852  test    eax, eax
0x18007e854  jns     short loc_18007E86B
0x18007e856  mov     r9d, eax; char *
0x18007e859  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007e860  mov     edx, 0C91h; void *
0x18007e865  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e86b  mov     qword ptr [rbp+ServiceName.Length], 220020h
0x18007e873  lea     rax, aTrustedinstall; "TrustedInstaller"
0x18007e87a  mov     [rbp+ServiceName.Buffer], rax
0x18007e87e  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x18007e882  mov     rdx, [rbp+ServiceSid]; ServiceSid
0x18007e886  lea     rcx, [rbp+ServiceName]; ServiceName
0x18007e88a  call    cs:__imp_RtlCreateServiceSid
0x18007e890  mov     ecx, eax; int
0x18007e892  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18007e897  mov     rcx, [rbp+18h]; this
0x18007e89b  test    eax, eax
0x18007e89d  jns     short loc_18007E8B4
0x18007e89f  mov     r9d, eax; char *
0x18007e8a2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007e8a9  mov     edx, 0C94h; void *
0x18007e8ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e8b4  mov     rdx, [rbp+ServiceSid]; Sid2
0x18007e8b8  mov     rcx, [rbp+Owner]; Sid1
0x18007e8bc  call    cs:__imp_RtlEqualSid
0x18007e8c2  test    al, al
0x18007e8c4  setnz   bl
0x18007e8c7  mov     rcx, rdi; hObject
0x18007e8ca  call    cs:__imp_CloseHandle
0x18007e8d0  nop
0x18007e8d1  lea     rcx, [rbp+ServiceSid]
0x18007e8d5  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x18007e8da  nop
0x18007e8db  lea     rcx, [rbp+SecurityDescriptor]
0x18007e8df  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x18007e8e4  mov     al, bl
0x18007e8e6  add     rsp, 70h
0x18007e8ea  pop     rdi
0x18007e8eb  pop     rbx
0x18007e8ec  pop     rbp
0x18007e8ed  retn
```
