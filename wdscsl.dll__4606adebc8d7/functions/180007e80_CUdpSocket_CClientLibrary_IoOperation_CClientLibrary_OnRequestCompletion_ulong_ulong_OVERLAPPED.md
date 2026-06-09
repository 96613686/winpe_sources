# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::OnRequestCompletion(ulong,ulong,_OVERLAPPED *)

- ea: `0x180007e80`
- end: `0x180007fe4`
- name: `?OnRequestCompletion@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@UEAAXKKPEAU_OVERLAPPED@@@Z`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007e80`
- `0x180008110`
- `0x180008404`
- `0x1800095ac`
- `0x18000aa7c`
- `0x18000bd5c`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180007fb7`
- `KERNEL32!SetEvent` at `0x180007fb7`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180007f94`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180007f94`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180007fd8`

## pseudocode

```c
void __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::OnRequestCompletion(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  int v7; // r14d
  unsigned int v8; // edi
  __int64 v9; // rdx
  unsigned int Requests; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx

  v7 = a2;
  if ( *(_DWORD *)(a4 + 40) == 1 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 428));
    v8 = 0;
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 68), 0) )
    {
      Requests = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(a1);
      ElValidateWin32(Requests, v11, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1979);
      if ( !v7 )
      {
        if ( a3 )
        {
          v8 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::SockaddrToEndpoint(
                 v12,
                 a4 + 64,
                 *(unsigned int *)(a4 + 192),
                 a4 + 196);
          if ( !(unsigned int)ElValidateWin32(v8, v13, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1987) )
            *(_DWORD *)(*(_QWORD *)(a4 + 48) + 48LL) = a3;
        }
      }
      goto LABEL_11;
    }
    goto LABEL_6;
  }
  if ( *(_DWORD *)(a4 + 40) != 2 )
    goto LABEL_15;
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 424));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 68), 0) )
  {
LABEL_6:
    v8 = 5023;
    goto LABEL_11;
  }
  v8 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::ProcessSendQueue(a1);
  ElValidateWin32(v8, v9, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 2059);
LABEL_11:
  if ( v8 && v8 != 5023 && v8 != 995 )
    ElValidateWin32(v8, a2, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 2122);
LABEL_15:
  IoOperation<CClientLibrary>::Release(a4);
  CMRSWLock::ReaderLock((CMRSWLock *)(a1 + 496));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 480), 0xFFFFFFFF) == 1 )
    SetEvent(*(HANDLE *)(a1 + 488));
  CMRSWLock::ReaderRelease((CMRSWLock *)(a1 + 496));
}

```

## disassembly

```asm
0x180007e80  mov     [rsp+arg_8], rbx
0x180007e85  mov     [rsp+arg_10], rbp
0x180007e8a  push    rsi
0x180007e8b  push    rdi
0x180007e8c  push    r14
0x180007e8e  sub     rsp, 20h
0x180007e92  mov     rbx, rcx
0x180007e95  mov     rsi, r9
0x180007e98  mov     ecx, [r9+28h]
0x180007e9c  mov     ebp, r8d
0x180007e9f  mov     r14d, edx
0x180007ea2  sub     ecx, 1
0x180007ea5  jz      short loc_180007EE2
0x180007ea7  cmp     ecx, 1
0x180007eaa  jnz     loc_180007F82
0x180007eb0  lock dec dword ptr [rbx+1A8h]
0x180007eb7  xor     eax, eax
0x180007eb9  lock xadd [rbx+44h], eax
0x180007ebe  test    eax, eax
0x180007ec0  jnz     short loc_180007EF6
0x180007ec2  mov     rcx, rbx
0x180007ec5  call    ?ProcessSendQueue@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::ProcessSendQueue(void)
0x180007eca  mov     r9d, 80Bh
0x180007ed0  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180007ed7  mov     ecx, eax
0x180007ed9  mov     edi, eax
0x180007edb  call    ElValidateWin32
0x180007ee0  jmp     short loc_180007F5A
0x180007ee2  lock dec dword ptr [rbx+1ACh]
0x180007ee9  xor     edi, edi
0x180007eeb  xor     eax, eax
0x180007eed  lock xadd [rbx+44h], eax
0x180007ef2  test    eax, eax
0x180007ef4  jz      short loc_180007EFD
0x180007ef6  mov     edi, 139Fh
0x180007efb  jmp     short loc_180007F5A
0x180007efd  mov     rcx, rbx
0x180007f00  call    ?PostMaximumReadRequests@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(void)
0x180007f05  mov     ecx, eax
0x180007f07  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180007f0e  mov     r9d, 7BBh
0x180007f14  call    ElValidateWin32
0x180007f19  test    r14d, r14d
0x180007f1c  jnz     short loc_180007F5A
0x180007f1e  test    ebp, ebp
0x180007f20  jz      short loc_180007F5A
0x180007f22  mov     r8d, [rsi+0C0h]
0x180007f29  lea     r9, [rsi+0C4h]
0x180007f30  lea     rdx, [rsi+40h]
0x180007f34  call    ?SockaddrToEndpoint@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKPEAUsockaddr_storage@@HPEAUtagWDS_ENDPOINT@@@Z; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::SockaddrToEndpoint(sockaddr_storage *,int,tagWDS_ENDPOINT *)
0x180007f39  mov     r9d, 7C3h
0x180007f3f  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180007f46  mov     ecx, eax
0x180007f48  mov     edi, eax
0x180007f4a  call    ElValidateWin32
0x180007f4f  test    eax, eax
0x180007f51  jnz     short loc_180007F5A
0x180007f53  mov     rax, [rsi+30h]
0x180007f57  mov     [rax+30h], ebp
0x180007f5a  test    edi, edi
0x180007f5c  jz      short loc_180007F82
0x180007f5e  cmp     edi, 139Fh
0x180007f64  jz      short loc_180007F82
0x180007f66  cmp     edi, 3E3h
0x180007f6c  jz      short loc_180007F82
0x180007f6e  mov     r9d, 84Ah
0x180007f74  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180007f7b  mov     ecx, edi
0x180007f7d  call    ElValidateWin32
0x180007f82  mov     rcx, rsi
0x180007f85  call    ?Release@?$IoOperation@VCClientLibrary@@@@QEAAKXZ; IoOperation<CClientLibrary>::Release(void)
0x180007f8a  lea     rdi, [rbx+1F0h]
0x180007f91  mov     rcx, rdi
0x180007f94  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180007f9b  nop     dword ptr [rax+rax+00h]
0x180007fa0  or      eax, 0FFFFFFFFh
0x180007fa3  lock xadd [rbx+1E0h], eax
0x180007fab  cmp     eax, 1
0x180007fae  jnz     short loc_180007FC3
0x180007fb0  mov     rcx, [rbx+1E8h]; hEvent
0x180007fb7  call    cs:__imp_SetEvent
0x180007fbe  nop     dword ptr [rax+rax+00h]
0x180007fc3  mov     rcx, rdi
0x180007fc6  mov     rbx, [rsp+38h+arg_8]
0x180007fcb  mov     rbp, [rsp+38h+arg_10]
0x180007fd0  add     rsp, 20h
0x180007fd4  pop     r14
0x180007fd6  pop     rdi
0x180007fd7  pop     rsi
0x180007fd8  jmp     cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
```
