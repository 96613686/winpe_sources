# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180079b40`
- end: `0x180079b5f`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007cce8`
- `0x1800a1578`

## callees

- `0x180079b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079b49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079b49`
- `SHCORE!SHTaskPoolAllowThreadReuse` at `0x180079b53`
- `SHCORE!SHTaskPoolAllowThreadReuse` at `0x180079b53`

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
0x180079b40  push    rbx
0x180079b42  sub     rsp, 20h
0x180079b46  mov     ebx, [rcx+8]
0x180079b49  call    cs:__imp_GetCurrentThreadId
0x180079b4f  cmp     eax, ebx
0x180079b51  jz      short loc_180079B59
0x180079b53  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180079b59  add     rsp, 20h
0x180079b5d  pop     rbx
0x180079b5e  retn
```
