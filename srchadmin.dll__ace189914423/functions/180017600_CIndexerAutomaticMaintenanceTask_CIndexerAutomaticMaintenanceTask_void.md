# CIndexerAutomaticMaintenanceTask::~CIndexerAutomaticMaintenanceTask(void)

- ea: `0x180017600`
- end: `0x18001763c`
- name: `??1CIndexerAutomaticMaintenanceTask@@IEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CIndexerAutomaticMaintenanceTask *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a584`

## callees

- `0x1800175e0`
- `0x1800181fc`
- `0x18001844c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017628`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017628`

## pseudocode

```c
void __fastcall CIndexerAutomaticMaintenanceTask::~CIndexerAutomaticMaintenanceTask(
        CIndexerAutomaticMaintenanceTask *this)
{
  SafeCloseHandle((void **)this + 14);
  SafeCloseHandle((void **)this + 15);
  Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CIndexerAutomaticMaintenanceTask *)((char *)this + 16));
}

```

## disassembly

```asm
0x180017600  push    rbx
0x180017602  sub     rsp, 20h
0x180017606  mov     rbx, rcx
0x180017609  add     rcx, 70h ; 'p'; void **
0x18001760d  call    ?SafeCloseHandle@@YAHPEAPEAX@Z; SafeCloseHandle(void * *)
0x180017612  lea     rcx, [rbx+78h]; void **
0x180017616  call    ?SafeCloseHandle@@YAHPEAPEAX@Z; SafeCloseHandle(void * *)
0x18001761b  lea     rcx, [rbx+68h]
0x18001761f  call    ?InternalRelease@?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(void)
0x180017624  lea     rcx, [rbx+40h]; lpCriticalSection
0x180017628  call    cs:__imp_DeleteCriticalSection
0x18001762e  lea     rcx, [rbx+10h]; this
0x180017632  add     rsp, 20h
0x180017636  pop     rbx
0x180017637  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
