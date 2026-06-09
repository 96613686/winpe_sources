# CSsdpService::~CSsdpService(void)

- ea: `0x180027cd4`
- end: `0x180027d88`
- name: `??1CSsdpService@@QEAA@XZ`
- size: `180`
- prototype: `void __fastcall(CSsdpService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180031ce8`

## callees

- `0x180008190`
- `0x18000ba2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027ced`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d1e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d3c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d5a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027ced`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d1e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d3c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d5a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027d0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027d0b`

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
0x180027cd4  push    rbx
0x180027cd6  sub     rsp, 20h
0x180027cda  mov     rbx, rcx
0x180027cdd  add     rcx, 70h ; 'p'; struct _SSDP_REQUEST *
0x180027ce1  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180027ce6  mov     rcx, [rbx+118h]; Block
0x180027ced  call    cs:__imp_free
0x180027cf4  nop     dword ptr [rax+rax+00h]
0x180027cf9  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180027d00  mov     qword ptr [rbx+118h], 0
0x180027d0b  call    cs:__imp_DeleteCriticalSection
0x180027d12  nop     dword ptr [rax+rax+00h]
0x180027d17  mov     rcx, [rbx+0D8h]; Block
0x180027d1e  call    cs:__imp_free
0x180027d25  nop     dword ptr [rax+rax+00h]
0x180027d2a  mov     qword ptr [rbx+0D8h], 0
0x180027d35  mov     rcx, [rbx+0D0h]; Block
0x180027d3c  call    cs:__imp_free
0x180027d43  nop     dword ptr [rax+rax+00h]
0x180027d48  mov     qword ptr [rbx+0D0h], 0
0x180027d53  mov     rcx, [rbx+0C8h]; Block
0x180027d5a  call    cs:__imp_free
0x180027d61  nop     dword ptr [rax+rax+00h]
0x180027d66  lea     rax, ??_7?$CTimer@VCSsdpService@@@@6B@; const CTimer<CSsdpService>::`vftable'
0x180027d6d  mov     qword ptr [rbx+0C8h], 0
0x180027d78  mov     rcx, rbx; this
0x180027d7b  mov     [rbx], rax
0x180027d7e  add     rsp, 20h
0x180027d82  pop     rbx
0x180027d83  jmp     ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
```
