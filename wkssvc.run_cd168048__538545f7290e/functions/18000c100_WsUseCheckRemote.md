# WsUseCheckRemote

- ea: `0x18000c100`
- end: `0x18000c1ae`
- name: `WsUseCheckRemote`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x18002be90`

## callees

- `0x18000c100`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000c170`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000c170`
- `netutils!NetpwPathCanonicalize` at `0x18000c157`
- `netutils!NetpwPathCanonicalize` at `0x18000c157`
- `netutils!NetpwPathType` at `0x18000c120`
- `netutils!NetpwPathType` at `0x18000c120`

## pseudocode

```c
__int64 __fastcall WsUseCheckRemote(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  int v8; // [rsp+78h] [rbp+20h] BYREF

  v8 = 0;
  result = NetpwPathType(a1, &v8, 0);
  if ( !(_DWORD)result )
  {
    if ( v8 != 4096 )
      return 87;
    result = NetpwPathCanonicalize(a1, a2, 520, 0, &v8, 0);
    if ( (_DWORD)result )
      return result;
    if ( !wcschr((const wchar_t *)(a2 + 4), 0x5Cu) )
      return 87;
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a2 + 2 * v7) );
    *a3 = v7;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c100  push    rbx
0x18000c102  push    rbp
0x18000c103  push    rsi
0x18000c104  push    rdi
0x18000c105  sub     rsp, 38h
0x18000c109  mov     rsi, r8
0x18000c10c  mov     rbx, rdx
0x18000c10f  xor     ebp, ebp
0x18000c111  lea     rdx, [rsp+58h+arg_18]
0x18000c116  xor     r8d, r8d
0x18000c119  mov     [rsp+58h+arg_18], ebp
0x18000c11d  mov     rdi, rcx
0x18000c120  call    cs:__imp_NetpwPathType
0x18000c127  nop     dword ptr [rax+rax+00h]
0x18000c12c  test    eax, eax
0x18000c12e  jnz     short loc_18000C19D
0x18000c130  cmp     [rsp+58h+arg_18], 1000h
0x18000c138  jnz     short loc_18000C1A7
0x18000c13a  lea     rax, [rsp+58h+arg_18]
0x18000c13f  mov     [rsp+58h+var_30], ebp
0x18000c143  xor     r9d, r9d
0x18000c146  mov     [rsp+58h+var_38], rax
0x18000c14b  mov     r8d, 208h
0x18000c151  mov     rdx, rbx
0x18000c154  mov     rcx, rdi
0x18000c157  call    cs:__imp_NetpwPathCanonicalize
0x18000c15e  nop     dword ptr [rax+rax+00h]
0x18000c163  test    eax, eax
0x18000c165  jnz     short loc_18000C19D
0x18000c167  mov     edx, 5Ch ; '\'; Ch
0x18000c16c  lea     rcx, [rbx+4]; Str
0x18000c170  call    cs:__imp_wcschr
0x18000c177  nop     dword ptr [rax+rax+00h]
0x18000c17c  test    rax, rax
0x18000c17f  jz      short loc_18000C1A7
0x18000c181  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c188  nop     dword ptr [rax+rax+00000000h]
0x18000c190  inc     rax
0x18000c193  cmp     [rbx+rax*2], bp
0x18000c197  jnz     short loc_18000C190
0x18000c199  mov     [rsi], eax
0x18000c19b  xor     eax, eax
0x18000c19d  add     rsp, 38h
0x18000c1a1  pop     rdi
0x18000c1a2  pop     rsi
0x18000c1a3  pop     rbp
0x18000c1a4  pop     rbx
0x18000c1a5  retn
0x18000c1a7  mov     eax, 57h ; 'W'
0x18000c1ac  jmp     short loc_18000C19D
```
