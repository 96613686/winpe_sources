# CTypeManager::Open(unsigned __int64,unsigned __int64,unsigned __int64,CObjectName &,ushort const *,CMemoryManager *,int)

- ea: `0x180017598`
- end: `0x180017880`
- name: `?Open@CTypeManager@@QEAAH_K00AEAVCObjectName@@PEBGPEAVCMemoryManager@@H@Z`
- size: `744`
- prototype: `__int64 __fastcall(CTypeManager *__hidden this, unsigned __int64, unsigned __int64, unsigned __int64, struct CObjectName *, const unsigned __int16 *, struct CMemoryManager *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180010e44`
- `0x180011578`

## callees

- `0x180002250`
- `0x180005e18`
- `0x18000f200`
- `0x180010400`
- `0x180010ca4`
- `0x1800150dc`
- `0x18001541c`
- `0x180016694`
- `0x180017598`
- `0x180017f94`
- `0x180018638`
- `0x18001dc70`
- `0x180027510`
- `0x18002a010`

## string_xrefs

- `0x180017819`: `CTypeManager::Open`
- `0x1800177f5`: `CTypeManager::Open: m_SpinLocks.Create(%s) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTypeManager::Open(
        CTypeManager *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 *a6,
        struct CMemoryManager *a7,
        int a8)
{
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // r14
  struct SMainPageHeader *v12; // rax
  unsigned __int64 v13; // rdi
  int v15; // ebx
  int *v16; // rax
  __int64 v17; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v19; // [rsp+78h] [rbp-90h]
  __int64 v20; // [rsp+80h] [rbp-88h]
  __int64 v21; // [rsp+88h] [rbp-80h]
  void *v22[3]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v23[368]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 v24[8]; // [rsp+218h] [rbp+110h] BYREF
  __int128 v25; // [rsp+228h] [rbp+120h]
  __int16 v26; // [rsp+238h] [rbp+130h]
  LPCWSTR lpModuleName; // [rsp+270h] [rbp+168h]

  v22[1] = (void *)-2LL;
  if ( !a3 )
    return 0;
  if ( !a6 )
    return 0;
  if ( !a7 )
    return 0;
  if ( !*a5 )
    return 0;
  *(_QWORD *)this = 0x4D53424C4B425244LL;
  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 2) = a4;
  *((_QWORD *)this + 4) = a7;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  v26 = 0;
  if ( (int)StringCchPrintfW(v24, 0x11u, L"%I64x", 0x4D53424C4B425244LL) < 0 )
    return 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v24[v10] );
  do
    ++v9;
  while ( a6[v9] );
  v19 = 0;
  v20 = 0;
  v18 = 0;
  v21 = 10;
  if ( !(unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize(&v18, v10 + v9 + 6)
    || (v11 = v19,
        (int)StringCchPrintfW((unsigned __int16 *)(v18 & -(__int64)(v19 != 0)), v19, L"%s.%s.spl", a6, v24) < 0)
    || !(unsigned int)CBin::Init((CBin *)v23, *((_QWORD *)this + 1), a7, 0) )
  {
LABEL_17:
    CBuffer::~CBuffer((CBuffer *)&v18);
    return 0;
  }
  v22[0] = 0;
  v12 = CBin::MapPageHeader((CBin *)v23, v22);
  if ( v12 )
  {
    v13 = *((_QWORD *)v12 + 2);
    CBin::UnmapPageHeader((CBin *)v23, v22[0]);
  }
  else
  {
    v13 = 0;
  }
  v17 = 0;
  if ( !CObjectName::Init((CObjectName *)&v17, *a5, v24) )
  {
LABEL_16:
    CObjectName::Close((CObjectName *)&v17);
    goto LABEL_17;
  }
  if ( !(unsigned int)CSpinLockFileMappingArray::Create(
                        (CTypeManager *)((char *)this + 24),
                        (const unsigned __int16 *)(v18 & ((unsigned __int128)-(__int128)v11 >> 64)),
                        (struct CObjectName *)&v17,
                        v13,
                        a8) )
  {
    if ( g_bEnableDiagnosticMode )
    {
      v15 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
      v16 = (int *)ConstructPartialMsgW(
                     0x6B000000u,
                     "CTypeManager::Open: m_SpinLocks.Create(%s) failed",
                     (const char *)(v18 & -(__int64)(v11 != 0)));
      WdsSetupLogMessageW(
        v16,
        589824,
        (__int64)L"D",
        0,
        0xFACu,
        L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
        L"CTypeManager::Open",
        lpModuleName,
        v15,
        0,
        0);
    }
    goto LABEL_16;
  }
  CObjectName::Close((CObjectName *)&v17);
  CBuffer::~CBuffer((CBuffer *)&v18);
  return 1;
}

```

## disassembly

