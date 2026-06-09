# std::for_each<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,Reachability_PeerRemover>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,Reachability_PeerRemover)

- ea: `0x18001ac00`
- end: `0x18001ae7a`
- name: `??$for_each@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@std@@UReachability_PeerRemover@@@std@@YA?AUReachability_PeerRemover@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@0@0U1@@Z`
- size: `634`
- prototype: `_OWORD *__fastcall(_OWORD *, void **, void **, char **)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800239c4`
- `0x180046a88`

## callees

- `0x180014774`
- `0x180018138`
- `0x180018dfc`
- `0x18001abcc`
- `0x18001ac00`
- `0x18001b810`
- `0x18001d9a0`
- `0x18002dbc4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001acdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ada9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001acdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ada9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001adbc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001adbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001acab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001acab`

## pseudocode

```c
_OWORD *__fastcall std::for_each<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,Reachability_PeerRemover>(
        _OWORD *a1,
        void **a2,
        void **a3,
        char **a4)
{
  void **v6; // r14
  char *v9; // r12
  void *v10; // rax
  __int64 v11; // r13
  __int64 v12; // rbp
  _QWORD ***v13; // r9
  _QWORD **i; // rdi
  char v15; // di
  char v16; // bp
  unsigned int v17; // edx
  NtpPeerGroupReachabilityInfo *v18; // rcx
  void *v19; // [rsp+20h] [rbp-58h] BYREF
  void *v20[10]; // [rsp+28h] [rbp-50h] BYREF

  v6 = a2;
  if ( a2 != a3 )
  {
    v9 = *a4;
    do
    {
      v10 = *v6;
      v20[0] = v10;
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)v10);
      v20[1] = v20;
      v19 = v20[0];
      if ( v20[0] )
        _InterlockedIncrement((volatile signed __int32 *)v20[0]);
      v20[2] = &v19;
      v11 = *((_QWORD *)v19 + 1);
      v12 = *(_QWORD *)(v11 + 120);
      EnterCriticalSection((LPCRITICAL_SECTION)v12);
      if ( (unsigned __int8)FileLogAllowEntry(116) )
        FileLogAdd(L"Reachability:  removing peer %s.  ", *((_QWORD *)v19 + 1) + 290LL);
      v13 = *(_QWORD ****)(v12 + 48);
      for ( i = *v13; ; i = (_QWORD **)*i )
      {
        if ( v13 == i )
          goto LABEL_12;
        if ( (unsigned int)AutoPtr<NtpPeer>::operator==(i + 2, &v19) )
          break;
      }
      if ( v13 == i )
        goto LABEL_12;
      *i[1] = *i;
      (*i)[1] = i[1];
      --*(_QWORD *)(v12 + 56);
      AutoPtr<NtpPeer>::`scalar deleting destructor'(i + 2);
      LocalFree(i);
      if ( *(_QWORD *)(v12 + 56) )
      {
        v15 = 1;
        v16 = 0;
      }
      else
      {
        if ( (unsigned __int8)FileLogAllowEntry(116) )
          FileLogAppend(L"LAST PEER IN GROUP!");
        v16 = 1;
        LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v11 + 120));
        v15 = 0;
        DeleteCriticalSection(*(LPCRITICAL_SECTION *)(v11 + 120));
        v18 = *(NtpPeerGroupReachabilityInfo **)(v11 + 120);
        if ( v18 )
          NtpPeerGroupReachabilityInfo::`scalar deleting destructor'(v18, v17);
      }
      if ( (unsigned __int8)FileLogAllowEntry(116) )
        FileLogAppend(L"\n");
      if ( v9 )
        *v9 = v16;
      if ( v15 )
LABEL_12:
        LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v11 + 120));
      if ( v19 && _InterlockedExchangeAdd((volatile signed __int32 *)v19, 0xFFFFFFFF) == 1 && v19 )
        Ref<NtpPeer>::`scalar deleting destructor'(v19);
      if ( v20[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v20[0], 0xFFFFFFFF) == 1 && v20[0] )
        Ref<NtpPeer>::`scalar deleting destructor'(v20[0]);
      ++v6;
    }
    while ( v6 != a3 );
  }
  *a1 = *(_OWORD *)a4;
  return a1;
}

```

## disassembly

