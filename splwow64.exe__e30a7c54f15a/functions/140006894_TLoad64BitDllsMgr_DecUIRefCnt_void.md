# TLoad64BitDllsMgr::DecUIRefCnt(void)

- ea: `0x140006894`
- end: `0x1400068c3`
- name: `?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ`
- size: `47`
- prototype: `void __fastcall(TLoad64BitDllsMgr *__hidden this)`
- caller_count: `14`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400066c0`
- `0x1400067b0`
- `0x1400068d0`
- `0x1400069b8`
- `0x140006c10`
- `0x1400077fc`
- `0x14000d420`
- `0x14000d6c0`
- `0x14000e89c`
- `0x14000ed78`
- `0x14000ef6c`
- `0x14000f42c`
- `0x14000f5c4`
- `0x140011814`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400068a5`
- `KERNEL32!EnterCriticalSection` at `0x1400068a5`
- `KERNEL32!LeaveCriticalSection` at `0x1400068bc`

## pseudocode

```c
void __fastcall TLoad64BitDllsMgr::DecUIRefCnt(TLoad64BitDllsMgr *this)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  --*((_DWORD *)this + 15);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
}

```

## disassembly

```asm
0x140006894  mov     [rsp+arg_0], rbx
0x140006899  push    rdi
0x14000689a  sub     rsp, 20h
0x14000689e  mov     rdi, rcx
0x1400068a1  add     rcx, 58h ; 'X'; lpCriticalSection
0x1400068a5  call    cs:__imp_EnterCriticalSection
0x1400068ab  dec     dword ptr [rdi+3Ch]
0x1400068ae  lea     rcx, [rdi+58h]
0x1400068b2  mov     rbx, [rsp+28h+arg_0]
0x1400068b7  add     rsp, 20h
0x1400068bb  pop     rdi
0x1400068bc  jmp     cs:__imp_LeaveCriticalSection
```
