# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x18001e460`
- end: `0x18001e485`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e408`
- `0x1800320e4`
- `0x180032994`
- `0x180034328`
- `0x180034940`
- `0x180041ed8`

## callees

- `0x18001e460`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e469`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e469`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e473`

## pseudocode

```c
void __fastcall Windows::Internal::ComTaskPoolHandler::OnComplete(Windows::Internal::ComTaskPoolHandler *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 2);
  if ( GetCurrentThreadId() != v1 )
    dword_1800DF118 = GetCurrentThreadId();
}

```

## disassembly

```asm
0x18001e460  push    rbx
0x18001e462  sub     rsp, 20h
0x18001e466  mov     ebx, [rcx+8]
0x18001e469  call    cs:__imp_GetCurrentThreadId
0x18001e46f  cmp     eax, ebx
0x18001e471  jz      short loc_18001E47F
0x18001e473  call    cs:__imp_GetCurrentThreadId
0x18001e479  mov     cs:dword_1800DF118, eax
0x18001e47f  add     rsp, 20h
0x18001e483  pop     rbx
0x18001e484  retn
```
