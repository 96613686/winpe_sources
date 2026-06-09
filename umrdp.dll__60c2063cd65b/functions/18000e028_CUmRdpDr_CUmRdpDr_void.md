# CUmRdpDr::~CUmRdpDr(void)

- ea: `0x18000e028`
- end: `0x18000e061`
- name: `??1CUmRdpDr@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CUmRdpDr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e784`

## callees

- `0x18000e028`
- `0x1800130e8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e048`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e048`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e05a`

## pseudocode

```c
void __fastcall CUmRdpDr::~CUmRdpDr(CUmRdpDr *this)
{
  void *v2; // rcx

  if ( *((_DWORD *)this + 543) )
    CUmRdpDr::Shutdown(this);
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CloseHandle(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2048));
}

```

## disassembly

```asm
0x18000e028  push    rbx
0x18000e02a  sub     rsp, 20h
0x18000e02e  cmp     dword ptr [rcx+87Ch], 0
0x18000e035  mov     rbx, rcx
0x18000e038  jz      short loc_18000E03F
0x18000e03a  call    ?Shutdown@CUmRdpDr@@QEAAHXZ; CUmRdpDr::Shutdown(void)
0x18000e03f  mov     rcx, [rbx+8]; hObject
0x18000e043  test    rcx, rcx
0x18000e046  jz      short loc_18000E04E
0x18000e048  call    cs:__imp_CloseHandle
0x18000e04e  lea     rcx, [rbx+800h]
0x18000e055  add     rsp, 20h
0x18000e059  pop     rbx
0x18000e05a  jmp     cs:__imp_DeleteCriticalSection
```
