# HTTP2PlugChannel::Unplug(void)

- ea: `0x18001ac8c`
- end: `0x18001ada5`
- name: `?Unplug@HTTP2PlugChannel@@QEAAJXZ`
- size: `281`
- prototype: `__int64 __fastcall(HTTP2PlugChannel *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006050`
- `0x180007dcc`
- `0x18000dfe8`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`

## callees

- `0x180005428`
- `0x180009d58`
- `0x180017d90`
- `0x18001ac8c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001ad21`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ad71`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ad8b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ad21`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ad71`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ad8b`
- `ntdll!RtlEnterCriticalSection` at `0x18001acdf`
- `ntdll!RtlEnterCriticalSection` at `0x18001ad51`
- `ntdll!RtlEnterCriticalSection` at `0x18001acdf`
- `ntdll!RtlEnterCriticalSection` at `0x18001ad51`
- `RPCRT4!I_RpcLogEvent` at `0x18001acbf`
- `RPCRT4!I_RpcLogEvent` at `0x18001acbf`

## pseudocode

```c
__int64 __fastcall HTTP2PlugChannel::Unplug(HTTP2PlugChannel *this, __int64 a2)
{
  HTTP2PlugChannel *v2; // rsi
  HTTP2PlugChannel *v3; // r8
  __int64 v4; // rdx
  unsigned int v5; // ebp
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  __int64 v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  __int64 v10; // rax

  v2 = this;
  v3 = this;
  LOBYTE(this) = 50;
  LOBYTE(a2) = 111;
  I_RpcLogEvent(this, a2, v3, 18350090, 0, 0, 0);
  while ( 1 )
  {
    v5 = HTTP2Channel::BeginSimpleSubmitAsync(*((HTTP2Channel **)v2 + 3), v4);
    if ( v5 )
      return v5;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v2 + 56));
    v6 = (_QWORD *)((char *)v2 + 40);
    v7 = (_QWORD *)*((_QWORD *)v2 + 5);
    if ( (HTTP2PlugChannel *)v7[1] != (HTTP2PlugChannel *)((char *)v2 + 40) )
      goto LABEL_12;
    v8 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_12;
    *v6 = v8;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)v2 + 56);
    *(_QWORD *)(v8 + 8) = v6;
    if ( v7 == v6 )
    {
      *((_DWORD *)v2 + 8) = 3;
      RtlLeaveCriticalSection(v9);
      v5 = 0;
      HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)v2 + 3));
      return v5;
    }
    *v7 = 0;
    v7[1] = 0;
    RtlLeaveCriticalSection(v9);
    v5 = HTTP2TransportChannel::Send(v2, (struct HTTP2SendContext *)(v7 - 9));
    HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)v2 + 3));
    if ( v5 && v5 != -1073606614 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v2 + 56));
      v10 = *v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 )
LABEL_12:
        __fastfail(3u);
      *v7 = v10;
      v7[1] = v6;
      *(_QWORD *)(v10 + 8) = v7;
      *v6 = v7;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v2 + 56));
      return v5;
    }
  }
}

```

## disassembly

```asm
0x18001ac8c  push    rbx
0x18001ac8e  push    rbp
0x18001ac8f  push    rsi
0x18001ac90  push    rdi
0x18001ac91  push    r14
0x18001ac93  sub     rsp, 40h
0x18001ac97  mov     rsi, rcx
0x18001ac9a  mov     [rsp+68h+var_38], 0
0x18001aca2  mov     r8, rcx
0x18001aca5  mov     [rsp+68h+var_40], 0
0x18001acad  mov     cl, 32h ; '2'
0x18001acaf  mov     [rsp+68h+var_48], 0
0x18001acb7  mov     r9d, 118000Ah
0x18001acbd  mov     dl, 6Fh ; 'o'
0x18001acbf  call    cs:__imp_I_RpcLogEvent
0x18001acc5  mov     rcx, [rsi+18h]; this
0x18001acc9  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x18001acce  mov     ebp, eax
0x18001acd0  test    eax, eax
0x18001acd2  jnz     loc_18001AD77
0x18001acd8  lea     r14, [rsi+38h]
0x18001acdc  mov     rcx, r14; CriticalSection
0x18001acdf  call    cs:__imp_RtlEnterCriticalSection
0x18001ace5  lea     rdi, [rsi+28h]
0x18001ace9  mov     rbx, [rdi]
0x18001acec  cmp     [rbx+8], rdi
0x18001acf0  jnz     loc_18001AD9E
0x18001acf6  mov     rax, [rbx]
0x18001acf9  cmp     [rax+8], rbx
0x18001acfd  jnz     loc_18001AD9E
0x18001ad03  mov     [rdi], rax
0x18001ad06  mov     rcx, r14; CriticalSection
0x18001ad09  mov     [rax+8], rdi
0x18001ad0d  cmp     rbx, rdi
0x18001ad10  jz      short loc_18001AD84
0x18001ad12  mov     qword ptr [rbx], 0
0x18001ad19  mov     qword ptr [rbx+8], 0
0x18001ad21  call    cs:__imp_RtlLeaveCriticalSection
0x18001ad27  lea     rdx, [rbx-48h]; struct HTTP2SendContext *
0x18001ad2b  mov     rcx, rsi; this
0x18001ad2e  call    ?Send@HTTP2TransportChannel@@UEAAJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::Send(HTTP2SendContext *)
0x18001ad33  mov     rcx, [rsi+18h]; this
0x18001ad37  mov     ebp, eax
0x18001ad39  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x18001ad3e  test    ebp, ebp
0x18001ad40  jz      short loc_18001ACC5
0x18001ad42  cmp     ebp, 0C002102Ah
0x18001ad48  jz      loc_18001ACC5
0x18001ad4e  mov     rcx, r14; CriticalSection
0x18001ad51  call    cs:__imp_RtlEnterCriticalSection
0x18001ad57  mov     rax, [rdi]
0x18001ad5a  cmp     [rax+8], rdi
0x18001ad5e  jnz     short loc_18001AD9E
0x18001ad60  mov     [rbx], rax
0x18001ad63  mov     rcx, r14; CriticalSection
0x18001ad66  mov     [rbx+8], rdi
0x18001ad6a  mov     [rax+8], rbx
0x18001ad6e  mov     [rdi], rbx
0x18001ad71  call    cs:__imp_RtlLeaveCriticalSection
0x18001ad77  mov     eax, ebp
0x18001ad79  add     rsp, 40h
0x18001ad7d  pop     r14
0x18001ad7f  pop     rdi
0x18001ad80  pop     rsi
0x18001ad81  pop     rbp
0x18001ad82  pop     rbx
0x18001ad83  retn
0x18001ad84  mov     dword ptr [rsi+20h], 3
0x18001ad8b  call    cs:__imp_RtlLeaveCriticalSection
0x18001ad91  mov     rcx, [rsi+18h]; this
0x18001ad95  xor     ebp, ebp
0x18001ad97  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x18001ad9c  jmp     short loc_18001AD77
0x18001ad9e  mov     ecx, 3
0x18001ada3  int     29h; Win8: RtlFailFast(ecx)
```
