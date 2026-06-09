# ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GrowBuffer(unsigned __int64)

- ea: `0x18002ae2c`
- end: `0x18002aef4`
- name: `?GrowBuffer@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c3ac`

## callees

- `0x180004c00`
- `0x18002ae2c`

## import_xrefs

- `msvcrt!calloc` at `0x18002ae67`
- `msvcrt!calloc` at `0x18002aea2`
- `msvcrt!calloc` at `0x18002ae67`
- `msvcrt!calloc` at `0x18002aea2`
- `msvcrt!memmove_s` at `0x18002aec5`
- `msvcrt!memmove_s` at `0x18002aec5`
- `msvcrt!free` at `0x18002aed5`
- `msvcrt!free` at `0x18002aed5`

## pseudocode

```c
char __fastcall ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GrowBuffer(__int64 a1, size_t a2)
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
    v6 = calloc(a2, 0x20u);
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
  v7 = calloc(a2, 0x20u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 32LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 32LL * *(_QWORD *)(a1 + 8));
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
0x18002ae2c  mov     [rsp+arg_0], rbx
0x18002ae31  mov     [rsp+arg_8], rsi
0x18002ae36  push    rdi
0x18002ae37  sub     rsp, 20h
0x18002ae3b  mov     rbx, rdx
0x18002ae3e  mov     rdi, rcx
0x18002ae41  mov     rdx, [rcx+10h]
0x18002ae45  cmp     rbx, rdx
0x18002ae48  jbe     loc_18002AEE2
0x18002ae4e  cmp     qword ptr [rdi], 0
0x18002ae52  movsxd  rcx, dword ptr [rcx+18h]
0x18002ae56  jnz     short loc_18002AE77
0x18002ae58  cmp     rcx, rbx
0x18002ae5b  mov     edx, 20h ; ' '; Size
0x18002ae60  cmova   rbx, rcx
0x18002ae64  mov     rcx, rbx; Count
0x18002ae67  call    cs:__imp_calloc
0x18002ae6d  mov     [rdi], rax
0x18002ae70  test    rax, rax
0x18002ae73  jz      short loc_18002AEB0
0x18002ae75  jmp     short loc_18002AEDE
0x18002ae77  test    rcx, rcx
0x18002ae7a  jnz     short loc_18002AE8F
0x18002ae7c  mov     rcx, rdx
0x18002ae7f  mov     rax, rbx
0x18002ae82  shr     rcx, 1
0x18002ae85  sub     rax, rdx
0x18002ae88  cmp     rax, rcx
0x18002ae8b  cmova   rcx, rax
0x18002ae8f  lea     rax, [rdx+rcx]
0x18002ae93  mov     edx, 20h ; ' '; Size
0x18002ae98  cmp     rbx, rax
0x18002ae9b  cmovb   rbx, rax
0x18002ae9f  mov     rcx, rbx; Count
0x18002aea2  call    cs:__imp_calloc
0x18002aea8  mov     rsi, rax
0x18002aeab  test    rax, rax
0x18002aeae  jnz     short loc_18002AEB4
0x18002aeb0  xor     al, al
0x18002aeb2  jmp     short loc_18002AEE4
0x18002aeb4  mov     rdx, [rdi+8]
0x18002aeb8  mov     rcx, rsi; Destination
0x18002aebb  mov     r8, [rdi]; Source
0x18002aebe  shl     rdx, 5; DestinationSize
0x18002aec2  mov     r9, rdx; SourceSize
0x18002aec5  call    cs:__imp_memmove_s
0x18002aecb  mov     ecx, eax; int
0x18002aecd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002aed2  mov     rcx, [rdi]; Block
0x18002aed5  call    cs:__imp_free
0x18002aedb  mov     [rdi], rsi
0x18002aede  mov     [rdi+10h], rbx
0x18002aee2  mov     al, 1
0x18002aee4  mov     rbx, [rsp+28h+arg_0]
0x18002aee9  mov     rsi, [rsp+28h+arg_8]
0x18002aeee  add     rsp, 20h
0x18002aef2  pop     rdi
0x18002aef3  retn
```
