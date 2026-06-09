# IsolationAwareLoadLibraryExW

- ea: `0x18001e38c`
- end: `0x18001e443`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180038b38`
- `0x180047c10`

## callees

- `0x18001e38c`
- `0x18001e5dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e3ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e3ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e438`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aa569`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e438`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aa569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa549`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e42c`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800aa55d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e42c`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800aa55d`

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
0x18001e38c  mov     rax, rsp
0x18001e38f  mov     [rax+8], rbx
0x18001e393  mov     [rax+18h], rsi
0x18001e397  mov     [rax+10h], rdx
0x18001e39b  push    rdi
0x18001e39c  sub     rsp, 30h
0x18001e3a0  mov     ebx, r8d
0x18001e3a3  mov     rdi, rcx
0x18001e3a6  mov     qword ptr [rax-18h], 0
0x18001e3ae  mov     qword ptr [rax+10h], 0
0x18001e3b6  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e3bd  jnz     short loc_18001E3E7
0x18001e3bf  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e3c6  jnz     short loc_18001E3E7
0x18001e3c8  lea     rcx, [rax+10h]; lpCookie
0x18001e3cc  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001e3d1  test    eax, eax
0x18001e3d3  jnz     short loc_18001E3E7
0x18001e3d5  xor     eax, eax
0x18001e3d7  mov     rbx, [rsp+38h+arg_0]
0x18001e3dc  mov     rsi, [rsp+38h+arg_10]
0x18001e3e1  add     rsp, 30h
0x18001e3e5  pop     rdi
0x18001e3e6  retn
0x18001e3e7  mov     r8d, ebx; dwFlags
0x18001e3ea  xor     edx, edx; hFile
0x18001e3ec  mov     rcx, rdi; lpLibFileName
0x18001e3ef  call    cs:__imp_LoadLibraryExW
0x18001e3f5  mov     rbx, rax
0x18001e3f8  mov     [rsp+38h+var_18], rax
0x18001e3fd  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e404  jz      short loc_18001E40F
0x18001e406  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e40d  jnz     short loc_18001E43E
0x18001e40f  test    rbx, rbx
0x18001e412  jnz     short loc_18001E421
0x18001e414  lea     esi, [rbx+1]
0x18001e417  call    cs:__imp_GetLastError
0x18001e41d  mov     edi, eax
0x18001e41f  jmp     short loc_18001E425
0x18001e421  xor     esi, esi
0x18001e423  xor     edi, edi
0x18001e425  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18001e42a  xor     ecx, ecx; dwFlags
0x18001e42c  call    cs:__imp_DeactivateActCtx
0x18001e432  test    esi, esi
0x18001e434  jz      short loc_18001E43E
0x18001e436  mov     ecx, edi; dwErrCode
0x18001e438  call    cs:__imp_SetLastError
0x18001e43e  mov     rax, rbx
0x18001e441  jmp     short loc_18001E3D7
0x1800aa520  push    rbx
0x1800aa522  push    rbp
0x1800aa523  push    rdi
0x1800aa524  sub     rsp, 20h
0x1800aa528  mov     rbp, rdx
0x1800aa52b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800aa532  jz      short loc_1800AA53D
0x1800aa534  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800aa53b  jnz     short loc_1800AA570
0x1800aa53d  cmp     qword ptr [rbp+20h], 0
0x1800aa542  jnz     short loc_1800AA553
0x1800aa544  mov     edi, 1
0x1800aa549  call    cs:__imp_GetLastError
0x1800aa54f  mov     ebx, eax
0x1800aa551  jmp     short loc_1800AA557
0x1800aa553  xor     edi, edi
0x1800aa555  xor     ebx, ebx
0x1800aa557  mov     rdx, [rbp+48h]; ulCookie
0x1800aa55b  xor     ecx, ecx; dwFlags
0x1800aa55d  call    cs:__imp_DeactivateActCtx
0x1800aa563  test    edi, edi
0x1800aa565  jz      short loc_1800AA570
0x1800aa567  mov     ecx, ebx; dwErrCode
0x1800aa569  call    cs:__imp_SetLastError
0x1800aa56f  nop
0x1800aa570  add     rsp, 20h
0x1800aa574  pop     rdi
0x1800aa575  pop     rbp
0x1800aa576  pop     rbx
0x1800aa577  retn
```
