# BtPanHandler::~BtPanHandler(void)

- ea: `0x180024818`
- end: `0x180024872`
- name: `??1BtPanHandler@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(BtPanHandler *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180014ab0`
- `0x180031e92`

## callees

- `0x18000a21c`
- `0x180024818`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024825`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024852`

## pseudocode

```c
void __fastcall BtPanHandler::~BtPanHandler(BtPanHandler *this)
{
  __int64 v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v2 = *((_QWORD *)this + 6);
  if ( v2 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  }
}

```

## disassembly

```asm
0x180024818  push    rbx
0x18002481a  sub     rsp, 20h
0x18002481e  mov     rbx, rcx
0x180024821  add     rcx, 38h ; '8'; lpCriticalSection
0x180024825  call    cs:__imp_DeleteCriticalSection
0x18002482b  nop
0x18002482c  mov     rcx, [rbx+30h]
0x180024830  test    rcx, rcx
0x180024833  jz      short loc_18002484A
0x180024835  mov     qword ptr [rbx+30h], 0
0x18002483d  mov     rax, [rcx]
0x180024840  mov     rax, [rax+10h]
0x180024844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024849  nop
0x18002484a  mov     rcx, [rbx]; hObject
0x18002484d  test    rcx, rcx
0x180024850  jz      short loc_18002485C
0x180024852  call    cs:__imp_CloseHandle
0x180024858  test    eax, eax
0x18002485a  jz      short loc_180024862
0x18002485c  add     rsp, 20h
0x180024860  pop     rbx
0x180024861  retn
0x180024862  mov     rcx, [rsp+28h]; this
0x180024867  mov     edx, 0A0Bh; void *
0x18002486c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
