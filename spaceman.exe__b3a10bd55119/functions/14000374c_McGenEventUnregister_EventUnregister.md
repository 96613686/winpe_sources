# McGenEventUnregister_EventUnregister

- ea: `0x14000374c`
- end: `0x140003774`
- name: `McGenEventUnregister_EventUnregister`
- size: `40`
- prototype: `ULONG __fastcall(REGHANDLE *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002074`
- `0x1400037dc`
- `0x140009328`

## callees

- `0x14000374c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140003761`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140003761`

## pseudocode

```c
ULONG __fastcall McGenEventUnregister_EventUnregister(REGHANDLE *a1)
{
  REGHANDLE v2; // rcx
  ULONG result; // eax

  v2 = *a1;
  if ( !v2 )
    return 0;
  result = EventUnregister(v2);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x14000374c  push    rbx
0x14000374e  sub     rsp, 20h
0x140003752  mov     rbx, rcx
0x140003755  mov     rcx, [rcx]; RegHandle
0x140003758  test    rcx, rcx
0x14000375b  jnz     short loc_140003761
0x14000375d  xor     eax, eax
0x14000375f  jmp     short loc_14000376E
0x140003761  call    cs:__imp_EventUnregister
0x140003767  mov     qword ptr [rbx], 0
0x14000376e  add     rsp, 20h
0x140003772  pop     rbx
0x140003773  retn
```
