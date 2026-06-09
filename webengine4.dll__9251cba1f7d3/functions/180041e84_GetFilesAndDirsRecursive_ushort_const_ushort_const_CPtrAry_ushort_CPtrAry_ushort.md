# GetFilesAndDirsRecursive(ushort const *,ushort const *,CPtrAry<ushort *> *,CPtrAry<ushort *> *)

- ea: `0x180041e84`
- end: `0x1800422f3`
- name: `?GetFilesAndDirsRecursive@@YAJPEBG0PEAV?$CPtrAry@PEAG@@1@Z`
- size: `1135`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1800418cc`
- `0x180041e84`
- `0x180042a58`

## callees

- `0x180002584`
- `0x180007824`
- `0x18003aba8`
- `0x18003abe4`
- `0x180041e84`
- `0x18004a28c`
- `0x18004a2dc`
- `0x18004a5c0`
- `0x18004d690`
- `0x18004d754`
- `0x18004e168`
- `0x18004e638`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180041f71`
- `KERNEL32!lstrlenW` at `0x180041f7c`
- `KERNEL32!lstrlenW` at `0x1800420f4`
- `KERNEL32!lstrlenW` at `0x180042100`
- `KERNEL32!lstrlenW` at `0x1800421aa`
- `KERNEL32!lstrlenW` at `0x1800421b5`
- `KERNEL32!lstrlenW` at `0x180041f71`
- `KERNEL32!lstrlenW` at `0x180041f7c`
- `KERNEL32!lstrlenW` at `0x1800420f4`
- `KERNEL32!lstrlenW` at `0x180042100`
- `KERNEL32!lstrlenW` at `0x1800421aa`
- `KERNEL32!lstrlenW` at `0x1800421b5`
- `KERNEL32!lstrcmpW` at `0x1800420c1`
- `KERNEL32!lstrcmpW` at `0x1800420de`
- `KERNEL32!lstrcmpW` at `0x1800420c1`
- `KERNEL32!lstrcmpW` at `0x1800420de`
- `SHLWAPI!PathFileExistsW` at `0x180041ee7`
- `SHLWAPI!PathFileExistsW` at `0x180041ee7`

## string_xrefs

- `0x180041ead`: `Getting all client file dirs and paths`
- `0x180042283`: `Getting all client file dirs and paths`

## pseudocode

