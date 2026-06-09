# CTpSrvKickDemote::RemoveClient(ulong)

- ea: `0x18000e968`
- end: `0x18000ea76`
- name: `?RemoveClient@CTpSrvKickDemote@@QEAAKK@Z`
- size: `270`
- prototype: `unsigned int __fastcall(CTpSrvKickDemote *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000fddc`
- `0x18001050c`

## callees

- `0x180008aa0`
- `0x18000e968`
- `0x18000f334`
- `0x18001a9a8`
- `0x180025850`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000ea59`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea59`
- `KERNEL32!EnterCriticalSection` at `0x18000e989`
- `KERNEL32!EnterCriticalSection` at `0x18000e989`

## pseudocode

```c
__int64 __fastcall CTpSrvKickDemote::RemoveClient(CTpSrvKickDemote *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  unsigned int v5; // edi
  void *v6; // rax
  const char *v7; // rdx
  void *v8; // rax
  const char *v9; // rdx

  v2 = *(struct _RTL_CRITICAL_SECTION **)this;
  v5 = 0;
  EnterCriticalSection(*(LPCRITICAL_SECTION *)this);
  v6 = (void *)CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::RemoveItem<unsigned long>((char *)this + 24, a2, a2);
  if ( v6 )
  {
    operator delete(v6);
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 686, 0) )
    {
      if ( *((_DWORD *)this + 1398) )
      {
        v5 = CTimer<CTpSrvDataState>::Change((__int64)this + 5480, 0xFFFFFFFE);
        if ( ElValidateWin32(v5, v7, "base\\eco\\wds\\transport\\server\\mc\\tpsrvkickdemote.cpp", 0x1A1u) )
          goto LABEL_11;
        *((_DWORD *)this + 1398) = 0;
      }
    }
  }
  v8 = (void *)CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::RemoveItem<unsigned long>(
                 (char *)this + 2752,
                 a2,
                 a2);
  if ( v8 )
  {
    operator delete(v8);
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 1368, 0) )
    {
      if ( *((_DWORD *)this + 1399) )
      {
        v5 = CTimer<CTpSrvDataState>::Change((__int64)this + 5536, 0xFFFFFFFE);
        if ( !ElValidateWin32(v5, v9, "base\\eco\\wds\\transport\\server\\mc\\tpsrvkickdemote.cpp", 0x1B2u) )
          *((_DWORD *)this + 1399) = 0;
      }
    }
  }
LABEL_11:
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18000e968  mov     [rsp+arg_0], rbx
0x18000e96d  mov     [rsp+arg_8], rbp
0x18000e972  mov     [rsp+arg_10], rsi
0x18000e977  push    rdi
0x18000e978  sub     rsp, 20h
0x18000e97c  mov     rbp, [rcx]
0x18000e97f  mov     rbx, rcx
0x18000e982  mov     rcx, rbp; lpCriticalSection
0x18000e985  mov     esi, edx
0x18000e987  xor     edi, edi
0x18000e989  call    cs:__imp_EnterCriticalSection
0x18000e98f  lea     rcx, [rbx+18h]
0x18000e993  mov     r8d, esi
0x18000e996  mov     edx, esi
0x18000e998  call    ??$RemoveItem@K@?$CSmHashTable@UClient@CTpSrvKickDemote@@VCNoLock@@$0HB@@@QEAAPEAUClient@CTpSrvKickDemote@@KK@Z; CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::RemoveItem<ulong>(ulong,ulong)
0x18000e99d  test    rax, rax
0x18000e9a0  jz      short loc_18000E9F1
0x18000e9a2  mov     rcx, rax; void *
0x18000e9a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e9aa  xor     eax, eax
0x18000e9ac  lock xadd [rbx+0AB8h], eax
0x18000e9b4  test    eax, eax
0x18000e9b6  jnz     short loc_18000E9F1
0x18000e9b8  cmp     [rbx+15D8h], edi
0x18000e9be  jz      short loc_18000E9F1
0x18000e9c0  lea     rcx, [rbx+1568h]
0x18000e9c7  mov     edx, 0FFFFFFFEh
0x18000e9cc  call    ?Change@?$CTimer@VCTpSrvDataState@@@@QEAAKKK@Z; CTimer<CTpSrvDataState>::Change(ulong,ulong)
0x18000e9d1  mov     r9d, 1A1h; unsigned int
0x18000e9d7  lea     r8, aBaseEcoWdsTran_18; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000e9de  mov     ecx, eax; unsigned int
0x18000e9e0  mov     edi, eax
0x18000e9e2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e9e7  test    eax, eax
0x18000e9e9  jnz     short loc_18000EA56
0x18000e9eb  and     [rbx+15D8h], eax
0x18000e9f1  lea     rcx, [rbx+0AC0h]
0x18000e9f8  mov     r8d, esi
0x18000e9fb  mov     edx, esi
0x18000e9fd  call    ??$RemoveItem@K@?$CSmHashTable@UClient@CTpSrvKickDemote@@VCNoLock@@$0HB@@@QEAAPEAUClient@CTpSrvKickDemote@@KK@Z; CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::RemoveItem<ulong>(ulong,ulong)
0x18000ea02  test    rax, rax
0x18000ea05  jz      short loc_18000EA56
0x18000ea07  mov     rcx, rax; void *
0x18000ea0a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ea0f  xor     eax, eax
0x18000ea11  lock xadd [rbx+1560h], eax
0x18000ea19  test    eax, eax
0x18000ea1b  jnz     short loc_18000EA56
0x18000ea1d  cmp     [rbx+15DCh], eax
0x18000ea23  jz      short loc_18000EA56
0x18000ea25  lea     rcx, [rbx+15A0h]
0x18000ea2c  mov     edx, 0FFFFFFFEh
0x18000ea31  call    ?Change@?$CTimer@VCTpSrvDataState@@@@QEAAKKK@Z; CTimer<CTpSrvDataState>::Change(ulong,ulong)
0x18000ea36  mov     r9d, 1B2h; unsigned int
0x18000ea3c  lea     r8, aBaseEcoWdsTran_18; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000ea43  mov     ecx, eax; unsigned int
0x18000ea45  mov     edi, eax
0x18000ea47  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ea4c  test    eax, eax
0x18000ea4e  jnz     short loc_18000EA56
0x18000ea50  and     [rbx+15DCh], eax
0x18000ea56  mov     rcx, rbp; lpCriticalSection
0x18000ea59  call    cs:__imp_LeaveCriticalSection
0x18000ea5f  mov     rbx, [rsp+28h+arg_0]
0x18000ea64  mov     eax, edi
0x18000ea66  mov     rbp, [rsp+28h+arg_8]
0x18000ea6b  mov     rsi, [rsp+28h+arg_10]
0x18000ea70  add     rsp, 20h
0x18000ea74  pop     rdi
0x18000ea75  retn
```
