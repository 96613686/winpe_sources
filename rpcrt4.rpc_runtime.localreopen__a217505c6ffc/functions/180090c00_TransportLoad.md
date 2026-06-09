# TransportLoad

- ea: `0x180090c00`
- end: `0x180090d89`
- name: `TransportLoad`
- size: `393`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180090b10`

## callees

- `0x180023020`
- `0x180090c00`
- `0x180090d90`
- `0x180090f00`
- `0x180090fc8`
- `0x1800aac88`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180090d5d`
- `ntdll!RtlDeleteCriticalSection` at `0x180090d5d`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180090c9e`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180090cbb`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180090c9e`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180090cbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090c76`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090c76`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x180090d6b`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x180090d6b`

## pseudocode

```c
__int64 __fastcall TransportLoad(wchar_t *String1, const struct RPC_CONNECTION_TRANSPORT **a2)
{
  bool v2; // zf
  struct TransportProtocol *v5; // rax
  struct TransportProtocol *v6; // rbx
  TransportProtocol *v7; // rdi
  __int64 v8; // rsi
  int v9; // eax
  const struct RPC_CONNECTION_TRANSPORT *v11; // rax

  v2 = dword_1800FF4DC == 0;
  *a2 = 0;
  if ( !v2 )
    goto LABEL_11;
  v5 = (struct TransportProtocol *)AllocWrapper(0x480u);
  v6 = v5;
  if ( v5 )
  {
    v7 = v5;
    v8 = 16;
    do
    {
      TransportProtocol::TransportProtocol(v7);
      v7 = (TransportProtocol *)((char *)v7 + 72);
      --v8;
    }
    while ( v8 );
    TransportProtocolArray = v6;
    gdwComputerNameLength = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, &gpstrComputerName, &gdwComputerNameLength) )
    {
      ++gdwComputerNameLength;
      if ( RtlInitializeCriticalSectionAndSpinCount(&AddressListLock, 0x80000000) >= 0 )
      {
        if ( RtlInitializeCriticalSectionAndSpinCount(&PNPNotificationsLock, 0x80000000) >= 0 )
        {
          if ( (_DWORD)gBCacheMode == 1 )
            gPostSize = 16;
          dword_1800FF4DC = 1;
LABEL_11:
          v9 = MapProtseq(String1);
          if ( v9 )
          {
            if ( v9 != 1 )
            {
              if ( v9 == 3 )
              {
                if ( (unsigned __int8)IsGetLocalVmAliasNamePresent() && (unsigned int)RemoteWinRTActivation() == 1 )
                  off_1800FE468 = 0;
                v11 = (const struct RPC_CONNECTION_TRANSPORT *)&NMP_TransportInterface;
                goto LABEL_18;
              }
              if ( v9 != 6 && v9 != 15 )
                return 1703;
            }
            v11 = WS_TransportLoad(v9);
            if ( v11 )
            {
LABEL_18:
              *a2 = v11;
              return 0;
            }
          }
          return 1703;
        }
        RtlDeleteCriticalSection(&AddressListLock);
      }
    }
  }
  else
  {
    TransportProtocolArray = 0;
  }
  return 14;
}

