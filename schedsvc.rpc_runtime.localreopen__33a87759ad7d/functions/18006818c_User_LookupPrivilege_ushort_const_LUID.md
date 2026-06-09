# User::LookupPrivilege(ushort const *,_LUID &)

- ea: `0x18006818c`
- end: `0x180068220`
- name: `?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(LPCWSTR lpName, PLUID lpLuid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068294`
- `0x18007b05c`

## callees

- `0x18006818c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800681be`
- `msvcrt!_wcsicmp` at `0x1800681be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681fc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180068209`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180068209`

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
    if ( !_wcsicmp((&off_180086DD0)[2 * v2], lpName) )
      break;
    ++v2;
  }
  v6 = (&off_180086DD0)[2 * v2];
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
    *lpLuid = (struct _LUID)*(&off_180086DD0 + 2 * v2 + 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18006818c  push    rbx
0x18006818e  push    rbp
0x18006818f  push    rsi
0x180068190  push    rdi
0x180068191  push    r14
0x180068193  push    r15
0x180068195  sub     rsp, 28h
0x180068199  xor     edi, edi
0x18006819b  lea     rbp, off_180086DD0; "SeCreateTokenPrivilege"
0x1800681a2  mov     r15, rdx
0x1800681a5  mov     rsi, rcx
0x1800681a8  lea     ebx, [rdi+1]
0x1800681ab  mov     rdx, rsi; lpName
0x1800681ae  cmp     edi, 23h ; '#'
0x1800681b1  jnb     short loc_180068204
0x1800681b3  mov     r14d, edi
0x1800681b6  add     r14, r14
0x1800681b9  mov     rcx, [rbp+r14*8+0]; String1
0x1800681be  call    cs:__imp__wcsicmp
0x1800681c4  test    eax, eax
0x1800681c6  jz      short loc_1800681CC
0x1800681c8  add     edi, ebx
0x1800681ca  jmp     short loc_1800681AB
0x1800681cc  mov     rax, [rbp+r14*8+0]
0x1800681d1  sub     rsi, rax
0x1800681d4  movzx   ecx, word ptr [rax]
0x1800681d7  movzx   edx, word ptr [rax+rsi]
0x1800681db  sub     ecx, edx
0x1800681dd  jnz     short loc_1800681E7
0x1800681df  add     rax, 2
0x1800681e3  test    edx, edx
0x1800681e5  jnz     short loc_1800681D4
0x1800681e7  test    ecx, ecx
0x1800681e9  jnz     short loc_1800681F5
0x1800681eb  mov     rax, [rbp+r14*8+8]
0x1800681f0  mov     [r15], rax
0x1800681f3  jmp     short loc_180068211
0x1800681f5  xor     ebx, ebx
0x1800681f7  mov     ecx, 521h; dwErrCode
0x1800681fc  call    cs:__imp_SetLastError
0x180068202  jmp     short loc_180068211
0x180068204  mov     r8, r15; lpLuid
0x180068207  xor     ecx, ecx; lpSystemName
0x180068209  call    cs:__imp_LookupPrivilegeValueW
0x18006820f  mov     ebx, eax
0x180068211  mov     eax, ebx
0x180068213  add     rsp, 28h
0x180068217  pop     r15
0x180068219  pop     r14
0x18006821b  pop     rdi
0x18006821c  pop     rsi
0x18006821d  pop     rbp
0x18006821e  pop     rbx
0x18006821f  retn
```
