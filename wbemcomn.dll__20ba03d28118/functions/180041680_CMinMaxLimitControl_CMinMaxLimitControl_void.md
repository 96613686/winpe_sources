# CMinMaxLimitControl::~CMinMaxLimitControl(void)

- ea: `0x180041680`
- end: `0x1800416b5`
- name: `??1CMinMaxLimitControl@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CMinMaxLimitControl *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800416c0`
- `0x180041890`
- `0x18004487c`

## callees

- `0x180022e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041691`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041691`

## pseudocode

```c
void __fastcall CMinMaxLimitControl::~CMinMaxLimitControl(CMinMaxLimitControl *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  WString::DeleteString((CMinMaxLimitControl *)((char *)this + 32), *((unsigned __int16 **)this + 4));
  *(_QWORD *)this = &CLimitControl::`vftable';
}

```

## disassembly

```asm
0x180041680  mov     [rsp+arg_0], rcx
0x180041685  push    rbx
0x180041686  sub     rsp, 20h
0x18004168a  mov     rbx, rcx
0x18004168d  add     rcx, 30h ; '0'; lpCriticalSection
0x180041691  call    cs:__imp_DeleteCriticalSection
0x180041697  nop
0x180041698  lea     rcx, [rbx+20h]; this
0x18004169c  mov     rdx, [rcx]; unsigned __int16 *
0x18004169f  call    ?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x1800416a4  nop
0x1800416a5  lea     rax, ??_7CLimitControl@@6B@; const CLimitControl::`vftable'
0x1800416ac  mov     [rbx], rax
0x1800416af  add     rsp, 20h
0x1800416b3  pop     rbx
0x1800416b4  retn
```
