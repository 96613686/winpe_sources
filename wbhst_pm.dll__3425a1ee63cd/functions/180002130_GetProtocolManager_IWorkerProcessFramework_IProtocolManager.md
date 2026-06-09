# GetProtocolManager(IWorkerProcessFramework *,IProtocolManager * *)

- ea: `0x180002130`
- end: `0x18000222a`
- name: `?GetProtocolManager@@YAJPEAVIWorkerProcessFramework@@PEAPEAVIProtocolManager@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(struct IWorkerProcessFramework *, struct IProtocolManager **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180002130`
- `0x180002230`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall GetProtocolManager(struct IWorkerProcessFramework *a1, struct IProtocolManager **a2)
{
  struct IProtocolManager *v4; // rax
  struct IProtocolManager *v5; // rbx
  int v6; // edi

  v4 = (struct IProtocolManager *)operator new(0x78u);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 13) = 1;
    *(_QWORD *)v4 = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'};
    *((_QWORD *)v4 + 7) = 0;
    *((_QWORD *)v4 + 1) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'};
    *((_QWORD *)v4 + 8) = 0;
    *((_QWORD *)v4 + 2) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'};
    *((_QWORD *)v4 + 3) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'};
    *((_QWORD *)v4 + 4) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'};
    *((_QWORD *)v4 + 5) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'};
    *((_QWORD *)v4 + 9) = 0;
    *((_QWORD *)v4 + 10) = 0;
    *((_QWORD *)v4 + 11) = 0;
    *((_QWORD *)v4 + 12) = 0;
    *((_QWORD *)v4 + 13) = 0;
    *((_QWORD *)v4 + 14) = 0;
    *((_DWORD *)v4 + 12) = 1297107031;
    v6 = WEBHOST_PROTOCOL_MANAGER::InitializeInstance(v4, a1);
    if ( v6 >= 0 )
    {
      *a2 = v5;
      return 0;
    }
    else
    {
      (*(void (__fastcall **)(struct IProtocolManager *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002130  mov     [rsp+arg_0], rbx
0x180002135  mov     [rsp+arg_8], rsi
0x18000213a  push    rdi
0x18000213b  sub     rsp, 20h
0x18000213f  mov     rdi, rcx
0x180002142  mov     rsi, rdx
0x180002145  mov     ecx, 78h ; 'x'; Size
0x18000214a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000214f  mov     rbx, rax
0x180002152  test    rax, rax
0x180002155  jz      loc_180002213
0x18000215b  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIProtocolManager@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'}
0x180002162  mov     dword ptr [rbx+34h], 1
0x180002169  mov     [rbx], rax
0x18000216c  mov     rdx, rdi; struct IWorkerProcessFramework *
0x18000216f  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmCustomActions@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'}
0x180002176  mov     qword ptr [rbx+38h], 0
0x18000217e  mov     [rbx+8], rax
0x180002182  mov     rcx, rbx; this
0x180002185  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmHealthAndIdleMonitor@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'}
0x18000218c  mov     qword ptr [rbx+40h], 0
0x180002194  mov     [rbx+10h], rax
0x180002198  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmListenerChannelManager@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'}
0x18000219f  mov     [rbx+18h], rax
0x1800021a3  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmApplicationPreload@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'}
0x1800021aa  mov     [rbx+20h], rax
0x1800021ae  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmIdleTimeOutAction@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'}
0x1800021b5  mov     [rbx+28h], rax
0x1800021b9  mov     qword ptr [rbx+48h], 0
0x1800021c1  mov     qword ptr [rbx+50h], 0
0x1800021c9  mov     qword ptr [rbx+58h], 0
0x1800021d1  mov     qword ptr [rbx+60h], 0
0x1800021d9  mov     qword ptr [rbx+68h], 0
0x1800021e1  mov     qword ptr [rbx+70h], 0
0x1800021e9  mov     dword ptr [rbx+30h], 4D504857h
0x1800021f0  call    ?InitializeInstance@WEBHOST_PROTOCOL_MANAGER@@QEAAJPEAVIWorkerProcessFramework@@@Z; WEBHOST_PROTOCOL_MANAGER::InitializeInstance(IWorkerProcessFramework *)
0x1800021f5  mov     edi, eax
0x1800021f7  test    eax, eax
0x1800021f9  jns     short loc_18000220C
0x1800021fb  mov     rcx, [rbx]
0x1800021fe  mov     rax, [rcx+8]
0x180002202  mov     rcx, rbx
0x180002205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220a  jmp     short loc_180002218
0x18000220c  mov     [rsi], rbx
0x18000220f  xor     edi, edi
0x180002211  jmp     short loc_180002218
0x180002213  mov     edi, 8007000Eh
0x180002218  mov     rbx, [rsp+28h+arg_0]
0x18000221d  mov     eax, edi
0x18000221f  mov     rsi, [rsp+28h+arg_8]
0x180002224  add     rsp, 20h
0x180002228  pop     rdi
0x180002229  retn
```
