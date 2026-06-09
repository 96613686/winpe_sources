# BuildPathFromModule(ushort const *,STRU *)

- ea: `0x180003550`
- end: `0x18000367b`
- name: `?BuildPathFromModule@@YAJPEBGPEAVSTRU@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800051dc`

## callees

- `0x180003550`

## import_xrefs

- `msvcrt!wcschr` at `0x18000362b`
- `msvcrt!wcschr` at `0x18000362b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800035ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800035ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003577`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035d6`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800035f2`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800035f2`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800035b0`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800035e4`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003601`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800035b0`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800035e4`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003601`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800035bb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003612`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800035bb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003612`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000364a`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000364a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000365a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000366a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000365a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000366a`

## string_xrefs

- `0x180003570`: `w3wphost.dll`

## pseudocode

```c
signed int __fastcall BuildPathFromModule(const unsigned __int16 *a1, struct STRU *a2)
{
  signed int result; // eax
  HMODULE ModuleHandleW; // rbp
  int v6; // esi
  unsigned int v7; // edx
  DWORD SizeCCH; // ebx
  WCHAR *Str; // rax
  DWORD ModuleFileNameW; // ebx
  wchar_t *v11; // rax
  const wchar_t *i; // rcx
  wchar_t *v13; // rbx

  if ( !a2 )
    return -2147024809;
  ModuleHandleW = GetModuleHandleW(L"w3wphost.dll");
  if ( ModuleHandleW )
  {
    v6 = 0;
    v7 = 520;
LABEL_11:
    result = STRU::Resize(a2, v7);
    if ( result >= 0 )
    {
      while ( !v6 )
      {
        SizeCCH = STRU::QuerySizeCCH(a2);
        Str = STRU::QueryStr(a2);
        ModuleFileNameW = GetModuleFileNameW(ModuleHandleW, Str, SizeCCH);
        if ( !ModuleFileNameW )
        {
          if ( GetLastError() != 122 )
            goto LABEL_4;
LABEL_10:
          v7 = 4 * STRU::QuerySizeCCH(a2);
          goto LABEL_11;
        }
        if ( STRU::QuerySizeCCH(a2) <= ModuleFileNameW )
          goto LABEL_10;
        v6 = 1;
      }
      v11 = STRU::QueryStr(a2);
      for ( i = v11; ; i = v11 + 1 )
      {
        v13 = v11;
        v11 = wcschr(i, 0x5Cu);
        if ( !v11 )
          break;
      }
      if ( v13 )
      {
        *v13 = 0;
        STRU::SyncWithBuffer(a2);
        result = STRU::Append(a2, L"\\");
        if ( result >= 0 )
          return STRU::Append(a2, a1);
      }
      else
      {
        return -2147023483;
      }
    }
  }
  else
  {
LABEL_4:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180003550  push    rbx
0x180003552  push    rbp
0x180003553  push    rsi
0x180003554  push    rdi
0x180003555  push    r14
0x180003557  sub     rsp, 20h
0x18000355b  mov     rdi, rdx
0x18000355e  mov     r14, rcx
0x180003561  test    rdx, rdx
0x180003564  jnz     short loc_180003570
0x180003566  mov     eax, 80070057h
0x18000356b  jmp     loc_180003670
0x180003570  lea     rcx, ModuleName; "w3wphost.dll"
0x180003577  call    cs:__imp_GetModuleHandleW
0x18000357d  mov     rbp, rax
0x180003580  test    rax, rax
0x180003583  jnz     short loc_1800035A0
0x180003585  call    cs:__imp_GetLastError
0x18000358b  test    eax, eax
0x18000358d  jle     loc_180003670
0x180003593  movzx   eax, ax
0x180003596  or      eax, 80070000h
0x18000359b  jmp     loc_180003670
0x1800035a0  xor     esi, esi
0x1800035a2  mov     edx, 208h
0x1800035a7  jmp     short loc_1800035EF
0x1800035a9  mov     rcx, rdi
0x1800035ac  test    esi, esi
0x1800035ae  jnz     short loc_180003612
0x1800035b0  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x1800035b6  mov     rcx, rdi
0x1800035b9  mov     ebx, eax
0x1800035bb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800035c1  mov     r8d, ebx; nSize
0x1800035c4  mov     rcx, rbp; hModule
0x1800035c7  mov     rdx, rax; lpFilename
0x1800035ca  call    cs:__imp_GetModuleFileNameW
0x1800035d0  mov     ebx, eax
0x1800035d2  test    eax, eax
0x1800035d4  jnz     short loc_1800035FE
0x1800035d6  call    cs:__imp_GetLastError
0x1800035dc  cmp     eax, 7Ah ; 'z'
0x1800035df  jnz     short loc_180003585
0x1800035e1  mov     rcx, rdi
0x1800035e4  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x1800035ea  shl     eax, 2
0x1800035ed  mov     edx, eax
0x1800035ef  mov     rcx, rdi
0x1800035f2  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800035f8  test    eax, eax
0x1800035fa  jns     short loc_1800035A9
0x1800035fc  jmp     short loc_180003670
0x1800035fe  mov     rcx, rdi
0x180003601  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180003607  cmp     eax, ebx
0x180003609  jbe     short loc_1800035E1
0x18000360b  mov     esi, 1
0x180003610  jmp     short loc_1800035A9
0x180003612  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003618  mov     rcx, rax
0x18000361b  mov     esi, 5Ch ; '\'
0x180003620  jmp     short loc_180003626
0x180003622  lea     rcx, [rax+2]; Str
0x180003626  mov     edx, esi; Ch
0x180003628  mov     rbx, rax
0x18000362b  call    cs:__imp_wcschr
0x180003631  test    rax, rax
0x180003634  jnz     short loc_180003622
0x180003636  test    rbx, rbx
0x180003639  jnz     short loc_180003642
0x18000363b  mov     eax, 80070585h
0x180003640  jmp     short loc_180003670
0x180003642  xor     eax, eax
0x180003644  mov     rcx, rdi
0x180003647  mov     [rbx], ax
0x18000364a  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003650  lea     rdx, asc_18000ECA8; "\\"
0x180003657  mov     rcx, rdi
0x18000365a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003660  test    eax, eax
0x180003662  js      short loc_180003670
0x180003664  mov     rdx, r14
0x180003667  mov     rcx, rdi
0x18000366a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003670  add     rsp, 20h
0x180003674  pop     r14
0x180003676  pop     rdi
0x180003677  pop     rsi
0x180003678  pop     rbp
0x180003679  pop     rbx
0x18000367a  retn
```
