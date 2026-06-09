# ComputeService::ContainerUtilities::ValidateNewMappedVirtualDisk(std::vector<Config::Containers::MappedDirectory,std::allocator<Config::Containers::MappedDirectory>> const &,std::vector<Config::Containers::MappedVirtualDisk,std::allocator<Config::Containers::MappedVirtualDisk>> const &,Config::Containers::MappedVirtualDisk const &,bool)

- ea: `0x1400b4344`
- end: `0x1400b45ed`
- name: `?ValidateNewMappedVirtualDisk@ContainerUtilities@ComputeService@@YAXAEBV?$vector@UMappedDirectory@Containers@Config@@V?$allocator@UMappedDirectory@Containers@Config@@@std@@@std@@AEBV?$vector@UMappedVirtualDisk@Containers@Config@@V?$allocator@UMappedVirtualDisk@Containers@Config@@@std@@@4@AEBUMappedVirtualDisk@Containers@Config@@_N@Z`
- size: `681`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14009aa60`
- `0x1400b4084`
- `0x1400c084c`

## callees

- `0x1400b4344`
- `0x1400c40e0`
- `0x1400d4928`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b44c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b4512`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b44c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b4512`

## string_xrefs

- `0x1400b436b`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b438c`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b43b0`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b43d4`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b43f8`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b4428`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b4450`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b447e`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b4549`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b4561`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400b45db`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`

## pseudocode

```c
void __fastcall ComputeService::ContainerUtilities::ValidateNewMappedVirtualDisk(
        __int64 *a1,
        __int64 **a2,
        __int64 *a3,
        char a4)
{
  unsigned __int8 v6; // al
  char v7; // si
  _QWORD *v8; // r15
  __int64 *v9; // rdi
  __int64 *v10; // r14
  _QWORD *v11; // rdx
  _QWORD *v12; // rcx
  __int64 *v14; // rdx
  __int64 *v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rsi
  _QWORD *v18; // rcx
  __int64 *v19; // r8
  int v21; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a4 )
  {
    v6 = *((_BYTE *)a3 + 64);
    if ( v6 < 2u )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30B,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( v6 > 0x3Fu )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30E,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)0x80070057LL,
        v21);
  }
  else
  {
    if ( *((_BYTE *)a3 + 65) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x314,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)0x80070032LL,
        v21);
    if ( *((_BYTE *)a3 + 67) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x318,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)0x80070032LL,
        v21);
  }
  if ( *((_DWORD *)a3 + 18) > 2u )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)0x80070057LL,
      v21);
  v7 = *((_BYTE *)a3 + 67);
  v8 = a3 + 6;
  if ( v7 )
  {
    if ( *v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x328,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)0x80070057LL,
        v21);
  }
  else if ( !*v8 )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x326,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)0x80070057LL,
      v21);
  }
  if ( a4 && v7 && !*((_BYTE *)a3 + 65) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)0x80070057LL,
      v21);
  v9 = *a2;
  v10 = a2[1];
  while ( v9 != v10 )
  {
    if ( v9 != a3 )
    {
      if ( !v7 )
      {
        v11 = a3 + 4;
        if ( (unsigned __int64)a3[7] > 7 )
          v11 = (_QWORD *)*v11;
        v12 = v9 + 4;
        if ( (unsigned __int64)v9[7] > 7 )
          v12 = (_QWORD *)*v12;
        if ( !(unsigned int)_o__wcsicmp(v12, v11) && *((_BYTE *)v9 + 65) == *((_BYTE *)a3 + 65) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x33D,
            (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
            (const char *)0x80070057LL,
            v21);
      }
      if ( (unsigned __int64)a3[3] <= 7 )
        v14 = a3;
      else
        v14 = (__int64 *)*a3;
      if ( (unsigned __int64)v9[3] <= 7 )
        v15 = v9;
      else
        v15 = (__int64 *)*v9;
      if ( !(unsigned int)_o__wcsicmp(v15, v14) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x341,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
          (const char *)0x80070057LL,
          v21);
    }
    v9 += 10;
  }
  if ( !v7 )
  {
    v16 = *a1;
    v17 = a1[1];
    while ( v16 != v17 )
    {
      v18 = (_QWORD *)(v16 + 32);
      if ( (unsigned __int64)a3[7] <= 7 )
        v19 = a3 + 4;
      else
        v19 = (__int64 *)a3[4];
      if ( *(_QWORD *)(v16 + 56) > 7u )
        v18 = (_QWORD *)*v18;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v18, *(_QWORD *)(v16 + 48), v19, *v8)
        && *(_BYTE *)(v16 + 69) == *((_BYTE *)a3 + 65) )
      {
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34A,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
          (const char *)0x80070057LL,
          v21);
      }
      v16 += 112;
    }
  }
}

```

