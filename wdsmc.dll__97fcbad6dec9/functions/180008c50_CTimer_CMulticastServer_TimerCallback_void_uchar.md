# CTimer<CMulticastServer>::_TimerCallback(void *,uchar)

- ea: `0x180008c50`
- end: `0x180008d31`
- name: `?_TimerCallback@?$CTimer@VCMulticastServer@@@@SAXPEAXE@Z`
- size: `225`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007a24`
- `0x180008aa0`
- `0x180008c50`
- `0x180008d38`
- `0x1800227d4`
- `0x180025850`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008c6e`
- `KERNEL32!GetCurrentThreadId` at `0x180008ca9`
- `KERNEL32!GetCurrentThreadId` at `0x180008c6e`
- `KERNEL32!GetCurrentThreadId` at `0x180008ca9`
- `KERNEL32!SwitchToThread` at `0x180008c89`
- `KERNEL32!SwitchToThread` at `0x180008c89`

## string_xrefs

- `0x180008cbe`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
void __fastcall CTimer<CMulticastServer>::_TimerCallback(PVOID a1)
{
  int v2; // edi
  DWORD CurrentThreadId; // ecx
  signed __int32 v4; // eax
  BOOL v5; // edi
  DWORD v6; // eax
  int v7; // r9d
  CMulticastServer *v8; // rbx
  unsigned int v9; // eax
  const char *v10; // rdx
  PVOID v11; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+38h] [rbp-10h]

  v12 = 0;
  v11 = a1;
  while ( 1 )
  {
    v2 = 0;
    if ( *((_DWORD *)a1 + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)a1, CurrentThreadId, 0);
    if ( !v4 || v4 == CurrentThreadId )
      break;
    if ( (unsigned int)++v2 >= *((_DWORD *)a1 + 2) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)a1 + 1);
  v5 = _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 10, 0) == 0;
  v12 = 0;
  v6 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0) != v6 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v7,
      0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 1, 0xFFFFFFFF) == 1 )
    _InterlockedExchange((volatile __int32 *)a1, 0);
  if ( v5 )
  {
    v8 = (CMulticastServer *)*((_QWORD *)a1 + 4);
    CMulticastServer::UpdateNamespaces(v8);
    v9 = CTimer<CTpSrvDataState>::Change((char *)v8 + 480, 30000);
    ElValidateWin32(v9, v10, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x95Au);
  }
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v11);
}

```

## disassembly

```asm
0x180008c50  mov     [rsp+arg_0], rbx
0x180008c55  push    rdi
0x180008c56  sub     rsp, 40h
0x180008c5a  and     [rsp+48h+var_10], 0
0x180008c5f  mov     rbx, rcx
0x180008c62  mov     [rsp+48h+var_18], rcx
0x180008c67  xor     edi, edi
0x180008c69  cmp     [rbx+8], edi
0x180008c6c  jbe     short loc_180008C89
0x180008c6e  call    cs:__imp_GetCurrentThreadId
0x180008c74  mov     ecx, eax
0x180008c76  xor     eax, eax
0x180008c78  lock cmpxchg [rbx], ecx
0x180008c7c  jz      short loc_180008C91
0x180008c7e  cmp     eax, ecx
0x180008c80  jz      short loc_180008C91
0x180008c82  inc     edi
0x180008c84  cmp     edi, [rbx+8]
0x180008c87  jb      short loc_180008C6E
0x180008c89  call    cs:__imp_SwitchToThread
0x180008c8f  jmp     short loc_180008C67
0x180008c91  lock inc dword ptr [rbx+4]
0x180008c95  xor     eax, eax
0x180008c97  lock xadd [rbx+28h], eax
0x180008c9c  xor     edi, edi
0x180008c9e  test    eax, eax
0x180008ca0  setz    dil
0x180008ca4  and     [rsp+48h+var_10], 0
0x180008ca9  call    cs:__imp_GetCurrentThreadId
0x180008caf  xor     ecx, ecx
0x180008cb1  lock xadd [rbx], ecx
0x180008cb5  cmp     ecx, eax
0x180008cb7  jz      short loc_180008CD6
0x180008cb9  and     [rsp+48h+var_28], 0
0x180008cbe  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180008cc5  mov     edx, 99h; unsigned int
0x180008cca  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180008cd1  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180008cd6  or      eax, 0FFFFFFFFh
0x180008cd9  lock xadd [rbx+4], eax
0x180008cde  cmp     eax, 1
0x180008ce1  jnz     short loc_180008CE7
0x180008ce3  xor     eax, eax
0x180008ce5  xchg    eax, [rbx]
0x180008ce7  test    edi, edi
0x180008ce9  jz      short loc_180008D1C
0x180008ceb  mov     rbx, [rbx+20h]
0x180008cef  mov     rcx, rbx; this
0x180008cf2  call    ?UpdateNamespaces@CMulticastServer@@AEAAXXZ; CMulticastServer::UpdateNamespaces(void)
0x180008cf7  lea     rcx, [rbx+1E0h]
0x180008cfe  mov     edx, 7530h
0x180008d03  call    ?Change@?$CTimer@VCTpSrvDataState@@@@QEAAKKK@Z; CTimer<CTpSrvDataState>::Change(ulong,ulong)
0x180008d08  mov     ecx, eax; unsigned int
0x180008d0a  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180008d11  mov     r9d, 95Ah; unsigned int
0x180008d17  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008d1c  lea     rcx, [rsp+48h+var_18]
0x180008d21  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180008d26  mov     rbx, [rsp+48h+arg_0]
0x180008d2b  add     rsp, 40h
0x180008d2f  pop     rdi
0x180008d30  retn
```
