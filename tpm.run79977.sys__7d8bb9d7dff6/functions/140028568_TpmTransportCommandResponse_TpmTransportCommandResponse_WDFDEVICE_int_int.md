# TpmTransportCommandResponse::TpmTransportCommandResponse(WDFDEVICE__ *,int,int)

- ea: `0x140028568`
- end: `0x1400285be`
- name: `??0TpmTransportCommandResponse@@QEAA@PEAUWDFDEVICE__@@HH@Z`
- size: `86`
- prototype: `TpmTransportCommandResponse *__fastcall(TpmTransportCommandResponse *__hidden this, struct WDFDEVICE__ *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001a0f4`

## callees

- `0x140022ea0`
- `0x140028458`
- `0x140028568`

## pseudocode

```c
TpmTransportCommandResponse *__fastcall TpmTransportCommandResponse::TpmTransportCommandResponse(
        TpmTransportCommandResponse *this,
        struct WDFDEVICE__ *a2,
        int a3,
        int a4)
{
  int inited; // eax
  TpmTransportCommandResponse *result; // rax

  TpmTransportMemBase::TpmTransportMemBase(this, a2, a3);
  *(_QWORD *)this = &TpmTransportACPI::`vftable';
  inited = 0;
  *((_QWORD *)this + 65) = 0;
  if ( a4 )
    inited = TpmTransportACPI::InitACPIWorkitem(this);
  *((_DWORD *)this + 2) = inited;
  *(_QWORD *)this = &TpmTransportCommandResponse::`vftable';
  result = this;
  *((_DWORD *)this + 132) = a4;
  return result;
}

```

## disassembly

```asm
0x140028568  mov     [rsp+arg_0], rbx
0x14002856d  push    rdi
0x14002856e  sub     rsp, 20h
0x140028572  mov     edi, r9d
0x140028575  mov     rbx, rcx
0x140028578  call    ??0TpmTransportMemBase@@QEAA@PEAUWDFDEVICE__@@H@Z; TpmTransportMemBase::TpmTransportMemBase(WDFDEVICE__ *,int)
0x14002857d  lea     rax, ??_7TpmTransportACPI@@6B@; const TpmTransportACPI::`vftable'
0x140028584  mov     [rbx], rax
0x140028587  xor     eax, eax
0x140028589  mov     [rbx+208h], rax
0x140028590  test    edi, edi
0x140028592  jz      short loc_14002859C
0x140028594  mov     rcx, rbx; this
0x140028597  call    ?InitACPIWorkitem@TpmTransportACPI@@AEAAJXZ; TpmTransportACPI::InitACPIWorkitem(void)
0x14002859c  mov     [rbx+8], eax
0x14002859f  lea     rax, ??_7TpmTransportCommandResponse@@6B@; const TpmTransportCommandResponse::`vftable'
0x1400285a6  mov     [rbx], rax
0x1400285a9  mov     rax, rbx
0x1400285ac  mov     [rbx+210h], edi
0x1400285b2  mov     rbx, [rsp+28h+arg_0]
0x1400285b7  add     rsp, 20h
0x1400285bb  pop     rdi
0x1400285bc  retn
```
