# CCabDecompressor::Init(char const * *,ulong,void *,ulong,int,int)

- ea: `0x180014cb8`
- end: `0x180014eaa`
- name: `?Init@CCabDecompressor@@QEAAJPEAPEBDKPEAXKHH@Z`
- size: `498`
- prototype: `__int64 __fastcall(CCabDecompressor *this, const char **, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015dfc`

## callees

- `0x180003950`
- `0x180014cb8`
- `0x180014eb0`
- `0x1800160c0`
- `0x180016414`
- `0x180042630`
- `0x1800430f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014de7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014de7`
- `RPCRT4!UuidToStringA` at `0x180014e1c`
- `RPCRT4!UuidToStringA` at `0x180014e1c`
- `Cabinet!__imp_FDICreate` at `0x180014daf`
- `Cabinet!__imp_FDICreate` at `0x180014daf`

## string_xrefs

- `0x180014cf5`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x180014e00`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::Init(
        CCabDecompressor *this,
        const char **a2,
        unsigned int a3,
        void *a4,
        unsigned int a5)
{
  __int64 v5; // rdi
  const char **v6; // rbp
  unsigned int LastFDIErrorHr; // ebx
  __int64 v9; // rdx
  __int64 result; // rax
  _QWORD *v11; // rax
  HFDI v12; // rax
  HRESULT v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rsi
  int pfnwrite; // [rsp+20h] [rbp-78h]
  GUID pguid; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = a3;
  v6 = a2;
  if ( !a2 && a3 )
  {
    LastFDIErrorHr = -2147024809;
    v9 = 96;
    goto LABEL_4;
  }
  v11 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v11 )
  {
    v11[3] = 0;
    *v11 = &CSusListIterator<COutputMemoryFile>::`vftable';
    v11[1] = 0;
    v11[2] = 0;
    v11[4] = 0;
  }
  *((_QWORD *)this + 8) = v11;
  if ( !v11 )
  {
    LastFDIErrorHr = -2147024882;
    v9 = 99;
    goto LABEL_4;
  }
  v12 = FDICreate(
          CCabDecompressor::CabDecompressorMemAlloc,
          CCabDecompressor::CabDecompressorMemFree,
          CCabDecompressor::CabDecompressorFileOpen,
          CCabDecompressor::CabDecompressorFileRead,
          CCabDecompressor::CabDecompressorFileWrite,
          CCabDecompressor::CabDecompressorFileClose,
          CCabDecompressor::CabDecompressorFileSeek,
          0,
          (PERF)this + 2);
  *((_QWORD *)this + 5) = v12;
  if ( !v12 )
  {
    LastFDIErrorHr = CCabDecompressor::GetLastFDIErrorHr(this);
    if ( (LastFDIErrorHr & 0x80000000) == 0 )
      return LastFDIErrorHr;
    v9 = 117;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)LastFDIErrorHr,
      pfnwrite);
    return LastFDIErrorHr;
  }
  pguid = 0;
  v13 = CoCreateGuid(&pguid);
  if ( v13 < 0 )
  {
    v14 = 129;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)(unsigned int)v13,
      pfnwrite);
    return (unsigned int)v13;
  }
  v13 = UuidToStringA(&pguid, (RPC_CSTR *)this + 6);
  if ( v13 < 0 )
  {
    v14 = 131;
    goto LABEL_15;
  }
  v13 = CSusArrayList<char *,CSusSortedArrayListItemOpsLPSTR>::Grow((char *)this + 80, (unsigned int)v5);
  if ( v13 < 0 )
  {
    v14 = 136;
    goto LABEL_15;
  }
  if ( (_DWORD)v5 )
  {
    v15 = v5;
    do
    {
      CSusSortedArrayList<char const *,CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete>::Add(
        (char *)this + 80,
        v6++);
      --v15;
    }
    while ( v15 );
  }
  *((_DWORD *)this + 38) = a5;
  result = 0;
  *((_DWORD *)this + 28) = v5;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 39) = 0;
  *((_DWORD *)this + 18) = 1;
  return result;
}

