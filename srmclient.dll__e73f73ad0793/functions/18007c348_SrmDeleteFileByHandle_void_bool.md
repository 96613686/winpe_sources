# SrmDeleteFileByHandle(void *,bool)

- ea: `0x18007c348`
- end: `0x18007c455`
- name: `?SrmDeleteFileByHandle@@YAXPEAX_N@Z`
- size: `269`
- prototype: `void __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005b2a8`

## callees

- `0x18006febc`
- `0x1800700b8`
- `0x180073f54`
- `0x18007c348`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007c3fb`
- `KERNEL32!GetLastError` at `0x18007c3fb`
- `KERNEL32!SetFileInformationByHandle` at `0x18007c3f1`
- `KERNEL32!SetFileInformationByHandle` at `0x18007c3f1`

## string_xrefs

- `0x18007c37b`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007c393`: `SRMPATHC`
- `0x18007c387`: `SrmDeleteFileByHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SrmDeleteFileByHandle(HANDLE hFile)
{
  DWORD LastError; // [rsp+20h] [rbp-E0h]
  char FileInformation[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v4; // [rsp+38h] [rbp-C8h]
  _QWORD v5[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v6; // [rsp+60h] [rbp-A0h]
  _BYTE v7[96]; // [rsp+68h] [rbp-98h] BYREF
  int v8; // [rsp+C8h] [rbp-38h]
  _QWORD v9[22]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = v5;
  v5[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v5[1] = L"SrmDeleteFileByHandle";
  v5[2] = L"SRMPATHC";
  v5[3] = 1582;
  v6 = 255;
  v8 = 0x1000000;
  memset_0(v7, 0, sizeof(v7));
  CSrmFunctionTracer::CSrmFunctionTracer(v9, v5, 0);
  FileInformation[0] = 1;
  if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, FileInformation, 1u) )
  {
    LastError = GetLastError();
    CSrmFunctionTracer::Trace((CSrmFunctionTracer *)v9, 0x8Cu, 0x63Eu, L"Failed to close handle, error %ld", LastError);
  }
  v9[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v9);
}

```

## disassembly

```asm
0x18007c348  mov     [rsp-8+arg_8], rbx
0x18007c34d  push    rbp
0x18007c34e  lea     rbp, [rsp-90h]
0x18007c356  sub     rsp, 190h
0x18007c35d  mov     rax, cs:__security_cookie
0x18007c364  xor     rax, rsp
0x18007c367  mov     [rbp+90h+var_10], rax
0x18007c36e  mov     rbx, rcx
0x18007c371  lea     rax, [rsp+190h+var_150]
0x18007c376  mov     [rsp+190h+var_158], rax
0x18007c37b  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007c382  mov     [rsp+190h+var_150], rax
0x18007c387  lea     rax, aSrmdeletefileb; "SrmDeleteFileByHandle"
0x18007c38e  mov     [rsp+190h+var_148], rax
0x18007c393  lea     rax, aSrmpathc; "SRMPATHC"
0x18007c39a  mov     [rsp+190h+var_140], rax
0x18007c39f  mov     [rsp+190h+var_138], 62Eh
0x18007c3a8  mov     [rsp+190h+var_130], 0FFh
0x18007c3b0  mov     [rbp+90h+var_C8], 1000000h
0x18007c3b7  xor     edx, edx; Val
0x18007c3b9  lea     r8d, [rdx+60h]; Size
0x18007c3bd  lea     rcx, [rsp+190h+var_128]; void *
0x18007c3c2  call    memset_0
0x18007c3c7  nop
0x18007c3c8  xor     r8d, r8d
0x18007c3cb  lea     rdx, [rsp+190h+var_150]
0x18007c3d0  lea     rcx, [rbp+90h+var_C0]
0x18007c3d4  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007c3d9  nop
0x18007c3da  mov     [rsp+190h+FileInformation], 1
0x18007c3df  mov     r9d, 1; dwBufferSize
0x18007c3e5  lea     r8, [rsp+190h+FileInformation]; lpFileInformation
0x18007c3ea  lea     edx, [r9+3]; FileInformationClass
0x18007c3ee  mov     rcx, rbx; hFile
0x18007c3f1  call    cs:__imp_SetFileInformationByHandle
0x18007c3f7  test    eax, eax
0x18007c3f9  jnz     short loc_18007C421
0x18007c3fb  call    cs:__imp_GetLastError
0x18007c401  mov     [rsp+190h+var_170], eax
0x18007c405  lea     r9, aFailedToCloseH; "Failed to close handle, error %ld"
0x18007c40c  mov     edx, 8Ch; unsigned int
0x18007c411  mov     r8d, 63Eh; unsigned int
0x18007c417  lea     rcx, [rbp+90h+var_C0]; this
0x18007c41b  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18007c420  nop
0x18007c421  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007c428  mov     [rbp+90h+var_C0], rax
0x18007c42c  lea     rcx, [rbp+90h+var_C0]; this
0x18007c430  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007c435  mov     rcx, [rbp+90h+var_10]
0x18007c43c  xor     rcx, rsp; StackCookie
0x18007c43f  call    __security_check_cookie
0x18007c444  mov     rbx, [rsp+190h+arg_8]
0x18007c44c  add     rsp, 190h
0x18007c453  pop     rbp
0x18007c454  retn
```
