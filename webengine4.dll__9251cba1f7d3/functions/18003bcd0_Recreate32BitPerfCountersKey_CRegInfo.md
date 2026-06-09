# Recreate32BitPerfCountersKey(CRegInfo *)

- ea: `0x18003bcd0`
- end: `0x18003bf19`
- name: `?Recreate32BitPerfCountersKey@@YAJPEAVCRegInfo@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(struct CRegInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ea8c`

## callees

- `0x180007824`
- `0x1800370b4`
- `0x180037df0`
- `0x18003bcd0`
- `0x18004d030`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003be1e`
- `KERNEL32!CloseHandle` at `0x18003be1e`
- `KERNEL32!lstrlenW` at `0x18003be2e`
- `KERNEL32!lstrlenW` at `0x18003be41`
- `KERNEL32!lstrlenW` at `0x18003be2e`
- `KERNEL32!lstrlenW` at `0x18003be41`
- `KERNEL32!CreateFileW` at `0x18003be0f`
- `KERNEL32!CreateFileW` at `0x18003be0f`
- `ADVAPI32!RegCloseKey` at `0x18003bee5`
- `ADVAPI32!RegCloseKey` at `0x18003bee5`
- `ADVAPI32!RegOpenKeyExW` at `0x18003be8c`
- `ADVAPI32!RegOpenKeyExW` at `0x18003be8c`
- `ADVAPI32!RegSetValueExW` at `0x18003bec7`
- `ADVAPI32!RegSetValueExW` at `0x18003bec7`

## string_xrefs

- `0x18003bdcb`: `aspnet_perf.dll`
- `0x18003be59`: `SYSTEM\CurrentControlSet\Services\ASP.NET\Performance`
- `0x18003be7e`: `SYSTEM\CurrentControlSet\Services\ASP.NET\Performance`
- `0x18003bd06`: `OpenPerfCommonData`
- `0x18003bd12`: `ClosePerfCommonData`
- `0x18003bd1e`: `CollectPerfCommonData`

## pseudocode

```c
__int64 __fastcall Recreate32BitPerfCountersKey(struct CRegInfo *a1)
{
  unsigned int PerfCounterEntryPoints; // ebx
  const unsigned __int16 *v3; // rsi
  WCHAR *v4; // rcx
  __int64 v5; // r8
  WCHAR v6; // ax
  WCHAR *v7; // rax
  HANDLE FileW; // rax
  WCHAR *v9; // r14
  int v10; // edi
  LSTATUS v11; // eax
  HKEY phkResult; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v14[3]; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR FileName[520]; // [rsp+68h] [rbp-A0h] BYREF

  v14[0] = L"OpenPerfCommonData";
  v14[1] = L"ClosePerfCommonData";
  v14[2] = L"CollectPerfCommonData";
  phkResult = 0;
  PerfCounterEntryPoints = 0;
  if ( a1 )
  {
    v3 = (const unsigned __int16 *)*((_QWORD *)a1 + 6);
    if ( v3 )
    {
      v4 = FileName;
      v5 = 520;
      do
      {
        if ( v5 == -2147483126 )
          break;
        v6 = *(WCHAR *)((char *)v4 + (char *)v3 - (char *)FileName);
        if ( !v6 )
          break;
        *v4++ = v6;
        --v5;
      }
      while ( v5 );
      v7 = v4 - 1;
      if ( v5 )
        v7 = v4;
      *v7 = 0;
      PerfCounterEntryPoints = v5 == 0 ? 0x8007007A : 0;
      if ( v5 )
      {
        PerfCounterEntryPoints = StringCchCatW(FileName, 0x208u, L"\\");
        if ( !PerfCounterEntryPoints )
        {
          PerfCounterEntryPoints = StringCchCatW(FileName, 0x208u, L"aspnet_perf.dll");
          if ( !PerfCounterEntryPoints )
          {
            FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
            if ( FileW != (HANDLE)-1LL )
            {
              CloseHandle(FileW);
              v9 = FileName;
              v10 = 2 * lstrlenW(FileName);
              goto LABEL_15;
            }
            v9 = (WCHAR *)*((_QWORD *)a1 + 3);
            v10 = 2 * lstrlenW(v9);
            if ( v9 )
            {
LABEL_15:
              PerfCounterEntryPoints = CreatePerfCounterEntryPoints(
                                         L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET\\Performance",
                                         (const unsigned __int16 **)v14);
              if ( !PerfCounterEntryPoints )
              {
                v11 = RegOpenKeyExW(
                        HKEY_LOCAL_MACHINE,
                        L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET\\Performance",
                        0,
                        0x20006u,
                        &phkResult);
                if ( v11 || (v11 = RegSetValueExW(phkResult, L"Library", 0, 1u, (const BYTE *)v9, v10 + 2)) != 0 )
                {
                  PerfCounterEntryPoints = (unsigned __int16)v11 | 0x80070000;
                  if ( v11 <= 0 )
                    PerfCounterEntryPoints = v11;
                }
                else
                {
                  PerfCounterEntryPoints = CallLoadPerfCounterTextStrings(v3);
                }
              }
            }
          }
        }
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
0x18003bcd0  mov     rax, rsp
0x18003bcd3  mov     [rax+10h], rbx
0x18003bcd7  mov     [rax+18h], rsi
0x18003bcdb  mov     [rax+20h], rdi
0x18003bcdf  push    rbp
0x18003bce0  push    r14
0x18003bce2  push    r15
0x18003bce4  lea     rbp, [rax-398h]
0x18003bceb  sub     rsp, 480h
0x18003bcf2  mov     rax, cs:__security_cookie
0x18003bcf9  xor     rax, rsp
0x18003bcfc  mov     [rbp+390h+var_20], rax
0x18003bd03  xor     r15d, r15d
0x18003bd06  lea     rax, aOpenperfcommon; "OpenPerfCommonData"
0x18003bd0d  mov     [rsp+490h+var_448], rax
0x18003bd12  lea     rax, aCloseperfcommo; "ClosePerfCommonData"
0x18003bd19  mov     [rsp+490h+var_440], rax
0x18003bd1e  lea     rax, aCollectperfcom; "CollectPerfCommonData"
0x18003bd25  mov     qword ptr [rsp+490h+var_438], rax
0x18003bd2a  mov     r14, rcx
0x18003bd2d  mov     [rsp+490h+phkResult], r15
0x18003bd32  mov     ebx, r15d
0x18003bd35  test    rcx, rcx
0x18003bd38  jz      loc_18003BEEB
0x18003bd3e  mov     rsi, [rcx+30h]
0x18003bd42  test    rsi, rsi
0x18003bd45  jz      loc_18003BEEB
0x18003bd4b  mov     edi, 208h
0x18003bd50  lea     rax, [rsp+490h+FileName]
0x18003bd55  mov     rdx, rsi
0x18003bd58  lea     rcx, [rsp+490h+FileName]
0x18003bd5d  mov     r8d, edi
0x18003bd60  sub     rdx, rax
0x18003bd63  lea     rax, [r8+7FFFFDF6h]
0x18003bd6a  test    rax, rax
0x18003bd6d  jz      short loc_18003BD85
0x18003bd6f  movzx   eax, word ptr [rdx+rcx]
0x18003bd73  test    ax, ax
0x18003bd76  jz      short loc_18003BD85
0x18003bd78  mov     [rcx], ax
0x18003bd7b  add     rcx, 2
0x18003bd7f  sub     r8, 1
0x18003bd83  jnz     short loc_18003BD63
0x18003bd85  test    r8, r8
0x18003bd88  lea     rax, [rcx-2]
0x18003bd8c  cmovnz  rax, rcx
0x18003bd90  mov     [rax], r15w
0x18003bd94  mov     rax, r8
0x18003bd97  neg     rax
0x18003bd9a  sbb     ebx, ebx
0x18003bd9c  not     ebx
0x18003bd9e  and     ebx, 8007007Ah
0x18003bda4  test    r8, r8
0x18003bda7  jz      loc_18003BEEB
0x18003bdad  lea     r8, SubBlock; "\\"
0x18003bdb4  mov     rdx, rdi; unsigned __int64
0x18003bdb7  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x18003bdbc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bdc1  mov     ebx, eax
0x18003bdc3  test    eax, eax
0x18003bdc5  jnz     loc_18003BEDB
0x18003bdcb  lea     r8, aAspnetPerfDll; "aspnet_perf.dll"
0x18003bdd2  mov     rdx, rdi; unsigned __int64
0x18003bdd5  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x18003bdda  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bddf  mov     ebx, eax
0x18003bde1  test    eax, eax
0x18003bde3  jnz     loc_18003BEDB
0x18003bde9  mov     [rsp+490h+hTemplateFile], r15; hTemplateFile
0x18003bdee  lea     r8d, [rax+1]; dwShareMode
0x18003bdf2  mov     [rsp+490h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003bdfa  lea     rcx, [rsp+490h+FileName]; lpFileName
0x18003bdff  xor     r9d, r9d; lpSecurityAttributes
0x18003be02  mov     [rsp+490h+dwCreationDisposition], 3; dwCreationDisposition
0x18003be0a  mov     edx, 80000000h; dwDesiredAccess
0x18003be0f  call    cs:__imp_CreateFileW
0x18003be15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003be19  jz      short loc_18003BE3A
0x18003be1b  mov     rcx, rax; hObject
0x18003be1e  call    cs:__imp_CloseHandle
0x18003be24  lea     rcx, [rsp+490h+FileName]; lpString
0x18003be29  lea     r14, [rsp+490h+FileName]
0x18003be2e  call    cs:__imp_lstrlenW
0x18003be34  mov     edi, eax
0x18003be36  add     edi, edi
0x18003be38  jmp     short loc_18003BE54
0x18003be3a  mov     r14, [r14+18h]
0x18003be3e  mov     rcx, r14; lpString
0x18003be41  call    cs:__imp_lstrlenW
0x18003be47  mov     edi, eax
0x18003be49  add     edi, edi
0x18003be4b  test    r14, r14
0x18003be4e  jz      loc_18003BEDB
0x18003be54  lea     rdx, [rsp+490h+var_448]; unsigned __int16 **
0x18003be59  lea     rcx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18003be60  call    ?CreatePerfCounterEntryPoints@@YAJPEBGPEAPEBG@Z; CreatePerfCounterEntryPoints(ushort const *,ushort const * *)
0x18003be65  mov     ebx, eax
0x18003be67  test    eax, eax
0x18003be69  jnz     short loc_18003BEDB
0x18003be6b  lea     rax, [rsp+490h+phkResult]
0x18003be70  mov     r9d, 20006h; samDesired
0x18003be76  xor     r8d, r8d; ulOptions
0x18003be79  mov     qword ptr [rsp+490h+dwCreationDisposition], rax; phkResult
0x18003be7e  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18003be85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003be8c  call    cs:__imp_RegOpenKeyExW
0x18003be92  test    eax, eax
0x18003be94  jz      short loc_18003BEA6
0x18003be96  movzx   ebx, ax
0x18003be99  or      ebx, 80070000h
0x18003be9f  test    eax, eax
0x18003bea1  cmovle  ebx, eax
0x18003bea4  jmp     short loc_18003BEDB
0x18003bea6  mov     rcx, [rsp+490h+phkResult]; hKey
0x18003beab  lea     eax, [rdi+2]
0x18003beae  mov     [rsp+490h+dwFlagsAndAttributes], eax; cbData
0x18003beb2  lea     rdx, aLibrary; "Library"
0x18003beb9  mov     r9d, 1; dwType
0x18003bebf  mov     qword ptr [rsp+490h+dwCreationDisposition], r14; lpData
0x18003bec4  xor     r8d, r8d; Reserved
0x18003bec7  call    cs:__imp_RegSetValueExW
0x18003becd  test    eax, eax
0x18003becf  jnz     short loc_18003BE96
0x18003bed1  mov     rcx, rsi; unsigned __int16 *
0x18003bed4  call    ?CallLoadPerfCounterTextStrings@@YAJPEBG@Z; CallLoadPerfCounterTextStrings(ushort const *)
0x18003bed9  mov     ebx, eax
0x18003bedb  mov     rcx, [rsp+490h+phkResult]; hKey
0x18003bee0  test    rcx, rcx
0x18003bee3  jz      short loc_18003BEEB
0x18003bee5  call    cs:__imp_RegCloseKey
0x18003beeb  mov     eax, ebx
0x18003beed  mov     rcx, [rbp+390h+var_20]
0x18003bef4  xor     rcx, rsp; StackCookie
0x18003bef7  call    __security_check_cookie
0x18003befc  lea     r11, [rsp+490h+var_10]
0x18003bf04  mov     rbx, [r11+28h]
0x18003bf08  mov     rsi, [r11+30h]
0x18003bf0c  mov     rdi, [r11+38h]
0x18003bf10  mov     rsp, r11
0x18003bf13  pop     r15
0x18003bf15  pop     r14
0x18003bf17  pop     rbp
0x18003bf18  retn
```
