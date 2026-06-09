# EnablePrivilegeEx

- ea: `0x18000c254`
- end: `0x18000c2a9`
- name: `EnablePrivilegeEx`
- size: `85`
- prototype: `__int64 __fastcall(LPCWSTR lpName, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006868`
- `0x18000b720`

## callees

- `0x18000c254`
- `0x18000c2b0`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000c27c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000c27c`

## pseudocode

```c
__int64 __fastcall EnablePrivilegeEx(LPCWSTR lpName, unsigned int a2, __int64 a3)
{
  unsigned int v5; // ebx
  struct _LUID v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v5 = 0;
  if ( LookupPrivilegeValueW(0, lpName, &v7) )
    return (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))EnablePrivilegeInternal)(v7, a2, a3);
  return v5;
}

```

## disassembly

```asm
0x18000c254  mov     rax, rsp
0x18000c257  mov     [rax+8], rbx
0x18000c25b  mov     [rax+10h], rsi
0x18000c25f  push    rdi
0x18000c260  sub     rsp, 20h
0x18000c264  mov     esi, edx
0x18000c266  mov     qword ptr [rax+20h], 0
0x18000c26e  mov     rdx, rcx; lpName
0x18000c271  mov     rdi, r8
0x18000c274  xor     ecx, ecx; lpSystemName
0x18000c276  lea     r8, [rax+20h]; lpLuid
0x18000c27a  xor     ebx, ebx
0x18000c27c  call    cs:__imp_LookupPrivilegeValueW
0x18000c282  test    eax, eax
0x18000c284  jz      short loc_18000C297
0x18000c286  mov     rcx, [rsp+28h+arg_18]
0x18000c28b  mov     r8, rdi
0x18000c28e  mov     edx, esi
0x18000c290  call    EnablePrivilegeInternal
0x18000c295  mov     ebx, eax
0x18000c297  mov     rsi, [rsp+28h+arg_8]
0x18000c29c  mov     eax, ebx
0x18000c29e  mov     rbx, [rsp+28h+arg_0]
0x18000c2a3  add     rsp, 20h
0x18000c2a7  pop     rdi
0x18000c2a8  retn
```
