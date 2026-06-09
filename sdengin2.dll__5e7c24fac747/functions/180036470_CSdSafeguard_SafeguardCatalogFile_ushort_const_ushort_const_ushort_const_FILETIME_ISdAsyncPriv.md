# CSdSafeguard::SafeguardCatalogFile(ushort const *,ushort const *,ushort const *,_FILETIME,ISdAsyncPriv *)

- ea: `0x180036470`
- end: `0x180036720`
- name: `?SafeguardCatalogFile@CSdSafeguard@@UEAAJPEBG00U_FILETIME@@PEAUISdAsyncPriv@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *this, LPCWSTR lpExistingFileName, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME, struct ISdAsyncPriv *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008240`
- `0x180036470`
- `0x1800370d8`
- `0x180037d84`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a20c`
- `0x18009ae34`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800365d4`
- `msvcrt!wcsrchr` at `0x1800365d4`
- `KERNEL32!SetFileAttributesW` at `0x1800365a1`
- `KERNEL32!SetFileAttributesW` at `0x18003668b`
- `KERNEL32!SetFileAttributesW` at `0x1800365a1`
- `KERNEL32!SetFileAttributesW` at `0x18003668b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036551`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800366b7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036551`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800366b7`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180036634`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180036634`

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
  v19[0] = (LPCWSTR)qword_1800E8530;
  v19[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
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
0x180036470  push    rbp
0x180036472  push    rbx
0x180036473  push    rsi
0x180036474  push    rdi
0x180036475  push    r12
0x180036477  push    r14
0x180036479  lea     rbp, [rsp-1Fh]
0x18003647e  sub     rsp, 98h
0x180036485  mov     rbx, r9
0x180036488  mov     r14, r8
0x18003648b  mov     rdi, rdx
0x18003648e  mov     rsi, rcx
0x180036491  mov     r9d, 1; unsigned __int16
0x180036497  mov     r8d, 1EBh; unsigned __int16
0x18003649d  lea     rdx, aCsdsafeguardSa_0; "CSdSafeguard::SafeguardCatalogFile"
0x1800364a4  lea     rcx, [rbp+47h+var_68]; this
0x1800364a8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800364ad  lea     rax, qword_1800E8530
0x1800364b4  mov     [rbp+47h+var_78], rax
0x1800364b8  xor     r12d, r12d
0x1800364bb  mov     [rbp+47h+var_70], r12
0x1800364bf  mov     [rbp+47h+lpFileName], rax
0x1800364c3  mov     [rbp+47h+var_80], r12
0x1800364c7  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800364cb  mov     qword ptr [rbp+47h+arg_8.dwLowDateTime], r12
0x1800364cf  mov     eax, 1F3h
0x1800364d4  test    rdi, rdi
0x1800364d7  jz      loc_1800366E7
0x1800364dd  mov     [rbp+47h+var_64], ax
0x1800364e1  mov     eax, 1F4h
0x1800364e6  test    r14, r14
0x1800364e9  jz      loc_1800366E7
0x1800364ef  mov     [rbp+47h+var_64], ax
0x1800364f3  mov     eax, 1F5h
0x1800364f8  test    rbx, rbx
0x1800364fb  jz      loc_1800366E7
0x180036501  mov     [rbp+47h+var_64], ax
0x180036505  mov     eax, 1F6h
0x18003650a  cmp     [rbp+47h+arg_28], r12
0x18003650e  jz      loc_1800366E7
0x180036514  mov     [rbp+47h+var_68], r12d
0x180036518  mov     [rbp+47h+var_64], ax
0x18003651c  lea     rax, WPP_GLOBAL_Control
0x180036523  mov     rcx, cs:WPP_GLOBAL_Control
0x18003652a  cmp     rcx, rax
0x18003652d  jz      short loc_18003654D
0x18003652f  test    byte ptr [rcx+1Ch], 20h
0x180036533  jz      short loc_18003654D
0x180036535  lea     edx, [r12+0Dh]
0x18003653a  mov     r9, rdi
0x18003653d  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x180036544  mov     rcx, [rcx+10h]
0x180036548  call    WPP_SF_S
0x18003654d  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180036551  call    cs:__imp_GetSystemTimeAsFileTime
0x180036557  lea     rax, [rbp+47h+lpFileName]
0x18003655b  mov     [rsp+0C0h+var_98], rax; struct CBsString *
0x180036560  lea     rax, c_wszGCSubpath; "Catalogs"
0x180036567  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18003656c  mov     r9, qword ptr [rbp+47h+arg_20.dwLowDateTime]; struct _FILETIME
0x180036570  mov     r8, rbx; unsigned __int16 *
0x180036573  mov     rdx, r14; unsigned __int16 *
0x180036576  mov     rcx, rsi; this
0x180036579  call    ?_CreateTargetDirectory@CSdSafeguard@@AEAAJPEBG0U_FILETIME@@0PEAVCBsString@@@Z; CSdSafeguard::_CreateTargetDirectory(ushort const *,ushort const *,_FILETIME,ushort const *,CBsString *)
0x18003657e  mov     ebx, eax
0x180036580  mov     [rbp+47h+var_68], eax
0x180036583  test    eax, eax
0x180036585  mov     eax, 200h
0x18003658a  js      loc_1800366EF
0x180036590  mov     [rbp+47h+var_64], ax
0x180036594  mov     r14d, 2
0x18003659a  mov     edx, r14d; dwFileAttributes
0x18003659d  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x1800365a1  call    cs:__imp_SetFileAttributesW
0x1800365a7  test    eax, eax
0x1800365a9  jnz     short loc_1800365BF
0x1800365ab  call    GetLastFailureAsHRESULT
0x1800365b0  mov     ebx, eax
0x1800365b2  mov     [rbp+47h+var_68], eax
0x1800365b5  mov     eax, 201h
0x1800365ba  jmp     loc_1800366EF
0x1800365bf  mov     [rbp+47h+var_68], r12d
0x1800365c3  mov     eax, 201h
0x1800365c8  mov     [rbp+47h+var_64], ax
0x1800365cc  mov     edx, 5Ch ; '\'; Ch
0x1800365d1  mov     rcx, rdi; Str
0x1800365d4  call    cs:__imp_wcsrchr
0x1800365da  test    rax, rax
0x1800365dd  jz      loc_1800366E2
0x1800365e3  lea     r9, [rax+2]; unsigned __int16 *
0x1800365e7  cmp     [r9], r12w
0x1800365eb  jz      loc_1800366E2
0x1800365f1  mov     [rbp+47h+var_68], r12d
0x1800365f5  mov     eax, 208h
0x1800365fa  mov     [rbp+47h+var_64], ax
0x1800365fe  lea     r8, Str; "\\"
0x180036605  mov     rdx, [rbp+47h+lpFileName]; unsigned __int16 *
0x180036609  lea     rcx, [rbp+47h+var_78]; this
0x18003660d  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x180036612  mov     ebx, eax
0x180036614  mov     [rbp+47h+var_68], eax
0x180036617  test    eax, eax
0x180036619  mov     eax, 20Eh
0x18003661e  js      loc_1800366EF
0x180036624  mov     [rbp+47h+var_64], ax
0x180036628  mov     r8, [rsi+40h]; pSecurityDescriptor
0x18003662c  mov     edx, 4; SecurityInformation
0x180036631  mov     rcx, rdi; lpFileName
0x180036634  call    cs:__imp_SetFileSecurityW
0x18003663a  test    eax, eax
0x18003663c  jnz     short loc_180036652
0x18003663e  call    GetLastFailureAsHRESULT
0x180036643  mov     ebx, eax
0x180036645  mov     [rbp+47h+var_68], eax
0x180036648  mov     eax, 213h
0x18003664d  jmp     loc_1800366EF
0x180036652  mov     [rbp+47h+var_68], r12d
0x180036656  mov     eax, 213h
0x18003665b  mov     [rbp+47h+var_64], ax
0x18003665f  mov     r9, [rbp+47h+arg_28]; struct ISdAsyncPriv *
0x180036663  mov     r8, [rbp+47h+var_78]; unsigned __int16 *
0x180036667  mov     rdx, rdi; lpExistingFileName
0x18003666a  mov     rcx, rsi; this
0x18003666d  call    ?_PrivateCopyFile@CSdSafeguard@@AEAAJPEBG0PEAUISdAsyncPriv@@@Z; CSdSafeguard::_PrivateCopyFile(ushort const *,ushort const *,ISdAsyncPriv *)
0x180036672  mov     ebx, eax
0x180036674  mov     [rbp+47h+var_68], eax
0x180036677  test    eax, eax
0x180036679  mov     eax, 215h
0x18003667e  js      short loc_1800366EF
0x180036680  mov     [rbp+47h+var_64], ax
0x180036684  mov     edx, r14d; dwFileAttributes
0x180036687  mov     rcx, [rbp+47h+var_78]; lpFileName
0x18003668b  call    cs:__imp_SetFileAttributesW
0x180036691  test    eax, eax
0x180036693  jnz     short loc_1800366A6
0x180036695  call    GetLastFailureAsHRESULT
0x18003669a  mov     ebx, eax
0x18003669c  mov     [rbp+47h+var_68], eax
0x18003669f  mov     eax, 217h
0x1800366a4  jmp     short loc_1800366EF
0x1800366a6  mov     [rbp+47h+var_68], r12d
0x1800366aa  mov     eax, 217h
0x1800366af  mov     [rbp+47h+var_64], ax
0x1800366b3  lea     rcx, [rbp+47h+arg_8]; lpSystemTimeAsFileTime
0x1800366b7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800366bd  mov     rcx, qword ptr [rbp+47h+arg_8.dwLowDateTime]
0x1800366c1  sub     rcx, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x1800366c5  mov     rax, 346DC5D63886594Bh
0x1800366cf  mul     rcx
0x1800366d2  shr     rdx, 0Bh
0x1800366d6  add     [rsi+80h], rdx
0x1800366dd  mov     ebx, [rbp+47h+var_68]
0x1800366e0  jmp     short loc_1800366F3
0x1800366e2  mov     eax, 208h
0x1800366e7  mov     ebx, 80070057h
0x1800366ec  mov     [rbp+47h+var_68], ebx
0x1800366ef  mov     [rbp+47h+var_62], ax
0x1800366f3  lea     rcx, [rbp+47h+lpFileName]; this
0x1800366f7  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800366fc  lea     rcx, [rbp+47h+var_78]; this
0x180036700  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180036705  lea     rcx, [rbp+47h+var_68]; this
0x180036709  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003670e  mov     eax, ebx
0x180036710  add     rsp, 98h
0x180036717  pop     r14
0x180036719  pop     r12
0x18003671b  pop     rdi
0x18003671c  pop     rsi
0x18003671d  pop     rbx
0x18003671e  pop     rbp
0x18003671f  retn
```
