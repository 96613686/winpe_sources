# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x14004d8e0`
- end: `0x14004d98a`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `170`
- prototype: `void *__fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1400396dc`
- `0x140046d00`
- `0x14004d8e0`
- `0x140054390`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14004d95d`
- `ADVAPI32!GetLengthSid` at `0x14004d95d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004d90c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004d90c`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessAce::GetACE(ATL::CDacl::CAccessAce *this)
{
  char *v1; // rdi
  size_t v3; // rbx
  char *v4; // rax
  __int64 v5; // rax
  DWORD LengthSid; // eax
  unsigned __int64 v8; // [rsp+20h] [rbp-28h]

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
    memset_0(v4, 0, v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    *v1 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessAce *))(v5 + 24))(this);
    *((_DWORD *)v1 + 1) = *((_DWORD *)this + 32);
    LengthSid = GetLengthSid((char *)this + 16);
    ATL::Checked::memcpy_s(
      (ATL::Checked *)(v1 + 8),
      (void *)(v3 - 8),
      (unsigned __int64)this + 16,
      (const void *)LengthSid,
      v8);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x14004d8e0  push    rbx
0x14004d8e2  push    rbp
0x14004d8e3  push    rsi
0x14004d8e4  push    rdi
0x14004d8e5  sub     rsp, 28h
0x14004d8e9  mov     rdi, [rcx+88h]
0x14004d8f0  mov     rsi, rcx
0x14004d8f3  test    rdi, rdi
0x14004d8f6  jnz     loc_14004D97E
0x14004d8fc  mov     rax, [rcx]
0x14004d8ff  mov     rax, [rax+10h]
0x14004d903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d908  mov     ecx, eax; Size
0x14004d90a  mov     ebx, eax
0x14004d90c  call    cs:__imp_malloc
0x14004d912  mov     rdi, rax
0x14004d915  test    rax, rax
0x14004d918  jnz     short loc_14004D925
0x14004d91a  mov     ecx, 8007000Eh; int
0x14004d91f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004d925  mov     r8, rbx; Size
0x14004d928  xor     edx, edx; Val
0x14004d92a  mov     rcx, rdi; void *
0x14004d92d  call    memset_0
0x14004d932  mov     al, [rsi+84h]
0x14004d938  mov     rcx, rsi
0x14004d93b  mov     [rdi+1], al
0x14004d93e  mov     rax, [rsi]
0x14004d941  mov     [rdi+2], bx
0x14004d945  mov     rax, [rax+18h]
0x14004d949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d94e  mov     [rdi], al
0x14004d950  lea     rcx, [rsi+10h]; pSid
0x14004d954  mov     eax, [rsi+80h]
0x14004d95a  mov     [rdi+4], eax
0x14004d95d  call    cs:__imp_GetLengthSid
0x14004d963  mov     r9d, eax; void *
0x14004d966  lea     rdx, [rbx-8]; void *
0x14004d96a  lea     rcx, [rdi+8]; this
0x14004d96e  lea     r8, [rsi+10h]; unsigned __int64
0x14004d972  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x14004d977  mov     [rsi+88h], rdi
0x14004d97e  mov     rax, rdi
0x14004d981  add     rsp, 28h
0x14004d985  pop     rdi
0x14004d986  pop     rsi
0x14004d987  pop     rbp
0x14004d988  pop     rbx
0x14004d989  retn
```
