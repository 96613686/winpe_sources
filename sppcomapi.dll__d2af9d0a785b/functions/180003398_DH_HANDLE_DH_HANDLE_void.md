# DH_HANDLE::~DH_HANDLE(void)

- ea: `0x180003398`
- end: `0x1800033c3`
- name: `??1DH_HANDLE@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(DH_HANDLE *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`
- `0x180037050`
- `0x1800398b4`
- `0x18003ac1c`

## callees

- `0x180003398`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033a9`

## pseudocode

```c
void __fastcall DH_HANDLE::~DH_HANDLE(void **this)
{
  void *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CloseHandle(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180003398  push    rbx
0x18000339a  sub     rsp, 20h
0x18000339e  mov     rbx, rcx
0x1800033a1  mov     rcx, [rcx]; hObject
0x1800033a4  test    rcx, rcx
0x1800033a7  jz      short loc_1800033BC
0x1800033a9  call    cs:__imp_CloseHandle
0x1800033b0  nop     dword ptr [rax+rax+00h]
0x1800033b5  mov     qword ptr [rbx], 0
0x1800033bc  add     rsp, 20h
0x1800033c0  pop     rbx
0x1800033c1  retn
```
