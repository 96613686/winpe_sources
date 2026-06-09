# LeaveSyncList

- ea: `0x180011800`
- end: `0x180011846`
- name: `LeaveSyncList`
- size: `70`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dff4`
- `0x18000e200`
- `0x18000e260`
- `0x18000e4c0`
- `0x18000e7a0`
- `0x18000ea20`
- `0x18000ecec`
- `0x18000eea0`
- `0x18000f780`
- `0x18000fa20`
- `0x18000fcb0`
- `0x18000ff90`
- `0x180010090`
- `0x1800102d0`
- `0x1800106d0`
- `0x1800108f0`
- `0x180010ab0`
- `0x180010c60`
- `0x180010ef0`
- `0x180011270`
- `0x1800113e0`

## callees

- `0x180011800`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011817`
- `KERNEL32!EnterCriticalSection` at `0x180011817`
- `KERNEL32!LeaveCriticalSection` at `0x18001183f`
- `KERNEL32!SetEvent` at `0x18001182c`
- `KERNEL32!SetEvent` at `0x18001182c`

## pseudocode

```c
void __fastcall LeaveSyncList(__int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 344);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 344));
  if ( (int)--*(_DWORD *)(a2 + 8) > 0 )
    SetEvent(**(HANDLE **)a2);
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180011800  mov     [rsp+arg_0], rbx
0x180011805  push    rdi
0x180011806  sub     rsp, 20h
0x18001180a  lea     rdi, [rcx+158h]
0x180011811  mov     rbx, rdx
0x180011814  mov     rcx, rdi; lpCriticalSection
0x180011817  call    cs:__imp_EnterCriticalSection
0x18001181d  dec     dword ptr [rbx+8]
0x180011820  cmp     dword ptr [rbx+8], 0
0x180011824  jle     short loc_180011832
0x180011826  mov     rcx, [rbx]
0x180011829  mov     rcx, [rcx]; hEvent
0x18001182c  call    cs:__imp_SetEvent
0x180011832  mov     rcx, rdi
0x180011835  mov     rbx, [rsp+28h+arg_0]
0x18001183a  add     rsp, 20h
0x18001183e  pop     rdi
0x18001183f  jmp     cs:__imp_LeaveCriticalSection
```
