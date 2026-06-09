# ATL::CComCriticalSection::Init(void)

- ea: `0x1800044fc`
- end: `0x180004523`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010a0`
- `0x180001130`
- `0x180001170`
- `0x18000452c`
- `0x18001a0b8`

## callees

- `0x1800044fc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004500`
- `KERNEL32!InitializeCriticalSection` at `0x180004500`

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
0x1800044fc  sub     rsp, 38h
0x180004500  call    cs:__imp_InitializeCriticalSection
0x180004507  nop     dword ptr [rax+rax+00h]
0x18000450c  xor     eax, eax
0x18000450e  mov     [rsp+38h+var_18], eax
0x180004512  jmp     short loc_18000451D
0x180004514  mov     eax, 8007000Eh
0x180004519  mov     [rsp+38h+var_18], eax
0x18000451d  add     rsp, 38h
0x180004521  retn
```
