# DoesSecurityPolicyAllow

- ea: `0x140004428`
- end: `0x14000448f`
- name: `DoesSecurityPolicyAllow`
- size: `103`
- prototype: `bool __fastcall(int (__fastcall *)(_QWORD, __int64, __int64, int *), __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007798`

## callees

- `0x140004428`
- `0x14000535c`
- `0x14000c010`

## pseudocode

```c
bool __fastcall DoesSecurityPolicyAllow(int (__fastcall *a1)(_QWORD, __int64, __int64, int *), __int64 a2, __int64 a3)
{
  int v7; // [rsp+58h] [rbp+20h] BYREF

  if ( !(unsigned __int8)IsUMCIEnabled() )
    return 1;
  v7 = 0;
  return a1 && a1(0, a2, a3, &v7) >= 0 && v7 != 0;
}

```

## disassembly

```asm
0x140004428  mov     [rsp+arg_0], rbx
0x14000442d  mov     [rsp+arg_8], rsi
0x140004432  push    rdi
0x140004433  sub     rsp, 30h
0x140004437  mov     rdi, r8
0x14000443a  mov     rsi, rdx
0x14000443d  mov     rbx, rcx
0x140004440  call    IsUMCIEnabled
0x140004445  test    al, al
0x140004447  jnz     short loc_14000444D
0x140004449  mov     al, 1
0x14000444b  jmp     short loc_14000447F
0x14000444d  mov     [rsp+38h+arg_18], 0
0x140004455  test    rbx, rbx
0x140004458  jz      short loc_14000447D
0x14000445a  lea     r9, [rsp+38h+arg_18]
0x14000445f  mov     r8, rdi
0x140004462  mov     rdx, rsi
0x140004465  xor     ecx, ecx
0x140004467  mov     rax, rbx
0x14000446a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000446f  test    eax, eax
0x140004471  js      short loc_14000447D
0x140004473  cmp     [rsp+38h+arg_18], 0
0x140004478  setnz   al
0x14000447b  jmp     short loc_14000447F
0x14000447d  xor     al, al
0x14000447f  mov     rbx, [rsp+38h+arg_0]
0x140004484  mov     rsi, [rsp+38h+arg_8]
0x140004489  add     rsp, 30h
0x14000448d  pop     rdi
0x14000448e  retn
```
