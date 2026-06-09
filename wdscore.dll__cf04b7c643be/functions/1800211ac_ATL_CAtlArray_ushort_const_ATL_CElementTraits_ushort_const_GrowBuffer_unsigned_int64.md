# ATL::CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>::GrowBuffer(unsigned __int64)

- ea: `0x1800211ac`
- end: `0x18002128d`
- name: `?GrowBuffer@?$CAtlArray@PEBGV?$CElementTraits@PEBG@ATL@@@ATL@@AEAA_N_K@Z`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002209c`

## callees

- `0x180020e24`
- `0x1800211ac`

## import_xrefs

- `msvcrt!memmove_s` at `0x180021251`
- `msvcrt!memmove_s` at `0x180021251`
- `msvcrt!free` at `0x180021267`
- `msvcrt!free` at `0x180021267`
- `msvcrt!calloc` at `0x1800211e7`
- `msvcrt!calloc` at `0x180021228`
- `msvcrt!calloc` at `0x1800211e7`
- `msvcrt!calloc` at `0x180021228`

## pseudocode

```c
char __fastcall ATL::CAtlArray<unsigned short const *,ATL::CElementTraits<unsigned short const *>>::GrowBuffer(
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
0x1800211ac  mov     [rsp+arg_0], rbx
0x1800211b1  mov     [rsp+arg_8], rsi
0x1800211b6  push    rdi
0x1800211b7  sub     rsp, 20h
0x1800211bb  mov     rbx, rdx
0x1800211be  mov     rdi, rcx
0x1800211c1  mov     rdx, [rcx+10h]
0x1800211c5  cmp     rbx, rdx
0x1800211c8  jbe     loc_18002127A
0x1800211ce  cmp     qword ptr [rdi], 0
0x1800211d2  movsxd  rcx, dword ptr [rcx+18h]
0x1800211d6  jnz     short loc_1800211FD
0x1800211d8  cmp     rcx, rbx
0x1800211db  mov     edx, 8; Size
0x1800211e0  cmova   rbx, rcx
0x1800211e4  mov     rcx, rbx; Count
0x1800211e7  call    cs:__imp_calloc
0x1800211ee  nop     dword ptr [rax+rax+00h]
0x1800211f3  mov     [rdi], rax
0x1800211f6  test    rax, rax
0x1800211f9  jz      short loc_18002123C
0x1800211fb  jmp     short loc_180021276
0x1800211fd  test    rcx, rcx
0x180021200  jnz     short loc_180021215
0x180021202  mov     rcx, rdx
0x180021205  mov     rax, rbx
0x180021208  shr     rcx, 1
0x18002120b  sub     rax, rdx
0x18002120e  cmp     rax, rcx
0x180021211  cmova   rcx, rax
0x180021215  lea     rax, [rdx+rcx]
0x180021219  mov     edx, 8; Size
0x18002121e  cmp     rbx, rax
0x180021221  cmovb   rbx, rax
0x180021225  mov     rcx, rbx; Count
0x180021228  call    cs:__imp_calloc
0x18002122f  nop     dword ptr [rax+rax+00h]
0x180021234  mov     rsi, rax
0x180021237  test    rax, rax
0x18002123a  jnz     short loc_180021240
0x18002123c  xor     al, al
0x18002123e  jmp     short loc_18002127C
0x180021240  mov     rdx, [rdi+8]
0x180021244  mov     rcx, rsi; Destination
0x180021247  mov     r8, [rdi]; Source
0x18002124a  shl     rdx, 3; DestinationSize
0x18002124e  mov     r9, rdx; SourceSize
0x180021251  call    cs:__imp_memmove_s
0x180021258  nop     dword ptr [rax+rax+00h]
0x18002125d  mov     ecx, eax; int
0x18002125f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180021264  mov     rcx, [rdi]; Block
0x180021267  call    cs:__imp_free
0x18002126e  nop     dword ptr [rax+rax+00h]
0x180021273  mov     [rdi], rsi
0x180021276  mov     [rdi+10h], rbx
0x18002127a  mov     al, 1
0x18002127c  mov     rbx, [rsp+28h+arg_0]
0x180021281  mov     rsi, [rsp+28h+arg_8]
0x180021286  add     rsp, 20h
0x18002128a  pop     rdi
0x18002128b  retn
```
