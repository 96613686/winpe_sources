# CSdSafeguard::SafeguardCatalogFile(ushort const *,ushort const *,ushort const *,_FILETIME,ISdAsyncPriv *)

- ea: `0x1800378e0`
- end: `0x180037bb5`
- name: `?SafeguardCatalogFile@CSdSafeguard@@UEAAJPEBG00U_FILETIME@@PEAUISdAsyncPriv@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(CSdSafeguard *__hidden this, LPCWSTR lpExistingFileName, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME, struct ISdAsyncPriv *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800083e4`
- `0x1800378e0`
- `0x180038578`
- `0x1800392c0`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e8c4`
- `0x18009f560`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180037a50`
- `msvcrt!wcsrchr` at `0x180037a50`
- `KERNEL32!SetFileAttributesW` at `0x180037a17`
- `KERNEL32!SetFileAttributesW` at `0x180037b13`
- `KERNEL32!SetFileAttributesW` at `0x180037a17`
- `KERNEL32!SetFileAttributesW` at `0x180037b13`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800379c1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180037b45`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800379c1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180037b45`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180037ab6`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180037ab6`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::SafeguardCatalogFile(
        PSECURITY_DESCRIPTOR *this,
        LPCWSTR lpExistingFileName,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _FILETIME a5,
        struct ISdAsyncPriv *a6)
{
  __int16 v10; // ax
  int TargetDirectory; // ebx
  __int64 v12; // rcx
  wchar_t *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-49h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+38h] [rbp-41h] BYREF
  LPCWSTR v19[2]; // [rsp+48h] [rbp-31h] BYREF
  int v20; // [rsp+58h] [rbp-21h] BYREF
  __int16 v21; // [rsp+5Ch] [rbp-1Dh]
  __int16 v22; // [rsp+5Eh] [rbp-1Bh]
  struct _FILETIME v23; // [rsp+D8h] [rbp+5Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "CSdSafeguard::SafeguardCatalogFile", 0x1EBu, 1u);
  v19[0] = (LPCWSTR)qword_1800EE510;
  v19[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  SystemTimeAsFileTime = 0;
  v23 = 0;
  v10 = 499;
  if ( !lpExistingFileName )
    goto LABEL_21;
  v21 = 499;
  v10 = 500;
  if ( !a3 )
    goto LABEL_21;
  v21 = 500;
  v10 = 501;
  if ( !a4 )
    goto LABEL_21;
  v21 = 501;
  v10 = 502;
  if ( !a6 )
    goto LABEL_21;
  v20 = 0;
  v21 = 502;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids,
      lpExistingFileName);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  TargetDirectory = CSdSafeguard::_CreateTargetDirectory(
                      (CSdSafeguard *)this,
                      a3,
                      a4,
                      a5,
                      L"Catalogs",
                      (struct CBsString *)lpFileName);
  v20 = TargetDirectory;
  v10 = 512;
  if ( TargetDirectory < 0 )
    goto LABEL_22;
  v21 = 512;
  if ( !SetFileAttributesW(lpFileName[0], 2u) )
  {
    TargetDirectory = GetLastFailureAsHRESULT(v12);
    v20 = TargetDirectory;
    v10 = 513;
LABEL_22:
    v22 = v10;
    goto LABEL_23;
  }
  v20 = 0;
  v21 = 513;
  v13 = wcsrchr(lpExistingFileName, 0x5Cu);
  if ( !v13 || !v13[1] )
  {
    v10 = 520;
LABEL_21:
    TargetDirectory = -2147024809;
    v20 = -2147024809;
    goto LABEL_22;
  }
  v20 = 0;
  v21 = 520;
  TargetDirectory = CBsString::Set((CBsString *)v19, lpFileName[0], L"\\", v13 + 1);
  v20 = TargetDirectory;
  v10 = 526;
  if ( TargetDirectory < 0 )
    goto LABEL_22;
  v21 = 526;
  if ( !SetFileSecurityW(lpExistingFileName, 4u, this[8]) )
  {
    TargetDirectory = GetLastFailureAsHRESULT(v14);
    v20 = TargetDirectory;
    v10 = 531;
    goto LABEL_22;
  }
  v20 = 0;
  v21 = 531;
  TargetDirectory = CSdSafeguard::_PrivateCopyFile((CSdSafeguard *)this, lpExistingFileName, v19[0], a6);
  v20 = TargetDirectory;
  v10 = 533;
  if ( TargetDirectory < 0 )
    goto LABEL_22;
  v21 = 533;
  if ( !SetFileAttributesW(v19[0], 2u) )
  {
    TargetDirectory = GetLastFailureAsHRESULT(v15);
    v20 = TargetDirectory;
    v10 = 535;
    goto LABEL_22;
  }
  v20 = 0;
  v21 = 535;
  GetSystemTimeAsFileTime(&v23);
  this[16] = (char *)this[16] + (*(_QWORD *)&v23 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL;
  TargetDirectory = v20;
LABEL_23:
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)v19);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return (unsigned int)TargetDirectory;
}

