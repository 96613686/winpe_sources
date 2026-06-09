# IsolationAwareLoadLibraryW

- ea: `0x1800513f4`
- end: `0x18005149f`
- name: `IsolationAwareLoadLibraryW`
- size: `171`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004e598`
- `0x18006b38c`

## callees

- `0x180022c04`
- `0x1800513f4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180051473`
- `KERNEL32!GetLastError` at `0x180076565`
- `KERNEL32!GetLastError` at `0x180051473`
- `KERNEL32!GetLastError` at `0x180076565`
- `KERNEL32!DeactivateActCtx` at `0x180051488`
- `KERNEL32!DeactivateActCtx` at `0x180076579`
- `KERNEL32!DeactivateActCtx` at `0x180051488`
- `KERNEL32!DeactivateActCtx` at `0x180076579`
- `KERNEL32!LoadLibraryW` at `0x18005144b`
- `KERNEL32!LoadLibraryW` at `0x18005144b`
- `KERNEL32!SetLastError` at `0x180051494`
- `KERNEL32!SetLastError` at `0x180076585`
- `KERNEL32!SetLastError` at `0x180051494`
- `KERNEL32!SetLastError` at `0x180076585`

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
0x1800513f4  mov     rax, rsp
0x1800513f7  mov     [rax+8], rbx
0x1800513fb  mov     [rax+18h], rsi
0x1800513ff  push    rdi
0x180051400  sub     rsp, 30h
0x180051404  mov     rbx, rcx
0x180051407  mov     qword ptr [rax-18h], 0
0x18005140f  mov     qword ptr [rax+10h], 0
0x180051417  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18005141e  jnz     short loc_180051448
0x180051420  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180051427  jnz     short loc_180051448
0x180051429  lea     rcx, [rax+10h]; lpCookie
0x18005142d  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180051432  test    eax, eax
0x180051434  jnz     short loc_180051448
0x180051436  xor     eax, eax
0x180051438  mov     rbx, [rsp+38h+arg_0]
0x18005143d  mov     rsi, [rsp+38h+arg_10]
0x180051442  add     rsp, 30h
0x180051446  pop     rdi
0x180051447  retn
0x180051448  mov     rcx, rbx; lpLibFileName
0x18005144b  call    cs:__imp_LoadLibraryW
0x180051451  mov     rbx, rax
0x180051454  mov     [rsp+38h+var_18], rax
0x180051459  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180051460  jz      short loc_18005146B
0x180051462  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180051469  jnz     short loc_18005149A
0x18005146b  test    rbx, rbx
0x18005146e  jnz     short loc_18005147D
0x180051470  lea     esi, [rbx+1]
0x180051473  call    cs:__imp_GetLastError
0x180051479  mov     edi, eax
0x18005147b  jmp     short loc_180051481
0x18005147d  xor     esi, esi
0x18005147f  xor     edi, edi
0x180051481  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180051486  xor     ecx, ecx; dwFlags
0x180051488  call    cs:__imp_DeactivateActCtx
0x18005148e  test    esi, esi
0x180051490  jz      short loc_18005149A
0x180051492  mov     ecx, edi; dwErrCode
0x180051494  call    cs:__imp_SetLastError
0x18005149a  mov     rax, rbx
0x18005149d  jmp     short loc_180051438
0x18007653c  push    rbx
0x18007653e  push    rbp
0x18007653f  push    rdi
0x180076540  sub     rsp, 20h
0x180076544  mov     rbp, rdx
0x180076547  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18007654e  jz      short loc_180076559
0x180076550  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180076557  jnz     short loc_18007658C
0x180076559  cmp     qword ptr [rbp+20h], 0
0x18007655e  jnz     short loc_18007656F
0x180076560  mov     edi, 1
0x180076565  call    cs:__imp_GetLastError
0x18007656b  mov     ebx, eax
0x18007656d  jmp     short loc_180076573
0x18007656f  xor     edi, edi
0x180076571  xor     ebx, ebx
0x180076573  mov     rdx, [rbp+48h]; ulCookie
0x180076577  xor     ecx, ecx; dwFlags
0x180076579  call    cs:__imp_DeactivateActCtx
0x18007657f  test    edi, edi
0x180076581  jz      short loc_18007658C
0x180076583  mov     ecx, ebx; dwErrCode
0x180076585  call    cs:__imp_SetLastError
0x18007658b  nop
0x18007658c  add     rsp, 20h
0x180076590  pop     rdi
0x180076591  pop     rbp
0x180076592  pop     rbx
0x180076593  retn
```
