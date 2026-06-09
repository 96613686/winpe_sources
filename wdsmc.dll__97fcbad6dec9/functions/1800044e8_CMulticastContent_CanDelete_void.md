# CMulticastContent::CanDelete(void)

- ea: `0x1800044e8`
- end: `0x180004528`
- name: `?CanDelete@CMulticastContent@@QEAAHXZ`
- size: `64`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002810`
- `0x1800029f4`
- `0x180003868`

## callees

- `0x1800044e8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004515`
- `KERNEL32!LeaveCriticalSection` at `0x180004515`
- `KERNEL32!EnterCriticalSection` at `0x1800044f5`
- `KERNEL32!EnterCriticalSection` at `0x1800044f5`

## pseudocode

```c
_BOOL8 __fastcall CMulticastContent::CanDelete(LPCRITICAL_SECTION lpCriticalSection)
{
  BOOL v2; // ebx

  EnterCriticalSection(lpCriticalSection);
  v2 = 0;
  if ( HIDWORD(lpCriticalSection[6].SpinCount) )
    v2 = HIDWORD(lpCriticalSection[7].LockSemaphore) == 0;
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x1800044e8  mov     [rsp+arg_0], rbx
0x1800044ed  push    rdi
0x1800044ee  sub     rsp, 20h
0x1800044f2  mov     rdi, rcx
0x1800044f5  call    cs:__imp_EnterCriticalSection
0x1800044fb  xor     ebx, ebx
0x1800044fd  cmp     [rdi+114h], ebx
0x180004503  jz      short loc_180004512
0x180004505  cmp     [rdi+134h], ebx
0x18000450b  jnz     short loc_180004512
0x18000450d  mov     ebx, 1
0x180004512  mov     rcx, rdi; lpCriticalSection
0x180004515  call    cs:__imp_LeaveCriticalSection
0x18000451b  mov     eax, ebx
0x18000451d  mov     rbx, [rsp+28h+arg_0]
0x180004522  add     rsp, 20h
0x180004526  pop     rdi
0x180004527  retn
```
