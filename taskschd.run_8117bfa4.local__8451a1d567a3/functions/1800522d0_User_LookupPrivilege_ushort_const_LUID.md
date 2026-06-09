# User::LookupPrivilege(ushort const *,_LUID &)

- ea: `0x1800522d0`
- end: `0x180052377`
- name: `?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(LPCWSTR lpName, PLUID lpLuid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180040d40`
- `0x18004f180`

## callees

- `0x1800522d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180052302`
- `msvcrt!_wcsicmp` at `0x180052302`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052346`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180052359`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180052359`

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
    if ( !_wcsicmp((&off_180078E50)[2 * v2], lpName) )
      break;
    ++v2;
  }
  v6 = (&off_180078E50)[2 * v2];
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
    *lpLuid = (struct _LUID)*(&off_180078E50 + 2 * v2 + 1);
  }
  return v5;
}

```

## disassembly

```asm
0x1800522d0  push    rbx
0x1800522d2  push    rbp
0x1800522d3  push    rsi
0x1800522d4  push    rdi
0x1800522d5  push    r14
0x1800522d7  push    r15
0x1800522d9  sub     rsp, 28h
0x1800522dd  xor     edi, edi
0x1800522df  lea     rbp, off_180078E50; "SeCreateTokenPrivilege"
0x1800522e6  mov     r15, rdx
0x1800522e9  mov     rsi, rcx
0x1800522ec  lea     ebx, [rdi+1]
0x1800522ef  mov     rdx, rsi; lpName
0x1800522f2  cmp     edi, 23h ; '#'
0x1800522f5  jnb     short loc_180052354
0x1800522f7  mov     r14d, edi
0x1800522fa  add     r14, r14
0x1800522fd  mov     rcx, [rbp+r14*8+0]; String1
0x180052302  call    cs:__imp__wcsicmp
0x180052309  nop     dword ptr [rax+rax+00h]
0x18005230e  test    eax, eax
0x180052310  jz      short loc_180052316
0x180052312  add     edi, ebx
0x180052314  jmp     short loc_1800522EF
0x180052316  mov     rax, [rbp+r14*8+0]
0x18005231b  sub     rsi, rax
0x18005231e  movzx   ecx, word ptr [rax]
0x180052321  movzx   edx, word ptr [rax+rsi]
0x180052325  sub     ecx, edx
0x180052327  jnz     short loc_180052331
0x180052329  add     rax, 2
0x18005232d  test    edx, edx
0x18005232f  jnz     short loc_18005231E
0x180052331  test    ecx, ecx
0x180052333  jnz     short loc_18005233F
0x180052335  mov     rax, [rbp+r14*8+8]
0x18005233a  mov     [r15], rax
0x18005233d  jmp     short loc_180052367
0x18005233f  xor     ebx, ebx
0x180052341  mov     ecx, 521h; dwErrCode
0x180052346  call    cs:__imp_SetLastError
0x18005234d  nop     dword ptr [rax+rax+00h]
0x180052352  jmp     short loc_180052367
0x180052354  mov     r8, r15; lpLuid
0x180052357  xor     ecx, ecx; lpSystemName
0x180052359  call    cs:__imp_LookupPrivilegeValueW
0x180052360  nop     dword ptr [rax+rax+00h]
0x180052365  mov     ebx, eax
0x180052367  mov     eax, ebx
0x180052369  add     rsp, 28h
0x18005236d  pop     r15
0x18005236f  pop     r14
0x180052371  pop     rdi
0x180052372  pop     rsi
0x180052373  pop     rbp
0x180052374  pop     rbx
0x180052375  retn
```
