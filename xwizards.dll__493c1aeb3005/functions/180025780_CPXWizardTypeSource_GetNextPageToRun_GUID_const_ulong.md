# CPXWizardTypeSource::GetNextPageToRun(_GUID const *,ulong *)

- ea: `0x180025780`
- end: `0x1800259fe`
- name: `?GetNextPageToRun@CPXWizardTypeSource@@UEAAJPEBU_GUID@@PEAK@Z`
- size: `638`
- prototype: `__int64 __fastcall(CPXWizardTypeSource *__hidden this, const struct _GUID *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x180021d04`
- `0x180025780`
- `0x180026090`
- `0x180026178`
- `0x1800263d8`
- `0x180026418`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800258f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800258f0`

## pseudocode

```c
__int64 __fastcall CPXWizardTypeSource::GetNextPageToRun(CPXWizardTypeSource *this, struct _GUID *a2, unsigned int *a3)
{
  CXWCriticalSection *v5; // rsi
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v10; // rcx
  struct _GUID *v11; // r13
  const struct _GUID *i; // rdx
  int NextPageToRun; // eax
  struct _GUID *v14; // rax
  struct _GUID *v17; // [rsp+88h] [rbp+20h] BYREF

  v17 = 0;
  v5 = (CPXWizardTypeSource *)((char *)this + 200);
  v6 = CXWCriticalSection::HrEnterCriticalSection((CPXWizardTypeSource *)((char *)this + 200));
  if ( (v6 & 0x80000000) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return v6;
    v8 = 20;
LABEL_5:
    WPP_SF_d(v7[2], v8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, v6);
    return v6;
  }
  if ( !*((_DWORD *)this + 62) )
  {
    if ( !*((_QWORD *)this + 20) )
    {
      try
      {
        v17 = a2;
        std::list<_GUID *>::push_back((char *)this + 152, &v17);
      }
      catch ( std::bad_alloc )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
            2147942414LL);
        CXWCriticalSection::HrLeaveCriticalSection((CPXWizardTypeSource *)((char *)this + 200));
        return 2147942414LL;
      }
      while ( *((_QWORD *)this + 20) )
      {
        v10 = **((_QWORD **)this + 19);
        v11 = *(struct _GUID **)(v10 + 16);
        if ( (v6 & 0x80000000) == 0 )
        {
          for ( i = *(const struct _GUID **)(v10 + 16); ; i = 0 )
          {
            NextPageToRun = CTask::HrGetNextPageToRun(*((CTask **)this + 8), i, a3);
            v6 = NextPageToRun;
            if ( NextPageToRun != 262656 )
              break;
          }
          if ( NextPageToRun < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
                (unsigned int)NextPageToRun);
            v6 = 262657;
          }
        }
        if ( v11 != a2 )
          CoTaskMemFree(v11);
        std::list<_GUID *>::pop_front((char *)this + 152);
      }
      CXWCriticalSection::HrLeaveCriticalSection(v5);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v6;
      v8 = 27;
      goto LABEL_5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
        *((unsigned int *)this + 40));
    try
    {
      if ( a2 )
      {
        v14 = (struct _GUID *)CoTaskMemAlloc(0x10u);
        v17 = v14;
        if ( !v14 )
        {
          v6 = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
              2147942414LL);
          goto LABEL_56;
        }
        *v14 = *a2;
      }
      std::list<_GUID *>::push_back((char *)this + 152, &v17);
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, 2147942414LL);
      CoTaskMemFree(v17);
      v6 = -2147024882;
    }
LABEL_56:
    CXWCriticalSection::HrLeaveCriticalSection(v5);
    return v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids);
  CXWCriticalSection::HrLeaveCriticalSection(v5);
  return 1;
}

