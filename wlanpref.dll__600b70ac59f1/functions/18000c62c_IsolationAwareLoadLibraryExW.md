# IsolationAwareLoadLibraryExW

- ea: `0x18000c62c`
- end: `0x18000c6e3`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007534`
- `0x18000acc0`

## callees

- `0x18000c62c`
- `0x18000c6ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c68f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c68f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ded5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ded5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002def5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002def5`
- `KERNEL32!DeactivateActCtx` at `0x18000c6cc`
- `KERNEL32!DeactivateActCtx` at `0x18002dee9`
- `KERNEL32!DeactivateActCtx` at `0x18000c6cc`
- `KERNEL32!DeactivateActCtx` at `0x18002dee9`

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
0x18000c62c  mov     rax, rsp
0x18000c62f  mov     [rax+8], rbx
0x18000c633  mov     [rax+18h], rsi
0x18000c637  mov     [rax+10h], rdx
0x18000c63b  push    rdi
0x18000c63c  sub     rsp, 30h
0x18000c640  mov     ebx, r8d
0x18000c643  mov     rdi, rcx
0x18000c646  mov     qword ptr [rax-18h], 0
0x18000c64e  mov     qword ptr [rax+10h], 0
0x18000c656  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000c65d  jnz     short loc_18000C687
0x18000c65f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000c666  jnz     short loc_18000C687
0x18000c668  lea     rcx, [rax+10h]; lpCookie
0x18000c66c  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000c671  test    eax, eax
0x18000c673  jnz     short loc_18000C687
0x18000c675  xor     eax, eax
0x18000c677  mov     rbx, [rsp+38h+arg_0]
0x18000c67c  mov     rsi, [rsp+38h+arg_10]
0x18000c681  add     rsp, 30h
0x18000c685  pop     rdi
0x18000c686  retn
0x18000c687  mov     r8d, ebx; dwFlags
0x18000c68a  xor     edx, edx; hFile
0x18000c68c  mov     rcx, rdi; lpLibFileName
0x18000c68f  call    cs:__imp_LoadLibraryExW
0x18000c695  mov     rbx, rax
0x18000c698  mov     [rsp+38h+var_18], rax
0x18000c69d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000c6a4  jz      short loc_18000C6AF
0x18000c6a6  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000c6ad  jnz     short loc_18000C6DE
0x18000c6af  test    rbx, rbx
0x18000c6b2  jnz     short loc_18000C6C1
0x18000c6b4  lea     esi, [rbx+1]
0x18000c6b7  call    cs:__imp_GetLastError
0x18000c6bd  mov     edi, eax
0x18000c6bf  jmp     short loc_18000C6C5
0x18000c6c1  xor     esi, esi
0x18000c6c3  xor     edi, edi
0x18000c6c5  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000c6ca  xor     ecx, ecx; dwFlags
0x18000c6cc  call    cs:__imp_DeactivateActCtx
0x18000c6d2  test    esi, esi
0x18000c6d4  jz      short loc_18000C6DE
0x18000c6d6  mov     ecx, edi; dwErrCode
0x18000c6d8  call    cs:__imp_SetLastError
0x18000c6de  mov     rax, rbx
0x18000c6e1  jmp     short loc_18000C677
0x18002deac  push    rbx
0x18002deae  push    rbp
0x18002deaf  push    rdi
0x18002deb0  sub     rsp, 20h
0x18002deb4  mov     rbp, rdx
0x18002deb7  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002debe  jz      short loc_18002DEC9
0x18002dec0  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002dec7  jnz     short loc_18002DEFC
0x18002dec9  cmp     qword ptr [rbp+20h], 0
0x18002dece  jnz     short loc_18002DEDF
0x18002ded0  mov     edi, 1
0x18002ded5  call    cs:__imp_GetLastError
0x18002dedb  mov     ebx, eax
0x18002dedd  jmp     short loc_18002DEE3
0x18002dedf  xor     edi, edi
0x18002dee1  xor     ebx, ebx
0x18002dee3  mov     rdx, [rbp+48h]; ulCookie
0x18002dee7  xor     ecx, ecx; dwFlags
0x18002dee9  call    cs:__imp_DeactivateActCtx
0x18002deef  test    edi, edi
0x18002def1  jz      short loc_18002DEFC
0x18002def3  mov     ecx, ebx; dwErrCode
0x18002def5  call    cs:__imp_SetLastError
0x18002defb  nop
0x18002defc  add     rsp, 20h
0x18002df00  pop     rdi
0x18002df01  pop     rbp
0x18002df02  pop     rbx
0x18002df03  retn
```
