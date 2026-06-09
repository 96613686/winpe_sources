# ATL::CComCriticalSection::Init(void)

- ea: `0x140004cd0`
- end: `0x140004cf0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001910`
- `0x140001b10`
- `0x140003de0`

## callees

- `0x140004cd0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x140004cd4`
- `KERNEL32!InitializeCriticalSection` at `0x140004cd4`

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
0x140004cd0  sub     rsp, 38h
0x140004cd4  call    cs:__imp_InitializeCriticalSection
0x140004cda  xor     eax, eax
0x140004cdc  mov     [rsp+38h+var_18], eax
0x140004ce0  jmp     short loc_140004CEB
0x140004ce2  mov     eax, 8007000Eh
0x140004ce7  mov     [rsp+38h+var_18], eax
0x140004ceb  add     rsp, 38h
0x140004cef  retn
0x140015650  push    rbp
0x140015652  sub     rsp, 20h
0x140015656  mov     rbp, rdx
0x140015659  mov     rax, [rcx]
0x14001565c  xor     ecx, ecx
0x14001565e  cmp     dword ptr [rax], 0C0000017h
0x140015664  setz    cl
0x140015667  mov     eax, ecx
0x140015669  add     rsp, 20h
0x14001566d  pop     rbp
0x14001566e  retn
```
