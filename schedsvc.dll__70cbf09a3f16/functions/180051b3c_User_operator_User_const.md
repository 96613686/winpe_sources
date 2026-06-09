# User::operator==(User const &)

- ea: `0x180051b3c`
- end: `0x180051c15`
- name: `??8User@@QEBA_NAEBV0@@Z`
- size: `217`
- prototype: `bool __fastcall(__int64 *, __int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004b2b4`
- `0x18004c6d0`
- `0x180050f58`
- `0x18005105c`
- `0x1800511b8`
- `0x180054700`
- `0x1800785f4`

## callees

- `0x180042f40`
- `0x180051b3c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180051bed`
- `msvcrt!_wcsicmp` at `0x180051bed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051bfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051bfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b5b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180051ba3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180051ba3`

## pseudocode

```c
bool __fastcall User::operator==(__int64 *a1, __int64 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v5; // rax
  bool v6; // di
  __int64 v7; // r8
  void *v8; // rcx
  void *v9; // rdx
  int v10; // eax
  __int64 v11; // r8
  const wchar_t ***v12; // rcx
  const wchar_t ***v13; // r9
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rcx

  v2 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v5 = *a1;
  v6 = 0;
  if ( !v5 )
  {
    if ( *a2 )
      goto LABEL_23;
    goto LABEL_8;
  }
  v7 = *a2;
  if ( *a2 )
  {
    if ( *(_BYTE *)v5 )
    {
      if ( !*(_BYTE *)v7 )
        goto LABEL_23;
    }
    else
    {
      if ( *(_BYTE *)v7 )
        goto LABEL_23;
      if ( v7 == v5 )
      {
LABEL_8:
        v6 = 1;
        goto LABEL_23;
      }
      v8 = *(void **)(v5 + 32);
      if ( v8 )
      {
        v9 = *(void **)(v7 + 32);
        if ( v9 )
        {
          v10 = EqualSid(v8, v9);
LABEL_22:
          v6 = v10 != 0;
          goto LABEL_23;
        }
      }
    }
    if ( !(unsigned __int8)_bstr_t::operator!(v5 + 8) && !(unsigned __int8)_bstr_t::operator!(v11 + 8) )
    {
      if ( *v12 )
        v14 = **v12;
      else
        v14 = 0;
      if ( *v13 )
        v15 = **v13;
      else
        v15 = 0;
      v10 = _wcsicmp(v15, v14);
      goto LABEL_22;
    }
  }
LABEL_23:
  LeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x180051b3c  mov     [rsp+arg_0], rbx
0x180051b41  mov     [rsp+arg_8], rsi
0x180051b46  push    rdi
0x180051b47  sub     rsp, 20h
0x180051b4b  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180051b52  mov     rdi, rcx
0x180051b55  mov     rcx, rbx; lpCriticalSection
0x180051b58  mov     rsi, rdx
0x180051b5b  call    cs:__imp_EnterCriticalSection
0x180051b61  mov     rax, [rdi]
0x180051b64  xor     edi, edi
0x180051b66  test    rax, rax
0x180051b69  jnz     short loc_180051B75
0x180051b6b  cmp     [rsi], rdi
0x180051b6e  jz      short loc_180051B8C
0x180051b70  jmp     loc_180051BF9
0x180051b75  mov     r8, [rsi]
0x180051b78  test    r8, r8
0x180051b7b  jz      short loc_180051BF9
0x180051b7d  cmp     [rax], dil
0x180051b80  jnz     short loc_180051BAB
0x180051b82  cmp     [r8], dil
0x180051b85  jnz     short loc_180051BF9
0x180051b87  cmp     r8, rax
0x180051b8a  jnz     short loc_180051B91
0x180051b8c  mov     dil, 1
0x180051b8f  jmp     short loc_180051BF9
0x180051b91  mov     rcx, [rax+20h]; pSid1
0x180051b95  test    rcx, rcx
0x180051b98  jz      short loc_180051BB0
0x180051b9a  mov     rdx, [r8+20h]; pSid2
0x180051b9e  test    rdx, rdx
0x180051ba1  jz      short loc_180051BB0
0x180051ba3  call    cs:__imp_EqualSid
0x180051ba9  jmp     short loc_180051BF3
0x180051bab  cmp     [r8], dil
0x180051bae  jz      short loc_180051BF9
0x180051bb0  lea     r9, [rax+8]
0x180051bb4  mov     rcx, r9
0x180051bb7  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180051bbc  test    al, al
0x180051bbe  jnz     short loc_180051BF9
0x180051bc0  lea     rcx, [r8+8]
0x180051bc4  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180051bc9  test    al, al
0x180051bcb  jnz     short loc_180051BF9
0x180051bcd  mov     rax, [rcx]
0x180051bd0  test    rax, rax
0x180051bd3  jz      short loc_180051BDA
0x180051bd5  mov     rdx, [rax]
0x180051bd8  jmp     short loc_180051BDD
0x180051bda  mov     rdx, rdi; String2
0x180051bdd  mov     rax, [r9]
0x180051be0  test    rax, rax
0x180051be3  jz      short loc_180051BEA
0x180051be5  mov     rcx, [rax]
0x180051be8  jmp     short loc_180051BED
0x180051bea  mov     rcx, rdi; String1
0x180051bed  call    cs:__imp__wcsicmp
0x180051bf3  test    eax, eax
0x180051bf5  setnz   dil
0x180051bf9  mov     rcx, rbx; lpCriticalSection
0x180051bfc  call    cs:__imp_LeaveCriticalSection
0x180051c02  mov     rbx, [rsp+28h+arg_0]
0x180051c07  mov     al, dil
0x180051c0a  mov     rsi, [rsp+28h+arg_8]
0x180051c0f  add     rsp, 20h
0x180051c13  pop     rdi
0x180051c14  retn
```
