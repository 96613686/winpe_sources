# PolicyHelpers::ReadPolicyString(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18001f328`
- end: `0x18001f443`
- name: `?ReadPolicyString@PolicyHelpers@@SAJPEB_W0PEAPEA_W@Z`
- size: `283`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18001e704`
- `0x18001f880`

## callees

- `0x18001f328`
- `0x18002ffd0`
- `0x18003002c`
- `0x180030038`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f398`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f405`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f398`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f405`

## pseudocode

```c
__int64 __fastcall PolicyHelpers::ReadPolicyString(LPCWSTR lpSubKey, LPCWSTR lpValue, wchar_t **a3)
{
  __int64 result; // rax
  LSTATUS ValueW; // ebx
  unsigned __int64 v8; // rax
  void *pvData; // rdi
  DWORD pcbData; // [rsp+40h] [rbp-38h] BYREF

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValue, 2u, 0, 0, &pcbData);
  if ( !ValueW )
  {
    v8 = 2 * ((unsigned __int64)pcbData >> 1);
    if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
      v8 = -1;
    pvData = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    if ( !pvData )
      return 2147942414LL;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValue, 2u, 0, pvData, &pcbData);
    if ( ValueW )
      operator delete(pvData);
    else
      *a3 = (wchar_t *)pvData;
  }
  result = (unsigned __int16)ValueW | 0x80070000;
  if ( ValueW <= 0 )
    return (unsigned int)ValueW;
  return result;
}

```

## disassembly

```asm
0x18001f328  push    rbx
0x18001f32a  push    rbp
0x18001f32b  push    rsi
0x18001f32c  push    rdi
0x18001f32d  push    r14
0x18001f32f  sub     rsp, 50h
0x18001f333  mov     rax, cs:__security_cookie
0x18001f33a  xor     rax, rsp
0x18001f33d  mov     [rsp+78h+var_30], rax
0x18001f342  mov     rsi, r8
0x18001f345  mov     r14, rdx
0x18001f348  mov     rbp, rcx
0x18001f34b  test    r8, r8
0x18001f34e  jnz     short loc_18001F35A
0x18001f350  mov     eax, 80004003h
0x18001f355  jmp     loc_18001F42B
0x18001f35a  lea     rax, [rsp+78h+var_38]
0x18001f35f  mov     qword ptr [r8], 0
0x18001f366  mov     [rsp+78h+pcbData], rax; pcbData
0x18001f36b  mov     r9d, 2; dwFlags
0x18001f371  mov     [rsp+78h+pvData], 0; pvData
0x18001f37a  mov     r8, r14; lpValue
0x18001f37d  mov     rdx, rbp; lpSubKey
0x18001f380  mov     [rsp+78h+pdwType], 0; pdwType
0x18001f389  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f390  mov     [rsp+78h+var_38], 0
0x18001f398  call    cs:__imp_RegGetValueW
0x18001f39e  mov     ebx, eax
0x18001f3a0  test    eax, eax
0x18001f3a2  jnz     short loc_18001F41E
0x18001f3a4  mov     ecx, [rsp+78h+var_38]
0x18001f3a8  lea     eax, [rbx+2]
0x18001f3ab  shr     rcx, 1
0x18001f3ae  mul     rcx
0x18001f3b1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f3b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f3bf  cmovb   rax, rcx
0x18001f3c3  mov     rcx, rax; unsigned __int64
0x18001f3c6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f3cb  mov     rdi, rax
0x18001f3ce  test    rax, rax
0x18001f3d1  jnz     short loc_18001F3DA
0x18001f3d3  mov     eax, 8007000Eh
0x18001f3d8  jmp     short loc_18001F42B
0x18001f3da  lea     rax, [rsp+78h+var_38]
0x18001f3df  mov     r9d, 2; dwFlags
0x18001f3e5  mov     [rsp+78h+pcbData], rax; pcbData
0x18001f3ea  mov     r8, r14; lpValue
0x18001f3ed  mov     [rsp+78h+pvData], rdi; pvData
0x18001f3f2  mov     rdx, rbp; lpSubKey
0x18001f3f5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f3fc  mov     [rsp+78h+pdwType], 0; pdwType
0x18001f405  call    cs:__imp_RegGetValueW
0x18001f40b  mov     ebx, eax
0x18001f40d  test    eax, eax
0x18001f40f  jnz     short loc_18001F416
0x18001f411  mov     [rsi], rdi
0x18001f414  jmp     short loc_18001F41E
0x18001f416  mov     rcx, rdi; Block
0x18001f419  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f41e  movzx   eax, bx
0x18001f421  or      eax, 80070000h
0x18001f426  test    ebx, ebx
0x18001f428  cmovle  eax, ebx
0x18001f42b  mov     rcx, [rsp+78h+var_30]
0x18001f430  xor     rcx, rsp; StackCookie
0x18001f433  call    __security_check_cookie
0x18001f438  add     rsp, 50h
0x18001f43c  pop     r14
0x18001f43e  pop     rdi
0x18001f43f  pop     rsi
0x18001f440  pop     rbp
0x18001f441  pop     rbx
0x18001f442  retn
```
