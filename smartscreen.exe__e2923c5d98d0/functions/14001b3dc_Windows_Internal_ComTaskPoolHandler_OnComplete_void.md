# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x14001b3dc`
- end: `0x14001b3fb`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140012a2c`
- `0x14001b358`
- `0x140035340`
- `0x14003f960`
- `0x14003f9b8`

## callees

- `0x14001b3dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001b3e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001b3e5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x14001b3ef`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x14001b3ef`

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
0x14001b3dc  push    rbx
0x14001b3de  sub     rsp, 20h
0x14001b3e2  mov     ebx, [rcx+8]
0x14001b3e5  call    cs:__imp_GetCurrentThreadId
0x14001b3eb  cmp     eax, ebx
0x14001b3ed  jz      short loc_14001B3F5
0x14001b3ef  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x14001b3f5  add     rsp, 20h
0x14001b3f9  pop     rbx
0x14001b3fa  retn
```