```asm
0x18001ac00  mov     [rsp+arg_10], rbx
0x18001ac05  push    rbp
0x18001ac06  push    rsi
0x18001ac07  push    rdi
0x18001ac08  push    r12
0x18001ac0a  push    r13
0x18001ac0c  push    r14
0x18001ac0e  push    r15
0x18001ac10  sub     rsp, 40h
0x18001ac14  mov     r15, r9
0x18001ac17  mov     rbx, r8
0x18001ac1a  mov     r14, rdx
0x18001ac1d  mov     rsi, rcx
0x18001ac20  cmp     rdx, r8
0x18001ac23  jnz     short loc_18001AC48
0x18001ac25  movaps  xmm0, xmmword ptr [r15]
0x18001ac29  movups  xmmword ptr [rsi], xmm0
0x18001ac2c  mov     rax, rsi
0x18001ac2f  mov     rbx, [rsp+78h+arg_10]
0x18001ac37  add     rsp, 40h
0x18001ac3b  pop     r15
0x18001ac3d  pop     r14
0x18001ac3f  pop     r13
0x18001ac41  pop     r12
0x18001ac43  pop     rdi
0x18001ac44  pop     rsi
0x18001ac45  pop     rbp
0x18001ac46  retn
0x18001ac48  mov     r12, [r9]
0x18001ac4b  lea     rax, [rsp+78h+var_50]
0x18001ac50  mov     [rsp+78h+arg_0], rax
0x18001ac58  mov     rax, [r14]
0x18001ac5b  mov     [rsp+78h+var_50], rax
0x18001ac60  test    rax, rax
0x18001ac63  jz      short loc_18001AC68
0x18001ac65  lock inc dword ptr [rax]
0x18001ac68  lea     rax, [rsp+78h+var_50]
0x18001ac6d  mov     [rsp+78h+var_48], rax
0x18001ac72  lea     rax, [rsp+78h+var_58]
0x18001ac77  mov     [rsp+78h+arg_8], rax
0x18001ac7f  mov     rax, [rsp+78h+var_50]
0x18001ac84  mov     [rsp+78h+var_58], rax
0x18001ac89  test    rax, rax
0x18001ac8c  jz      short loc_18001AC91
0x18001ac8e  lock inc dword ptr [rax]
0x18001ac91  lea     rax, [rsp+78h+var_58]
0x18001ac96  mov     [rsp+78h+var_40], rax
0x18001ac9b  mov     rax, [rsp+78h+var_58]
0x18001aca0  mov     r13, [rax+8]
0x18001aca4  mov     rbp, [r13+78h]
0x18001aca8  mov     rcx, rbp; lpCriticalSection
0x18001acab  call    cs:__imp_EnterCriticalSection
0x18001acb2  nop     dword ptr [rax+rax+00h]
0x18001acb7  mov     ecx, 74h ; 't'
0x18001acbc  call    FileLogAllowEntry
0x18001acc1  test    al, al
0x18001acc3  jnz     loc_18001AE0F
0x18001acc9  mov     r9, [rbp+30h]
0x18001accd  mov     rdi, [r9]
0x18001acd0  cmp     r9, rdi
0x18001acd3  jnz     loc_18001AE30
0x18001acd9  mov     rcx, [r13+78h]; lpCriticalSection
0x18001acdd  call    cs:__imp_LeaveCriticalSection
0x18001ace4  nop     dword ptr [rax+rax+00h]
0x18001ace9  jmp     short loc_18001AD4E
0x18001aceb  cmp     r9, rdi
0x18001acee  jz      short loc_18001ACD9
0x18001acf0  mov     rdx, [rdi+8]
0x18001acf4  mov     rax, [rdi]
0x18001acf7  mov     [rdx], rax
0x18001acfa  mov     rdx, [rdi]
0x18001acfd  mov     rax, [rdi+8]
0x18001ad01  mov     [rdx+8], rax
0x18001ad05  dec     qword ptr [rbp+38h]
0x18001ad09  lea     rcx, [rdi+10h]
0x18001ad0d  call    ??_G?$AutoPtr@UNtpPeer@@@@QEAAPEAXI@Z; AutoPtr<NtpPeer>::`scalar deleting destructor'(uint)
0x18001ad12  mov     rcx, rdi; hMem
0x18001ad15  call    cs:__imp_LocalFree
0x18001ad1c  nop     dword ptr [rax+rax+00h]
0x18001ad21  cmp     qword ptr [rbp+38h], 0
0x18001ad26  jz      short loc_18001AD90
0x18001ad28  mov     dil, 1
0x18001ad2b  xor     bpl, bpl
0x18001ad2e  mov     ecx, 74h ; 't'
0x18001ad33  call    FileLogAllowEntry
0x18001ad38  test    al, al
0x18001ad3a  jnz     loc_18001AE5F
0x18001ad40  test    r12, r12
0x18001ad43  jnz     loc_18001AE70
0x18001ad49  test    dil, dil
0x18001ad4c  jnz     short loc_18001ACD9
0x18001ad4e  mov     rcx, [rsp+78h+var_58]
0x18001ad53  test    rcx, rcx
0x18001ad56  jz      short loc_18001AD66
0x18001ad58  mov     eax, 0FFFFFFFFh
0x18001ad5d  lock xadd [rcx], eax
0x18001ad61  cmp     eax, 1
0x18001ad64  jz      short loc_18001ADDF
0x18001ad66  mov     rcx, [rsp+78h+var_50]
0x18001ad6b  test    rcx, rcx
0x18001ad6e  jz      short loc_18001AD7E
0x18001ad70  mov     eax, 0FFFFFFFFh
0x18001ad75  lock xadd [rcx], eax
0x18001ad79  cmp     eax, 1
0x18001ad7c  jz      short loc_18001ADF7
0x18001ad7e  add     r14, 8
0x18001ad82  cmp     r14, rbx
0x18001ad85  jz      loc_18001AC25
0x18001ad8b  jmp     loc_18001AC4B
0x18001ad90  mov     ecx, 74h ; 't'
0x18001ad95  call    FileLogAllowEntry
0x18001ad9a  test    al, al
0x18001ad9c  jnz     loc_18001AE4E
0x18001ada2  mov     bpl, 1
0x18001ada5  mov     rcx, [r13+78h]; lpCriticalSection
0x18001ada9  call    cs:__imp_LeaveCriticalSection
0x18001adb0  nop     dword ptr [rax+rax+00h]
0x18001adb5  xor     dil, dil
0x18001adb8  mov     rcx, [r13+78h]; lpCriticalSection
0x18001adbc  call    cs:__imp_DeleteCriticalSection
0x18001adc3  nop     dword ptr [rax+rax+00h]
0x18001adc8  mov     rcx, [r13+78h]; this
0x18001adcc  test    rcx, rcx
0x18001adcf  jz      loc_18001AD2E
0x18001add5  call    ??_GNtpPeerGroupReachabilityInfo@@QEAAPEAXI@Z; NtpPeerGroupReachabilityInfo::`scalar deleting destructor'(uint)
0x18001adda  jmp     loc_18001AD2E
0x18001addf  mov     rcx, [rsp+78h+var_58]; void *
0x18001ade4  test    rcx, rcx
0x18001ade7  jz      loc_18001AD66
0x18001aded  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x18001adf2  jmp     loc_18001AD66
0x18001adf7  mov     rcx, [rsp+78h+var_50]; void *
0x18001adfc  test    rcx, rcx
0x18001adff  jz      loc_18001AD7E
0x18001ae05  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x18001ae0a  jmp     loc_18001AD7E
0x18001ae0f  mov     rax, [rsp+78h+var_58]
0x18001ae14  mov     rdx, [rax+8]
0x18001ae18  add     rdx, 122h
0x18001ae1f  lea     rcx, aReachabilityRe; "Reachability:  removing peer %s.  "
0x18001ae26  call    FileLogAdd
0x18001ae2b  jmp     loc_18001ACC9
0x18001ae30  lea     rdx, [rsp+78h+var_58]
0x18001ae35  lea     rcx, [rdi+10h]
0x18001ae39  call    ??8?$AutoPtr@UNtpPeer@@@@QEAAHAEBV0@@Z; AutoPtr<NtpPeer>::operator==(AutoPtr<NtpPeer> const &)
0x18001ae3e  test    eax, eax
0x18001ae40  jnz     loc_18001ACEB
0x18001ae46  mov     rdi, [rdi]
0x18001ae49  jmp     loc_18001ACD0
0x18001ae4e  lea     rcx, aLastPeerInGrou; "LAST PEER IN GROUP!"
0x18001ae55  call    FileLogAppend
0x18001ae5a  jmp     loc_18001ADA2
0x18001ae5f  lea     rcx, asc_18007145C; "\n"
0x18001ae66  call    FileLogAppend
0x18001ae6b  jmp     loc_18001AD40
0x18001ae70  mov     [r12], bpl
0x18001ae74  jmp     loc_18001AD49
```