```

## disassembly

```asm
0x1800378e0  push    rbp
0x1800378e2  push    rbx
0x1800378e3  push    rsi
0x1800378e4  push    rdi
0x1800378e5  push    r12
0x1800378e7  push    r14
0x1800378e9  lea     rbp, [rsp-1Fh]
0x1800378ee  sub     rsp, 98h
0x1800378f5  mov     rbx, r9
0x1800378f8  mov     r14, r8
0x1800378fb  mov     rdi, rdx
0x1800378fe  mov     rsi, rcx
0x180037901  mov     r9d, 1; unsigned __int16
0x180037907  mov     r8d, 1EBh; unsigned __int16
0x18003790d  lea     rdx, aCsdsafeguardSa_0; "CSdSafeguard::SafeguardCatalogFile"
0x180037914  lea     rcx, [rbp+47h+var_68]; this
0x180037918  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003791d  lea     rax, qword_1800EE510
0x180037924  mov     [rbp+47h+var_78], rax
0x180037928  xor     r12d, r12d
0x18003792b  mov     [rbp+47h+var_70], r12
0x18003792f  mov     [rbp+47h+lpFileName], rax
0x180037933  mov     [rbp+47h+var_80], r12
0x180037937  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18003793b  mov     qword ptr [rbp+47h+arg_8.dwLowDateTime], r12
0x18003793f  mov     eax, 1F3h
0x180037944  test    rdi, rdi
0x180037947  jz      loc_180037B7B
0x18003794d  mov     [rbp+47h+var_64], ax
0x180037951  mov     eax, 1F4h
0x180037956  test    r14, r14
0x180037959  jz      loc_180037B7B
0x18003795f  mov     [rbp+47h+var_64], ax
0x180037963  mov     eax, 1F5h
0x180037968  test    rbx, rbx
0x18003796b  jz      loc_180037B7B
0x180037971  mov     [rbp+47h+var_64], ax
0x180037975  mov     eax, 1F6h
0x18003797a  cmp     [rbp+47h+arg_28], r12
0x18003797e  jz      loc_180037B7B
0x180037984  mov     [rbp+47h+var_68], r12d
0x180037988  mov     [rbp+47h+var_64], ax
0x18003798c  lea     rax, WPP_GLOBAL_Control
0x180037993  mov     rcx, cs:WPP_GLOBAL_Control
0x18003799a  cmp     rcx, rax
0x18003799d  jz      short loc_1800379BD
0x18003799f  test    byte ptr [rcx+1Ch], 20h
0x1800379a3  jz      short loc_1800379BD
0x1800379a5  lea     edx, [r12+0Dh]
0x1800379aa  mov     r9, rdi
0x1800379ad  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x1800379b4  mov     rcx, [rcx+10h]
0x1800379b8  call    WPP_SF_S
0x1800379bd  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800379c1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800379c8  nop     dword ptr [rax+rax+00h]
0x1800379cd  lea     rax, [rbp+47h+lpFileName]
0x1800379d1  mov     [rsp+0C0h+var_98], rax; struct CBsString *
0x1800379d6  lea     rax, c_wszGCSubpath; "Catalogs"
0x1800379dd  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x1800379e2  mov     r9, qword ptr [rbp+47h+arg_20.dwLowDateTime]; struct _FILETIME
0x1800379e6  mov     r8, rbx; unsigned __int16 *
0x1800379e9  mov     rdx, r14; unsigned __int16 *
0x1800379ec  mov     rcx, rsi; this
0x1800379ef  call    ?_CreateTargetDirectory@CSdSafeguard@@AEAAJPEBG0U_FILETIME@@0PEAVCBsString@@@Z; CSdSafeguard::_CreateTargetDirectory(ushort const *,ushort const *,_FILETIME,ushort const *,CBsString *)
0x1800379f4  mov     ebx, eax
0x1800379f6  mov     [rbp+47h+var_68], eax
0x1800379f9  test    eax, eax
0x1800379fb  mov     eax, 200h
0x180037a00  js      loc_180037B83
0x180037a06  mov     [rbp+47h+var_64], ax
0x180037a0a  mov     r14d, 2
0x180037a10  mov     edx, r14d; dwFileAttributes
0x180037a13  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x180037a17  call    cs:__imp_SetFileAttributesW
0x180037a1e  nop     dword ptr [rax+rax+00h]
0x180037a23  test    eax, eax
0x180037a25  jnz     short loc_180037A3B
0x180037a27  call    GetLastFailureAsHRESULT
0x180037a2c  mov     ebx, eax
0x180037a2e  mov     [rbp+47h+var_68], eax
0x180037a31  mov     eax, 201h
0x180037a36  jmp     loc_180037B83
0x180037a3b  mov     [rbp+47h+var_68], r12d
0x180037a3f  mov     eax, 201h
0x180037a44  mov     [rbp+47h+var_64], ax
0x180037a48  mov     edx, 5Ch ; '\'; Ch
0x180037a4d  mov     rcx, rdi; Str
0x180037a50  call    cs:__imp_wcsrchr
0x180037a57  nop     dword ptr [rax+rax+00h]
0x180037a5c  test    rax, rax
0x180037a5f  jz      loc_180037B76
0x180037a65  lea     r9, [rax+2]; unsigned __int16 *
0x180037a69  cmp     [r9], r12w
0x180037a6d  jz      loc_180037B76
0x180037a73  mov     [rbp+47h+var_68], r12d
0x180037a77  mov     eax, 208h
0x180037a7c  mov     [rbp+47h+var_64], ax
0x180037a80  lea     r8, Str; "\\"
0x180037a87  mov     rdx, [rbp+47h+lpFileName]; unsigned __int16 *
0x180037a8b  lea     rcx, [rbp+47h+var_78]; this
0x180037a8f  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x180037a94  mov     ebx, eax
0x180037a96  mov     [rbp+47h+var_68], eax
0x180037a99  test    eax, eax
0x180037a9b  mov     eax, 20Eh
0x180037aa0  js      loc_180037B83
0x180037aa6  mov     [rbp+47h+var_64], ax
0x180037aaa  mov     r8, [rsi+40h]; pSecurityDescriptor
0x180037aae  mov     edx, 4; SecurityInformation
0x180037ab3  mov     rcx, rdi; lpFileName
0x180037ab6  call    cs:__imp_SetFileSecurityW
0x180037abd  nop     dword ptr [rax+rax+00h]
0x180037ac2  test    eax, eax
0x180037ac4  jnz     short loc_180037ADA
0x180037ac6  call    GetLastFailureAsHRESULT
0x180037acb  mov     ebx, eax
0x180037acd  mov     [rbp+47h+var_68], eax
0x180037ad0  mov     eax, 213h
0x180037ad5  jmp     loc_180037B83
0x180037ada  mov     [rbp+47h+var_68], r12d
0x180037ade  mov     eax, 213h
0x180037ae3  mov     [rbp+47h+var_64], ax
0x180037ae7  mov     r9, [rbp+47h+arg_28]; struct ISdAsyncPriv *
0x180037aeb  mov     r8, [rbp+47h+var_78]; unsigned __int16 *
0x180037aef  mov     rdx, rdi; lpExistingFileName
0x180037af2  mov     rcx, rsi; this
0x180037af5  call    ?_PrivateCopyFile@CSdSafeguard@@AEAAJPEBG0PEAUISdAsyncPriv@@@Z; CSdSafeguard::_PrivateCopyFile(ushort const *,ushort const *,ISdAsyncPriv *)
0x180037afa  mov     ebx, eax
0x180037afc  mov     [rbp+47h+var_68], eax
0x180037aff  test    eax, eax
0x180037b01  mov     eax, 215h
0x180037b06  js      short loc_180037B83
0x180037b08  mov     [rbp+47h+var_64], ax
0x180037b0c  mov     edx, r14d; dwFileAttributes
0x180037b0f  mov     rcx, [rbp+47h+var_78]; lpFileName
0x180037b13  call    cs:__imp_SetFileAttributesW
0x180037b1a  nop     dword ptr [rax+rax+00h]
0x180037b1f  test    eax, eax
0x180037b21  jnz     short loc_180037B34
0x180037b23  call    GetLastFailureAsHRESULT
0x180037b28  mov     ebx, eax
0x180037b2a  mov     [rbp+47h+var_68], eax
0x180037b2d  mov     eax, 217h
0x180037b32  jmp     short loc_180037B83
0x180037b34  mov     [rbp+47h+var_68], r12d
0x180037b38  mov     eax, 217h
0x180037b3d  mov     [rbp+47h+var_64], ax
0x180037b41  lea     rcx, [rbp+47h+arg_8]; lpSystemTimeAsFileTime
0x180037b45  call    cs:__imp_GetSystemTimeAsFileTime
0x180037b4c  nop     dword ptr [rax+rax+00h]
0x180037b51  mov     rcx, qword ptr [rbp+47h+arg_8.dwLowDateTime]
0x180037b55  sub     rcx, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x180037b59  mov     rax, 346DC5D63886594Bh
0x180037b63  mul     rcx
0x180037b66  shr     rdx, 0Bh
0x180037b6a  add     [rsi+80h], rdx
0x180037b71  mov     ebx, [rbp+47h+var_68]
0x180037b74  jmp     short loc_180037B87
0x180037b76  mov     eax, 208h
0x180037b7b  mov     ebx, 80070057h
0x180037b80  mov     [rbp+47h+var_68], ebx
0x180037b83  mov     [rbp+47h+var_62], ax
0x180037b87  lea     rcx, [rbp+47h+lpFileName]; this
0x180037b8b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180037b90  lea     rcx, [rbp+47h+var_78]; this
0x180037b94  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180037b99  lea     rcx, [rbp+47h+var_68]; this
0x180037b9d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180037ba2  mov     eax, ebx
0x180037ba4  add     rsp, 98h
0x180037bab  pop     r14
0x180037bad  pop     r12
0x180037baf  pop     rdi
0x180037bb0  pop     rsi
0x180037bb1  pop     rbx
0x180037bb2  pop     rbp
0x180037bb3  retn
```
