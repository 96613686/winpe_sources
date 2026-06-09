# HTTP2Channel::CheckSendCompleteForSync(long,HTTP2SendContext *)

- ea: `0x180005d18`
- end: `0x180005d4a`
- name: `?CheckSendCompleteForSync@HTTP2Channel@@IEAAJJPEAVHTTP2SendContext@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800182f0`
- `0x180018340`

## callees

- `0x180005d18`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180005d36`
- `KERNEL32!SetEvent` at `0x180005d36`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::CheckSendCompleteForSync(
        HTTP2Channel *this,
        unsigned int a2,
        struct HTTP2SendContext *a3)
{
  if ( !*((_QWORD *)a3 + 8) )
    return 0;
  *((_QWORD *)a3 + 1) = a2;
  _InterlockedExchange((volatile __int32 *)a3 + 7, 1);
  SetEvent(*((HANDLE *)a3 + 8));
  return 3221360681LL;
}

```

## disassembly

```asm
0x180005d18  sub     rsp, 28h
0x180005d1c  cmp     qword ptr [r8+40h], 0
0x180005d21  jz      short loc_180005D43
0x180005d23  mov     eax, edx
0x180005d25  mov     [r8+8], rax
0x180005d29  mov     eax, 1
0x180005d2e  xchg    eax, [r8+1Ch]
0x180005d32  mov     rcx, [r8+40h]; hEvent
0x180005d36  call    cs:__imp_SetEvent
0x180005d3c  mov     eax, 0C0021029h
0x180005d41  jmp     short loc_180005D45
0x180005d43  xor     eax, eax
0x180005d45  add     rsp, 28h
0x180005d49  retn
```
