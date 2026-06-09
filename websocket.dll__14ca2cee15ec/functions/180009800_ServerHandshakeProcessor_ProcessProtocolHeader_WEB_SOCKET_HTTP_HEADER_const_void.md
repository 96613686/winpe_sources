# ServerHandshakeProcessor::ProcessProtocolHeader(_WEB_SOCKET_HTTP_HEADER * const,void *)

- ea: `0x180009800`
- end: `0x180009860`
- name: `?ProcessProtocolHeader@ServerHandshakeProcessor@@CAJQEAU_WEB_SOCKET_HTTP_HEADER@@PEAX@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct _WEB_SOCKET_HTTP_HEADER *const, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002578`
- `0x180009800`
- `0x18000b8d8`

## pseudocode

```c
__int64 __fastcall ServerHandshakeProcessor::ProcessProtocolHeader(
        struct _WEB_SOCKET_HTTP_HEADER *const a1,
        __int64 a2)
{
  __int64 v2; // r8
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD v6[5]; // [rsp+30h] [rbp-28h] BYREF

  v2 = *((_QWORD *)a1 + 2);
  v6[2] = v2 + *((unsigned int *)a1 + 6);
  v6[0] = v2;
  v6[1] = v2;
  v3 = StringVerifier::VerifyList(
         (StringVerifier *)v6,
         0xD0000035,
         (unsigned int (__fastcall *)(StringVerifier *))StringVerifier::TryDecodeToken,
         0xFFFFFFFF,
         (__int64 (__fastcall *)(__int64, unsigned __int64, __int64))ServerHandshakeProcessor::VerifyProtocolValue,
         a2);
  v4 = v3;
  if ( v3 < 0 )
    Trace::Error(v3, 0xD0000010);
  return v4;
}

```

## disassembly

```asm
0x180009800  mov     r11, rsp
0x180009803  push    rbx
0x180009804  sub     rsp, 50h
0x180009808  mov     r8, [rcx+10h]
0x18000980c  or      r9d, 0FFFFFFFFh
0x180009810  mov     eax, [rcx+18h]
0x180009813  lea     rcx, [r11-28h]; this
0x180009817  add     rax, r8
0x18000981a  mov     [r11-30h], rdx
0x18000981e  mov     [r11-18h], rax
0x180009822  mov     edx, 0D0000035h; uID
0x180009827  lea     rax, ?VerifyProtocolValue@ServerHandshakeProcessor@@CAJPEBDKPEAX@Z; ServerHandshakeProcessor::VerifyProtocolValue(char const *,ulong,void *)
0x18000982e  mov     [r11-28h], r8
0x180009832  mov     [r11-20h], r8
0x180009836  lea     r8, ?TryDecodeToken@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeToken(void)
0x18000983d  mov     [r11-38h], rax
0x180009841  call    ?VerifyList@StringVerifier@@AEAAJKP81@EAAHXZKP6AJPEBDKPEAX@Z2@Z; StringVerifier::VerifyList(ulong,int (StringVerifier::*)(void),ulong,long (*)(char const *,ulong,void *),void *)
0x180009846  mov     ebx, eax
0x180009848  test    eax, eax
0x18000984a  jns     short loc_180009858
0x18000984c  mov     edx, 0D0000010h; unsigned int
0x180009851  mov     ecx, eax; int
0x180009853  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x180009858  mov     eax, ebx
0x18000985a  add     rsp, 50h
0x18000985e  pop     rbx
0x18000985f  retn
```