```c
__int64 __fastcall GetFilesAndDirsRecursive(
        const WCHAR *a1,
        const unsigned __int16 *a2,
        CImplPtrAry *a3,
        CImplPtrAry *a4)
{
  const WCHAR *v4; // r15
  const WCHAR *v5; // r14
  unsigned int appended; // ebx
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // r13
  unsigned __int16 *v9; // rsi
  signed int v10; // r12d
  __int64 v11; // r14
  const WCHAR *v12; // rcx
  int v13; // ebx
  unsigned __int64 v14; // r15
  unsigned __int16 *v15; // rax
  signed int v16; // r12d
  __int64 v17; // r14
  int v18; // ebx
  unsigned __int64 v19; // rsi
  unsigned __int16 *v20; // rax
  const WCHAR *v21; // rcx
  int v22; // ebx
  unsigned __int64 v23; // r15
  unsigned __int16 *v24; // rax
  __int128 v26; // [rsp+30h] [rbp-28h] BYREF
  __int128 v27; // [rsp+40h] [rbp-18h] BYREF

  v4 = a2;
  v5 = a1;
  appended = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v27 = 0;
  v26 = 0;
  CSetupLogging::Log(1, "GetFilesAndDirsRecursive", 0, "Getting all client file dirs and paths");
  if ( !PathFileExistsW(v5) )
    goto LABEL_37;
  CSetupLogging::Log(1, "ListDir", 0, "Enumerating all client source files: ", v5);
  appended = ListDir(v5, 1, &v27);
  CSetupLogging::Log(appended, "ListDir", 0, "Enumerating all client source files: ", v5);
  if ( appended )
    goto LABEL_37;
  v10 = 0;
  if ( (v27 & 0xFFFFFFFC) != 0 )
  {
    v11 = 0;
    do
    {
      v12 = *(const WCHAR **)(v11 + *((_QWORD *)&v27 + 1));
      if ( v4 )
      {
        v13 = lstrlenW(v12);
        v14 = v13 + lstrlenW(v4) + 2;
        v15 = (unsigned __int16 *)MemAlloc(saturated_mul(v14, 2u));
        v7 = v15;
        if ( !v15 )
          goto LABEL_39;
        appended = StringCchCopyW(v15, v14, a2);
        if ( appended )
          goto LABEL_37;
        appended = StringCchCatW(v7, v14, L"\\");
        if ( appended )
          goto LABEL_37;
        appended = StringCchCatW(v7, v14, *(const unsigned __int16 **)(v11 + *((_QWORD *)&v27 + 1)));
        if ( appended )
          goto LABEL_37;
        v4 = a2;
      }
      else
      {
        v7 = DupStr(v12);
        if ( !v7 )
          goto LABEL_39;
      }
      appended = AppendCStrAry(a3, v7);
      if ( appended )
        goto LABEL_37;
      MemFree(v7);
      ++v10;
      v11 += 8;
    }
    while ( v10 < (int)((unsigned int)v27 >> 2) );
    v5 = a1;
  }
  CSetupLogging::Log(1, "ListDir", 0, "Enumerating all client sub directories");
  appended = ListDir(v5, 2, &v26);
  CSetupLogging::Log(appended, "ListDir", 0, "Enumerating all client sub directories");
  v7 = 0;
  if ( appended )
    goto LABEL_37;
  v16 = 0;
  if ( (v26 & 0xFFFFFFFC) == 0 )
    goto LABEL_37;
  v17 = 0;
  while ( 1 )
  {
    if ( !lstrcmpW(*(LPCWSTR *)(v17 + *((_QWORD *)&v26 + 1)), L".")
      || !lstrcmpW(*(LPCWSTR *)(v17 + *((_QWORD *)&v26 + 1)), L"..") )
    {
      goto LABEL_35;
    }
    v18 = lstrlenW(*(LPCWSTR *)(v17 + *((_QWORD *)&v26 + 1)));
    v19 = v18 + lstrlenW(a1) + 2;
    v20 = (unsigned __int16 *)MemAlloc(saturated_mul(v19, 2u));
    v8 = v20;
    if ( !v20 )
      break;
    appended = StringCchCopyW(v20, v19, a1);
    if ( appended
      || (appended = StringCchCatW(v8, v19, L"\\")) != 0
      || (appended = StringCchCatW(v8, v19, *(const unsigned __int16 **)(v17 + *((_QWORD *)&v26 + 1)))) != 0 )
    {
LABEL_36:
      v9 = 0;
      goto LABEL_37;
    }
    v21 = *(const WCHAR **)(v17 + *((_QWORD *)&v26 + 1));
    if ( v4 )
    {
      v22 = lstrlenW(v21);
      v23 = v22 + lstrlenW(v4) + 2;
      v24 = (unsigned __int16 *)MemAlloc(saturated_mul(v23, 2u));
      v9 = v24;
      if ( !v24 )
        goto LABEL_39;
      appended = StringCchCopyW(v24, v23, a2);
      if ( appended )
        goto LABEL_37;
      appended = StringCchCatW(v9, v23, L"\\");
      if ( appended )
        goto LABEL_37;
      appended = StringCchCatW(v9, v23, *(const unsigned __int16 **)(v17 + *((_QWORD *)&v26 + 1)));
      if ( appended )
        goto LABEL_37;
      v4 = a2;
    }
    else
    {
      v9 = DupStr(v21);
      if ( !v9 )
        goto LABEL_39;
    }
    appended = AppendCStrAry(a4, v9);
    if ( appended )
      goto LABEL_37;
    appended = GetFilesAndDirsRecursive(v8, v9, a3, a4);
    if ( appended )
      goto LABEL_37;
    MemFree(v9);
LABEL_35:
    ++v16;
    v17 += 8;
    if ( v16 >= (int)((unsigned int)v26 >> 2) )
      goto LABEL_36;
  }
  v9 = 0;
LABEL_39:
  appended = -2147024882;
LABEL_37:
  CSetupLogging::Log(appended, "GetFilesAndDirsRecursive", 0, "Getting all client file dirs and paths");
  MemFree(v7);
  MemFree(v8);
  MemFree(v9);
  CleanupCStrAry((CImplAry *)&v27);
  CleanupCStrAry((CImplAry *)&v26);
  CImplAry::~CImplAry((CImplAry *)&v26);
  CImplAry::~CImplAry((CImplAry *)&v27);
  return appended;
}

```

