# std::thread::~thread(void)

- ea: `0x18000865c`
- end: `0x180008672`
- name: `??1thread@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(std::thread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800086b0`
- `0x18000c0ad`

## callees

- `0x18000865c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180008666`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180008666`

## pseudocode

```c
void __fastcall std::thread::~thread(std::thread *this)
{
  if ( *((_DWORD *)this + 2) )
  {
    _o_terminate();
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18000865c  sub     rsp, 28h
0x180008660  cmp     dword ptr [rcx+8], 0
0x180008664  jz      short loc_18000866D
0x180008666  call    cs:__imp__o_terminate
0x18000866c  int     3; Trap to Debugger
0x18000866d  add     rsp, 28h
0x180008671  retn
```
