# CredStore::~CredStore(void)

- ea: `0x1800181b0`
- end: `0x1800181e3`
- name: `??1CredStore@@AEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CredStore *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018fec`

## callees

- `0x180005150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800181b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800181c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800181b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800181c9`

## pseudocode

```c
void __fastcall CredStore::~CredStore(CredStore *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  wmi::AutoRegKey::Close((CredStore *)((char *)this + 40));
}

```

## disassembly

```asm
0x1800181b0  push    rbx
0x1800181b2  sub     rsp, 20h
0x1800181b6  mov     rbx, rcx
0x1800181b9  call    cs:__imp_DeleteCriticalSection
0x1800181c0  nop     dword ptr [rax+rax+00h]
0x1800181c5  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800181c9  call    cs:__imp_DeleteCriticalSection
0x1800181d0  nop     dword ptr [rax+rax+00h]
0x1800181d5  lea     rcx, [rbx+28h]; this
0x1800181d9  add     rsp, 20h
0x1800181dd  pop     rbx
0x1800181de  jmp     ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
```
