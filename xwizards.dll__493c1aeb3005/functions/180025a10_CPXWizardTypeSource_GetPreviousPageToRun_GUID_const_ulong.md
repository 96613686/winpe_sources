# CPXWizardTypeSource::GetPreviousPageToRun(_GUID const *,ulong *)

- ea: `0x180025a10`
- end: `0x180025c7b`
- name: `?GetPreviousPageToRun@CPXWizardTypeSource@@UEAAJPEBU_GUID@@PEAK@Z`
- size: `619`
- prototype: `__int64 __fastcall(CPXWizardTypeSource *__hidden this, const struct _GUID *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x180022fec`
- `0x180025a10`
- `0x180026090`
- `0x180026178`
- `0x1800263d8`
- `0x180026418`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025bf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025bf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b70`

## pseudocode

```c
__int64 __fastcall CPXWizardTypeSource::GetPreviousPageToRun(
        CPXWizardTypeSource *this,
        struct _GUID *a2,
        unsigned int *a3)
{
  CXWCriticalSection *v5; // rsi
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v10; // rcx
  struct _GUID *v11; // r13
  int PreviousPageToRun; // eax
  struct _GUID *v13; // rax
  struct _GUID *v16; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  v5 = (CPXWizardTypeSource *)((char *)this + 200);
  v6 = CXWCriticalSection::HrEnterCriticalSection((CPXWizardTypeSource *)((char *)this + 200));
  if ( (v6 & 0x80000000) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return v6;
    v8 = 28;
LABEL_5:
    WPP_SF_d(v7[2], v8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, v6);
    return v6;
  }
  if ( !*((_DWORD *)this + 62) )
  {
    if ( !*((_QWORD *)this + 22) )
    {
      try
      {
        v16 = a2;
        std::list<_GUID *>::push_back((char *)this + 168, &v16);
      }
      catch ( std::bad_alloc )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
            2147942414LL);
        CXWCriticalSection::HrLeaveCriticalSection((CPXWizardTypeSource *)((char *)this + 200));
        return 2147942414LL;
      }
      while ( *((_QWORD *)this + 22) )
      {
        v10 = **((_QWORD **)this + 21);
        v11 = *(struct _GUID **)(v10 + 16);
        if ( (v6 & 0x80000000) == 0 )
        {
          PreviousPageToRun = CTask::HrGetPreviousPageToRun(
                                *((CTask **)this + 8),
                                *(const struct _GUID **)(v10 + 16),
                                a3);
          v6 = PreviousPageToRun;
          if ( PreviousPageToRun < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
              (unsigned int)PreviousPageToRun);
          }
        }
        if ( v11 != a2 )
          CoTaskMemFree(v11);
        std::list<_GUID *>::pop_front((char *)this + 168);
      }
      CXWCriticalSection::HrLeaveCriticalSection(v5);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v6;
      v8 = 35;
      goto LABEL_5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
        *((unsigned int *)this + 44));
    try
    {
      if ( a2 )
      {
        v13 = (struct _GUID *)CoTaskMemAlloc(0x10u);
        v16 = v13;
        if ( !v13 )
        {
          v6 = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              WPP_fa339ca505f03532a01d2a69d711b092_Traceguids,
              2147942414LL);
          goto LABEL_52;
        }
        *v13 = *a2;
      }
      std::list<_GUID *>::push_back((char *)this + 168, &v16);
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, 2147942414LL);
      CoTaskMemFree(v16);
      v6 = -2147024882;
    }
LABEL_52:
    CXWCriticalSection::HrLeaveCriticalSection(v5);
    return v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids);
  CXWCriticalSection::HrLeaveCriticalSection(v5);
  return 1;
}

