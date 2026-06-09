# CTftpServer::Shutdown(void)

- ea: `0x180001754`
- end: `0x180001948`
- name: `?Shutdown@CTftpServer@@QEAAKXZ`
- size: `500`
- prototype: `__int64 __fastcall(CTftpServer *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180005c50`

## callees

- `0x180001754`
- `0x180002ccc`
- `0x180002f08`
- `0x180002f8c`
- `0x180002ff4`
- `0x18000313c`
- `0x180003170`
- `0x1800036ac`
- `0x1800094bc`
- `0x18000a960`
- `0x18000a9a8`
- `0x18003a940`
- `0x18003c514`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180001776`
- `KERNEL32!EnterCriticalSection` at `0x180001776`
- `KERNEL32!LeaveCriticalSection` at `0x180001920`
- `KERNEL32!LeaveCriticalSection` at `0x180001920`
- `WDSCSL!WdsClientFreeLibrary` at `0x1800018c2`
- `WDSCSL!WdsClientFreeLibrary` at `0x1800018c2`
- `WS2_32!__imp_WSACleanup` at `0x1800018de`
- `WS2_32!__imp_WSACleanup` at `0x1800018de`

## pseudocode

```c
__int64 __fastcall CTftpServer::Shutdown(CTftpServer *this)
{
  int v2; // edi
  const char *v3; // rdx
  int v4; // r9d
  unsigned int v5; // eax
  const char *v6; // rdx
  unsigned int v7; // eax
  const char *v8; // rdx
  int v9; // edi
  unsigned int v10; // eax
  const char *v11; // rdx
  void *v12; // rcx
  CMRSWLock *v14; // [rsp+30h] [rbp-20h] BYREF
  int v15; // [rsp+38h] [rbp-18h]
  char *v16; // [rsp+40h] [rbp-10h] BYREF
  int v17; // [rsp+48h] [rbp-8h]

  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  v15 = 0;
  v14 = this;
  CloseEndpointOutsideLock<CAutoWriterLock>(&v14, (char *)this + 184);
  CloseEndpointOutsideLock<CAutoWriterLock>(&v14, (char *)this + 192);
  v17 = 0;
  v16 = (char *)this + 200;
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(&v16);
  _InterlockedExchange((volatile __int32 *)this + 60, 1);
  v2 = v17;
  if ( v17 )
  {
    CAutoTypeLock<CSpinLock>::Unlock(&v16);
    v2 = v17;
  }
  CTimer<CTftpSession>::Delete((char *)this + 200);
  if ( v2 )
  {
    CAutoTypeLock<CSpinLock>::Unlock(&v16);
    if ( v17 )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h", 0x16Au, "m_uLockCount == 0", v4, 0);
  }
  ElValidateWin32(0, v3, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x148u);
  v5 = CClientContext::Shutdown((CTftpServer *)((char *)this + 320));
  ElValidateWin32(v5, v6, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x14Du);
  v7 = CTftpReadFileManager::Shutdown((LPCRITICAL_SECTION)((char *)this + 576));
  ElValidateWin32(v7, v8, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x152u);
  if ( v15 )
  {
    v9 = v15 + 1;
  }
  else
  {
    CAutoWriterLock::Lock((CAutoWriterLock *)&v14);
    v9 = v15;
  }
  v10 = CFolderFilter::Shutdown((LPCRITICAL_SECTION)((char *)this + 264));
  ElValidateWin32(v10, v11, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x159u);
  v12 = (void *)*((_QWORD *)this + 32);
  if ( v12 )
  {
    operator delete(v12);
    *((_QWORD *)this + 32) = 0;
  }
  *((_QWORD *)this + 21) = 0;
  if ( *((_DWORD *)this + 857) )
  {
    WdsClientFreeLibrary();
    *((_DWORD *)this + 857) = 0;
  }
  if ( *((_DWORD *)this + 856) )
  {
    WSACleanup();
    *((_DWORD *)this + 856) = 0;
  }
  if ( v9 )
  {
    if ( !--v9 )
      CMRSWLock::WriterRelease(v14);
  }
  McGenEventUnregister();
  if ( v9 == 1 )
    CMRSWLock::WriterRelease(v14);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
  return 0;
}