```

## disassembly

```asm
0x180090c00  push    rbx
0x180090c02  push    rbp
0x180090c03  push    rsi
0x180090c04  push    rdi
0x180090c05  push    r14
0x180090c07  sub     rsp, 20h
0x180090c0b  cmp     cs:dword_1800FF4DC, 0
0x180090c12  mov     r14, rdx
0x180090c15  mov     rbp, rcx
0x180090c18  mov     qword ptr [rdx], 0
0x180090c1f  jnz     loc_180090CEC
0x180090c25  mov     ecx, 480h; dwBytes
0x180090c2a  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180090c2f  mov     rbx, rax
0x180090c32  test    rax, rax
0x180090c35  jz      loc_180090D32
0x180090c3b  mov     rdi, rax
0x180090c3e  mov     esi, 10h
0x180090c43  mov     rcx, rdi; this
0x180090c46  call    ??0TransportProtocol@@QEAA@XZ; TransportProtocol::TransportProtocol(void)
0x180090c4b  add     rdi, 48h ; 'H'
0x180090c4f  sub     rsi, 1
0x180090c53  jnz     short loc_180090C43
0x180090c55  lea     r8, ?gdwComputerNameLength@@3KA; nSize
0x180090c5c  mov     cs:?TransportProtocolArray@@3PEAVTransportProtocol@@EA, rbx; TransportProtocol * TransportProtocolArray
0x180090c63  lea     rdx, ?gpstrComputerName@@3PAGA; lpBuffer
0x180090c6a  mov     cs:?gdwComputerNameLength@@3KA, 10h; ulong gdwComputerNameLength
0x180090c74  xor     ecx, ecx; NameType
0x180090c76  call    cs:__imp_GetComputerNameExW
0x180090c7d  nop     dword ptr [rax+rax+00h]
0x180090c82  test    eax, eax
0x180090c84  jz      loc_180090D3D
0x180090c8a  inc     cs:?gdwComputerNameLength@@3KA; ulong gdwComputerNameLength
0x180090c90  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180090c97  mov     ebx, 80000000h
0x180090c9c  mov     edx, ebx; SpinCount
0x180090c9e  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180090ca5  nop     dword ptr [rax+rax+00h]
0x180090caa  test    eax, eax
0x180090cac  js      loc_180090D3D
0x180090cb2  mov     edx, ebx; SpinCount
0x180090cb4  lea     rcx, PNPNotificationsLock; CriticalSection
0x180090cbb  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180090cc2  nop     dword ptr [rax+rax+00h]
0x180090cc7  test    eax, eax
0x180090cc9  js      loc_180090D56
0x180090ccf  cmp     cs:?gBCacheMode@@3W4BCacheMode@@A, 1; BCacheMode gBCacheMode
0x180090cd6  jnz     short loc_180090CE2
0x180090cd8  mov     cs:?gPostSize@@3IA, 10h; uint gPostSize
0x180090ce2  mov     cs:dword_1800FF4DC, 1
0x180090cec  mov     rcx, rbp; String1
0x180090cef  call    ?MapProtseq@@YAHPEBG@Z; MapProtseq(ushort const *)
0x180090cf4  test    eax, eax
0x180090cf6  jz      short loc_180090D0E
0x180090cf8  mov     edx, eax
0x180090cfa  sub     edx, 1
0x180090cfd  jz      short loc_180090D15
0x180090cff  sub     edx, 2
0x180090d02  jz      short loc_180090D44
0x180090d04  sub     edx, 3
0x180090d07  jz      short loc_180090D15
0x180090d09  cmp     edx, 9
0x180090d0c  jz      short loc_180090D15
0x180090d0e  mov     eax, 6A7h
0x180090d13  jmp     short loc_180090D26
0x180090d15  mov     ecx, eax; int
0x180090d17  call    ?WS_TransportLoad@@YAPEBURPC_CONNECTION_TRANSPORT@@H@Z; WS_TransportLoad(int)
0x180090d1c  test    rax, rax
0x180090d1f  jz      short loc_180090D0E
0x180090d21  mov     [r14], rax
0x180090d24  xor     eax, eax
0x180090d26  add     rsp, 20h
0x180090d2a  pop     r14
0x180090d2c  pop     rdi
0x180090d2d  pop     rsi
0x180090d2e  pop     rbp
0x180090d2f  pop     rbx
0x180090d30  retn
0x180090d32  mov     cs:?TransportProtocolArray@@3PEAVTransportProtocol@@EA, 0; TransportProtocol * TransportProtocolArray
0x180090d3d  mov     eax, 0Eh
0x180090d42  jmp     short loc_180090D26
0x180090d44  call    IsGetLocalVmAliasNamePresent
0x180090d49  test    al, al
0x180090d4b  jnz     short loc_180090D6B
0x180090d4d  lea     rax, ?NMP_TransportInterface@@3URPC_CONNECTION_TRANSPORT@@A; RPC_CONNECTION_TRANSPORT NMP_TransportInterface
0x180090d54  jmp     short loc_180090D21
0x180090d56  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180090d5d  call    cs:__imp_RtlDeleteCriticalSection
0x180090d64  nop     dword ptr [rax+rax+00h]
0x180090d69  jmp     short loc_180090D3D
0x180090d6b  call    cs:__imp_RemoteWinRTActivation
0x180090d72  nop     dword ptr [rax+rax+00h]
0x180090d77  cmp     eax, 1
0x180090d7a  jnz     short loc_180090D4D
0x180090d7c  mov     cs:off_1800FE468, 0
0x180090d87  jmp     short loc_180090D4D
```
