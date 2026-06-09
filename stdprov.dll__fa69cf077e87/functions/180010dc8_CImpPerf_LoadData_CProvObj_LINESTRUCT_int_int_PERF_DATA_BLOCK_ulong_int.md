# CImpPerf::LoadData(CProvObj &,_LINESTRUCT *,int *,int *,_PERF_DATA_BLOCK * *,ulong *,int)

- ea: `0x180010dc8`
- end: `0x180010f7e`
- name: `?LoadData@CImpPerf@@QEAAJAEAVCProvObj@@PEAU_LINESTRUCT@@PEAH2PEAPEAU_PERF_DATA_BLOCK@@PEAKH@Z`
- size: `438`
- prototype: `LSTATUS __fastcall(PCNZWCH *this, struct CProvObj *, struct _LINESTRUCT *, int *, int *, struct _PERF_DATA_BLOCK **, unsigned int *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010fc0`
- `0x180011300`

## callees

- `0x180001010`
- `0x180001310`
- `0x1800087c0`
- `0x1800087f0`
- `0x18000f234`
- `0x180010ae0`
- `0x180010dc8`
- `0x18001175c`
- `0x1800118ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180010e39`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180010e39`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010ecd`

## pseudocode

```c
LSTATUS __fastcall CImpPerf::LoadData(
        PCNZWCH *this,
        struct CProvObj *a2,
        struct _LINESTRUCT *a3,
        int *a4,
        int *a5,
        struct _PERF_DATA_BLOCK **a6,
        unsigned int *a7,
        int a8)
{
  const WCHAR *lpString2; // rax
  int v13; // ebx
  const unsigned __int16 *Token; // rax
  const unsigned __int16 *v15; // rax
  LSTATUS result; // eax
  const unsigned __int16 *v17; // rax
  int TitleIndex; // eax
  const unsigned __int16 *v19; // rax
  int v20; // ebx
  const unsigned __int16 *v21; // rax
  __int16 *v22; // [rsp+30h] [rbp-48h] BYREF
  __int16 v23; // [rsp+38h] [rbp-40h] BYREF
  int v24; // [rsp+3Ch] [rbp-3Ch]

  if ( !CProvObj::sGetToken(a2, 0) || !a4 || !a5 )
    return -2147217400;
  lpString2 = CProvObj::sGetToken(a2, 0);
  v13 = CompareStringW(0x7Fu, 1u, this[68], -1, lpString2, -1);
  Token = CProvObj::sGetToken(a2, 0);
  v23 = 0;
  v22 = &v23;
  v24 = 0;
  TString::assign((TString *)&v22, Token);
  TString::operator=(this + 68, &v22);
  TString::Empty((TString *)&v22);
  if ( v13 == 2 )
  {
    if ( this[71] || this[73] )
      goto LABEL_10;
    goto LABEL_9;
  }
  v15 = CProvObj::sGetToken(a2, 0);
  result = CImpPerf::dwGetRegHandles(this, v15);
  if ( !result )
  {
LABEL_9:
    result = CImpPerf::GetPerfTitleSz((CImpPerf *)this);
    if ( result )
      return result;
LABEL_10:
    *((_DWORD *)this + 132) = GetTickCount();
    v17 = CProvObj::sGetToken(a2, 1);
    *a4 = CImpPerf::iGetTitleIndex((CImpPerf *)this, v17, 0);
    if ( a8 )
    {
      TitleIndex = 0;
    }
    else
    {
      v19 = CProvObj::sGetToken(a2, 2);
      TitleIndex = CImpPerf::iGetTitleIndex((CImpPerf *)this, v19, 1);
    }
    *a5 = TitleIndex;
    v20 = *a4;
    if ( *a4 != -1 && TitleIndex != -1 )
    {
      v21 = CProvObj::sGetToken(a2, 0);
      return PerfCache::dwGetNew((PerfCache *)(this + 17), v21, v20, (unsigned __int8 **)a6, a7, a3);
    }
    return -2147217400;
  }
  return result;
}

```

## disassembly