```

## disassembly

```asm
0x180001754  mov     rax, rsp
0x180001757  mov     [rax+8], rbx
0x18000175b  mov     [rax+10h], rsi
0x18000175f  mov     [rax+18h], rdi
0x180001763  mov     [rax+20h], r14
0x180001767  push    rbp
0x180001768  mov     rbp, rsp
0x18000176b  sub     rsp, 50h
0x18000176f  mov     rbx, rcx
0x180001772  add     rcx, 78h ; 'x'; lpCriticalSection
0x180001776  call    cs:__imp_EnterCriticalSection
0x18000177d  nop     dword ptr [rax+rax+00h]
0x180001782  and     [rbp+var_18], 0
0x180001786  lea     rdx, [rbx+0B8h]
0x18000178d  lea     rcx, [rbp+var_20]
0x180001791  mov     [rbp+var_20], rbx
0x180001795  call    ??$CloseEndpointOutsideLock@VCAutoWriterLock@@@@YAXAEAVCAutoWriterLock@@AEAPEAX@Z; CloseEndpointOutsideLock<CAutoWriterLock>(CAutoWriterLock &,void * &)
0x18000179a  lea     rdx, [rbx+0C0h]
0x1800017a1  lea     rcx, [rbp+var_20]
0x1800017a5  call    ??$CloseEndpointOutsideLock@VCAutoWriterLock@@@@YAXAEAVCAutoWriterLock@@AEAPEAX@Z; CloseEndpointOutsideLock<CAutoWriterLock>(CAutoWriterLock &,void * &)
0x1800017aa  and     [rbp+var_8], 0
0x1800017ae  lea     rsi, [rbx+0C8h]
0x1800017b5  lea     rcx, [rbp+var_10]
0x1800017b9  mov     [rbp+var_10], rsi
0x1800017bd  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x1800017c2  mov     eax, 1
0x1800017c7  xchg    eax, [rsi+28h]
0x1800017ca  mov     edi, [rbp+var_8]
0x1800017cd  test    edi, edi
0x1800017cf  jz      short loc_1800017DD
0x1800017d1  lea     rcx, [rbp+var_10]
0x1800017d5  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x1800017da  mov     edi, [rbp+var_8]
0x1800017dd  mov     rcx, rsi
0x1800017e0  call    ?Delete@?$CTimer@VCTftpSession@@@@AEAAXXZ; CTimer<CTftpSession>::Delete(void)
0x1800017e5  test    edi, edi
0x1800017e7  jz      short loc_180001816
0x1800017e9  lea     rcx, [rbp+var_10]
0x1800017ed  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x1800017f2  mov     edi, [rbp+var_8]
0x1800017f5  test    edi, edi
0x1800017f7  jz      short loc_180001816
0x1800017f9  and     [rsp+50h+var_30], 0
0x1800017fe  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180001805  mov     edx, 16Ah; unsigned int
0x18000180a  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x180001811  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180001816  lea     rsi, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000181d  mov     r9d, 148h; unsigned int
0x180001823  mov     r8, rsi; char *
0x180001826  xor     ecx, ecx; unsigned int
0x180001828  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000182d  lea     rcx, [rbx+140h]; this
0x180001834  call    ?Shutdown@CClientContext@@QEAAKXZ; CClientContext::Shutdown(void)
0x180001839  mov     ecx, eax; unsigned int
0x18000183b  mov     r9d, 14Dh; unsigned int
0x180001841  mov     r8, rsi; char *
0x180001844  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001849  lea     rcx, [rbx+240h]; lpCriticalSection
0x180001850  call    ?Shutdown@CTftpReadFileManager@@QEAAKXZ; CTftpReadFileManager::Shutdown(void)
0x180001855  mov     ecx, eax; unsigned int
0x180001857  mov     r9d, 152h; unsigned int
0x18000185d  mov     r8, rsi; char *
0x180001860  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001865  mov     edi, [rbp+var_18]
0x180001868  test    edi, edi
0x18000186a  jnz     short loc_18000187A
0x18000186c  lea     rcx, [rbp+var_20]; this
0x180001870  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180001875  mov     edi, [rbp+var_18]
0x180001878  jmp     short loc_18000187C
0x18000187a  inc     edi
0x18000187c  lea     rcx, [rbx+108h]; lpCriticalSection
0x180001883  call    ?Shutdown@CFolderFilter@@QEAAKXZ; CFolderFilter::Shutdown(void)
0x180001888  mov     ecx, eax; unsigned int
0x18000188a  mov     r9d, 159h; unsigned int
0x180001890  mov     r8, rsi; char *
0x180001893  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001898  mov     rcx, [rbx+100h]; void *
0x18000189f  test    rcx, rcx
0x1800018a2  jz      short loc_1800018B1
0x1800018a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800018a9  and     qword ptr [rbx+100h], 0
0x1800018b1  and     qword ptr [rbx+0A8h], 0
0x1800018b9  cmp     dword ptr [rbx+0D64h], 0
0x1800018c0  jz      short loc_1800018D5
0x1800018c2  call    cs:__imp_WdsClientFreeLibrary
0x1800018c9  nop     dword ptr [rax+rax+00h]
0x1800018ce  and     dword ptr [rbx+0D64h], 0
0x1800018d5  cmp     dword ptr [rbx+0D60h], 0
0x1800018dc  jz      short loc_1800018F1
0x1800018de  call    cs:__imp_WSACleanup
0x1800018e5  nop     dword ptr [rax+rax+00h]
0x1800018ea  and     dword ptr [rbx+0D60h], 0
0x1800018f1  test    edi, edi
0x1800018f3  jz      short loc_180001903
0x1800018f5  add     edi, 0FFFFFFFFh
0x1800018f8  jnz     short loc_180001903
0x1800018fa  mov     rcx, [rbp+var_20]; this
0x1800018fe  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180001903  call    McGenEventUnregister
0x180001908  test    edi, edi
0x18000190a  jz      short loc_18000191C
0x18000190c  lea     eax, [rdi-1]
0x18000190f  test    eax, eax
0x180001911  jnz     short loc_18000191C
0x180001913  mov     rcx, [rbp+var_20]; this
0x180001917  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x18000191c  lea     rcx, [rbx+78h]; lpCriticalSection
0x180001920  call    cs:__imp_LeaveCriticalSection
0x180001927  nop     dword ptr [rax+rax+00h]
0x18000192c  mov     rbx, [rsp+50h+arg_0]
0x180001931  xor     eax, eax
0x180001933  mov     rsi, [rsp+50h+arg_8]
0x180001938  mov     rdi, [rsp+50h+arg_10]
0x18000193d  mov     r14, [rsp+50h+arg_18]
0x180001942  add     rsp, 50h
0x180001946  pop     rbp
0x180001947  retn
```
