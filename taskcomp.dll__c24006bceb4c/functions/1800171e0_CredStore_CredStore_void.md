# CredStore::~CredStore(void)

- ea: `0x1800171e0`
- end: `0x180017207`
- name: `??1CredStore@@AEAA@XZ`
- size: `39`
- prototype: `void __fastcall(CredStore *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017f08`

## callees

- `0x180004ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800171e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800171f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800171e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800171f3`

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
0x1800171e0  push    rbx
0x1800171e2  sub     rsp, 20h
0x1800171e6  mov     rbx, rcx
0x1800171e9  call    cs:__imp_DeleteCriticalSection
0x1800171ef  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800171f3  call    cs:__imp_DeleteCriticalSection
0x1800171f9  lea     rcx, [rbx+28h]; this
0x1800171fd  add     rsp, 20h
0x180017201  pop     rbx
0x180017202  jmp     ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
```
