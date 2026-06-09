# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180002fec`
- end: `0x18000304d`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800030a0`

## callees

- `0x180002fec`
- `0x180011010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003032`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003032`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003003`

## pseudocode

```c
void __fastcall CWinTaskHandler::~CWinTaskHandler(CWinTaskHandler *this)
{
  char *v2; // rcx
  __int64 v3; // rcx

  v2 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 5) = -1;
  }
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 6) = 0;
  }
  free(*((void **)this + 1));
  *((_QWORD *)this + 1) = 0;
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
}

```

## disassembly

```asm
0x180002fec  push    rbx
0x180002fee  sub     rsp, 20h
0x180002ff2  mov     rbx, rcx
0x180002ff5  mov     rcx, [rcx+28h]; hObject
0x180002ff9  lea     rax, [rcx-1]
0x180002ffd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003001  ja      short loc_180003011
0x180003003  call    cs:__imp_CloseHandle
0x180003009  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180003011  mov     rcx, [rbx+30h]
0x180003015  test    rcx, rcx
0x180003018  jz      short loc_18000302E
0x18000301a  mov     rax, [rcx]
0x18000301d  mov     rax, [rax+10h]
0x180003021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003026  mov     qword ptr [rbx+30h], 0
0x18000302e  mov     rcx, [rbx+8]; Block
0x180003032  call    cs:__imp_free
0x180003038  mov     qword ptr [rbx+8], 0
0x180003040  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003047  add     rsp, 20h
0x18000304b  pop     rbx
0x18000304c  retn
```
