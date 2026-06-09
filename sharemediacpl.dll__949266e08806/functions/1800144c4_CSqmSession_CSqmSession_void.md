# CSqmSession::~CSqmSession(void)

- ea: `0x1800144c4`
- end: `0x18001455d`
- name: `??1CSqmSession@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(CSqmSession *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800154d4`
- `0x180015dd8`

## callees

- `0x180001954`
- `0x1800144c4`
- `0x180014774`
- `0x180014aec`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014556`
- `ole32!CoTaskMemFree` at `0x180014533`
- `ole32!CoTaskMemFree` at `0x180014533`

## pseudocode

```c
void __fastcall CSqmSession::~CSqmSession(CSqmSession *this)
{
  __int64 *v1; // rbx
  __int64 v3; // rdx
  __int64 v4; // rax
  void **NextValue; // rax
  void *v6; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = (__int64 *)((char *)this + 48);
  if ( *((_QWORD *)this + 7) && *((_DWORD *)this + 16) )
  {
    v3 = *v1;
    v4 = 0;
    while ( !*(_QWORD *)(v3 + 8 * v4) )
    {
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 >= *((_DWORD *)this + 16) )
        goto LABEL_9;
    }
    v7 = *(_QWORD *)(v3 + 8 * v4);
    do
    {
      NextValue = (void **)ATL::CAtlMap<unsigned long,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::GetNextValue(
                             v1,
                             &v7);
      operator delete(*NextValue);
    }
    while ( v7 );
  }
LABEL_9:
  ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(v1);
  v6 = (void *)*((_QWORD *)this + 15);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 15) = 0;
  }
  ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(v1);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800144c4  mov     [rsp+arg_8], rbx
0x1800144c9  push    rdi
0x1800144ca  sub     rsp, 20h
0x1800144ce  lea     rbx, [rcx+30h]
0x1800144d2  mov     rdi, rcx
0x1800144d5  cmp     qword ptr [rbx+8], 0
0x1800144da  jz      short loc_180014522
0x1800144dc  cmp     dword ptr [rbx+10h], 0
0x1800144e0  jbe     short loc_180014522
0x1800144e2  mov     rdx, [rbx]
0x1800144e5  xor     eax, eax
0x1800144e7  cmp     qword ptr [rdx+rax*8], 0
0x1800144ec  jnz     short loc_1800144F7
0x1800144ee  inc     eax
0x1800144f0  cmp     eax, [rbx+10h]
0x1800144f3  jb      short loc_1800144E7
0x1800144f5  jmp     short loc_180014522
0x1800144f7  mov     rcx, [rdx+rax*8]
0x1800144fb  mov     [rsp+28h+arg_0], rcx
0x180014500  lea     rdx, [rsp+28h+arg_0]
0x180014505  mov     rcx, rbx
0x180014508  call    ?GetNextValue@?$CAtlMap@KPEAVSqmTimerEntry@CSqmSession@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmTimerEntry@CSqmSession@@@4@@ATL@@QEAAAEAPEAVSqmTimerEntry@CSqmSession@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::GetNextValue(__POSITION * &)
0x18001450d  mov     edx, 8
0x180014512  mov     rcx, [rax]; Block
0x180014515  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001451a  cmp     [rsp+28h+arg_0], 0
0x180014520  jnz     short loc_180014500
0x180014522  mov     rcx, rbx
0x180014525  call    ?RemoveAll@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(void)
0x18001452a  mov     rcx, [rdi+78h]; pv
0x18001452e  test    rcx, rcx
0x180014531  jz      short loc_180014541
0x180014533  call    cs:__imp_CoTaskMemFree
0x180014539  mov     qword ptr [rdi+78h], 0
0x180014541  mov     rcx, rbx
0x180014544  call    ?RemoveAll@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(void)
0x180014549  mov     rcx, rdi
0x18001454c  mov     rbx, [rsp+28h+arg_8]
0x180014551  add     rsp, 20h
0x180014555  pop     rdi
0x180014556  jmp     cs:__imp_DeleteCriticalSection
```
