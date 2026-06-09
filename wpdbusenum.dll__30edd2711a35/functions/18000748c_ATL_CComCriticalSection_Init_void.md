# ATL::CComCriticalSection::Init(void)

- ea: `0x18000748c`
- end: `0x1800074ac`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001050`
- `0x180007404`

## callees

- `0x18000748c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007490`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007490`

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
0x18000748c  sub     rsp, 38h
0x180007490  call    cs:__imp_InitializeCriticalSection
0x180007496  xor     eax, eax
0x180007498  mov     [rsp+38h+var_18], eax
0x18000749c  jmp     short loc_1800074A7
0x18000749e  mov     eax, 8007000Eh
0x1800074a3  mov     [rsp+38h+var_18], eax
0x1800074a7  add     rsp, 38h
0x1800074ab  retn
0x1800156a2  push    rbp
0x1800156a4  sub     rsp, 20h
0x1800156a8  mov     rbp, rdx
0x1800156ab  mov     rax, [rcx]
0x1800156ae  xor     ecx, ecx
0x1800156b0  cmp     dword ptr [rax], 0C0000017h
0x1800156b6  setz    cl
0x1800156b9  mov     eax, ecx
0x1800156bb  add     rsp, 20h
0x1800156bf  pop     rbp
0x1800156c0  retn
```
