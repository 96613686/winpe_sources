# SCardWriteCacheCommon(unsigned __int64,_GUID *,ulong,uchar *,uchar *,ulong,int)

- ea: `0x180011880`
- end: `0x180011b05`
- name: `?SCardWriteCacheCommon@@YAJ_KPEAU_GUID@@KPEAE2KH@Z`
- size: `645`
- prototype: `__int64 __fastcall(unsigned __int64, struct _GUID *, unsigned int, unsigned __int8 *, unsigned __int8 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011850`
- `0x180026f80`

## callees

- `0x18000e090`
- `0x18000e680`
- `0x180011880`
- `0x180012650`
- `0x1800126f0`
- `0x180012730`
- `0x180012d80`
- `0x18001b9b8`
- `0x18002c15c`
- `0x18002ef20`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800118c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800118c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011903`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011903`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SCardWriteCacheCommon(
        unsigned __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        int a7)
{
  unsigned __int8 *v7; // rsi
  unsigned int v8; // r12d
  struct _GUID *v9; // r14
  CHandleList *v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // r15
  struct CHandleList::HandlePtr *HandlePtr; // rax
  CSCardUserContext *v14; // rbx
  int v15; // r13d
  int v16; // eax
  const unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  unsigned int v20; // [rsp+40h] [rbp-C8h]
  ulong pExceptionObject; // [rsp+44h] [rbp-C4h] BYREF
  ulong v22; // [rsp+48h] [rbp-C0h] BYREF
  ulong v23; // [rsp+4Ch] [rbp-BCh] BYREF
  ulong v24; // [rsp+50h] [rbp-B8h] BYREF
  const int *v25; // [rsp+58h] [rbp-B0h] BYREF
  void *v26; // [rsp+60h] [rbp-A8h]
  int v27; // [rsp+68h] [rbp-A0h]
  int v28; // [rsp+6Ch] [rbp-9Ch]
  void **v29; // [rsp+70h] [rbp-98h] BYREF
  int v30; // [rsp+78h] [rbp-90h]
  const int *v31; // [rsp+80h] [rbp-88h]
  __int64 v32; // [rsp+88h] [rbp-80h]
  int v33; // [rsp+90h] [rbp-78h]
  int v34; // [rsp+94h] [rbp-74h]
  _QWORD v35[2]; // [rsp+98h] [rbp-70h] BYREF
  int v36; // [rsp+A8h] [rbp-60h]
  int v37; // [rsp+ACh] [rbp-5Ch]
  ulong v38; // [rsp+B0h] [rbp-58h] BYREF
  ulong v39; // [rsp+B4h] [rbp-54h] BYREF
  CSCardUserContext *v40; // [rsp+B8h] [rbp-50h]
  char *v41; // [rsp+C0h] [rbp-48h]

  v7 = a4;
  v8 = a3;
  v9 = a2;
  v20 = 0;
  try
  {
    v11 = g_phlContexts;
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v41 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v11, a1);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v40 = *(CSCardUserContext **)HandlePtr;
    v14 = v40;
    LeaveCriticalSection(v12);
    if ( *((_DWORD *)v40 + 4) )
    {
      v22 = -2146435042;
      throw &v22;
    }
    if ( !v9 || !v7 )
    {
      v24 = -2146435068;
      throw &v24;
    }
    v25 = &CBuffer::`vftable';
    v26 = 0;
    v27 = 0;
    v28 = 0;
    CBuffer::Set((CBuffer *)&v25, a5, a6);
    v29 = &CTextString::`vftable';
    v31 = &CBuffer::`vftable';
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35[0] = &CBuffer::`vftable';
    v35[1] = 0;
    v36 = 0;
    v37 = 0;
    v30 = 3;
    v15 = a7;
    if ( a7 == 1 )
    {
      CTextString::operator=(&v29, v7);
    }
    else
    {
      v16 = ((__int64 (__fastcall *)(void ***, unsigned __int8 *))v29[2])(&v29, v7);
      CBuffer::Set((CBuffer *)v35, v7, v16 + 1);
      v30 = 1;
    }
    try
    {
      v17 = CTextString::Unicode((CTextString *)&v29);
      CSCardUserContext::WriteCache(v14, v9, v8, v17, (struct CBuffer *)&v25);
    }
    catch ( ulong v38 )
    {
      if ( v38 != 1753 && v38 + 2146435043 > 1 )
      {
        v23 = v38;
        throw &v23;
      }
      v15 = a7;
      v7 = a4;
      v8 = a3;
      v9 = a2;
      v14 = v40;
    }
    v18 = *((_QWORD *)v14 + 16);
    if ( v18 )
      v20 = I_SCardWriteCache(v18, v9, v8, v7, a5, a6, v15 == 1);
    CTextString::~CTextString((CTextString *)&v29);
    v25 = &CBuffer::`vftable';
    if ( v26 )
      operator delete(v26);
    v26 = 0;
    v27 = 0;
    v28 = 0;
  }
  catch ( ulong v39 )
  {
    return v39;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v20;
}

```

## disassembly

```asm
0x180011880  mov     rax, rsp
0x180011883  mov     [rax+20h], r9
0x180011887  mov     [rax+18h], r8d
0x18001188b  mov     [rax+10h], rdx
0x18001188f  push    rbx
0x180011890  push    rsi
0x180011891  push    rdi
0x180011892  push    r12
0x180011894  push    r13
0x180011896  push    r14
0x180011898  push    r15
0x18001189a  sub     rsp, 0D0h
0x1800118a1  mov     rsi, r9
0x1800118a4  mov     r12d, r8d
0x1800118a7  mov     r14, rdx
0x1800118aa  mov     r13, rcx
0x1800118ad  xor     edi, edi
0x1800118af  mov     [rsp+108h+var_C8], edi
0x1800118b3  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x1800118ba  lea     r15, [rbx+20h]
0x1800118be  mov     [rax-48h], r15
0x1800118c2  mov     rcx, r15; lpCriticalSection
0x1800118c5  call    cs:__imp_EnterCriticalSection
0x1800118cb  nop
0x1800118cc  mov     rdx, r13; unsigned __int64
0x1800118cf  mov     rcx, rbx; this
0x1800118d2  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800118d7  test    rax, rax
0x1800118da  jnz     short loc_1800118F5
0x1800118dc  mov     [rsp+108h+pExceptionObject], 6
0x1800118e4  lea     rdx, _TI1K; pThrowInfo
0x1800118eb  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800118f0  call    _CxxThrowException_0
0x1800118f5  mov     rbx, [rax]
0x1800118f8  mov     [rsp+108h+var_50], rbx
0x180011900  mov     rcx, r15; lpCriticalSection
0x180011903  call    cs:__imp_LeaveCriticalSection
0x180011909  cmp     [rbx+10h], edi
0x18001190c  jz      short loc_180011927
0x18001190e  mov     [rsp+108h+var_C0], 8010001Eh
0x180011916  lea     rdx, _TI1K; pThrowInfo
0x18001191d  lea     rcx, [rsp+108h+var_C0]; pExceptionObject
0x180011922  call    _CxxThrowException_0
0x180011927  test    r14, r14
0x18001192a  jz      loc_180011AD2
0x180011930  test    rsi, rsi
0x180011933  jz      loc_180011AD2
0x180011939  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180011940  mov     [rsp+108h+var_B0], r15
0x180011945  mov     [rsp+108h+var_A8], rdi
0x18001194a  mov     [rsp+108h+var_A0], edi
0x18001194e  mov     [rsp+108h+var_9C], edi
0x180011952  mov     r8d, [rsp+108h+arg_28]; unsigned int
0x18001195a  mov     rdx, [rsp+108h+arg_20]; unsigned __int8 *
0x180011962  lea     rcx, [rsp+108h+var_B0]; this
0x180011967  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18001196c  nop
0x18001196d  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180011974  mov     [rsp+108h+var_98], rax
0x180011979  mov     [rsp+108h+var_88], r15
0x180011981  mov     [rsp+108h+var_80], rdi
0x180011989  mov     [rsp+108h+var_78], edi
0x180011990  mov     [rsp+108h+var_74], edi
0x180011997  mov     [rsp+108h+var_70], r15
0x18001199f  mov     [rsp+108h+var_68], rdi
0x1800119a7  mov     [rsp+108h+var_60], edi
0x1800119ae  mov     [rsp+108h+var_5C], edi
0x1800119b5  mov     [rsp+108h+var_90], 3
0x1800119bd  mov     r13d, [rsp+108h+arg_30]
0x1800119c5  mov     rdx, rsi
0x1800119c8  lea     rcx, [rsp+108h+var_98]
0x1800119cd  cmp     r13d, 1
0x1800119d1  jnz     short loc_1800119DA
0x1800119d3  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x1800119d8  jmp     short loc_180011A04
0x1800119da  mov     rax, [rsp+108h+var_98]
0x1800119df  mov     rax, [rax+10h]
0x1800119e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119e8  lea     r8d, [rax+1]; unsigned int
0x1800119ec  mov     rdx, rsi; unsigned __int8 *
0x1800119ef  lea     rcx, [rsp+108h+var_70]; this
0x1800119f7  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x1800119fc  mov     [rsp+108h+var_90], 1
0x180011a04  lea     rcx, [rsp+108h+var_98]; this
0x180011a09  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180011a0e  lea     rcx, [rsp+108h+var_B0]
0x180011a13  mov     [rsp+108h+var_E8], rcx; struct CBuffer *
0x180011a18  mov     r9, rax; unsigned __int16 *
0x180011a1b  mov     r8d, r12d; unsigned int
0x180011a1e  mov     rdx, r14; struct _GUID *
0x180011a21  mov     rcx, rbx; this
0x180011a24  call    ?WriteCache@CSCardUserContext@@QEAAXPEAU_GUID@@KPEBGAEAVCBuffer@@@Z; CSCardUserContext::WriteCache(_GUID *,ulong,ushort const *,CBuffer &)
0x180011a29  nop
0x180011a2a  jmp     short loc_180011A5D
0x180011a2c  xor     edi, edi
0x180011a2e  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180011a35  mov     r13d, [rsp+108h+arg_30]
0x180011a3d  mov     rsi, [rsp+108h+arg_18]
0x180011a45  mov     r12d, [rsp+108h+arg_10]
0x180011a4d  mov     r14, [rsp+108h+arg_8]
0x180011a55  mov     rbx, [rsp+108h+var_50]
0x180011a5d  mov     rcx, [rbx+80h]; unsigned __int64
0x180011a64  test    rcx, rcx
0x180011a67  jz      short loc_180011AA4
0x180011a69  mov     eax, [rsp+108h+arg_28]
0x180011a70  mov     r9, rsi; unsigned __int8 *
0x180011a73  mov     r8d, r12d; unsigned int
0x180011a76  mov     rdx, r14; struct _GUID *
0x180011a79  cmp     r13d, 1
0x180011a7d  jnz     short loc_180011A86
0x180011a7f  mov     [rsp+108h+var_D8], r13d
0x180011a84  jmp     short loc_180011A8A
0x180011a86  mov     [rsp+108h+var_D8], edi; int
0x180011a8a  mov     [rsp+108h+var_E0], eax; unsigned int
0x180011a8e  mov     rax, [rsp+108h+arg_20]
0x180011a96  mov     [rsp+108h+var_E8], rax; unsigned __int8 *
0x180011a9b  call    ?I_SCardWriteCache@@YAJ_KPEAU_GUID@@KPEAE2KH@Z; I_SCardWriteCache(unsigned __int64,_GUID *,ulong,uchar *,uchar *,ulong,int)
0x180011aa0  mov     [rsp+108h+var_C8], eax
0x180011aa4  lea     rcx, [rsp+108h+var_98]; this
0x180011aa9  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180011aae  nop
0x180011aaf  mov     [rsp+108h+var_B0], r15
0x180011ab4  mov     rcx, [rsp+108h+var_A8]; void *
0x180011ab9  test    rcx, rcx
0x180011abc  jz      short loc_180011AC3
0x180011abe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011ac3  mov     [rsp+108h+var_A8], rdi
0x180011ac8  mov     [rsp+108h+var_A0], edi
0x180011acc  mov     [rsp+108h+var_9C], edi
0x180011ad0  jmp     short loc_180011AEE
0x180011ad2  mov     [rsp+108h+var_B8], 80100004h
0x180011ada  lea     rdx, _TI1K; pThrowInfo
0x180011ae1  lea     rcx, [rsp+108h+var_B8]; pExceptionObject
0x180011ae6  call    _CxxThrowException_0
0x180011aec  jmp     short $+2
0x180011aee  mov     eax, [rsp+108h+var_C8]
0x180011af2  add     rsp, 0D0h
0x180011af9  pop     r15
0x180011afb  pop     r14
0x180011afd  pop     r13
0x180011aff  pop     r12
0x180011b01  pop     rdi
0x180011b02  pop     rsi
0x180011b03  pop     rbx
0x180011b04  retn
```
