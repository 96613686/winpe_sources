# CleanupTempDir(CASPNET_VER_LIST *)

- ea: `0x18003785c`
- end: `0x1800379d9`
- name: `?CleanupTempDir@@YAJPEAVCASPNET_VER_LIST@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(struct CASPNET_VER_LIST *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18003ef38`

## callees

- `0x180002584`
- `0x180007824`
- `0x18000b354`
- `0x18003785c`
- `0x18003abe4`
- `0x18004abf0`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800378c9`
- `KERNEL32!lstrlenW` at `0x1800378d8`
- `KERNEL32!lstrlenW` at `0x180037920`
- `KERNEL32!lstrlenW` at `0x1800378c9`
- `KERNEL32!lstrlenW` at `0x1800378d8`
- `KERNEL32!lstrlenW` at `0x180037920`

## string_xrefs

- `0x1800378cf`: `Temporary ASP.NET Files`
- `0x18003793c`: `Temporary ASP.NET Files`
- `0x18003787b`: `Deleting the Temporary ASP.NET directory`
- `0x18003798d`: `Deleting the Temporary ASP.NET directory`
- `0x180037998`: `Deleting the Temporary ASP.NET directory`
- `0x180037886`: `CleanupTempDir`

## pseudocode

```c
__int64 __fastcall CleanupTempDir(struct CASPNET_VER_LIST *this)
{
  unsigned int v1; // ebx
  WCHAR *v3; // rdi
  int v4; // esi
  const WCHAR *InstallPath; // rax
  const unsigned __int16 *v6; // rbp
  int v7; // ebx
  unsigned __int64 v8; // r15
  unsigned __int16 *v9; // rax
  int v10; // eax
  int v11; // ecx

  v1 = 0;
  v3 = 0;
  CSetupLogging::Log(1, "CleanupTempDir", 0, "Deleting the Temporary ASP.NET directory", 0);
  v4 = 0;
  if ( (*(_DWORD *)this & 0xFFFFFFFC) != 0 )
  {
    while ( 1 )
    {
      InstallPath = CASPNET_VER_LIST::GetInstallPath(this, v4);
      v6 = InstallPath;
      if ( !InstallPath )
        break;
      v7 = lstrlenW(InstallPath);
      v8 = v7 + lstrlenW(L"Temporary ASP.NET Files") + 2;
      v9 = (unsigned __int16 *)MemAllocClear(saturated_mul(v8, 2u));
      v3 = v9;
      if ( !v9 )
      {
        v1 = -2147024882;
        goto LABEL_13;
      }
      v1 = StringCchCopyW(v9, v8, v6);
      if ( !v1 )
      {
        v10 = lstrlenW(v3) - 1;
        if ( v10 > 0 && v3[v10] != 92 )
          v3[v10 + 1] = 92;
        v1 = StringCchCatW(v3, v8, L"Temporary ASP.NET Files");
        if ( !v1 )
        {
          v1 = RemoveDirectoryRecursively(v3, 1);
          MemFree(v3);
          v3 = 0;
          if ( ++v4 < *(_DWORD *)this >> 2 )
            continue;
        }
      }
      goto LABEL_13;
    }
    v1 = -2147418113;
    v3 = 0;
  }
LABEL_13:
  v11 = 0;
  if ( (_WORD)v1 != 3 )
    v11 = v1;
  CSetupLogging::Log(v11, "Deleting the Temporary ASP.NET directory", 0, "Deleting the Temporary ASP.NET directory", 0);
  MemFree(v3);
  return v1;
}