## disassembly

```asm
0x1400b4344  push    rbx
0x1400b4346  push    rbp
0x1400b4347  push    rsi
0x1400b4348  push    rdi
0x1400b4349  push    r12
0x1400b434b  push    r14
0x1400b434d  push    r15; int
0x1400b434f  sub     rsp, 20h
0x1400b4353  mov     rbx, r8
0x1400b4356  mov     r12, rcx
0x1400b4359  test    r9b, r9b
0x1400b435c  jz      short loc_1400B43A4
0x1400b435e  mov     al, [r8+40h]
0x1400b4362  cmp     al, 2
0x1400b4364  jnb     short loc_1400B4383
0x1400b4366  mov     rcx, [rsp+58h]; this
0x1400b436b  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b4372  mov     r9d, 80070057h; char *
0x1400b4378  mov     edx, 30Bh; void *
0x1400b437d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b4383  cmp     al, 3Fh ; '?'
0x1400b4385  jbe     short loc_1400B43EC
0x1400b4387  mov     rcx, [rsp+58h]; this
0x1400b438c  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b4393  mov     r9d, 80070057h; char *
0x1400b4399  mov     edx, 30Eh; void *
0x1400b439e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b43a4  cmp     byte ptr [r8+41h], 0
0x1400b43a9  jz      short loc_1400B43C8
0x1400b43ab  mov     rcx, [rsp+58h]; this
0x1400b43b0  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b43b7  mov     r9d, 80070032h; char *
0x1400b43bd  mov     edx, 314h; void *
0x1400b43c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b43c8  cmp     byte ptr [r8+43h], 0
0x1400b43cd  jz      short loc_1400B43EC
0x1400b43cf  mov     rcx, [rsp+58h]; this
0x1400b43d4  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b43db  mov     r9d, 80070032h; char *
0x1400b43e1  mov     edx, 318h; void *
0x1400b43e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b43ec  cmp     dword ptr [r8+48h], 2
0x1400b43f1  jbe     short loc_1400B4410
0x1400b43f3  mov     rcx, [rsp+58h]; this
0x1400b43f8  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b43ff  mov     r9d, 80070057h; char *
0x1400b4405  mov     edx, 31Fh; void *
0x1400b440a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b4410  mov     sil, [r8+43h]
0x1400b4414  lea     r15, [r8+30h]
0x1400b4418  test    sil, sil
0x1400b441b  jnz     short loc_1400B4445
0x1400b441d  cmp     qword ptr [r15], 0
0x1400b4421  jnz     short loc_1400B4440
0x1400b4423  mov     rcx, [rsp+58h]; this
0x1400b4428  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b442f  mov     r9d, 80070057h; char *
0x1400b4435  mov     edx, 326h; void *
0x1400b443a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b4440  test    sil, sil
0x1400b4443  jz      short loc_1400B4468
0x1400b4445  cmp     qword ptr [r15], 0
0x1400b4449  jz      short loc_1400B4468
0x1400b444b  mov     rcx, [rsp+58h]; this
0x1400b4450  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b4457  mov     r9d, 80070057h; char *
0x1400b445d  mov     edx, 328h; void *
0x1400b4462  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b4468  test    r9b, r9b
0x1400b446b  jz      short loc_1400B4496
0x1400b446d  test    sil, sil
0x1400b4470  jz      short loc_1400B4496
0x1400b4472  cmp     byte ptr [r8+41h], 0
0x1400b4477  jnz     short loc_1400B4496
0x1400b4479  mov     rcx, [rsp+58h]; this
0x1400b447e  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b4485  mov     r9d, 80070057h; char *
0x1400b448b  mov     edx, 32Fh; void *
0x1400b4490  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b4496  mov     rdi, [rdx]
0x1400b4499  mov     r14, [rdx+8]
0x1400b449d  jmp     loc_1400B4526
0x1400b44a2  cmp     rdi, rbx
0x1400b44a5  jz      short loc_1400B4522
0x1400b44a7  test    sil, sil
0x1400b44aa  jnz     short loc_1400B44EF
0x1400b44ac  cmp     qword ptr [rbx+38h], 7
0x1400b44b1  lea     rdx, [rbx+20h]
0x1400b44b5  jbe     short loc_1400B44BA
0x1400b44b7  mov     rdx, [rdx]
0x1400b44ba  cmp     qword ptr [rdi+38h], 7
0x1400b44bf  lea     rcx, [rdi+20h]
0x1400b44c3  jbe     short loc_1400B44C8
0x1400b44c5  mov     rcx, [rcx]
0x1400b44c8  call    cs:__imp__o__wcsicmp
0x1400b44cf  nop     dword ptr [rax+rax+00h]
0x1400b44d4  test    eax, eax
0x1400b44d6  jnz     short loc_1400B44E4
0x1400b44d8  mov     al, [rbx+41h]
0x1400b44db  cmp     [rdi+41h], al
0x1400b44de  jnz     short loc_1400B44E4
0x1400b44e0  mov     al, 1
0x1400b44e2  jmp     short loc_1400B44E6
0x1400b44e4  xor     al, al
0x1400b44e6  mov     rcx, [rsp+58h]; this
0x1400b44eb  test    al, al
0x1400b44ed  jnz     short loc_1400B4543
0x1400b44ef  cmp     qword ptr [rbx+18h], 7
0x1400b44f4  jbe     short loc_1400B44FB
0x1400b44f6  mov     rdx, [rbx]
0x1400b44f9  jmp     short loc_1400B44FE
0x1400b44fb  mov     rdx, rbx
0x1400b44fe  cmp     qword ptr [rdi+18h], 7
0x1400b4503  jbe     short loc_1400B450A
0x1400b4505  mov     rcx, [rdi]
0x1400b4508  jmp     short loc_1400B450D
0x1400b450a  mov     rcx, rdi
0x1400b450d  mov     rbp, [rsp+58h]
0x1400b4512  call    cs:__imp__o__wcsicmp
0x1400b4519  nop     dword ptr [rax+rax+00h]
0x1400b451e  test    eax, eax
0x1400b4520  jz      short loc_1400B455B
0x1400b4522  add     rdi, 50h ; 'P'
0x1400b4526  cmp     rdi, r14
0x1400b4529  jnz     loc_1400B44A2
0x1400b452f  test    sil, sil
0x1400b4532  jnz     loc_1400B45C5
0x1400b4538  mov     rdi, [r12]
0x1400b453c  mov     rsi, [r12+8]
0x1400b4541  jmp     short loc_1400B45C0
0x1400b4543  mov     r9d, 80070057h; char *
0x1400b4549  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b4550  mov     edx, 33Dh; void *
0x1400b4555  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b455b  mov     r9d, 80070057h; char *
0x1400b4561  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b4568  mov     edx, 341h; void *
0x1400b456d  mov     rcx, rbp; this
0x1400b4570  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b4576  cmp     qword ptr [rbx+38h], 7
0x1400b457b  lea     rcx, [rdi+20h]
0x1400b457f  jbe     short loc_1400B4587
0x1400b4581  mov     r8, [rbx+20h]
0x1400b4585  jmp     short loc_1400B458B
0x1400b4587  lea     r8, [rbx+20h]
0x1400b458b  cmp     qword ptr [rcx+18h], 7
0x1400b4590  jbe     short loc_1400B4595
0x1400b4592  mov     rcx, [rcx]
0x1400b4595  mov     r9, [r15]
0x1400b4598  mov     rdx, [rdi+30h]
0x1400b459c  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1400b45a1  test    al, al
0x1400b45a3  jz      short loc_1400B45B1
0x1400b45a5  mov     al, [rbx+41h]
0x1400b45a8  cmp     [rdi+45h], al
0x1400b45ab  jnz     short loc_1400B45B1
0x1400b45ad  mov     al, 1
0x1400b45af  jmp     short loc_1400B45B3
0x1400b45b1  xor     al, al
0x1400b45b3  mov     rcx, [rsp+58h]; this
0x1400b45b8  test    al, al
0x1400b45ba  jnz     short loc_1400B45D5
0x1400b45bc  add     rdi, 70h ; 'p'
0x1400b45c0  cmp     rdi, rsi
0x1400b45c3  jnz     short loc_1400B4576
0x1400b45c5  add     rsp, 20h
0x1400b45c9  pop     r15
0x1400b45cb  pop     r14
0x1400b45cd  pop     r12
0x1400b45cf  pop     rdi
0x1400b45d0  pop     rsi
0x1400b45d1  pop     rbp
0x1400b45d2  pop     rbx
0x1400b45d3  retn
0x1400b45d5  mov     r9d, 80070057h; char *
0x1400b45db  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400b45e2  mov     edx, 34Ah; void *
0x1400b45e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
