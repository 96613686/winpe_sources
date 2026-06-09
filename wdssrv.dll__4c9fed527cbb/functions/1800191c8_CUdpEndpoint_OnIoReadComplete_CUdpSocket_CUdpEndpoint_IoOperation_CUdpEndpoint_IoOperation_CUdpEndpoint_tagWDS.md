# CUdpEndpoint::OnIoReadComplete(CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>> *,IoOperation<CUdpEndpoint> *,tagWDS_ENDPOINT *,CMemoryBuffer *)

- ea: `0x1800191c8`
- end: `0x180019290`
- name: `?OnIoReadComplete@CUdpEndpoint@@QEAAXPEAV?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@PEAU?$IoOperation@VCUdpEndpoint@@@@PEAUtagWDS_ENDPOINT@@PEAVCMemoryBuffer@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019668`

## callees

- `0x1800191c8`
- `0x18001d010`

## import_xrefs

- `WdsServerCommonLib!?Batch@CPerfCounters@@QEAAKKZZ` at `0x180019233`
- `WdsServerCommonLib!?Batch@CPerfCounters@@QEAAKKZZ` at `0x180019233`

## pseudocode

```c
__int64 __fastcall CUdpEndpoint::OnIoReadComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v8; // rbx
  volatile signed __int32 *v9; // rdi
  int v10; // [rsp+20h] [rbp-28h]
  int v11; // [rsp+28h] [rbp-20h]
  int v12; // [rsp+38h] [rbp-10h]

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 88), 0);
  if ( !(_DWORD)result )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 72) + 60LL), 0);
    if ( !(_DWORD)result )
    {
      v8 = *(_QWORD *)(a1 + 64);
      v9 = *(volatile signed __int32 **)(a1 + 72);
      v12 = 1;
      v11 = 2;
      v10 = 1;
      CPerfCounters::Batch((CPerfCounters *)&g_PerfCounters, 2u, 0, 0, v10, v11, 0, v12);
      _InterlockedIncrement(v9 + 14);
      _InterlockedIncrement((volatile signed __int32 *)(a3 + 1248));
      return (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v9 + 72LL))(
               v9,
               a3,
               v8,
               a1 + 988,
               a4,
               *(_QWORD *)(a3 + 48));
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800191c8  mov     r11, rsp
0x1800191cb  mov     [r11+8], rbx
0x1800191cf  mov     [r11+10h], rbp
0x1800191d3  mov     [r11+18h], rsi
0x1800191d7  mov     [r11+20h], rdi
0x1800191db  push    r14
0x1800191dd  sub     rsp, 40h
0x1800191e1  mov     r14, r9
0x1800191e4  mov     rbp, r8
0x1800191e7  mov     rsi, rcx
0x1800191ea  xor     eax, eax
0x1800191ec  lock xadd [rcx+58h], eax
0x1800191f1  test    eax, eax
0x1800191f3  jnz     short loc_180019274
0x1800191f5  mov     rdx, [rcx+48h]
0x1800191f9  lock xadd [rdx+3Ch], eax
0x1800191fe  test    eax, eax
0x180019200  jnz     short loc_180019274
0x180019202  mov     rbx, [rcx+40h]
0x180019206  lea     edx, [rax+2]
0x180019209  mov     rdi, [rcx+48h]
0x18001920d  xor     r9d, r9d
0x180019210  mov     [rsp+48h+var_10], 1
0x180019218  lea     rcx, ?g_PerfCounters@@3VCWdsPerfCounters@@A; CWdsPerfCounters g_PerfCounters
0x18001921f  and     qword ptr [r11-18h], 0
0x180019224  xor     r8d, r8d
0x180019227  mov     [rsp+48h+var_20], edx
0x18001922b  mov     dword ptr [rsp+48h+var_28], 1
0x180019233  call    cs:__imp_?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18001923a  nop     dword ptr [rax+rax+00h]
0x18001923f  lock inc dword ptr [rdi+38h]
0x180019243  lock inc dword ptr [rbp+4E0h]
0x18001924a  mov     rdx, [rbp+30h]
0x18001924e  lea     r9, [rsi+3DCh]
0x180019255  mov     rax, [rdi]
0x180019258  mov     r8, rbx
0x18001925b  mov     qword ptr [rsp+48h+var_20], rdx
0x180019260  mov     rcx, rdi
0x180019263  mov     rdx, rbp
0x180019266  mov     [rsp+48h+var_28], r14
0x18001926b  mov     rax, [rax+48h]
0x18001926f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019274  mov     rbx, [rsp+48h+arg_0]
0x180019279  mov     rbp, [rsp+48h+arg_8]
0x18001927e  mov     rsi, [rsp+48h+arg_10]
0x180019283  mov     rdi, [rsp+48h+arg_18]
0x180019288  add     rsp, 40h
0x18001928c  pop     r14
0x18001928e  retn
```
