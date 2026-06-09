# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x140001ef0`
- end: `0x140001fa4`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `180`
- prototype: `char *__fastcall(ATL::CDacl::CAccessAce *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001ef0`
- `0x140003130`
- `0x1400072bc`
- `0x140007b4f`
- `0x14000c010`

## import_xrefs

- `msvcrt!malloc` at `0x140001f24`
- `msvcrt!malloc` at `0x140001f24`
- `msvcrt!memcpy_s` at `0x140001f80`
- `msvcrt!memcpy_s` at `0x140001f80`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140001f6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140001f6b`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessAce::GetACE(ATL::CDacl::CAccessAce *this)
{
  char *v1; // rbx
  size_t v4; // rdi
  char *v5; // rax
  __int64 v6; // rax
  DWORD LengthSid; // eax
  errno_t v8; // eax

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v4 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessAce *))(*(_QWORD *)this + 16LL))(this);
    v5 = (char *)malloc(v4);
    v1 = v5;
    if ( !v5 )
      ATL::PrivateAtlThrow(-2147024882);
    memset_0(v5, 0, (unsigned int)v4);
    v1[1] = *((_BYTE *)this + 132);
    v6 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v4;
    *v1 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessAce *))(v6 + 24))(this);
    *((_DWORD *)v1 + 1) = *((_DWORD *)this + 32);
    LengthSid = GetLengthSid((char *)this + 16);
    v8 = memcpy_s(v1 + 8, v4 - 8, (char *)this + 16, LengthSid);
    ATL::AtlCrtErrorCheck(v8);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x140001ef0  push    rbx
0x140001ef2  push    rbp
0x140001ef3  push    rsi
0x140001ef4  push    rdi
0x140001ef5  sub     rsp, 28h
0x140001ef9  mov     rbx, [rcx+88h]
0x140001f00  mov     rsi, rcx
0x140001f03  test    rbx, rbx
0x140001f06  jz      short loc_140001F14
0x140001f08  mov     rax, rbx
0x140001f0b  add     rsp, 28h
0x140001f0f  pop     rdi
0x140001f10  pop     rsi
0x140001f11  pop     rbp
0x140001f12  pop     rbx
0x140001f13  retn
0x140001f14  mov     rax, [rcx]
0x140001f17  mov     rax, [rax+10h]
0x140001f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f20  mov     ecx, eax; Size
0x140001f22  mov     edi, eax
0x140001f24  call    cs:__imp_malloc
0x140001f2a  mov     rbx, rax
0x140001f2d  test    rax, rax
0x140001f30  jz      short loc_140001F99
0x140001f32  mov     r8d, edi; Size
0x140001f35  xor     edx, edx; Val
0x140001f37  mov     rcx, rax; void *
0x140001f3a  call    memset_0
0x140001f3f  movzx   eax, byte ptr [rsi+84h]
0x140001f46  mov     rcx, rsi
0x140001f49  mov     [rbx+1], al
0x140001f4c  mov     rax, [rsi]
0x140001f4f  mov     [rbx+2], di
0x140001f53  mov     rax, [rax+18h]
0x140001f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f5c  mov     [rbx], al
0x140001f5e  lea     rcx, [rsi+10h]; pSid
0x140001f62  mov     eax, [rsi+80h]
0x140001f68  mov     [rbx+4], eax
0x140001f6b  call    cs:__imp_GetLengthSid
0x140001f71  mov     r9d, eax; SourceSize
0x140001f74  lea     rdx, [rdi-8]; DestinationSize
0x140001f78  lea     rcx, [rbx+8]; Destination
0x140001f7c  lea     r8, [rsi+10h]; Source
0x140001f80  call    cs:__imp_memcpy_s
0x140001f86  mov     ecx, eax; int
0x140001f88  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140001f8d  mov     [rsi+88h], rbx
0x140001f94  jmp     loc_140001F08
0x140001f99  mov     ecx, 8007000Eh; int
0x140001f9e  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
