# ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::GrowBuffer(unsigned __int64)

- ea: `0x1800d2d68`
- end: `0x1800d2e34`
- name: `?GrowBuffer@?$CAtlArray@UPACKDATA_OBJECTINFO@ILangDataPack@@V?$CElementTraits@UPACKDATA_OBJECTINFO@ILangDataPack@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d2bdc`

## callees

- `0x180016efc`
- `0x1800d2d68`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800d2e05`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800d2e05`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d2da3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d2dde`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d2da3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d2dde`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d2e15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d2e15`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rsi
  errno_t v9; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 0x30u);
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
  v7 = calloc(a2, 0x30u);
  if ( !v7 )
    return 0;
  v9 = memmove_s(v7, 48LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 48LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v9);
  free(*(void **)a1);
  *(_QWORD *)a1 = v7;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x1800d2d68  mov     [rsp+arg_0], rbx
0x1800d2d6d  mov     [rsp+arg_8], rsi
0x1800d2d72  push    rdi
0x1800d2d73  sub     rsp, 20h
0x1800d2d77  mov     rdi, rdx
0x1800d2d7a  mov     rbx, rcx
0x1800d2d7d  mov     rdx, [rcx+10h]
0x1800d2d81  cmp     rdi, rdx
0x1800d2d84  jbe     loc_1800D2E22
0x1800d2d8a  cmp     qword ptr [rbx], 0
0x1800d2d8e  movsxd  rcx, dword ptr [rcx+18h]
0x1800d2d92  jnz     short loc_1800D2DB3
0x1800d2d94  cmp     rcx, rdi
0x1800d2d97  mov     edx, 30h ; '0'; Size
0x1800d2d9c  cmova   rdi, rcx
0x1800d2da0  mov     rcx, rdi; Count
0x1800d2da3  call    cs:__imp_calloc
0x1800d2da9  mov     [rbx], rax
0x1800d2dac  test    rax, rax
0x1800d2daf  jz      short loc_1800D2DEC
0x1800d2db1  jmp     short loc_1800D2E1E
0x1800d2db3  test    rcx, rcx
0x1800d2db6  jnz     short loc_1800D2DCB
0x1800d2db8  mov     rcx, rdx
0x1800d2dbb  mov     rax, rdi
0x1800d2dbe  shr     rcx, 1
0x1800d2dc1  sub     rax, rdx
0x1800d2dc4  cmp     rax, rcx
0x1800d2dc7  cmova   rcx, rax
0x1800d2dcb  lea     rax, [rdx+rcx]
0x1800d2dcf  mov     edx, 30h ; '0'; Size
0x1800d2dd4  cmp     rdi, rax
0x1800d2dd7  cmovb   rdi, rax
0x1800d2ddb  mov     rcx, rdi; Count
0x1800d2dde  call    cs:__imp_calloc
0x1800d2de4  mov     rsi, rax
0x1800d2de7  test    rax, rax
0x1800d2dea  jnz     short loc_1800D2DF0
0x1800d2dec  xor     al, al
0x1800d2dee  jmp     short loc_1800D2E24
0x1800d2df0  mov     rax, [rbx+8]
0x1800d2df4  mov     rcx, rsi; Destination
0x1800d2df7  mov     r8, [rbx]; Source
0x1800d2dfa  lea     rdx, [rax+rax*2]
0x1800d2dfe  shl     rdx, 4; DestinationSize
0x1800d2e02  mov     r9, rdx; SourceSize
0x1800d2e05  call    cs:__imp_memmove_s
0x1800d2e0b  mov     ecx, eax; int
0x1800d2e0d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800d2e12  mov     rcx, [rbx]; Block
0x1800d2e15  call    cs:__imp_free
0x1800d2e1b  mov     [rbx], rsi
0x1800d2e1e  mov     [rbx+10h], rdi
0x1800d2e22  mov     al, 1
0x1800d2e24  mov     rbx, [rsp+28h+arg_0]
0x1800d2e29  mov     rsi, [rsp+28h+arg_8]
0x1800d2e2e  add     rsp, 20h
0x1800d2e32  pop     rdi
0x1800d2e33  retn
```
