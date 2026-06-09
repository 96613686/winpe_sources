# SxSetFileAttributes(ushort const *,ulong)

- ea: `0x18000deac`
- end: `0x18000e0d5`
- name: `?SxSetFileAttributes@@YAJPEBGK@Z`
- size: `553`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000dc78`
- `0x18000dd64`

## callees

- `0x180003ce0`
- `0x180003e5c`
- `0x18000d348`
- `0x18000d43c`
- `0x18000deac`
- `0x18000f154`
- `0x18000f1e4`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000e0a1`
- `KERNEL32!CloseHandle` at `0x18000e0a1`
- `KERNEL32!CreateFileW` at `0x18000df89`
- `KERNEL32!CreateFileW` at `0x18000df89`
- `ntdll!NtSetInformationFile` at `0x18000e079`
- `ntdll!NtSetInformationFile` at `0x18000e079`
- `ntdll!NtQueryInformationFile` at `0x18000e03f`
- `ntdll!NtQueryInformationFile` at `0x18000e03f`

## string_xrefs

- `0x18000df0f`: `SxSetFileAttributes`

## pseudocode

```c
__int64 __fastcall SxSetFileAttributes(LPCWSTR lpFileName, int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int LastFailureAsHRESULT; // ebx
  HANDLE FileW; // rdi
  unsigned int v8; // eax
  __int16 v9; // ax
  unsigned int v10; // eax
  int v12; // [rsp+40h] [rbp-49h] BYREF
  __int16 v13; // [rsp+44h] [rbp-45h]
  __int16 v14; // [rsp+46h] [rbp-43h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-11h] BYREF
  _BYTE FileInformation[40]; // [rsp+88h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxSetFileAttributes", 2380);
  memset(FileInformation, 0, sizeof(FileInformation));
  IoStatusBlock = 0;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v12 = -2147024809;
    v14 = 2386;
    goto LABEL_18;
  }
  v12 = 0;
  v13 = 2386;
  FileW = CreateFileW(lpFileName, 0x180u, 7u, 0, 3u, 0x2200000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v12 = 0;
    v13 = 2395;
    memset(FileInformation, 0, sizeof(FileInformation));
    v8 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v8);
    v12 = LastFailureAsHRESULT;
    v9 = 2399;
    if ( LastFailureAsHRESULT >= 0
      && (v13 = 2399,
          *(_DWORD *)&FileInformation[32] = a2 | 0x80,
          v10 = NtSetInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation),
          LastFailureAsHRESULT = HRESULTFromNTSTATUS(v10),
          v12 = LastFailureAsHRESULT,
          v9 = 2405,
          LastFailureAsHRESULT >= 0) )
    {
      v13 = 2405;
    }
    else
    {
      v14 = v9;
    }
LABEL_17:
    CloseHandle(FileW);
    goto LABEL_18;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  v12 = LastFailureAsHRESULT;
  v14 = 2395;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids,
      (unsigned int)"sh.IsValid()",
      (__int64)lpFileName,
      LastFailureAsHRESULT);
    LastFailureAsHRESULT = v12;
  }
  if ( FileW != (HANDLE)-1LL && FileW )
    goto LABEL_17;
LABEL_18:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12, v4, v5);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000deac  mov     [rsp-8+arg_10], rbx
0x18000deb1  push    rbp
0x18000deb2  push    rsi
0x18000deb3  push    rdi
0x18000deb4  push    r12
0x18000deb6  push    r14
0x18000deb8  lea     rbp, [rsp-37h]
0x18000debd  sub     rsp, 0C0h
0x18000dec4  mov     rax, cs:__security_cookie
0x18000decb  xor     rax, rsp
0x18000dece  mov     [rbp+57h+var_30], rax
0x18000ded2  mov     r14d, edx
0x18000ded5  mov     rsi, rcx
0x18000ded8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dedf  lea     r12, WPP_GLOBAL_Control
0x18000dee6  cmp     rcx, r12
0x18000dee9  jz      short loc_18000DF09
0x18000deeb  test    dword ptr [rcx+1Ch], 20000000h
0x18000def2  jz      short loc_18000DF09
0x18000def4  mov     rcx, [rcx+10h]
0x18000def8  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18000deff  mov     edx, 43h ; 'C'
0x18000df04  call    WPP_SF_
0x18000df09  mov     r8d, 94Ch; unsigned __int16
0x18000df0f  lea     rdx, aSxsetfileattri; "SxSetFileAttributes"
0x18000df16  lea     rcx, [rbp+57h+var_A0]; this
0x18000df1a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000df1f  xorps   xmm0, xmm0
0x18000df22  mov     dword ptr [rbp+57h+FileInformation], 0
0x18000df29  xor     eax, eax
0x18000df2b  mov     [rbp+57h+var_34], eax
0x18000df2e  movups  [rbp+57h+FileInformation+4], xmm0
0x18000df32  movups  [rbp+57h+var_44], xmm0
0x18000df36  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000df3a  test    rsi, rsi
0x18000df3d  jnz     short loc_18000DF55
0x18000df3f  mov     ebx, 80070057h
0x18000df44  mov     eax, 952h
0x18000df49  mov     [rbp+57h+var_A0], ebx
0x18000df4c  mov     [rbp+57h+var_9A], ax
0x18000df50  jmp     loc_18000E0A7
0x18000df55  xor     r9d, r9d; lpSecurityAttributes
0x18000df58  mov     [rbp+57h+var_A0], eax
0x18000df5b  mov     eax, 952h
0x18000df60  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18000df69  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000df71  mov     edx, 180h; dwDesiredAccess
0x18000df76  mov     rcx, rsi; lpFileName
0x18000df79  mov     [rbp+57h+var_9C], ax
0x18000df7d  lea     r8d, [r9+7]; dwShareMode
0x18000df81  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000df89  call    cs:__imp_CreateFileW
0x18000df8f  mov     rdi, rax
0x18000df92  inc     rax
0x18000df95  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000df9b  jnz     short loc_18000E005
0x18000df9d  call    GetLastFailureAsHRESULT
0x18000dfa2  mov     ebx, eax
0x18000dfa4  mov     [rbp+57h+var_A0], eax
0x18000dfa7  mov     eax, 95Bh
0x18000dfac  mov     [rbp+57h+var_9A], ax
0x18000dfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfb7  cmp     rcx, r12
0x18000dfba  jz      short loc_18000DFED
0x18000dfbc  test    dword ptr [rcx+1Ch], 2000000h
0x18000dfc3  jz      short loc_18000DFED
0x18000dfc5  mov     rcx, [rcx+10h]
0x18000dfc9  lea     r9, aShIsvalid; "sh.IsValid()"
0x18000dfd0  mov     edx, 44h ; 'D'
0x18000dfd5  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx
0x18000dfd9  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18000dfe0  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x18000dfe5  call    WPP_SF_sSd
0x18000dfea  mov     ebx, [rbp+57h+var_A0]
0x18000dfed  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000dff1  jz      loc_18000E0A7
0x18000dff7  test    rdi, rdi
0x18000dffa  jz      loc_18000E0A7
0x18000e000  jmp     loc_18000E09E
0x18000e005  xorps   xmm0, xmm0
0x18000e008  mov     [rbp+57h+var_A0], 0
0x18000e00f  mov     eax, 95Bh
0x18000e014  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000e018  mov     [rbp+57h+var_9C], ax
0x18000e01c  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e020  xor     eax, eax
0x18000e022  mov     rcx, rdi; FileHandle
0x18000e025  movups  [rbp+57h+FileInformation], xmm0
0x18000e029  mov     qword ptr [rbp+57h+var_44+0Ch], rax
0x18000e02d  movups  xmmword ptr [rbp+0Fh], xmm0
0x18000e031  lea     r12d, [rax+28h]
0x18000e035  lea     esi, [rax+4]
0x18000e038  mov     r9d, r12d; Length
0x18000e03b  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x18000e03f  call    cs:__imp_NtQueryInformationFile
0x18000e045  mov     ecx, eax
0x18000e047  call    HRESULTFromNTSTATUS
0x18000e04c  mov     ebx, eax
0x18000e04e  mov     [rbp+57h+var_A0], eax
0x18000e051  test    eax, eax
0x18000e053  mov     eax, 95Fh
0x18000e058  js      short loc_18000E094
0x18000e05a  bts     r14d, 7
0x18000e05f  mov     [rbp+57h+var_9C], ax
0x18000e063  mov     r9d, r12d; Length
0x18000e066  mov     dword ptr [rbp+57h+var_44+0Ch], r14d
0x18000e06a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000e06e  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x18000e072  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e076  mov     rcx, rdi; FileHandle
0x18000e079  call    cs:__imp_NtSetInformationFile
0x18000e07f  mov     ecx, eax
0x18000e081  call    HRESULTFromNTSTATUS
0x18000e086  mov     ebx, eax
0x18000e088  mov     [rbp+57h+var_A0], eax
0x18000e08b  test    eax, eax
0x18000e08d  mov     eax, 965h
0x18000e092  jns     short loc_18000E09A
0x18000e094  mov     [rbp+57h+var_9A], ax
0x18000e098  jmp     short loc_18000E09E
0x18000e09a  mov     [rbp+57h+var_9C], ax
0x18000e09e  mov     rcx, rdi; hObject
0x18000e0a1  call    cs:__imp_CloseHandle
0x18000e0a7  lea     rcx, [rbp+57h+var_A0]; this
0x18000e0ab  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e0b0  mov     eax, ebx
0x18000e0b2  mov     rcx, [rbp+57h+var_30]
0x18000e0b6  xor     rcx, rsp; StackCookie
0x18000e0b9  call    __security_check_cookie
0x18000e0be  mov     rbx, [rsp+0E0h+arg_10]
0x18000e0c6  add     rsp, 0C0h
0x18000e0cd  pop     r14
0x18000e0cf  pop     r12
0x18000e0d1  pop     rdi
0x18000e0d2  pop     rsi
0x18000e0d3  pop     rbp
0x18000e0d4  retn
```
