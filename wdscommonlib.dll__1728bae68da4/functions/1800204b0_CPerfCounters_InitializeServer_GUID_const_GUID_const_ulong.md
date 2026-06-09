# CPerfCounters::InitializeServer(_GUID const &,_GUID const &,ulong)

- ea: `0x1800204b0`
- end: `0x1800205ff`
- name: `?InitializeServer@CPerfCounters@@QEAAKAEBU_GUID@@0K@Z`
- size: `335`
- prototype: `unsigned int __fastcall(CPerfCounters *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001fe80`
- `0x18001fff0`
- `0x1800204b0`
- `0x1800207d0`
- `0x180030362`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800205b5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800205b5`
- `KERNEL32!GetLastError` at `0x180020565`
- `KERNEL32!GetLastError` at `0x180020565`
- `KERNEL32!LocalFree` at `0x1800205ca`
- `KERNEL32!LocalFree` at `0x1800205ca`
- `KERNEL32!MapViewOfFile` at `0x180020587`
- `KERNEL32!MapViewOfFile` at `0x180020587`
- `KERNEL32!CreateFileMappingW` at `0x180020551`
- `KERNEL32!CreateFileMappingW` at `0x180020551`

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
0x1800204b0  mov     [rsp-18h+arg_0], rbx
0x1800204b5  mov     [rsp-18h+arg_8], rsi
0x1800204ba  mov     [rsp-18h+arg_10], rdi
0x1800204bf  push    rbp
0x1800204c0  push    r14
0x1800204c2  push    r15
0x1800204c4  mov     rbp, rsp
0x1800204c7  sub     rsp, 60h
0x1800204cb  and     [rbp+var_28], 0
0x1800204d0  lea     rdx, [rbp+hMem]; void **
0x1800204d4  xor     eax, eax
0x1800204d6  lea     r14d, ds:0[r9*8]
0x1800204de  and     [rbp+hMem], rax
0x1800204e2  xorps   xmm0, xmm0
0x1800204e5  movups  xmmword ptr [rbp+FileMappingAttributes.nLength], xmm0
0x1800204e9  mov     qword ptr [rbp+FileMappingAttributes.bInheritHandle], rax
0x1800204ed  mov     r15d, r9d
0x1800204f0  mov     rsi, r8
0x1800204f3  mov     rdi, rcx
0x1800204f6  call    ?BuildSecureSD@CPerfCounters@@IEAAKPEAPEAX@Z; CPerfCounters::BuildSecureSD(void * *)
0x1800204fb  mov     ebx, eax
0x1800204fd  test    eax, eax
0x1800204ff  jnz     loc_1800205C1
0x180020505  and     dword ptr [rbp+FileMappingAttributes+4], eax
0x180020508  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18002050c  and     dword ptr [rbp+FileMappingAttributes+14h], eax
0x18002050f  mov     rdx, rsi; struct _GUID *
0x180020512  and     [rbp+FileMappingAttributes.bInheritHandle], eax
0x180020515  mov     rcx, rdi; this
0x180020518  mov     rax, [rbp+hMem]
0x18002051c  mov     [rbp+FileMappingAttributes.lpSecurityDescriptor], rax
0x180020520  mov     [rbp+FileMappingAttributes.nLength], 18h
0x180020527  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x18002052c  mov     rsi, [rbp+var_28]
0x180020530  mov     ebx, eax
0x180020532  test    eax, eax
0x180020534  jnz     short loc_1800205AD
0x180020536  mov     [rsp+60h+lpName], rsi; lpName
0x18002053b  lea     rdx, [rbp+FileMappingAttributes]; lpFileMappingAttributes
0x18002053f  xor     r9d, r9d; dwMaximumSizeHigh
0x180020542  mov     [rsp+60h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x180020547  mov     r8d, 8000004h; flProtect
0x18002054d  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180020551  call    cs:__imp_CreateFileMappingW
0x180020558  nop     dword ptr [rax+rax+00h]
0x18002055d  mov     [rdi], rax
0x180020560  test    rax, rax
0x180020563  jnz     short loc_180020575
0x180020565  call    cs:__imp_GetLastError
0x18002056c  nop     dword ptr [rax+rax+00h]
0x180020571  mov     ebx, eax
0x180020573  jmp     short loc_1800205AD
0x180020575  xor     r9d, r9d; dwFileOffsetLow
0x180020578  mov     qword ptr [rsp+60h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x18002057d  xor     r8d, r8d; dwFileOffsetHigh
0x180020580  mov     rcx, rax; hFileMappingObject
0x180020583  lea     edx, [r9+6]; dwDesiredAccess
0x180020587  call    cs:__imp_MapViewOfFile
0x18002058e  nop     dword ptr [rax+rax+00h]
0x180020593  mov     [rdi+8], rax
0x180020597  test    rax, rax
0x18002059a  jz      short loc_180020565
0x18002059c  mov     r8, r14; Size
0x18002059f  xor     edx, edx; Val
0x1800205a1  mov     rcx, rax; void *
0x1800205a4  call    memset_0
0x1800205a9  mov     [rdi+18h], r15d
0x1800205ad  test    rsi, rsi
0x1800205b0  jz      short loc_1800205C1
0x1800205b2  mov     rcx, rsi
0x1800205b5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800205bc  nop     dword ptr [rax+rax+00h]
0x1800205c1  mov     rcx, [rbp+hMem]; hMem
0x1800205c5  test    rcx, rcx
0x1800205c8  jz      short loc_1800205D6
0x1800205ca  call    cs:__imp_LocalFree
0x1800205d1  nop     dword ptr [rax+rax+00h]
0x1800205d6  test    ebx, ebx
0x1800205d8  jz      short loc_1800205E2
0x1800205da  mov     rcx, rdi; this
0x1800205dd  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x1800205e2  lea     r11, [rsp+60h+var_s0]
0x1800205e7  mov     eax, ebx
0x1800205e9  mov     rbx, [r11+20h]
0x1800205ed  mov     rsi, [r11+28h]
0x1800205f1  mov     rdi, [r11+30h]
0x1800205f5  mov     rsp, r11
0x1800205f8  pop     r15
0x1800205fa  pop     r14
0x1800205fc  pop     rbp
0x1800205fd  retn
```
