# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(void)

- ea: `0x180019434`
- end: `0x180019491`
- name: `?PostMaximumReadRequests@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ`
- size: `93`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180019668`
- `0x1800197b0`
- `0x180019a44`

## callees

- `0x180003944`
- `0x180019434`
- `0x180019498`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(__int64 a1)
{
  unsigned int Request; // edi
  __int64 v3; // rdx

  Request = 0;
  if ( (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 428), 0) < *(_DWORD *)(a1 + 72) )
  {
    do
      Request = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostReadRequest(a1);
    while ( !(unsigned int)ElValidateWin32(Request, v3, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1674)
         && (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 428), 0) < *(_DWORD *)(a1 + 72) );
  }
  return Request;
}

```

## disassembly

```asm
0x180019434  mov     [rsp+arg_0], rbx
0x180019439  push    rdi
0x18001943a  sub     rsp, 20h
0x18001943e  xor     edi, edi
0x180019440  mov     rbx, rcx
0x180019443  xor     eax, eax
0x180019445  lock xadd [rcx+1ACh], eax
0x18001944d  cmp     eax, [rcx+48h]
0x180019450  jnb     short loc_180019483
0x180019452  mov     rcx, rbx
0x180019455  call    ?PostReadRequest@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostReadRequest(void)
0x18001945a  mov     r9d, 68Ah
0x180019460  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019467  mov     ecx, eax
0x180019469  mov     edi, eax
0x18001946b  call    ElValidateWin32
0x180019470  test    eax, eax
0x180019472  jnz     short loc_180019483
0x180019474  xor     ecx, ecx
0x180019476  lock xadd [rbx+1ACh], ecx
0x18001947e  cmp     ecx, [rbx+48h]
0x180019481  jb      short loc_180019452
0x180019483  mov     rbx, [rsp+28h+arg_0]
0x180019488  mov     eax, edi
0x18001948a  add     rsp, 20h
0x18001948e  pop     rdi
0x18001948f  retn
```
