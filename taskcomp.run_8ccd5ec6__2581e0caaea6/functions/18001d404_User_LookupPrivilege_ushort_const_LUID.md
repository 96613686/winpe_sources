# User::LookupPrivilege(ushort const *,_LUID &)

- ea: `0x18001d404`
- end: `0x18001d4ab`
- name: `?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(LPCWSTR lpName, PLUID lpLuid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ccc`
- `0x18002096c`

## callees

- `0x18001d404`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d436`
- `msvcrt!_wcsicmp` at `0x18001d436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d47a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d47a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001d48d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001d48d`

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
    if ( !_wcsicmp((&off_180035250)[2 * v2], lpName) )
      break;
    ++v2;
  }
  v6 = (&off_180035250)[2 * v2];
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
    *lpLuid = (struct _LUID)*(&off_180035250 + 2 * v2 + 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18001d404  push    rbx
0x18001d406  push    rbp
0x18001d407  push    rsi
0x18001d408  push    rdi
0x18001d409  push    r14
0x18001d40b  push    r15
0x18001d40d  sub     rsp, 28h
0x18001d411  xor     edi, edi
0x18001d413  lea     rbp, off_180035250; "SeCreateTokenPrivilege"
0x18001d41a  mov     r15, rdx
0x18001d41d  mov     rsi, rcx
0x18001d420  lea     ebx, [rdi+1]
0x18001d423  mov     rdx, rsi; lpName
0x18001d426  cmp     edi, 23h ; '#'
0x18001d429  jnb     short loc_18001D488
0x18001d42b  mov     r14d, edi
0x18001d42e  add     r14, r14
0x18001d431  mov     rcx, [rbp+r14*8+0]; String1
0x18001d436  call    cs:__imp__wcsicmp
0x18001d43d  nop     dword ptr [rax+rax+00h]
0x18001d442  test    eax, eax
0x18001d444  jz      short loc_18001D44A
0x18001d446  add     edi, ebx
0x18001d448  jmp     short loc_18001D423
0x18001d44a  mov     rax, [rbp+r14*8+0]
0x18001d44f  sub     rsi, rax
0x18001d452  movzx   ecx, word ptr [rax]
0x18001d455  movzx   edx, word ptr [rax+rsi]
0x18001d459  sub     ecx, edx
0x18001d45b  jnz     short loc_18001D465
0x18001d45d  add     rax, 2
0x18001d461  test    edx, edx
0x18001d463  jnz     short loc_18001D452
0x18001d465  test    ecx, ecx
0x18001d467  jnz     short loc_18001D473
0x18001d469  mov     rax, [rbp+r14*8+8]
0x18001d46e  mov     [r15], rax
0x18001d471  jmp     short loc_18001D49B
0x18001d473  xor     ebx, ebx
0x18001d475  mov     ecx, 521h; dwErrCode
0x18001d47a  call    cs:__imp_SetLastError
0x18001d481  nop     dword ptr [rax+rax+00h]
0x18001d486  jmp     short loc_18001D49B
0x18001d488  mov     r8, r15; lpLuid
0x18001d48b  xor     ecx, ecx; lpSystemName
0x18001d48d  call    cs:__imp_LookupPrivilegeValueW
0x18001d494  nop     dword ptr [rax+rax+00h]
0x18001d499  mov     ebx, eax
0x18001d49b  mov     eax, ebx
0x18001d49d  add     rsp, 28h
0x18001d4a1  pop     r15
0x18001d4a3  pop     r14
0x18001d4a5  pop     rdi
0x18001d4a6  pop     rsi
0x18001d4a7  pop     rbp
0x18001d4a8  pop     rbx
0x18001d4a9  retn
```