```

## disassembly

```asm
0x180025780  mov     rax, rsp
0x180025783  mov     [rax+18h], r8
0x180025787  mov     [rax+8], rcx
0x18002578b  push    rbx
0x18002578c  push    rsi
0x18002578d  push    rdi
0x18002578e  push    r12
0x180025790  push    r13
0x180025792  push    r14
0x180025794  push    r15
0x180025796  sub     rsp, 30h
0x18002579a  mov     r12, rdx
0x18002579d  mov     r14, rcx
0x1800257a0  mov     qword ptr [rax+20h], 0
0x1800257a8  lea     rsi, [rcx+0C8h]
0x1800257af  mov     rcx, rsi; this
0x1800257b2  call    ?HrEnterCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrEnterCriticalSection(void)
0x1800257b7  mov     ebx, eax
0x1800257b9  test    eax, eax
0x1800257bb  jns     short loc_1800257FB
0x1800257bd  lea     rdi, WPP_GLOBAL_Control
0x1800257c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257cb  cmp     rcx, rdi
0x1800257ce  jz      loc_1800259EC
0x1800257d4  test    byte ptr [rcx+1Ch], 4
0x1800257d8  jz      loc_1800259EC
0x1800257de  mov     edx, 14h
0x1800257e3  mov     r9d, ebx
0x1800257e6  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x1800257ed  mov     rcx, [rcx+10h]
0x1800257f1  call    WPP_SF_d
0x1800257f6  jmp     loc_1800259EC
0x1800257fb  cmp     dword ptr [r14+0F8h], 0
0x180025803  jz      short loc_180025845
0x180025805  lea     rdi, WPP_GLOBAL_Control
0x18002580c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025813  cmp     rcx, rdi
0x180025816  jz      short loc_180025833
0x180025818  test    byte ptr [rcx+1Ch], 8
0x18002581c  jz      short loc_180025833
0x18002581e  mov     edx, 15h
0x180025823  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x18002582a  mov     rcx, [rcx+10h]
0x18002582e  call    WPP_SF_
0x180025833  mov     rcx, rsi; this
0x180025836  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x18002583b  mov     eax, 1
0x180025840  jmp     loc_1800259EE
0x180025845  mov     [rsp+68h+var_48], rsi
0x18002584a  lea     r15, [r14+98h]
0x180025851  cmp     qword ptr [r15+8], 0
0x180025856  jnz     loc_180025939
0x18002585c  mov     [rsp+68h+arg_18], r12
0x180025864  lea     rdx, [rsp+68h+arg_18]
0x18002586c  mov     rcx, r15
0x18002586f  call    ?push_back@?$list@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@QEAAXAEBQEAU_GUID@@@Z; std::list<_GUID *>::push_back(_GUID * const &)
0x180025874  nop
0x180025875  lea     rdi, WPP_GLOBAL_Control
0x18002587c  cmp     qword ptr [r14+0A0h], 0
0x180025884  jz      short loc_180025903
0x180025886  mov     rax, [r15]
0x180025889  mov     rcx, [rax]
0x18002588c  mov     r13, [rcx+10h]
0x180025890  test    ebx, ebx
0x180025892  js      short loc_1800258E8
0x180025894  mov     rdx, r13
0x180025897  jmp     short loc_18002589B
0x180025899  xor     edx, edx; struct _GUID *
0x18002589b  mov     r8, [rsp+68h+arg_10]; unsigned int *
0x1800258a3  mov     rcx, [r14+40h]; this
0x1800258a7  call    ?HrGetNextPageToRun@CTask@@AEAAJPEBU_GUID@@PEAK@Z; CTask::HrGetNextPageToRun(_GUID const *,ulong *)
0x1800258ac  cmp     eax, 40200h
0x1800258b1  mov     ebx, eax
0x1800258b3  jz      short loc_180025899
0x1800258b5  test    eax, eax
0x1800258b7  jns     short loc_1800258E8
0x1800258b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258c0  cmp     rcx, rdi
0x1800258c3  jz      short loc_1800258E3
0x1800258c5  test    byte ptr [rcx+1Ch], 8
0x1800258c9  jz      short loc_1800258E3
0x1800258cb  mov     edx, 1Ah
0x1800258d0  mov     r9d, eax
0x1800258d3  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x1800258da  mov     rcx, [rcx+10h]
0x1800258de  call    WPP_SF_d
0x1800258e3  mov     ebx, 40201h
0x1800258e8  cmp     r13, r12
0x1800258eb  jz      short loc_1800258F6
0x1800258ed  mov     rcx, r13; pv
0x1800258f0  call    cs:__imp_CoTaskMemFree
0x1800258f6  mov     rcx, r15
0x1800258f9  call    ?pop_front@?$list@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@QEAAXXZ; std::list<_GUID *>::pop_front(void)
0x1800258fe  jmp     loc_18002587C
0x180025903  mov     rcx, rsi; this
0x180025906  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x18002590b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025912  cmp     rcx, rdi
0x180025915  jz      loc_1800259EC
0x18002591b  test    byte ptr [rcx+1Ch], 10h
0x18002591f  jz      loc_1800259EC
0x180025925  mov     edx, 1Bh
0x18002592a  jmp     loc_1800257E3
0x18002592f  mov     eax, 8007000Eh
0x180025934  jmp     loc_1800259EE
0x180025939  lea     rdi, WPP_GLOBAL_Control
0x180025940  mov     rcx, cs:WPP_GLOBAL_Control
0x180025947  cmp     rcx, rdi
0x18002594a  jz      short loc_18002596E
0x18002594c  test    byte ptr [rcx+1Ch], 8
0x180025950  jz      short loc_18002596E
0x180025952  mov     edx, 16h
0x180025957  mov     r9d, [r14+0A0h]
0x18002595e  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025965  mov     rcx, [rcx+10h]
0x180025969  call    WPP_SF_d
0x18002596e  test    r12, r12
0x180025971  jz      short loc_180025994
0x180025973  mov     ecx, 10h; cb
0x180025978  call    cs:__imp_CoTaskMemAlloc
0x18002597e  mov     [rsp+68h+arg_18], rax
0x180025986  test    rax, rax
0x180025989  jz      short loc_1800259A7
0x18002598b  movups  xmm0, xmmword ptr [r12]
0x180025990  movdqu  xmmword ptr [rax], xmm0
0x180025994  lea     rdx, [rsp+68h+arg_18]
0x18002599c  mov     rcx, r15
0x18002599f  call    ?push_back@?$list@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@QEAAXAEBQEAU_GUID@@@Z; std::list<_GUID *>::push_back(_GUID * const &)
0x1800259a4  nop
0x1800259a5  jmp     short loc_1800259E4
0x1800259a7  mov     ebx, 8007000Eh
0x1800259ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259b3  cmp     rcx, rdi
0x1800259b6  jz      short loc_1800259E4
0x1800259b8  test    byte ptr [rcx+1Ch], 4
0x1800259bc  jz      short loc_1800259E4
0x1800259be  mov     edx, 17h
0x1800259c3  mov     r9d, 8007000Eh
0x1800259c9  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x1800259d0  mov     rcx, [rcx+10h]
0x1800259d4  call    WPP_SF_d
0x1800259d9  jmp     short loc_1800259E4
0x1800259db  mov     ebx, [rsp+68h+arg_0]
0x1800259df  mov     rsi, [rsp+68h+var_48]
0x1800259e4  mov     rcx, rsi; this
0x1800259e7  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x1800259ec  mov     eax, ebx
0x1800259ee  add     rsp, 30h
0x1800259f2  pop     r15
0x1800259f4  pop     r14
0x1800259f6  pop     r13
0x1800259f8  pop     r12
0x1800259fa  pop     rdi
0x1800259fb  pop     rsi
0x1800259fc  pop     rbx
0x1800259fd  retn
```
