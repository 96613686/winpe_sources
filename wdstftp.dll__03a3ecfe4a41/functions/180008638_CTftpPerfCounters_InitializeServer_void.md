# CTftpPerfCounters::InitializeServer(void)

- ea: `0x180008638`
- end: `0x18000877b`
- name: `?InitializeServer@CTftpPerfCounters@@QEAAKXZ`
- size: `323`
- prototype: `unsigned int __fastcall(CTftpPerfCounters *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800012e0`

## callees

- `0x180008638`
- `0x18000a960`
- `0x18003bf9c`
- `0x18003c00c`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180008714`
- `KERNEL32!MapViewOfFile` at `0x180008714`
- `KERNEL32!CreateFileMappingW` at `0x1800086da`
- `KERNEL32!CreateFileMappingW` at `0x1800086da`
- `KERNEL32!GetLastError` at `0x180008677`
- `KERNEL32!GetLastError` at `0x1800086ee`
- `KERNEL32!GetLastError` at `0x180008677`
- `KERNEL32!GetLastError` at `0x1800086ee`
- `KERNEL32!LocalFree` at `0x180008754`
- `KERNEL32!LocalFree` at `0x180008754`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008667`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008667`

## pseudocode

```c
__int64 __fastcall CTftpPerfCounters::InitializeServer(CTftpPerfCounters *this)
{
  DWORD LastError; // ebx
  const struct _GUID *v3; // rdx
  CPerfCounters *v4; // rcx
  unsigned int ObjectName; // eax
  WCHAR *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rax
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+28h] BYREF
  LPCWSTR lpName; // [rsp+80h] [rbp+30h] BYREF

  lpName = 0;
  SecurityDescriptor = 0;
  LastError = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;LU)(A;;GR;;;MU)",
          1u,
          &SecurityDescriptor,
          0) )
    LastError = GetLastError();
  if ( !LastError )
  {
    *(&FileMappingAttributes.nLength + 1) = 0;
    *(&FileMappingAttributes.bInheritHandle + 1) = 0;
    FileMappingAttributes.bInheritHandle = 0;
    FileMappingAttributes.lpSecurityDescriptor = SecurityDescriptor;
    FileMappingAttributes.nLength = 24;
    ObjectName = CPerfCounters::CreateObjectName(v4, v3, (unsigned __int16 **)&lpName);
    v6 = (WCHAR *)lpName;
    LastError = ObjectName;
    if ( !ObjectName )
    {
      v7 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 0x8000004u, 0, 0x48u, lpName);
      *(_QWORD *)this = v7;
      if ( v7 && (v8 = MapViewOfFile(v7, 6u, 0, 0, 0x48u), (*((_QWORD *)this + 1) = v8) != 0) )
      {
        memset_0(v8, 0, 0x48u);
        *((_DWORD *)this + 6) = 9;
      }
      else
      {
        LastError = GetLastError();
      }
    }
    if ( v6 )
      operator delete(v6);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( LastError )
    CPerfCounters::Shutdown(this);
  return LastError;
}

```

## disassembly

```asm
0x180008638  mov     [rsp-18h+arg_0], rbx
0x18000863d  push    rbp
0x18000863e  push    rsi
0x18000863f  push    rdi
0x180008640  mov     rbp, rsp
0x180008643  sub     rsp, 50h
0x180008647  and     [rbp+arg_10], 0
0x18000864c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180008650  and     [rbp+SecurityDescriptor], 0
0x180008655  mov     rsi, rcx
0x180008658  xor     ebx, ebx
0x18000865a  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;LU)("...
0x180008661  xor     r9d, r9d; SecurityDescriptorSize
0x180008664  lea     edx, [rbx+1]; StringSDRevision
0x180008667  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000866e  nop     dword ptr [rax+rax+00h]
0x180008673  test    eax, eax
0x180008675  jnz     short loc_180008685
0x180008677  call    cs:__imp_GetLastError
0x18000867e  nop     dword ptr [rax+rax+00h]
0x180008683  mov     ebx, eax
0x180008685  test    ebx, ebx
0x180008687  jnz     loc_18000874B
0x18000868d  mov     rax, [rbp+SecurityDescriptor]
0x180008691  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x180008695  and     dword ptr [rbp+FileMappingAttributes+4], ebx
0x180008698  and     dword ptr [rbp+FileMappingAttributes+14h], ebx
0x18000869b  and     [rbp+FileMappingAttributes.bInheritHandle], ebx
0x18000869e  mov     [rbp+FileMappingAttributes.lpSecurityDescriptor], rax
0x1800086a2  mov     [rbp+FileMappingAttributes.nLength], 18h
0x1800086a9  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x1800086ae  mov     rdi, [rbp+arg_10]
0x1800086b2  mov     ebx, eax
0x1800086b4  test    eax, eax
0x1800086b6  jnz     loc_18000873E
0x1800086bc  mov     [rsp+50h+lpName], rdi; lpName
0x1800086c1  lea     rdx, [rbp+FileMappingAttributes]; lpFileMappingAttributes
0x1800086c5  xor     r9d, r9d; dwMaximumSizeHigh
0x1800086c8  mov     [rsp+50h+dwMaximumSizeLow], 48h ; 'H'; dwMaximumSizeLow
0x1800086d0  mov     r8d, 8000004h; flProtect
0x1800086d6  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800086da  call    cs:__imp_CreateFileMappingW
0x1800086e1  nop     dword ptr [rax+rax+00h]
0x1800086e6  mov     [rsi], rax
0x1800086e9  test    rax, rax
0x1800086ec  jnz     short loc_1800086FE
0x1800086ee  call    cs:__imp_GetLastError
0x1800086f5  nop     dword ptr [rax+rax+00h]
0x1800086fa  mov     ebx, eax
0x1800086fc  jmp     short loc_18000873E
0x1800086fe  xor     r9d, r9d; dwFileOffsetLow
0x180008701  mov     qword ptr [rsp+50h+dwMaximumSizeLow], 48h ; 'H'; dwNumberOfBytesToMap
0x18000870a  xor     r8d, r8d; dwFileOffsetHigh
0x18000870d  mov     rcx, rax; hFileMappingObject
0x180008710  lea     edx, [r9+6]; dwDesiredAccess
0x180008714  call    cs:__imp_MapViewOfFile
0x18000871b  nop     dword ptr [rax+rax+00h]
0x180008720  mov     [rsi+8], rax
0x180008724  test    rax, rax
0x180008727  jz      short loc_1800086EE
0x180008729  xor     edx, edx; Val
0x18000872b  mov     rcx, rax; void *
0x18000872e  lea     r8d, [rdx+48h]; Size
0x180008732  call    memset_0
0x180008737  mov     dword ptr [rsi+18h], 9
0x18000873e  test    rdi, rdi
0x180008741  jz      short loc_18000874B
0x180008743  mov     rcx, rdi; void *
0x180008746  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000874b  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000874f  test    rcx, rcx
0x180008752  jz      short loc_180008760
0x180008754  call    cs:__imp_LocalFree
0x18000875b  nop     dword ptr [rax+rax+00h]
0x180008760  test    ebx, ebx
0x180008762  jz      short loc_18000876C
0x180008764  mov     rcx, rsi; this
0x180008767  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x18000876c  mov     eax, ebx
0x18000876e  mov     rbx, [rsp+50h+arg_0]
0x180008773  add     rsp, 50h
0x180008777  pop     rdi
0x180008778  pop     rsi
0x180008779  pop     rbp
0x18000877a  retn
```
