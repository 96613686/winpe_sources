# SxSetFileAttributes(ushort const *,ulong)

- ea: `0x18002eed4`
- end: `0x18002f103`
- name: `?SxSetFileAttributes@@YAJPEBGK@Z`
- size: `559`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18002ea8c`
- `0x18002eb80`

## callees

- `0x180020710`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18002d778`
- `0x18002eed4`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002efb7`
- `KERNEL32!CreateFileW` at `0x18002efb7`
- `KERNEL32!CloseHandle` at `0x18002f0cf`
- `KERNEL32!CloseHandle` at `0x18002f0cf`
- `ntdll!NtSetInformationFile` at `0x18002f0a7`
- `ntdll!NtSetInformationFile` at `0x18002f0a7`
- `ntdll!NtQueryInformationFile` at `0x18002f06d`
- `ntdll!NtQueryInformationFile` at `0x18002f06d`

## string_xrefs

- `0x18002ef37`: `SxSetFileAttributes`

## pseudocode

```c
__int64 __fastcall SxSetFileAttributes(LPCWSTR lpFileName, int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int LastFailureAsHRESULT; // ebx
  __int64 v7; // rcx
  HANDLE FileW; // rdi
  unsigned int v9; // eax
  __int16 v10; // ax
  unsigned int v11; // eax
  int v13; // [rsp+40h] [rbp-49h] BYREF
  __int16 v14; // [rsp+44h] [rbp-45h]
  __int16 v15; // [rsp+46h] [rbp-43h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-11h] BYREF
  _BYTE FileInformation[40]; // [rsp+88h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "SxSetFileAttributes", 2380, 1);
  memset(FileInformation, 0, sizeof(FileInformation));
  IoStatusBlock = 0;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v13 = -2147024809;
    v15 = 2386;
    goto LABEL_18;
  }
  v13 = 0;
  v14 = 2386;
  FileW = CreateFileW(lpFileName, 0x180u, 7u, 0, 3u, 0x2200000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v13 = 0;
    v14 = 2395;
    memset(FileInformation, 0, sizeof(FileInformation));
    v9 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v9);
    v13 = LastFailureAsHRESULT;
    v10 = 2399;
    if ( LastFailureAsHRESULT >= 0
      && (v14 = 2399,
          *(_DWORD *)&FileInformation[32] = a2 | 0x80,
          v11 = NtSetInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation),
          LastFailureAsHRESULT = HRESULTFromNTSTATUS(v11),
          v13 = LastFailureAsHRESULT,
          v10 = 2405,
          LastFailureAsHRESULT >= 0) )
    {
      v14 = 2405;
    }
    else
    {
      v15 = v10;
    }
LABEL_17:
    CloseHandle(FileW);
    goto LABEL_18;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
  v13 = LastFailureAsHRESULT;
  v15 = 2395;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)&WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids,
      (unsigned int)"sh.IsValid()",
      (__int64)lpFileName,
      LastFailureAsHRESULT);
    LastFailureAsHRESULT = v13;
  }
  if ( FileW != (HANDLE)-1LL && FileW )
    goto LABEL_17;
