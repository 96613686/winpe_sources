# WdipGetSessionFromId

- ea: `0x180006e40`
- end: `0x180006e9c`
- name: `WdipGetSessionFromId`
- size: `92`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005cf0`
- `0x18000d228`

## callees

- `0x180006e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e88`

## pseudocode

```c
_QWORD *__fastcall WdipGetSessionFromId(_QWORD *a1)
{
  _QWORD *v2; // rbx

  EnterCriticalSection(&g_csWDI);
  v2 = g_pWdiSessionHead;
  if ( g_pWdiSessionHead )
  {
    do
    {
      if ( *v2 == *a1 && v2[1] == a1[1] )
        break;
      v2 = (_QWORD *)v2[13];
    }
    while ( v2 );
  }
  LeaveCriticalSection(&g_csWDI);
  return v2;
}

```

## disassembly

```asm
0x180006e40  mov     [rsp+arg_0], rbx
0x180006e45  push    rdi
0x180006e46  sub     rsp, 20h
0x180006e4a  mov     rdi, rcx
0x180006e4d  lea     rcx, g_csWDI; lpCriticalSection
0x180006e54  call    cs:__imp_EnterCriticalSection
0x180006e5a  mov     rbx, cs:g_pWdiSessionHead
0x180006e61  test    rbx, rbx
0x180006e64  jz      short loc_180006E81
0x180006e66  mov     rax, [rbx]
0x180006e69  cmp     rax, [rdi]
0x180006e6c  jnz     short loc_180006E78
0x180006e6e  mov     rax, [rbx+8]
0x180006e72  cmp     rax, [rdi+8]
0x180006e76  jz      short loc_180006E81
0x180006e78  mov     rbx, [rbx+68h]
0x180006e7c  test    rbx, rbx
0x180006e7f  jnz     short loc_180006E66
0x180006e81  lea     rcx, g_csWDI; lpCriticalSection
0x180006e88  call    cs:__imp_LeaveCriticalSection
0x180006e8e  mov     rax, rbx
0x180006e91  mov     rbx, [rsp+28h+arg_0]
0x180006e96  add     rsp, 20h
0x180006e9a  pop     rdi
0x180006e9b  retn
```
