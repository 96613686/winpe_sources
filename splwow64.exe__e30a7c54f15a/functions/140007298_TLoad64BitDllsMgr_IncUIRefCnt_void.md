# TLoad64BitDllsMgr::IncUIRefCnt(void)

- ea: `0x140007298`
- end: `0x1400072c7`
- name: `?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ`
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
- `0x140011624`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400072a9`
- `KERNEL32!EnterCriticalSection` at `0x1400072a9`
- `KERNEL32!LeaveCriticalSection` at `0x1400072c0`

## pseudocode

```c
void __fastcall TLoad64BitDllsMgr::IncUIRefCnt(TLoad64BitDllsMgr *this)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  ++*((_DWORD *)this + 15);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
}

```

## disassembly

```asm
0x140007298  mov     [rsp+arg_0], rbx
0x14000729d  push    rdi
0x14000729e  sub     rsp, 20h
0x1400072a2  mov     rdi, rcx
0x1400072a5  add     rcx, 58h ; 'X'; lpCriticalSection
0x1400072a9  call    cs:__imp_EnterCriticalSection
0x1400072af  inc     dword ptr [rdi+3Ch]
0x1400072b2  lea     rcx, [rdi+58h]
0x1400072b6  mov     rbx, [rsp+28h+arg_0]
0x1400072bb  add     rsp, 20h
0x1400072bf  pop     rdi
0x1400072c0  jmp     cs:__imp_LeaveCriticalSection
```
