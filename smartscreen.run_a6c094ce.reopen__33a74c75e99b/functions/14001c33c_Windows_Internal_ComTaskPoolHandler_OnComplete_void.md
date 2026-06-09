# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x14001c33c`
- end: `0x14001c368`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `44`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400136a4`
- `0x14001c2b4`
- `0x14003688c`
- `0x140041094`
- `0x1400410ec`

## callees

- `0x14001c33c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c345`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c345`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x14001c355`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x14001c355`

## pseudocode

```c
void __fastcall Windows::Internal::ComTaskPoolHandler::OnComplete(Windows::Internal::ComTaskPoolHandler *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 2);
  if ( GetCurrentThreadId() != v1 )
    SHTaskPoolAllowThreadReuse();
}

```

## disassembly

```asm
0x14001c33c  push    rbx
0x14001c33e  sub     rsp, 20h
0x14001c342  mov     ebx, [rcx+8]
0x14001c345  call    cs:__imp_GetCurrentThreadId
0x14001c34c  nop     dword ptr [rax+rax+00h]
0x14001c351  cmp     eax, ebx
0x14001c353  jz      short loc_14001C361
0x14001c355  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x14001c35c  nop     dword ptr [rax+rax+00h]
0x14001c361  add     rsp, 20h
0x14001c365  pop     rbx
0x14001c366  retn
```
