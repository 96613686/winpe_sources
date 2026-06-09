# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)

- ea: `0x140003060`
- end: `0x140003124`
- name: `?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `196`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140002b40`

## callees

- `0x140003060`
- `0x140003130`

## import_xrefs

- `msvcrt!free` at `0x1400030f7`
- `msvcrt!free` at `0x1400030f7`
- `msvcrt!memmove_s` at `0x1400030e7`
- `msvcrt!memmove_s` at `0x1400030e7`
- `msvcrt!calloc` at `0x140003097`
- `msvcrt!calloc` at `0x1400030c8`
- `msvcrt!calloc` at `0x140003097`
- `msvcrt!calloc` at `0x1400030c8`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v3; // rdi
  unsigned __int64 v4; // rcx
  const void *v5; // rsi
  size_t v6; // rdx
  void *v7; // rax
  void *v9; // rax
  void *v10; // rbp
  errno_t v11; // eax

  v3 = a2;
  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 > v4 )
  {
    v5 = *(const void **)a1;
    v6 = *(int *)(a1 + 24);
    if ( *(_QWORD *)a1 )
    {
      if ( !*(_DWORD *)(a1 + 24) )
      {
        v6 = v4 >> 1;
        if ( v3 - v4 > v4 >> 1 )
          v6 = v3 - v4;
      }
      if ( v3 < v4 + v6 )
        v3 = v4 + v6;
      v9 = calloc(v3, 8u);
      v10 = v9;
      if ( !v9 )
        return 0;
      v11 = memmove_s(v9, 8LL * *(_QWORD *)(a1 + 8), v5, 8LL * *(_QWORD *)(a1 + 8));
      ATL::AtlCrtErrorCheck(v11);
      free(*(void **)a1);
      *(_QWORD *)a1 = v10;
    }
    else
    {
      if ( v6 > v3 )
        v3 = *(int *)(a1 + 24);
      v7 = calloc(v3, 8u);
      *(_QWORD *)a1 = v7;
      if ( !v7 )
        return 0;
    }
    *(_QWORD *)(a1 + 16) = v3;
  }
  return 1;
}

```

## disassembly

```asm
0x140003060  push    rbx
0x140003062  push    rbp
0x140003063  push    rsi
0x140003064  push    rdi
0x140003065  sub     rsp, 28h
0x140003069  mov     rbx, rcx
0x14000306c  mov     rdi, rdx
0x14000306f  mov     rcx, [rcx+10h]
0x140003073  cmp     rdx, rcx
0x140003076  jbe     loc_140003104
0x14000307c  mov     rsi, [rbx]
0x14000307f  movsxd  rdx, dword ptr [rbx+18h]
0x140003083  test    rsi, rsi
0x140003086  jnz     short loc_1400030B0
0x140003088  cmp     rdx, rdi
0x14000308b  cmova   rdi, rdx
0x14000308f  mov     edx, 8; Size
0x140003094  mov     rcx, rdi; Count
0x140003097  call    cs:__imp_calloc
0x14000309d  mov     [rbx], rax
0x1400030a0  test    rax, rax
0x1400030a3  jnz     short loc_140003100
0x1400030a5  xor     al, al
0x1400030a7  add     rsp, 28h
0x1400030ab  pop     rdi
0x1400030ac  pop     rsi
0x1400030ad  pop     rbp
0x1400030ae  pop     rbx
0x1400030af  retn
0x1400030b0  test    rdx, rdx
0x1400030b3  jz      short loc_14000310F
0x1400030b5  lea     rax, [rcx+rdx]
0x1400030b9  mov     edx, 8; Size
0x1400030be  cmp     rdi, rax
0x1400030c1  cmovb   rdi, rax
0x1400030c5  mov     rcx, rdi; Count
0x1400030c8  call    cs:__imp_calloc
0x1400030ce  mov     rbp, rax
0x1400030d1  test    rax, rax
0x1400030d4  jz      short loc_1400030A5
0x1400030d6  mov     rdx, [rbx+8]
0x1400030da  mov     r8, rsi; Source
0x1400030dd  shl     rdx, 3; DestinationSize
0x1400030e1  mov     rcx, rax; Destination
0x1400030e4  mov     r9, rdx; SourceSize
0x1400030e7  call    cs:__imp_memmove_s
0x1400030ed  mov     ecx, eax; int
0x1400030ef  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400030f4  mov     rcx, [rbx]; Block
0x1400030f7  call    cs:__imp_free
0x1400030fd  mov     [rbx], rbp
0x140003100  mov     [rbx+10h], rdi
0x140003104  mov     al, 1
0x140003106  add     rsp, 28h
0x14000310a  pop     rdi
0x14000310b  pop     rsi
0x14000310c  pop     rbp
0x14000310d  pop     rbx
0x14000310e  retn
0x14000310f  mov     rdx, rcx
0x140003112  mov     rax, rdi
0x140003115  shr     rdx, 1
0x140003118  sub     rax, rcx
0x14000311b  cmp     rax, rdx
0x14000311e  cmova   rdx, rax
0x140003122  jmp     short loc_1400030B5
```
