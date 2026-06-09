# CMulticastPerfCounters::InitializeServer(void)

- ea: `0x1800092cc`
- end: `0x1800093eb`
- name: `?InitializeServer@CMulticastPerfCounters@@QEAAKXZ`
- size: `287`
- prototype: `unsigned int __fastcall(CMulticastPerfCounters *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800053a0`

## callees

- `0x1800092cc`
- `0x18001a9a8`
- `0x1800228e8`
- `0x18002294c`
- `0x180026d46`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009305`
- `KERNEL32!GetLastError` at `0x180009370`
- `KERNEL32!GetLastError` at `0x180009305`
- `KERNEL32!GetLastError` at `0x180009370`
- `KERNEL32!CreateFileMappingW` at `0x180009362`
- `KERNEL32!CreateFileMappingW` at `0x180009362`
- `KERNEL32!MapViewOfFile` at `0x180009390`
- `KERNEL32!MapViewOfFile` at `0x180009390`
- `KERNEL32!LocalFree` at `0x1800093ca`
- `KERNEL32!LocalFree` at `0x1800093ca`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800092fb`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800092fb`

## pseudocode

```c
__int64 __fastcall CMulticastPerfCounters::InitializeServer(CMulticastPerfCounters *this)
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
    *(_QWORD *)&FileMappingAttributes.bInheritHandle = 0;
    *(&FileMappingAttributes.nLength + 1) = 0;
    FileMappingAttributes.lpSecurityDescriptor = SecurityDescriptor;
    FileMappingAttributes.nLength = 24;
    ObjectName = CPerfCounters::CreateObjectName(v4, v3, (unsigned __int16 **)&lpName);
    v6 = (WCHAR *)lpName;
    LastError = ObjectName;
    if ( !ObjectName )
    {
      v7 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 0x8000004u, 0, 0x70u, lpName);
      *(_QWORD *)this = v7;
      if ( v7 && (v8 = MapViewOfFile(v7, 6u, 0, 0, 0x70u), (*((_QWORD *)this + 1) = v8) != 0) )
      {
        memset_0(v8, 0, 0x70u);
        *((_DWORD *)this + 6) = 14;
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
0x1800092cc  mov     [rsp-18h+arg_0], rbx
0x1800092d1  push    rbp
0x1800092d2  push    rsi
0x1800092d3  push    rdi
0x1800092d4  mov     rbp, rsp
0x1800092d7  sub     rsp, 50h
0x1800092db  and     [rbp+arg_10], 0
0x1800092e0  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800092e4  and     [rbp+SecurityDescriptor], 0
0x1800092e9  mov     rsi, rcx
0x1800092ec  xor     ebx, ebx
0x1800092ee  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;LU)("...
0x1800092f5  xor     r9d, r9d; SecurityDescriptorSize
0x1800092f8  lea     edx, [rbx+1]; StringSDRevision
0x1800092fb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180009301  test    eax, eax
0x180009303  jnz     short loc_18000930D
0x180009305  call    cs:__imp_GetLastError
0x18000930b  mov     ebx, eax
0x18000930d  test    ebx, ebx
0x18000930f  jnz     loc_1800093C1
0x180009315  xor     eax, eax
0x180009317  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18000931b  mov     qword ptr [rbp+FileMappingAttributes.bInheritHandle], rax
0x18000931f  and     [rbp+FileMappingAttributes.bInheritHandle], eax
0x180009322  mov     qword ptr [rbp+FileMappingAttributes.nLength], rax
0x180009326  mov     rax, [rbp+SecurityDescriptor]
0x18000932a  mov     [rbp+FileMappingAttributes.lpSecurityDescriptor], rax
0x18000932e  mov     [rbp+FileMappingAttributes.nLength], 18h
0x180009335  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x18000933a  mov     rdi, [rbp+arg_10]
0x18000933e  mov     ebx, eax
0x180009340  test    eax, eax
0x180009342  jnz     short loc_1800093B4
0x180009344  mov     [rsp+50h+lpName], rdi; lpName
0x180009349  lea     rdx, [rbp+FileMappingAttributes]; lpFileMappingAttributes
0x18000934d  xor     r9d, r9d; dwMaximumSizeHigh
0x180009350  mov     [rsp+50h+dwMaximumSizeLow], 70h ; 'p'; dwMaximumSizeLow
0x180009358  mov     r8d, 8000004h; flProtect
0x18000935e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180009362  call    cs:__imp_CreateFileMappingW
0x180009368  mov     [rsi], rax
0x18000936b  test    rax, rax
0x18000936e  jnz     short loc_18000937A
0x180009370  call    cs:__imp_GetLastError
0x180009376  mov     ebx, eax
0x180009378  jmp     short loc_1800093B4
0x18000937a  xor     r9d, r9d; dwFileOffsetLow
0x18000937d  mov     qword ptr [rsp+50h+dwMaximumSizeLow], 70h ; 'p'; dwNumberOfBytesToMap
0x180009386  xor     r8d, r8d; dwFileOffsetHigh
0x180009389  mov     rcx, rax; hFileMappingObject
0x18000938c  lea     edx, [r9+6]; dwDesiredAccess
0x180009390  call    cs:__imp_MapViewOfFile
0x180009396  mov     [rsi+8], rax
0x18000939a  test    rax, rax
0x18000939d  jz      short loc_180009370
0x18000939f  xor     edx, edx; Val
0x1800093a1  mov     rcx, rax; void *
0x1800093a4  lea     r8d, [rdx+70h]; Size
0x1800093a8  call    memset_0
0x1800093ad  mov     dword ptr [rsi+18h], 0Eh
0x1800093b4  test    rdi, rdi
0x1800093b7  jz      short loc_1800093C1
0x1800093b9  mov     rcx, rdi; void *
0x1800093bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800093c1  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800093c5  test    rcx, rcx
0x1800093c8  jz      short loc_1800093D0
0x1800093ca  call    cs:__imp_LocalFree
0x1800093d0  test    ebx, ebx
0x1800093d2  jz      short loc_1800093DC
0x1800093d4  mov     rcx, rsi; this
0x1800093d7  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x1800093dc  mov     eax, ebx
0x1800093de  mov     rbx, [rsp+50h+arg_0]
0x1800093e3  add     rsp, 50h
0x1800093e7  pop     rdi
0x1800093e8  pop     rsi
0x1800093e9  pop     rbp
0x1800093ea  retn
```
