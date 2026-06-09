# CSsdpService::~CSsdpService(void)

- ea: `0x180025f5c`
- end: `0x180025ff2`
- name: `??1CSsdpService@@QEAA@XZ`
- size: `150`
- prototype: `void __fastcall(CSsdpService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002f9e8`

## callees

- `0x180006d70`
- `0x18000a358`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025f75`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025f9a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025fb2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025fca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025f75`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025f9a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025fb2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025fca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f8d`

## pseudocode

```c
void __fastcall CSsdpService::~CSsdpService(CSsdpService *this)
{
  FreeSsdpRequest((CSsdpService *)((char *)this + 112));
  free(*((void **)this + 35));
  *((_QWORD *)this + 35) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  free(*((void **)this + 27));
  *((_QWORD *)this + 27) = 0;
  free(*((void **)this + 26));
  *((_QWORD *)this + 26) = 0;
  free(*((void **)this + 25));
  *((_QWORD *)this + 25) = 0;
  *(_QWORD *)this = &CTimer<CSsdpService>::`vftable';
  CTimerBase::~CTimerBase(this);
}

```

## disassembly

```asm
0x180025f5c  push    rbx
0x180025f5e  sub     rsp, 20h
0x180025f62  mov     rbx, rcx
0x180025f65  add     rcx, 70h ; 'p'; struct _SSDP_REQUEST *
0x180025f69  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180025f6e  mov     rcx, [rbx+118h]; Block
0x180025f75  call    cs:__imp_free
0x180025f7b  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180025f82  mov     qword ptr [rbx+118h], 0
0x180025f8d  call    cs:__imp_DeleteCriticalSection
0x180025f93  mov     rcx, [rbx+0D8h]; Block
0x180025f9a  call    cs:__imp_free
0x180025fa0  mov     qword ptr [rbx+0D8h], 0
0x180025fab  mov     rcx, [rbx+0D0h]; Block
0x180025fb2  call    cs:__imp_free
0x180025fb8  mov     qword ptr [rbx+0D0h], 0
0x180025fc3  mov     rcx, [rbx+0C8h]; Block
0x180025fca  call    cs:__imp_free
0x180025fd0  lea     rax, ??_7?$CTimer@VCSsdpService@@@@6B@; const CTimer<CSsdpService>::`vftable'
0x180025fd7  mov     qword ptr [rbx+0C8h], 0
0x180025fe2  mov     rcx, rbx; this
0x180025fe5  mov     [rbx], rax
0x180025fe8  add     rsp, 20h
0x180025fec  pop     rbx
0x180025fed  jmp     ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
```
