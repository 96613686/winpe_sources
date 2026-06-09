# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x1800170dc`
- end: `0x1800170fb`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005a378`
- `0x18005a3d0`
- `0x18005a428`
- `0x18006cfe8`

## callees

- `0x1800170dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170e5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800170ef`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800170ef`

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
0x1800170dc  push    rbx
0x1800170de  sub     rsp, 20h
0x1800170e2  mov     ebx, [rcx+8]
0x1800170e5  call    cs:__imp_GetCurrentThreadId
0x1800170eb  cmp     eax, ebx
0x1800170ed  jz      short loc_1800170F5
0x1800170ef  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x1800170f5  add     rsp, 20h
0x1800170f9  pop     rbx
0x1800170fa  retn
```
