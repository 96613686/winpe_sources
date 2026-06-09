# CWbemNamespace::CreateClassEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x180047f00`
- end: `0x180048357`
- name: `?CreateClassEnum@CWbemNamespace@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `1111`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000ae2c`
- `0x18000b140`
- `0x180020870`
- `0x180020c90`
- `0x18003cfe0`
- `0x180047ed0`
- `0x180047f00`
- `0x180048360`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180048151`
- `wbemcomn!GetMemLogObject` at `0x18004817e`
- `wbemcomn!GetMemLogObject` at `0x18004819a`
- `wbemcomn!GetMemLogObject` at `0x1800481e2`
- `wbemcomn!GetMemLogObject` at `0x18004822a`
- `wbemcomn!GetMemLogObject` at `0x18004825d`
- `wbemcomn!GetMemLogObject` at `0x1800482ae`
- `wbemcomn!GetMemLogObject` at `0x180048151`
- `wbemcomn!GetMemLogObject` at `0x18004817e`
- `wbemcomn!GetMemLogObject` at `0x18004819a`
- `wbemcomn!GetMemLogObject` at `0x1800481e2`
- `wbemcomn!GetMemLogObject` at `0x18004822a`
- `wbemcomn!GetMemLogObject` at `0x18004825d`
- `wbemcomn!GetMemLogObject` at `0x1800482ae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004815f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004818b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800481a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800481ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048238`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004826b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800482bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004815f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004818b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800481a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800481ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048238`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004826b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800482bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::CreateClassEnum(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
  int v6; // ebx
  CWbemNamespace *v8; // rcx
  int v9; // r8d
  struct IEnumWbemClassObject **v10; // r14
  struct IWbemContext *v11; // r13
  struct _IWmiFinalizer *v12; // rsi
  int v13; // eax
  unsigned int v14; // ebx
  struct _IWmiFinalizer *v15; // rbx
  struct _IWmiFinalizer *v16; // rcx
  CClientCnt *v17; // rcx
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v22; // rcx
  __int64 v23; // rdx
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CClientCnt *v26; // rcx
  __int64 v27; // rdx
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r9
  CMemoryLog *v32; // rax
  int ClassEnumAsync; // [rsp+40h] [rbp-48h] BYREF
  struct _IWmiFinalizer *v34; // [rsp+48h] [rbp-40h] BYREF
  struct _IWmiFinalizer *v35; // [rsp+50h] [rbp-38h] BYREF
  struct _IWmiFinalizer *v36; // [rsp+58h] [rbp-30h]
  struct IWbemContext *v38; // [rsp+A8h] [rbp+20h] BYREF

  v38 = a4;
  v6 = (int)a2;
  ClassEnumAsync = CWbemNamespace::CheckNs(this);
  if ( ClassEnumAsync < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ClassEnumAsync);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)ClassEnumAsync;
    }
    v23 = 821;
    goto LABEL_51;
  }
  ClassEnumAsync = CWbemNamespace::AdjustCtx(v8, &v38);
  if ( ClassEnumAsync >= 0 )
  {
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      v10 = a5;
    }
    else
    {
      v10 = a5;
      WPP_SF_Sdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 823, v9, v6, a3, (char)a5, *((_DWORD *)this + 76));
    }
    if ( (a3 & 0xFFFDFFCE) != 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, -2147217400);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v27 = 824;
    }
    else
    {
      if ( v10 )
      {
        *v10 = 0;
        v34 = 0;
        v11 = v38;
        ClassEnumAsync = CWbemNamespace::CreateSyncFinalizer(this, v38, &v34);
        if ( ClassEnumAsync >= 0 )
        {
          v12 = v34;
          v35 = v34;
          try
          {
            ClassEnumAsync = CWbemNamespace::_CreateClassEnumAsync(
                               this,
                               (a3 & 0x10) != 0 ? 33554441 : 16777225,
                               v34,
                               0,
                               a2,
                               a3 & 0xFFFFFFCF,
                               v11,
                               0);
          }
          catch ( CX_MemoryException )
          {
            v32 = GetMemLogObject();
            CMemoryLog::Write(v32, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                827,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749894LL);
            }
            v14 = -2147217402;
            goto LABEL_59;
          }
          v13 = ClassEnumAsync;
          if ( ClassEnumAsync < 0 )
          {
            v19 = GetMemLogObject();
            CMemoryLog::Write(v19, ClassEnumAsync);
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_27;
            }
            v30 = 828;
            v31 = (unsigned int)ClassEnumAsync;
          }
          else
          {
            if ( (a3 & 0x10) == 0 )
            {
              (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, int *))(*(_QWORD *)v12 + 104LL))(
                v12,
                0,
                0xFFFFFFFFLL,
                &ClassEnumAsync);
              v13 = ClassEnumAsync;
            }
            if ( v13 < 0 )
              goto LABEL_28;
            v34 = 0;
            v14 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct _IWmiFinalizer **))(*(_QWORD *)v12 + 88LL))(
                    v12,
                    a3,
                    &IID_IEnumWbemClassObject,
                    &v34);
            if ( (v14 & 0x80000000) != 0 )
            {
LABEL_59:
              CReleaseMe::release((CReleaseMe *)&v35);
              return v14;
            }
            v15 = v34;
            v36 = v34;
            v16 = v34;
            *v10 = (struct IEnumWbemClassObject *)v34;
            (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v16 + 8LL))(v16);
            if ( v15 )
              (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v15 + 16LL))(v15);
            v36 = 0;
            v14 = ClassEnumAsync;
            if ( ClassEnumAsync < 0 )
            {
LABEL_28:
              v20 = GetMemLogObject();
              CMemoryLog::Write(v20, ClassEnumAsync);
              v14 = ClassEnumAsync;
            }
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
LABEL_19:
              if ( v12 )
                (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v12 + 16LL))(v12);
              v35 = 0;
              return v14;
            }
            v30 = 829;
            v31 = v14;
          }
          WPP_SF_d(*((_QWORD *)v17 + 2), v30, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v31);
