# wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()

- ea: `0x180007988`
- end: `0x1800079b2`
- name: `wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006608`
- `0x1800085b8`
- `0x18000a81c`
- `0x18001d6b4`
- `0x180023a38`
- `0x180023e54`
- `0x180024378`
- `0x180024aac`

## callees

- `0x180007988`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x1800079a4`
- `ncrypt!NCryptDeleteKey` at `0x1800079a4`

## pseudocode

```c
SECURITY_STATUS __fastcall wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()(
        __int64 a1)
{
  NCRYPT_KEY_HANDLE *v1; // rax
  NCRYPT_KEY_HANDLE v2; // rcx
  SECURITY_STATUS result; // eax

  if ( *(_BYTE *)(a1 + 9) )
  {
    *(_BYTE *)(a1 + 9) = 0;
    v1 = *(NCRYPT_KEY_HANDLE **)a1;
    v2 = **(_QWORD **)a1;
    *v1 = 0;
    return NCryptDeleteKey(v2, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180007988  mov     [rsp+arg_0], rcx
0x18000798d  sub     rsp, 28h
0x180007991  xor     edx, edx; dwFlags
0x180007993  cmp     [rcx+9], dl
0x180007996  jz      short loc_1800079AB
0x180007998  mov     [rcx+9], dl
0x18000799b  mov     rax, [rcx]
0x18000799e  mov     rcx, [rax]; hKey
0x1800079a1  mov     [rax], rdx
0x1800079a4  call    cs:__imp_NCryptDeleteKey
0x1800079aa  nop
0x1800079ab  jmp     short $+2
0x1800079ad  add     rsp, 28h
0x1800079b1  retn
```
