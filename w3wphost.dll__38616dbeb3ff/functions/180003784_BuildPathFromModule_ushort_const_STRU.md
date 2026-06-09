# BuildPathFromModule(ushort const *,STRU *)

- ea: `0x180003784`
- end: `0x18000390e`
- name: `?BuildPathFromModule@@YAJPEBGPEAVSTRU@@@Z`
- size: `394`
- prototype: `signed int __fastcall(const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000561c`

## callees

- `0x180003784`

## import_xrefs

- `msvcrt!wcschr` at `0x1800038a5`
- `msvcrt!wcschr` at `0x1800038a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000381a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000381a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000382c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000382c`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003854`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003854`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800037f4`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003840`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000386c`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800037f4`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003840`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000386c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003805`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003886`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003805`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003886`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800038ca`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800038ca`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800038e0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800038f6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800038e0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800038f6`

## string_xrefs

- `0x1800037a4`: `w3wphost.dll`

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
0x180003784  push    rbx
0x180003786  push    rbp
0x180003787  push    rsi
0x180003788  push    rdi
0x180003789  push    r14
0x18000378b  sub     rsp, 20h
0x18000378f  mov     rdi, rdx
0x180003792  mov     r14, rcx
0x180003795  test    rdx, rdx
0x180003798  jnz     short loc_1800037A4
0x18000379a  mov     eax, 80070057h
0x18000379f  jmp     loc_180003902
0x1800037a4  lea     rcx, ModuleName; "w3wphost.dll"
0x1800037ab  call    cs:__imp_GetModuleHandleW
0x1800037b2  nop     dword ptr [rax+rax+00h]
0x1800037b7  mov     rbp, rax
0x1800037ba  test    rax, rax
0x1800037bd  jnz     short loc_1800037E0
0x1800037bf  call    cs:__imp_GetLastError
0x1800037c6  nop     dword ptr [rax+rax+00h]
0x1800037cb  test    eax, eax
0x1800037cd  jle     loc_180003902
0x1800037d3  movzx   eax, ax
0x1800037d6  or      eax, 80070000h
0x1800037db  jmp     loc_180003902
0x1800037e0  xor     esi, esi
0x1800037e2  mov     edx, 208h
0x1800037e7  jmp     short loc_180003851
0x1800037e9  mov     rcx, rdi
0x1800037ec  test    esi, esi
0x1800037ee  jnz     loc_180003886
0x1800037f4  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x1800037fb  nop     dword ptr [rax+rax+00h]
0x180003800  mov     rcx, rdi
0x180003803  mov     ebx, eax
0x180003805  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000380c  nop     dword ptr [rax+rax+00h]
0x180003811  mov     r8d, ebx; nSize
0x180003814  mov     rcx, rbp; hModule
0x180003817  mov     rdx, rax; lpFilename
0x18000381a  call    cs:__imp_GetModuleFileNameW
0x180003821  nop     dword ptr [rax+rax+00h]
0x180003826  mov     ebx, eax
0x180003828  test    eax, eax
0x18000382a  jnz     short loc_180003869
0x18000382c  call    cs:__imp_GetLastError
0x180003833  nop     dword ptr [rax+rax+00h]
0x180003838  cmp     eax, 7Ah ; 'z'
0x18000383b  jnz     short loc_1800037BF
0x18000383d  mov     rcx, rdi
0x180003840  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180003847  nop     dword ptr [rax+rax+00h]
0x18000384c  shl     eax, 2
0x18000384f  mov     edx, eax
0x180003851  mov     rcx, rdi
0x180003854  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000385b  nop     dword ptr [rax+rax+00h]
0x180003860  test    eax, eax
0x180003862  jns     short loc_1800037E9
0x180003864  jmp     loc_180003902
0x180003869  mov     rcx, rdi
0x18000386c  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180003873  nop     dword ptr [rax+rax+00h]
0x180003878  cmp     eax, ebx
0x18000387a  jbe     short loc_18000383D
0x18000387c  mov     esi, 1
0x180003881  jmp     loc_1800037E9
0x180003886  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000388d  nop     dword ptr [rax+rax+00h]
0x180003892  mov     rcx, rax
0x180003895  mov     esi, 5Ch ; '\'
0x18000389a  jmp     short loc_1800038A0
0x18000389c  lea     rcx, [rax+2]; Str
0x1800038a0  mov     edx, esi; Ch
0x1800038a2  mov     rbx, rax
0x1800038a5  call    cs:__imp_wcschr
0x1800038ac  nop     dword ptr [rax+rax+00h]
0x1800038b1  test    rax, rax
0x1800038b4  jnz     short loc_18000389C
0x1800038b6  test    rbx, rbx
0x1800038b9  jnz     short loc_1800038C2
0x1800038bb  mov     eax, 80070585h
0x1800038c0  jmp     short loc_180003902
0x1800038c2  xor     eax, eax
0x1800038c4  mov     rcx, rdi
0x1800038c7  mov     [rbx], ax
0x1800038ca  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800038d1  nop     dword ptr [rax+rax+00h]
0x1800038d6  lea     rdx, asc_18000FCB8; "\\"
0x1800038dd  mov     rcx, rdi
0x1800038e0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800038e7  nop     dword ptr [rax+rax+00h]
0x1800038ec  test    eax, eax
0x1800038ee  js      short loc_180003902
0x1800038f0  mov     rdx, r14
0x1800038f3  mov     rcx, rdi
0x1800038f6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800038fd  nop     dword ptr [rax+rax+00h]
0x180003902  add     rsp, 20h
0x180003906  pop     r14
0x180003908  pop     rdi
0x180003909  pop     rsi
0x18000390a  pop     rbp
0x18000390b  pop     rbx
0x18000390c  retn
```