## disassembly

```asm
0x180041e84  mov     rax, rsp
0x180041e87  mov     [rax+20h], r9
0x180041e8b  mov     [rax+18h], r8
0x180041e8f  mov     [rax+10h], rdx
0x180041e93  mov     [rax+8], rcx
0x180041e97  push    rbp
0x180041e98  push    rbx
0x180041e99  push    rsi
0x180041e9a  push    rdi
0x180041e9b  push    r12
0x180041e9d  push    r13
0x180041e9f  push    r14
0x180041ea1  push    r15
0x180041ea3  mov     rbp, rsp
0x180041ea6  sub     rsp, 58h
0x180041eaa  mov     r15, rdx
0x180041ead  lea     r9, aGettingAllClie; "Getting all client file dirs and paths"
0x180041eb4  mov     r14, rcx
0x180041eb7  lea     rdx, aGetfilesanddir; "GetFilesAndDirsRecursive"
0x180041ebe  xorps   xmm0, xmm0
0x180041ec1  xorps   xmm1, xmm1
0x180041ec4  xor     ebx, ebx
0x180041ec6  xor     r8d, r8d; unsigned int
0x180041ec9  xor     edi, edi
0x180041ecb  xor     r13d, r13d
0x180041ece  xor     esi, esi
0x180041ed0  movups  [rbp+var_18], xmm0
0x180041ed4  lea     r12d, [rbx+1]
0x180041ed8  mov     ecx, r12d; int
0x180041edb  movups  [rbp+var_28], xmm1
0x180041edf  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180041ee4  mov     rcx, r14; pszPath
0x180041ee7  call    cs:__imp_PathFileExistsW
0x180041eed  test    eax, eax
0x180041eef  jz      loc_180042283
0x180041ef5  lea     r9, aEnumeratingAll; "Enumerating all client source files: "
0x180041efc  mov     [rsp+58h+var_38], r14; unsigned __int16 *
0x180041f01  xor     r8d, r8d; unsigned int
0x180041f04  lea     rdx, aListdir; "ListDir"
0x180041f0b  mov     ecx, r12d; int
0x180041f0e  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180041f13  lea     r8, [rbp+var_18]
0x180041f17  mov     edx, r12d
0x180041f1a  mov     rcx, r14
0x180041f1d  call    ?ListDir@@YAJPEBGKPEAV?$CPtrAry@PEAG@@@Z; ListDir(ushort const *,ulong,CPtrAry<ushort *> *)
0x180041f22  lea     r9, aEnumeratingAll; "Enumerating all client source files: "
0x180041f29  mov     [rsp+58h+var_38], r14; unsigned __int16 *
0x180041f2e  xor     r8d, r8d; unsigned int
0x180041f31  lea     rdx, aListdir; "ListDir"
0x180041f38  mov     ecx, eax; int
0x180041f3a  mov     ebx, eax
0x180041f3c  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180041f41  test    ebx, ebx
0x180041f43  jnz     loc_180042283
0x180041f49  xor     r12d, r12d
0x180041f4c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041f50  test    dword ptr [rbp+var_18], 0FFFFFFFCh
0x180041f57  jbe     loc_180042050
0x180041f5d  xor     r14d, r14d
0x180041f60  mov     rcx, qword ptr [rbp+var_18+8]
0x180041f64  mov     rcx, [r14+rcx]; Src
0x180041f68  test    r15, r15
0x180041f6b  jz      loc_180042002
0x180041f71  call    cs:__imp_lstrlenW
0x180041f77  mov     rcx, r15; lpString
0x180041f7a  mov     ebx, eax
0x180041f7c  call    cs:__imp_lstrlenW
0x180041f82  lea     ecx, [rax+2]
0x180041f85  mov     eax, 2
0x180041f8a  add     ecx, ebx
0x180041f8c  movsxd  r15, ecx
0x180041f8f  mul     r15
0x180041f92  cmovo   rax, rdi
0x180041f96  mov     rcx, rax; unsigned __int64
0x180041f99  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180041f9e  mov     rdi, rax
0x180041fa1  test    rax, rax
0x180041fa4  jz      loc_1800422EC
0x180041faa  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180041fae  mov     rdx, r15; unsigned __int64
0x180041fb1  mov     rcx, rax; unsigned __int16 *
0x180041fb4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041fb9  mov     ebx, eax
0x180041fbb  test    eax, eax
0x180041fbd  jnz     loc_180042283
0x180041fc3  lea     r8, SubBlock; "\\"
0x180041fca  mov     rdx, r15; unsigned __int64
0x180041fcd  mov     rcx, rdi; unsigned __int16 *
0x180041fd0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041fd5  mov     ebx, eax
0x180041fd7  test    eax, eax
0x180041fd9  jnz     loc_180042283
0x180041fdf  mov     r8, qword ptr [rbp+var_18+8]
0x180041fe3  mov     rdx, r15; unsigned __int64
0x180041fe6  mov     rcx, rdi; unsigned __int16 *
0x180041fe9  mov     r8, [r14+r8]; unsigned __int16 *
0x180041fed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041ff2  mov     ebx, eax
0x180041ff4  test    eax, eax
0x180041ff6  jnz     loc_180042283
0x180041ffc  mov     r15, [rbp+arg_8]
0x180042000  jmp     short loc_180042013
0x180042002  call    ?DupStr@@YAPEAGPEBG@Z; DupStr(ushort const *)
0x180042007  mov     rdi, rax
0x18004200a  test    rax, rax
0x18004200d  jz      loc_1800422EC
0x180042013  mov     rcx, [rbp+arg_10]; this
0x180042017  mov     rdx, rdi; Src
0x18004201a  call    ?AppendCStrAry@@YAJPEAV?$CPtrAry@PEAG@@PEAG@Z; AppendCStrAry(CPtrAry<ushort *> *,ushort *)
0x18004201f  mov     ebx, eax
0x180042021  test    eax, eax
0x180042023  jnz     loc_180042283
0x180042029  mov     rcx, rdi; lpMem
0x18004202c  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180042031  mov     eax, dword ptr [rbp+var_18]
0x180042034  inc     r12d
0x180042037  shr     eax, 2
0x18004203a  add     r14, 8
0x18004203e  cmp     r12d, eax
0x180042041  jge     short loc_18004204C
0x180042043  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180042047  jmp     loc_180041F60
0x18004204c  mov     r14, [rbp+lpString]
0x180042050  xor     r8d, r8d; unsigned int
0x180042053  lea     r9, aEnumeratingAll_0; "Enumerating all client sub directories"
0x18004205a  lea     rdx, aListdir; "ListDir"
0x180042061  lea     ecx, [r8+1]; int
0x180042065  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x18004206a  lea     r8, [rbp+var_28]
0x18004206e  mov     edx, 2
0x180042073  mov     rcx, r14
0x180042076  call    ?ListDir@@YAJPEBGKPEAV?$CPtrAry@PEAG@@@Z; ListDir(ushort const *,ulong,CPtrAry<ushort *> *)
0x18004207b  lea     r9, aEnumeratingAll_0; "Enumerating all client sub directories"
0x180042082  xor     r8d, r8d; unsigned int
0x180042085  lea     rdx, aListdir; "ListDir"
0x18004208c  mov     ecx, eax; int
0x18004208e  mov     ebx, eax
0x180042090  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180042095  xor     edi, edi
0x180042097  test    ebx, ebx
0x180042099  jnz     loc_180042283
0x18004209f  xor     r12d, r12d
0x1800420a2  test    dword ptr [rbp+var_28], 0FFFFFFFCh
0x1800420a9  jbe     loc_180042283
0x1800420af  xor     r14d, r14d
0x1800420b2  mov     rcx, qword ptr [rbp+var_28+8]
0x1800420b6  lea     rdx, asc_1800766B0; "."
0x1800420bd  mov     rcx, [r14+rcx]; lpString1
0x1800420c1  call    cs:__imp_lstrcmpW
0x1800420c7  test    eax, eax
0x1800420c9  jz      loc_18004226B
0x1800420cf  mov     rcx, qword ptr [rbp+var_28+8]
0x1800420d3  lea     rdx, asc_1800766B4; ".."
0x1800420da  mov     rcx, [r14+rcx]; lpString1
0x1800420de  call    cs:__imp_lstrcmpW
0x1800420e4  test    eax, eax
0x1800420e6  jz      loc_18004226B
0x1800420ec  mov     rcx, qword ptr [rbp+var_28+8]
0x1800420f0  mov     rcx, [r14+rcx]; lpString
0x1800420f4  call    cs:__imp_lstrlenW
0x1800420fa  mov     rcx, [rbp+lpString]; lpString
0x1800420fe  mov     ebx, eax
0x180042100  call    cs:__imp_lstrlenW
0x180042106  lea     ecx, [rax+2]
0x180042109  mov     eax, 2
0x18004210e  add     ecx, ebx
0x180042110  movsxd  rsi, ecx
0x180042113  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004211a  mul     rsi
0x18004211d  cmovo   rax, rcx
0x180042121  mov     rcx, rax; unsigned __int64
0x180042124  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180042129  mov     r13, rax
0x18004212c  test    rax, rax
0x18004212f  jz      loc_1800422EA
0x180042135  mov     r8, [rbp+lpString]; unsigned __int16 *
0x180042139  mov     rdx, rsi; unsigned __int64
0x18004213c  mov     rcx, rax; unsigned __int16 *
0x18004213f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042144  mov     ebx, eax
0x180042146  test    eax, eax
0x180042148  jnz     loc_180042281
0x18004214e  lea     r8, SubBlock; "\\"
0x180042155  mov     rdx, rsi; unsigned __int64
0x180042158  mov     rcx, r13; unsigned __int16 *
0x18004215b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180042160  mov     ebx, eax
0x180042162  test    eax, eax
0x180042164  jnz     loc_180042281
0x18004216a  mov     r8, qword ptr [rbp+var_28+8]
0x18004216e  mov     rdx, rsi; unsigned __int64
0x180042171  mov     rcx, r13; unsigned __int16 *
0x180042174  mov     r8, [r14+r8]; unsigned __int16 *
0x180042178  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004217d  mov     ebx, eax
0x18004217f  test    eax, eax
0x180042181  jnz     loc_180042281
0x180042187  mov     rcx, qword ptr [rbp+var_28+8]
0x18004218b  mov     rcx, [r14+rcx]; Src
0x18004218f  test    r15, r15
0x180042192  jnz     short loc_1800421AA
0x180042194  call    ?DupStr@@YAPEAGPEBG@Z; DupStr(ushort const *)
0x180042199  mov     rsi, rax
0x18004219c  test    rax, rax
0x18004219f  jz      loc_1800422EC
0x1800421a5  jmp     loc_180042238
0x1800421aa  call    cs:__imp_lstrlenW
0x1800421b0  mov     rcx, r15; lpString
0x1800421b3  mov     ebx, eax
0x1800421b5  call    cs:__imp_lstrlenW
0x1800421bb  lea     ecx, [rax+2]
0x1800421be  mov     eax, 2
0x1800421c3  add     ecx, ebx
0x1800421c5  movsxd  r15, ecx
0x1800421c8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800421cf  mul     r15
0x1800421d2  cmovo   rax, rcx
0x1800421d6  mov     rcx, rax; unsigned __int64
0x1800421d9  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x1800421de  mov     rsi, rax
0x1800421e1  test    rax, rax
0x1800421e4  jz      loc_1800422EC
0x1800421ea  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x1800421ee  mov     rdx, r15; unsigned __int64
0x1800421f1  mov     rcx, rax; unsigned __int16 *
0x1800421f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800421f9  mov     ebx, eax
0x1800421fb  test    eax, eax
0x1800421fd  jnz     loc_180042283
0x180042203  lea     r8, SubBlock; "\\"
0x18004220a  mov     rdx, r15; unsigned __int64
0x18004220d  mov     rcx, rsi; unsigned __int16 *
0x180042210  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180042215  mov     ebx, eax
0x180042217  test    eax, eax
0x180042219  jnz     short loc_180042283
0x18004221b  mov     r8, qword ptr [rbp+var_28+8]
0x18004221f  mov     rdx, r15; unsigned __int64
0x180042222  mov     rcx, rsi; unsigned __int16 *
0x180042225  mov     r8, [r14+r8]; unsigned __int16 *
0x180042229  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004222e  mov     ebx, eax
0x180042230  test    eax, eax
0x180042232  jnz     short loc_180042283
0x180042234  mov     r15, [rbp+arg_8]
0x180042238  mov     rcx, [rbp+arg_18]; this
0x18004223c  mov     rdx, rsi; Src
0x18004223f  call    ?AppendCStrAry@@YAJPEAV?$CPtrAry@PEAG@@PEAG@Z; AppendCStrAry(CPtrAry<ushort *> *,ushort *)
0x180042244  mov     ebx, eax
0x180042246  test    eax, eax
0x180042248  jnz     short loc_180042283
0x18004224a  mov     r9, [rbp+arg_18]
0x18004224e  mov     rdx, rsi
0x180042251  mov     r8, [rbp+arg_10]
0x180042255  mov     rcx, r13
0x180042258  call    ?GetFilesAndDirsRecursive@@YAJPEBG0PEAV?$CPtrAry@PEAG@@1@Z; GetFilesAndDirsRecursive(ushort const *,ushort const *,CPtrAry<ushort *> *,CPtrAry<ushort *> *)
0x18004225d  mov     ebx, eax
0x18004225f  test    eax, eax
0x180042261  jnz     short loc_180042283
0x180042263  mov     rcx, rsi; lpMem
0x180042266  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18004226b  mov     eax, dword ptr [rbp+var_28]
0x18004226e  inc     r12d
0x180042271  shr     eax, 2
0x180042274  add     r14, 8
0x180042278  cmp     r12d, eax
0x18004227b  jl      loc_1800420B2
0x180042281  xor     esi, esi
0x180042283  lea     r9, aGettingAllClie; "Getting all client file dirs and paths"
0x18004228a  xor     r8d, r8d; unsigned int
0x18004228d  lea     rdx, aGetfilesanddir; "GetFilesAndDirsRecursive"
0x180042294  mov     ecx, ebx; int
0x180042296  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x18004229b  mov     rcx, rdi; lpMem
0x18004229e  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800422a3  mov     rcx, r13; lpMem
0x1800422a6  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800422ab  mov     rcx, rsi; lpMem
0x1800422ae  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800422b3  lea     rcx, [rbp+var_18]; this
0x1800422b7  call    ?CleanupCStrAry@@YAXPEAV?$CPtrAry@PEAG@@@Z; CleanupCStrAry(CPtrAry<ushort *> *)
0x1800422bc  lea     rcx, [rbp+var_28]; this
0x1800422c0  call    ?CleanupCStrAry@@YAXPEAV?$CPtrAry@PEAG@@@Z; CleanupCStrAry(CPtrAry<ushort *> *)
0x1800422c5  lea     rcx, [rbp+var_28]; this
0x1800422c9  call    ??1CImplAry@@QEAA@XZ; CImplAry::~CImplAry(void)
0x1800422ce  lea     rcx, [rbp+var_18]; this
0x1800422d2  call    ??1CImplAry@@QEAA@XZ; CImplAry::~CImplAry(void)
0x1800422d7  mov     eax, ebx
0x1800422d9  add     rsp, 58h
0x1800422dd  pop     r15
0x1800422df  pop     r14
0x1800422e1  pop     r13
0x1800422e3  pop     r12
0x1800422e5  pop     rdi
0x1800422e6  pop     rsi
0x1800422e7  pop     rbx
0x1800422e8  pop     rbp
0x1800422e9  retn
0x1800422ea  xor     esi, esi
0x1800422ec  mov     ebx, 8007000Eh
  ... truncated ...
```
