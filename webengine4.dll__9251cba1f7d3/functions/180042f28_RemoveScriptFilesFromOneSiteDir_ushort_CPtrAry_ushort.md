# RemoveScriptFilesFromOneSiteDir(ushort *,CPtrAry<ushort *> *)

- ea: `0x180042f28`
- end: `0x180043116`
- name: `?RemoveScriptFilesFromOneSiteDir@@YAJPEAGPEAV?$CPtrAry@PEAG@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x180042a58`

## callees

- `0x180002584`
- `0x180007824`
- `0x180012b30`
- `0x18003aba8`
- `0x18003abe4`
- `0x180042f28`
- `0x18004d350`
- `0x18004d754`
- `0x18004d7d4`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180042f89`
- `KERNEL32!lstrlenW` at `0x180042f94`
- `KERNEL32!lstrlenW` at `0x180043031`
- `KERNEL32!lstrlenW` at `0x180042f89`
- `KERNEL32!lstrlenW` at `0x180042f94`
- `KERNEL32!lstrlenW` at `0x180043031`
- `KERNEL32!DeleteFileW` at `0x180043048`
- `KERNEL32!DeleteFileW` at `0x180043048`
- `SHLWAPI!PathFileExistsW` at `0x180043020`
- `SHLWAPI!PathFileExistsW` at `0x180043020`

## string_xrefs

- `0x180042f4b`: `Remove the client side script or web admin files from a site directory`
- `0x1800430d0`: `Remove the client side script or web admin files from a site directory`
- `0x180042f55`: `RemoveScriptFilesFromOneSiteDir`
- `0x1800430da`: `RemoveScriptFilesFromOneSiteDir`
- `0x180043068`: `DeleteFile`
- `0x180043087`: `DeleteFile`

## pseudocode

```c
__int64 __fastcall RemoveScriptFilesFromOneSiteDir(LPCWSTR lpString, __int64 a2)
{
  const WCHAR *v3; // rdi
  unsigned int LastWin32Error; // ebx
  unsigned __int16 *v5; // r12
  int v6; // esi
  __int64 v7; // r14
  const WCHAR *v8; // r13
  int v9; // ebx
  unsigned __int64 v10; // rbp
  SIZE_T v11; // rax
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rdi

  v3 = lpString;
  LastWin32Error = 0;
  v5 = 0;
  CSetupLogging::Log(
    1,
    "RemoveScriptFilesFromOneSiteDir",
    0,
    "Remove the client side script or web admin files from a site directory");
  v6 = 0;
  if ( (*(_DWORD *)a2 & 0xFFFFFFFC) != 0 )
  {
    v7 = 0;
    do
    {
      v8 = *(const WCHAR **)(v7 + *(_QWORD *)(a2 + 8));
      v9 = lstrlenW(v8);
      v10 = v9 + lstrlenW(v3) + 2;
      v11 = 2 * v10;
      if ( !is_mul_ok(v10, 2u) )
        v11 = -1;
      v12 = (unsigned __int16 *)MemReAlloc(v5, v11);
      v13 = v12;
      if ( !v12 )
      {
        LastWin32Error = -2147024882;
        break;
      }
      v5 = v12;
      LastWin32Error = StringCchCopyW(v12, v10, lpString);
      if ( LastWin32Error )
        break;
      LastWin32Error = StringCchCatW(v5, v10, L"\\");
      if ( LastWin32Error )
        break;
      LastWin32Error = StringCchCatW(v5, v10, v8);
      if ( LastWin32Error )
        break;
      if ( PathFileExistsW(v5) )
      {
        if ( lstrlenW(v5) >= 260 )
        {
          LastWin32Error = -2147024690;
          goto LABEL_14;
        }
        if ( !DeleteFileW(v13) )
        {
          LastWin32Error = GetLastWin32Error();
LABEL_14:
          CSetupLogging::Log(1, "DeleteFile", 0, "Deleting file in: ", v13);
          CSetupLogging::Log(LastWin32Error, "DeleteFile", 0, "Deleting file in: ", v13);
          XspLogEvent(0x8000042B);
          if ( LastWin32Error )
            break;
        }
      }
      ++v6;
      v3 = lpString;
      v7 += 8;
    }
    while ( v6 < *(_DWORD *)a2 >> 2 );
  }
  CSetupLogging::Log(
    LastWin32Error,
    "RemoveScriptFilesFromOneSiteDir",
    0,
    "Remove the client side script or web admin files from a site directory");
  MemFree(0);
  MemFree(v5);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180042f28  mov     rax, rsp
0x180042f2b  mov     [rax+10h], rbx
0x180042f2f  mov     [rax+18h], rbp
0x180042f33  mov     [rax+20h], rsi
0x180042f37  mov     [rax+8], rcx
0x180042f3b  push    rdi
0x180042f3c  push    r12
0x180042f3e  push    r13
0x180042f40  push    r14
0x180042f42  push    r15
0x180042f44  sub     rsp, 30h
0x180042f48  mov     r15, rdx
0x180042f4b  lea     r9, aRemoveTheClien; "Remove the client side script or web ad"...
0x180042f52  mov     rdi, rcx
0x180042f55  lea     rdx, aRemovescriptfi; "RemoveScriptFilesFromOneSiteDir"
0x180042f5c  xor     ebx, ebx
0x180042f5e  xor     r8d, r8d; unsigned int
0x180042f61  xor     r12d, r12d
0x180042f64  lea     ecx, [rbx+1]; int
0x180042f67  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180042f6c  xor     esi, esi
0x180042f6e  test    dword ptr [r15], 0FFFFFFFCh
0x180042f75  jbe     loc_1800430D0
0x180042f7b  xor     r14d, r14d
0x180042f7e  mov     rax, [r15+8]
0x180042f82  mov     r13, [r14+rax]
0x180042f86  mov     rcx, r13; lpString
0x180042f89  call    cs:__imp_lstrlenW
0x180042f8f  mov     rcx, rdi; lpString
0x180042f92  mov     ebx, eax
0x180042f94  call    cs:__imp_lstrlenW
0x180042f9a  lea     ecx, [rax+2]
0x180042f9d  mov     eax, 2
0x180042fa2  add     ecx, ebx
0x180042fa4  movsxd  rbp, ecx
0x180042fa7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180042fae  mul     rbp
0x180042fb1  cmovo   rax, rcx
0x180042fb5  mov     rcx, r12; lpMem
0x180042fb8  mov     rdx, rax; dwBytes
0x180042fbb  call    ?MemReAlloc@@YAPEAXPEAX_K@Z; MemReAlloc(void *,unsigned __int64)
0x180042fc0  mov     rdi, rax
0x180042fc3  test    rax, rax
0x180042fc6  jz      loc_1800430CB
0x180042fcc  mov     r8, [rsp+58h+arg_0]; unsigned __int16 *
0x180042fd1  mov     rdx, rbp; unsigned __int64
0x180042fd4  mov     rcx, rax; unsigned __int16 *
0x180042fd7  mov     r12, rax
0x180042fda  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042fdf  mov     ebx, eax
0x180042fe1  test    eax, eax
0x180042fe3  jnz     loc_1800430D0
0x180042fe9  lea     r8, SubBlock; "\\"
0x180042ff0  mov     rdx, rbp; unsigned __int64
0x180042ff3  mov     rcx, r12; unsigned __int16 *
0x180042ff6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180042ffb  mov     ebx, eax
0x180042ffd  test    eax, eax
0x180042fff  jnz     loc_1800430D0
0x180043005  mov     r8, r13; unsigned __int16 *
0x180043008  mov     rdx, rbp; unsigned __int64
0x18004300b  mov     rcx, r12; unsigned __int16 *
0x18004300e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180043013  mov     ebx, eax
0x180043015  test    eax, eax
0x180043017  jnz     loc_1800430D0
0x18004301d  mov     rcx, r12; pszPath
0x180043020  call    cs:__imp_PathFileExistsW
0x180043026  test    eax, eax
0x180043028  jz      loc_1800430B0
0x18004302e  mov     rcx, r12; lpString
0x180043031  call    cs:__imp_lstrlenW
0x180043037  cmp     eax, 104h
0x18004303c  jl      short loc_180043045
0x18004303e  mov     ebx, 800700CEh
0x180043043  jmp     short loc_180043059
0x180043045  mov     rcx, rdi; lpFileName
0x180043048  call    cs:__imp_DeleteFileW
0x18004304e  test    eax, eax
0x180043050  jnz     short loc_1800430B0
0x180043052  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180043057  mov     ebx, eax
0x180043059  xor     r8d, r8d; unsigned int
0x18004305c  mov     [rsp+58h+var_38], rdi; unsigned __int16 *
0x180043061  lea     r9, aDeletingFileIn; "Deleting file in: "
0x180043068  lea     rdx, aDeletefile; "DeleteFile"
0x18004306f  lea     ecx, [r8+1]; int
0x180043073  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180043078  lea     r9, aDeletingFileIn; "Deleting file in: "
0x18004307f  mov     [rsp+58h+var_38], rdi; unsigned __int16 *
0x180043084  xor     r8d, r8d; unsigned int
0x180043087  lea     rdx, aDeletefile; "DeleteFile"
0x18004308e  mov     ecx, ebx; int
0x180043090  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180043095  mov     r9d, ebx
0x180043098  lea     rdx, aS08x; "%s^%08x"
0x18004309f  mov     r8, rdi
0x1800430a2  mov     ecx, 8000042Bh; dwEventID
0x1800430a7  call    XspLogEvent
0x1800430ac  test    ebx, ebx
0x1800430ae  jnz     short loc_1800430D0
0x1800430b0  mov     eax, [r15]
0x1800430b3  inc     esi
0x1800430b5  mov     rdi, [rsp+58h+arg_0]
0x1800430ba  add     r14, 8
0x1800430be  shr     eax, 2
0x1800430c1  cmp     esi, eax
0x1800430c3  jl      loc_180042F7E
0x1800430c9  jmp     short loc_1800430D0
0x1800430cb  mov     ebx, 8007000Eh
0x1800430d0  lea     r9, aRemoveTheClien; "Remove the client side script or web ad"...
0x1800430d7  xor     r8d, r8d; unsigned int
0x1800430da  lea     rdx, aRemovescriptfi; "RemoveScriptFilesFromOneSiteDir"
0x1800430e1  mov     ecx, ebx; int
0x1800430e3  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800430e8  xor     ecx, ecx; lpMem
0x1800430ea  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800430ef  mov     rcx, r12; lpMem
0x1800430f2  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800430f7  mov     rbp, [rsp+58h+arg_10]
0x1800430fc  mov     eax, ebx
0x1800430fe  mov     rbx, [rsp+58h+arg_8]
0x180043103  mov     rsi, [rsp+58h+arg_18]
0x180043108  add     rsp, 30h
0x18004310c  pop     r15
0x18004310e  pop     r14
0x180043110  pop     r13
0x180043112  pop     r12
0x180043114  pop     rdi
0x180043115  retn
```
