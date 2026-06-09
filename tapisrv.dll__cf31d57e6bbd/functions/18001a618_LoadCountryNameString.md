# LoadCountryNameString

- ea: `0x18001a618`
- end: `0x18001a6fc`
- name: `LoadCountryNameString`
- size: `228`
- prototype: `__int64 __fastcall(int, UINT, WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800028cc`
- `0x18000c8a0`

## callees

- `0x18001a618`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001a6e9`
- `KERNEL32!FreeLibrary` at `0x18001a6e9`
- `KERNEL32!LoadLibraryW` at `0x18001a672`
- `KERNEL32!LoadLibraryW` at `0x18001a672`
- `KERNEL32!GetLastError` at `0x18001a6bb`
- `KERNEL32!GetLastError` at `0x18001a6bb`
- `USER32!LoadStringW` at `0x18001a6af`
- `USER32!LoadStringW` at `0x18001a6af`

## string_xrefs

- `0x18001a688`: `Failed to load ResDll=%ls for ResId=%ld!`
- `0x18001a6c4`: `LoadString failed for ResId=%ld with GetLastError %ld`

## pseudocode

```c
__int64 __fastcall LoadCountryNameString(int a1, UINT a2, WCHAR *a3)
{
  HMODULE LibraryW; // rbx
  int i; // r9d
  __int64 v7; // rax
  __int64 v8; // rdi
  int StringW; // edi
  DWORD LastError; // eax

  LibraryW = ghInstance;
  for ( i = 0; i < g_numDialRulesInArray; ++i )
  {
    if ( gaTapiDialRules[10 * i] == a1 )
    {
      _mm_lfence();
      v7 = dword_18004628C[10 * i];
      if ( (_DWORD)v7 )
      {
        v8 = dword_18004628C[10 * i];
        LibraryW = LoadLibraryW((LPCWSTR)gaTapiNameResDlls[v7]);
        if ( !LibraryW )
        {
          TRACELogPrint(65538, "Failed to load ResDll=%ls for ResId=%ld!", (const wchar_t *)gaTapiNameResDlls[v8], a2);
          return 0xFFFFFFFFLL;
        }
      }
      break;
    }
  }
  StringW = LoadStringW(LibraryW, a2, a3, 96);
  if ( StringW <= 0 )
  {
    LastError = GetLastError();
    TRACELogPrint(65538, "LoadString failed for ResId=%ld with GetLastError %ld", a2, LastError);
  }
  if ( LibraryW )
  {
    if ( LibraryW != ghInstance )
      FreeLibrary(LibraryW);
  }
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x18001a618  push    rbx
0x18001a61a  push    rbp
0x18001a61b  push    rsi
0x18001a61c  push    rdi
0x18001a61d  push    r14
0x18001a61f  sub     rsp, 20h
0x18001a623  mov     rbx, cs:ghInstance
0x18001a62a  lea     r14, __ImageBase
0x18001a631  mov     rbp, r8
0x18001a634  mov     esi, edx
0x18001a636  xor     r9d, r9d
0x18001a639  cmp     r9d, cs:g_numDialRulesInArray
0x18001a640  jge     short loc_18001A6A1
0x18001a642  movsxd  rax, r9d
0x18001a645  lea     rax, [rax+rax*4]
0x18001a649  cmp     ds:rva gaTapiDialRules[r14+rax*8], ecx
0x18001a651  jz      short loc_18001A658
0x18001a653  inc     r9d
0x18001a656  jmp     short loc_18001A639
0x18001a658  lfence
0x18001a65b  movsxd  rax, ds:rva dword_18004628C[r14+rax*8]
0x18001a663  test    eax, eax
0x18001a665  jz      short loc_18001A6A1
0x18001a667  mov     rcx, ds:rva gaTapiNameResDlls[r14+rax*8]; lpLibFileName
0x18001a66f  mov     rdi, rax
0x18001a672  call    cs:__imp_LoadLibraryW
0x18001a678  mov     rbx, rax
0x18001a67b  test    rax, rax
0x18001a67e  jnz     short loc_18001A6A1
0x18001a680  mov     r8, ds:rva gaTapiNameResDlls[r14+rdi*8]
0x18001a688  lea     rdx, aFailedToLoadRe; "Failed to load ResDll=%ls for ResId=%ld"...
0x18001a68f  mov     r9d, esi
0x18001a692  mov     ecx, 10002h
0x18001a697  call    TRACELogPrint
0x18001a69c  or      eax, 0FFFFFFFFh
0x18001a69f  jmp     short loc_18001A6F1
0x18001a6a1  mov     r9d, 60h ; '`'; cchBufferMax
0x18001a6a7  mov     r8, rbp; lpBuffer
0x18001a6aa  mov     edx, esi; uID
0x18001a6ac  mov     rcx, rbx; hInstance
0x18001a6af  call    cs:__imp_LoadStringW
0x18001a6b5  mov     edi, eax
0x18001a6b7  test    eax, eax
0x18001a6b9  jg      short loc_18001A6D8
0x18001a6bb  call    cs:__imp_GetLastError
0x18001a6c1  mov     r8d, esi
0x18001a6c4  lea     rdx, aLoadstringFail; "LoadString failed for ResId=%ld with Ge"...
0x18001a6cb  mov     r9d, eax
0x18001a6ce  mov     ecx, 10002h
0x18001a6d3  call    TRACELogPrint
0x18001a6d8  test    rbx, rbx
0x18001a6db  jz      short loc_18001A6EF
0x18001a6dd  cmp     rbx, cs:ghInstance
0x18001a6e4  jz      short loc_18001A6EF
0x18001a6e6  mov     rcx, rbx; hLibModule
0x18001a6e9  call    cs:__imp_FreeLibrary
0x18001a6ef  mov     eax, edi
0x18001a6f1  add     rsp, 20h
0x18001a6f5  pop     r14
0x18001a6f7  pop     rdi
0x18001a6f8  pop     rsi
0x18001a6f9  pop     rbp
0x18001a6fa  pop     rbx
0x18001a6fb  retn
```
