# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)

- ea: `0x180006e30`
- end: `0x180006f50`
- name: `??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z`
- size: `288`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cfb8`
- `0x18000fa44`
- `0x180010d8c`
- `0x180011308`

## callees

- `0x180003870`
- `0x180006e30`
- `0x18000c228`
- `0x18001d010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006eaa`
- `msvcrt!memmove_s` at `0x180006eaa`
- `msvcrt!memcpy_s` at `0x180006eb5`
- `msvcrt!memcpy_s` at `0x180006eb5`

## pseudocode

```c
char **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        char **a1,
        char *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // r15
  char *v7; // rcx
  rsize_t v8; // r9
  char *v9; // rax
  char *v10; // rdx
  __int64 v11; // rbx

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a2[2 * v4] );
    if ( (_DWORD)v4 )
    {
      v5 = (a2 - *a1) >> 1;
      v6 = *((unsigned int *)*a1 - 4);
      if ( (int)((*((_DWORD *)*a1 - 3) - v4) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v4);
      v7 = *a1;
      v8 = 2LL * (int)v4;
      if ( v5 > v6 )
        memcpy_s(v7, v8, a2, v8);
      else
        memmove_s(v7, v8, &v7[2 * v5], v8);
      if ( (int)v4 >= 0 && (int)v4 <= *((_DWORD *)*a1 - 3) )
      {
        *((_DWORD *)*a1 - 4) = v4;
        *(_WORD *)&(*a1)[2 * (int)v4] = 0;
        return a1;
      }
LABEL_21:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  v9 = *a1;
  v10 = *a1 - 24;
  if ( !*((_DWORD *)v10 + 2) )
    return a1;
  if ( *((int *)v10 + 4) < 0 )
  {
    if ( *((int *)v9 - 3) >= 0 )
    {
      *((_DWORD *)v9 - 4) = 0;
      *(_WORD *)*a1 = 0;
      return a1;
    }
    goto LABEL_21;
  }
  v11 = *(_QWORD *)v10;
  if ( _InterlockedDecrement((volatile signed __int32 *)v10 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  *a1 = (char *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11) + 24);
  return a1;
}

```

## disassembly

```asm
0x180006e30  push    rbx
0x180006e32  push    rbp
0x180006e33  push    rsi
0x180006e34  push    rdi
0x180006e35  push    r12
0x180006e37  push    r14
0x180006e39  push    r15
0x180006e3b  sub     rsp, 20h
0x180006e3f  mov     rdi, rcx
0x180006e42  xor     r12d, r12d
0x180006e45  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006e49  mov     r14, rdx
0x180006e4c  test    rdx, rdx
0x180006e4f  jz      loc_180006ED8
0x180006e55  mov     rbx, rcx
0x180006e58  inc     rbx
0x180006e5b  cmp     [rdx+rbx*2], r12w
0x180006e60  jnz     short loc_180006E58
0x180006e62  test    ebx, ebx
0x180006e64  jz      short loc_180006ED8
0x180006e66  mov     rax, [rdi]
0x180006e69  mov     rbp, r14
0x180006e6c  sub     rbp, rax
0x180006e6f  mov     ecx, 1
0x180006e74  sar     rbp, 1
0x180006e77  sub     ecx, [rax-8]
0x180006e7a  mov     r15d, [rax-10h]
0x180006e7e  mov     eax, [rax-0Ch]
0x180006e81  sub     eax, ebx
0x180006e83  or      ecx, eax
0x180006e85  jge     short loc_180006E91
0x180006e87  mov     edx, ebx
0x180006e89  mov     rcx, rdi
0x180006e8c  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180006e91  mov     rcx, [rdi]; Destination
0x180006e94  movsxd  rax, ebx
0x180006e97  lea     rsi, [rax+rax]
0x180006e9b  mov     r9, rsi; SourceSize
0x180006e9e  mov     rdx, rsi; DestinationSize
0x180006ea1  cmp     rbp, r15
0x180006ea4  ja      short loc_180006EB2
0x180006ea6  lea     r8, [rcx+rbp*2]; Source
0x180006eaa  call    cs:__imp_memmove_s
0x180006eb0  jmp     short loc_180006EBB
0x180006eb2  mov     r8, r14; Source
0x180006eb5  call    cs:__imp_memcpy_s
0x180006ebb  test    ebx, ebx
0x180006ebd  js      loc_180006F45
0x180006ec3  mov     rax, [rdi]
0x180006ec6  cmp     ebx, [rax-0Ch]
0x180006ec9  jg      short loc_180006F45
0x180006ecb  mov     [rax-10h], ebx
0x180006ece  mov     rcx, [rdi]
0x180006ed1  mov     [rsi+rcx], r12w
0x180006ed6  jmp     short loc_180006F33
0x180006ed8  mov     rax, [rdi]
0x180006edb  lea     rdx, [rax-18h]
0x180006edf  cmp     [rdx+8], r12d
0x180006ee3  jz      short loc_180006F33
0x180006ee5  cmp     [rdx+10h], r12d
0x180006ee9  jge     short loc_180006EFE
0x180006eeb  cmp     [rax-0Ch], r12d
0x180006eef  jl      short loc_180006F45
0x180006ef1  mov     [rax-10h], r12d
0x180006ef5  mov     rcx, [rdi]
0x180006ef8  mov     [rcx], r12w
0x180006efc  jmp     short loc_180006F33
0x180006efe  mov     rbx, [rdx]
0x180006f01  mov     eax, ecx
0x180006f03  lock xadd [rdx+10h], eax
0x180006f08  add     eax, ecx
0x180006f0a  test    eax, eax
0x180006f0c  jg      short loc_180006F1D
0x180006f0e  mov     rcx, [rdx]
0x180006f11  mov     rax, [rcx]
0x180006f14  mov     rax, [rax+8]
0x180006f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1d  mov     rax, [rbx]
0x180006f20  mov     rcx, rbx
0x180006f23  mov     rax, [rax+18h]
0x180006f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2c  add     rax, 18h
0x180006f30  mov     [rdi], rax
0x180006f33  mov     rax, rdi
0x180006f36  add     rsp, 20h
0x180006f3a  pop     r15
0x180006f3c  pop     r14
0x180006f3e  pop     r12
0x180006f40  pop     rdi
0x180006f41  pop     rsi
0x180006f42  pop     rbp
0x180006f43  pop     rbx
0x180006f44  retn
0x180006f45  mov     ecx, 80070057h; int
0x180006f4a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
