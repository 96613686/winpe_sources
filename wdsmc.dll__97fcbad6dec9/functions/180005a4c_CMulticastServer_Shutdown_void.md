# CMulticastServer::Shutdown(void)

- ea: `0x180005a4c`
- end: `0x180005e20`
- name: `?Shutdown@CMulticastServer@@QEAAKXZ`
- size: `980`
- prototype: `unsigned int __fastcall(CMulticastServer *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180009130`

## callees

- `0x1800026b8`
- `0x180002810`
- `0x180003868`
- `0x180005a4c`
- `0x180008698`
- `0x1800088f0`
- `0x180008aa0`
- `0x180008b58`
- `0x180008dcc`
- `0x18000aed0`
- `0x180019124`
- `0x18001a9a8`
- `0x1800227d4`
- `0x180024b0c`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x180005d82`
- `KERNEL32!WaitForSingleObjectEx` at `0x180005d82`
- `KERNEL32!LeaveCriticalSection` at `0x180005d5b`
- `KERNEL32!LeaveCriticalSection` at `0x180005e00`
- `KERNEL32!LeaveCriticalSection` at `0x180005d5b`
- `KERNEL32!LeaveCriticalSection` at `0x180005e00`
- `KERNEL32!EnterCriticalSection` at `0x180005a83`
- `KERNEL32!EnterCriticalSection` at `0x180005d3c`
- `KERNEL32!EnterCriticalSection` at `0x180005a83`
- `KERNEL32!EnterCriticalSection` at `0x180005d3c`
- `KERNEL32!DeleteCriticalSection` at `0x180005c77`
- `KERNEL32!DeleteCriticalSection` at `0x180005c77`
- `ADVAPI32!DeregisterEventSource` at `0x180005cde`
- `ADVAPI32!DeregisterEventSource` at `0x180005cde`
- `ADVAPI32!RegCloseKey` at `0x180005c69`
- `ADVAPI32!RegCloseKey` at `0x180005c69`
- `WS2_32!__imp_WSACleanup` at `0x180005d0a`
- `WS2_32!__imp_WSACleanup` at `0x180005d0a`
- `WDSCSL!WdsClientFreeLibrary` at `0x180005cf4`
- `WDSCSL!WdsClientFreeLibrary` at `0x180005cf4`

## pseudocode

```c
__int64 __fastcall CMulticastServer::Shutdown(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // r15d
  unsigned int v3; // eax
  const char *v4; // rdx
  int v5; // ebx
  __int64 v6; // r14
  __int64 v7; // rax
  __int64 v8; // r11
  CMRSWLock *v9; // r15
  bool v10; // zf
  int v11; // esi
  CMRSWLock *v12; // r13
  CMulticastNamespace *v13; // rsi
  unsigned int v14; // eax
  const char *v15; // rdx
  unsigned int v16; // eax
  const char *v17; // rdx
  int v18; // ebx
  __int64 v19; // rsi
  HKEY v20; // rcx
  unsigned int v21; // eax
  const char *v22; // rdx
  int v23; // r9d
  CMRSWLock *v24; // rdi
  struct _RTL_CRITICAL_SECTION *v25; // rbx
  const char *v26; // rdx
  DWORD v27; // eax
  CMRSWLock *v29; // [rsp+30h] [rbp-40h] BYREF
  int v30; // [rsp+38h] [rbp-38h]
  CMRSWLock *v31; // [rsp+40h] [rbp-30h] BYREF
  int v32; // [rsp+48h] [rbp-28h]
  __int128 v33; // [rsp+50h] [rbp-20h] BYREF
  int v34; // [rsp+64h] [rbp-Ch]
  __int64 LockSemaphore; // [rsp+B0h] [rbp+40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp+48h]

  lpCriticalSection = this + 6;
  v2 = 0;
  v33 = 0;
  v34 = 0;
  EnterCriticalSection(this + 6);
  v30 = 0;
  v31 = (CMRSWLock *)&this[3];
  v32 = 0;
  v29 = (CMRSWLock *)this;
  CloseEndpointOutsideLock<CAutoWriterLock>(&v29, &this[7].OwningThread);
  CloseEndpointOutsideLock<CAutoWriterLock>(&v29, &this[7].LockSemaphore);
  CloseEndpointOutsideLock<CAutoWriterLock>(&v29, &this[7].SpinCount);
  v3 = CTimer<CTpSrvDataState>::Change(&this[12], 4294967294LL);
  ElValidateWin32(v3, v4, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x16Au);
  if ( v30 )
  {
    v5 = ++v30;
  }
  else
  {
    CAutoWriterLock::Lock((LPCRITICAL_SECTION *)&v29);
    v5 = v30;
  }
  v6 = v33;
  if ( this[20].LockSemaphore )
  {
    LockSemaphore = (__int64)this[20].LockSemaphore;
    do
    {
      v7 = CList<CMulticastNamespace,CNoLock>::DeleteAt(&this[20].LockSemaphore, &LockSemaphore);
      *(_QWORD *)(v7 + 456) = 0;
      *((_QWORD *)&v33 + 1) = v7;
      if ( v6 )
      {
        *(_QWORD *)(v7 + 464) = v8;
        *(_QWORD *)(v8 + 456) = v7;
      }
      else
      {
        v6 = v7;
        *(_QWORD *)&v33 = v7;
        *(_QWORD *)(v7 + 464) = 0;
      }
      v34 = ++v2;
    }
    while ( LockSemaphore );
  }
  v9 = v29;
  if ( v5 )
  {
    v10 = v5-- == 1;
    v30 = v5;
    if ( v10 )
      CMRSWLock::WriterRelease(v29);
  }
  CAutoWriterLock::Lock((LPCRITICAL_SECTION *)&v31);
  v11 = v32;
  v12 = v31;
  CDynArray<unsigned short *,CDeallocateString>::Clear(&this[27].LockSemaphore);
  if ( v11 )
  {
    v32 = v11 - 1;
    if ( v11 == 1 )
      CMRSWLock::WriterRelease(v12);
  }
  if ( v6 )
  {
    LockSemaphore = v6;
    do
    {
      v13 = (CMulticastNamespace *)CList<CMulticastNamespace,CNoLock>::DeleteAt(&v33, &LockSemaphore);
      v14 = CMulticastNamespace::Close(v13, 1);
      ElValidateWin32(v14, v15, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x189u);
      CMulticastNamespace::Cleanup(v13);
      v16 = CMulticastNamespace::Shutdown(v13);
      ElValidateWin32(v16, v17, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x18Bu);
      if ( v13 )
        (*(void (__fastcall **)(CMulticastNamespace *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    while ( LockSemaphore );
  }
  if ( v5 )
  {
    v18 = v5 + 1;
    v30 = v18;
  }
  else
  {
    CAutoWriterLock::Lock((LPCRITICAL_SECTION *)&v29);
    v18 = v30;
    v9 = v29;
  }
  v19 = *(_QWORD *)&this[21].LockCount;
  if ( v19 )
  {
    v20 = *(HKEY *)(v19 + 48);
    if ( v20 )
    {
      RegCloseKey(v20);
      *(_QWORD *)(v19 + 48) = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(v19 + 8));
    operator delete((void *)v19);
    *(_QWORD *)&this[21].LockCount = 0;
  }
  v21 = CContentProvidersHandler::Shutdown((CContentProvidersHandler *)&this[13].OwningThread);
  ElValidateWin32(v21, v22, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x199u);
  if ( LODWORD(this[20].OwningThread) )
    WdsAssert(
      "base\\eco\\wds\\transport\\server\\mc\\bandwidthmanager.cpp",
      0x4Du,
      "m_Interfaces.GetCount() == 0",
      v23,
      0);
  if ( hEventLog )
  {
    DeregisterEventSource(hEventLog);
    hEventLog = 0;
  }
  if ( this[28].RecursionCount )
  {
    WdsClientFreeLibrary();
    this[28].RecursionCount = 0;
  }
  if ( this[28].LockCount )
  {
    WSACleanup();
    this[28].LockCount = 0;
  }
  if ( v18 )
  {
    v30 = v18 - 1;
    if ( v18 == 1 )
      CMRSWLock::WriterRelease(v9);
  }
  v24 = qword_1800336E8;
  v25 = (struct _RTL_CRITICAL_SECTION *)((char *)qword_1800336E8 + 872);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)qword_1800336E8 + 872));
  ListDeleteAllObjects<CMulticastNotification::Callback,CNoLock>((char *)v24 + 920);
  *((_DWORD *)v24 + 228) = 1;
  LeaveCriticalSection(v25);
  while ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 236, 0) )
  {
    v27 = WaitForSingleObjectEx(*((HANDLE *)v24 + 119), 0x1F4u, 1);
    if ( v27 && v27 != 258 && v27 != 192 )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(0x80000u, L"CChildCount::WaitForChildren failed; %u", v27);
      break;
    }
  }
  ElValidateWin32(0, v26, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x1B7u);
  if ( v32 == 1 )
    CMRSWLock::WriterRelease(v31);
  if ( v30 == 1 )
    CMRSWLock::WriterRelease(v29);
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180005a4c  mov     [rsp-38h+arg_10], rbx
0x180005a51  push    rbp
0x180005a52  push    rsi
0x180005a53  push    rdi
0x180005a54  push    r12
0x180005a56  push    r13
0x180005a58  push    r14
0x180005a5a  push    r15
0x180005a5c  mov     rbp, rsp
0x180005a5f  sub     rsp, 70h
0x180005a63  lea     rax, [rcx+0F0h]
0x180005a6a  mov     rdi, rcx
0x180005a6d  xorps   xmm0, xmm0
0x180005a70  mov     [rbp+lpCriticalSection], rax
0x180005a74  xor     r15d, r15d
0x180005a77  mov     rcx, rax; lpCriticalSection
0x180005a7a  movdqu  [rbp+var_20], xmm0
0x180005a7f  mov     [rbp+var_C], r15d
0x180005a83  call    cs:__imp_EnterCriticalSection
0x180005a89  and     [rbp+var_38], r15d
0x180005a8d  lea     r13, [rdi+78h]
0x180005a91  xor     esi, esi
0x180005a93  mov     [rbp+var_30], r13
0x180005a97  lea     rdx, [rdi+128h]
0x180005a9e  mov     [rbp+var_28], esi
0x180005aa1  lea     rcx, [rbp+var_40]
0x180005aa5  mov     [rbp+var_40], rdi
0x180005aa9  call    ??$CloseEndpointOutsideLock@VCAutoWriterLock@@@@YAXAEAVCAutoWriterLock@@AEAPEAX@Z; CloseEndpointOutsideLock<CAutoWriterLock>(CAutoWriterLock &,void * &)
0x180005aae  lea     rdx, [rdi+130h]
0x180005ab5  lea     rcx, [rbp+var_40]
0x180005ab9  call    ??$CloseEndpointOutsideLock@VCAutoWriterLock@@@@YAXAEAVCAutoWriterLock@@AEAPEAX@Z; CloseEndpointOutsideLock<CAutoWriterLock>(CAutoWriterLock &,void * &)
0x180005abe  lea     rdx, [rdi+138h]
0x180005ac5  lea     rcx, [rbp+var_40]
0x180005ac9  call    ??$CloseEndpointOutsideLock@VCAutoWriterLock@@@@YAXAEAVCAutoWriterLock@@AEAPEAX@Z; CloseEndpointOutsideLock<CAutoWriterLock>(CAutoWriterLock &,void * &)
0x180005ace  lea     rcx, [rdi+1E0h]
0x180005ad5  mov     edx, 0FFFFFFFEh
0x180005ada  call    ?Change@?$CTimer@VCTpSrvDataState@@@@QEAAKKK@Z; CTimer<CTpSrvDataState>::Change(ulong,ulong)
0x180005adf  mov     ecx, eax; unsigned int
0x180005ae1  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005ae8  mov     r9d, 16Ah; unsigned int
0x180005aee  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005af3  mov     ebx, [rbp+var_38]
0x180005af6  test    ebx, ebx
0x180005af8  jnz     short loc_180005B08
0x180005afa  lea     rcx, [rbp+var_40]; this
0x180005afe  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180005b03  mov     ebx, [rbp+var_38]
0x180005b06  jmp     short loc_180005B0D
0x180005b08  inc     ebx
0x180005b0a  mov     [rbp+var_38], ebx
0x180005b0d  mov     r14, qword ptr [rbp+var_20]
0x180005b11  lea     r12, [rdi+338h]
0x180005b18  mov     rax, [r12]
0x180005b1c  test    rax, rax
0x180005b1f  jz      short loc_180005B75
0x180005b21  mov     r11, qword ptr [rbp+var_20+8]
0x180005b25  mov     [rbp+arg_0], rax
0x180005b29  lea     rdx, [rbp+arg_0]
0x180005b2d  mov     rcx, r12
0x180005b30  call    ?DeleteAt@?$CList@VCMulticastNamespace@@VCNoLock@@@@QEAAPEAVCMulticastNamespace@@AEAPEAX@Z; CList<CMulticastNamespace,CNoLock>::DeleteAt(void * &)
0x180005b35  xor     ecx, ecx
0x180005b37  mov     [rax+1C8h], rcx
0x180005b3e  mov     qword ptr [rbp+var_20+8], rax
0x180005b42  test    r14, r14
0x180005b45  jnz     short loc_180005B57
0x180005b47  mov     r14, rax
0x180005b4a  mov     qword ptr [rbp+var_20], rax
0x180005b4e  mov     [rax+1D0h], rcx
0x180005b55  jmp     short loc_180005B65
0x180005b57  mov     [rax+1D0h], r11
0x180005b5e  mov     [r11+1C8h], rax
0x180005b65  inc     r15d
0x180005b68  mov     r11, rax
0x180005b6b  mov     [rbp+var_C], r15d
0x180005b6f  cmp     [rbp+arg_0], rcx
0x180005b73  jnz     short loc_180005B29
0x180005b75  mov     r15, [rbp+var_40]
0x180005b79  xor     r12d, r12d
0x180005b7c  test    ebx, ebx
0x180005b7e  jz      short loc_180005B90
0x180005b80  add     ebx, 0FFFFFFFFh
0x180005b83  mov     [rbp+var_38], ebx
0x180005b86  jnz     short loc_180005B90
0x180005b88  mov     rcx, r15; this
0x180005b8b  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005b90  lea     rcx, [rbp+var_30]; this
0x180005b94  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180005b99  mov     esi, [rbp+var_28]
0x180005b9c  lea     rcx, [rdi+450h]
0x180005ba3  mov     r13, [rbp+var_30]
0x180005ba7  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x180005bac  test    esi, esi
0x180005bae  jz      short loc_180005BC0
0x180005bb0  add     esi, 0FFFFFFFFh
0x180005bb3  mov     [rbp+var_28], esi
0x180005bb6  jnz     short loc_180005BC0
0x180005bb8  mov     rcx, r13; this
0x180005bbb  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005bc0  test    r14, r14
0x180005bc3  jz      short loc_180005C39
0x180005bc5  mov     [rbp+arg_0], r14
0x180005bc9  lea     rdx, [rbp+arg_0]
0x180005bcd  lea     rcx, [rbp+var_20]
0x180005bd1  call    ?DeleteAt@?$CList@VCMulticastNamespace@@VCNoLock@@@@QEAAPEAVCMulticastNamespace@@AEAPEAX@Z; CList<CMulticastNamespace,CNoLock>::DeleteAt(void * &)
0x180005bd6  mov     edx, 1; int
0x180005bdb  mov     rcx, rax; this
0x180005bde  mov     rsi, rax
0x180005be1  call    ?Close@CMulticastNamespace@@QEAAKH@Z; CMulticastNamespace::Close(int)
0x180005be6  mov     ecx, eax; unsigned int
0x180005be8  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005bef  mov     r9d, 189h; unsigned int
0x180005bf5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005bfa  mov     rcx, rsi; this
0x180005bfd  call    ?Cleanup@CMulticastNamespace@@QEAAXXZ; CMulticastNamespace::Cleanup(void)
0x180005c02  mov     rcx, rsi; this
0x180005c05  call    ?Shutdown@CMulticastNamespace@@QEAAKXZ; CMulticastNamespace::Shutdown(void)
0x180005c0a  mov     ecx, eax; unsigned int
0x180005c0c  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005c13  mov     r9d, 18Bh; unsigned int
0x180005c19  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005c1e  test    rsi, rsi
0x180005c21  jz      short loc_180005C33
0x180005c23  mov     rax, [rsi]
0x180005c26  mov     rcx, rsi
0x180005c29  mov     rax, [rax+8]
0x180005c2d  call    cs:__guard_dispatch_icall_fptr
0x180005c33  cmp     [rbp+arg_0], r12
0x180005c37  jnz     short loc_180005BC9
0x180005c39  test    ebx, ebx
0x180005c3b  jnz     short loc_180005C4F
0x180005c3d  lea     rcx, [rbp+var_40]; this
0x180005c41  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180005c46  mov     ebx, [rbp+var_38]
0x180005c49  mov     r15, [rbp+var_40]
0x180005c4d  jmp     short loc_180005C54
0x180005c4f  inc     ebx
0x180005c51  mov     [rbp+var_38], ebx
0x180005c54  mov     rsi, [rdi+350h]
0x180005c5b  test    rsi, rsi
0x180005c5e  jz      short loc_180005C8C
0x180005c60  mov     rcx, [rsi+30h]; hKey
0x180005c64  test    rcx, rcx
0x180005c67  jz      short loc_180005C73
0x180005c69  call    cs:__imp_RegCloseKey
0x180005c6f  mov     [rsi+30h], r12
0x180005c73  lea     rcx, [rsi+8]; lpCriticalSection
0x180005c77  call    cs:__imp_DeleteCriticalSection
0x180005c7d  mov     rcx, rsi; void *
0x180005c80  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005c85  mov     [rdi+350h], r12
0x180005c8c  lea     rcx, [rdi+218h]; this
0x180005c93  call    ?Shutdown@CContentProvidersHandler@@QEAAKXZ; CContentProvidersHandler::Shutdown(void)
0x180005c98  mov     ecx, eax; unsigned int
0x180005c9a  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005ca1  mov     r9d, 199h; unsigned int
0x180005ca7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005cac  cmp     [rdi+330h], r12d
0x180005cb3  jz      short loc_180005CD2
0x180005cb5  lea     r8, aMInterfacesGet; "m_Interfaces.GetCount() == 0"
0x180005cbc  mov     [rsp+70h+var_50], r12d; int
0x180005cc1  mov     edx, 4Dh ; 'M'; unsigned int
0x180005cc6  lea     rcx, aBaseEcoWdsTran_20; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005ccd  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180005cd2  mov     rcx, cs:hEventLog; hEventLog
0x180005cd9  test    rcx, rcx
0x180005cdc  jz      short loc_180005CEB
0x180005cde  call    cs:__imp_DeregisterEventSource
0x180005ce4  mov     cs:hEventLog, r12
0x180005ceb  cmp     [rdi+46Ch], r12d
0x180005cf2  jz      short loc_180005D01
0x180005cf4  call    cs:__imp_WdsClientFreeLibrary
0x180005cfa  mov     [rdi+46Ch], r12d
0x180005d01  cmp     [rdi+468h], r12d
0x180005d08  jz      short loc_180005D17
0x180005d0a  call    cs:__imp_WSACleanup
0x180005d10  mov     [rdi+468h], r12d
0x180005d17  test    ebx, ebx
0x180005d19  jz      short loc_180005D2B
0x180005d1b  add     ebx, 0FFFFFFFFh
0x180005d1e  mov     [rbp+var_38], ebx
0x180005d21  jnz     short loc_180005D2B
0x180005d23  mov     rcx, r15; this
0x180005d26  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005d2b  mov     rdi, cs:qword_1800336E8
0x180005d32  lea     rbx, [rdi+368h]
0x180005d39  mov     rcx, rbx; lpCriticalSection
0x180005d3c  call    cs:__imp_EnterCriticalSection
0x180005d42  lea     rcx, [rdi+398h]
0x180005d49  call    ??$ListDeleteAllObjects@UCallback@CMulticastNotification@@VCNoLock@@@@YAXPEAV?$CList@UCallback@CMulticastNotification@@VCNoLock@@@@@Z; ListDeleteAllObjects<CMulticastNotification::Callback,CNoLock>(CList<CMulticastNotification::Callback,CNoLock> *)
0x180005d4e  mov     rcx, rbx; lpCriticalSection
0x180005d51  mov     dword ptr [rdi+390h], 1
0x180005d5b  call    cs:__imp_LeaveCriticalSection
0x180005d61  mov     eax, r12d
0x180005d64  lock xadd [rdi+3B0h], eax
0x180005d6c  test    eax, eax
0x180005d6e  jz      short loc_180005DBE
0x180005d70  mov     rcx, [rdi+3B8h]; hHandle
0x180005d77  mov     edx, 1F4h; dwMilliseconds
0x180005d7c  mov     r8d, 1; bAlertable
0x180005d82  call    cs:__imp_WaitForSingleObjectEx
0x180005d88  test    eax, eax
0x180005d8a  jz      short loc_180005D61
0x180005d8c  cmp     eax, 102h
0x180005d91  jz      short loc_180005D61
0x180005d93  cmp     eax, 0C0h
0x180005d98  jz      short loc_180005D61
0x180005d9a  mov     r9, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180005da1  test    r9, r9
0x180005da4  jz      short loc_180005DBE
0x180005da6  mov     r8d, eax
0x180005da9  lea     rdx, aCchildcountWai; "CChildCount::WaitForChildren failed; %u"
0x180005db0  mov     rax, r9
0x180005db3  mov     ecx, 80000h
0x180005db8  call    cs:__guard_dispatch_icall_fptr
0x180005dbe  mov     r9d, 1B7h; unsigned int
0x180005dc4  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005dcb  xor     ecx, ecx; unsigned int
0x180005dcd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005dd2  mov     eax, [rbp+var_28]
0x180005dd5  test    eax, eax
0x180005dd7  jz      short loc_180005DE7
0x180005dd9  cmp     eax, 1
0x180005ddc  jnz     short loc_180005DE7
0x180005dde  mov     rcx, [rbp+var_30]; this
0x180005de2  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005de7  mov     eax, [rbp+var_38]
0x180005dea  test    eax, eax
0x180005dec  jz      short loc_180005DFC
0x180005dee  cmp     eax, 1
0x180005df1  jnz     short loc_180005DFC
0x180005df3  mov     rcx, [rbp+var_40]; this
0x180005df7  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005dfc  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180005e00  call    cs:__imp_LeaveCriticalSection
0x180005e06  mov     rbx, [rsp+70h+arg_10]
0x180005e0e  xor     eax, eax
0x180005e10  add     rsp, 70h
0x180005e14  pop     r15
0x180005e16  pop     r14
0x180005e18  pop     r13
0x180005e1a  pop     r12
0x180005e1c  pop     rdi
0x180005e1d  pop     rsi
0x180005e1e  pop     rbp
0x180005e1f  retn
```