LABEL_18:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v4, v5);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002eed4  mov     [rsp-8+arg_10], rbx
0x18002eed9  push    rbp
0x18002eeda  push    rsi
0x18002eedb  push    rdi
0x18002eedc  push    r12
0x18002eede  push    r14
0x18002eee0  lea     rbp, [rsp-37h]
0x18002eee5  sub     rsp, 0C0h
0x18002eeec  mov     rax, cs:__security_cookie
0x18002eef3  xor     rax, rsp
0x18002eef6  mov     [rbp+57h+var_30], rax
0x18002eefa  mov     r14d, edx
0x18002eefd  mov     rsi, rcx
0x18002ef00  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef07  lea     r12, WPP_GLOBAL_Control
0x18002ef0e  cmp     rcx, r12
0x18002ef11  jz      short loc_18002EF31
0x18002ef13  test    dword ptr [rcx+1Ch], 20000000h
0x18002ef1a  jz      short loc_18002EF31
0x18002ef1c  mov     rcx, [rcx+10h]
0x18002ef20  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002ef27  mov     edx, 43h ; 'C'
0x18002ef2c  call    WPP_SF_
0x18002ef31  mov     r9d, 1; unsigned __int16
0x18002ef37  lea     rdx, aSxsetfileattri; "SxSetFileAttributes"
0x18002ef3e  mov     r8d, 94Ch; unsigned __int16
0x18002ef44  lea     rcx, [rbp+57h+var_A0]; this
0x18002ef48  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002ef4d  xorps   xmm0, xmm0
0x18002ef50  mov     dword ptr [rbp+57h+FileInformation], 0
0x18002ef57  xor     eax, eax
0x18002ef59  mov     [rbp+57h+var_34], eax
0x18002ef5c  movups  [rbp+57h+FileInformation+4], xmm0
0x18002ef60  movups  [rbp+57h+var_44], xmm0
0x18002ef64  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002ef68  test    rsi, rsi
0x18002ef6b  jnz     short loc_18002EF83
0x18002ef6d  mov     ebx, 80070057h
0x18002ef72  mov     eax, 952h
0x18002ef77  mov     [rbp+57h+var_A0], ebx
0x18002ef7a  mov     [rbp+57h+var_9A], ax
0x18002ef7e  jmp     loc_18002F0D5
0x18002ef83  xor     r9d, r9d; lpSecurityAttributes
0x18002ef86  mov     [rbp+57h+var_A0], eax
0x18002ef89  mov     eax, 952h
0x18002ef8e  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18002ef97  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18002ef9f  mov     edx, 180h; dwDesiredAccess
0x18002efa4  mov     rcx, rsi; lpFileName
0x18002efa7  mov     [rbp+57h+var_9C], ax
0x18002efab  lea     r8d, [r9+7]; dwShareMode
0x18002efaf  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002efb7  call    cs:__imp_CreateFileW
0x18002efbd  mov     rdi, rax
0x18002efc0  inc     rax
0x18002efc3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002efc9  jnz     short loc_18002F033
0x18002efcb  call    GetLastFailureAsHRESULT
0x18002efd0  mov     ebx, eax
0x18002efd2  mov     [rbp+57h+var_A0], eax
0x18002efd5  mov     eax, 95Bh
0x18002efda  mov     [rbp+57h+var_9A], ax
0x18002efde  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efe5  cmp     rcx, r12
0x18002efe8  jz      short loc_18002F01B
0x18002efea  test    dword ptr [rcx+1Ch], 2000000h
0x18002eff1  jz      short loc_18002F01B
0x18002eff3  mov     rcx, [rcx+10h]
0x18002eff7  lea     r9, aShIsvalid; "sh.IsValid()"
0x18002effe  mov     edx, 44h ; 'D'
0x18002f003  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx
0x18002f007  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002f00e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x18002f013  call    WPP_SF_sSd
0x18002f018  mov     ebx, [rbp+57h+var_A0]
0x18002f01b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002f01f  jz      loc_18002F0D5
0x18002f025  test    rdi, rdi
0x18002f028  jz      loc_18002F0D5
0x18002f02e  jmp     loc_18002F0CC
0x18002f033  xorps   xmm0, xmm0
0x18002f036  mov     [rbp+57h+var_A0], 0
0x18002f03d  mov     eax, 95Bh
0x18002f042  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18002f046  mov     [rbp+57h+var_9C], ax
0x18002f04a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002f04e  xor     eax, eax
0x18002f050  mov     rcx, rdi; FileHandle
0x18002f053  movups  [rbp+57h+FileInformation], xmm0
0x18002f057  mov     qword ptr [rbp+57h+var_44+0Ch], rax
0x18002f05b  movups  xmmword ptr [rbp+0Fh], xmm0
0x18002f05f  lea     r12d, [rax+28h]
0x18002f063  lea     esi, [rax+4]
0x18002f066  mov     r9d, r12d; Length
0x18002f069  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x18002f06d  call    cs:__imp_NtQueryInformationFile
0x18002f073  mov     ecx, eax
0x18002f075  call    HRESULTFromNTSTATUS
0x18002f07a  mov     ebx, eax
0x18002f07c  mov     [rbp+57h+var_A0], eax
0x18002f07f  test    eax, eax
0x18002f081  mov     eax, 95Fh
0x18002f086  js      short loc_18002F0C2
0x18002f088  bts     r14d, 7
0x18002f08d  mov     [rbp+57h+var_9C], ax
0x18002f091  mov     r9d, r12d; Length
0x18002f094  mov     dword ptr [rbp+57h+var_44+0Ch], r14d
0x18002f098  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18002f09c  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x18002f0a0  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002f0a4  mov     rcx, rdi; FileHandle
0x18002f0a7  call    cs:__imp_NtSetInformationFile
0x18002f0ad  mov     ecx, eax
0x18002f0af  call    HRESULTFromNTSTATUS
0x18002f0b4  mov     ebx, eax
0x18002f0b6  mov     [rbp+57h+var_A0], eax
0x18002f0b9  test    eax, eax
0x18002f0bb  mov     eax, 965h
0x18002f0c0  jns     short loc_18002F0C8
0x18002f0c2  mov     [rbp+57h+var_9A], ax
0x18002f0c6  jmp     short loc_18002F0CC
0x18002f0c8  mov     [rbp+57h+var_9C], ax
0x18002f0cc  mov     rcx, rdi; hObject
0x18002f0cf  call    cs:__imp_CloseHandle
0x18002f0d5  lea     rcx, [rbp+57h+var_A0]; this
0x18002f0d9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002f0de  mov     eax, ebx
0x18002f0e0  mov     rcx, [rbp+57h+var_30]
0x18002f0e4  xor     rcx, rsp; StackCookie
0x18002f0e7  call    __security_check_cookie
0x18002f0ec  mov     rbx, [rsp+0E0h+arg_10]
0x18002f0f4  add     rsp, 0C0h
0x18002f0fb  pop     r14
0x18002f0fd  pop     r12
0x18002f0ff  pop     rdi
0x18002f100  pop     rsi
0x18002f101  pop     rbp
0x18002f102  retn
```
