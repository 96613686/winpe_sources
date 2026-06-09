# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(void)

- ea: `0x180008110`
- end: `0x18000816d`
- name: `?PostMaximumReadRequests@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007e80`
- `0x180008404`

## callees

- `0x180008110`
- `0x180008174`
- `0x18000bd5c`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(__int64 a1)
{
  unsigned int Request; // edi
  __int64 v3; // rdx

  Request = 0;
  if ( (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 428), 0) < *(_DWORD *)(a1 + 72) )
  {
    do
      Request = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostReadRequest(a1);
    while ( !(unsigned int)ElValidateWin32(Request, v3, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1674)
         && (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 428), 0) < *(_DWORD *)(a1 + 72) );
  }
  return Request;
}

```

## disassembly

```asm
0x180008110  mov     [rsp+arg_0], rbx
0x180008115  push    rdi
0x180008116  sub     rsp, 20h
0x18000811a  xor     edi, edi
0x18000811c  mov     rbx, rcx
0x18000811f  xor     eax, eax
0x180008121  lock xadd [rcx+1ACh], eax
0x180008129  cmp     eax, [rcx+48h]
0x18000812c  jnb     short loc_18000815F
0x18000812e  mov     rcx, rbx
0x180008131  call    ?PostReadRequest@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostReadRequest(void)
0x180008136  mov     r9d, 68Ah
0x18000813c  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180008143  mov     ecx, eax
0x180008145  mov     edi, eax
0x180008147  call    ElValidateWin32
0x18000814c  test    eax, eax
0x18000814e  jnz     short loc_18000815F
0x180008150  xor     ecx, ecx
0x180008152  lock xadd [rbx+1ACh], ecx
0x18000815a  cmp     ecx, [rbx+48h]
0x18000815d  jb      short loc_18000812E
0x18000815f  mov     rbx, [rsp+28h+arg_0]
0x180008164  mov     eax, edi
0x180008166  add     rsp, 20h
0x18000816a  pop     rdi
0x18000816b  retn
```
