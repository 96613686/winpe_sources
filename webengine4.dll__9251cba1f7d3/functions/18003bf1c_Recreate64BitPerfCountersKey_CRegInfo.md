# Recreate64BitPerfCountersKey(CRegInfo *)

- ea: `0x18003bf1c`
- end: `0x18003c1e7`
- name: `?Recreate64BitPerfCountersKey@@YAJPEAVCRegInfo@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(struct CRegInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ea8c`

## callees

- `0x180007824`
- `0x1800370b4`
- `0x180037df0`
- `0x18003bf1c`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003c073`
- `KERNEL32!CloseHandle` at `0x18003c073`
- `KERNEL32!lstrlenW` at `0x18003c07e`
- `KERNEL32!lstrlenW` at `0x18003c07e`
- `KERNEL32!CreateFileW` at `0x18003c05a`
- `KERNEL32!CreateFileW` at `0x18003c05a`
- `ADVAPI32!RegCloseKey` at `0x18003c1b3`
- `ADVAPI32!RegCloseKey` at `0x18003c1b3`
- `ADVAPI32!RegOpenKeyExW` at `0x18003c158`
- `ADVAPI32!RegOpenKeyExW` at `0x18003c158`
- `ADVAPI32!RegSetValueExW` at `0x18003c195`
- `ADVAPI32!RegSetValueExW` at `0x18003c195`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003c11a`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003c11a`

## string_xrefs

- `0x18003c016`: `aspnet_perf.dll`
- `0x18003bf52`: `OpenPerfCommonData`
- `0x18003bf5e`: `ClosePerfCommonData`
- `0x18003bf6a`: `CollectPerfCommonData`
- `0x18003c125`: `SYSTEM\CurrentControlSet\Services\ASP.NET_64\Performance`
- `0x18003c14a`: `SYSTEM\CurrentControlSet\Services\ASP.NET_64\Performance`

## pseudocode

```c
__int64 __fastcall Recreate64BitPerfCountersKey(struct CRegInfo *a1)
{
  unsigned int PerfCounterEntryPoints; // ebx
  const unsigned __int16 *v2; // rdi
  WCHAR *v3; // rcx
  __int64 v4; // rdx
  WCHAR v5; // ax
  WCHAR *v6; // rax
  HANDLE FileW; // rax
  unsigned int LastWin32Error; // eax
  int v9; // eax
  __int64 v10; // r8
  WCHAR *v11; // rcx
  DWORD v12; // esi
  WCHAR v13; // ax
  WCHAR *v14; // rax
  LSTATUS v15; // eax
  HKEY phkResult; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v18[3]; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR FileName[520]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR CommandLine[520]; // [rsp+478h] [rbp+370h] BYREF

  v18[0] = L"OpenPerfCommonData";
  v18[1] = L"ClosePerfCommonData";
  v18[2] = L"CollectPerfCommonData";
  PerfCounterEntryPoints = 0;
  phkResult = 0;
  if ( a1 )
  {
    v2 = (const unsigned __int16 *)*((_QWORD *)a1 + 7);
    if ( v2 )
    {
      v3 = FileName;
      v4 = 520;
      do
      {
        if ( v4 == -2147483126 )
          break;
        v5 = *(WCHAR *)((char *)v3 + (char *)v2 - (char *)FileName);
        if ( !v5 )
          break;
        *v3++ = v5;
        --v4;
      }
      while ( v4 );
      v6 = v3 - 1;
      if ( v4 )
        v6 = v3;
      *v6 = 0;
      PerfCounterEntryPoints = v4 == 0 ? 0x8007007A : 0;
      if ( v4 )
      {
        PerfCounterEntryPoints = StringCchCatW(FileName, 0x208u, L"\\");
        if ( !PerfCounterEntryPoints )
        {
          PerfCounterEntryPoints = StringCchCatW(FileName, 0x208u, L"aspnet_perf.dll");
          if ( !PerfCounterEntryPoints )
          {
            FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
            if ( FileW == (HANDLE)-1LL )
            {
              LastWin32Error = GetLastWin32Error();
            }
            else
            {
              CloseHandle(FileW);
              v9 = lstrlenW(FileName);
              v10 = 520;
              v11 = CommandLine;
              v12 = 2 * v9 + 2;
              do
              {
                if ( v10 == -2147483126 )
                  break;
                v13 = *(WCHAR *)((char *)v11 + (char *)L"u " - (char *)CommandLine);
                if ( !v13 )
                  break;
                *v11++ = v13;
                --v10;
              }
              while ( v10 );
              v14 = v11 - 1;
              if ( v10 )
                v14 = v11;
              *v14 = 0;
              PerfCounterEntryPoints = v10 == 0 ? 0x8007007A : 0;
              if ( !v10 )
                goto LABEL_30;
              PerfCounterEntryPoints = StringCchCatW(CommandLine, 0x208u, L"ASP.NET_64");
              if ( PerfCounterEntryPoints )
                goto LABEL_30;
              UnloadPerfCounterTextStringsW(CommandLine, 1);
              PerfCounterEntryPoints = CreatePerfCounterEntryPoints(
                                         L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET_64\\Performance",
                                         (const unsigned __int16 **)v18);
              if ( PerfCounterEntryPoints )
                goto LABEL_30;
              v15 = RegOpenKeyExW(
                      HKEY_LOCAL_MACHINE,
                      L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET_64\\Performance",
                      0,
                      0x20006u,
                      &phkResult);
              if ( v15 || (v15 = RegSetValueExW(phkResult, L"Library", 0, 1u, (const BYTE *)FileName, v12)) != 0 )
              {
                PerfCounterEntryPoints = (unsigned __int16)v15 | 0x80070000;
                if ( v15 <= 0 )
                  PerfCounterEntryPoints = v15;
                goto LABEL_30;
              }
              LastWin32Error = CallLoadPerfCounterTextStrings(v2);
            }
            PerfCounterEntryPoints = LastWin32Error;
          }
        }
LABEL_30:
        if ( phkResult )
          RegCloseKey(phkResult);
      }
    }
  }
  return PerfCounterEntryPoints;
}

