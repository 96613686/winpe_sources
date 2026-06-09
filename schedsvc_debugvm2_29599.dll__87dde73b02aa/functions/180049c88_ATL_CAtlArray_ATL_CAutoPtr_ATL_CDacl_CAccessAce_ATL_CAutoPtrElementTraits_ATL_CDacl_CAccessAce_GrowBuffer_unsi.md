# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)

- ea: `0x180049c88`
- end: `0x180049d50`
- name: `?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18006b0e4`

## callees

- `0x18001fc54`
- `0x180049c88`

## import_xrefs

- `msvcrt!memmove_s` at `0x180049d21`
- `msvcrt!memmove_s` at `0x180049d21`
- `msvcrt!calloc` at `0x180049cc3`
- `msvcrt!calloc` at `0x180049cfe`
- `msvcrt!calloc` at `0x180049cc3`
- `msvcrt!calloc` at `0x180049cfe`
- `msvcrt!free` at `0x180049d31`
- `msvcrt!free` at `0x180049d31`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  unsigned __int64 v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 > v4 )
  {
    v5 = *(int *)(a1 + 24);
    if ( *(_QWORD *)a1 )
    {
      if ( !v5 )
      {
        v5 = v4 >> 1;
        if ( a2 - v4 > v4 >> 1 )
          v5 = a2 - v4;
      }
      if ( a2 < v4 + v5 )
        a2 = v4 + v5;
      v7 = calloc(a2, 8u);
      v8 = v7;
      if ( !v7 )
        return 0;
      v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
      ATL::AtlCrtErrorCheck(v10);
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
    }
    else
    {
      if ( v5 > a2 )
        a2 = v5;
      v6 = calloc(a2, 8u);
      *(_QWORD *)a1 = v6;
      if ( !v6 )
        return 0;
    }
    *(_QWORD *)(a1 + 16) = a2;
  }
  return 1;
}

```

## disassembly

```asm
0x180049c88  mov     [rsp+arg_0], rbx
0x180049c8d  mov     [rsp+arg_8], rsi
0x180049c92  push    rdi
0x180049c93  sub     rsp, 20h
0x180049c97  mov     rbx, rdx
0x180049c9a  mov     rdi, rcx
0x180049c9d  mov     rdx, [rcx+10h]
0x180049ca1  cmp     rbx, rdx
0x180049ca4  jbe     loc_180049D3E
0x180049caa  cmp     qword ptr [rdi], 0
0x180049cae  movsxd  rcx, dword ptr [rcx+18h]
0x180049cb2  jnz     short loc_180049CD3
0x180049cb4  cmp     rcx, rbx
0x180049cb7  mov     edx, 8; Size
0x180049cbc  cmova   rbx, rcx
0x180049cc0  mov     rcx, rbx; Count
0x180049cc3  call    cs:__imp_calloc
0x180049cc9  mov     [rdi], rax
0x180049ccc  test    rax, rax
0x180049ccf  jnz     short loc_180049D3A
0x180049cd1  jmp     short loc_180049D0C
0x180049cd3  test    rcx, rcx
0x180049cd6  jnz     short loc_180049CEB
0x180049cd8  mov     rcx, rdx
0x180049cdb  mov     rax, rbx
0x180049cde  shr     rcx, 1
0x180049ce1  sub     rax, rdx
0x180049ce4  cmp     rax, rcx
0x180049ce7  cmova   rcx, rax
0x180049ceb  lea     rax, [rdx+rcx]
0x180049cef  mov     edx, 8; Size
0x180049cf4  cmp     rbx, rax
0x180049cf7  cmovb   rbx, rax
0x180049cfb  mov     rcx, rbx; Count
0x180049cfe  call    cs:__imp_calloc
0x180049d04  mov     rsi, rax
0x180049d07  test    rax, rax
0x180049d0a  jnz     short loc_180049D10
0x180049d0c  xor     al, al
0x180049d0e  jmp     short loc_180049D40
0x180049d10  mov     rdx, [rdi+8]
0x180049d14  mov     rcx, rsi; Destination
0x180049d17  mov     r8, [rdi]; Source
0x180049d1a  shl     rdx, 3; DestinationSize
0x180049d1e  mov     r9, rdx; SourceSize
0x180049d21  call    cs:__imp_memmove_s
0x180049d27  mov     ecx, eax; int
0x180049d29  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180049d2e  mov     rcx, [rdi]; Block
0x180049d31  call    cs:__imp_free
0x180049d37  mov     [rdi], rsi
0x180049d3a  mov     [rdi+10h], rbx
0x180049d3e  mov     al, 1
0x180049d40  mov     rbx, [rsp+28h+arg_0]
0x180049d45  mov     rsi, [rsp+28h+arg_8]
0x180049d4a  add     rsp, 20h
0x180049d4e  pop     rdi
0x180049d4f  retn
```
