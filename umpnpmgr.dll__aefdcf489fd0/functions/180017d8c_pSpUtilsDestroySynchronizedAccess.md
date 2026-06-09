# _pSpUtilsDestroySynchronizedAccess

- ea: `0x180017d8c`
- end: `0x180017dca`
- name: `_pSpUtilsDestroySynchronizedAccess`
- size: `62`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013498`

## callees

- `0x180017d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017db5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017db5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017da7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017da7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dbe`

## pseudocode

```c
int __fastcall pSpUtilsDestroySynchronizedAccess(__int64 a1)
{
  void *v1; // rax
  void *v2; // rbx

  v1 = *(void **)(a1 + 8);
  v2 = *(void **)a1;
  *(_OWORD *)a1 = 0;
  if ( v1 )
    LODWORD(v1) = CloseHandle(v1);
  if ( v2 )
  {
    SetEvent(v2);
    LODWORD(v1) = CloseHandle(v2);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x180017d8c  push    rbx
0x180017d8e  sub     rsp, 20h
0x180017d92  mov     rax, [rcx+8]
0x180017d96  xorps   xmm0, xmm0
0x180017d99  mov     rbx, [rcx]
0x180017d9c  movups  xmmword ptr [rcx], xmm0
0x180017d9f  test    rax, rax
0x180017da2  jz      short loc_180017DAD
0x180017da4  mov     rcx, rax; hObject
0x180017da7  call    cs:__imp_CloseHandle
0x180017dad  test    rbx, rbx
0x180017db0  jz      short loc_180017DC4
0x180017db2  mov     rcx, rbx; hEvent
0x180017db5  call    cs:__imp_SetEvent
0x180017dbb  mov     rcx, rbx; hObject
0x180017dbe  call    cs:__imp_CloseHandle
0x180017dc4  add     rsp, 20h
0x180017dc8  pop     rbx
0x180017dc9  retn
```