```

## disassembly

```asm
0x18003bf1c  mov     rax, rsp
0x18003bf1f  mov     [rax+8], rbx
0x18003bf23  mov     [rax+10h], rsi
0x18003bf27  mov     [rax+18h], rdi
0x18003bf2b  push    rbp
0x18003bf2c  push    r12
0x18003bf2e  push    r14
0x18003bf30  lea     rbp, [rax-7A8h]
0x18003bf37  sub     rsp, 890h
0x18003bf3e  mov     rax, cs:__security_cookie
0x18003bf45  xor     rax, rsp
0x18003bf48  mov     [rbp+7A0h+var_20], rax
0x18003bf4f  xor     r14d, r14d
0x18003bf52  lea     rax, aOpenperfcommon; "OpenPerfCommonData"
0x18003bf59  mov     [rsp+8A0h+var_858], rax
0x18003bf5e  lea     rax, aCloseperfcommo; "ClosePerfCommonData"
0x18003bf65  mov     [rsp+8A0h+var_850], rax
0x18003bf6a  lea     rax, aCollectperfcom; "CollectPerfCommonData"
0x18003bf71  mov     qword ptr [rsp+8A0h+var_848], rax
0x18003bf76  mov     ebx, r14d
0x18003bf79  mov     [rsp+8A0h+phkResult], r14
0x18003bf7e  test    rcx, rcx
0x18003bf81  jz      loc_18003C1B9
0x18003bf87  mov     rdi, [rcx+38h]
0x18003bf8b  test    rdi, rdi
0x18003bf8e  jz      loc_18003C1B9
0x18003bf94  mov     r12d, 208h
0x18003bf9a  lea     rax, [rsp+8A0h+FileName]
0x18003bf9f  mov     r8, rdi
0x18003bfa2  lea     rcx, [rsp+8A0h+FileName]
0x18003bfa7  mov     edx, r12d
0x18003bfaa  sub     r8, rax
0x18003bfad  lea     rax, [rdx+7FFFFDF6h]
0x18003bfb4  test    rax, rax
0x18003bfb7  jz      short loc_18003BFD0
0x18003bfb9  movzx   eax, word ptr [r8+rcx]
0x18003bfbe  test    ax, ax
0x18003bfc1  jz      short loc_18003BFD0
0x18003bfc3  mov     [rcx], ax
0x18003bfc6  add     rcx, 2
0x18003bfca  sub     rdx, 1
0x18003bfce  jnz     short loc_18003BFAD
0x18003bfd0  test    rdx, rdx
0x18003bfd3  lea     rax, [rcx-2]
0x18003bfd7  cmovnz  rax, rcx
0x18003bfdb  mov     [rax], r14w
0x18003bfdf  mov     rax, rdx
0x18003bfe2  neg     rax
0x18003bfe5  sbb     ebx, ebx
0x18003bfe7  not     ebx
0x18003bfe9  and     ebx, 8007007Ah
0x18003bfef  test    rdx, rdx
0x18003bff2  jz      loc_18003C1B9
0x18003bff8  lea     r8, SubBlock; "\\"
0x18003bfff  mov     rdx, r12; unsigned __int64
0x18003c002  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x18003c007  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c00c  mov     ebx, eax
0x18003c00e  test    eax, eax
0x18003c010  jnz     loc_18003C1A9
0x18003c016  lea     r8, aAspnetPerfDll; "aspnet_perf.dll"
0x18003c01d  mov     rdx, r12; unsigned __int64
0x18003c020  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x18003c025  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c02a  mov     ebx, eax
0x18003c02c  test    eax, eax
0x18003c02e  jnz     loc_18003C1A9
0x18003c034  mov     [rsp+8A0h+hTemplateFile], r14; hTemplateFile
0x18003c039  lea     r8d, [rax+1]; dwShareMode
0x18003c03d  mov     [rsp+8A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003c045  lea     rcx, [rsp+8A0h+FileName]; lpFileName
0x18003c04a  xor     r9d, r9d; lpSecurityAttributes
0x18003c04d  mov     [rsp+8A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003c055  mov     edx, 80000000h; dwDesiredAccess
0x18003c05a  call    cs:__imp_CreateFileW
0x18003c060  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c064  jnz     short loc_18003C070
0x18003c066  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003c06b  jmp     loc_18003C1A7
0x18003c070  mov     rcx, rax; hObject
0x18003c073  call    cs:__imp_CloseHandle
0x18003c079  lea     rcx, [rsp+8A0h+FileName]; lpString
0x18003c07e  call    cs:__imp_lstrlenW
0x18003c084  lea     rdx, aU_0; "u "
0x18003c08b  mov     r8, r12
0x18003c08e  lea     rcx, [rbp+7A0h+CommandLine]
0x18003c095  lea     esi, ds:2[rax*2]
0x18003c09c  lea     rax, [rbp+7A0h+CommandLine]
0x18003c0a3  sub     rdx, rax
0x18003c0a6  lea     rax, [r8+7FFFFDF6h]
0x18003c0ad  test    rax, rax
0x18003c0b0  jz      short loc_18003C0C8
0x18003c0b2  movzx   eax, word ptr [rdx+rcx]
0x18003c0b6  test    ax, ax
0x18003c0b9  jz      short loc_18003C0C8
0x18003c0bb  mov     [rcx], ax
0x18003c0be  add     rcx, 2
0x18003c0c2  sub     r8, 1
0x18003c0c6  jnz     short loc_18003C0A6
0x18003c0c8  test    r8, r8
0x18003c0cb  lea     rax, [rcx-2]
0x18003c0cf  cmovnz  rax, rcx
0x18003c0d3  mov     [rax], r14w
0x18003c0d7  mov     rax, r8
0x18003c0da  neg     rax
0x18003c0dd  sbb     ebx, ebx
0x18003c0df  not     ebx
0x18003c0e1  and     ebx, 8007007Ah
0x18003c0e7  test    r8, r8
0x18003c0ea  jz      loc_18003C1A9
0x18003c0f0  lea     r8, aAspNet64; "ASP.NET_64"
0x18003c0f7  mov     rdx, r12; unsigned __int64
0x18003c0fa  lea     rcx, [rbp+7A0h+CommandLine]; unsigned __int16 *
0x18003c101  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c106  mov     ebx, eax
0x18003c108  test    eax, eax
0x18003c10a  jnz     loc_18003C1A9
0x18003c110  lea     edx, [rax+1]; bQuietModeArg
0x18003c113  lea     rcx, [rbp+7A0h+CommandLine]; lpCommandLine
0x18003c11a  call    cs:__imp_UnloadPerfCounterTextStringsW
0x18003c120  lea     rdx, [rsp+8A0h+var_858]; unsigned __int16 **
0x18003c125  lea     rcx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18003c12c  call    ?CreatePerfCounterEntryPoints@@YAJPEBGPEAPEBG@Z; CreatePerfCounterEntryPoints(ushort const *,ushort const * *)
0x18003c131  mov     ebx, eax
0x18003c133  test    eax, eax
0x18003c135  jnz     short loc_18003C1A9
0x18003c137  lea     rax, [rsp+8A0h+phkResult]
0x18003c13c  mov     r9d, 20006h; samDesired
0x18003c142  xor     r8d, r8d; ulOptions
0x18003c145  mov     qword ptr [rsp+8A0h+dwCreationDisposition], rax; phkResult
0x18003c14a  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18003c151  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c158  call    cs:__imp_RegOpenKeyExW
0x18003c15e  test    eax, eax
0x18003c160  jz      short loc_18003C172
0x18003c162  movzx   ebx, ax
0x18003c165  or      ebx, 80070000h
0x18003c16b  test    eax, eax
0x18003c16d  cmovle  ebx, eax
0x18003c170  jmp     short loc_18003C1A9
0x18003c172  mov     rcx, [rsp+8A0h+phkResult]; hKey
0x18003c177  lea     rax, [rsp+8A0h+FileName]
0x18003c17c  mov     [rsp+8A0h+dwFlagsAndAttributes], esi; cbData
0x18003c180  lea     rdx, aLibrary; "Library"
0x18003c187  mov     r9d, 1; dwType
0x18003c18d  mov     qword ptr [rsp+8A0h+dwCreationDisposition], rax; lpData
0x18003c192  xor     r8d, r8d; Reserved
0x18003c195  call    cs:__imp_RegSetValueExW
0x18003c19b  test    eax, eax
0x18003c19d  jnz     short loc_18003C162
0x18003c19f  mov     rcx, rdi; unsigned __int16 *
0x18003c1a2  call    ?CallLoadPerfCounterTextStrings@@YAJPEBG@Z; CallLoadPerfCounterTextStrings(ushort const *)
0x18003c1a7  mov     ebx, eax
0x18003c1a9  mov     rcx, [rsp+8A0h+phkResult]; hKey
0x18003c1ae  test    rcx, rcx
0x18003c1b1  jz      short loc_18003C1B9
0x18003c1b3  call    cs:__imp_RegCloseKey
0x18003c1b9  mov     eax, ebx
0x18003c1bb  mov     rcx, [rbp+7A0h+var_20]
0x18003c1c2  xor     rcx, rsp; StackCookie
0x18003c1c5  call    __security_check_cookie
0x18003c1ca  lea     r11, [rsp+8A0h+var_10]
0x18003c1d2  mov     rbx, [r11+20h]
0x18003c1d6  mov     rsi, [r11+28h]
0x18003c1da  mov     rdi, [r11+30h]
0x18003c1de  mov     rsp, r11
0x18003c1e1  pop     r14
0x18003c1e3  pop     r12
0x18003c1e5  pop     rbp
0x18003c1e6  retn
```
