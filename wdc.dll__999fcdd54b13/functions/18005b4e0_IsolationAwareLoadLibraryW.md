# IsolationAwareLoadLibraryW

- ea: `0x18005b4e0`
- end: `0x18005b58b`
- name: `IsolationAwareLoadLibraryW`
- size: `171`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002e740`
- `0x180067cac`

## callees

- `0x180046818`
- `0x18005b4e0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18005b537`
- `KERNEL32!LoadLibraryW` at `0x18005b537`
- `KERNEL32!DeactivateActCtx` at `0x18005b574`
- `KERNEL32!DeactivateActCtx` at `0x1800852b4`
- `KERNEL32!DeactivateActCtx` at `0x18005b574`
- `KERNEL32!DeactivateActCtx` at `0x1800852b4`
- `KERNEL32!GetLastError` at `0x18005b55f`
- `KERNEL32!GetLastError` at `0x1800852a0`
- `KERNEL32!GetLastError` at `0x18005b55f`
- `KERNEL32!GetLastError` at `0x1800852a0`
- `KERNEL32!SetLastError` at `0x18005b580`
- `KERNEL32!SetLastError` at `0x1800852c0`
- `KERNEL32!SetLastError` at `0x18005b580`
- `KERNEL32!SetLastError` at `0x1800852c0`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryW(LPCWSTR lpLibFileName)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  int v5; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  v4 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
    {
      v5 = 0;
      LastError = 0;
    }
    else
    {
      v5 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v5 )
      SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x18005b4e0  mov     rax, rsp
0x18005b4e3  mov     [rax+8], rbx
0x18005b4e7  mov     [rax+18h], rsi
0x18005b4eb  push    rdi
0x18005b4ec  sub     rsp, 30h
0x18005b4f0  mov     rbx, rcx
0x18005b4f3  mov     qword ptr [rax-18h], 0
0x18005b4fb  mov     qword ptr [rax+10h], 0
0x18005b503  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18005b50a  jnz     short loc_18005B534
0x18005b50c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18005b513  jnz     short loc_18005B534
0x18005b515  lea     rcx, [rax+10h]; lpCookie
0x18005b519  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18005b51e  test    eax, eax
0x18005b520  jnz     short loc_18005B534
0x18005b522  xor     eax, eax
0x18005b524  mov     rbx, [rsp+38h+arg_0]
0x18005b529  mov     rsi, [rsp+38h+arg_10]
0x18005b52e  add     rsp, 30h
0x18005b532  pop     rdi
0x18005b533  retn
0x18005b534  mov     rcx, rbx; lpLibFileName
0x18005b537  call    cs:__imp_LoadLibraryW
0x18005b53d  mov     rbx, rax
0x18005b540  mov     [rsp+38h+var_18], rax
0x18005b545  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18005b54c  jz      short loc_18005B557
0x18005b54e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18005b555  jnz     short loc_18005B586
0x18005b557  test    rbx, rbx
0x18005b55a  jnz     short loc_18005B569
0x18005b55c  lea     esi, [rbx+1]
0x18005b55f  call    cs:__imp_GetLastError
0x18005b565  mov     edi, eax
0x18005b567  jmp     short loc_18005B56D
0x18005b569  xor     esi, esi
0x18005b56b  xor     edi, edi
0x18005b56d  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18005b572  xor     ecx, ecx; dwFlags
0x18005b574  call    cs:__imp_DeactivateActCtx
0x18005b57a  test    esi, esi
0x18005b57c  jz      short loc_18005B586
0x18005b57e  mov     ecx, edi; dwErrCode
0x18005b580  call    cs:__imp_SetLastError
0x18005b586  mov     rax, rbx
0x18005b589  jmp     short loc_18005B524
0x180085277  push    rbx
0x180085279  push    rbp
0x18008527a  push    rdi
0x18008527b  sub     rsp, 20h
0x18008527f  mov     rbp, rdx
0x180085282  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180085289  jz      short loc_180085294
0x18008528b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180085292  jnz     short loc_1800852C7
0x180085294  cmp     qword ptr [rbp+20h], 0
0x180085299  jnz     short loc_1800852AA
0x18008529b  mov     edi, 1
0x1800852a0  call    cs:__imp_GetLastError
0x1800852a6  mov     ebx, eax
0x1800852a8  jmp     short loc_1800852AE
0x1800852aa  xor     edi, edi
0x1800852ac  xor     ebx, ebx
0x1800852ae  mov     rdx, [rbp+48h]; ulCookie
0x1800852b2  xor     ecx, ecx; dwFlags
0x1800852b4  call    cs:__imp_DeactivateActCtx
0x1800852ba  test    edi, edi
0x1800852bc  jz      short loc_1800852C7
0x1800852be  mov     ecx, ebx; dwErrCode
0x1800852c0  call    cs:__imp_SetLastError
0x1800852c6  nop
0x1800852c7  add     rsp, 20h
0x1800852cb  pop     rdi
0x1800852cc  pop     rbp
0x1800852cd  pop     rbx
0x1800852ce  retn
```
