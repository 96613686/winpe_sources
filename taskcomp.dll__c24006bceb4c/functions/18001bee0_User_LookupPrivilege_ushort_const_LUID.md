# User::LookupPrivilege(ushort const *,_LUID &)

- ea: `0x18001bee0`
- end: `0x18001bf74`
- name: `?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(LPCWSTR lpName, PLUID lpLuid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800097dc`
- `0x18001f380`

## callees

- `0x18001bee0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001bf12`
- `msvcrt!_wcsicmp` at `0x18001bf12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf50`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001bf5d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001bf5d`

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
    if ( !_wcsicmp((&off_180033250)[2 * v2], lpName) )
      break;
    ++v2;
  }
  v6 = (&off_180033250)[2 * v2];
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
    *lpLuid = (struct _LUID)*(&off_180033250 + 2 * v2 + 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18001bee0  push    rbx
0x18001bee2  push    rbp
0x18001bee3  push    rsi
0x18001bee4  push    rdi
0x18001bee5  push    r14
0x18001bee7  push    r15
0x18001bee9  sub     rsp, 28h
0x18001beed  xor     edi, edi
0x18001beef  lea     rbp, off_180033250; "SeCreateTokenPrivilege"
0x18001bef6  mov     r15, rdx
0x18001bef9  mov     rsi, rcx
0x18001befc  lea     ebx, [rdi+1]
0x18001beff  mov     rdx, rsi; lpName
0x18001bf02  cmp     edi, 23h ; '#'
0x18001bf05  jnb     short loc_18001BF58
0x18001bf07  mov     r14d, edi
0x18001bf0a  add     r14, r14
0x18001bf0d  mov     rcx, [rbp+r14*8+0]; String1
0x18001bf12  call    cs:__imp__wcsicmp
0x18001bf18  test    eax, eax
0x18001bf1a  jz      short loc_18001BF20
0x18001bf1c  add     edi, ebx
0x18001bf1e  jmp     short loc_18001BEFF
0x18001bf20  mov     rax, [rbp+r14*8+0]
0x18001bf25  sub     rsi, rax
0x18001bf28  movzx   ecx, word ptr [rax]
0x18001bf2b  movzx   edx, word ptr [rax+rsi]
0x18001bf2f  sub     ecx, edx
0x18001bf31  jnz     short loc_18001BF3B
0x18001bf33  add     rax, 2
0x18001bf37  test    edx, edx
0x18001bf39  jnz     short loc_18001BF28
0x18001bf3b  test    ecx, ecx
0x18001bf3d  jnz     short loc_18001BF49
0x18001bf3f  mov     rax, [rbp+r14*8+8]
0x18001bf44  mov     [r15], rax
0x18001bf47  jmp     short loc_18001BF65
0x18001bf49  xor     ebx, ebx
0x18001bf4b  mov     ecx, 521h; dwErrCode
0x18001bf50  call    cs:__imp_SetLastError
0x18001bf56  jmp     short loc_18001BF65
0x18001bf58  mov     r8, r15; lpLuid
0x18001bf5b  xor     ecx, ecx; lpSystemName
0x18001bf5d  call    cs:__imp_LookupPrivilegeValueW
0x18001bf63  mov     ebx, eax
0x18001bf65  mov     eax, ebx
0x18001bf67  add     rsp, 28h
0x18001bf6b  pop     r15
0x18001bf6d  pop     r14
0x18001bf6f  pop     rdi
0x18001bf70  pop     rsi
0x18001bf71  pop     rbp
0x18001bf72  pop     rbx
0x18001bf73  retn
```
