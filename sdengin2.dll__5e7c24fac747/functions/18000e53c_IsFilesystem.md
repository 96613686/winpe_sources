# IsFilesystem

- ea: `0x18000e53c`
- end: `0x18000e773`
- name: `IsFilesystem`
- size: `567`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, wchar_t *String2)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18000e77c`
- `0x18000e848`

## callees

- `0x18000e53c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e6fd`
- `msvcrt!_wcsicmp` at `0x18000e6fd`
- `ntdll!RtlSetThreadErrorMode` at `0x18000e624`
- `ntdll!RtlSetThreadErrorMode` at `0x18000e724`
- `ntdll!RtlSetThreadErrorMode` at `0x18000e624`
- `ntdll!RtlSetThreadErrorMode` at `0x18000e724`
- `ntdll!RtlGetThreadErrorMode` at `0x18000e614`
- `ntdll!RtlGetThreadErrorMode` at `0x18000e614`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000e6d0`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000e6d0`
- `KERNEL32!CreateFileW` at `0x18000e674`
- `KERNEL32!CreateFileW` at `0x18000e674`
- `KERNEL32!CloseHandle` at `0x18000e70f`
- `KERNEL32!CloseHandle` at `0x18000e73b`
- `KERNEL32!CloseHandle` at `0x18000e70f`
- `KERNEL32!CloseHandle` at `0x18000e73b`

## pseudocode

```c
__int64 __fastcall IsFilesystem(LPCWSTR lpFileName, wchar_t *String2, _DWORD *a3)
{
  unsigned int v6; // edi
  __int16 v7; // ax
  ULONG ThreadErrorMode; // r14d
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 FileW; // rbx
  unsigned int v12; // eax
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v15; // [rsp+44h] [rbp-BCh]
  __int16 v16; // [rsp+46h] [rbp-BAh]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  int FsInformation; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v19[8]; // [rsp+94h] [rbp-6Ch] BYREF
  wchar_t String1[266]; // [rsp+9Ch] [rbp-64h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "IsFilesystem", 528, 1);
  IoStatusBlock = 0;
  FsInformation = 0;
  memset_0(v19, 0, 0x214u);
  if ( a3 )
    *a3 = 0;
  if ( !lpFileName )
  {
    v6 = -2147024809;
    LastFailureAsHRESULT = -2147024809;
    v16 = 536;
    goto LABEL_22;
  }
  v15 = 536;
  v7 = 537;
  if ( !String2 || (v15 = 537, v7 = 538, !a3) )
  {
    v6 = -2147024809;
    LastFailureAsHRESULT = -2147024809;
    v16 = v7;
    goto LABEL_22;
  }
  LastFailureAsHRESULT = 0;
  v15 = 538;
  ThreadErrorMode = RtlGetThreadErrorMode();
  v9 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, 0);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v9);
  if ( LastFailureAsHRESULT < 0 )
  {
    v16 = 544;
LABEL_17:
    FileW = -1;
    goto LABEL_18;
  }
  v15 = 544;
  FileW = (__int64)CreateFileW(lpFileName, 0x1000A0u, 3u, 0, 3u, 0, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    LastFailureAsHRESULT = 0;
    v15 = 558;
    v12 = NtQueryVolumeInformationFile(
            (HANDLE)FileW,
            &IoStatusBlock,
            &FsInformation,
            0x218u,
            FileFsAttributeInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v12);
    if ( LastFailureAsHRESULT >= 0 )
    {
      v15 = 564;
      *a3 = _wcsicmp(String1, String2) == 0;
    }
    else
    {
      v16 = 564;
    }
    goto LABEL_16;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
  v16 = 558;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_16:
    CloseHandle((HANDLE)FileW);
    goto LABEL_17;
  }
LABEL_18:
  if ( ThreadErrorMode != -1 )
    RtlSetThreadErrorMode(ThreadErrorMode, 0);
  v6 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
