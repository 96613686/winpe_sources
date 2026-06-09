# IsAppCompatModeEnabled

- ea: `0x18002c6f0`
- end: `0x18002c847`
- name: `IsAppCompatModeEnabled`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002c6f0`
- `0x18002c850`
- `0x18002cb08`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c74f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c74f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002c763`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002c763`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002c77e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002c77e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c7b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c7b9`

## pseudocode

```c
__int64 __fastcall IsAppCompatModeEnabled(int a1)
{
  __int64 v1; // rbx
  HMODULE ModuleHandleW; // rax
  int *v4; // rdx
  const WCHAR *FileNameW; // rbp
  unsigned int i; // edi
  __int64 v7; // rsi
  WCHAR Filename[128]; // [rsp+20h] [rbp-118h] BYREF

  v1 = a1;
  if ( !byte_1800E1C88 )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x80u) )
    {
      FileNameW = PathFindFileNameW(Filename);
      if ( FileNameW )
      {
        for ( i = 0; i < 0x23; ++i )
        {
          v7 = 4LL * (int)i;
          if ( !lstrcmpiW((&off_1800A4ED0)[v7], FileNameW)
            && (unsigned int)_IsAppCompatVersion(Filename, *(const unsigned __int16 **)&algn_1800A4ED8[v7 * 8]) )
          {
            dword_1800E1C90[SLODWORD(qword_1800A4EE0[v7])] = 1;
            dword_1800E1C90[SHIDWORD(qword_1800A4EE0[v7])] = 1;
            dword_1800E1C90[SLODWORD(qword_1800A4EE0[v7 + 1])] = 1;
            break;
          }
        }
        _GetRegistryCompatFlags(Filename, v4);
      }
    }
    byte_1800E1C88 = 1;
  }
  return (unsigned int)dword_1800E1C90[v1];
}

```

## disassembly

```asm
0x18002c6f0  mov     [rsp+arg_18], rbx
0x18002c6f5  push    r14
0x18002c6f7  sub     rsp, 130h
0x18002c6fe  mov     rax, cs:__security_cookie
0x18002c705  xor     rax, rsp
0x18002c708  mov     [rsp+138h+var_18], rax
0x18002c710  cmp     cs:byte_1800E1C88, 0
0x18002c717  lea     r14, __ImageBase
0x18002c71e  movsxd  rbx, ecx
0x18002c721  jz      short loc_18002C74D
0x18002c723  mov     eax, rva dword_1800E1C90[r14+rbx*4]
0x18002c72b  mov     rcx, [rsp+138h+var_18]
0x18002c733  xor     rcx, rsp; StackCookie
0x18002c736  call    __security_check_cookie
0x18002c73b  mov     rbx, [rsp+138h+arg_18]
0x18002c743  add     rsp, 130h
0x18002c74a  pop     r14
0x18002c74c  retn
0x18002c74d  xor     ecx, ecx; lpModuleName
0x18002c74f  call    cs:__imp_GetModuleHandleW
0x18002c755  mov     r8d, 80h; nSize
0x18002c75b  lea     rdx, [rsp+138h+Filename]; lpFilename
0x18002c760  mov     rcx, rax; hModule
0x18002c763  call    cs:__imp_GetModuleFileNameW
0x18002c769  test    eax, eax
0x18002c76b  jz      loc_18002C83B
0x18002c771  lea     rcx, [rsp+138h+Filename]; pszPath
0x18002c776  mov     [rsp+138h+arg_0], rbp
0x18002c77e  call    cs:__imp_PathFindFileNameW
0x18002c784  mov     rbp, rax
0x18002c787  test    rax, rax
0x18002c78a  jz      loc_18002C833
0x18002c790  mov     [rsp+138h+arg_10], rdi
0x18002c798  xor     edi, edi
0x18002c79a  mov     [rsp+138h+arg_8], rsi
0x18002c7a2  cmp     edi, 23h ; '#'
0x18002c7a5  jnb     short loc_18002C819
0x18002c7a7  movsxd  rsi, edi
0x18002c7aa  mov     rdx, rbp; lpString2
0x18002c7ad  shl     rsi, 5
0x18002c7b1  mov     rcx, [rsi+r14+0A4ED0h]; lpString1
0x18002c7b9  call    cs:__imp_lstrcmpiW
0x18002c7bf  test    eax, eax
0x18002c7c1  jz      short loc_18002C7C7
0x18002c7c3  inc     edi
0x18002c7c5  jmp     short loc_18002C7A2
0x18002c7c7  mov     rdx, [rsi+r14+0A4ED8h]; unsigned __int16 *
0x18002c7cf  lea     rcx, [rsp+138h+Filename]; unsigned __int16 *
0x18002c7d4  call    ?_IsAppCompatVersion@@YAHPEBG0@Z; _IsAppCompatVersion(ushort const *,ushort const *)
0x18002c7d9  test    eax, eax
0x18002c7db  jz      short loc_18002C7C3
0x18002c7dd  movsxd  rax, dword ptr [rsi+r14+0A4EE0h]
0x18002c7e5  mov     rva dword_1800E1C90[r14+rax*4], 1
0x18002c7f1  movsxd  rax, dword ptr [rsi+r14+0A4EE4h]
0x18002c7f9  mov     rva dword_1800E1C90[r14+rax*4], 1
0x18002c805  movsxd  rax, dword ptr [rsi+r14+0A4EE8h]
0x18002c80d  mov     rva dword_1800E1C90[r14+rax*4], 1
0x18002c819  lea     rcx, [rsp+138h+Filename]; unsigned __int16 *
0x18002c81e  call    ?_GetRegistryCompatFlags@@YAXPEBGPEAHI@Z; _GetRegistryCompatFlags(ushort const *,int *,uint)
0x18002c823  mov     rdi, [rsp+138h+arg_10]
0x18002c82b  mov     rsi, [rsp+138h+arg_8]
0x18002c833  mov     rbp, [rsp+138h+arg_0]
0x18002c83b  mov     cs:byte_1800E1C88, 1
0x18002c842  jmp     loc_18002C723
```
