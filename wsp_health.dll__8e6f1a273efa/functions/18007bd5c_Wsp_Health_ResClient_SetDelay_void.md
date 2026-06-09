# Wsp::Health::ResClient::SetDelay(void)

- ea: `0x18007bd5c`
- end: `0x18007bd9d`
- name: `?SetDelay@ResClient@Health@Wsp@@AEAAXXZ`
- size: `65`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007ae8c`

## callees

- `0x18007bd04`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007bd80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007bd80`

## pseudocode

```c
void __fastcall Wsp::Health::ResClient::SetDelay(PTP_TIMER *this)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pftDueTime = (struct _FILETIME)-300000000LL;
  SetThreadpoolTimer(this[42], &pftDueTime, 0, 0);
  Wsp::Health::ResClient::SetCanConnect((Wsp::Health::ResClient *)this, 0);
}

```

## disassembly

```asm
0x18007bd5c  push    rbx
0x18007bd5e  sub     rsp, 20h
0x18007bd62  mov     rbx, rcx
0x18007bd65  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x18007bd6e  mov     rcx, [rcx+150h]; pti
0x18007bd75  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18007bd7a  xor     r9d, r9d; msWindowLength
0x18007bd7d  xor     r8d, r8d; msPeriod
0x18007bd80  call    cs:__imp_SetThreadpoolTimer
0x18007bd87  nop     dword ptr [rax+rax+00h]
0x18007bd8c  xor     edx, edx; bool
0x18007bd8e  mov     rcx, rbx; this
0x18007bd91  call    ?SetCanConnect@ResClient@Health@Wsp@@QEAAX_N@Z; Wsp::Health::ResClient::SetCanConnect(bool)
0x18007bd96  add     rsp, 20h
0x18007bd9a  pop     rbx
0x18007bd9b  retn
```
