# UL_CONTROL_CHANNEL::Cleanup(void)

- ea: `0x180014588`
- end: `0x1800145e0`
- name: `?Cleanup@UL_CONTROL_CHANNEL@@QEAAKXZ`
- size: `88`
- prototype: `unsigned int __fastcall(UL_CONTROL_CHANNEL *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014564`
- `0x180015a40`

## callees

- `0x180014588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145b9`
- `HTTPAPI!HttpCloseUrlGroup` at `0x1800145a0`
- `HTTPAPI!HttpCloseUrlGroup` at `0x1800145a0`

## pseudocode

```c
__int64 __fastcall UL_CONTROL_CHANNEL::Cleanup(UL_CONTROL_CHANNEL *this)
{
  ULONG LastError; // edi
  HTTP_URL_GROUP_ID v3; // rcx
  void *v4; // rcx

  LastError = 0;
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    LastError = HttpCloseUrlGroup(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 && !CloseHandle(v4) )
    LastError = GetLastError();
  *((_QWORD *)this + 5) = 0;
  return LastError;
}

```

## disassembly

```asm
0x180014588  mov     [rsp+arg_0], rbx
0x18001458d  push    rdi
0x18001458e  sub     rsp, 20h
0x180014592  mov     rbx, rcx
0x180014595  xor     edi, edi
0x180014597  mov     rcx, [rcx+20h]; UrlGroupId
0x18001459b  test    rcx, rcx
0x18001459e  jz      short loc_1800145B0
0x1800145a0  call    cs:__imp_HttpCloseUrlGroup
0x1800145a6  mov     edi, eax
0x1800145a8  mov     qword ptr [rbx+20h], 0
0x1800145b0  mov     rcx, [rbx+28h]; hObject
0x1800145b4  test    rcx, rcx
0x1800145b7  jz      short loc_1800145CB
0x1800145b9  call    cs:__imp_CloseHandle
0x1800145bf  test    eax, eax
0x1800145c1  jnz     short loc_1800145CB
0x1800145c3  call    cs:__imp_GetLastError
0x1800145c9  mov     edi, eax
0x1800145cb  mov     qword ptr [rbx+28h], 0
0x1800145d3  mov     eax, edi
0x1800145d5  mov     rbx, [rsp+28h+arg_0]
0x1800145da  add     rsp, 20h
0x1800145de  pop     rdi
0x1800145df  retn
```
