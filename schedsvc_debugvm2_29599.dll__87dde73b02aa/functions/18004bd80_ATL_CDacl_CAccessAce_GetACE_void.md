# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x18004bd80`
- end: `0x18004be32`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `178`
- prototype: `void *__fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001fc54`
- `0x18004bd80`
- `0x1800504b4`
- `0x18007e68a`
- `0x180084010`

## import_xrefs

- `msvcrt!malloc` at `0x18004bdac`
- `msvcrt!malloc` at `0x18004bdac`
- `msvcrt!memcpy_s` at `0x18004be12`
- `msvcrt!memcpy_s` at `0x18004be12`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004bdfd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004bdfd`

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
0x18004bd80  push    rbx
0x18004bd82  push    rbp
0x18004bd83  push    rsi
0x18004bd84  push    rdi
0x18004bd85  sub     rsp, 28h
0x18004bd89  mov     rdi, [rcx+88h]
0x18004bd90  mov     rsi, rcx
0x18004bd93  test    rdi, rdi
0x18004bd96  jnz     loc_18004BE26
0x18004bd9c  mov     rax, [rcx]
0x18004bd9f  mov     rax, [rax+10h]
0x18004bda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bda8  mov     ecx, eax; Size
0x18004bdaa  mov     ebx, eax
0x18004bdac  call    cs:__imp_malloc
0x18004bdb2  mov     rdi, rax
0x18004bdb5  test    rax, rax
0x18004bdb8  jnz     short loc_18004BDC5
0x18004bdba  mov     ecx, 8007000Eh; unsigned int
0x18004bdbf  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004bdc5  mov     r8, rbx; Size
0x18004bdc8  xor     edx, edx; Val
0x18004bdca  mov     rcx, rdi; void *
0x18004bdcd  call    memset_0
0x18004bdd2  mov     al, [rsi+84h]
0x18004bdd8  mov     rcx, rsi
0x18004bddb  mov     [rdi+1], al
0x18004bdde  mov     rax, [rsi]
0x18004bde1  mov     [rdi+2], bx
0x18004bde5  mov     rax, [rax+18h]
0x18004bde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdee  mov     [rdi], al
0x18004bdf0  lea     rcx, [rsi+10h]; pSid
0x18004bdf4  mov     eax, [rsi+80h]
0x18004bdfa  mov     [rdi+4], eax
0x18004bdfd  call    cs:__imp_GetLengthSid
0x18004be03  mov     r9d, eax; SourceSize
0x18004be06  lea     rdx, [rbx-8]; DestinationSize
0x18004be0a  lea     rcx, [rdi+8]; Destination
0x18004be0e  lea     r8, [rsi+10h]; Source
0x18004be12  call    cs:__imp_memcpy_s
0x18004be18  mov     ecx, eax; int
0x18004be1a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004be1f  mov     [rsi+88h], rdi
0x18004be26  mov     rax, rdi
0x18004be29  add     rsp, 28h
0x18004be2d  pop     rdi
0x18004be2e  pop     rsi
0x18004be2f  pop     rbp
0x18004be30  pop     rbx
0x18004be31  retn
```
