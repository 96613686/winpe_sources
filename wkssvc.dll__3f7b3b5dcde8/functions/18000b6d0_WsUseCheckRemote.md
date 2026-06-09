# WsUseCheckRemote

- ea: `0x18000b6d0`
- end: `0x18000b763`
- name: `WsUseCheckRemote`
- size: `147`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800299a4`

## callees

- `0x18000b6d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b734`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b734`
- `netutils!NetpwPathCanonicalize` at `0x18000b721`
- `netutils!NetpwPathCanonicalize` at `0x18000b721`
- `netutils!NetpwPathType` at `0x18000b6f0`
- `netutils!NetpwPathType` at `0x18000b6f0`

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
0x18000b6d0  push    rbx
0x18000b6d2  push    rbp
0x18000b6d3  push    rsi
0x18000b6d4  push    rdi
0x18000b6d5  sub     rsp, 38h
0x18000b6d9  mov     rsi, r8
0x18000b6dc  mov     rbx, rdx
0x18000b6df  xor     ebp, ebp
0x18000b6e1  lea     rdx, [rsp+58h+arg_18]
0x18000b6e6  xor     r8d, r8d
0x18000b6e9  mov     [rsp+58h+arg_18], ebp
0x18000b6ed  mov     rdi, rcx
0x18000b6f0  call    cs:__imp_NetpwPathType
0x18000b6f6  test    eax, eax
0x18000b6f8  jnz     short loc_18000B753
0x18000b6fa  cmp     [rsp+58h+arg_18], 1000h
0x18000b702  jnz     short loc_18000B75C
0x18000b704  lea     rax, [rsp+58h+arg_18]
0x18000b709  mov     [rsp+58h+var_30], ebp
0x18000b70d  xor     r9d, r9d
0x18000b710  mov     [rsp+58h+var_38], rax
0x18000b715  mov     r8d, 208h
0x18000b71b  mov     rdx, rbx
0x18000b71e  mov     rcx, rdi
0x18000b721  call    cs:__imp_NetpwPathCanonicalize
0x18000b727  test    eax, eax
0x18000b729  jnz     short loc_18000B753
0x18000b72b  mov     edx, 5Ch ; '\'; Ch
0x18000b730  lea     rcx, [rbx+4]; Str
0x18000b734  call    cs:__imp_wcschr
0x18000b73a  test    rax, rax
0x18000b73d  jz      short loc_18000B75C
0x18000b73f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b746  inc     rax
0x18000b749  cmp     [rbx+rax*2], bp
0x18000b74d  jnz     short loc_18000B746
0x18000b74f  mov     [rsi], eax
0x18000b751  xor     eax, eax
0x18000b753  add     rsp, 38h
0x18000b757  pop     rdi
0x18000b758  pop     rsi
0x18000b759  pop     rbp
0x18000b75a  pop     rbx
0x18000b75b  retn
0x18000b75c  mov     eax, 57h ; 'W'
0x18000b761  jmp     short loc_18000B753
```
