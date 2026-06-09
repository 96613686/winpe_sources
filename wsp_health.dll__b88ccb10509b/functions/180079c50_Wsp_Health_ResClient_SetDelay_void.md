# Wsp::Health::ResClient::SetDelay(void)

- ea: `0x180079c50`
- end: `0x180079c8a`
- name: `?SetDelay@ResClient@Health@Wsp@@AEAAXXZ`
- size: `58`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180078ec8`

## callees

- `0x180079c04`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180079c74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180079c74`

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
0x180079c50  push    rbx
0x180079c52  sub     rsp, 20h
0x180079c56  mov     rbx, rcx
0x180079c59  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x180079c62  mov     rcx, [rcx+150h]; pti
0x180079c69  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180079c6e  xor     r9d, r9d; msWindowLength
0x180079c71  xor     r8d, r8d; msPeriod
0x180079c74  call    cs:__imp_SetThreadpoolTimer
0x180079c7a  xor     edx, edx; bool
0x180079c7c  mov     rcx, rbx; this
0x180079c7f  call    ?SetCanConnect@ResClient@Health@Wsp@@QEAAX_N@Z; Wsp::Health::ResClient::SetCanConnect(bool)
0x180079c84  add     rsp, 20h
0x180079c88  pop     rbx
0x180079c89  retn
```
