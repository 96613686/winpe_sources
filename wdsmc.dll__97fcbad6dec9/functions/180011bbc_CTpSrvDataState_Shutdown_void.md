# CTpSrvDataState::Shutdown(void)

- ea: `0x180011bbc`
- end: `0x180011d5e`
- name: `?Shutdown@CTpSrvDataState@@QEAAKXZ`
- size: `418`
- prototype: `unsigned int __fastcall(CTpSrvDataState *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001198c`
- `0x180011a4c`
- `0x1800150c0`

## callees

- `0x180008738`
- `0x180008d38`
- `0x18000d978`
- `0x180011220`
- `0x180011bbc`
- `0x180014108`
- `0x18001a9a8`
- `0x1800227d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011c34`
- `KERNEL32!GetCurrentThreadId` at `0x180011c68`
- `KERNEL32!GetCurrentThreadId` at `0x180011c34`
- `KERNEL32!GetCurrentThreadId` at `0x180011c68`
- `KERNEL32!SwitchToThread` at `0x180011c4f`
- `KERNEL32!SwitchToThread` at `0x180011c4f`
- `KERNEL32!LeaveCriticalSection` at `0x180011d37`
- `KERNEL32!LeaveCriticalSection` at `0x180011d37`
- `KERNEL32!EnterCriticalSection` at `0x180011cca`
- `KERNEL32!EnterCriticalSection` at `0x180011cca`

## string_xrefs