```

## disassembly

```asm
0x18003785c  mov     rax, rsp
0x18003785f  mov     [rax+8], rbx
0x180037863  mov     [rax+10h], rbp
0x180037867  mov     [rax+18h], rsi
0x18003786b  mov     [rax+20h], rdi
0x18003786f  push    r13
0x180037871  push    r14
0x180037873  push    r15
0x180037875  sub     rsp, 30h
0x180037879  xor     ebx, ebx
0x18003787b  lea     r9, aDeletingTheTem; "Deleting the Temporary ASP.NET director"...
0x180037882  and     [rax-28h], rbx
0x180037886  lea     rdx, aCleanuptempdir; "CleanupTempDir"
0x18003788d  mov     r14, rcx
0x180037890  xor     r8d, r8d; unsigned int
0x180037893  xor     edi, edi
0x180037895  lea     ecx, [rbx+1]; int
0x180037898  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003789d  xor     esi, esi
0x18003789f  test    dword ptr [r14], 0FFFFFFFCh
0x1800378a6  jbe     loc_18003798B
0x1800378ac  lea     r13d, [rbx+5Ch]
0x1800378b0  mov     edx, esi; int
0x1800378b2  mov     rcx, r14; this
0x1800378b5  call    ?GetInstallPath@CASPNET_VER_LIST@@QEAAPEAGH@Z; CASPNET_VER_LIST::GetInstallPath(int)
0x1800378ba  mov     rbp, rax
0x1800378bd  test    rax, rax
0x1800378c0  jz      loc_180037984
0x1800378c6  mov     rcx, rax; lpString
0x1800378c9  call    cs:__imp_lstrlenW
0x1800378cf  lea     rcx, aTemporaryAspNe; "Temporary ASP.NET Files"
0x1800378d6  mov     ebx, eax
0x1800378d8  call    cs:__imp_lstrlenW
0x1800378de  lea     ecx, [rax+2]
0x1800378e1  mov     eax, 2
0x1800378e6  add     ecx, ebx
0x1800378e8  movsxd  r15, ecx
0x1800378eb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800378f2  mul     r15
0x1800378f5  cmovo   rax, rcx
0x1800378f9  mov     rcx, rax; unsigned __int64
0x1800378fc  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180037901  mov     rdi, rax
0x180037904  test    rax, rax
0x180037907  jz      short loc_18003797D
0x180037909  mov     r8, rbp; unsigned __int16 *
0x18003790c  mov     rdx, r15; unsigned __int64
0x18003790f  mov     rcx, rax; unsigned __int16 *
0x180037912  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037917  mov     ebx, eax
0x180037919  test    eax, eax
0x18003791b  jnz     short loc_18003798B
0x18003791d  mov     rcx, rdi; lpString
0x180037920  call    cs:__imp_lstrlenW
0x180037926  dec     eax
0x180037928  test    eax, eax
0x18003792a  jle     short loc_18003793C
0x18003792c  movsxd  rcx, eax
0x18003792f  cmp     [rdi+rcx*2], r13w
0x180037934  jz      short loc_18003793C
0x180037936  mov     [rdi+rcx*2+2], r13w
0x18003793c  lea     r8, aTemporaryAspNe; "Temporary ASP.NET Files"
0x180037943  mov     rdx, r15; unsigned __int64
0x180037946  mov     rcx, rdi; unsigned __int16 *
0x180037949  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003794e  mov     ebx, eax
0x180037950  test    eax, eax
0x180037952  jnz     short loc_18003798B
0x180037954  lea     edx, [rax+1]; int
0x180037957  mov     rcx, rdi; unsigned __int16 *
0x18003795a  call    ?RemoveDirectoryRecursively@@YAJPEAGH@Z; RemoveDirectoryRecursively(ushort *,int)
0x18003795f  mov     rcx, rdi; lpMem
0x180037962  mov     ebx, eax
0x180037964  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180037969  mov     eax, [r14]
0x18003796c  xor     edi, edi
0x18003796e  shr     eax, 2
0x180037971  inc     esi
0x180037973  cmp     esi, eax
0x180037975  jl      loc_1800378B0
0x18003797b  jmp     short loc_18003798B
0x18003797d  mov     ebx, 8007000Eh
0x180037982  jmp     short loc_18003798B
0x180037984  mov     ebx, 8000FFFFh
0x180037989  xor     edi, edi
0x18003798b  xor     ecx, ecx
0x18003798d  lea     r9, aDeletingTheTem; "Deleting the Temporary ASP.NET director"...
0x180037994  cmp     bx, 3
0x180037998  lea     rdx, aDeletingTheTem; "Deleting the Temporary ASP.NET director"...
0x18003799f  cmovnz  ecx, ebx; int
0x1800379a2  and     [rsp+48h+var_28], 0
0x1800379a8  xor     r8d, r8d; unsigned int
0x1800379ab  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x1800379b0  mov     rcx, rdi; lpMem
0x1800379b3  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800379b8  mov     rbp, [rsp+48h+arg_8]
0x1800379bd  mov     eax, ebx
0x1800379bf  mov     rbx, [rsp+48h+arg_0]
0x1800379c4  mov     rsi, [rsp+48h+arg_10]
0x1800379c9  mov     rdi, [rsp+48h+arg_18]
0x1800379ce  add     rsp, 30h
0x1800379d2  pop     r15
0x1800379d4  pop     r14
0x1800379d6  pop     r13
0x1800379d8  retn
```
