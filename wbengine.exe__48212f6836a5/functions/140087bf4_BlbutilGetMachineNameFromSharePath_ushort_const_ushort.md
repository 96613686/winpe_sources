# BlbutilGetMachineNameFromSharePath(ushort const *,ushort * *)

- ea: `0x140087bf4`
- end: `0x140088083`
- name: `?BlbutilGetMachineNameFromSharePath@@YAJPEBGPEAPEAG@Z`
- size: `1167`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x14008e584`
- `0x1400940f0`
- `0x1400efa40`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140087bf4`
- `0x14008808c`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140087db9`
- `KERNEL32!CreateFileW` at `0x140087db9`
- `KERNEL32!CloseHandle` at `0x140088031`
- `KERNEL32!CloseHandle` at `0x140088031`
- `KERNEL32!GetLastError` at `0x140087dc7`
- `KERNEL32!GetLastError` at `0x140087dc7`
- `msvcrt!wcsstr` at `0x140087cb0`
- `msvcrt!wcsstr` at `0x140087cd9`
- `msvcrt!wcsstr` at `0x140087d02`
- `msvcrt!wcsstr` at `0x140087f9a`
- `msvcrt!wcsstr` at `0x140087cb0`
- `msvcrt!wcsstr` at `0x140087cd9`
- `msvcrt!wcsstr` at `0x140087d02`
- `msvcrt!wcsstr` at `0x140087f9a`
- `ntdll!RtlNtStatusToDosError` at `0x140087e6b`
- `ntdll!RtlNtStatusToDosError` at `0x140087f25`
- `ntdll!RtlNtStatusToDosError` at `0x140087e6b`
- `ntdll!RtlNtStatusToDosError` at `0x140087f25`
- `ntdll!NtQueryInformationFile` at `0x140087e53`
- `ntdll!NtQueryInformationFile` at `0x140087f17`
- `ntdll!NtQueryInformationFile` at `0x140087e53`
- `ntdll!NtQueryInformationFile` at `0x140087f17`
- `ole32!CoTaskMemAlloc` at `0x140087d1e`
- `ole32!CoTaskMemAlloc` at `0x140087ed4`
- `ole32!CoTaskMemAlloc` at `0x140087fb9`
- `ole32!CoTaskMemAlloc` at `0x140087d1e`
- `ole32!CoTaskMemAlloc` at `0x140087ed4`
- `ole32!CoTaskMemAlloc` at `0x140087fb9`
- `ole32!CoTaskMemFree` at `0x14008803f`
- `ole32!CoTaskMemFree` at `0x140088048`
- `ole32!CoTaskMemFree` at `0x140088056`
- `ole32!CoTaskMemFree` at `0x14008803f`
- `ole32!CoTaskMemFree` at `0x140088048`
- `ole32!CoTaskMemFree` at `0x140088056`

## string_xrefs

- `0x140087c25`: `wszFilePath`

## pseudocode

```c
__int64 __fastcall BlbutilGetMachineNameFromSharePath(wchar_t *a1, unsigned __int16 **a2)
{
  wchar_t *v2; // r15
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rax
  signed int v7; // ebx
  const wchar_t *v8; // rcx
  unsigned __int64 v9; // rax
  wchar_t *v10; // rax
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  wchar_t *v13; // rax
  unsigned __int64 v14; // rdi
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rbp
  HANDLE FileW; // rax
  void *v18; // r12
  signed int LastError; // eax
  void *v20; // rdi
  NTSTATUS v21; // eax
  signed int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  ULONG v25; // ebx
  SIZE_T v26; // r14
  wchar_t *v27; // rax
  int v28; // eax
  signed int v29; // eax
  wchar_t *v30; // rax
  unsigned __int64 v31; // rsi
  void *v32; // rax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-58h] BYREF
  __int64 FileInformation; // [rsp+50h] [rbp-48h] BYREF

  v2 = 0;
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\util\\networkutils.cpp", 0x17Au, "wszFilePath");
  *a2 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids, a1);
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  if ( v6 < 2 )
    return (unsigned int)-2147024809;
  if ( wcsstr(a1, L"\\\\") != a1 )
    return (unsigned int)-2147024809;
  v8 = a1 + 2;
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  if ( v9 < 2 )
    return (unsigned int)-2147024809;
  v10 = wcsstr(v8, L"\\");
  if ( !v10 )
    return (unsigned int)-2147024809;
  v11 = v10 + 1;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  if ( v12 < 2 || (v13 = wcsstr(v11, L"\\")) == 0 )
    return (unsigned int)-2147024809;
  v14 = v13 - a1 + 1;
  v15 = (unsigned __int16 *)CoTaskMemAlloc(2 * v14);
  v16 = v15;
  if ( !v15 )
    return (unsigned int)-2147024882;
  memset_0(v15, 0, 2 * v14);
  v7 = StringCchCopyNW(v16, v14, a1, v14 - 1);
  if ( v7 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids, v16);
    }
    FileW = CreateFileW(v16, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
    v18 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids,
          (_DWORD)v16,
          v7);
      }
      goto LABEL_65;
    }
    FileInformation = 0;
    v20 = 0;
    IoStatusBlock = 0;
    v21 = NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 8u, FileNetworkPhysicalNameInformation);
    if ( ((v21 + 0x80000000) & 0x80000000) == 0 && v21 != -2147483643 )
    {
      v22 = RtlNtStatusToDosError(v21);
      v7 = v22;
      if ( v22 > 0 )
        v7 = (unsigned __int16)v22 | 0x80070000;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v24 = 20;
      goto LABEL_42;
    }
    v25 = FileInformation + 8;
    v26 = (unsigned int)(FileInformation + 8);
    v27 = (wchar_t *)CoTaskMemAlloc(v26);
    v2 = v27;
    if ( v27 )
    {
      memset_0(v27, 0, v26);
      IoStatusBlock = 0;
      v28 = NtQueryInformationFile(v18, &IoStatusBlock, v2, v25, FileNetworkPhysicalNameInformation);
      if ( v28 < 0 )
      {
        v29 = RtlNtStatusToDosError(v28);
        v7 = v29;
        if ( v29 > 0 )
          v7 = (unsigned __int16)v29 | 0x80070000;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_63;
        }
        v24 = 21;
LABEL_42:
        WPP_SF_d(v23[2], v24, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids);
        goto LABEL_63;
      }
      do
        ++v5;
      while ( v2[v5 + 3] );
      if ( v5 < 2 || (v30 = wcsstr(v2 + 3, L"\\")) == 0 )
      {
        v7 = -2147024809;
LABEL_63:
        CloseHandle(v18);
        if ( v20 )
          CoTaskMemFree(v20);
        goto LABEL_65;
      }
      v31 = (((char *)v30 - (char *)(v2 + 2) - 2) >> 1) + 1;
      v32 = CoTaskMemAlloc(2 * v31);
      v20 = v32;
      if ( v32 )
      {
        memset_0(v32, 0, 2 * v31);
        v7 = StringCchCopyNW((unsigned __int16 *)v20, v31, v2 + 3, v31 - 1);
        if ( v7 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids, v20);
          }
          *a2 = (unsigned __int16 *)v20;
          v20 = 0;
        }
        goto LABEL_63;
      }
    }
    v7 = -2147024882;
    goto LABEL_63;
  }
