# TLoad64BitDllsMgr::~TLoad64BitDllsMgr(void)

- ea: `0x140006620`
- end: `0x140006663`
- name: `??1TLoad64BitDllsMgr@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(TLoad64BitDllsMgr *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140006680`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140006642`
- `KERNEL32!DeleteCriticalSection` at `0x140006642`

## pseudocode

```c
void __fastcall TLoad64BitDllsMgr::~TLoad64BitDllsMgr(TLoad64BitDllsMgr *this)
{
  *(_QWORD *)this = &TLoad64BitDllsMgr::`vftable'{for `TRefCntMgr'};
  *((_QWORD *)this + 2) = &TLoad64BitDllsMgr::`vftable'{for `TPrinterDriver'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 2) = &TPrinterDriver::`vftable';
  *(_QWORD *)this = &TRefCntMgr::`vftable';
}

```

## disassembly

```asm
0x140006620  push    rbx
0x140006622  sub     rsp, 20h
0x140006626  lea     rax, ??_7TLoad64BitDllsMgr@@6BTRefCntMgr@@@; const TLoad64BitDllsMgr::`vftable'{for `TRefCntMgr'}
0x14000662d  mov     rbx, rcx
0x140006630  mov     [rcx], rax
0x140006633  lea     rax, ??_7TLoad64BitDllsMgr@@6BTPrinterDriver@@@; const TLoad64BitDllsMgr::`vftable'{for `TPrinterDriver'}
0x14000663a  mov     [rcx+10h], rax
0x14000663e  add     rcx, 58h ; 'X'; lpCriticalSection
0x140006642  call    cs:__imp_DeleteCriticalSection
0x140006648  lea     rax, ??_7TPrinterDriver@@6B@; const TPrinterDriver::`vftable'
0x14000664f  mov     [rbx+10h], rax
0x140006653  lea     rax, ??_7TRefCntMgr@@6B@; const TRefCntMgr::`vftable'
0x14000665a  mov     [rbx], rax
0x14000665d  add     rsp, 20h
0x140006661  pop     rbx
0x140006662  retn
```
