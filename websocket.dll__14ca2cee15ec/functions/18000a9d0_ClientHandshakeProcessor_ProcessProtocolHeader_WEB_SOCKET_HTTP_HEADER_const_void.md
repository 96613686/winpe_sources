# ClientHandshakeProcessor::ProcessProtocolHeader(_WEB_SOCKET_HTTP_HEADER * const,void *)

- ea: `0x18000a9d0`
- end: `0x18000aa1c`
- name: `?ProcessProtocolHeader@ClientHandshakeProcessor@@CAJQEAU_WEB_SOCKET_HTTP_HEADER@@PEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(struct _WEB_SOCKET_HTTP_HEADER *const, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b8d8`

## pseudocode

```c
__int64 __fastcall ClientHandshakeProcessor::ProcessProtocolHeader(
        struct _WEB_SOCKET_HTTP_HEADER *const a1,
        __int64 a2)
{
  __int64 v2; // r8
  _QWORD v4[5]; // [rsp+30h] [rbp-28h] BYREF

  v2 = *((_QWORD *)a1 + 2);
  v4[2] = v2 + *((unsigned int *)a1 + 6);
  v4[0] = v2;
  v4[1] = v2;
  return StringVerifier::VerifyList(
           (StringVerifier *)v4,
           0xD0000035,
           (unsigned int (__fastcall *)(StringVerifier *))StringVerifier::TryDecodeToken,
           1u,
           (__int64 (__fastcall *)(__int64, unsigned __int64, __int64))ClientHandshakeProcessor::VerifyProtocolValue,
           a2);
}

```

## disassembly

```asm
0x18000a9d0  mov     r11, rsp
0x18000a9d3  sub     rsp, 58h
0x18000a9d7  mov     r8, [rcx+10h]
0x18000a9db  mov     r9d, 1
0x18000a9e1  mov     eax, [rcx+18h]
0x18000a9e4  lea     rcx, [r11-28h]; this
0x18000a9e8  add     rax, r8
0x18000a9eb  mov     [r11-30h], rdx
0x18000a9ef  mov     [r11-18h], rax
0x18000a9f3  mov     edx, 0D0000035h; uID
0x18000a9f8  lea     rax, ?VerifyProtocolValue@ClientHandshakeProcessor@@CAJPEBDKPEAX@Z; ClientHandshakeProcessor::VerifyProtocolValue(char const *,ulong,void *)
0x18000a9ff  mov     [r11-28h], r8
0x18000aa03  mov     [r11-20h], r8
0x18000aa07  lea     r8, ?TryDecodeToken@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeToken(void)
0x18000aa0e  mov     [r11-38h], rax
0x18000aa12  call    ?VerifyList@StringVerifier@@AEAAJKP81@EAAHXZKP6AJPEBDKPEAX@Z2@Z; StringVerifier::VerifyList(ulong,int (StringVerifier::*)(void),ulong,long (*)(char const *,ulong,void *),void *)
0x18000aa17  add     rsp, 58h
0x18000aa1b  retn
```
