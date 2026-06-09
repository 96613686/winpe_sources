# VaultAccessCheckVault

- ea: `0x180027550`
- end: `0x180027603`
- name: `VaultAccessCheckVault`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180027550`
- `0x180027630`
- `0x18003a580`
- `0x18004b430`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall VaultAccessCheckVault(unsigned int a1, __int64 a2)
{
  BOOL v4; // edx
  _BYTE Buf1[16]; // [rsp+20h] [rbp-28h] BYREF

  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 24LL))(a2, Buf1);
  v4 = !memcmp_0(Buf1, &Vault_DefaultVault_ID, 0x10u) || !memcmp_0(Buf1, Vault_GlobalSchemaVault, 0x10u);
  if ( (a1 <= 2 || a1 == 4) && v4 )
    return 1;
  else
    return VaultAccessCheckCommon(a1, a2);
}

```

## disassembly

```asm
0x180027550  mov     [rsp+arg_10], rbx
0x180027555  push    rdi
0x180027556  sub     rsp, 40h
0x18002755a  mov     rax, cs:__security_cookie
0x180027561  xor     rax, rsp
0x180027564  mov     [rsp+48h+var_18], rax
0x180027569  mov     rax, [rdx]
0x18002756c  mov     rdi, rdx
0x18002756f  mov     ebx, ecx
0x180027571  lea     rdx, [rsp+48h+Buf1]
0x180027576  mov     rcx, rdi
0x180027579  mov     rax, [rax+18h]
0x18002757d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027582  mov     r8d, 10h; Size
0x180027588  lea     rdx, Vault_DefaultVault_ID; Buf2
0x18002758f  lea     rcx, [rsp+48h+Buf1]; Buf1
0x180027594  call    memcmp_0
0x180027599  test    eax, eax
0x18002759b  jnz     short loc_1800275D8
0x18002759d  mov     edx, 1
0x1800275a2  mov     ecx, ebx
0x1800275a4  test    ebx, ebx
0x1800275a6  jz      short loc_1800275B7
0x1800275a8  sub     ecx, 1
0x1800275ab  jz      short loc_1800275B7
0x1800275ad  sub     ecx, 1
0x1800275b0  jz      short loc_1800275B7
0x1800275b2  cmp     ecx, 2
0x1800275b5  jnz     short loc_1800275F7
0x1800275b7  test    edx, edx
0x1800275b9  jz      short loc_1800275F7
0x1800275bb  mov     eax, 1
0x1800275c0  mov     rcx, [rsp+48h+var_18]
0x1800275c5  xor     rcx, rsp; StackCookie
0x1800275c8  call    __security_check_cookie
0x1800275cd  mov     rbx, [rsp+48h+arg_10]
0x1800275d2  add     rsp, 40h
0x1800275d6  pop     rdi
0x1800275d7  retn
0x1800275d8  mov     r8d, 10h; Size
0x1800275de  lea     rdx, Vault_GlobalSchemaVault; Buf2
0x1800275e5  lea     rcx, [rsp+48h+Buf1]; Buf1
0x1800275ea  call    memcmp_0
0x1800275ef  test    eax, eax
0x1800275f1  jz      short loc_18002759D
0x1800275f3  xor     edx, edx
0x1800275f5  jmp     short loc_1800275A2
0x1800275f7  mov     rdx, rdi
0x1800275fa  mov     ecx, ebx
0x1800275fc  call    VaultAccessCheckCommon
0x180027601  jmp     short loc_1800275C0
```
