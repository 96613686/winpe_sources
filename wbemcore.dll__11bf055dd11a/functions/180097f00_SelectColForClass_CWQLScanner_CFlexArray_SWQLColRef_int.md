# SelectColForClass(CWQLScanner &,CFlexArray *,SWQLColRef *,int &)

- ea: `0x180097f00`
- end: `0x1800982da`
- name: `?SelectColForClass@@YAJAEAVCWQLScanner@@PEAVCFlexArray@@PEAUSWQLColRef@@AEAH@Z`
- size: `986`
- prototype: `int(struct CWQLScanner *, struct CFlexArray *, struct SWQLColRef *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009703c`

## callees

- `0x18000b140`
- `0x18000ebd0`
- `0x180097f00`
- `0x1800982e0`
- `0x1800983a0`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180097fa8`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180097fa8`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180097ff7`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800981e1`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180097ff7`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800981e1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800980ce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18009821f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800980ce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18009821f`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180097f97`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180098148`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800981d0`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180097f97`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180098148`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800981d0`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180097f84`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180098135`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800981bb`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180097f84`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180098135`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800981bb`
- `wbemcomn!GetMemLogObject` at `0x180097f22`
- `wbemcomn!GetMemLogObject` at `0x18009801c`
- `wbemcomn!GetMemLogObject` at `0x180098074`
- `wbemcomn!GetMemLogObject` at `0x1800980d9`
- `wbemcomn!GetMemLogObject` at `0x180098161`
- `wbemcomn!GetMemLogObject` at `0x18009822a`
- `wbemcomn!GetMemLogObject` at `0x180098289`
- `wbemcomn!GetMemLogObject` at `0x180097f22`
- `wbemcomn!GetMemLogObject` at `0x18009801c`
- `wbemcomn!GetMemLogObject` at `0x180098074`
- `wbemcomn!GetMemLogObject` at `0x1800980d9`
- `wbemcomn!GetMemLogObject` at `0x180098161`
- `wbemcomn!GetMemLogObject` at `0x18009822a`
- `wbemcomn!GetMemLogObject` at `0x180098289`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180097f32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009802c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180098084`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800980e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180098171`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009823a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180098299`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180097f32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009802c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180098084`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800980e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180098171`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009823a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180098299`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SelectColForClass(struct CWQLScanner *a1, struct CFlexArray *a2, struct SWQLColRef *a3, int *a4)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v8; // ebx
  CClientCnt *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int i; // ebp
  SelectedClass *v14; // r14
  const unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rbx
  CMemoryLog *v18; // rax
  CClientCnt *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  int k; // ebx
  SelectedClass *v25; // rax
  CMemoryLog *v26; // rax
  int v27; // ebp
  int j; // r14d
  SelectedClass *v29; // r12
  __int64 v30; // rbx
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  _BYTE v33[104]; // [rsp+20h] [rbp-68h] BYREF

  if ( !a3 )
  {
    MemLogObject = GetMemLogObject();
    v8 = -2147217407;
    CMemoryLog::Write(MemLogObject, -2147217407);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 20;
      v11 = 2147749889LL;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_62b2ebb011ba3ee846cac58fb40169b9_Traceguids, v11);
    }
    return v8;
  }
  if ( *((_QWORD *)a3 + 1) )
  {
    for ( i = 0; i < CFlexArray::Size(a2); ++i )
    {
      v14 = (SelectedClass *)CFlexArray::GetAt(a2, i);
      v15 = (const unsigned __int16 *)*((_QWORD *)a3 + 1);
      v16 = (const unsigned __int16 *)WString::operator unsigned short *((char *)v14 + 8);
      if ( !(unsigned int)wbem_wcsicmp(v16, v15) )
      {
        if ( **(_WORD **)a3 == 42 && !*(_WORD *)(*(_QWORD *)a3 + 2LL) )
        {
          SelectedClass::SetAll(v14, a4);
          return 0;
        }
        v17 = *(_QWORD *)v14;
        CVar::CVar((CVar *)v33);
        if ( (*(int (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v17 + 776LL))(v17, *(_QWORD *)a3, v33) >= 0 )
        {
          if ( (unsigned int)SelectedClass::SetNamed(v14, *(unsigned __int16 **)a3, a4) )
          {
            v22 = GetMemLogObject();
            v8 = -2147217402;
            CMemoryLog::Write(v22, -2147217402);
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v20 = 22;
              v21 = 2147749894LL;
              goto LABEL_27;
            }
          }
          else
          {
            v8 = 0;
          }
        }
        else
        {
          v18 = GetMemLogObject();
          v8 = -2147217385;
          CMemoryLog::Write(v18, -2147217385);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v20 = 21;
            v21 = 2147749911LL;
LABEL_27:
            WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_62b2ebb011ba3ee846cac58fb40169b9_Traceguids, v21);
            goto LABEL_29;
          }
        }
        goto LABEL_29;
      }
    }
    v23 = GetMemLogObject();
    v8 = -2147217385;
    CMemoryLog::Write(v23, -2147217385);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 23;
      goto LABEL_59;
    }
    return v8;
  }
  if ( (*((_BYTE *)a3 + 20) & 4) == 0 )
  {
    v27 = 0;
    for ( j = 0; j < CFlexArray::Size(a2); ++j )
    {
      v29 = (SelectedClass *)CFlexArray::GetAt(a2, j);
      v30 = *(_QWORD *)v29;
      CVar::CVar((CVar *)v33);
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v30 + 776LL))(v30, *(_QWORD *)a3, v33) )
      {
        if ( (unsigned int)SelectedClass::SetNamed(v29, *(unsigned __int16 **)a3, a4) )
        {
          v31 = GetMemLogObject();
          v8 = -2147217402;
          CMemoryLog::Write(v31, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_62b2ebb011ba3ee846cac58fb40169b9_Traceguids,
              2147749894LL);
          }
LABEL_29:
          CVar::~CVar((CVar *)v33);
          return v8;
        }
        ++v27;
      }
      CVar::~CVar((CVar *)v33);
    }
    if ( v27 == 1 )
      return 0;
    v32 = GetMemLogObject();
    v8 = -2147217385;
    CMemoryLog::Write(v32, -2147217385);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 26;
