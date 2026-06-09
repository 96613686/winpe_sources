# User::LookupPrivilege(ushort const *,_LUID &)

- ea: `0x18004e604`
- end: `0x18004e698`
- name: `?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(LPCWSTR lpName, PLUID lpLuid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d870`
- `0x18004b588`

## callees

- `0x18004e604`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004e636`
- `msvcrt!_wcsicmp` at `0x18004e636`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e674`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e674`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004e681`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004e681`

## pseudocode

```c
__int64 __fastcall User::LookupPrivilege(LPCWSTR lpName, PLUID lpLuid)
{
  unsigned int v2; // edi
  unsigned int v5; // ebx
  wchar_t *v6; // rax
  char *v7; // rsi
  int v8; // edx
  int v9; // ecx

  v2 = 0;
  v5 = 1;
  while ( 1 )
  {
    if ( v2 >= 0x23 )
      return LookupPrivilegeValueW(0, lpName, lpLuid);
    if ( !_wcsicmp((&off_180074E70)[2 * v2], lpName) )
      break;
    ++v2;
  }
  v6 = (&off_180074E70)[2 * v2];
  v7 = (char *)((char *)lpName - (char *)v6);
  do
  {
    v8 = *(unsigned __int16 *)&v7[(_QWORD)v6];
    v9 = *v6 - v8;
    if ( v9 )
      break;
    ++v6;
  }
  while ( v8 );
  if ( v9 )
  {
    v5 = 0;
    SetLastError(0x521u);
  }
  else
  {
    *lpLuid = (struct _LUID)*(&off_180074E70 + 2 * v2 + 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18004e604  push    rbx
0x18004e606  push    rbp
0x18004e607  push    rsi
0x18004e608  push    rdi
0x18004e609  push    r14
0x18004e60b  push    r15
0x18004e60d  sub     rsp, 28h
0x18004e611  xor     edi, edi
0x18004e613  lea     rbp, off_180074E70; "SeCreateTokenPrivilege"
0x18004e61a  mov     r15, rdx
0x18004e61d  mov     rsi, rcx
0x18004e620  lea     ebx, [rdi+1]
0x18004e623  mov     rdx, rsi; lpName
0x18004e626  cmp     edi, 23h ; '#'
0x18004e629  jnb     short loc_18004E67C
0x18004e62b  mov     r14d, edi
0x18004e62e  add     r14, r14
0x18004e631  mov     rcx, [rbp+r14*8+0]; String1
0x18004e636  call    cs:__imp__wcsicmp
0x18004e63c  test    eax, eax
0x18004e63e  jz      short loc_18004E644
0x18004e640  add     edi, ebx
0x18004e642  jmp     short loc_18004E623
0x18004e644  mov     rax, [rbp+r14*8+0]
0x18004e649  sub     rsi, rax
0x18004e64c  movzx   ecx, word ptr [rax]
0x18004e64f  movzx   edx, word ptr [rax+rsi]
0x18004e653  sub     ecx, edx
0x18004e655  jnz     short loc_18004E65F
0x18004e657  add     rax, 2
0x18004e65b  test    edx, edx
0x18004e65d  jnz     short loc_18004E64C
0x18004e65f  test    ecx, ecx
0x18004e661  jnz     short loc_18004E66D
0x18004e663  mov     rax, [rbp+r14*8+8]
0x18004e668  mov     [r15], rax
0x18004e66b  jmp     short loc_18004E689
0x18004e66d  xor     ebx, ebx
0x18004e66f  mov     ecx, 521h; dwErrCode
0x18004e674  call    cs:__imp_SetLastError
0x18004e67a  jmp     short loc_18004E689
0x18004e67c  mov     r8, r15; lpLuid
0x18004e67f  xor     ecx, ecx; lpSystemName
0x18004e681  call    cs:__imp_LookupPrivilegeValueW
0x18004e687  mov     ebx, eax
0x18004e689  mov     eax, ebx
0x18004e68b  add     rsp, 28h
0x18004e68f  pop     r15
0x18004e691  pop     r14
0x18004e693  pop     rdi
0x18004e694  pop     rsi
0x18004e695  pop     rbp
0x18004e696  pop     rbx
0x18004e697  retn
```
