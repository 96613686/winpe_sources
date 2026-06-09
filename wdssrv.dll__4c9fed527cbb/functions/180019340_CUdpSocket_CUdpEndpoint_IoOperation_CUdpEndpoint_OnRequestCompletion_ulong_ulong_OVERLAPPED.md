# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::OnRequestCompletion(ulong,ulong,_OVERLAPPED *)

- ea: `0x180019340`
- end: `0x18001942d`
- name: `?OnRequestCompletion@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@UEAAXKKPEAU_OVERLAPPED@@@Z`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003160`
- `0x180003944`
- `0x180019340`
- `0x180019668`
- `0x1800197b0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180019403`
- `KERNEL32!SetEvent` at `0x180019403`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800193e0`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800193e0`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180019421`

## pseudocode

```c
void __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::OnRequestCompletion(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  unsigned int Completion; // edi
  __int64 v7; // rdx

  if ( *(_DWORD *)(a4 + 40) == 1 )
  {
    Completion = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessReadCompletion(a1, a2, a3, a4);
  }
  else
  {
    if ( *(_DWORD *)(a4 + 40) != 2 )
      goto LABEL_11;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 424));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 68), 0) )
    {
      Completion = 5023;
    }
    else
    {
      Completion = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessSendQueue(a1);
      ElValidateWin32(Completion, v7, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 2059);
    }
  }
  if ( Completion && Completion != 5023 && Completion != 995 )
    ElValidateWin32(Completion, a2, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 2122);
LABEL_11:
  IoOperation<CUdpEndpoint>::Release(a4);
  CMRSWLock::ReaderLock((CMRSWLock *)(a1 + 496));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 480), 0xFFFFFFFF) == 1 )
    SetEvent(*(HANDLE *)(a1 + 488));
  CMRSWLock::ReaderRelease((CMRSWLock *)(a1 + 496));
}

```

## disassembly

```asm
0x180019340  mov     [rsp+arg_8], rbx
0x180019345  mov     [rsp+arg_10], rsi
0x18001934a  push    rdi
0x18001934b  sub     rsp, 20h
0x18001934f  mov     rbx, rcx
0x180019352  mov     rsi, r9
0x180019355  mov     ecx, [r9+28h]
0x180019359  sub     ecx, 1
0x18001935c  jz      short loc_18001939C
0x18001935e  cmp     ecx, 1
0x180019361  jnz     short loc_1800193CE
0x180019363  lock dec dword ptr [rbx+1A8h]
0x18001936a  xor     eax, eax
0x18001936c  lock xadd [rbx+44h], eax
0x180019371  test    eax, eax
0x180019373  jz      short loc_18001937C
0x180019375  mov     edi, 139Fh
0x18001937a  jmp     short loc_1800193A6
0x18001937c  mov     rcx, rbx
0x18001937f  call    ?ProcessSendQueue@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessSendQueue(void)
0x180019384  mov     r9d, 80Bh
0x18001938a  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019391  mov     ecx, eax
0x180019393  mov     edi, eax
0x180019395  call    ElValidateWin32
0x18001939a  jmp     short loc_1800193A6
0x18001939c  mov     rcx, rbx
0x18001939f  call    ?ProcessReadCompletion@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKKKPEAU?$IoOperation@VCUdpEndpoint@@@@@Z; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessReadCompletion(ulong,ulong,IoOperation<CUdpEndpoint> *)
0x1800193a4  mov     edi, eax
0x1800193a6  test    edi, edi
0x1800193a8  jz      short loc_1800193CE
0x1800193aa  cmp     edi, 139Fh
0x1800193b0  jz      short loc_1800193CE
0x1800193b2  cmp     edi, 3E3h
0x1800193b8  jz      short loc_1800193CE
0x1800193ba  mov     r9d, 84Ah
0x1800193c0  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x1800193c7  mov     ecx, edi
0x1800193c9  call    ElValidateWin32
0x1800193ce  mov     rcx, rsi
0x1800193d1  call    ?Release@?$IoOperation@VCUdpEndpoint@@@@QEAAKXZ; IoOperation<CUdpEndpoint>::Release(void)
0x1800193d6  lea     rdi, [rbx+1F0h]
0x1800193dd  mov     rcx, rdi
0x1800193e0  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x1800193e7  nop     dword ptr [rax+rax+00h]
0x1800193ec  or      eax, 0FFFFFFFFh
0x1800193ef  lock xadd [rbx+1E0h], eax
0x1800193f7  cmp     eax, 1
0x1800193fa  jnz     short loc_18001940F
0x1800193fc  mov     rcx, [rbx+1E8h]; hEvent
0x180019403  call    cs:__imp_SetEvent
0x18001940a  nop     dword ptr [rax+rax+00h]
0x18001940f  mov     rcx, rdi
0x180019412  mov     rbx, [rsp+28h+arg_8]
0x180019417  mov     rsi, [rsp+28h+arg_10]
0x18001941c  add     rsp, 20h
0x180019420  pop     rdi
0x180019421  jmp     cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
```
