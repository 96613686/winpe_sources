# OnDeleteIf<void * &,void (*)(void * &),&RevertRegister_(void * &)>::~OnDeleteIf<void * &,void (*)(void * &),&RevertRegister_(void * &)>(void)

- ea: `0x18000b524`
- end: `0x18000b54d`
- name: `??1?$OnDeleteIf@AEAPEAXP6AXAEAPEAX@Z$1?RevertRegister_@@YAX0@Z@@QEAA@XZ`
- size: `41`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae3c`
- `0x18001e048`
- `0x18001e05a`
- `0x18001e06c`

## callees

- `0x18000b524`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000b53a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000b53a`

## pseudocode

```c
BOOL __fastcall OnDeleteIf<void * &,void (*)(void * &),&void RevertRegister_(void * &)>::~OnDeleteIf<void * &,void (*)(void * &),&void RevertRegister_(void * &)>(
        __int64 a1)
{
  HANDLE *v1; // rbx
  BOOL result; // eax

  if ( !*(_BYTE *)(a1 + 8) )
  {
    v1 = *(HANDLE **)a1;
    result = UnregisterWaitEx(**(HANDLE **)a1, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b524  push    rbx
0x18000b526  sub     rsp, 20h
0x18000b52a  cmp     byte ptr [rcx+8], 0
0x18000b52e  jnz     short loc_18000B547
0x18000b530  mov     rbx, [rcx]
0x18000b533  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000b537  mov     rcx, [rbx]; WaitHandle
0x18000b53a  call    cs:__imp_UnregisterWaitEx
0x18000b540  mov     qword ptr [rbx], 0
0x18000b547  add     rsp, 20h
0x18000b54b  pop     rbx
0x18000b54c  retn
```