LABEL_22:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v6;
}

```

## disassembly

```asm
0x18000e53c  mov     [rsp-8+arg_18], rbx
0x18000e541  push    rbp
0x18000e542  push    rsi
0x18000e543  push    rdi
0x18000e544  push    r14
0x18000e546  push    r15
0x18000e548  lea     rbp, [rsp-1C0h]
0x18000e550  sub     rsp, 2C0h
0x18000e557  mov     rax, cs:__security_cookie
0x18000e55e  xor     rax, rsp
0x18000e561  mov     [rbp+1E0h+var_30], rax
0x18000e568  mov     rdi, r8
0x18000e56b  mov     r15, rdx
0x18000e56e  mov     rbx, rcx
0x18000e571  mov     r9d, 1; unsigned __int16
0x18000e577  mov     r8d, 210h; unsigned __int16
0x18000e57d  lea     rdx, aIsfilesystem; "IsFilesystem"
0x18000e584  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000e589  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e58e  xorps   xmm0, xmm0
0x18000e591  movups  xmmword ptr [rsp+2E0h+IoStatusBlock], xmm0
0x18000e596  mov     [rbp+1E0h+FsInformation], 0
0x18000e59d  xor     edx, edx; Val
0x18000e59f  mov     r8d, 214h; Size
0x18000e5a5  lea     rcx, [rbp+1E0h+var_24C]; void *
0x18000e5a9  call    memset_0
0x18000e5ae  test    rdi, rdi
0x18000e5b1  jz      short loc_18000E5B9
0x18000e5b3  mov     dword ptr [rdi], 0
0x18000e5b9  mov     esi, 218h
0x18000e5be  test    rbx, rbx
0x18000e5c1  jnz     short loc_18000E5D6
0x18000e5c3  mov     edi, 80070057h
0x18000e5c8  mov     [rsp+2E0h+var_2A0], edi
0x18000e5cc  mov     [rsp+2E0h+var_29A], si
0x18000e5d1  jmp     loc_18000E741
0x18000e5d6  mov     [rsp+2E0h+var_29C], si
0x18000e5db  mov     eax, 219h
0x18000e5e0  test    r15, r15
0x18000e5e3  jnz     short loc_18000E5F8
0x18000e5e5  mov     edi, 80070057h
0x18000e5ea  mov     [rsp+2E0h+var_2A0], edi
0x18000e5ee  mov     [rsp+2E0h+var_29A], ax
0x18000e5f3  jmp     loc_18000E741
0x18000e5f8  mov     [rsp+2E0h+var_29C], ax
0x18000e5fd  mov     eax, 21Ah
0x18000e602  test    rdi, rdi
0x18000e605  jz      short loc_18000E5E5
0x18000e607  mov     [rsp+2E0h+var_2A0], 0
0x18000e60f  mov     [rsp+2E0h+var_29C], ax
0x18000e614  call    cs:__imp_RtlGetThreadErrorMode
0x18000e61a  mov     r14d, eax
0x18000e61d  mov     ecx, eax
0x18000e61f  or      ecx, 10h; NewMode
0x18000e622  xor     edx, edx; OldMode
0x18000e624  call    cs:__imp_RtlSetThreadErrorMode
0x18000e62a  mov     ecx, eax
0x18000e62c  call    HRESULTFromNTSTATUS
0x18000e631  mov     [rsp+2E0h+var_2A0], eax
0x18000e635  test    eax, eax
0x18000e637  mov     eax, 220h
0x18000e63c  jns     short loc_18000E648
0x18000e63e  mov     [rsp+2E0h+var_29A], ax
0x18000e643  jmp     loc_18000E715
0x18000e648  mov     [rsp+2E0h+var_29C], ax
0x18000e64d  mov     [rsp+2E0h+hTemplateFile], 0; hTemplateFile
0x18000e656  mov     [rsp+2E0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000e65e  mov     r8d, 3; dwShareMode
0x18000e664  mov     [rsp+2E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000e669  xor     r9d, r9d; lpSecurityAttributes
0x18000e66c  mov     edx, 1000A0h; dwDesiredAccess
0x18000e671  mov     rcx, rbx; lpFileName
0x18000e674  call    cs:__imp_CreateFileW
0x18000e67a  mov     rbx, rax
0x18000e67d  inc     rax
0x18000e680  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e686  jnz     short loc_18000E6A7
0x18000e688  call    GetLastFailureAsHRESULT
0x18000e68d  mov     [rsp+2E0h+var_2A0], eax
0x18000e691  mov     eax, 22Eh
0x18000e696  mov     [rsp+2E0h+var_29A], ax
0x18000e69b  lea     rax, [rbx-1]
0x18000e69f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e6a3  ja      short loc_18000E719
0x18000e6a5  jmp     short loc_18000E70C
0x18000e6a7  mov     [rsp+2E0h+var_2A0], 0
0x18000e6af  mov     eax, 22Eh
0x18000e6b4  mov     [rsp+2E0h+var_29C], ax
0x18000e6b9  mov     [rsp+2E0h+dwCreationDisposition], 5; FsInformationClass
0x18000e6c1  mov     r9d, esi; Length
0x18000e6c4  lea     r8, [rbp+1E0h+FsInformation]; FsInformation
0x18000e6c8  lea     rdx, [rsp+2E0h+IoStatusBlock]; IoStatusBlock
0x18000e6cd  mov     rcx, rbx; FileHandle
0x18000e6d0  call    cs:__imp_NtQueryVolumeInformationFile
0x18000e6d6  mov     ecx, eax
0x18000e6d8  call    HRESULTFromNTSTATUS
0x18000e6dd  mov     [rsp+2E0h+var_2A0], eax
0x18000e6e1  test    eax, eax
0x18000e6e3  mov     eax, 234h
0x18000e6e8  jns     short loc_18000E6F1
0x18000e6ea  mov     [rsp+2E0h+var_29A], ax
0x18000e6ef  jmp     short loc_18000E70C
0x18000e6f1  mov     [rsp+2E0h+var_29C], ax
0x18000e6f6  mov     rdx, r15; String2
0x18000e6f9  lea     rcx, [rbp+1E0h+String1]; String1
0x18000e6fd  call    cs:__imp__wcsicmp
0x18000e703  xor     ecx, ecx
0x18000e705  test    eax, eax
0x18000e707  setz    cl
0x18000e70a  mov     [rdi], ecx
0x18000e70c  mov     rcx, rbx; hObject
0x18000e70f  call    cs:__imp_CloseHandle
0x18000e715  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e719  cmp     r14d, 0FFFFFFFFh
0x18000e71d  jz      short loc_18000E72A
0x18000e71f  xor     edx, edx; OldMode
0x18000e721  mov     ecx, r14d; NewMode
0x18000e724  call    cs:__imp_RtlSetThreadErrorMode
0x18000e72a  mov     edi, [rsp+2E0h+var_2A0]
0x18000e72e  lea     rcx, [rbx-1]
0x18000e732  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000e736  ja      short loc_18000E741
0x18000e738  mov     rcx, rbx; hObject
0x18000e73b  call    cs:__imp_CloseHandle
0x18000e741  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000e746  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e74b  mov     eax, edi
0x18000e74d  mov     rcx, [rbp+1E0h+var_30]
0x18000e754  xor     rcx, rsp; StackCookie
0x18000e757  call    __security_check_cookie
0x18000e75c  mov     rbx, [rsp+2E0h+arg_18]
0x18000e764  add     rsp, 2C0h
0x18000e76b  pop     r15
0x18000e76d  pop     r14
0x18000e76f  pop     rdi
0x18000e770  pop     rsi
0x18000e771  pop     rbp
0x18000e772  retn
```
