# IsolationAwareLoadLibraryExW

- ea: `0x18001b2a8`
- end: `0x18001b35f`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800191ec`
- `0x180019e0c`

## callees

- `0x180009a60`
- `0x18001b2a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b30b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b30b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002965d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b354`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002967d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b354`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002967d`
- `KERNEL32!DeactivateActCtx` at `0x18001b348`
- `KERNEL32!DeactivateActCtx` at `0x180029671`
- `KERNEL32!DeactivateActCtx` at `0x18001b348`
- `KERNEL32!DeactivateActCtx` at `0x180029671`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName, __int64 a2, DWORD a3)
{
  HMODULE Library; // rax
  HMODULE v7; // rbx
  int v8; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, a3);
  v7 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      v8 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x18001b2a8  mov     rax, rsp
0x18001b2ab  mov     [rax+8], rbx
0x18001b2af  mov     [rax+18h], rsi
0x18001b2b3  mov     [rax+10h], rdx
0x18001b2b7  push    rdi
0x18001b2b8  sub     rsp, 30h
0x18001b2bc  mov     ebx, r8d
0x18001b2bf  mov     rdi, rcx
0x18001b2c2  mov     qword ptr [rax-18h], 0
0x18001b2ca  mov     qword ptr [rax+10h], 0
0x18001b2d2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001b2d9  jnz     short loc_18001B303
0x18001b2db  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001b2e2  jnz     short loc_18001B303
0x18001b2e4  lea     rcx, [rax+10h]; lpCookie
0x18001b2e8  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001b2ed  test    eax, eax
0x18001b2ef  jnz     short loc_18001B303
0x18001b2f1  xor     eax, eax
0x18001b2f3  mov     rbx, [rsp+38h+arg_0]
0x18001b2f8  mov     rsi, [rsp+38h+arg_10]
0x18001b2fd  add     rsp, 30h
0x18001b301  pop     rdi
0x18001b302  retn
0x18001b303  mov     r8d, ebx; dwFlags
0x18001b306  xor     edx, edx; hFile
0x18001b308  mov     rcx, rdi; lpLibFileName
0x18001b30b  call    cs:__imp_LoadLibraryExW
0x18001b311  mov     rbx, rax
0x18001b314  mov     [rsp+38h+var_18], rax
0x18001b319  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001b320  jz      short loc_18001B32B
0x18001b322  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001b329  jnz     short loc_18001B35A
0x18001b32b  test    rbx, rbx
0x18001b32e  jnz     short loc_18001B33D
0x18001b330  lea     esi, [rbx+1]
0x18001b333  call    cs:__imp_GetLastError
0x18001b339  mov     edi, eax
0x18001b33b  jmp     short loc_18001B341
0x18001b33d  xor     esi, esi
0x18001b33f  xor     edi, edi
0x18001b341  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18001b346  xor     ecx, ecx; dwFlags
0x18001b348  call    cs:__imp_DeactivateActCtx
0x18001b34e  test    esi, esi
0x18001b350  jz      short loc_18001B35A
0x18001b352  mov     ecx, edi; dwErrCode
0x18001b354  call    cs:__imp_SetLastError
0x18001b35a  mov     rax, rbx
0x18001b35d  jmp     short loc_18001B2F3
0x180029634  push    rbx
0x180029636  push    rbp
0x180029637  push    rdi
0x180029638  sub     rsp, 20h
0x18002963c  mov     rbp, rdx
0x18002963f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180029646  jz      short loc_180029651
0x180029648  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002964f  jnz     short loc_180029684
0x180029651  cmp     qword ptr [rbp+20h], 0
0x180029656  jnz     short loc_180029667
0x180029658  mov     edi, 1
0x18002965d  call    cs:__imp_GetLastError
0x180029663  mov     ebx, eax
0x180029665  jmp     short loc_18002966B
0x180029667  xor     edi, edi
0x180029669  xor     ebx, ebx
0x18002966b  mov     rdx, [rbp+48h]; ulCookie
0x18002966f  xor     ecx, ecx; dwFlags
0x180029671  call    cs:__imp_DeactivateActCtx
0x180029677  test    edi, edi
0x180029679  jz      short loc_180029684
0x18002967b  mov     ecx, ebx; dwErrCode
0x18002967d  call    cs:__imp_SetLastError
0x180029683  nop
0x180029684  add     rsp, 20h
0x180029688  pop     rdi
0x180029689  pop     rbp
0x18002968a  pop     rbx
0x18002968b  retn
```