LABEL_65:
  CoTaskMemFree(v16);
  if ( v2 )
    CoTaskMemFree(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140087bf4  mov     [rsp+arg_10], rbx
0x140087bf9  push    rbp
0x140087bfa  push    rsi
0x140087bfb  push    rdi
0x140087bfc  push    r12
0x140087bfe  push    r13
0x140087c00  push    r14
0x140087c02  push    r15
0x140087c04  sub     rsp, 60h
0x140087c08  mov     rax, cs:__security_cookie
0x140087c0f  xor     rax, rsp
0x140087c12  mov     [rsp+98h+var_40], rax
0x140087c17  xor     r15d, r15d
0x140087c1a  mov     r13, rdx
0x140087c1d  mov     rbx, rcx
0x140087c20  test    rcx, rcx
0x140087c23  jnz     short loc_140087C3D
0x140087c25  lea     r8, aWszfilepath; "wszFilePath"
0x140087c2c  mov     edx, 17Ah; unsigned int
0x140087c31  lea     rcx, aBaseStorBlbUti_9; "base\\stor\\blb\\util\\networkutils.cpp"
0x140087c38  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140087c3d  xorps   xmm0, xmm0
0x140087c40  mov     [r13+0], r15
0x140087c44  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x140087c49  mov     [rsp+98h+FileInformation], r15
0x140087c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140087c55  lea     r12, WPP_GLOBAL_Control
0x140087c5c  cmp     rcx, r12
0x140087c5f  jz      short loc_140087C85
0x140087c61  test    byte ptr [rcx+1Ch], 1
0x140087c65  jz      short loc_140087C85
0x140087c67  cmp     byte ptr [rcx+19h], 4
0x140087c6b  jb      short loc_140087C85
0x140087c6d  mov     rcx, [rcx+10h]
0x140087c71  lea     r8, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids
0x140087c78  mov     edx, 11h
0x140087c7d  mov     r9, rbx
0x140087c80  call    WPP_SF_S
0x140087c85  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140087c89  mov     rax, rsi
0x140087c8c  inc     rax
0x140087c8f  cmp     [rbx+rax*2], r15w
0x140087c94  jnz     short loc_140087C8C
0x140087c96  cmp     rax, 2
0x140087c9a  jnb     short loc_140087CA6
0x140087c9c  mov     ebx, 80070057h
0x140087ca1  jmp     loc_14008805C
0x140087ca6  lea     rdx, SubStr; "\\\\"
0x140087cad  mov     rcx, rbx; Str
0x140087cb0  call    cs:__imp_wcsstr
0x140087cb6  cmp     rax, rbx
0x140087cb9  jnz     short loc_140087C9C
0x140087cbb  lea     rcx, [rbx+4]; Str
0x140087cbf  mov     rax, rsi
0x140087cc2  inc     rax
0x140087cc5  cmp     [rcx+rax*2], r15w
0x140087cca  jnz     short loc_140087CC2
0x140087ccc  cmp     rax, 2
0x140087cd0  jb      short loc_140087C9C
0x140087cd2  lea     rdx, asc_14013C090; "\\"
0x140087cd9  call    cs:__imp_wcsstr
0x140087cdf  test    rax, rax
0x140087ce2  jz      short loc_140087C9C
0x140087ce4  lea     rcx, [rax+2]; Str
0x140087ce8  mov     rax, rsi
0x140087ceb  inc     rax
0x140087cee  cmp     [rcx+rax*2], r15w
0x140087cf3  jnz     short loc_140087CEB
0x140087cf5  cmp     rax, 2
0x140087cf9  jb      short loc_140087C9C
0x140087cfb  lea     rdx, asc_14013C090; "\\"
0x140087d02  call    cs:__imp_wcsstr
0x140087d08  test    rax, rax
0x140087d0b  jz      short loc_140087C9C
0x140087d0d  sub     rax, rbx
0x140087d10  sar     rax, 1
0x140087d13  lea     rdi, [rax+1]
0x140087d17  lea     r14, [rdi+rdi]
0x140087d1b  mov     rcx, r14; cb
0x140087d1e  call    cs:__imp_CoTaskMemAlloc
0x140087d24  mov     rbp, rax
0x140087d27  test    rax, rax
0x140087d2a  jnz     short loc_140087D36
0x140087d2c  mov     ebx, 8007000Eh
0x140087d31  jmp     loc_14008805C
0x140087d36  mov     r8, r14; Size
0x140087d39  xor     edx, edx; Val
0x140087d3b  mov     rcx, rbp; void *
0x140087d3e  call    memset_0
0x140087d43  lea     r9, [rdi-1]; unsigned __int64
0x140087d47  mov     r8, rbx; unsigned __int16 *
0x140087d4a  mov     rdx, rdi; unsigned __int64
0x140087d4d  mov     rcx, rbp; unsigned __int16 *
0x140087d50  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140087d55  mov     ebx, eax
0x140087d57  test    eax, eax
0x140087d59  js      loc_140088045
0x140087d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140087d66  cmp     rcx, r12
0x140087d69  jz      short loc_140087D8F
0x140087d6b  test    byte ptr [rcx+1Ch], 1
0x140087d6f  jz      short loc_140087D8F
0x140087d71  cmp     byte ptr [rcx+19h], 4
0x140087d75  jb      short loc_140087D8F
0x140087d77  mov     rcx, [rcx+10h]
0x140087d7b  lea     r8, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids
0x140087d82  mov     edx, 12h
0x140087d87  mov     r9, rbp
0x140087d8a  call    WPP_SF_S
0x140087d8f  xor     ebx, ebx
0x140087d91  mov     r14d, 80000000h
0x140087d97  mov     [rsp+98h+hTemplateFile], rbx; hTemplateFile
0x140087d9c  xor     r9d, r9d; lpSecurityAttributes
0x140087d9f  mov     [rsp+98h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140087da7  mov     edx, r14d; dwDesiredAccess
0x140087daa  mov     rcx, rbp; lpFileName
0x140087dad  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x140087db5  lea     r8d, [rbx+7]; dwShareMode
0x140087db9  call    cs:__imp_CreateFileW
0x140087dbf  mov     r12, rax
0x140087dc2  cmp     rax, rsi
0x140087dc5  jnz     short loc_140087E28
0x140087dc7  call    cs:__imp_GetLastError
0x140087dcd  mov     ebx, eax
0x140087dcf  test    eax, eax
0x140087dd1  jle     short loc_140087DDC
0x140087dd3  movzx   ebx, ax
0x140087dd6  or      ebx, 80070000h
0x140087ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x140087de3  lea     rax, WPP_GLOBAL_Control
0x140087dea  cmp     rcx, rax
0x140087ded  jz      loc_140088045
0x140087df3  test    byte ptr [rcx+1Ch], 1
0x140087df7  jz      loc_140088045
0x140087dfd  cmp     byte ptr [rcx+19h], 2
0x140087e01  jb      loc_140088045
0x140087e07  mov     rcx, [rcx+10h]
0x140087e0b  lea     r8, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids
0x140087e12  mov     edx, 13h
0x140087e17  mov     [rsp+98h+dwCreationDisposition], ebx
0x140087e1b  mov     r9, rbp
0x140087e1e  call    WPP_SF_Sd
0x140087e23  jmp     loc_140088045
0x140087e28  xorps   xmm0, xmm0
0x140087e2b  mov     [rsp+98h+FileInformation], rbx
0x140087e30  mov     r9d, 8; Length
0x140087e36  mov     [rsp+98h+dwCreationDisposition], 31h ; '1'; FileInformationClass
0x140087e3e  lea     r8, [rsp+98h+FileInformation]; FileInformation
0x140087e43  mov     rcx, r12; FileHandle
0x140087e46  lea     rdx, [rsp+98h+IoStatusBlock]; IoStatusBlock
0x140087e4b  mov     rdi, rbx
0x140087e4e  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x140087e53  call    cs:__imp_NtQueryInformationFile
0x140087e59  lea     ecx, [rax+r14]
0x140087e5d  test    r14d, ecx
0x140087e60  jnz     short loc_140087EC8
0x140087e62  cmp     eax, 80000005h
0x140087e67  jz      short loc_140087EC8
0x140087e69  mov     ecx, eax; Status
0x140087e6b  call    cs:__imp_RtlNtStatusToDosError
0x140087e71  mov     ebx, eax
0x140087e73  test    eax, eax
0x140087e75  jle     short loc_140087E80
0x140087e77  movzx   ebx, ax
0x140087e7a  or      ebx, 80070000h
0x140087e80  mov     rcx, cs:WPP_GLOBAL_Control
0x140087e87  lea     rax, WPP_GLOBAL_Control
0x140087e8e  cmp     rcx, rax
0x140087e91  jz      loc_14008802E
0x140087e97  test    byte ptr [rcx+1Ch], 1
0x140087e9b  jz      loc_14008802E
0x140087ea1  cmp     byte ptr [rcx+19h], 2
0x140087ea5  jb      loc_14008802E
0x140087eab  mov     edx, 14h
0x140087eb0  mov     rcx, [rcx+10h]
0x140087eb4  lea     r8, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids
0x140087ebb  mov     r9d, ebx
0x140087ebe  call    WPP_SF_d
0x140087ec3  jmp     loc_14008802E
0x140087ec8  mov     ebx, dword ptr [rsp+98h+FileInformation]
0x140087ecc  add     ebx, 8
0x140087ecf  mov     ecx, ebx; cb
0x140087ed1  mov     r14d, ebx
0x140087ed4  call    cs:__imp_CoTaskMemAlloc
0x140087eda  mov     r15, rax
0x140087edd  test    rax, rax
0x140087ee0  jnz     short loc_140087EEC
0x140087ee2  mov     ebx, 8007000Eh
0x140087ee7  jmp     loc_14008802E
0x140087eec  mov     r8, r14; Size
0x140087eef  xor     edx, edx; Val
0x140087ef1  mov     rcx, r15; void *
0x140087ef4  call    memset_0
0x140087ef9  xorps   xmm0, xmm0
0x140087efc  mov     [rsp+98h+dwCreationDisposition], 31h ; '1'; FileInformationClass
0x140087f04  mov     r9d, ebx; Length
0x140087f07  lea     rdx, [rsp+98h+IoStatusBlock]; IoStatusBlock
0x140087f0c  mov     r8, r15; FileInformation
0x140087f0f  mov     rcx, r12; FileHandle
0x140087f12  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x140087f17  call    cs:__imp_NtQueryInformationFile
0x140087f1d  xor     ecx, ecx
0x140087f1f  test    eax, eax
0x140087f21  jns     short loc_140087F6F
0x140087f23  mov     ecx, eax; Status
0x140087f25  call    cs:__imp_RtlNtStatusToDosError
0x140087f2b  mov     ebx, eax
0x140087f2d  test    eax, eax
0x140087f2f  jle     short loc_140087F3A
0x140087f31  movzx   ebx, ax
0x140087f34  or      ebx, 80070000h
0x140087f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140087f41  lea     rax, WPP_GLOBAL_Control
0x140087f48  cmp     rcx, rax
0x140087f4b  jz      loc_14008802E
0x140087f51  test    byte ptr [rcx+1Ch], 1
0x140087f55  jz      loc_14008802E
0x140087f5b  cmp     byte ptr [rcx+19h], 2
0x140087f5f  jb      loc_14008802E
0x140087f65  mov     edx, 15h
0x140087f6a  jmp     loc_140087EB0
0x140087f6f  lea     r14, [r15+4]
0x140087f73  lea     rbx, [r14+2]
0x140087f77  inc     rsi
0x140087f7a  cmp     [rbx+rsi*2], cx
0x140087f7e  jnz     short loc_140087F77
0x140087f80  cmp     rsi, 2
0x140087f84  jnb     short loc_140087F90
0x140087f86  mov     ebx, 80070057h
0x140087f8b  jmp     loc_14008802E
0x140087f90  lea     rdx, asc_14013C090; "\\"
0x140087f97  mov     rcx, rbx; Str
0x140087f9a  call    cs:__imp_wcsstr
0x140087fa0  test    rax, rax
0x140087fa3  jz      short loc_140087F86
0x140087fa5  sub     rax, r14
0x140087fa8  lea     rsi, [rax-2]
0x140087fac  sar     rsi, 1
0x140087faf  inc     rsi
0x140087fb2  lea     r14, [rsi+rsi]
0x140087fb6  mov     rcx, r14; cb
0x140087fb9  call    cs:__imp_CoTaskMemAlloc
0x140087fbf  mov     rdi, rax
0x140087fc2  test    rax, rax
0x140087fc5  jz      loc_140087EE2
0x140087fcb  mov     r8, r14; Size
0x140087fce  xor     edx, edx; Val
0x140087fd0  mov     rcx, rax; void *
0x140087fd3  call    memset_0
0x140087fd8  lea     r9, [rsi-1]; unsigned __int64
0x140087fdc  mov     r8, rbx; unsigned __int16 *
0x140087fdf  mov     rdx, rsi; unsigned __int64
0x140087fe2  mov     rcx, rdi; unsigned __int16 *
0x140087fe5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140087fea  xor     esi, esi
0x140087fec  mov     ebx, eax
0x140087fee  test    eax, eax
0x140087ff0  js      short loc_14008802E
0x140087ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x140087ff9  lea     rax, WPP_GLOBAL_Control
0x140088000  cmp     rcx, rax
0x140088003  jz      short loc_140088027
0x140088005  test    byte ptr [rcx+1Ch], 1
0x140088009  jz      short loc_140088027
0x14008800b  cmp     byte ptr [rcx+19h], 4
0x14008800f  jb      short loc_140088027
0x140088011  mov     rcx, [rcx+10h]
0x140088015  lea     edx, [rsi+16h]
0x140088018  mov     r9, rdi
0x14008801b  lea     r8, WPP_4e7a3de9d30b32dc1c5370d3ac2b5860_Traceguids
0x140088022  call    WPP_SF_S
0x140088027  mov     [r13+0], rdi
0x14008802b  mov     rdi, rsi
0x14008802e  mov     rcx, r12; hObject
0x140088031  call    cs:__imp_CloseHandle
0x140088037  test    rdi, rdi
0x14008803a  jz      short loc_140088045
0x14008803c  mov     rcx, rdi; pv
0x14008803f  call    cs:__imp_CoTaskMemFree
0x140088045  mov     rcx, rbp; pv
0x140088048  call    cs:__imp_CoTaskMemFree
0x14008804e  test    r15, r15
0x140088051  jz      short loc_14008805C
0x140088053  mov     rcx, r15; pv
0x140088056  call    cs:__imp_CoTaskMemFree
0x14008805c  mov     eax, ebx
0x14008805e  mov     rcx, [rsp+98h+var_40]
0x140088063  xor     rcx, rsp; StackCookie
0x140088066  call    __security_check_cookie
0x14008806b  mov     rbx, [rsp+98h+arg_10]
0x140088073  add     rsp, 60h
0x140088077  pop     r15
0x140088079  pop     r14
0x14008807b  pop     r13
0x14008807d  pop     r12
0x14008807f  pop     rdi
0x140088080  pop     rsi
0x140088081  pop     rbp
0x140088082  retn
```
