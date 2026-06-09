# Reachability_CreateGroup(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>)

- ea: `0x180018aa0`
- end: `0x180018df4`
- name: `?Reachability_CreateGroup@@YAJV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@std@@0@Z`
- size: `852`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180018180`

## callees

- `0x180014774`
- `0x180018138`
- `0x180018aa0`
- `0x180018dfc`
- `0x180019714`
- `0x180019798`
- `0x180019800`
- `0x180019828`
- `0x18001abcc`
- `0x18001d9a0`
- `0x18002c918`
- `0x18003d294`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018d74`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018d74`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180018ba1`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180018c24`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180018ba1`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180018c24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018ddb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018ddb`

## string_xrefs

- `0x180018d4b`: `Created reachability group: (\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Reachability_CreateGroup(void **a1, void **a2)
{
  char v3; // si
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  unsigned int v5; // edx
  int v6; // r14d
  void *v7; // rax
  __int64 v8; // r13
  _QWORD *v9; // rcx
  volatile signed __int32 *v10; // rax
  _QWORD *v11; // rax
  unsigned int v12; // edx
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rax
  unsigned int v16; // eax
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+28h] [rbp-80h]
  __int64 v19; // [rsp+30h] [rbp-78h]
  _BYTE v20[24]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v21[24]; // [rsp+60h] [rbp-48h] BYREF
  int v22; // [rsp+78h] [rbp-30h]
  volatile signed __int32 *v24; // [rsp+C0h] [rbp+18h] BYREF
  void *v25; // [rsp+C8h] [rbp+20h]

  v3 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x48u);
  v24 = (volatile signed __int32 *)v4;
  v4[1].DebugInfo = 0;
  *(_QWORD *)&v4[1].LockCount = 0;
  v4[1].OwningThread = 0;
  std::list<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::_Alloc_sentinel_and_proxy();
  v17 = v4;
  v6 = myInitializeCriticalSection(v4);
  if ( v6 < 0 )
  {
LABEL_26:
    if ( v4 )
    {
      if ( v3 )
        DeleteCriticalSection(v4);
      NtpPeerGroupReachabilityInfo::`scalar deleting destructor'((NtpPeerGroupReachabilityInfo *)v4, v5);
    }
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(116) )
      FileLogAdd(L"Created reachability group: (\n");
    v3 = 1;
    while ( a1 != a2 )
    {
      v7 = *a1;
      v25 = v7;
      if ( v7 )
        _InterlockedAdd((volatile signed __int32 *)v7, 1u);
      *(_QWORD *)(*((_QWORD *)v25 + 1) + 120LL) = v4;
      *(_DWORD *)(*((_QWORD *)v25 + 1) + 128LL) = 0;
      *(_QWORD *)(*((_QWORD *)v25 + 1) + 280LL) = -1;
      *(_BYTE *)(*((_QWORD *)v25 + 1) + 288LL) = 1;
      v19 = _set_se_translator(SeTransFunc);
      v6 = 0;
      try
      {
        if ( v4[1].OwningThread == (HANDLE)0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("list too long");
        v8 = *(_QWORD *)&v4[1].LockCount;
        v9 = (_QWORD *)MyThrowingAllocator<std::_List_node<AutoPtr<NtpPeer>,void *>>::allocate();
        v10 = (volatile signed __int32 *)v25;
        v9[2] = v25;
        if ( v10 )
          _InterlockedAdd(v10, 1u);
        ++v4[1].OwningThread;
        v11 = *(_QWORD **)(v8 + 8);
        *v9 = v8;
        v9[1] = v11;
        *(_QWORD *)(v8 + 8) = v9;
        *v11 = v9;
      }
      catch ( SeException v21 )
      {
        v16 = v22;
        if ( v22 > 0 )
          v16 = (unsigned __int16)v22 | 0x80070000;
        LODWORD(v24) = v16;
        SeException::~SeException((SeException *)v21);
        v3 = 1;
        v6 = (int)v24;
        v4 = v17;
      }
      catch ( std::bad_alloc v20 )
      {
        LODWORD(v24) = -2147024882;
        SeException::~SeException((SeException *)v20);
        v3 = 1;
        v6 = (int)v24;
        v4 = v17;
      }
      catch ( ... )
      {
        LODWORD(v24) = -2147418113;
        v3 = 1;
        v6 = (int)v24;
        v4 = v17;
      }
      _set_se_translator(v19);
      if ( v6 < 0 )
      {
        if ( v25 && _InterlockedExchangeAdd((volatile signed __int32 *)v25, 0xFFFFFFFF) == 1 && v25 )
          Ref<NtpPeer>::`scalar deleting destructor'(v25, v5);
        goto LABEL_26;
      }
      if ( (unsigned __int8)FileLogAllowEntry(116) )
      {
        FileLogSockaddrInEx2(
          0,
          (struct sockaddr *)(*((_QWORD *)v25 + 1) + 136LL),
          *(_DWORD *)(*((_QWORD *)v25 + 1) + 264LL));
        FileLogAppend(L",\n");
      }
      if ( v25 && _InterlockedExchangeAdd((volatile signed __int32 *)v25, 0xFFFFFFFF) == 1 && v25 )
        Ref<NtpPeer>::`scalar deleting destructor'(v25, v12);
      ++a1;
    }
    if ( (unsigned __int8)FileLogAllowEntry(116) )
      FileLogAdd(L")\n");
    v13 = **(_QWORD **)&v4[1].LockCount;
    v4[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v13;
    v25 = &v24;
    v14 = *(volatile signed __int32 **)(v13 + 16);
    v24 = v14;
    if ( v14 )
      _InterlockedAdd(v14, 1u);
    SetPeerTimeRemaining(&v24, gc_toZero);
    v4[1].LockSemaphore = (HANDLE)1000000;
    v4[1].DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)v4[1].DebugInfo;
    return 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018aa0  mov     [rsp+arg_0], rbx
0x180018aa5  mov     [rsp+arg_8], rdx
0x180018aaa  push    rsi
0x180018aab  push    rdi
0x180018aac  push    r13
0x180018aae  push    r14
0x180018ab0  push    r15
0x180018ab2  sub     rsp, 80h
0x180018ab9  mov     rbx, rcx
0x180018abc  xor     sil, sil
0x180018abf  mov     ecx, 48h ; 'H'; Size
0x180018ac4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ac9  mov     rdi, rax
0x180018acc  mov     [rsp+0A8h+arg_10], rax
0x180018ad4  mov     qword ptr [rax+28h], 0
0x180018adc  lea     rcx, [rax+30h]
0x180018ae0  mov     qword ptr [rcx], 0
0x180018ae7  mov     qword ptr [rcx+8], 0
0x180018aef  call    ?_Alloc_sentinel_and_proxy@?$list@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@AEAAXXZ; std::list<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::_Alloc_sentinel_and_proxy(void)
0x180018af4  nop
0x180018af5  mov     [rsp+0A8h+var_80], rdi
0x180018afa  mov     rcx, rdi; lpCriticalSection
0x180018afd  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x180018b02  mov     r14d, eax
0x180018b05  test    eax, eax
0x180018b07  js      loc_180018CF7
0x180018b0d  mov     ecx, 74h ; 't'
0x180018b12  call    FileLogAllowEntry
0x180018b17  test    al, al
0x180018b19  jnz     loc_180018D4B
0x180018b1f  mov     esi, 1
0x180018b24  mov     [rsp+0A8h+var_88], rbx
0x180018b29  cmp     rbx, [rsp+0A8h+arg_8]
0x180018b31  jz      loc_180018C71
0x180018b37  mov     rax, [rbx]
0x180018b3a  mov     [rsp+0A8h+arg_18], rax
0x180018b42  test    rax, rax
0x180018b45  jz      short loc_180018B4A
0x180018b47  lock add [rax], esi
0x180018b4a  mov     rax, [rsp+0A8h+arg_18]
0x180018b52  mov     rcx, [rax+8]
0x180018b56  mov     [rcx+78h], rdi
0x180018b5a  mov     rax, [rsp+0A8h+arg_18]
0x180018b62  mov     rcx, [rax+8]
0x180018b66  mov     dword ptr [rcx+80h], 0
0x180018b70  mov     rax, [rsp+0A8h+arg_18]
0x180018b78  mov     rcx, [rax+8]
0x180018b7c  mov     qword ptr [rcx+118h], 0FFFFFFFFFFFFFFFFh
0x180018b87  mov     rax, [rsp+0A8h+arg_18]
0x180018b8f  mov     rcx, [rax+8]
0x180018b93  mov     [rcx+120h], sil
0x180018b9a  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180018ba1  call    cs:__imp__set_se_translator
0x180018ba8  nop     dword ptr [rax+rax+00h]
0x180018bad  mov     [rsp+0A8h+var_78], rax
0x180018bb2  xor     r14d, r14d
0x180018bb5  lea     r15, [rdi+30h]
0x180018bb9  mov     rax, 0AAAAAAAAAAAAAAAh
0x180018bc3  cmp     [r15+8], rax
0x180018bc7  jz      loc_180018D6D
0x180018bcd  mov     r13, [r15]
0x180018bd0  mov     [rsp+0A8h+var_70], r15
0x180018bd5  mov     [rsp+0A8h+var_68], r14
0x180018bda  mov     [rsp+0A8h+var_68], r14
0x180018bdf  call    ?allocate@?$MyThrowingAllocator@U?$_List_node@V?$AutoPtr@UNtpPeer@@@@PEAX@std@@@@QEAAPEAU?$_List_node@V?$AutoPtr@UNtpPeer@@@@PEAX@std@@_KPEBX@Z; MyThrowingAllocator<std::_List_node<AutoPtr<NtpPeer>,void *>>::allocate(unsigned __int64,void const *)
0x180018be4  mov     rcx, rax
0x180018be7  mov     [rsp+0A8h+var_68], rax
0x180018bec  mov     rax, [rsp+0A8h+arg_18]
0x180018bf4  mov     [rcx+10h], rax
0x180018bf8  test    rax, rax
0x180018bfb  jz      short loc_180018C00
0x180018bfd  lock add [rax], esi
0x180018c00  add     [r15+8], rsi
0x180018c04  mov     rax, [r13+8]
0x180018c08  mov     [rcx], r13
0x180018c0b  mov     [rcx+8], rax
0x180018c0f  mov     [rsp+0A8h+var_68], 0
0x180018c18  mov     [r13+8], rcx
0x180018c1c  mov     [rax], rcx
0x180018c1f  mov     rcx, [rsp+0A8h+var_78]
0x180018c24  call    cs:__imp__set_se_translator
0x180018c2b  nop     dword ptr [rax+rax+00h]
0x180018c30  test    r14d, r14d
0x180018c33  js      loc_180018CDE
0x180018c39  mov     ecx, 74h ; 't'
0x180018c3e  call    FileLogAllowEntry
0x180018c43  test    al, al
0x180018c45  jnz     loc_180018DA1
0x180018c4b  mov     rax, [rsp+0A8h+arg_18]
0x180018c53  test    rax, rax
0x180018c56  jz      short loc_180018C68
0x180018c58  or      ecx, 0FFFFFFFFh
0x180018c5b  lock xadd [rax], ecx
0x180018c5f  cmp     ecx, 1
0x180018c62  jz      loc_180018D1C
0x180018c68  add     rbx, 8
0x180018c6c  jmp     loc_180018B24
0x180018c71  mov     ecx, 74h ; 't'
0x180018c76  call    FileLogAllowEntry
0x180018c7b  test    al, al
0x180018c7d  jnz     loc_180018D5C
0x180018c83  mov     rax, [rdi+30h]
0x180018c87  mov     rcx, [rax]
0x180018c8a  mov     [rdi+28h], rcx
0x180018c8e  mov     rdx, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x180018c95  lea     rax, [rsp+0A8h+arg_10]
0x180018c9d  mov     [rsp+0A8h+arg_18], rax
0x180018ca5  mov     rax, [rcx+10h]
0x180018ca9  mov     [rsp+0A8h+arg_10], rax
0x180018cb1  test    rax, rax
0x180018cb4  jz      short loc_180018CB9
0x180018cb6  lock add [rax], esi
0x180018cb9  lea     rcx, [rsp+0A8h+arg_10]
0x180018cc1  call    ?SetPeerTimeRemaining@@YAXV?$AutoPtr@UNtpPeer@@@@UNtTimePeriod@@@Z; SetPeerTimeRemaining(AutoPtr<NtpPeer>,NtTimePeriod)
0x180018cc6  mov     qword ptr [rdi+40h], 0F4240h
0x180018cce  mov     rax, [rdi+28h]
0x180018cd2  mov     rcx, [rax]
0x180018cd5  mov     [rdi+28h], rcx
0x180018cd9  xor     r14d, r14d
0x180018cdc  jmp     short loc_180018D00
0x180018cde  mov     rax, [rsp+0A8h+arg_18]
0x180018ce6  test    rax, rax
0x180018ce9  jz      short loc_180018CF7
0x180018ceb  or      ecx, 0FFFFFFFFh
0x180018cee  lock xadd [rax], ecx
0x180018cf2  cmp     ecx, 1
0x180018cf5  jz      short loc_180018D37
0x180018cf7  test    rdi, rdi
0x180018cfa  jnz     loc_180018DD3
0x180018d00  mov     eax, r14d
0x180018d03  mov     rbx, [rsp+0A8h+arg_0]
0x180018d0b  add     rsp, 80h
0x180018d12  pop     r15
0x180018d14  pop     r14
0x180018d16  pop     r13
0x180018d18  pop     rdi
0x180018d19  pop     rsi
0x180018d1a  retn
0x180018d1c  mov     rcx, [rsp+0A8h+arg_18]; void *
0x180018d24  test    rcx, rcx
0x180018d27  jz      loc_180018C68
0x180018d2d  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x180018d32  jmp     loc_180018C68
0x180018d37  mov     rcx, [rsp+0A8h+arg_18]; void *
0x180018d3f  test    rcx, rcx
0x180018d42  jz      short loc_180018CF7
0x180018d44  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x180018d49  jmp     short loc_180018CF7
0x180018d4b  lea     rcx, aCreatedReachab; "Created reachability group: (\n"
0x180018d52  call    FileLogAdd
0x180018d57  jmp     loc_180018B1F
0x180018d5c  lea     rcx, asc_180073DC8; ")\n"
0x180018d63  call    FileLogAdd
0x180018d68  jmp     loc_180018C83
0x180018d6d  lea     rcx, aListTooLong; "list too long"
0x180018d74  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018d81  jmp     short loc_180018D85
0x180018d83  jmp     short $+2
0x180018d85  mov     esi, 1
0x180018d8a  mov     r14d, dword ptr [rsp+0A8h+arg_10]
0x180018d92  mov     rdi, [rsp+0A8h+var_80]
0x180018d97  mov     rbx, [rsp+0A8h+var_88]
0x180018d9c  jmp     loc_180018C1F
0x180018da1  mov     rax, [rsp+0A8h+arg_18]
0x180018da9  mov     r8, [rax+8]
0x180018dad  lea     rdx, [r8+88h]; struct sockaddr_storage *
0x180018db4  mov     r8d, [r8+108h]; unsigned int
0x180018dbb  xor     ecx, ecx; bool
0x180018dbd  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x180018dc2  lea     rcx, asc_180073DC0; ",\n"
0x180018dc9  call    FileLogAppend
0x180018dce  jmp     loc_180018C4B
0x180018dd3  test    sil, sil
0x180018dd6  jz      short loc_180018DE7
0x180018dd8  mov     rcx, rdi; lpCriticalSection
0x180018ddb  call    cs:__imp_DeleteCriticalSection
0x180018de2  nop     dword ptr [rax+rax+00h]
0x180018de7  mov     rcx, rdi; this
0x180018dea  call    ??_GNtpPeerGroupReachabilityInfo@@QEAAPEAXI@Z; NtpPeerGroupReachabilityInfo::`scalar deleting destructor'(uint)
0x180018def  jmp     loc_180018D00
```