```

## disassembly

```asm
0x180014cb8  push    rbx
0x180014cba  push    rbp
0x180014cbb  push    rsi
0x180014cbc  push    rdi
0x180014cbd  push    r14
0x180014cbf  sub     rsp, 70h
0x180014cc3  mov     rax, cs:__security_cookie
0x180014cca  xor     rax, rsp
0x180014ccd  mov     [rsp+98h+var_38], rax
0x180014cd2  mov     edi, r8d
0x180014cd5  mov     rbp, rdx
0x180014cd8  mov     rbx, rcx
0x180014cdb  test    rdx, rdx
0x180014cde  jnz     short loc_180014D0B
0x180014ce0  test    r8d, r8d
0x180014ce3  jz      short loc_180014D0B
0x180014ce5  mov     ebx, 80070057h
0x180014cea  lea     edx, [rbp+60h]; void *
0x180014ced  mov     rcx, [rsp+98h]; this
0x180014cf5  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180014cfc  mov     r9d, ebx; char *
0x180014cff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d04  mov     eax, ebx
0x180014d06  jmp     loc_180014E92
0x180014d0b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014d12  mov     ecx, 28h ; '('; unsigned __int64
0x180014d17  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014d1c  test    rax, rax
0x180014d1f  jz      short loc_180014D4B
0x180014d21  lea     rcx, ??_7?$CSusListIterator@VCOutputMemoryFile@@@@6B@; const CSusListIterator<COutputMemoryFile>::`vftable'
0x180014d28  mov     qword ptr [rax+18h], 0
0x180014d30  mov     [rax], rcx
0x180014d33  mov     qword ptr [rax+8], 0
0x180014d3b  mov     qword ptr [rax+10h], 0
0x180014d43  mov     qword ptr [rax+20h], 0
0x180014d4b  mov     [rbx+40h], rax
0x180014d4f  test    rax, rax
0x180014d52  jnz     short loc_180014D5E
0x180014d54  mov     ebx, 8007000Eh
0x180014d59  lea     edx, [rax+63h]
0x180014d5c  jmp     short loc_180014CED
0x180014d5e  lea     rax, [rbx+18h]
0x180014d62  mov     [rsp+98h+perf], rax; perf
0x180014d67  lea     r9, ?CabDecompressorFileRead@CCabDecompressor@@CAI_JPEAXI@Z; pfnread
0x180014d6e  mov     [rsp+98h+cpuType], 0; cpuType
0x180014d76  lea     rax, ?CabDecompressorFileSeek@CCabDecompressor@@CAJ_JJH@Z; CCabDecompressor::CabDecompressorFileSeek(__int64,long,int)
0x180014d7d  mov     [rsp+98h+pfnseek], rax; pfnseek
0x180014d82  lea     r8, ?CabDecompressorFileOpen@CCabDecompressor@@CA_JPEBDHH@Z; pfnopen
0x180014d89  lea     rax, ?CabDecompressorFileClose@CCabDecompressor@@CAH_J@Z; CCabDecompressor::CabDecompressorFileClose(__int64)
0x180014d90  mov     [rsp+98h+pfnclose], rax; pfnclose
0x180014d95  lea     rdx, ?CabDecompressorMemFree@CCabDecompressor@@CAXPEAX@Z; pfnfree
0x180014d9c  lea     rax, ?CabDecompressorFileWrite@CCabDecompressor@@CAI_JPEBXI@Z; CCabDecompressor::CabDecompressorFileWrite(__int64,void const *,uint)
0x180014da3  lea     rcx, ?CabDecompressorMemAlloc@CCabDecompressor@@CAPEAXK@Z; pfnalloc
0x180014daa  mov     [rsp+98h+pfnwrite], rax; int
0x180014daf  call    cs:__imp_FDICreate
0x180014db5  mov     [rbx+28h], rax
0x180014db9  test    rax, rax
0x180014dbc  jnz     short loc_180014DDA
0x180014dbe  mov     rcx, rbx; this
0x180014dc1  call    ?GetLastFDIErrorHr@CCabDecompressor@@QEAAJXZ; CCabDecompressor::GetLastFDIErrorHr(void)
0x180014dc6  mov     ebx, eax
0x180014dc8  test    eax, eax
0x180014dca  jns     loc_180014D04
0x180014dd0  mov     edx, 75h ; 'u'
0x180014dd5  jmp     loc_180014CED
0x180014dda  xorps   xmm0, xmm0
0x180014ddd  lea     rcx, [rsp+98h+pguid]; pguid
0x180014de2  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x180014de7  call    cs:__imp_CoCreateGuid
0x180014ded  mov     esi, eax
0x180014def  test    eax, eax
0x180014df1  jns     short loc_180014E13
0x180014df3  mov     edx, 81h; void *
0x180014df8  mov     rcx, [rsp+98h]; this
0x180014e00  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180014e07  mov     r9d, esi; char *
0x180014e0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e0f  mov     eax, esi
0x180014e11  jmp     short loc_180014E92
0x180014e13  lea     rdx, [rbx+30h]; StringUuid
0x180014e17  lea     rcx, [rsp+98h+pguid]; Uuid
0x180014e1c  call    cs:__imp_UuidToStringA
0x180014e22  mov     esi, eax
0x180014e24  test    eax, eax
0x180014e26  jns     short loc_180014E2F
0x180014e28  mov     edx, 83h
0x180014e2d  jmp     short loc_180014DF8
0x180014e2f  mov     edx, edi
0x180014e31  lea     rcx, [rbx+50h]
0x180014e35  call    ?Grow@?$CSusArrayList@PEADVCSusSortedArrayListItemOpsLPSTR@@@@QEAAJK@Z; CSusArrayList<char *,CSusSortedArrayListItemOpsLPSTR>::Grow(ulong)
0x180014e3a  mov     esi, eax
0x180014e3c  test    eax, eax
0x180014e3e  jns     short loc_180014E47
0x180014e40  mov     edx, 88h
0x180014e45  jmp     short loc_180014DF8
0x180014e47  test    edi, edi
0x180014e49  jz      short loc_180014E64
0x180014e4b  mov     rsi, rdi
0x180014e4e  mov     rdx, rbp
0x180014e51  lea     rcx, [rbx+50h]
0x180014e55  call    ?Add@?$CSusSortedArrayList@PEBDVCSusSortedArrayListItemOpsLPCSTRNoDelete@CCabDecompressor@@@@QEAAJAEBQEBDK@Z; CSusSortedArrayList<char const *,CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete>::Add(char const * const &,ulong)
0x180014e5a  add     rbp, 8
0x180014e5e  sub     rsi, 1
0x180014e62  jnz     short loc_180014E4E
0x180014e64  mov     eax, [rsp+98h+arg_20]
0x180014e6b  mov     [rbx+98h], eax
0x180014e71  xor     eax, eax
0x180014e73  mov     [rbx+70h], edi
0x180014e76  mov     qword ptr [rbx+90h], 0
0x180014e81  mov     dword ptr [rbx+9Ch], 0
0x180014e8b  mov     dword ptr [rbx+48h], 1
0x180014e92  mov     rcx, [rsp+98h+var_38]
0x180014e97  xor     rcx, rsp; StackCookie
0x180014e9a  call    __security_check_cookie
0x180014e9f  add     rsp, 70h
0x180014ea3  pop     r14
0x180014ea5  pop     rdi
0x180014ea6  pop     rsi
0x180014ea7  pop     rbp
0x180014ea8  pop     rbx
0x180014ea9  retn
```
