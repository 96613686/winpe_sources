# CSqmSessionMgr::~CSqmSessionMgr(void)

- ea: `0x1800153ac`
- end: `0x1800153e0`
- name: `??1CSqmSessionMgr@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d430`

## callees

- `0x180014aec`
- `0x1800153ac`
- `0x180015cdc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800153d4`
- `KERNEL32!DeleteCriticalSection` at `0x1800153d4`

## pseudocode

```c
void __fastcall CSqmSessionMgr::~CSqmSessionMgr(LPCRITICAL_SECTION lpCriticalSection)
{
  ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll(&lpCriticalSection[3].LockCount);
  ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(&lpCriticalSection[1].OwningThread);
  if ( LOBYTE(lpCriticalSection[1].DebugInfo) )
  {
    LOBYTE(lpCriticalSection[1].DebugInfo) = 0;
    DeleteCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x1800153ac  push    rbx
0x1800153ae  sub     rsp, 20h
0x1800153b2  mov     rbx, rcx
0x1800153b5  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800153b9  call    ?RemoveAll@?$CAtlList@PEAVCSqmSession@@V?$CElementTraits@PEAVCSqmSession@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll(void)
0x1800153be  lea     rcx, [rbx+38h]
0x1800153c2  call    ?RemoveAll@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(void)
0x1800153c7  cmp     byte ptr [rbx+28h], 0
0x1800153cb  jz      short loc_1800153DA
0x1800153cd  mov     rcx, rbx; lpCriticalSection
0x1800153d0  mov     byte ptr [rbx+28h], 0
0x1800153d4  call    cs:__imp_DeleteCriticalSection
0x1800153da  add     rsp, 20h
0x1800153de  pop     rbx
0x1800153df  retn
```
