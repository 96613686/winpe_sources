# IsolationAwareLoadLibraryExW

- ea: `0x180011714`
- end: `0x1800117cb`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009124`
- `0x180013e88`
- `0x180014950`

## callees

- `0x180011714`
- `0x1800117d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001179f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e42b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001179f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e42b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800117c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e44b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800117c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e44b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011777`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011777`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800117b4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e43f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800117b4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e43f`

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
0x180011714  mov     rax, rsp
0x180011717  mov     [rax+8], rbx
0x18001171b  mov     [rax+18h], rsi
0x18001171f  mov     [rax+10h], rdx
0x180011723  push    rdi
0x180011724  sub     rsp, 30h
0x180011728  mov     ebx, r8d
0x18001172b  mov     rdi, rcx
0x18001172e  mov     qword ptr [rax-18h], 0
0x180011736  mov     qword ptr [rax+10h], 0
0x18001173e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180011745  jnz     short loc_18001176F
0x180011747  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001174e  jnz     short loc_18001176F
0x180011750  lea     rcx, [rax+10h]; lpCookie
0x180011754  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180011759  test    eax, eax
0x18001175b  jnz     short loc_18001176F
0x18001175d  xor     eax, eax
0x18001175f  mov     rbx, [rsp+38h+arg_0]
0x180011764  mov     rsi, [rsp+38h+arg_10]
0x180011769  add     rsp, 30h
0x18001176d  pop     rdi
0x18001176e  retn
0x18001176f  mov     r8d, ebx; dwFlags
0x180011772  xor     edx, edx; hFile
0x180011774  mov     rcx, rdi; lpLibFileName
0x180011777  call    cs:__imp_LoadLibraryExW
0x18001177d  mov     rbx, rax
0x180011780  mov     [rsp+38h+var_18], rax
0x180011785  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001178c  jz      short loc_180011797
0x18001178e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011795  jnz     short loc_1800117C6
0x180011797  test    rbx, rbx
0x18001179a  jnz     short loc_1800117A9
0x18001179c  lea     esi, [rbx+1]
0x18001179f  call    cs:__imp_GetLastError
0x1800117a5  mov     edi, eax
0x1800117a7  jmp     short loc_1800117AD
0x1800117a9  xor     esi, esi
0x1800117ab  xor     edi, edi
0x1800117ad  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800117b2  xor     ecx, ecx; dwFlags
0x1800117b4  call    cs:__imp_DeactivateActCtx
0x1800117ba  test    esi, esi
0x1800117bc  jz      short loc_1800117C6
0x1800117be  mov     ecx, edi; dwErrCode
0x1800117c0  call    cs:__imp_SetLastError
0x1800117c6  mov     rax, rbx
0x1800117c9  jmp     short loc_18001175F
0x18001e402  push    rbx
0x18001e404  push    rbp
0x18001e405  push    rdi
0x18001e406  sub     rsp, 20h
0x18001e40a  mov     rbp, rdx
0x18001e40d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e414  jz      short loc_18001E41F
0x18001e416  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e41d  jnz     short loc_18001E452
0x18001e41f  cmp     qword ptr [rbp+20h], 0
0x18001e424  jnz     short loc_18001E435
0x18001e426  mov     edi, 1
0x18001e42b  call    cs:__imp_GetLastError
0x18001e431  mov     ebx, eax
0x18001e433  jmp     short loc_18001E439
0x18001e435  xor     edi, edi
0x18001e437  xor     ebx, ebx
0x18001e439  mov     rdx, [rbp+48h]; ulCookie
0x18001e43d  xor     ecx, ecx; dwFlags
0x18001e43f  call    cs:__imp_DeactivateActCtx
0x18001e445  test    edi, edi
0x18001e447  jz      short loc_18001E452
0x18001e449  mov     ecx, ebx; dwErrCode
0x18001e44b  call    cs:__imp_SetLastError
0x18001e451  nop
0x18001e452  add     rsp, 20h
0x18001e456  pop     rdi
0x18001e457  pop     rbp
0x18001e458  pop     rbx
0x18001e459  retn
```
