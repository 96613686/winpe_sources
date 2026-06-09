# CWinSATTaskMangerTask::~CWinSATTaskMangerTask(void)

- ea: `0x1800203c4`
- end: `0x180020420`
- name: `??1CWinSATTaskMangerTask@@QEAA@XZ`
- size: `92`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015484`
- `0x1800156f0`

## callees

- `0x180001a34`
- `0x1800071d0`
- `0x18001004c`
- `0x1800203c4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203e0`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::~CWinSATTaskMangerTask(CWinSATTaskMangerTask *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CWinSATTaskMangerTask::`vftable';
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 11) = 0;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((char *)this + 120);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 8);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CWinSATTaskMangerTask *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800203c4  push    rbx
0x1800203c6  sub     rsp, 20h
0x1800203ca  lea     rax, ??_7CWinSATTaskMangerTask@@6B@; const CWinSATTaskMangerTask::`vftable'
0x1800203d1  mov     rbx, rcx
0x1800203d4  mov     [rcx], rax
0x1800203d7  mov     rcx, [rcx+58h]; hObject
0x1800203db  test    rcx, rcx
0x1800203de  jz      short loc_1800203EE
0x1800203e0  call    cs:__imp_CloseHandle
0x1800203e6  mov     qword ptr [rbx+58h], 0
0x1800203ee  lea     rcx, [rbx+78h]
0x1800203f2  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800203f7  lea     rcx, [rbx+50h]
0x1800203fb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020400  lea     rcx, [rbx+48h]
0x180020404  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020409  lea     rcx, [rbx+40h]
0x18002040d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020412  lea     rcx, [rbx+10h]; this
0x180020416  add     rsp, 20h
0x18002041a  pop     rbx
0x18002041b  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
