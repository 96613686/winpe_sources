# CTrkWksSvc::~CTrkWksSvc(void)

- ea: `0x18000ef50`
- end: `0x18000efe8`
- name: `??1CTrkWksSvc@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(CTrkWksSvc *this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000a618`

## callees

- `0x1800016f4`
- `0x1800019c8`
- `0x180007440`
- `0x18000d814`
- `0x18000ef08`
- `0x18000ef2c`
- `0x18000eff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef90`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000efd4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef90`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000efd4`

## pseudocode

```c
void __fastcall CTrkWksSvc::~CTrkWksSvc(CTrkWksSvc *this, int a2)
{
  *(_QWORD *)this = &CTrkWksSvc::`vftable'{for `IServiceHandler'};
  *((_QWORD *)this + 1) = &CTrkWksSvc::`vftable'{for `PWorkItem'};
  CTrkWksSvc::UnInitialize(this, a2);
  *((_DWORD *)this + 91) = 1800893012;
  CTrkRegistryKey::~CTrkRegistryKey((CTrkWksSvc *)((char *)this + 2384));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  CVolumeManager::~CVolumeManager((CTrkWksSvc *)((char *)this + 576));
  CTrkWksConfiguration::~CTrkWksConfiguration((CTrkWksSvc *)((char *)this + 536));
  CRpcServer::~CRpcServer((CTrkWksSvc *)((char *)this + 448));
  *((_QWORD *)this + 48) = &CPort::`vftable';
  CPort::UnInitialize((CTrkWksSvc *)((char *)this + 384));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  CTrkConfiguration::UnInitialize((CTrkWksSvc *)((char *)this + 16));
}

```

## disassembly

```asm
0x18000ef50  push    rbx
0x18000ef52  sub     rsp, 20h
0x18000ef56  lea     rax, ??_7CTrkWksSvc@@6BIServiceHandler@@@; const CTrkWksSvc::`vftable'{for `IServiceHandler'}
0x18000ef5d  mov     rbx, rcx
0x18000ef60  mov     [rcx], rax
0x18000ef63  lea     rax, ??_7CTrkWksSvc@@6BPWorkItem@@@; const CTrkWksSvc::`vftable'{for `PWorkItem'}
0x18000ef6a  mov     [rcx+8], rax
0x18000ef6e  call    ?UnInitialize@CTrkWksSvc@@QEAAXJ@Z; CTrkWksSvc::UnInitialize(long)
0x18000ef73  lea     rcx, [rbx+950h]; this
0x18000ef7a  mov     dword ptr [rbx+16Ch], 6B577254h
0x18000ef84  call    ??1CTrkRegistryKey@@QEAA@XZ; CTrkRegistryKey::~CTrkRegistryKey(void)
0x18000ef89  lea     rcx, [rbx+418h]; lpCriticalSection
0x18000ef90  call    cs:__imp_DeleteCriticalSection
0x18000ef96  lea     rcx, [rbx+240h]; this
0x18000ef9d  call    ??1CVolumeManager@@QEAA@XZ; CVolumeManager::~CVolumeManager(void)
0x18000efa2  lea     rcx, [rbx+218h]; this
0x18000efa9  call    ??1CTrkWksConfiguration@@QEAA@XZ; CTrkWksConfiguration::~CTrkWksConfiguration(void)
0x18000efae  lea     rcx, [rbx+1C0h]; this
0x18000efb5  call    ??1CRpcServer@@QEAA@XZ; CRpcServer::~CRpcServer(void)
0x18000efba  lea     rcx, [rbx+180h]; this
0x18000efc1  lea     rax, ??_7CPort@@6B@; const CPort::`vftable'
0x18000efc8  mov     [rcx], rax
0x18000efcb  call    ?UnInitialize@CPort@@QEAAXXZ; CPort::UnInitialize(void)
0x18000efd0  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000efd4  call    cs:__imp_DeleteCriticalSection
0x18000efda  lea     rcx, [rbx+10h]; this
0x18000efde  add     rsp, 20h
0x18000efe2  pop     rbx
0x18000efe3  jmp     ?UnInitialize@CTrkConfiguration@@QEAAXXZ; CTrkConfiguration::UnInitialize(void)
```
