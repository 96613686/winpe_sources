# Srv2ProcessPacket

- ea: `0x140074b20`
- end: `0x140074c8d`
- name: `Srv2ProcessPacket`
- size: `365`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14005d3d0`
- `0x1400749c0`

## callees

- `0x140005070`
- `0x140008200`
- `0x140019ab8`
- `0x1400222ec`
- `0x140038490`
- `0x140074b20`
- `0x14008d6c8`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x140074c4d`
- `ntoskrnl!IoClearActivityIdThread` at `0x140074c4d`
- `ntoskrnl!IoSetActivityIdThread` at `0x140074c33`
- `ntoskrnl!IoSetActivityIdThread` at `0x140074c33`

## pseudocode

```c
__int64 __fastcall Srv2ProcessPacket(__int64 a1)
{
  __int64 v1; // rsi
  char v2; // di
  __int64 i; // rax
  __int64 result; // rax
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF

  v1 = 0;
  v2 = 0;
  v6 = 0;
  if ( (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    SRV2_PERF_ISSUE_RECEIVE_CORRELATION(a1);
    if ( (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
    {
      v6 = *(_OWORD *)(a1 + 584);
      v1 = IoSetActivityIdThread(&v6);
      v2 = 1;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_42ed7384cb6a3283aec034377101fac6_Traceguids, a1);
  }
  if ( !*(_QWORD *)(a1 + 512) )
  {
    for ( i = Srv2ProviderList; Srv2ProviderList; i = *(_QWORD *)(i + 32) )
    {
      if ( (*(_DWORD *)(a1 + 392) & *(_DWORD *)(i + 44)) != 0 )
        break;
    }
    *(_QWORD *)(a1 + 512) = i;
  }
  if ( !*(_BYTE *)(*(_QWORD *)(a1 + 96) + 508LL) )
    Srv2InitializeConnectionPassive();
  SRV2_PERF_ENTER_EX(a1 + 584, 0, 121, "Srv2ProcessPacket", 1);
  result = Srv2CallProviders(a1, 0, 0);
  if ( v2 )
    return IoClearActivityIdThread(v1);
  return result;
}

```

## disassembly

```asm
0x140074b20  mov     [rsp+arg_8], rbx
0x140074b25  mov     [rsp+arg_10], rsi
0x140074b2a  push    rdi
0x140074b2b  sub     rsp, 50h
0x140074b2f  mov     rax, cs:__security_cookie
0x140074b36  xor     rax, rsp
0x140074b39  mov     [rsp+58h+var_18], rax
0x140074b3e  xor     esi, esi
0x140074b40  xor     dil, dil
0x140074b43  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140074b4a  xorps   xmm0, xmm0
0x140074b4d  mov     rbx, rcx
0x140074b50  movups  [rsp+58h+var_28], xmm0
0x140074b55  jnz     loc_140074C10
0x140074b5b  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074b62  lea     rax, WPP_GLOBAL_Control
0x140074b69  cmp     r10, rax
0x140074b6c  jz      short loc_140074B7B
0x140074b6e  mov     ecx, [r10+2Ch]
0x140074b72  test    cl, 40h
0x140074b75  jnz     loc_140074C5B
0x140074b7b  cmp     qword ptr [rbx+200h], 0
0x140074b83  jnz     short loc_140074BAF
0x140074b85  mov     r8, cs:Srv2ProviderList
0x140074b8c  mov     rax, r8
0x140074b8f  test    r8, r8
0x140074b92  jz      short loc_140074BA8
0x140074b94  mov     edx, [rbx+188h]
0x140074b9a  test    [rax+2Ch], edx
0x140074b9d  jnz     short loc_140074BA8
0x140074b9f  mov     rax, [rax+20h]
0x140074ba3  test    r8, r8
0x140074ba6  jnz     short loc_140074B9A
0x140074ba8  mov     [rbx+200h], rax
0x140074baf  mov     rcx, [rbx+60h]
0x140074bb3  cmp     byte ptr [rcx+1FCh], 0
0x140074bba  jz      loc_140074C83
0x140074bc0  lea     rcx, [rbx+248h]
0x140074bc7  mov     [rsp+58h+var_38], 1
0x140074bcc  lea     r9, aSrv2processpac; "Srv2ProcessPacket"
0x140074bd3  xor     edx, edx
0x140074bd5  mov     r8d, 79h ; 'y'
0x140074bdb  call    SRV2_PERF_ENTER_EX
0x140074be0  xor     r8d, r8d
0x140074be3  xor     edx, edx
0x140074be5  mov     rcx, rbx
0x140074be8  call    Srv2CallProviders
0x140074bed  test    dil, dil
0x140074bf0  jnz     short loc_140074C4A
0x140074bf2  mov     rcx, [rsp+58h+var_18]
0x140074bf7  xor     rcx, rsp; StackCookie
0x140074bfa  call    __security_check_cookie
0x140074bff  mov     rbx, [rsp+58h+arg_8]
0x140074c04  mov     rsi, [rsp+58h+arg_10]
0x140074c09  add     rsp, 50h
0x140074c0d  pop     rdi
0x140074c0e  retn
0x140074c10  call    SRV2_PERF_ISSUE_RECEIVE_CORRELATION
0x140074c15  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140074c1c  jz      loc_140074B5B
0x140074c22  movups  xmm0, xmmword ptr [rbx+248h]
0x140074c29  lea     rcx, [rsp+58h+var_28]
0x140074c2e  movups  [rsp+58h+var_28], xmm0
0x140074c33  call    cs:__imp_IoSetActivityIdThread
0x140074c3a  nop     dword ptr [rax+rax+00h]
0x140074c3f  mov     rsi, rax
0x140074c42  mov     dil, 1
0x140074c45  jmp     loc_140074B5B
0x140074c4a  mov     rcx, rsi
0x140074c4d  call    cs:__imp_IoClearActivityIdThread
0x140074c54  nop     dword ptr [rax+rax+00h]
0x140074c59  jmp     short loc_140074BF2
0x140074c5b  cmp     byte ptr [r10+29h], 2
0x140074c60  jb      loc_140074B7B
0x140074c66  mov     rcx, [r10+18h]
0x140074c6a  lea     r8, WPP_42ed7384cb6a3283aec034377101fac6_Traceguids
0x140074c71  mov     edx, 0Ah
0x140074c76  mov     r9, rbx
0x140074c79  call    WPP_SF_q
0x140074c7e  jmp     loc_140074B7B
0x140074c83  call    Srv2InitializeConnectionPassive
0x140074c88  jmp     loc_140074BC0
```
