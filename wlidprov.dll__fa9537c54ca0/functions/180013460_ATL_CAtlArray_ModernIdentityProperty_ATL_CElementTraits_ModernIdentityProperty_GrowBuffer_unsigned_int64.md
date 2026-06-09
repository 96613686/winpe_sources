# ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::GrowBuffer(unsigned __int64)

- ea: `0x180013460`
- end: `0x180013528`
- name: `?GrowBuffer@?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003e99c`

## callees

- `0x180013460`
- `0x180015788`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800134f9`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800134f9`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001349b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800134d6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001349b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800134d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013509`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013509`

## pseudocode

```c
char __fastcall ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::GrowBuffer(
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
    v6 = calloc(a2, 0x10u);
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
  v7 = calloc(a2, 0x10u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 16LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 16LL * *(_QWORD *)(a1 + 8));
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
0x180013460  mov     [rsp+arg_0], rbx
0x180013465  mov     [rsp+arg_8], rsi
0x18001346a  push    rdi
0x18001346b  sub     rsp, 20h
0x18001346f  mov     rdi, rdx
0x180013472  mov     rbx, rcx
0x180013475  mov     rdx, [rcx+10h]
0x180013479  cmp     rdi, rdx
0x18001347c  jbe     loc_180013516
0x180013482  cmp     qword ptr [rbx], 0
0x180013486  movsxd  rcx, dword ptr [rcx+18h]
0x18001348a  jnz     short loc_1800134AB
0x18001348c  cmp     rcx, rdi
0x18001348f  mov     edx, 10h; Size
0x180013494  cmova   rdi, rcx
0x180013498  mov     rcx, rdi; Count
0x18001349b  call    cs:__imp_calloc
0x1800134a1  mov     [rbx], rax
0x1800134a4  test    rax, rax
0x1800134a7  jz      short loc_1800134E4
0x1800134a9  jmp     short loc_180013512
0x1800134ab  test    rcx, rcx
0x1800134ae  jnz     short loc_1800134C3
0x1800134b0  mov     rcx, rdx
0x1800134b3  mov     rax, rdi
0x1800134b6  shr     rcx, 1
0x1800134b9  sub     rax, rdx
0x1800134bc  cmp     rax, rcx
0x1800134bf  cmova   rcx, rax
0x1800134c3  lea     rax, [rdx+rcx]
0x1800134c7  mov     edx, 10h; Size
0x1800134cc  cmp     rdi, rax
0x1800134cf  cmovb   rdi, rax
0x1800134d3  mov     rcx, rdi; Count
0x1800134d6  call    cs:__imp_calloc
0x1800134dc  mov     rsi, rax
0x1800134df  test    rax, rax
0x1800134e2  jnz     short loc_1800134E8
0x1800134e4  xor     al, al
0x1800134e6  jmp     short loc_180013518
0x1800134e8  mov     rdx, [rbx+8]
0x1800134ec  mov     rcx, rsi; Destination
0x1800134ef  mov     r8, [rbx]; Source
0x1800134f2  shl     rdx, 4; DestinationSize
0x1800134f6  mov     r9, rdx; SourceSize
0x1800134f9  call    cs:__imp_memmove_s
0x1800134ff  mov     ecx, eax; int
0x180013501  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180013506  mov     rcx, [rbx]; Block
0x180013509  call    cs:__imp_free
0x18001350f  mov     [rbx], rsi
0x180013512  mov     [rbx+10h], rdi
0x180013516  mov     al, 1
0x180013518  mov     rbx, [rsp+28h+arg_0]
0x18001351d  mov     rsi, [rsp+28h+arg_8]
0x180013522  add     rsp, 20h
0x180013526  pop     rdi
0x180013527  retn
```