```asm
0x180017598  mov     rax, rsp
0x18001759b  push    rbp
0x18001759c  push    rdi
0x18001759d  push    r12
0x18001759f  push    r13
0x1800175a1  push    r14
0x1800175a3  lea     rbp, [rax-168h]
0x1800175aa  sub     rsp, 240h
0x1800175b1  mov     [rbp+160h+var_1D0], 0FFFFFFFFFFFFFFFEh
0x1800175b9  mov     [rax+10h], rbx
0x1800175bd  mov     [rax+18h], rsi
0x1800175c1  mov     rax, cs:__security_cookie
0x1800175c8  xor     rax, rsp
0x1800175cb  mov     [rbp+160h+var_28], rax
0x1800175d2  mov     rbx, rcx
0x1800175d5  mov     r12, [rbp+160h+arg_20]
0x1800175dc  mov     rdi, [rbp+160h+arg_28]
0x1800175e3  xor     r13d, r13d
0x1800175e6  test    r8, r8
0x1800175e9  jz      loc_180017763
0x1800175ef  test    rdi, rdi
0x1800175f2  jz      loc_180017763
0x1800175f8  mov     rsi, [rbp+160h+arg_30]
0x1800175ff  test    rsi, rsi
0x180017602  jz      loc_180017763
0x180017608  cmp     [r12], r13
0x18001760c  jz      loc_180017763
0x180017612  mov     rcx, 4D53424C4B425244h
0x18001761c  mov     [rbx], rcx
0x18001761f  mov     [rbx+8], r8
0x180017623  mov     [rbx+10h], r9
0x180017627  mov     [rbx+20h], rsi
0x18001762b  xorps   xmm0, xmm0
0x18001762e  xor     eax, eax
0x180017630  movups  xmmword ptr [rbp+160h+var_50], xmm0
0x180017637  movups  [rbp+160h+var_40], xmm0
0x18001763e  mov     [rbp+160h+var_30], ax
0x180017645  mov     r9, rcx
0x180017648  lea     r8, aI64x; "%I64x"
0x18001764f  lea     edx, [rax+11h]; unsigned __int64
0x180017652  lea     rcx, [rbp+160h+var_50]; unsigned __int16 *
0x180017659  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001765e  test    eax, eax
0x180017660  js      loc_180017763
0x180017666  lea     rdx, [rbp+160h+var_50]
0x18001766d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017671  mov     rcx, rax
0x180017674  inc     rcx
0x180017677  cmp     [rdx+rcx*2], r13w
0x18001767c  jnz     short loc_180017674
0x18001767e  inc     rax
0x180017681  cmp     [rdi+rax*2], r13w
0x180017686  jnz     short loc_18001767E
0x180017688  lea     rdx, [rax+6]
0x18001768c  add     rdx, rcx
0x18001768f  mov     [rsp+260h+var_1F0], r13
0x180017694  mov     [rsp+260h+var_1E8], r13
0x180017699  mov     [rsp+260h+var_1F8], r13
0x18001769e  mov     [rbp+160h+var_1E0], 0Ah
0x1800176a6  lea     rcx, [rsp+260h+var_1F8]
0x1800176ab  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x1800176b0  test    eax, eax
0x1800176b2  jz      loc_180017759
0x1800176b8  mov     r14, [rsp+260h+var_1F0]
0x1800176bd  mov     rax, r14
0x1800176c0  neg     rax
0x1800176c3  sbb     rcx, rcx
0x1800176c6  and     rcx, [rsp+260h+var_1F8]; unsigned __int16 *
0x1800176cb  lea     rax, [rbp+160h+var_50]
0x1800176d2  mov     qword ptr [rsp+260h+var_240], rax
0x1800176d7  mov     r9, rdi
0x1800176da  lea     r8, aSSSpl; "%s.%s.spl"
0x1800176e1  mov     rdx, r14; unsigned __int64
0x1800176e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800176e9  test    eax, eax
0x1800176eb  js      short loc_180017759
0x1800176ed  xor     r9d, r9d; unsigned __int64
0x1800176f0  mov     r8, rsi; struct CMemoryManager *
0x1800176f3  mov     rdx, [rbx+8]; unsigned __int64
0x1800176f7  lea     rcx, [rbp+160h+var_1C0]; this
0x1800176fb  call    ?Init@CBin@@QEAAH_KPEAVCMemoryManager@@0@Z; CBin::Init(unsigned __int64,CMemoryManager *,unsigned __int64)
0x180017700  test    eax, eax
0x180017702  jz      short loc_180017759
0x180017704  mov     [rbp+160h+var_1D8], r13
0x180017708  lea     rdx, [rbp+160h+var_1D8]; void **
0x18001770c  lea     rcx, [rbp+160h+var_1C0]; this
0x180017710  call    ?MapPageHeader@CBin@@AEAAPEAUSMainPageHeader@@PEAPEAX@Z; CBin::MapPageHeader(void * *)
0x180017715  test    rax, rax
0x180017718  jnz     short loc_18001771F
0x18001771a  mov     rdi, r13
0x18001771d  jmp     short loc_180017730
0x18001771f  mov     rdi, [rax+10h]
0x180017723  mov     rdx, [rbp+160h+var_1D8]; void *
0x180017727  lea     rcx, [rbp+160h+var_1C0]; this
0x18001772b  call    ?UnmapPageHeader@CBin@@AEAAHPEAX@Z; CBin::UnmapPageHeader(void *)
0x180017730  mov     [rsp+260h+var_200], r13
0x180017735  lea     r8, [rbp+160h+var_50]; unsigned __int16 *
0x18001773c  mov     rdx, [r12]; unsigned __int16 *
0x180017740  lea     rcx, [rsp+260h+var_200]; this
0x180017745  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x18001774a  test    eax, eax
0x18001774c  jnz     short loc_180017791
0x18001774e  lea     rcx, [rsp+260h+var_200]; this
0x180017753  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180017758  nop
0x180017759  lea     rcx, [rsp+260h+var_1F8]; this
0x18001775e  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180017763  xor     eax, eax
0x180017765  mov     rcx, [rbp+160h+var_28]
0x18001776c  xor     rcx, rsp; StackCookie
0x18001776f  call    __security_check_cookie
0x180017774  lea     r11, [rsp+260h+var_20]
0x18001777c  mov     rbx, [r11+38h]
0x180017780  mov     rsi, [r11+40h]
0x180017784  mov     rsp, r11
0x180017787  pop     r14
0x180017789  pop     r13
0x18001778b  pop     r12
0x18001778d  pop     rdi
0x18001778e  pop     rbp
0x18001778f  retn
0x180017791  mov     rax, r14
0x180017794  neg     rax
0x180017797  sbb     rdx, rdx
0x18001779a  and     rdx, [rsp+260h+var_1F8]; unsigned __int16 *
0x18001779f  lea     rcx, [rbx+18h]; this
0x1800177a3  mov     eax, [rbp+160h+arg_38]
0x1800177a9  mov     [rsp+260h+var_240], eax; int
0x1800177ad  mov     r9, rdi; unsigned __int64
0x1800177b0  lea     r8, [rsp+260h+var_200]; struct CObjectName *
0x1800177b5  call    ?Create@CSpinLockFileMappingArray@@QEAAHPEBGAEAVCObjectName@@_KH@Z; CSpinLockFileMappingArray::Create(ushort const *,CObjectName &,unsigned __int64,int)
0x1800177ba  test    eax, eax
0x1800177bc  jnz     loc_180017861
0x1800177c2  cmp     cs:?g_bEnableDiagnosticMode@@3HA, r13d; int g_bEnableDiagnosticMode
0x1800177c9  jz      loc_180017851
0x1800177cf  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800177d6  mov     rax, [rcx]
0x1800177d9  mov     rax, [rax]
0x1800177dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177e1  mov     ebx, eax
0x1800177e3  mov     rdi, [rbp+168h]
0x1800177ea  neg     r14
0x1800177ed  sbb     r8, r8
0x1800177f0  and     r8, [rsp+260h+var_1F8]
0x1800177f5  lea     rdx, aCtypemanagerOp_0; "CTypeManager::Open: m_SpinLocks.Create("...
0x1800177fc  mov     ecx, 6B000000h; unsigned int
0x180017801  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017806  mov     [rsp+260h+var_210], r13d; int
0x18001780b  mov     [rsp+260h+var_218], r13; __int64
0x180017810  mov     [rsp+260h+var_220], ebx; int
0x180017814  mov     [rsp+260h+lpModuleName], rdi; lpModuleName
0x180017819  lea     rcx, aCtypemanagerOp; "CTypeManager::Open"
0x180017820  mov     [rsp+260h+var_230], rcx; __int64
0x180017825  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x18001782c  mov     [rsp+260h+var_238], rcx; unsigned __int16 *
0x180017831  mov     [rsp+260h+var_240], 0FACh; int
0x180017839  xor     r9d, r9d; int
0x18001783c  lea     r8, aD_1; "D"
0x180017843  mov     edx, 90000h; int
0x180017848  mov     rcx, rax; int
0x18001784b  call    WdsSetupLogMessageW
0x180017850  nop
0x180017851  lea     rcx, [rsp+260h+var_200]; this
0x180017856  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x18001785b  nop
0x18001785c  jmp     loc_180017759
0x180017861  lea     rcx, [rsp+260h+var_200]; this
0x180017866  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x18001786b  nop
0x18001786c  lea     rcx, [rsp+260h+var_1F8]; this
0x180017871  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180017876  mov     eax, 1
0x18001787b  jmp     loc_180017765
```
