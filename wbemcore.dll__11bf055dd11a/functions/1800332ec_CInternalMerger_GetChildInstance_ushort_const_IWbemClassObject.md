# CInternalMerger::GetChildInstance(ushort const *,IWbemClassObject * *)

- ea: `0x1800332ec`
- end: `0x18003375b`
- name: `?GetChildInstance@CInternalMerger@@IEAAJPEBGPEAPEAUIWbemClassObject@@@Z`
- size: `1135`
- prototype: `__int64 __fastcall(CInternalMerger *__hidden this, const unsigned __int16 *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031dc4`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x180031228`
- `0x1800332ec`
- `0x180034110`
- `0x180034e20`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800335ef`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033683`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800335ef`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033683`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033337`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033337`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180033328`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180033328`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800334ba`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800334ba`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x180033355`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x1800333d1`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x180033355`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x1800333d1`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x1800333f8`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x1800334ab`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x1800333f8`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x1800334ab`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x180033403`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x180033403`
- `wbemcomn!GetMemLogObject` at `0x18003339a`
- `wbemcomn!GetMemLogObject` at `0x18003354a`
- `wbemcomn!GetMemLogObject` at `0x1800335fa`
- `wbemcomn!GetMemLogObject` at `0x1800336bc`
- `wbemcomn!GetMemLogObject` at `0x180033716`
- `wbemcomn!GetMemLogObject` at `0x18003339a`
- `wbemcomn!GetMemLogObject` at `0x18003354a`
- `wbemcomn!GetMemLogObject` at `0x1800335fa`
- `wbemcomn!GetMemLogObject` at `0x1800336bc`
- `wbemcomn!GetMemLogObject` at `0x180033716`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800333a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033555`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033605`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800336c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033721`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800333a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033555`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033605`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800336c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033721`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInternalMerger::GetChildInstance(
        CInternalMerger *this,
        const unsigned __int16 *a2,
        struct IWbemClassObject **a3)
{
  __int64 v6; // rbx
  DWORD TickCount; // eax
  int v8; // ebx
  __int64 v9; // rbx
  unsigned int v10; // r14d
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  char v13; // al
  __int64 v14; // rbp
  int v15; // eax
  CClientCnt *v16; // rcx
  struct IWbemClassObject *v18; // rcx
  bool v19; // r15
  __int64 v20; // rax
  CMemoryLog *v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // eax
  bool v24; // al
  void *v25; // rcx
  void *v26; // rcx
  CMemoryLog *v27; // rax
  __int64 v28; // rdx
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  _BYTE v31[16]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v32[56]; // [rsp+40h] [rbp-38h] BYREF
  char v33; // [rsp+80h] [rbp+8h] BYREF
  __int64 v34; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids);
  }
  WString::WString((WString *)&v33, a2);
  v6 = *(_QWORD *)(*((_QWORD *)this + 7) + 24LL);
  TickCount = GetTickCount();
  *((_DWORD *)this + 38) = TickCount;
  *(_DWORD *)(v6 + 64) = TickCount;
  CCheckedInCritSec::CCheckedInCritSec((CCheckedInCritSec *)v31, (CInternalMerger *)((char *)this + 176));
  v8 = *((_DWORD *)this + 28);
  if ( v8 >= 0 )
  {
    std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::find(
      (char *)this + 64,
      &v34,
      &v33);
    v9 = v34;
    if ( v34 == *((_QWORD *)this + 8) )
    {
      v10 = 0;
      v11 = 0;
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids);
      }
    }
    else
    {
      v18 = *(struct IWbemClassObject **)(v34 + 40);
      *a3 = v18;
      ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->AddRef)(v18);
      v10 = -*(_DWORD *)(v9 + 48);
      v19 = 0;
      if ( *((_DWORD *)this + 20) )
        v19 = v9 == *((_QWORD *)this + 29);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 + 40) + 16LL))(*(_QWORD *)(v9 + 40));
      v20 = *(_QWORD *)std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::erase(
                         (char *)this + 64,
                         &v34,
                         v9);
      if ( v19 )
        *((_QWORD *)this + 29) = v20;
      v11 = -1;
    }
    *((_DWORD *)this + 54) += v10;
    *((_DWORD *)this + 34) += v11;
    CCheckedInCritSec::CCheckedInCritSec((CCheckedInCritSec *)v32, (CInternalMerger *)((char *)this + 176));
    v13 = *((_BYTE *)this + 157);
    if ( *((_BYTE *)this + 156) )
    {
      if ( !v13 )
      {
        v22 = *((_DWORD *)this + 34);
        v23 = *((_DWORD *)this + 35);
        if ( v23 <= v22 )
        {
          v24 = 1;
          goto LABEL_39;
        }
LABEL_38:
        v24 = v23 - v22 < *((_DWORD *)this + 41);
LABEL_39:
        if ( !v24 )
          goto LABEL_7;
      }
    }
    else
    {
      if ( !v13 )
        goto LABEL_7;
      v22 = *((_DWORD *)this + 35);
      v23 = *((_DWORD *)this + 34);
      if ( v23 > v22 )
        goto LABEL_38;
    }
    *((_WORD *)this + 78) = 0;
    v25 = (void *)*((_QWORD *)this + 15);
    if ( v25 )
      SetEvent(v25);
    v26 = (void *)*((_QWORD *)this + 16);
    if ( v26 )
      SetEvent(v26);
LABEL_7:
    CCheckedInCritSec::~CCheckedInCritSec((CCheckedInCritSec *)v32);
    CCheckedInCritSec::Leave((CCheckedInCritSec *)v31);
    v14 = *(_QWORD *)(*((_QWORD *)this + 7) + 24LL);
    v8 = 0;
    if ( *(_QWORD *)(v14 + 40)
      && (v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v14 + 48) + 152LL))(
                  *(_QWORD *)(v14 + 48),
                  0,
                  v10),
          v8 = v15,
          v15 < 0)
      && (unsigned int)(v15 + 2147209215) > 1
      || (_InterlockedAdd((volatile signed __int32 *)(v14 + 328), v10), v8 < 0) )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, v8);
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids,
        (unsigned int)v8);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v8 == 266240 || v8 == -2147209215 )
    {
      v8 = 0;
    }
    else if ( v8 < 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v8);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v16 != (CClientCnt *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)v16 + 2), 62, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids, (unsigned int)v8);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v8 < 0 )
    {
      CWmiMerger::Cancel(*(CWmiMerger **)(*((_QWORD *)this + 7) + 24LL), v8);
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, v8);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v16 != (CClientCnt *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 2u )
    {
      v28 = 52;
      goto LABEL_57;
    }
    goto LABEL_23;
  }
  v27 = GetMemLogObject();
  CMemoryLog::Write(v27, v8);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = 50;
LABEL_57:
    WPP_SF_d(*((_QWORD *)v16 + 2), v28, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids, (unsigned int)v8);
  }
LABEL_23:
  CCheckedInCritSec::~CCheckedInCritSec((CCheckedInCritSec *)v31);
  WString::~WString((WString *)&v33);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800332ec  mov     [rsp+arg_8], rbx
0x1800332f1  push    rbp
0x1800332f2  push    rdi
0x1800332f3  push    r12
0x1800332f5  push    r14
0x1800332f7  push    r15
0x1800332f9  sub     rsp, 50h
0x1800332fd  mov     r14, r8
0x180033300  mov     rbx, rdx
0x180033303  mov     rdi, rcx
0x180033306  lea     r15, WPP_GLOBAL_Control
0x18003330d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033314  cmp     rcx, r15
0x180033317  jnz     loc_180033560
0x18003331d  mov     rdx, rbx
0x180033320  lea     rcx, [rsp+78h+arg_0]
0x180033328  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x18003332e  nop
0x18003332f  mov     rax, [rdi+38h]
0x180033333  mov     rbx, [rax+18h]
0x180033337  call    cs:__imp_GetTickCount
0x18003333d  mov     [rdi+98h], eax
0x180033343  mov     [rbx+40h], eax
0x180033346  lea     r12, [rdi+0B0h]
0x18003334d  mov     rdx, r12
0x180033350  lea     rcx, [rsp+78h+var_48]
0x180033355  call    cs:__imp_??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z; CCheckedInCritSec::CCheckedInCritSec(CCritSec *)
0x18003335b  nop
0x18003335c  mov     ebx, [rdi+70h]
0x18003335f  test    ebx, ebx
0x180033361  js      loc_1800335FA
0x180033367  lea     rbp, [rdi+40h]
0x18003336b  lea     r8, [rsp+78h+arg_0]
0x180033373  lea     rdx, [rsp+78h+arg_18]
0x18003337b  mov     rcx, rbp
0x18003337e  call    ?find@?$_Tree@V?$_Tmap_traits@VWString@@UCInternalMergerRecord@@VWSiless@@VCKeyToInstRecordAlloc@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVWString@@UCInternalMergerRecord@@@std@@@std@@@std@@@2@AEBVWString@@@Z; std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::find(WString const &)
0x180033383  mov     rbx, [rsp+78h+arg_18]
0x18003338b  cmp     rbx, [rbp+0]
0x18003338f  jnz     loc_1800334D7
0x180033395  xor     r14d, r14d
0x180033398  xor     ebx, ebx
0x18003339a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800333a0  or      edx, 0FFFFFFFFh
0x1800333a3  mov     rcx, rax
0x1800333a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800333ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333b3  cmp     rcx, r15
0x1800333b6  jnz     loc_180033655
0x1800333bc  add     [rdi+0D8h], r14d
0x1800333c3  add     [rdi+88h], ebx
0x1800333c9  mov     rdx, r12
0x1800333cc  lea     rcx, [rsp+78h+var_38]
0x1800333d1  call    cs:__imp_??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z; CCheckedInCritSec::CCheckedInCritSec(CCritSec *)
0x1800333d7  nop
0x1800333d8  mov     al, [rdi+9Dh]
0x1800333de  cmp     byte ptr [rdi+9Ch], 0
0x1800333e5  jnz     loc_18003358E
0x1800333eb  test    al, al
0x1800333ed  jnz     loc_1800335A6
0x1800333f3  lea     rcx, [rsp+78h+var_38]
0x1800333f8  call    cs:__imp_??1CCheckedInCritSec@@QEAA@XZ; CCheckedInCritSec::~CCheckedInCritSec(void)
0x1800333fe  lea     rcx, [rsp+78h+var_48]
0x180033403  call    cs:__imp_?Leave@CCheckedInCritSec@@QEAAXXZ; CCheckedInCritSec::Leave(void)
0x180033409  mov     rax, [rdi+38h]
0x18003340d  mov     rbp, [rax+18h]
0x180033411  xor     ebx, ebx
0x180033413  mov     r9, [rbp+28h]
0x180033417  test    r9, r9
0x18003341a  jz      short loc_18003343E
0x18003341c  mov     rcx, [rbp+30h]
0x180033420  mov     rax, [rcx]
0x180033423  mov     r8d, r14d
0x180033426  xor     edx, edx
0x180033428  mov     rax, [rax+98h]
0x18003342f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033434  mov     ebx, eax
0x180033436  test    eax, eax
0x180033438  js      loc_18003353C
0x18003343e  lock add [rbp+148h], r14d
0x180033446  test    ebx, ebx
0x180033448  js      loc_18003354A
0x18003344e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033455  cmp     rcx, r15
0x180033458  jz      short loc_180033464
0x18003345a  test    byte ptr [rcx+1Ch], 1
0x18003345e  jnz     loc_18003368E
0x180033464  cmp     ebx, 41000h
0x18003346a  jnz     short loc_180033470
0x18003346c  xor     ebx, ebx
0x18003346e  jmp     short loc_180033480
0x180033470  cmp     ebx, 80043001h
0x180033476  jz      short loc_18003346C
0x180033478  test    ebx, ebx
0x18003347a  js      loc_1800336BC
0x180033480  cmp     rcx, r15
0x180033483  jz      short loc_18003348F
0x180033485  test    byte ptr [rcx+1Ch], 1
0x180033489  jnz     loc_1800336D9
0x18003348f  test    ebx, ebx
0x180033491  js      loc_180033707
0x180033497  cmp     rcx, r15
0x18003349a  jz      short loc_1800334A6
0x18003349c  test    byte ptr [rcx+1Ch], 1
0x1800334a0  jnz     loc_180033733
0x1800334a6  lea     rcx, [rsp+78h+var_48]
0x1800334ab  call    cs:__imp_??1CCheckedInCritSec@@QEAA@XZ; CCheckedInCritSec::~CCheckedInCritSec(void)
0x1800334b1  nop
0x1800334b2  lea     rcx, [rsp+78h+arg_0]
0x1800334ba  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x1800334c0  mov     eax, ebx
0x1800334c2  mov     rbx, [rsp+78h+arg_8]
0x1800334ca  add     rsp, 50h
0x1800334ce  pop     r15
0x1800334d0  pop     r14
0x1800334d2  pop     r12
0x1800334d4  pop     rdi
0x1800334d5  pop     rbp
0x1800334d6  retn
0x1800334d7  mov     rcx, [rbx+28h]
0x1800334db  mov     [r14], rcx
0x1800334de  mov     rax, [rcx]
0x1800334e1  mov     rax, [rax+8]
0x1800334e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334ea  mov     r14d, [rbx+30h]
0x1800334ee  neg     r14d
0x1800334f1  xor     r15b, r15b
0x1800334f4  cmp     dword ptr [rdi+50h], 0
0x1800334f8  jnz     loc_180033639
0x1800334fe  mov     rcx, [rbx+28h]
0x180033502  mov     rax, [rcx]
0x180033505  mov     rax, [rax+10h]
0x180033509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003350e  mov     r8, rbx
0x180033511  lea     rdx, [rsp+78h+arg_18]
0x180033519  mov     rcx, rbp
0x18003351c  call    ?erase@?$_Tree@V?$_Tmap_traits@VWString@@UCInternalMergerRecord@@VWSiless@@VCKeyToInstRecordAlloc@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVWString@@UCInternalMergerRecord@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVWString@@UCInternalMergerRecord@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WString const,CInternalMergerRecord>>>>)
0x180033521  mov     rax, [rax]
0x180033524  test    r15b, r15b
0x180033527  jnz     loc_180033649
0x18003352d  or      ebx, 0FFFFFFFFh
0x180033530  lea     r15, WPP_GLOBAL_Control
0x180033537  jmp     loc_1800333BC
0x18003353c  add     eax, 7FFBCFFFh
0x180033541  cmp     eax, 1
0x180033544  jbe     loc_18003343E
0x18003354a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180033550  mov     edx, ebx
0x180033552  mov     rcx, rax
0x180033555  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003355b  jmp     loc_18003344E
0x180033560  test    byte ptr [rcx+1Ch], 1
0x180033564  jz      loc_18003331D
0x18003356a  cmp     byte ptr [rcx+19h], 5
0x18003356e  jb      loc_18003331D
0x180033574  mov     edx, 31h ; '1'
0x180033579  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x180033580  mov     rcx, [rcx+10h]
0x180033584  call    WPP_SF_
0x180033589  jmp     loc_18003331D
0x18003358e  test    al, al
0x180033590  jnz     short loc_1800335C9
0x180033592  mov     ecx, [rdi+88h]
0x180033598  mov     eax, [rdi+8Ch]
0x18003359e  cmp     eax, ecx
0x1800335a0  ja      short loc_1800335B6
0x1800335a2  mov     al, 1
0x1800335a4  jmp     short loc_1800335C1
0x1800335a6  mov     ecx, [rdi+8Ch]
0x1800335ac  mov     eax, [rdi+88h]
0x1800335b2  cmp     eax, ecx
0x1800335b4  jbe     short loc_1800335C9
0x1800335b6  sub     eax, ecx
0x1800335b8  cmp     eax, [rdi+0A4h]
0x1800335be  setb    al
0x1800335c1  test    al, al
0x1800335c3  jz      loc_1800333F3
0x1800335c9  mov     word ptr [rdi+9Ch], 0
0x1800335d2  mov     rcx, [rdi+78h]; hEvent
0x1800335d6  test    rcx, rcx
0x1800335d9  jnz     loc_180033683
0x1800335df  mov     rcx, [rdi+80h]; hEvent
0x1800335e6  test    rcx, rcx
0x1800335e9  jz      loc_1800333F3
0x1800335ef  call    cs:__imp_SetEvent
0x1800335f5  jmp     loc_1800333F3
0x1800335fa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180033600  mov     edx, ebx
0x180033602  mov     rcx, rax
0x180033605  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003360b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033612  cmp     rcx, r15
0x180033615  jz      loc_1800334A6
0x18003361b  test    byte ptr [rcx+1Ch], 1
0x18003361f  jz      loc_1800334A6
0x180033625  cmp     byte ptr [rcx+19h], 2
0x180033629  jb      loc_1800334A6
0x18003362f  mov     edx, 32h ; '2'
0x180033634  jmp     loc_180033742
0x180033639  cmp     rbx, [rdi+0E8h]
0x180033640  setz    r15b
0x180033644  jmp     loc_1800334FE
0x180033649  mov     [rdi+0E8h], rax
0x180033650  jmp     loc_18003352D
0x180033655  test    byte ptr [rcx+1Ch], 1
0x180033659  jz      loc_1800333BC
0x18003365f  cmp     byte ptr [rcx+19h], 2
0x180033663  jb      loc_1800333BC
0x180033669  mov     edx, 33h ; '3'
0x18003366e  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x180033675  mov     rcx, [rcx+10h]
0x180033679  call    WPP_SF_
0x18003367e  jmp     loc_1800333BC
0x180033683  call    cs:__imp_SetEvent
0x180033689  jmp     loc_1800335DF
0x18003368e  cmp     byte ptr [rcx+19h], 2
0x180033692  jb      loc_180033464
0x180033698  mov     edx, 26h ; '&'
0x18003369d  mov     r9d, ebx
0x1800336a0  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x1800336a7  mov     rcx, [rcx+10h]
0x1800336ab  call    WPP_SF_d
0x1800336b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336b7  jmp     loc_180033464
0x1800336bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800336c2  mov     edx, ebx
0x1800336c4  mov     rcx, rax
0x1800336c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800336cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336d4  jmp     loc_180033480
0x1800336d9  cmp     byte ptr [rcx+19h], 2
0x1800336dd  jb      loc_18003348F
0x1800336e3  mov     edx, 3Eh ; '>'
0x1800336e8  mov     r9d, ebx
0x1800336eb  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x1800336f2  mov     rcx, [rcx+10h]
0x1800336f6  call    WPP_SF_d
0x1800336fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180033702  jmp     loc_18003348F
0x180033707  mov     rcx, [rdi+38h]
0x18003370b  mov     edx, ebx; int
0x18003370d  mov     rcx, [rcx+18h]; this
0x180033711  call    ?Cancel@CWmiMerger@@QEAAJJ@Z; CWmiMerger::Cancel(long)
0x180033716  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003371c  mov     edx, ebx
0x18003371e  mov     rcx, rax
0x180033721  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180033727  mov     rcx, cs:WPP_GLOBAL_Control
0x18003372e  jmp     loc_180033497
0x180033733  cmp     byte ptr [rcx+19h], 2
0x180033737  jb      loc_1800334A6
0x18003373d  mov     edx, 34h ; '4'
0x180033742  mov     r9d, ebx
0x180033745  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x18003374c  mov     rcx, [rcx+10h]
0x180033750  call    WPP_SF_d
0x180033755  jmp     loc_1800334A6
```