- `0x180011c82`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
__int64 __fastcall CTpSrvDataState::Shutdown(CTpSrvDataState *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r12
  unsigned int v3; // eax
  const char *v4; // rdx
  unsigned int v5; // eax
  const char *v6; // rdx
  volatile signed __int32 *v7; // rbx
  int v8; // edi
  DWORD CurrentThreadId; // ecx
  signed __int32 v10; // eax
  DWORD v11; // eax
  int v12; // r9d
  const char *v13; // rdx
  __int64 v14; // rdi
  unsigned int *v15; // rsi
  unsigned int i; // ebx
  _QWORD *v17; // rbp
  __int64 v18; // rcx
  char *v20; // [rsp+30h] [rbp-28h] BYREF
  int v21; // [rsp+38h] [rbp-20h]

  v1 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  v3 = CTpSrvSPM::Shutdown((CTpSrvDataState *)((char *)this + 48));
  ElValidateWin32(v3, v4, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x97u);
  v5 = CTpSrvTxRate::Shutdown((CTpSrvDataState *)((char *)this + 192));
  ElValidateWin32(v5, v6, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x98u);
  v21 = 0;
  v7 = (volatile signed __int32 *)((char *)this + 592);
  v20 = (char *)this + 592;
  while ( 1 )
  {
    v8 = 0;
    if ( *((_DWORD *)this + 150) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = _InterlockedCompareExchange(v7, CurrentThreadId, 0);
    if ( !v10 || v10 == CurrentThreadId )
      break;
    if ( (unsigned int)++v8 >= *((_DWORD *)this + 150) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 149);
  _InterlockedExchange((volatile __int32 *)this + 158, 1);
  v21 = 0;
  v11 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd(v7, 0) != v11 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v12,
      0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 149, 0xFFFFFFFF) == 1 )
    _InterlockedExchange(v7, 0);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)this + 592);
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v20);
  ElValidateWin32(0, v13, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x99u);
  EnterCriticalSection(v1);
  v14 = *((_QWORD *)this + 46);
  while ( v14 )
  {
    v15 = (unsigned int *)v14;
    v14 = *(_QWORD *)(v14 + 65544);
    for ( i = *v15; i <= v15[1]; ++i )
    {
      v17 = *(_QWORD **)&v15[2 * i + 2];
      if ( v17 )
      {
        v18 = v17[4];
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
          v17[4] = 0;
        }
        operator delete(v17);
      }
    }
  }
  ListDeleteAllObjects<CDynList<CTpSrvDataState::DataPacket,CNoLock>::Element,CNoLock>((char *)this + 368);
  *((_DWORD *)this + 98) = 0;
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x180011bbc  mov     rax, rsp
0x180011bbf  mov     [rax+8], rbx
0x180011bc3  mov     [rax+10h], rbp
0x180011bc7  mov     [rax+18h], rsi
0x180011bcb  mov     [rax+20h], rdi
0x180011bcf  push    r12
0x180011bd1  push    r14
0x180011bd3  push    r15
0x180011bd5  sub     rsp, 40h
0x180011bd9  mov     r12, [rcx+8]
0x180011bdd  mov     r15, rcx
0x180011be0  add     rcx, 30h ; '0'; this
0x180011be4  call    ?Shutdown@CTpSrvSPM@@QEAAKXZ; CTpSrvSPM::Shutdown(void)
0x180011be9  lea     rsi, aBaseEcoWdsTran_21; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180011bf0  mov     ecx, eax; unsigned int
0x180011bf2  mov     r8, rsi; char *
0x180011bf5  mov     r9d, 97h; unsigned int
0x180011bfb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011c00  lea     rcx, [r15+0C0h]; this
0x180011c07  call    ?Shutdown@CTpSrvTxRate@@QEAAKXZ; CTpSrvTxRate::Shutdown(void)
0x180011c0c  mov     ecx, eax; unsigned int
0x180011c0e  mov     r9d, 98h; unsigned int
0x180011c14  mov     r8, rsi; char *
0x180011c17  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011c1c  and     [rsp+58h+var_20], 0
0x180011c21  lea     rbx, [r15+250h]
0x180011c28  mov     [rsp+58h+var_28], rbx
0x180011c2d  xor     edi, edi
0x180011c2f  cmp     [rbx+8], edi
0x180011c32  jbe     short loc_180011C4F
0x180011c34  call    cs:__imp_GetCurrentThreadId
0x180011c3a  mov     ecx, eax
0x180011c3c  xor     eax, eax
0x180011c3e  lock cmpxchg [rbx], ecx
0x180011c42  jz      short loc_180011C57
0x180011c44  cmp     eax, ecx
0x180011c46  jz      short loc_180011C57
0x180011c48  inc     edi
0x180011c4a  cmp     edi, [rbx+8]
0x180011c4d  jb      short loc_180011C34
0x180011c4f  call    cs:__imp_SwitchToThread
0x180011c55  jmp     short loc_180011C2D
0x180011c57  lock inc dword ptr [rbx+4]
0x180011c5b  mov     eax, 1
0x180011c60  xchg    eax, [rbx+28h]
0x180011c63  and     [rsp+58h+var_20], 0
0x180011c68  call    cs:__imp_GetCurrentThreadId
0x180011c6e  xor     ecx, ecx
0x180011c70  lock xadd [rbx], ecx
0x180011c74  mov     edi, 99h
0x180011c79  cmp     ecx, eax
0x180011c7b  jz      short loc_180011C97
0x180011c7d  and     [rsp+58h+var_38], 0
0x180011c82  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180011c89  mov     edx, edi; unsigned int
0x180011c8b  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180011c92  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180011c97  or      eax, 0FFFFFFFFh
0x180011c9a  lock xadd [rbx+4], eax
0x180011c9f  cmp     eax, 1
0x180011ca2  jnz     short loc_180011CA8
0x180011ca4  xor     eax, eax
0x180011ca6  xchg    eax, [rbx]
0x180011ca8  mov     rcx, rbx
0x180011cab  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x180011cb0  lea     rcx, [rsp+58h+var_28]
0x180011cb5  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180011cba  mov     r9d, edi; unsigned int
0x180011cbd  mov     r8, rsi; char *
0x180011cc0  xor     ecx, ecx; unsigned int
0x180011cc2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011cc7  mov     rcx, r12; lpCriticalSection
0x180011cca  call    cs:__imp_EnterCriticalSection
0x180011cd0  lea     r14, [r15+170h]
0x180011cd7  mov     rdi, [r14]
0x180011cda  jmp     short loc_180011D20
0x180011cdc  lea     rsi, [rdi]
0x180011cdf  mov     rdi, [rdi+10008h]
0x180011ce6  mov     ebx, [rsi]
0x180011ce8  jmp     short loc_180011D1B
0x180011cea  mov     eax, ebx
0x180011cec  mov     rbp, [rsi+rax*8+8]
0x180011cf1  test    rbp, rbp
0x180011cf4  jz      short loc_180011D19
0x180011cf6  mov     rcx, [rbp+20h]
0x180011cfa  test    rcx, rcx
0x180011cfd  jz      short loc_180011D11
0x180011cff  mov     rax, [rcx]
0x180011d02  mov     rax, [rax+8]
0x180011d06  call    cs:__guard_dispatch_icall_fptr
0x180011d0c  and     qword ptr [rbp+20h], 0
0x180011d11  mov     rcx, rbp; void *
0x180011d14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011d19  inc     ebx
0x180011d1b  cmp     ebx, [rsi+4]
0x180011d1e  jbe     short loc_180011CEA
0x180011d20  test    rdi, rdi
0x180011d23  jnz     short loc_180011CDC
0x180011d25  mov     rcx, r14
0x180011d28  call    ??$ListDeleteAllObjects@UElement@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@VCNoLock@@@@YAXPEAV?$CList@UElement@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@VCNoLock@@@@@Z; ListDeleteAllObjects<CDynList<CTpSrvDataState::DataPacket,CNoLock>::Element,CNoLock>(CList<CDynList<CTpSrvDataState::DataPacket,CNoLock>::Element,CNoLock> *)
0x180011d2d  and     [r15+188h], edi
0x180011d34  mov     rcx, r12; lpCriticalSection
0x180011d37  call    cs:__imp_LeaveCriticalSection
0x180011d3d  mov     rbx, [rsp+58h+arg_0]
0x180011d42  xor     eax, eax
0x180011d44  mov     rbp, [rsp+58h+arg_8]
0x180011d49  mov     rsi, [rsp+58h+arg_10]
0x180011d4e  mov     rdi, [rsp+58h+arg_18]
0x180011d53  add     rsp, 40h
0x180011d57  pop     r15
0x180011d59  pop     r14
0x180011d5b  pop     r12
0x180011d5d  retn
```