```asm
0x180010dc8  push    rbx
0x180010dca  push    rbp
0x180010dcb  push    rsi
0x180010dcc  push    rdi
0x180010dcd  push    r12
0x180010dcf  push    r14
0x180010dd1  push    r15
0x180010dd3  sub     rsp, 40h
0x180010dd7  mov     r14, r9
0x180010dda  mov     r12, r8
0x180010ddd  mov     rbp, rdx
0x180010de0  mov     rsi, rcx
0x180010de3  xor     edx, edx; int
0x180010de5  mov     rcx, rbp; this
0x180010de8  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180010ded  test    rax, rax
0x180010df0  jz      loc_180010F6A
0x180010df6  test    r14, r14
0x180010df9  jz      loc_180010F6A
0x180010dff  mov     r15, [rsp+78h+arg_20]
0x180010e07  test    r15, r15
0x180010e0a  jz      loc_180010F6A
0x180010e10  xor     edx, edx; int
0x180010e12  mov     rcx, rbp; this
0x180010e15  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180010e1a  lea     rdi, [rsi+220h]
0x180010e21  or      ecx, 0FFFFFFFFh
0x180010e24  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180010e28  mov     [rsp+78h+lpString2], rax; lpString2
0x180010e2d  mov     r9d, ecx; cchCount1
0x180010e30  mov     r8, [rdi]; lpString1
0x180010e33  lea     edx, [rcx+2]; dwCmpFlags
0x180010e36  lea     ecx, [rdx+7Eh]; Locale
0x180010e39  call    cs:__imp_CompareStringW
0x180010e3f  mov     ebx, eax
0x180010e41  xor     edx, edx; int
0x180010e43  mov     rcx, rbp; this
0x180010e46  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180010e4b  xor     edx, edx
0x180010e4d  mov     [rsp+78h+var_40], dx
0x180010e52  lea     rcx, [rsp+78h+var_40]
0x180010e57  mov     [rsp+78h+var_48], rcx
0x180010e5c  mov     [rsp+78h+var_3C], edx
0x180010e60  mov     rdx, rax; unsigned __int16 *
0x180010e63  lea     rcx, [rsp+78h+var_48]; this
0x180010e68  call    ?assign@TString@@AEAAXPEBG@Z; TString::assign(ushort const *)
0x180010e6d  nop
0x180010e6e  lea     rdx, [rsp+78h+var_48]
0x180010e73  mov     rcx, rdi
0x180010e76  call    ??4TString@@QEAAAEAV0@AEBV0@@Z; TString::operator=(TString const &)
0x180010e7b  nop
0x180010e7c  lea     rcx, [rsp+78h+var_48]; this
0x180010e81  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x180010e86  cmp     ebx, 2
0x180010e89  jz      short loc_180010EA9
0x180010e8b  xor     edx, edx; int
0x180010e8d  mov     rcx, rbp; this
0x180010e90  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180010e95  mov     rdx, rax; unsigned __int16 *
0x180010e98  mov     rcx, rsi; this
0x180010e9b  call    ?dwGetRegHandles@CImpPerf@@QEAAKPEBG@Z; CImpPerf::dwGetRegHandles(ushort const *)
0x180010ea0  test    eax, eax
0x180010ea2  jz      short loc_180010EBD
0x180010ea4  jmp     loc_180010F6F
0x180010ea9  cmp     qword ptr [rsi+238h], 0
0x180010eb1  jnz     short loc_180010ECD
0x180010eb3  cmp     qword ptr [rsi+248h], 0
0x180010ebb  jnz     short loc_180010ECD
0x180010ebd  mov     rcx, rsi; this
0x180010ec0  call    ?GetPerfTitleSz@CImpPerf@@QEAAKXZ; CImpPerf::GetPerfTitleSz(void)
0x180010ec5  test    eax, eax
0x180010ec7  jnz     loc_180010F6F
0x180010ecd  call    cs:__imp_GetTickCount
0x180010ed3  mov     [rsi+210h], eax
0x180010ed9  mov     ebx, 1
0x180010ede  mov     edx, ebx; int
0x180010ee0  mov     rcx, rbp; this
0x180010ee3  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180010ee8  mov     rdx, rax; unsigned __int16 *
0x180010eeb  xor     r8d, r8d; int
0x180010eee  mov     rcx, rsi; this
0x180010ef1  call    ?iGetTitleIndex@CImpPerf@@QEAAHPEBGH@Z; CImpPerf::iGetTitleIndex(ushort const *,int)
0x180010ef6  mov     [r14], eax
0x180010ef9  cmp     [rsp+78h+arg_38], 0
0x180010f01  jz      short loc_180010F07
0x180010f03  xor     eax, eax
0x180010f05  jmp     short loc_180010F22
0x180010f07  mov     edx, 2; int
0x180010f0c  mov     rcx, rbp; this
0x180010f0f  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180010f14  mov     rdx, rax; unsigned __int16 *
0x180010f17  mov     r8d, ebx; int
0x180010f1a  mov     rcx, rsi; this
0x180010f1d  call    ?iGetTitleIndex@CImpPerf@@QEAAHPEBGH@Z; CImpPerf::iGetTitleIndex(ushort const *,int)
0x180010f22  mov     [r15], eax
0x180010f25  mov     ebx, [r14]
0x180010f28  cmp     ebx, 0FFFFFFFFh
0x180010f2b  jz      short loc_180010F6A
0x180010f2d  cmp     eax, 0FFFFFFFFh
0x180010f30  jz      short loc_180010F6A
0x180010f32  xor     edx, edx; int
0x180010f34  mov     rcx, rbp; this
0x180010f37  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180010f3c  lea     rcx, [rsi+88h]; this
0x180010f43  mov     qword ptr [rsp+78h+cchCount2], r12; struct _LINESTRUCT *
0x180010f48  mov     rdx, [rsp+78h+arg_30]
0x180010f50  mov     [rsp+78h+lpString2], rdx; unsigned int *
0x180010f55  mov     r9, [rsp+78h+arg_28]; unsigned __int8 **
0x180010f5d  mov     r8d, ebx; int
0x180010f60  mov     rdx, rax; unsigned __int16 *
0x180010f63  call    ?dwGetNew@PerfCache@@QEAAKPEBGHPEAPEAEPEAKPEAU_LINESTRUCT@@@Z; PerfCache::dwGetNew(ushort const *,int,uchar * *,ulong *,_LINESTRUCT *)
0x180010f68  jmp     short loc_180010F6F
0x180010f6a  mov     eax, 80041008h
0x180010f6f  add     rsp, 40h
0x180010f73  pop     r15
0x180010f75  pop     r14
0x180010f77  pop     r12
0x180010f79  pop     rdi
0x180010f7a  pop     rsi
0x180010f7b  pop     rbp
0x180010f7c  pop     rbx
0x180010f7d  retn
```
