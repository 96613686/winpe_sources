# CWTPage::~CWTPage(void)

- ea: `0x18002b86c`
- end: `0x18002b8d5`
- name: `??1CWTPage@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(CWTPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b82c`

## callees

- `0x18000327c`
- `0x18002b86c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b879`

## pseudocode

```c
void __fastcall CWTPage::~CWTPage(LPVOID *this)
{
  LPVOID v2; // rcx
  LPVOID v3; // rcx
  LPVOID v4; // rcx

  CoTaskMemFree(this[13]);
  v2 = this[18];
  if ( v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = this[19];
  if ( v3 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = this[17];
  if ( v4 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(this + 2));
}

```

## disassembly

```asm
0x18002b86c  push    rbx
0x18002b86e  sub     rsp, 20h
0x18002b872  mov     rbx, rcx
0x18002b875  mov     rcx, [rcx+68h]; pv
0x18002b879  call    cs:__imp_CoTaskMemFree
0x18002b87f  mov     rcx, [rbx+90h]
0x18002b886  test    rcx, rcx
0x18002b889  jz      short loc_18002B897
0x18002b88b  mov     rax, [rcx]
0x18002b88e  mov     rax, [rax+10h]
0x18002b892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b897  mov     rcx, [rbx+98h]
0x18002b89e  test    rcx, rcx
0x18002b8a1  jz      short loc_18002B8AF
0x18002b8a3  mov     rax, [rcx]
0x18002b8a6  mov     rax, [rax+10h]
0x18002b8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8af  mov     rcx, [rbx+88h]
0x18002b8b6  test    rcx, rcx
0x18002b8b9  jz      short loc_18002B8C7
0x18002b8bb  mov     rax, [rcx]
0x18002b8be  mov     rax, [rax+10h]
0x18002b8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8c7  lea     rcx, [rbx+10h]; this
0x18002b8cb  add     rsp, 20h
0x18002b8cf  pop     rbx
0x18002b8d0  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
