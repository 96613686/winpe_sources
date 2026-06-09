# ATL::CComCriticalSection::Init(void)

- ea: `0x180001cd0`
- end: `0x180001cf0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001230`
- `0x1800012f0`
- `0x180001be0`
- `0x180007798`
- `0x180007960`
- `0x18000e194`
- `0x18000e504`
- `0x180011854`

## callees

- `0x180001cd0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180001cd4`
- `KERNEL32!InitializeCriticalSection` at `0x180001cd4`

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
0x180001cd0  sub     rsp, 38h
0x180001cd4  call    cs:__imp_InitializeCriticalSection
0x180001cda  xor     eax, eax
0x180001cdc  mov     [rsp+38h+var_18], eax
0x180001ce0  jmp     short loc_180001CEB
0x180001ce2  mov     eax, 8007000Eh
0x180001ce7  mov     [rsp+38h+var_18], eax
0x180001ceb  add     rsp, 38h
0x180001cef  retn
0x180015cd0  push    rbp
0x180015cd2  sub     rsp, 20h
0x180015cd6  mov     rbp, rdx
0x180015cd9  mov     rax, [rcx]
0x180015cdc  xor     ecx, ecx
0x180015cde  cmp     dword ptr [rax], 0C0000017h
0x180015ce4  setz    cl
0x180015ce7  mov     eax, ecx
0x180015ce9  add     rsp, 20h
0x180015ced  pop     rbp
0x180015cee  retn
```
