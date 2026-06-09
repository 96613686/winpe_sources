# WiaTrace::GetBanner(ulong,char const *,_SYSTEMTIME *,char *,ulong)

- ea: `0x180001010`
- end: `0x1800012eb`
- name: `?GetBanner@WiaTrace@@YAJKPEBDPEAU_SYSTEMTIME@@PEADK@Z`
- size: `731`
- prototype: `__int64 __fastcall(WiaTrace *this, const char *, const char *, struct _SYSTEMTIME *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180001300`
- `0x180001fb0`

## callees

- `0x180001010`
- `0x180001f20`
- `0x1800024e0`
- `0x180002980`
- `0x1800031fa`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x1800010ff`
- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x1800010ff`
- `KERNEL32!GetCurrentProcessId` at `0x180001140`
- `KERNEL32!GetCurrentProcessId` at `0x180001140`
- `KERNEL32!GetLocalTime` at `0x1800011fb`
- `KERNEL32!GetLocalTime` at `0x18000128e`
- `KERNEL32!GetLocalTime` at `0x1800011fb`
- `KERNEL32!GetLocalTime` at `0x18000128e`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180001212`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180001212`
- `KERNEL32!GetModuleFileNameA` at `0x180001092`
- `KERNEL32!GetModuleFileNameA` at `0x180001092`

## string_xrefs

- `0x18000114b`: `\n**************** Started trace for Module: [%s] in Executable [%s] ProcessID: [%lu] at %04lu/%02lu/%02lu %02lu:%02lu:%02lu:%03lu ****************\n`

## pseudocode

