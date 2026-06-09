# CImpersonateTokenBased::Impersonate(void)

- ea: `0x180016da0`
- end: `0x180016de1`
- name: `?Impersonate@CImpersonateTokenBased@@UEAAJXZ`
- size: `65`
- prototype: `__int64 __fastcall(CImpersonateTokenBased *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016da0`
- `0x180034010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016dc7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016dc7`

## pseudocode

```c
__int64 __fastcall CImpersonateTokenBased::Impersonate(CImpersonateTokenBased *this)
{
  HANDLE *v1; // rbx
  __int64 result; // rax
  BOOL v3; // eax
  unsigned int v4; // ecx

  v1 = (HANDLE *)((char *)this + 8);
  if ( *((_QWORD *)this + 1)
    || (result = (*(__int64 (__fastcall **)(CImpersonateTokenBased *, char *))(*(_QWORD *)this + 24LL))(
                   this,
                   (char *)this + 8),
        (int)result >= 0) )
  {
    v3 = ImpersonateLoggedOnUser(*v1);
    v4 = -2147467259;
    if ( v3 )
      return 0;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180016da0  push    rbx
0x180016da2  sub     rsp, 20h
0x180016da6  cmp     qword ptr [rcx+8], 0
0x180016dab  lea     rbx, [rcx+8]
0x180016daf  jnz     short loc_180016DC4
0x180016db1  mov     rax, [rcx]
0x180016db4  mov     rdx, rbx
0x180016db7  mov     rax, [rax+18h]
0x180016dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dc0  test    eax, eax
0x180016dc2  js      short loc_180016DDB
0x180016dc4  mov     rcx, [rbx]; hToken
0x180016dc7  call    cs:__imp_ImpersonateLoggedOnUser
0x180016dcd  xor     edx, edx
0x180016dcf  mov     ecx, 80004005h
0x180016dd4  test    eax, eax
0x180016dd6  cmovnz  ecx, edx
0x180016dd9  mov     eax, ecx
0x180016ddb  add     rsp, 20h
0x180016ddf  pop     rbx
0x180016de0  retn
```
