# IsolationAwareLoadLibraryExW

- ea: `0x18001e7e8`
- end: `0x18001e8bb`
- name: `IsolationAwareLoadLibraryExW`
- size: `211`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003ad04`
- `0x180049e1c`

## callees

- `0x18001e7e8`
- `0x18001ea84`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e84c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e84c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af56f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af543`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e895`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800af55d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e895`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800af55d`

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
0x18001e7e8  mov     rax, rsp
0x18001e7eb  mov     [rax+8], rbx
0x18001e7ef  mov     [rax+18h], rsi
0x18001e7f3  mov     [rax+10h], rdx
0x18001e7f7  push    rdi
0x18001e7f8  sub     rsp, 30h
0x18001e7fc  mov     ebx, r8d
0x18001e7ff  mov     rdi, rcx
0x18001e802  mov     qword ptr [rax-18h], 0
0x18001e80a  mov     qword ptr [rax+10h], 0
0x18001e812  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e819  jnz     short loc_18001E844
0x18001e81b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e822  jnz     short loc_18001E844
0x18001e824  lea     rcx, [rax+10h]; lpCookie
0x18001e828  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001e82d  test    eax, eax
0x18001e82f  jnz     short loc_18001E844
0x18001e831  xor     eax, eax
0x18001e833  mov     rbx, [rsp+38h+arg_0]
0x18001e838  mov     rsi, [rsp+38h+arg_10]
0x18001e83d  add     rsp, 30h
0x18001e841  pop     rdi
0x18001e842  retn
0x18001e844  mov     r8d, ebx; dwFlags
0x18001e847  xor     edx, edx; hFile
0x18001e849  mov     rcx, rdi; lpLibFileName
0x18001e84c  call    cs:__imp_LoadLibraryExW
0x18001e853  nop     dword ptr [rax+rax+00h]
0x18001e858  mov     rbx, rax
0x18001e85b  mov     [rsp+38h+var_18], rax
0x18001e860  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e867  jz      short loc_18001E872
0x18001e869  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e870  jnz     short loc_18001E8B3
0x18001e872  test    rbx, rbx
0x18001e875  jnz     short loc_18001E88A
0x18001e877  lea     esi, [rbx+1]
0x18001e87a  call    cs:__imp_GetLastError
0x18001e881  nop     dword ptr [rax+rax+00h]
0x18001e886  mov     edi, eax
0x18001e888  jmp     short loc_18001E88E
0x18001e88a  xor     esi, esi
0x18001e88c  xor     edi, edi
0x18001e88e  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18001e893  xor     ecx, ecx; dwFlags
0x18001e895  call    cs:__imp_DeactivateActCtx
0x18001e89c  nop     dword ptr [rax+rax+00h]
0x18001e8a1  test    esi, esi
0x18001e8a3  jz      short loc_18001E8B3
0x18001e8a5  mov     ecx, edi; dwErrCode
0x18001e8a7  call    cs:__imp_SetLastError
0x18001e8ae  nop     dword ptr [rax+rax+00h]
0x18001e8b3  mov     rax, rbx
0x18001e8b6  jmp     loc_18001E833
0x1800af51a  push    rbx
0x1800af51c  push    rbp
0x1800af51d  push    rdi
0x1800af51e  sub     rsp, 20h
0x1800af522  mov     rbp, rdx
0x1800af525  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800af52c  jz      short loc_1800AF537
0x1800af52e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800af535  jnz     short loc_1800AF57C
0x1800af537  cmp     qword ptr [rbp+20h], 0
0x1800af53c  jnz     short loc_1800AF553
0x1800af53e  mov     edi, 1
0x1800af543  call    cs:__imp_GetLastError
0x1800af54a  nop     dword ptr [rax+rax+00h]
0x1800af54f  mov     ebx, eax
0x1800af551  jmp     short loc_1800AF557
0x1800af553  xor     edi, edi
0x1800af555  xor     ebx, ebx
0x1800af557  mov     rdx, [rbp+48h]; ulCookie
0x1800af55b  xor     ecx, ecx; dwFlags
0x1800af55d  call    cs:__imp_DeactivateActCtx
0x1800af564  nop     dword ptr [rax+rax+00h]
0x1800af569  test    edi, edi
0x1800af56b  jz      short loc_1800AF57C
0x1800af56d  mov     ecx, ebx; dwErrCode
0x1800af56f  call    cs:__imp_SetLastError
0x1800af576  nop     dword ptr [rax+rax+00h]
0x1800af57b  nop
0x1800af57c  add     rsp, 20h
0x1800af580  pop     rdi
0x1800af581  pop     rbp
0x1800af582  pop     rbx
0x1800af583  retn
```