LABEL_59:
      v11 = 2147749911LL;
      goto LABEL_6;
    }
    return v8;
  }
  for ( k = 0; k < CFlexArray::Size(a2); ++k )
  {
    v25 = (SelectedClass *)CFlexArray::GetAt(a2, k);
    if ( (unsigned int)SelectedClass::SetAll(v25, a4) )
    {
      v26 = GetMemLogObject();
      v8 = -2147217402;
      CMemoryLog::Write(v26, -2147217402);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 24;
        v11 = 2147749894LL;
        goto LABEL_6;
      }
      return v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180097f00  push    rbx
0x180097f02  push    rbp
0x180097f03  push    rsi
0x180097f04  push    rdi
0x180097f05  push    r12
0x180097f07  push    r13
0x180097f09  push    r14
0x180097f0b  push    r15
0x180097f0d  sub     rsp, 48h
0x180097f11  mov     r15, r9
0x180097f14  mov     rdi, r8
0x180097f17  mov     rsi, rdx
0x180097f1a  xor     r13d, r13d
0x180097f1d  test    r8, r8
0x180097f20  jnz     short loc_180097F74
0x180097f22  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180097f28  mov     ebx, 80041001h
0x180097f2d  mov     edx, ebx
0x180097f2f  mov     rcx, rax
0x180097f32  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180097f38  lea     rax, WPP_GLOBAL_Control
0x180097f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180097f46  cmp     rcx, rax
0x180097f49  jz      short loc_180097F70
0x180097f4b  test    byte ptr [rcx+1Ch], 1
0x180097f4f  jz      short loc_180097F70
0x180097f51  cmp     byte ptr [rcx+19h], 2
0x180097f55  jb      short loc_180097F70
0x180097f57  lea     edx, [rdi+14h]
0x180097f5a  mov     r9d, 80041001h
0x180097f60  lea     r8, WPP_62b2ebb011ba3ee846cac58fb40169b9_Traceguids
0x180097f67  mov     rcx, [rcx+10h]
0x180097f6b  call    WPP_SF_d
0x180097f70  mov     eax, ebx
0x180097f72  jmp     short loc_180097FDE
0x180097f74  cmp     [r8+8], r13
0x180097f78  jz      loc_180098124
0x180097f7e  mov     ebp, r13d
0x180097f81  mov     rcx, rsi
0x180097f84  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180097f8a  cmp     ebp, eax
0x180097f8c  jge     loc_1800980D9
0x180097f92  mov     edx, ebp
0x180097f94  mov     rcx, rsi
0x180097f97  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180097f9d  mov     r14, rax
0x180097fa0  mov     rbx, [rdi+8]
0x180097fa4  lea     rcx, [rax+8]
0x180097fa8  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180097fae  mov     rdx, rbx; unsigned __int16 *
0x180097fb1  mov     rcx, rax; unsigned __int16 *
0x180097fb4  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180097fb9  test    eax, eax
0x180097fbb  jz      short loc_180097FC1
0x180097fbd  inc     ebp
0x180097fbf  jmp     short loc_180097F81
0x180097fc1  mov     rax, [rdi]
0x180097fc4  cmp     word ptr [rax], 2Ah ; '*'
0x180097fc8  jnz     short loc_180097FEF
0x180097fca  cmp     [rax+2], r13w
0x180097fcf  jnz     short loc_180097FEF
0x180097fd1  mov     rdx, r15; int *
0x180097fd4  mov     rcx, r14; this
0x180097fd7  call    ?SetAll@SelectedClass@@QEAAHAEAH@Z; SelectedClass::SetAll(int &)
0x180097fdc  xor     eax, eax
0x180097fde  add     rsp, 48h
0x180097fe2  pop     r15
0x180097fe4  pop     r14
0x180097fe6  pop     r13
0x180097fe8  pop     r12
0x180097fea  pop     rdi
0x180097feb  pop     rsi
0x180097fec  pop     rbp
0x180097fed  pop     rbx
0x180097fee  retn
0x180097fef  mov     rbx, [r14]
0x180097ff2  lea     rcx, [rsp+88h+var_68]
0x180097ff7  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180097ffd  nop
0x180097ffe  mov     rax, [rbx]
0x180098001  lea     r8, [rsp+88h+var_68]
0x180098006  mov     rdx, [rdi]
0x180098009  mov     rcx, rbx
0x18009800c  mov     rax, [rax+308h]
0x180098013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098018  test    eax, eax
0x18009801a  jns     short loc_180098062
0x18009801c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180098022  mov     ebx, 80041017h
0x180098027  mov     edx, ebx
0x180098029  mov     rcx, rax
0x18009802c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180098032  lea     rax, WPP_GLOBAL_Control
0x180098039  mov     rcx, cs:WPP_GLOBAL_Control
0x180098040  cmp     rcx, rax
0x180098043  jz      loc_1800980C9
0x180098049  test    byte ptr [rcx+1Ch], 1
0x18009804d  jz      short loc_1800980C9
0x18009804f  cmp     byte ptr [rcx+19h], 2
0x180098053  jb      short loc_1800980C9
0x180098055  mov     edx, 15h
0x18009805a  mov     r9d, 80041017h
0x180098060  jmp     short loc_1800980B4
0x180098062  mov     r8, r15; int *
0x180098065  mov     rdx, [rdi]; unsigned __int16 *
0x180098068  mov     rcx, r14; this
0x18009806b  call    ?SetNamed@SelectedClass@@QEAAHPEAGAEAH@Z; SelectedClass::SetNamed(ushort *,int &)
0x180098070  test    eax, eax
0x180098072  jz      short loc_1800980C6
0x180098074  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009807a  mov     ebx, 80041006h
0x18009807f  mov     edx, ebx
0x180098081  mov     rcx, rax
0x180098084  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009808a  lea     rax, WPP_GLOBAL_Control
0x180098091  mov     rcx, cs:WPP_GLOBAL_Control
0x180098098  cmp     rcx, rax
0x18009809b  jz      short loc_1800980C9
0x18009809d  test    byte ptr [rcx+1Ch], 1
0x1800980a1  jz      short loc_1800980C9
0x1800980a3  cmp     byte ptr [rcx+19h], 2
0x1800980a7  jb      short loc_1800980C9
0x1800980a9  mov     edx, 16h
0x1800980ae  mov     r9d, 80041006h
0x1800980b4  lea     r8, WPP_62b2ebb011ba3ee846cac58fb40169b9_Traceguids
0x1800980bb  mov     rcx, [rcx+10h]
0x1800980bf  call    WPP_SF_d
0x1800980c4  jmp     short loc_1800980C9
0x1800980c6  mov     ebx, r13d
0x1800980c9  lea     rcx, [rsp+88h+var_68]
0x1800980ce  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800980d4  jmp     loc_180097F70
0x1800980d9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800980df  mov     ebx, 80041017h
0x1800980e4  mov     edx, ebx
0x1800980e6  mov     rcx, rax
0x1800980e9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800980ef  lea     rax, WPP_GLOBAL_Control
0x1800980f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800980fd  cmp     rcx, rax
0x180098100  jz      loc_180097F70
0x180098106  test    byte ptr [rcx+1Ch], 1
0x18009810a  jz      loc_180097F70
0x180098110  cmp     byte ptr [rcx+19h], 2
0x180098114  jb      loc_180097F70
0x18009811a  mov     edx, 17h
0x18009811f  jmp     loc_1800982CF
0x180098124  test    byte ptr [r8+14h], 4
0x180098129  jz      loc_1800981B2
0x18009812f  mov     ebx, r13d
0x180098132  mov     rcx, rsi
0x180098135  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18009813b  cmp     ebx, eax
0x18009813d  jge     loc_180097FDC
0x180098143  mov     edx, ebx
0x180098145  mov     rcx, rsi
0x180098148  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18009814e  mov     rdx, r15; int *
0x180098151  mov     rcx, rax; this
0x180098154  call    ?SetAll@SelectedClass@@QEAAHAEAH@Z; SelectedClass::SetAll(int &)
0x180098159  test    eax, eax
0x18009815b  jnz     short loc_180098161
0x18009815d  inc     ebx
0x18009815f  jmp     short loc_180098132
0x180098161  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180098167  mov     ebx, 80041006h
0x18009816c  mov     edx, ebx
0x18009816e  mov     rcx, rax
0x180098171  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180098177  lea     rax, WPP_GLOBAL_Control
0x18009817e  mov     rcx, cs:WPP_GLOBAL_Control
0x180098185  cmp     rcx, rax
0x180098188  jz      loc_180097F70
0x18009818e  test    byte ptr [rcx+1Ch], 1
0x180098192  jz      loc_180097F70
0x180098198  cmp     byte ptr [rcx+19h], 2
0x18009819c  jb      loc_180097F70
0x1800981a2  mov     edx, 18h
0x1800981a7  mov     r9d, 80041006h
0x1800981ad  jmp     loc_180097F60
0x1800981b2  mov     ebp, r13d
0x1800981b5  mov     r14d, r13d
0x1800981b8  mov     rcx, rsi
0x1800981bb  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800981c1  cmp     r14d, eax
0x1800981c4  jge     loc_180098280
0x1800981ca  mov     edx, r14d
0x1800981cd  mov     rcx, rsi
0x1800981d0  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800981d6  mov     r12, rax
0x1800981d9  mov     rbx, [rax]
0x1800981dc  lea     rcx, [rsp+88h+var_68]
0x1800981e1  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800981e7  nop
0x1800981e8  mov     rdx, [rbx]
0x1800981eb  mov     rax, [rdx+308h]
0x1800981f2  lea     r8, [rsp+88h+var_68]
0x1800981f7  mov     rdx, [rdi]
0x1800981fa  mov     rcx, rbx
0x1800981fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098202  test    eax, eax
0x180098204  jnz     short loc_18009821A
0x180098206  mov     r8, r15; int *
0x180098209  mov     rdx, [rdi]; unsigned __int16 *
0x18009820c  mov     rcx, r12; this
0x18009820f  call    ?SetNamed@SelectedClass@@QEAAHPEAGAEAH@Z; SelectedClass::SetNamed(ushort *,int &)
0x180098214  test    eax, eax
0x180098216  jnz     short loc_18009822A
0x180098218  inc     ebp
0x18009821a  lea     rcx, [rsp+88h+var_68]
0x18009821f  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180098225  inc     r14d
0x180098228  jmp     short loc_1800981B8
0x18009822a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180098230  mov     ebx, 80041006h
0x180098235  mov     edx, ebx
0x180098237  mov     rcx, rax
0x18009823a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180098240  lea     rax, WPP_GLOBAL_Control
0x180098247  mov     rcx, cs:WPP_GLOBAL_Control
0x18009824e  cmp     rcx, rax
0x180098251  jz      short loc_18009827B
0x180098253  test    byte ptr [rcx+1Ch], 1
0x180098257  jz      short loc_18009827B
0x180098259  cmp     byte ptr [rcx+19h], 2
0x18009825d  jb      short loc_18009827B
0x18009825f  mov     edx, 19h
0x180098264  mov     r9d, 80041006h
0x18009826a  lea     r8, WPP_62b2ebb011ba3ee846cac58fb40169b9_Traceguids
0x180098271  mov     rcx, [rcx+10h]
0x180098275  call    WPP_SF_d
0x18009827a  nop
0x18009827b  jmp     loc_1800980C9
0x180098280  cmp     ebp, 1
0x180098283  jz      loc_180097FDC
0x180098289  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009828f  mov     ebx, 80041017h
0x180098294  mov     edx, ebx
0x180098296  mov     rcx, rax
0x180098299  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009829f  lea     rax, WPP_GLOBAL_Control
0x1800982a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800982ad  cmp     rcx, rax
0x1800982b0  jz      loc_180097F70
0x1800982b6  test    byte ptr [rcx+1Ch], 1
0x1800982ba  jz      loc_180097F70
0x1800982c0  cmp     byte ptr [rcx+19h], 2
0x1800982c4  jb      loc_180097F70
0x1800982ca  mov     edx, 1Ah
0x1800982cf  mov     r9d, 80041017h
0x1800982d5  jmp     loc_180097F60
```