LABEL_27:
          v14 = ClassEnumAsync;
          goto LABEL_19;
        }
        v29 = GetMemLogObject();
        CMemoryLog::Write(v29, ClassEnumAsync);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)ClassEnumAsync;
        }
        v23 = 826;
        goto LABEL_51;
      }
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, -2147217400);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v27 = 825;
    }
    WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  v24 = GetMemLogObject();
  CMemoryLog::Write(v24, ClassEnumAsync);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)ClassEnumAsync;
  }
  v23 = 822;
LABEL_51:
  WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)ClassEnumAsync);
  return (unsigned int)ClassEnumAsync;
}

```

## disassembly

```asm
0x180047f00  mov     rax, rsp
0x180047f03  mov     [rax+8], rbx
0x180047f07  mov     [rax+18h], rsi
0x180047f0b  mov     [rax+20h], r9
0x180047f0f  mov     [rax+10h], rdx
0x180047f13  push    rdi
0x180047f14  push    r12
0x180047f16  push    r13
0x180047f18  push    r14
0x180047f1a  push    r15
0x180047f1c  sub     rsp, 60h
0x180047f20  mov     r12d, r8d
0x180047f23  mov     rbx, rdx
0x180047f26  mov     r15, rcx
0x180047f29  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x180047f2e  mov     [rsp+88h+var_48], eax
0x180047f32  test    eax, eax
0x180047f34  js      loc_18004819A
0x180047f3a  lea     rdx, [rsp+88h+arg_18]; struct IWbemContext **
0x180047f42  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x180047f47  mov     [rsp+88h+var_48], eax
0x180047f4b  test    eax, eax
0x180047f4d  js      loc_1800481E2
0x180047f53  lea     rdi, WPP_GLOBAL_Control
0x180047f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f61  cmp     rcx, rdi
0x180047f64  jnz     loc_18004810A
0x180047f6a  mov     r14, [rsp+88h+arg_20]
0x180047f72  test    r12d, 0FFFDFFCEh
0x180047f79  jnz     loc_18004822A
0x180047f7f  test    r14, r14
0x180047f82  jz      loc_18004825D
0x180047f88  mov     qword ptr [r14], 0
0x180047f8f  mov     [rsp+88h+var_40], 0
0x180047f98  lea     r8, [rsp+88h+var_40]; struct _IWmiFinalizer **
0x180047f9d  mov     r13, [rsp+88h+arg_18]
0x180047fa5  mov     rdx, r13; struct IWbemContext *
0x180047fa8  mov     rcx, r15; this
0x180047fab  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x180047fb0  mov     [rsp+88h+var_48], eax
0x180047fb4  test    eax, eax
0x180047fb6  js      loc_1800482AE
0x180047fbc  mov     rsi, [rsp+88h+var_40]
0x180047fc1  mov     [rsp+88h+var_38], rsi
0x180047fc6  mov     ebx, r12d
0x180047fc9  and     ebx, 10h
0x180047fcc  mov     eax, ebx
0x180047fce  neg     eax
0x180047fd0  sbb     edx, edx
0x180047fd2  and     edx, 1000000h
0x180047fd8  add     edx, 1000009h; unsigned int
0x180047fde  mov     eax, r12d
0x180047fe1  and     eax, 0FFFFFFCFh
0x180047fe4  mov     [rsp+88h+var_50], 0; struct IWbemObjectSink *
0x180047fed  mov     [rsp+88h+var_58], r13; struct IWbemContext *
0x180047ff2  mov     [rsp+88h+var_60], eax; int
0x180047ff6  mov     rax, [rsp+88h+arg_8]
0x180047ffe  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180048003  xor     r9d, r9d; struct _IWmiCoreHandle *
0x180048006  mov     r8, rsi; struct _IWmiFinalizer *
0x180048009  mov     rcx, r15; this
0x18004800c  call    ?_CreateClassEnumAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_CreateClassEnumAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x180048011  mov     [rsp+88h+var_48], eax
0x180048015  mov     eax, [rsp+88h+var_48]
0x180048019  xor     r15d, r15d
0x18004801c  test    eax, eax
0x18004801e  js      loc_180048151
0x180048024  test    ebx, ebx
0x180048026  jnz     short loc_180048046
0x180048028  mov     rax, [rsi]
0x18004802b  lea     r9, [rsp+88h+var_48]
0x180048030  or      r8d, 0FFFFFFFFh
0x180048034  xor     edx, edx
0x180048036  mov     rcx, rsi
0x180048039  mov     rax, [rax+68h]
0x18004803d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048042  mov     eax, [rsp+88h+var_48]
0x180048046  test    eax, eax
0x180048048  js      loc_18004817E
0x18004804e  mov     [rsp+88h+var_40], r15
0x180048053  mov     rax, [rsi]
0x180048056  lea     r9, [rsp+88h+var_40]
0x18004805b  lea     r8, IID_IEnumWbemClassObject
0x180048062  mov     edx, r12d
0x180048065  mov     rcx, rsi
0x180048068  mov     rax, [rax+58h]
0x18004806c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048071  mov     ebx, eax
0x180048073  test    eax, eax
0x180048075  js      loc_180048348
0x18004807b  mov     rbx, [rsp+88h+var_40]
0x180048080  mov     [rsp+88h+var_30], rbx
0x180048085  mov     rcx, [rsp+88h+var_40]
0x18004808a  mov     [r14], rcx
0x18004808d  mov     rax, [rcx]
0x180048090  mov     rax, [rax+8]
0x180048094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048099  nop
0x18004809a  test    rbx, rbx
0x18004809d  jz      short loc_1800480AE
0x18004809f  mov     rax, [rbx]
0x1800480a2  mov     rcx, rbx
0x1800480a5  mov     rax, [rax+10h]
0x1800480a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480ae  mov     [rsp+88h+var_30], r15
0x1800480b3  mov     ebx, [rsp+88h+var_48]
0x1800480b7  test    ebx, ebx
0x1800480b9  js      loc_18004817E
0x1800480bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800480c6  cmp     rcx, rdi
0x1800480c9  jz      short loc_1800480D5
0x1800480cb  test    byte ptr [rcx+1Ch], 1
0x1800480cf  jnz     loc_18004831C
0x1800480d5  test    rsi, rsi
0x1800480d8  jz      short loc_1800480E9
0x1800480da  mov     rax, [rsi]
0x1800480dd  mov     rcx, rsi
0x1800480e0  mov     rax, [rax+10h]
0x1800480e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480e9  mov     [rsp+88h+var_38], r15
0x1800480ee  mov     eax, ebx
0x1800480f0  lea     r11, [rsp+88h+var_28]
0x1800480f5  mov     rbx, [r11+30h]
0x1800480f9  mov     rsi, [r11+40h]
0x1800480fd  mov     rsp, r11
0x180048100  pop     r15
0x180048102  pop     r14
0x180048104  pop     r13
0x180048106  pop     r12
0x180048108  pop     rdi
0x180048109  retn
0x18004810a  test    byte ptr [rcx+1Ch], 1
0x18004810e  jz      loc_180047F6A
0x180048114  cmp     byte ptr [rcx+19h], 5
0x180048118  jb      loc_180047F6A
0x18004811e  mov     edx, 337h
0x180048123  mov     eax, [r15+130h]
0x18004812a  mov     dword ptr [rsp+88h+var_58], eax
0x18004812e  mov     r14, [rsp+88h+arg_20]
0x180048136  mov     qword ptr [rsp+88h+var_60], r14
0x18004813b  mov     dword ptr [rsp+88h+var_68], r12d
0x180048140  mov     r9, rbx
0x180048143  mov     rcx, [rcx+10h]
0x180048147  call    WPP_SF_Sdql
0x18004814c  jmp     loc_180047F72
0x180048151  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048157  nop
0x180048158  mov     edx, [rsp+88h+var_48]
0x18004815c  mov     rcx, rax
0x18004815f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048165  mov     rcx, cs:WPP_GLOBAL_Control
0x18004816c  cmp     rcx, rdi
0x18004816f  jnz     loc_1800482FC
0x180048175  mov     ebx, [rsp+88h+var_48]
0x180048179  jmp     loc_1800480D5
0x18004817e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048184  mov     edx, [rsp+88h+var_48]
0x180048188  mov     rcx, rax
0x18004818b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048191  mov     ebx, [rsp+88h+var_48]
0x180048195  jmp     loc_1800480BF
0x18004819a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800481a0  mov     edx, [rsp+88h+var_48]
0x1800481a4  mov     rcx, rax
0x1800481a7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800481ad  lea     rdi, WPP_GLOBAL_Control
0x1800481b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800481bb  cmp     rcx, rdi
0x1800481be  jz      loc_1800482F3
0x1800481c4  test    byte ptr [rcx+1Ch], 1
0x1800481c8  jz      loc_1800482F3
0x1800481ce  cmp     byte ptr [rcx+19h], 2
0x1800481d2  jb      loc_1800482F3
0x1800481d8  mov     edx, 335h
0x1800481dd  jmp     loc_1800482DE
0x1800481e2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800481e8  mov     edx, [rsp+88h+var_48]
0x1800481ec  mov     rcx, rax
0x1800481ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800481f5  lea     rdi, WPP_GLOBAL_Control
0x1800481fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180048203  cmp     rcx, rdi
0x180048206  jz      loc_1800482F3
0x18004820c  test    byte ptr [rcx+1Ch], 1
0x180048210  jz      loc_1800482F3
0x180048216  cmp     byte ptr [rcx+19h], 2
0x18004821a  jb      loc_1800482F3
0x180048220  mov     edx, 336h
0x180048225  jmp     loc_1800482DE
0x18004822a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048230  mov     edx, 80041008h
0x180048235  mov     rcx, rax
0x180048238  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004823e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048245  cmp     rcx, rdi
0x180048248  jz      short loc_1800482A4
0x18004824a  test    byte ptr [rcx+1Ch], 1
0x18004824e  jz      short loc_1800482A4
0x180048250  cmp     byte ptr [rcx+19h], 2
0x180048254  jb      short loc_1800482A4
0x180048256  mov     edx, 338h
0x18004825b  jmp     short loc_18004828E
0x18004825d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048263  mov     edx, 80041008h
0x180048268  mov     rcx, rax
0x18004826b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048271  mov     rcx, cs:WPP_GLOBAL_Control
0x180048278  cmp     rcx, rdi
0x18004827b  jz      short loc_1800482A4
0x18004827d  test    byte ptr [rcx+1Ch], 1
0x180048281  jz      short loc_1800482A4
0x180048283  cmp     byte ptr [rcx+19h], 2
0x180048287  jb      short loc_1800482A4
0x180048289  mov     edx, 339h
0x18004828e  mov     r9d, 80041008h
0x180048294  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004829b  mov     rcx, [rcx+10h]
0x18004829f  call    WPP_SF_d
0x1800482a4  mov     eax, 80041008h
0x1800482a9  jmp     loc_1800480F0
0x1800482ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800482b4  mov     edx, [rsp+88h+var_48]
0x1800482b8  mov     rcx, rax
0x1800482bb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800482c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482c8  cmp     rcx, rdi
0x1800482cb  jz      short loc_1800482F3
0x1800482cd  test    byte ptr [rcx+1Ch], 1
0x1800482d1  jz      short loc_1800482F3
0x1800482d3  cmp     byte ptr [rcx+19h], 2
0x1800482d7  jb      short loc_1800482F3
0x1800482d9  mov     edx, 33Ah
0x1800482de  mov     r9d, [rsp+88h+var_48]
0x1800482e3  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800482ea  mov     rcx, [rcx+10h]
0x1800482ee  call    WPP_SF_d
0x1800482f3  mov     eax, [rsp+88h+var_48]
0x1800482f7  jmp     loc_1800480F0
0x1800482fc  test    byte ptr [rcx+1Ch], 1
0x180048300  jz      loc_180048175
0x180048306  cmp     byte ptr [rcx+19h], 2
0x18004830a  jb      loc_180048175
0x180048310  mov     edx, 33Ch
0x180048315  mov     r9d, [rsp+88h+var_48]
0x18004831a  jmp     short loc_18004832E
0x18004831c  cmp     byte ptr [rcx+19h], 2
0x180048320  jb      loc_1800480D5
0x180048326  mov     edx, 33Dh
0x18004832b  mov     r9d, ebx
0x18004832e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180048335  mov     rcx, [rcx+10h]
0x180048339  call    WPP_SF_d
0x18004833e  jmp     loc_180048175
0x180048343  mov     ebx, 80041006h
0x180048348  lea     rcx, [rsp+88h+var_38]; this
0x18004834d  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180048352  jmp     loc_1800480EE
```
