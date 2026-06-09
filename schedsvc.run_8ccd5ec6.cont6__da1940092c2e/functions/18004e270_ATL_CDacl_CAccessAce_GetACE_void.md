# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x18004e270`
- end: `0x18004e335`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `197`
- prototype: `void *__fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002c2f4`
- `0x18004e270`
- `0x1800529a0`
- `0x1800829fa`
- `0x180088010`

## import_xrefs

- `msvcrt!malloc` at `0x18004e29c`
- `msvcrt!malloc` at `0x18004e29c`
- `msvcrt!memcpy_s` at `0x18004e30e`
- `msvcrt!memcpy_s` at `0x18004e30e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e2f3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e2f3`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessAce::GetACE(ATL::CDacl::CAccessAce *this)
{
  char *v1; // rdi
  size_t v3; // rbx
  char *v4; // rax
  __int64 v5; // rax
  DWORD LengthSid; // eax
  errno_t v7; // eax

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::PrivateAtlThrow(0x8007000E);
    memset_0(v4, 0, v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    *v1 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessAce *))(v5 + 24))(this);
    *((_DWORD *)v1 + 1) = *((_DWORD *)this + 32);
    LengthSid = GetLengthSid((char *)this + 16);
    v7 = memcpy_s(v1 + 8, v3 - 8, (char *)this + 16, LengthSid);
    ATL::AtlCrtErrorCheck(v7);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x18004e270  push    rbx
0x18004e272  push    rbp
0x18004e273  push    rsi
0x18004e274  push    rdi
0x18004e275  sub     rsp, 28h
0x18004e279  mov     rdi, [rcx+88h]
0x18004e280  mov     rsi, rcx
0x18004e283  test    rdi, rdi
0x18004e286  jnz     loc_18004E328
0x18004e28c  mov     rax, [rcx]
0x18004e28f  mov     rax, [rax+10h]
0x18004e293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e298  mov     ecx, eax; Size
0x18004e29a  mov     ebx, eax
0x18004e29c  call    cs:__imp_malloc
0x18004e2a3  nop     dword ptr [rax+rax+00h]
0x18004e2a8  mov     rdi, rax
0x18004e2ab  test    rax, rax
0x18004e2ae  jnz     short loc_18004E2BB
0x18004e2b0  mov     ecx, 8007000Eh; unsigned int
0x18004e2b5  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004e2bb  mov     r8, rbx; Size
0x18004e2be  xor     edx, edx; Val
0x18004e2c0  mov     rcx, rdi; void *
0x18004e2c3  call    memset_0
0x18004e2c8  mov     al, [rsi+84h]
0x18004e2ce  mov     rcx, rsi
0x18004e2d1  mov     [rdi+1], al
0x18004e2d4  mov     rax, [rsi]
0x18004e2d7  mov     [rdi+2], bx
0x18004e2db  mov     rax, [rax+18h]
0x18004e2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2e4  mov     [rdi], al
0x18004e2e6  lea     rcx, [rsi+10h]; pSid
0x18004e2ea  mov     eax, [rsi+80h]
0x18004e2f0  mov     [rdi+4], eax
0x18004e2f3  call    cs:__imp_GetLengthSid
0x18004e2fa  nop     dword ptr [rax+rax+00h]
0x18004e2ff  mov     r9d, eax; SourceSize
0x18004e302  lea     rdx, [rbx-8]; DestinationSize
0x18004e306  lea     rcx, [rdi+8]; Destination
0x18004e30a  lea     r8, [rsi+10h]; Source
0x18004e30e  call    cs:__imp_memcpy_s
0x18004e315  nop     dword ptr [rax+rax+00h]
0x18004e31a  mov     ecx, eax; int
0x18004e31c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004e321  mov     [rsi+88h], rdi
0x18004e328  mov     rax, rdi
0x18004e32b  add     rsp, 28h
0x18004e32f  pop     rdi
0x18004e330  pop     rsi
0x18004e331  pop     rbp
0x18004e332  pop     rbx
0x18004e333  retn
```