```c
__int64 __fastcall WiaTrace::GetBanner(WiaTrace *this, const char *a2, const char *a3, struct _SYSTEMTIME *a4)
{
  int v6; // ebx
  int v7; // edi
  int v8; // esi
  int v9; // r14d
  int v10; // r15d
  int v11; // r12d
  int v12; // r13d
  DWORD CurrentProcessId; // eax
  const char *SystemTime; // [rsp+78h] [rbp-90h]
  struct _SYSTEMTIME SystemTime_8; // [rsp+80h] [rbp-88h] BYREF
  CHAR Filename[272]; // [rsp+98h] [rbp-70h] BYREF
  char Ext[256]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v19[512]; // [rsp+2A8h] [rbp+1A0h] BYREF

  *(_QWORD *)&SystemTime_8.wYear = a4;
  SystemTime = a2;
  if ( !a4 )
    return 2147500035LL;
  switch ( (_DWORD)this )
  {
    case 2:
      memset_0(Filename, 0, 0x105u);
      SystemTime_8 = 0;
      GetLocalTime(&SystemTime_8);
      ExpandEnvironmentStringsA("%systemroot%\\Debug\\WIA\\wiatrace.bak.log", Filename, 0x105u);
      StringCchPrintfA(
        (char *)a4,
        0x100u,
        "\r\n"
        "**************** File Rollover at %04lu/%02lu/%02lu %02lu:%02lu:%02lu:%03lu, previous file stored at '%s' ****************\r\n",
        SystemTime_8.wYear,
        SystemTime_8.wMonth,
        SystemTime_8.wDay,
        SystemTime_8.wHour,
        SystemTime_8.wMinute,
        SystemTime_8.wSecond,
        SystemTime_8.wMilliseconds,
        Filename);
      break;
    case 1:
      memset_0(Filename, 0, 0x104u);
      GetModuleFileNameA(0, Filename, 0x104u);
      memset_0(v19, 0, sizeof(v19));
      memset_0(Ext, 0, sizeof(Ext));
      _splitpath_s(Filename, 0, 0, 0, 0, v19, 0x200u, Ext, 0x100u);
      StringCchCatA(v19, 0x200u, Ext);
      v6 = *((unsigned __int16 *)a3 + 7);
      v7 = *((unsigned __int16 *)a3 + 6);
      v8 = *((unsigned __int16 *)a3 + 5);
      v9 = *((unsigned __int16 *)a3 + 4);
      v10 = *((unsigned __int16 *)a3 + 3);
      v11 = *((unsigned __int16 *)a3 + 1);
      v12 = *(unsigned __int16 *)a3;
      CurrentProcessId = GetCurrentProcessId();
      StringCchPrintfA(
        *(char **)&SystemTime_8.wYear,
        0x100u,
        "\r\n"
        "**************** Started trace for Module: [%s] in Executable [%s] ProcessID: [%lu] at %04lu/%02lu/%02lu %02lu:%"
        "02lu:%02lu:%03lu ****************\r\n",
        SystemTime,
        v19,
        CurrentProcessId,
        v12,
        v11,
        v10,
        v9,
        v8,
        v7,
        v6);
      break;
    case 3:
      SystemTime_8 = 0;
      GetLocalTime(&SystemTime_8);
      StringCchPrintfA(
        (char *)a4,
        0x100u,
        "\r\n"
        "**************** Maximum file size exceeded at %04lu/%02lu/%02lu %02lu:%02lu:%02lu:%03lu - file wrapping is turn"
        "ed off. ****************\r\n",
        SystemTime_8.wYear,
        SystemTime_8.wMonth,
        SystemTime_8.wDay,
        SystemTime_8.wHour,
        SystemTime_8.wMinute,
        SystemTime_8.wSecond,
        SystemTime_8.wMilliseconds);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  push    rbp
0x180001014  push    rdi
0x180001015  push    r13
0x180001017  lea     rbp, [r11-3E8h]
0x18000101e  sub     rsp, 4D0h
0x180001025  mov     rax, cs:__security_cookie
0x18000102c  xor     rax, rsp
0x18000102f  mov     [rbp+3E0h+var_40], rax
0x180001036  mov     qword ptr [rsp+4E0h+SystemTime.wHour], r9
0x18000103b  mov     rdi, r9
0x18000103e  mov     qword ptr [rsp+4E0h+SystemTime.wYear], rdx
0x180001043  mov     r13, r8
0x180001046  test    r9, r9
0x180001049  jz      loc_1800011D6
0x18000104f  mov     [r11+8], rbx
0x180001053  cmp     ecx, 2
0x180001056  jz      loc_1800011DD
0x18000105c  cmp     ecx, 1
0x18000105f  jnz     loc_180001278
0x180001065  mov     [r11-20h], rsi
0x180001069  lea     rcx, [rbp+3E0h+Filename]; void *
0x18000106d  mov     [r11-28h], r12
0x180001071  xor     edx, edx; Val
0x180001073  mov     [r11-30h], r14
0x180001077  mov     r8d, 104h; Size
0x18000107d  mov     [r11-38h], r15
0x180001081  call    memset_0
0x180001086  mov     r8d, 104h; nSize
0x18000108c  lea     rdx, [rbp+3E0h+Filename]; lpFilename
0x180001090  xor     ecx, ecx; hModule
0x180001092  call    cs:__imp_GetModuleFileNameA
0x180001098  xor     edx, edx; Val
0x18000109a  lea     rcx, [rbp+3E0h+var_240]; void *
0x1800010a1  mov     r8d, 200h; Size
0x1800010a7  call    memset_0
0x1800010ac  xor     edx, edx; Val
0x1800010ae  lea     rcx, [rbp+3E0h+var_340]; void *
0x1800010b5  mov     r8d, 100h; Size
0x1800010bb  call    memset_0
0x1800010c0  mov     [rsp+4E0h+ExtCount], 100h; ExtCount
0x1800010c9  lea     rax, [rbp+3E0h+var_340]
0x1800010d0  mov     [rsp+4E0h+Ext], rax; Ext
0x1800010d5  lea     rcx, [rbp+3E0h+Filename]; FullPath
0x1800010d9  lea     rax, [rbp+3E0h+var_240]
0x1800010e0  mov     [rsp+4E0h+FilenameCount], 200h; FilenameCount
0x1800010e9  mov     [rsp+4E0h+var_4B8], rax; Filename
0x1800010ee  xor     r9d, r9d; Dir
0x1800010f1  xor     r8d, r8d; DriveCount
0x1800010f4  mov     [rsp+4E0h+DirCount], 0; DirCount
0x1800010fd  xor     edx, edx; Drive
0x1800010ff  call    cs:__imp__splitpath_s
0x180001105  lea     r8, [rbp+3E0h+var_340]; char *
0x18000110c  mov     edx, 200h; unsigned __int64
0x180001111  lea     rcx, [rbp+3E0h+var_240]; char *
0x180001118  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000111d  movzx   ebx, word ptr [r13+0Eh]
0x180001122  movzx   edi, word ptr [r13+0Ch]
0x180001127  movzx   esi, word ptr [r13+0Ah]
0x18000112c  movzx   r14d, word ptr [r13+8]
0x180001131  movzx   r15d, word ptr [r13+6]
0x180001136  movzx   r12d, word ptr [r13+2]
0x18000113b  movzx   r13d, word ptr [r13+0]
0x180001140  call    cs:__imp_GetCurrentProcessId
0x180001146  mov     r9, qword ptr [rsp+4E0h+SystemTime.wYear]
0x18000114b  lea     r8, aStartedTraceFo; "\r\n**************** Started trace for "...
0x180001152  mov     rcx, qword ptr [rsp+4E0h+SystemTime.wHour]; char *
0x180001157  mov     edx, 100h; unsigned __int64
0x18000115c  mov     [rsp+60h], ebx
0x180001160  mov     [rsp+4E0h+var_488], edi
0x180001164  mov     [rsp+4E0h+var_490], esi
0x180001168  mov     dword ptr [rsp+4E0h+var_498], r14d
0x18000116d  mov     dword ptr [rsp+4E0h+ExtCount], r15d
0x180001172  mov     dword ptr [rsp+4E0h+Ext], r12d
0x180001177  mov     dword ptr [rsp+4E0h+FilenameCount], r13d
0x18000117c  mov     dword ptr [rsp+4E0h+var_4B8], eax
0x180001180  lea     rax, [rbp+3E0h+var_240]
0x180001187  mov     [rsp+4E0h+DirCount], rax
0x18000118c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180001191  mov     r15, [rsp+4E0h+var_30]
0x180001199  mov     r14, [rsp+4E0h+var_28]
0x1800011a1  mov     r12, [rsp+4E0h+var_20]
0x1800011a9  mov     rsi, [rsp+4C8h]
0x1800011b1  mov     rbx, [rsp+4E0h+arg_0]
0x1800011b9  xor     eax, eax
0x1800011bb  mov     rcx, [rbp+3E0h+var_40]
0x1800011c2  xor     rcx, rsp; StackCookie
0x1800011c5  call    __security_check_cookie
0x1800011ca  add     rsp, 4D0h
0x1800011d1  pop     r13
0x1800011d3  pop     rdi
0x1800011d4  pop     rbp
0x1800011d5  retn
0x1800011d6  mov     eax, 80004003h
0x1800011db  jmp     short loc_1800011BB
0x1800011dd  xor     edx, edx; Val
0x1800011df  lea     rcx, [rbp+3E0h+Filename]; void *
0x1800011e3  mov     r8d, 105h; Size
0x1800011e9  call    memset_0
0x1800011ee  xorps   xmm0, xmm0
0x1800011f1  lea     rcx, [rsp+4E0h+SystemTime.wHour]; lpSystemTime
0x1800011f6  movups  xmmword ptr [rsp+4E0h+SystemTime.wHour], xmm0
0x1800011fb  call    cs:__imp_GetLocalTime
0x180001201  mov     r8d, 105h; nSize
0x180001207  lea     rdx, [rbp+3E0h+Filename]; lpDst
0x18000120b  lea     rcx, Src; "%systemroot%\\Debug\\WIA\\wiatrace.bak."...
0x180001212  call    cs:__imp_ExpandEnvironmentStringsA
0x180001218  movzx   edx, [rbp+3E0h+var_45C]
0x18000121c  lea     rcx, [rbp+3E0h+Filename]
0x180001220  movzx   r8d, [rbp+3E0h+var_45E]
0x180001225  movzx   eax, [rbp+3E0h+var_45A]
0x180001229  movzx   r10d, [rbp+3E0h+var_460]
0x18000122e  movzx   r11d, [rsp+4E0h+SystemTime.wMilliseconds]
0x180001234  movzx   ebx, [rsp+4E0h+SystemTime.wMinute]
0x180001239  movzx   r9d, [rsp+4E0h+SystemTime.wHour]
0x18000123f  mov     qword ptr [rsp+4E0h+var_490], rcx
0x180001244  mov     rcx, rdi; char *
0x180001247  mov     dword ptr [rsp+4E0h+var_498], eax
0x18000124b  mov     dword ptr [rsp+4E0h+ExtCount], edx
0x18000124f  mov     edx, 100h; unsigned __int64
0x180001254  mov     dword ptr [rsp+4E0h+Ext], r8d
0x180001259  lea     r8, aFileRolloverAt; "\r\n**************** File Rollover at %"...
0x180001260  mov     dword ptr [rsp+4E0h+FilenameCount], r10d
0x180001265  mov     dword ptr [rsp+4E0h+var_4B8], r11d
0x18000126a  mov     dword ptr [rsp+4E0h+DirCount], ebx
0x18000126e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180001273  jmp     loc_1800011B1
0x180001278  cmp     ecx, 3
0x18000127b  jnz     loc_1800011B1
0x180001281  xorps   xmm0, xmm0
0x180001284  lea     rcx, [rsp+4E0h+SystemTime.wHour]; lpSystemTime
0x180001289  movups  xmmword ptr [rsp+4E0h+SystemTime.wHour], xmm0
0x18000128e  call    cs:__imp_GetLocalTime
0x180001294  movzx   ecx, [rbp+3E0h+var_45C]
0x180001298  movzx   edx, [rbp+3E0h+var_45E]
0x18000129c  movzx   r8d, [rbp+3E0h+var_460]
0x1800012a1  movzx   eax, [rbp+3E0h+var_45A]
0x1800012a5  movzx   r10d, [rsp+4E0h+SystemTime.wMilliseconds]
0x1800012ab  movzx   r11d, [rsp+4E0h+SystemTime.wMinute]
0x1800012b1  movzx   r9d, [rsp+4E0h+SystemTime.wHour]
0x1800012b7  mov     dword ptr [rsp+4E0h+var_498], eax
0x1800012bb  mov     dword ptr [rsp+4E0h+ExtCount], ecx
0x1800012bf  mov     rcx, rdi; char *
0x1800012c2  mov     dword ptr [rsp+4E0h+Ext], edx
0x1800012c6  mov     edx, 100h; unsigned __int64
0x1800012cb  mov     dword ptr [rsp+4E0h+FilenameCount], r8d
0x1800012d0  lea     r8, aMaximumFileSiz; "\r\n**************** Maximum file size "...
0x1800012d7  mov     dword ptr [rsp+4E0h+var_4B8], r10d
0x1800012dc  mov     dword ptr [rsp+4E0h+DirCount], r11d
0x1800012e1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800012e6  jmp     loc_1800011B1
```
