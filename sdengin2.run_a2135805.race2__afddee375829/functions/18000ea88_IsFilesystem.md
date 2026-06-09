# IsFilesystem

- ea: `0x18000ea88`
- end: `0x18000ecf4`
- name: `IsFilesystem`
- size: `620`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, wchar_t *String2)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ecfc`
- `0x18000edc8`

## callees

- `0x18000ea88`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ec65`
- `msvcrt!_wcsicmp` at `0x18000ec65`
- `ntdll!RtlSetThreadErrorMode` at `0x18000eb76`
- `ntdll!RtlSetThreadErrorMode` at `0x18000ec98`
- `ntdll!RtlSetThreadErrorMode` at `0x18000eb76`
- `ntdll!RtlSetThreadErrorMode` at `0x18000ec98`
- `ntdll!RtlGetThreadErrorMode` at `0x18000eb60`
- `ntdll!RtlGetThreadErrorMode` at `0x18000eb60`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000ec32`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000ec32`
- `KERNEL32!CreateFileW` at `0x18000ebcc`
- `KERNEL32!CreateFileW` at `0x18000ebcc`
- `KERNEL32!CloseHandle` at `0x18000ec7d`
- `KERNEL32!CloseHandle` at `0x18000ecb5`
- `KERNEL32!CloseHandle` at `0x18000ec7d`
- `KERNEL32!CloseHandle` at `0x18000ecb5`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "IsFilesystem", 0x210u, 1u);
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
0x18000ea88  mov     [rsp-8+arg_18], rbx
0x18000ea8d  push    rbp
0x18000ea8e  push    rsi
0x18000ea8f  push    rdi
0x18000ea90  push    r14
0x18000ea92  push    r15
0x18000ea94  lea     rbp, [rsp-1C0h]
0x18000ea9c  sub     rsp, 2C0h
0x18000eaa3  mov     rax, cs:__security_cookie
0x18000eaaa  xor     rax, rsp
0x18000eaad  mov     [rbp+1E0h+var_30], rax
0x18000eab4  mov     rdi, r8
0x18000eab7  mov     r15, rdx
0x18000eaba  mov     rbx, rcx
0x18000eabd  mov     r9d, 1; unsigned __int16
0x18000eac3  mov     r8d, 210h; unsigned __int16
0x18000eac9  lea     rdx, aIsfilesystem; "IsFilesystem"
0x18000ead0  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000ead5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000eada  xorps   xmm0, xmm0
0x18000eadd  movups  xmmword ptr [rsp+2E0h+IoStatusBlock], xmm0
0x18000eae2  mov     [rbp+1E0h+FsInformation], 0
0x18000eae9  xor     edx, edx; Val
0x18000eaeb  mov     r8d, 214h; Size
0x18000eaf1  lea     rcx, [rbp+1E0h+var_24C]; void *
0x18000eaf5  call    memset_0
0x18000eafa  test    rdi, rdi
0x18000eafd  jz      short loc_18000EB05
0x18000eaff  mov     dword ptr [rdi], 0
0x18000eb05  mov     esi, 218h
0x18000eb0a  test    rbx, rbx
0x18000eb0d  jnz     short loc_18000EB22
0x18000eb0f  mov     edi, 80070057h
0x18000eb14  mov     [rsp+2E0h+var_2A0], edi
0x18000eb18  mov     [rsp+2E0h+var_29A], si
0x18000eb1d  jmp     loc_18000ECC1
0x18000eb22  mov     [rsp+2E0h+var_29C], si
0x18000eb27  mov     eax, 219h
0x18000eb2c  test    r15, r15
0x18000eb2f  jnz     short loc_18000EB44
0x18000eb31  mov     edi, 80070057h
0x18000eb36  mov     [rsp+2E0h+var_2A0], edi
0x18000eb3a  mov     [rsp+2E0h+var_29A], ax
0x18000eb3f  jmp     loc_18000ECC1
0x18000eb44  mov     [rsp+2E0h+var_29C], ax
0x18000eb49  mov     eax, 21Ah
0x18000eb4e  test    rdi, rdi
0x18000eb51  jz      short loc_18000EB31
0x18000eb53  mov     [rsp+2E0h+var_2A0], 0
0x18000eb5b  mov     [rsp+2E0h+var_29C], ax
0x18000eb60  call    cs:__imp_RtlGetThreadErrorMode
0x18000eb67  nop     dword ptr [rax+rax+00h]
0x18000eb6c  mov     r14d, eax
0x18000eb6f  mov     ecx, eax
0x18000eb71  or      ecx, 10h; NewMode
0x18000eb74  xor     edx, edx; OldMode
0x18000eb76  call    cs:__imp_RtlSetThreadErrorMode
0x18000eb7d  nop     dword ptr [rax+rax+00h]
0x18000eb82  mov     ecx, eax
0x18000eb84  call    HRESULTFromNTSTATUS
0x18000eb89  mov     [rsp+2E0h+var_2A0], eax
0x18000eb8d  test    eax, eax
0x18000eb8f  mov     eax, 220h
0x18000eb94  jns     short loc_18000EBA0
0x18000eb96  mov     [rsp+2E0h+var_29A], ax
0x18000eb9b  jmp     loc_18000EC89
0x18000eba0  mov     [rsp+2E0h+var_29C], ax
0x18000eba5  mov     [rsp+2E0h+hTemplateFile], 0; hTemplateFile
0x18000ebae  mov     [rsp+2E0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000ebb6  mov     r8d, 3; dwShareMode
0x18000ebbc  mov     [rsp+2E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000ebc1  xor     r9d, r9d; lpSecurityAttributes
0x18000ebc4  mov     edx, 1000A0h; dwDesiredAccess
0x18000ebc9  mov     rcx, rbx; lpFileName
0x18000ebcc  call    cs:__imp_CreateFileW
0x18000ebd3  nop     dword ptr [rax+rax+00h]
0x18000ebd8  mov     rbx, rax
0x18000ebdb  inc     rax
0x18000ebde  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000ebe4  jnz     short loc_18000EC09
0x18000ebe6  call    GetLastFailureAsHRESULT
0x18000ebeb  mov     [rsp+2E0h+var_2A0], eax
0x18000ebef  mov     eax, 22Eh
0x18000ebf4  mov     [rsp+2E0h+var_29A], ax
0x18000ebf9  lea     rax, [rbx-1]
0x18000ebfd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ec01  ja      loc_18000EC8D
0x18000ec07  jmp     short loc_18000EC7A
0x18000ec09  mov     [rsp+2E0h+var_2A0], 0
0x18000ec11  mov     eax, 22Eh
0x18000ec16  mov     [rsp+2E0h+var_29C], ax
0x18000ec1b  mov     [rsp+2E0h+dwCreationDisposition], 5; FsInformationClass
0x18000ec23  mov     r9d, esi; Length
0x18000ec26  lea     r8, [rbp+1E0h+FsInformation]; FsInformation
0x18000ec2a  lea     rdx, [rsp+2E0h+IoStatusBlock]; IoStatusBlock
0x18000ec2f  mov     rcx, rbx; FileHandle
0x18000ec32  call    cs:__imp_NtQueryVolumeInformationFile
0x18000ec39  nop     dword ptr [rax+rax+00h]
0x18000ec3e  mov     ecx, eax
0x18000ec40  call    HRESULTFromNTSTATUS
0x18000ec45  mov     [rsp+2E0h+var_2A0], eax
0x18000ec49  test    eax, eax
0x18000ec4b  mov     eax, 234h
0x18000ec50  jns     short loc_18000EC59
0x18000ec52  mov     [rsp+2E0h+var_29A], ax
0x18000ec57  jmp     short loc_18000EC7A
0x18000ec59  mov     [rsp+2E0h+var_29C], ax
0x18000ec5e  mov     rdx, r15; String2
0x18000ec61  lea     rcx, [rbp+1E0h+String1]; String1
0x18000ec65  call    cs:__imp__wcsicmp
0x18000ec6c  nop     dword ptr [rax+rax+00h]
0x18000ec71  xor     ecx, ecx
0x18000ec73  test    eax, eax
0x18000ec75  setz    cl
0x18000ec78  mov     [rdi], ecx
0x18000ec7a  mov     rcx, rbx; hObject
0x18000ec7d  call    cs:__imp_CloseHandle
0x18000ec84  nop     dword ptr [rax+rax+00h]
0x18000ec89  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ec8d  cmp     r14d, 0FFFFFFFFh
0x18000ec91  jz      short loc_18000ECA4
0x18000ec93  xor     edx, edx; OldMode
0x18000ec95  mov     ecx, r14d; NewMode
0x18000ec98  call    cs:__imp_RtlSetThreadErrorMode
0x18000ec9f  nop     dword ptr [rax+rax+00h]
0x18000eca4  mov     edi, [rsp+2E0h+var_2A0]
0x18000eca8  lea     rcx, [rbx-1]
0x18000ecac  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000ecb0  ja      short loc_18000ECC1
0x18000ecb2  mov     rcx, rbx; hObject
0x18000ecb5  call    cs:__imp_CloseHandle
0x18000ecbc  nop     dword ptr [rax+rax+00h]
0x18000ecc1  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000ecc6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000eccb  mov     eax, edi
0x18000eccd  mov     rcx, [rbp+1E0h+var_30]
0x18000ecd4  xor     rcx, rsp; StackCookie
0x18000ecd7  call    __security_check_cookie
0x18000ecdc  mov     rbx, [rsp+2E0h+arg_18]
0x18000ece4  add     rsp, 2C0h
0x18000eceb  pop     r15
0x18000eced  pop     r14
0x18000ecef  pop     rdi
0x18000ecf0  pop     rsi
0x18000ecf1  pop     rbp
0x18000ecf2  retn
```
