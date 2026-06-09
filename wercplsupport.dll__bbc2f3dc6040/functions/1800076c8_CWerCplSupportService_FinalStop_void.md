# CWerCplSupportService::FinalStop(void)

- ea: `0x1800076c8`
- end: `0x180007733`
- name: `?FinalStop@CWerCplSupportService@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(CWerCplSupportService *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180007624`
- `0x18000773c`

## callees

- `0x180001674`
- `0x1800076c8`
- `0x180007c9c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007707`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007713`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007713`

## pseudocode

```c
void __fastcall CWerCplSupportService::FinalStop(CWerCplSupportService *this)
{
  _QWORD *v2; // rcx
  void *v3; // rcx

  v2 = (_QWORD *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    *v2 = &CErcLuaSupportClassFactory::`vftable';
    operator delete(v2);
    *((_QWORD *)this + 9) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  UnregisterWaitEx(*((HANDLE *)this + 8), 0);
  *((_QWORD *)this + 8) = 0;
  CWerCplSupportService::_SetServiceStatus(this, 1u);
}

```

## disassembly

```asm
0x1800076c8  push    rbx
0x1800076ca  sub     rsp, 20h
0x1800076ce  mov     rbx, rcx
0x1800076d1  mov     rcx, [rcx+48h]; Block
0x1800076d5  test    rcx, rcx
0x1800076d8  jz      short loc_1800076F1
0x1800076da  lea     rax, ??_7CErcLuaSupportClassFactory@@6B@; const CErcLuaSupportClassFactory::`vftable'
0x1800076e1  mov     [rcx], rax
0x1800076e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800076e9  mov     qword ptr [rbx+48h], 0
0x1800076f1  mov     rcx, [rbx+38h]; hObject
0x1800076f5  mov     qword ptr [rbx+38h], 0
0x1800076fd  lea     rax, [rcx+1]
0x180007701  cmp     rax, 1
0x180007705  jbe     short loc_18000770D
0x180007707  call    cs:__imp_CloseHandle
0x18000770d  mov     rcx, [rbx+40h]; WaitHandle
0x180007711  xor     edx, edx; CompletionEvent
0x180007713  call    cs:__imp_UnregisterWaitEx
0x180007719  mov     edx, 1; unsigned int
0x18000771e  mov     qword ptr [rbx+40h], 0
0x180007726  mov     rcx, rbx; this
0x180007729  add     rsp, 20h
0x18000772d  pop     rbx
0x18000772e  jmp     ?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z; CWerCplSupportService::_SetServiceStatus(ulong,ulong)
```
