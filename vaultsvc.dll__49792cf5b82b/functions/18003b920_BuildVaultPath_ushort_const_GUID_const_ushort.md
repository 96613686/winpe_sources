# BuildVaultPath(ushort const *,_GUID const *,ushort * *)

- ea: `0x18003b920`
- end: `0x18003b9a5`
- name: `?BuildVaultPath@@YAKPEBGPEBU_GUID@@PEAPEAG@Z`
- size: `133`
- prototype: `unsigned int __fastcall(wchar_t *Source, const struct _GUID *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18003c784`
- `0x18003cc10`
- `0x18003d960`

## callees

- `0x18001b5a0`
- `0x1800354f4`
- `0x18003a580`
- `0x18003b920`

## pseudocode

```c
__int64 __fastcall BuildVaultPath(wchar_t *Source, const struct _GUID *a2, unsigned __int16 **a3)
{
  __int64 result; // rax
  unsigned __int16 *v6; // [rsp+20h] [rbp-78h] BYREF
  wchar_t v7[40]; // [rsp+30h] [rbp-68h] BYREF

  v6 = 0;
  ConvertGuidToString(a2, v7, 0x25u);
  result = PathCombine(Source, v7, &v6);
  if ( !(_DWORD)result )
  {
    *a3 = v6;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003b920  mov     [rsp+arg_18], rbx
0x18003b925  push    rdi
0x18003b926  sub     rsp, 90h
0x18003b92d  mov     rax, cs:__security_cookie
0x18003b934  xor     rax, rsp
0x18003b937  mov     [rsp+98h+var_18], rax
0x18003b93f  mov     rax, rdx
0x18003b942  mov     [rsp+98h+var_78], 0
0x18003b94b  mov     rdi, r8
0x18003b94e  lea     rdx, [rsp+98h+var_68]; unsigned __int16 *
0x18003b953  mov     rbx, rcx
0x18003b956  mov     r8d, 25h ; '%'; unsigned int
0x18003b95c  mov     rcx, rax; struct _GUID *
0x18003b95f  call    ?ConvertGuidToString@@YAKPEBU_GUID@@PEAGK@Z; ConvertGuidToString(_GUID const *,ushort *,ulong)
0x18003b964  lea     r8, [rsp+98h+var_78]; unsigned __int16 **
0x18003b969  mov     rcx, rbx; Source
0x18003b96c  lea     rdx, [rsp+98h+var_68]; wchar_t *
0x18003b971  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x18003b976  test    eax, eax
0x18003b978  jnz     short loc_18003B984
0x18003b97a  mov     rax, [rsp+98h+var_78]
0x18003b97f  mov     [rdi], rax
0x18003b982  xor     eax, eax
0x18003b984  mov     rcx, [rsp+98h+var_18]
0x18003b98c  xor     rcx, rsp; StackCookie
0x18003b98f  call    __security_check_cookie
0x18003b994  mov     rbx, [rsp+98h+arg_18]
0x18003b99c  add     rsp, 90h
0x18003b9a3  pop     rdi
0x18003b9a4  retn
```
