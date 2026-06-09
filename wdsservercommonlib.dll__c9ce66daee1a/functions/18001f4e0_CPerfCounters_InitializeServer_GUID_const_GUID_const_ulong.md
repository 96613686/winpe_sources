# CPerfCounters::InitializeServer(_GUID const &,_GUID const &,ulong)

- ea: `0x18001f4e0`
- end: `0x18001f628`
- name: `?InitializeServer@CPerfCounters@@QEAAKAEBU_GUID@@0K@Z`
- size: `328`
- prototype: `unsigned int __fastcall(CPerfCounters *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001eeb0`
- `0x18001f020`
- `0x18001f4e0`
- `0x18001f7f0`
- `0x18002e468`
- `0x18002f3ba`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f595`
- `KERNEL32!GetLastError` at `0x18001f595`
- `KERNEL32!LocalFree` at `0x18001f5f3`
- `KERNEL32!LocalFree` at `0x18001f5f3`
- `KERNEL32!MapViewOfFile` at `0x18001f5b7`
- `KERNEL32!MapViewOfFile` at `0x18001f5b7`
- `KERNEL32!CreateFileMappingW` at `0x18001f581`
- `KERNEL32!CreateFileMappingW` at `0x18001f581`

## pseudocode

```c
__int64 __fastcall CPerfCounters::InitializeServer(
        CPerfCounters *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        int a4)
{
  size_t dwMaximumSizeLow; // r14
  DWORD LastError; // ebx
  unsigned int ObjectName; // eax
  WCHAR *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rax
  HLOCAL hMem; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpName; // [rsp+38h] [rbp-28h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+40h] [rbp-20h] BYREF

  lpName = 0;
  dwMaximumSizeLow = (unsigned int)(8 * a4);
  hMem = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  LastError = CPerfCounters::BuildSecureSD(this, &hMem);
  if ( !LastError )
  {
    *(&FileMappingAttributes.nLength + 1) = 0;
    *(&FileMappingAttributes.bInheritHandle + 1) = 0;
    FileMappingAttributes.bInheritHandle = 0;
    FileMappingAttributes.lpSecurityDescriptor = hMem;
    FileMappingAttributes.nLength = 24;
    ObjectName = CPerfCounters::CreateObjectName(this, a3, (unsigned __int16 **)&lpName);
    v10 = (WCHAR *)lpName;
    LastError = ObjectName;
    if ( !ObjectName )
    {
      v11 = CreateFileMappingW(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &FileMappingAttributes,
              0x8000004u,
              0,
              dwMaximumSizeLow,
              lpName);
      *(_QWORD *)this = v11;
      if ( v11 && (v12 = MapViewOfFile(v11, 6u, 0, 0, dwMaximumSizeLow), (*((_QWORD *)this + 1) = v12) != 0) )
      {
        memset_0(v12, 0, dwMaximumSizeLow);
        *((_DWORD *)this + 6) = a4;
      }
      else
      {
        LastError = GetLastError();
      }
    }
    if ( v10 )
      operator delete(v10);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( LastError )
    CPerfCounters::Shutdown(this);
  return LastError;
}

```

## disassembly

```asm
0x18001f4e0  mov     [rsp-18h+arg_0], rbx
0x18001f4e5  mov     [rsp-18h+arg_8], rsi
0x18001f4ea  mov     [rsp-18h+arg_10], rdi
0x18001f4ef  push    rbp
0x18001f4f0  push    r14
0x18001f4f2  push    r15
0x18001f4f4  mov     rbp, rsp
0x18001f4f7  sub     rsp, 60h
0x18001f4fb  and     [rbp+var_28], 0
0x18001f500  lea     rdx, [rbp+hMem]; void **
0x18001f504  xor     eax, eax
0x18001f506  lea     r14d, ds:0[r9*8]
0x18001f50e  and     [rbp+hMem], rax
0x18001f512  xorps   xmm0, xmm0
0x18001f515  movups  xmmword ptr [rbp+FileMappingAttributes.nLength], xmm0
0x18001f519  mov     qword ptr [rbp+FileMappingAttributes.bInheritHandle], rax
0x18001f51d  mov     r15d, r9d
0x18001f520  mov     rsi, r8
0x18001f523  mov     rdi, rcx
0x18001f526  call    ?BuildSecureSD@CPerfCounters@@IEAAKPEAPEAX@Z; CPerfCounters::BuildSecureSD(void * *)
0x18001f52b  mov     ebx, eax
0x18001f52d  test    eax, eax
0x18001f52f  jnz     loc_18001F5EA
0x18001f535  and     dword ptr [rbp+FileMappingAttributes+4], eax
0x18001f538  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18001f53c  and     dword ptr [rbp+FileMappingAttributes+14h], eax
0x18001f53f  mov     rdx, rsi; struct _GUID *
0x18001f542  and     [rbp+FileMappingAttributes.bInheritHandle], eax
0x18001f545  mov     rcx, rdi; this
0x18001f548  mov     rax, [rbp+hMem]
0x18001f54c  mov     [rbp+FileMappingAttributes.lpSecurityDescriptor], rax
0x18001f550  mov     [rbp+FileMappingAttributes.nLength], 18h
0x18001f557  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x18001f55c  mov     rsi, [rbp+var_28]
0x18001f560  mov     ebx, eax
0x18001f562  test    eax, eax
0x18001f564  jnz     short loc_18001F5DD
0x18001f566  mov     [rsp+60h+lpName], rsi; lpName
0x18001f56b  lea     rdx, [rbp+FileMappingAttributes]; lpFileMappingAttributes
0x18001f56f  xor     r9d, r9d; dwMaximumSizeHigh
0x18001f572  mov     [rsp+60h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x18001f577  mov     r8d, 8000004h; flProtect
0x18001f57d  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001f581  call    cs:__imp_CreateFileMappingW
0x18001f588  nop     dword ptr [rax+rax+00h]
0x18001f58d  mov     [rdi], rax
0x18001f590  test    rax, rax
0x18001f593  jnz     short loc_18001F5A5
0x18001f595  call    cs:__imp_GetLastError
0x18001f59c  nop     dword ptr [rax+rax+00h]
0x18001f5a1  mov     ebx, eax
0x18001f5a3  jmp     short loc_18001F5DD
0x18001f5a5  xor     r9d, r9d; dwFileOffsetLow
0x18001f5a8  mov     qword ptr [rsp+60h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x18001f5ad  xor     r8d, r8d; dwFileOffsetHigh
0x18001f5b0  mov     rcx, rax; hFileMappingObject
0x18001f5b3  lea     edx, [r9+6]; dwDesiredAccess
0x18001f5b7  call    cs:__imp_MapViewOfFile
0x18001f5be  nop     dword ptr [rax+rax+00h]
0x18001f5c3  mov     [rdi+8], rax
0x18001f5c7  test    rax, rax
0x18001f5ca  jz      short loc_18001F595
0x18001f5cc  mov     r8, r14; Size
0x18001f5cf  xor     edx, edx; Val
0x18001f5d1  mov     rcx, rax; void *
0x18001f5d4  call    memset_0
0x18001f5d9  mov     [rdi+18h], r15d
0x18001f5dd  test    rsi, rsi
0x18001f5e0  jz      short loc_18001F5EA
0x18001f5e2  mov     rcx, rsi; lpMem
0x18001f5e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f5ea  mov     rcx, [rbp+hMem]; hMem
0x18001f5ee  test    rcx, rcx
0x18001f5f1  jz      short loc_18001F5FF
0x18001f5f3  call    cs:__imp_LocalFree
0x18001f5fa  nop     dword ptr [rax+rax+00h]
0x18001f5ff  test    ebx, ebx
0x18001f601  jz      short loc_18001F60B
0x18001f603  mov     rcx, rdi; this
0x18001f606  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x18001f60b  lea     r11, [rsp+60h+var_s0]
0x18001f610  mov     eax, ebx
0x18001f612  mov     rbx, [r11+20h]
0x18001f616  mov     rsi, [r11+28h]
0x18001f61a  mov     rdi, [r11+30h]
0x18001f61e  mov     rsp, r11
0x18001f621  pop     r15
0x18001f623  pop     r14
0x18001f625  pop     rbp
0x18001f626  retn
```
