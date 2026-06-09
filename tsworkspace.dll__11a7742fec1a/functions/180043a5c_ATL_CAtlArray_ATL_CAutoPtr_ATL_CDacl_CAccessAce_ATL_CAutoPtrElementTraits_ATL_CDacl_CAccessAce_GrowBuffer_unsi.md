# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)

- ea: `0x180043a5c`
- end: `0x180043b24`
- name: `?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800422d4`

## callees

- `0x180006cc8`
- `0x180043a5c`

## import_xrefs

- `msvcrt!calloc` at `0x180043a97`
- `msvcrt!calloc` at `0x180043ad2`
- `msvcrt!calloc` at `0x180043a97`
- `msvcrt!calloc` at `0x180043ad2`
- `msvcrt!memmove_s` at `0x180043af5`
- `msvcrt!memmove_s` at `0x180043af5`
- `msvcrt!free` at `0x180043b05`
- `msvcrt!free` at `0x180043b05`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 8u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
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
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180043a5c  mov     [rsp+arg_0], rbx
0x180043a61  mov     [rsp+arg_8], rsi
0x180043a66  push    rdi
0x180043a67  sub     rsp, 20h
0x180043a6b  mov     rbx, rdx
0x180043a6e  mov     rdi, rcx
0x180043a71  mov     rdx, [rcx+10h]
0x180043a75  cmp     rbx, rdx
0x180043a78  jbe     loc_180043B12
0x180043a7e  cmp     qword ptr [rdi], 0
0x180043a82  movsxd  rcx, dword ptr [rcx+18h]
0x180043a86  jnz     short loc_180043AA7
0x180043a88  cmp     rcx, rbx
0x180043a8b  mov     edx, 8; Size
0x180043a90  cmova   rbx, rcx
0x180043a94  mov     rcx, rbx; Count
0x180043a97  call    cs:__imp_calloc
0x180043a9d  mov     [rdi], rax
0x180043aa0  test    rax, rax
0x180043aa3  jz      short loc_180043AE0
0x180043aa5  jmp     short loc_180043B0E
0x180043aa7  test    rcx, rcx
0x180043aaa  jnz     short loc_180043ABF
0x180043aac  mov     rcx, rdx
0x180043aaf  mov     rax, rbx
0x180043ab2  shr     rcx, 1
0x180043ab5  sub     rax, rdx
0x180043ab8  cmp     rax, rcx
0x180043abb  cmova   rcx, rax
0x180043abf  lea     rax, [rdx+rcx]
0x180043ac3  mov     edx, 8; Size
0x180043ac8  cmp     rbx, rax
0x180043acb  cmovb   rbx, rax
0x180043acf  mov     rcx, rbx; Count
0x180043ad2  call    cs:__imp_calloc
0x180043ad8  mov     rsi, rax
0x180043adb  test    rax, rax
0x180043ade  jnz     short loc_180043AE4
0x180043ae0  xor     al, al
0x180043ae2  jmp     short loc_180043B14
0x180043ae4  mov     rdx, [rdi+8]
0x180043ae8  mov     rcx, rsi; Destination
0x180043aeb  mov     r8, [rdi]; Source
0x180043aee  shl     rdx, 3; DestinationSize
0x180043af2  mov     r9, rdx; SourceSize
0x180043af5  call    cs:__imp_memmove_s
0x180043afb  mov     ecx, eax; int
0x180043afd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180043b02  mov     rcx, [rdi]; Block
0x180043b05  call    cs:__imp_free
0x180043b0b  mov     [rdi], rsi
0x180043b0e  mov     [rdi+10h], rbx
0x180043b12  mov     al, 1
0x180043b14  mov     rbx, [rsp+28h+arg_0]
0x180043b19  mov     rsi, [rsp+28h+arg_8]
0x180043b1e  add     rsp, 20h
0x180043b22  pop     rdi
0x180043b23  retn
```
