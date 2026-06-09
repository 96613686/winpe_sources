# ATL::CComCriticalSection::Init(void)

- ea: `0x180002dcc`
- end: `0x180002df6`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002b40`

## callees

- `0x180002dcc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002dd4`
- `KERNEL32!InitializeCriticalSection` at `0x180002dd4`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x180002dcc  push    rbx
0x180002dce  sub     rsp, 20h
0x180002dd2  xor     ebx, ebx
0x180002dd4  call    cs:__imp_InitializeCriticalSection
0x180002dda  jmp     short loc_180002DEE
0x180002ddc  mov     ebx, 80004005h
0x180002de1  mov     ecx, 8007000Eh
0x180002de6  cmp     eax, 0C0000017h
0x180002deb  cmovz   ebx, ecx
0x180002dee  mov     eax, ebx
0x180002df0  add     rsp, 20h
0x180002df4  pop     rbx
0x180002df5  retn
```
