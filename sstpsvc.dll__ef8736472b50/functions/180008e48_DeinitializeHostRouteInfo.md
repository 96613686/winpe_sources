# DeinitializeHostRouteInfo

- ea: `0x180008e48`
- end: `0x180008eb1`
- name: `DeinitializeHostRouteInfo`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059f0`

## callees

- `0x180008e48`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008e79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008e79`

## pseudocode

```c
void DeinitializeHostRouteInfo()
{
  if ( *((_QWORD *)&xmmword_18002EBA0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002EBA0 + 1),
      L"Entering DeinitializeHostRouteInfo");
  DeleteCriticalSection(&RouteEntryCs);
  if ( *((_QWORD *)&xmmword_18002EBA0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002EBA0 + 1),
      L"Leaving DeinitializeHostRouteInfo");
}

```

## disassembly

```asm
0x180008e48  sub     rsp, 28h
0x180008e4c  mov     rdx, qword ptr cs:xmmword_18002EBA0+8
0x180008e53  test    rdx, rdx
0x180008e56  jz      short loc_180008E72
0x180008e58  mov     rcx, cs:gHostRoutEtwContext
0x180008e5f  lea     r8, aEnteringDeinit; "Entering DeinitializeHostRouteInfo"
0x180008e66  mov     rax, cs:gHostRoutTemplateFunc
0x180008e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e72  lea     rcx, RouteEntryCs; lpCriticalSection
0x180008e79  call    cs:__imp_DeleteCriticalSection
0x180008e80  nop     dword ptr [rax+rax+00h]
0x180008e85  mov     rdx, qword ptr cs:xmmword_18002EBA0+8
0x180008e8c  test    rdx, rdx
0x180008e8f  jz      short loc_180008EAB
0x180008e91  mov     rcx, cs:gHostRoutEtwContext
0x180008e98  lea     r8, aLeavingDeiniti; "Leaving DeinitializeHostRouteInfo"
0x180008e9f  mov     rax, cs:gHostRoutTemplateFunc
0x180008ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eab  add     rsp, 28h
0x180008eaf  retn
```