```

## disassembly

```asm
0x180025a10  mov     rax, rsp
0x180025a13  mov     [rax+18h], r8
0x180025a17  mov     [rax+8], rcx
0x180025a1b  push    rbx
0x180025a1c  push    rsi
0x180025a1d  push    rdi
0x180025a1e  push    r12
0x180025a20  push    r13
0x180025a22  push    r14
0x180025a24  push    r15
0x180025a26  sub     rsp, 30h
0x180025a2a  mov     r12, rdx
0x180025a2d  mov     r14, rcx
0x180025a30  mov     qword ptr [rax+20h], 0
0x180025a38  lea     rsi, [rcx+0C8h]
0x180025a3f  mov     rcx, rsi; this
0x180025a42  call    ?HrEnterCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrEnterCriticalSection(void)
0x180025a47  mov     ebx, eax
0x180025a49  test    eax, eax
0x180025a4b  jns     short loc_180025A8B
0x180025a4d  lea     rdi, WPP_GLOBAL_Control
0x180025a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a5b  cmp     rcx, rdi
0x180025a5e  jz      loc_180025C69
0x180025a64  test    byte ptr [rcx+1Ch], 4
0x180025a68  jz      loc_180025C69
0x180025a6e  mov     edx, 1Ch
0x180025a73  mov     r9d, ebx
0x180025a76  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025a7d  mov     rcx, [rcx+10h]
0x180025a81  call    WPP_SF_d
0x180025a86  jmp     loc_180025C69
0x180025a8b  cmp     dword ptr [r14+0F8h], 0
0x180025a93  jz      short loc_180025AD5
0x180025a95  lea     rdi, WPP_GLOBAL_Control
0x180025a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025aa3  cmp     rcx, rdi
0x180025aa6  jz      short loc_180025AC3
0x180025aa8  test    byte ptr [rcx+1Ch], 8
0x180025aac  jz      short loc_180025AC3
0x180025aae  mov     edx, 1Dh
0x180025ab3  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025aba  mov     rcx, [rcx+10h]
0x180025abe  call    WPP_SF_
0x180025ac3  mov     rcx, rsi; this
0x180025ac6  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x180025acb  mov     eax, 1
0x180025ad0  jmp     loc_180025C6B
0x180025ad5  mov     [rsp+68h+var_48], rsi
0x180025ada  lea     r15, [r14+0A8h]
0x180025ae1  cmp     qword ptr [r15+8], 0
0x180025ae6  jnz     loc_180025BB6
0x180025aec  mov     [rsp+68h+arg_18], r12
0x180025af4  lea     rdx, [rsp+68h+arg_18]
0x180025afc  mov     rcx, r15
0x180025aff  call    ?push_back@?$list@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@QEAAXAEBQEAU_GUID@@@Z; std::list<_GUID *>::push_back(_GUID * const &)
0x180025b04  nop
0x180025b05  lea     rdi, WPP_GLOBAL_Control
0x180025b0c  cmp     qword ptr [r14+0B0h], 0
0x180025b14  jz      short loc_180025B80
0x180025b16  mov     rax, [r15]
0x180025b19  mov     rcx, [rax]
0x180025b1c  mov     r13, [rcx+10h]
0x180025b20  test    ebx, ebx
0x180025b22  js      short loc_180025B68
0x180025b24  mov     r8, [rsp+68h+arg_10]; unsigned int *
0x180025b2c  mov     rdx, r13; struct _GUID *
0x180025b2f  mov     rcx, [r14+40h]; this
0x180025b33  call    ?HrGetPreviousPageToRun@CTask@@AEAAJPEBU_GUID@@PEAK@Z; CTask::HrGetPreviousPageToRun(_GUID const *,ulong *)
0x180025b38  mov     ebx, eax
0x180025b3a  test    eax, eax
0x180025b3c  jns     short loc_180025B68
0x180025b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b45  cmp     rcx, rdi
0x180025b48  jz      short loc_180025B68
0x180025b4a  test    byte ptr [rcx+1Ch], 8
0x180025b4e  jz      short loc_180025B68
0x180025b50  mov     edx, 22h ; '"'
0x180025b55  mov     r9d, eax
0x180025b58  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025b5f  mov     rcx, [rcx+10h]
0x180025b63  call    WPP_SF_d
0x180025b68  cmp     r13, r12
0x180025b6b  jz      short loc_180025B76
0x180025b6d  mov     rcx, r13; pv
0x180025b70  call    cs:__imp_CoTaskMemFree
0x180025b76  mov     rcx, r15
0x180025b79  call    ?pop_front@?$list@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@QEAAXXZ; std::list<_GUID *>::pop_front(void)
0x180025b7e  jmp     short loc_180025B0C
0x180025b80  mov     rcx, rsi; this
0x180025b83  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x180025b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b8f  cmp     rcx, rdi
0x180025b92  jz      loc_180025C69
0x180025b98  test    byte ptr [rcx+1Ch], 10h
0x180025b9c  jz      loc_180025C69
0x180025ba2  mov     edx, 23h ; '#'
0x180025ba7  jmp     loc_180025A73
0x180025bac  mov     eax, 8007000Eh
0x180025bb1  jmp     loc_180025C6B
0x180025bb6  lea     rdi, WPP_GLOBAL_Control
0x180025bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bc4  cmp     rcx, rdi
0x180025bc7  jz      short loc_180025BEB
0x180025bc9  test    byte ptr [rcx+1Ch], 8
0x180025bcd  jz      short loc_180025BEB
0x180025bcf  mov     edx, 1Eh
0x180025bd4  mov     r9d, [r14+0B0h]
0x180025bdb  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025be2  mov     rcx, [rcx+10h]
0x180025be6  call    WPP_SF_d
0x180025beb  test    r12, r12
0x180025bee  jz      short loc_180025C11
0x180025bf0  mov     ecx, 10h; cb
0x180025bf5  call    cs:__imp_CoTaskMemAlloc
0x180025bfb  mov     [rsp+68h+arg_18], rax
0x180025c03  test    rax, rax
0x180025c06  jz      short loc_180025C24
0x180025c08  movups  xmm0, xmmword ptr [r12]
0x180025c0d  movdqu  xmmword ptr [rax], xmm0
0x180025c11  lea     rdx, [rsp+68h+arg_18]
0x180025c19  mov     rcx, r15
0x180025c1c  call    ?push_back@?$list@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@QEAAXAEBQEAU_GUID@@@Z; std::list<_GUID *>::push_back(_GUID * const &)
0x180025c21  nop
0x180025c22  jmp     short loc_180025C61
0x180025c24  mov     ebx, 8007000Eh
0x180025c29  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c30  cmp     rcx, rdi
0x180025c33  jz      short loc_180025C61
0x180025c35  test    byte ptr [rcx+1Ch], 4
0x180025c39  jz      short loc_180025C61
0x180025c3b  mov     edx, 1Fh
0x180025c40  mov     r9d, 8007000Eh
0x180025c46  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025c4d  mov     rcx, [rcx+10h]
0x180025c51  call    WPP_SF_d
0x180025c56  jmp     short loc_180025C61
0x180025c58  mov     ebx, [rsp+68h+arg_0]
0x180025c5c  mov     rsi, [rsp+68h+var_48]
0x180025c61  mov     rcx, rsi; this
0x180025c64  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x180025c69  mov     eax, ebx
0x180025c6b  add     rsp, 30h
0x180025c6f  pop     r15
0x180025c71  pop     r14
0x180025c73  pop     r13
0x180025c75  pop     r12
0x180025c77  pop     rdi
0x180025c78  pop     rsi
0x180025c79  pop     rbx
0x180025c7a  retn
```
