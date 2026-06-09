# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)

- ea: `0x18000901c`
- end: `0x180009120`
- name: `?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z`
- size: `260`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180007604`
- `0x18000ce6c`
- `0x18000cfb8`
- `0x18000e31c`
- `0x18000fa44`
- `0x1800104cc`
- `0x180010d8c`
- `0x180011308`
- `0x180014370`

## callees

- `0x18000901c`
- `0x180009128`
- `0x18001477c`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x1800090a4`
- `KERNEL32!SizeofResource` at `0x1800090a4`
- `KERNEL32!LoadResource` at `0x18000907e`
- `KERNEL32!LoadResource` at `0x18000907e`
- `KERNEL32!FindResourceExW` at `0x18000906a`
- `KERNEL32!FindResourceExW` at `0x18000906a`
- `KERNEL32!LockResource` at `0x180009090`
- `KERNEL32!LockResource` at `0x180009090`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        ATL::CAtlBaseModule *a1,
        unsigned int a2)
{
  HMODULE HInstanceAt; // rdi
  int v5; // ebp
  HRSRC Resource; // rax
  ATL::CAtlBaseModule *v7; // rcx
  HRSRC v8; // rsi
  HGLOBAL v9; // rax
  __int64 v10; // rax
  ATL::CAtlBaseModule *v11; // rbx
  int v12; // edx
  int v13; // edx

  HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(a1, 0);
  v5 = 1;
  if ( !HInstanceAt )
    return 0;
  while ( 1 )
  {
    Resource = FindResourceExW(HInstanceAt, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a2 >> 4) + 1), 0);
    v8 = Resource;
    if ( Resource )
      break;
LABEL_12:
    v13 = v5++;
    HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v7, v13);
    if ( !HInstanceAt )
      return 0;
  }
  v9 = LoadResource(HInstanceAt, Resource);
  if ( !v9 )
    goto LABEL_4;
  v11 = (ATL::CAtlBaseModule *)LockResource(v9);
  if ( !v11 )
    goto LABEL_4;
  v7 = (ATL::CAtlBaseModule *)((char *)v11 + SizeofResource(HInstanceAt, v8));
  v12 = a2 & 0xF;
  if ( (a2 & 0xF) != 0 )
  {
    while ( v11 < v7 )
    {
      v11 = (ATL::CAtlBaseModule *)((char *)v11 + 2 * *(unsigned __int16 *)v11 + 2);
      if ( !--v12 )
        goto LABEL_9;
    }
    goto LABEL_4;
  }
LABEL_9:
  if ( v11 >= v7 )
  {
LABEL_4:
    v10 = 0;
    goto LABEL_11;
  }
  v10 = (unsigned __int64)v11 & -(__int64)(*(_WORD *)v11 != 0);
LABEL_11:
  if ( !v10 )
    goto LABEL_12;
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
           a1,
           HInstanceAt,
           a2);
}

```

## disassembly

```asm
0x18000901c  push    rbx
0x18000901e  push    rbp
0x18000901f  push    rsi
0x180009020  push    rdi
0x180009021  push    r12
0x180009023  push    r13
0x180009025  push    r14
0x180009027  push    r15
0x180009029  sub     rsp, 28h
0x18000902d  mov     r14d, edx
0x180009030  mov     r15, rcx
0x180009033  xor     edx, edx; int
0x180009035  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x18000903a  mov     r13d, 1
0x180009040  mov     rdi, rax
0x180009043  mov     ebp, r13d
0x180009046  test    rax, rax
0x180009049  jz      loc_1800090F8
0x18000904f  mov     eax, r14d
0x180009052  shr     eax, 4
0x180009055  add     ax, r13w
0x180009059  movzx   r12d, ax
0x18000905d  xor     r9d, r9d; wLanguage
0x180009060  mov     r8, r12; lpName
0x180009063  mov     rcx, rdi; hModule
0x180009066  lea     edx, [r9+6]; lpType
0x18000906a  call    cs:__imp_FindResourceExW
0x180009070  mov     rsi, rax
0x180009073  test    rax, rax
0x180009076  jz      short loc_1800090E2
0x180009078  mov     rdx, rax; hResInfo
0x18000907b  mov     rcx, rdi; hModule
0x18000907e  call    cs:__imp_LoadResource
0x180009084  test    rax, rax
0x180009087  jnz     short loc_18000908D
0x180009089  xor     eax, eax
0x18000908b  jmp     short loc_1800090DD
0x18000908d  mov     rcx, rax; hResData
0x180009090  call    cs:__imp_LockResource
0x180009096  mov     rbx, rax
0x180009099  test    rax, rax
0x18000909c  jz      short loc_180009089
0x18000909e  mov     rdx, rsi; hResInfo
0x1800090a1  mov     rcx, rdi; hModule
0x1800090a4  call    cs:__imp_SizeofResource
0x1800090aa  mov     ecx, eax
0x1800090ac  mov     edx, r14d
0x1800090af  add     rcx, rbx; this
0x1800090b2  and     edx, 0Fh
0x1800090b5  jbe     short loc_1800090CC
0x1800090b7  cmp     rbx, rcx
0x1800090ba  jnb     short loc_180009089
0x1800090bc  movzx   eax, word ptr [rbx]
0x1800090bf  lea     rbx, [rbx+rax*2]
0x1800090c3  add     rbx, 2
0x1800090c7  add     edx, 0FFFFFFFFh
0x1800090ca  jnz     short loc_1800090B7
0x1800090cc  cmp     rbx, rcx
0x1800090cf  jnb     short loc_180009089
0x1800090d1  movzx   eax, word ptr [rbx]
0x1800090d4  neg     ax
0x1800090d7  sbb     rax, rax
0x1800090da  and     rax, rbx
0x1800090dd  test    rax, rax
0x1800090e0  jnz     short loc_18000910B
0x1800090e2  mov     edx, ebp; int
0x1800090e4  add     ebp, r13d
0x1800090e7  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x1800090ec  mov     rdi, rax
0x1800090ef  test    rax, rax
0x1800090f2  jnz     loc_18000905D
0x1800090f8  xor     eax, eax
0x1800090fa  add     rsp, 28h
0x1800090fe  pop     r15
0x180009100  pop     r14
0x180009102  pop     r13
0x180009104  pop     r12
0x180009106  pop     rdi
0x180009107  pop     rsi
0x180009108  pop     rbp
0x180009109  pop     rbx
0x18000910a  retn
0x18000910b  test    rdi, rdi
0x18000910e  jz      short loc_1800090F8
0x180009110  mov     r8d, r14d
0x180009113  mov     rdx, rdi
0x180009116  mov     rcx, r15
0x180009119  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x18000911e  jmp     short loc_1800090FA
```
