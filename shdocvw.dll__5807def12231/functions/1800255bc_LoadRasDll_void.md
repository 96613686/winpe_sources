# LoadRasDll(void)

- ea: `0x1800255bc`
- end: `0x180025657`
- name: `?LoadRasDll@@YAHXZ`
- size: `155`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800256a8`

## callees

- `0x1800255bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002560e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002560e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800255dc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800255dc`

## string_xrefs

- `0x1800255d5`: `RASAPI32.DLL`

## pseudocode

```c
HMODULE LoadRasDll(void)
{
  HMODULE result; // rax
  HMODULE v1; // rcx
  int v2; // edi
  __int64 v3; // rbx
  FARPROC ProcAddress; // rax

  if ( hLibModule )
    return (HMODULE)1;
  result = LoadLibraryW(L"RASAPI32.DLL");
  hLibModule = result;
  v1 = result;
  if ( result )
  {
    v2 = 0;
    if ( off_1800380F8 )
    {
      do
      {
        v3 = 2LL * v2;
        ProcAddress = GetProcAddress(v1, (LPCSTR)*(&rgRasApiMap + 2 * v2++ + 1));
        *(_QWORD *)*(&rgRasApiMap + v3) = ProcAddress;
        v1 = hLibModule;
      }
      while ( *(&rgRasApiMap + 2 * v2 + 1) );
    }
    return (HMODULE)(v1 != 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800255bc  mov     [rsp+arg_0], rbx
0x1800255c1  mov     [rsp+arg_8], rbp
0x1800255c6  push    rdi
0x1800255c7  sub     rsp, 20h
0x1800255cb  cmp     cs:hLibModule, 0
0x1800255d3  jnz     short loc_180025642
0x1800255d5  lea     rcx, aRasapi32Dll; "RASAPI32.DLL"
0x1800255dc  call    cs:__imp_LoadLibraryW
0x1800255e2  mov     cs:hLibModule, rax
0x1800255e9  mov     rcx, rax; hModule
0x1800255ec  test    rax, rax
0x1800255ef  jz      short loc_180025640
0x1800255f1  xor     edi, edi
0x1800255f3  cmp     cs:off_1800380F8, rdi; "RasSetAutodialParamA"
0x1800255fa  jz      short loc_180025636
0x1800255fc  lea     rbp, ?rgRasApiMap@@3PAU_tagAPIMAPENTRY@@A; _tagAPIMAPENTRY near * rgRasApiMap
0x180025603  movsxd  rbx, edi
0x180025606  add     rbx, rbx
0x180025609  mov     rdx, [rbp+rbx*8+8]; lpProcName
0x18002560e  call    cs:__imp_GetProcAddress
0x180025614  mov     rcx, rax
0x180025617  inc     edi
0x180025619  mov     rax, [rbp+rbx*8+0]
0x18002561e  mov     [rax], rcx
0x180025621  mov     rcx, cs:hLibModule
0x180025628  movsxd  rax, edi
0x18002562b  add     rax, rax
0x18002562e  cmp     qword ptr [rbp+rax*8+8], 0
0x180025634  jnz     short loc_180025603
0x180025636  xor     eax, eax
0x180025638  test    rcx, rcx
0x18002563b  setnz   al
0x18002563e  jmp     short loc_180025647
0x180025640  jmp     short loc_180025647
0x180025642  mov     eax, 1
0x180025647  mov     rbx, [rsp+28h+arg_0]
0x18002564c  mov     rbp, [rsp+28h+arg_8]
0x180025651  add     rsp, 20h
0x180025655  pop     rdi
0x180025656  retn
```
