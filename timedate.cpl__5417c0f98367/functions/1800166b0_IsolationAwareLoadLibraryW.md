# IsolationAwareLoadLibraryW

- ea: `0x1800166b0`
- end: `0x18001675b`
- name: `IsolationAwareLoadLibraryW`
- size: `171`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001473c`
- `0x180014ebc`
- `0x180015784`
- `0x180016928`
- `0x180016d9c`

## callees

- `0x180009a60`
- `0x1800166b0`
- `0x18001b2a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001672f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001672f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016750`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016750`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180016707`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180016707`
- `KERNEL32!DeactivateActCtx` at `0x180016744`
- `KERNEL32!DeactivateActCtx` at `0x180016744`

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
0x1800166b0  mov     rax, rsp
0x1800166b3  mov     [rax+8], rbx
0x1800166b7  mov     [rax+18h], rsi
0x1800166bb  push    rdi
0x1800166bc  sub     rsp, 30h
0x1800166c0  mov     rbx, rcx
0x1800166c3  mov     qword ptr [rax-18h], 0
0x1800166cb  mov     qword ptr [rax+10h], 0
0x1800166d3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800166da  jnz     short loc_180016704
0x1800166dc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800166e3  jnz     short loc_180016704
0x1800166e5  lea     rcx, [rax+10h]; lpCookie
0x1800166e9  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800166ee  test    eax, eax
0x1800166f0  jnz     short loc_180016704
0x1800166f2  xor     eax, eax
0x1800166f4  mov     rbx, [rsp+38h+arg_0]
0x1800166f9  mov     rsi, [rsp+38h+arg_10]
0x1800166fe  add     rsp, 30h
0x180016702  pop     rdi
0x180016703  retn
0x180016704  mov     rcx, rbx; lpLibFileName
0x180016707  call    cs:__imp_LoadLibraryW
0x18001670d  mov     rbx, rax
0x180016710  mov     [rsp+38h+var_18], rax
0x180016715  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001671c  jz      short loc_180016727
0x18001671e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180016725  jnz     short loc_180016756
0x180016727  test    rbx, rbx
0x18001672a  jnz     short loc_180016739
0x18001672c  lea     esi, [rbx+1]
0x18001672f  call    cs:__imp_GetLastError
0x180016735  mov     edi, eax
0x180016737  jmp     short loc_18001673D
0x180016739  xor     esi, esi
0x18001673b  xor     edi, edi
0x18001673d  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180016742  xor     ecx, ecx; dwFlags
0x180016744  call    cs:__imp_DeactivateActCtx
0x18001674a  test    esi, esi
0x18001674c  jz      short loc_180016756
0x18001674e  mov     ecx, edi; dwErrCode
0x180016750  call    cs:__imp_SetLastError
0x180016756  mov     rax, rbx
0x180016759  jmp     short loc_1800166F4
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
