# TpmTransport::InitializeTimeoutValues(void)

- ea: `0x140022d00`
- end: `0x140022e7c`
- name: `?InitializeTimeoutValues@TpmTransport@@IEAAXXZ`
- size: `380`
- prototype: `void __fastcall(TpmTransport *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022ba0`

## callees

- `0x140009278`
- `0x140009fc8`
- `0x140022d00`

## string_xrefs

- `0x140022d30`: `TimeoutCommand`
- `0x140022d77`: `TimeoutCommandCreate`
- `0x140022dac`: `TimeoutCommandCancel`

## pseudocode

```c
void __fastcall TpmTransport::InitializeTimeoutValues(TpmTransport *this)
{
  unsigned int v2; // [rsp+40h] [rbp+8h] BYREF

  *((_DWORD *)this + 62) = 180000;
  *((_DWORD *)this + 63) = 180000;
  *((_DWORD *)this + 64) = 180000;
  v2 = 0;
  if ( !(unsigned int)TpmRegistry::QueryValue(0, L"TimeoutCommand", 4, &v2, 4, 0) && v2 > *((_DWORD *)this + 62) )
    *((_DWORD *)this + 62) = v2;
  if ( !(unsigned int)TpmRegistry::QueryValue(0, L"TimeoutCommandCreate", 4, &v2, 4, 0) && v2 > *((_DWORD *)this + 63) )
    *((_DWORD *)this + 63) = v2;
  if ( !(unsigned int)TpmRegistry::QueryValue(0, L"TimeoutCommandCancel", 4, &v2, 4, 0) && v2 > *((_DWORD *)this + 64) )
    *((_DWORD *)this + 64) = v2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids,
        *((unsigned int *)this + 62));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids,
          *((unsigned int *)this + 63));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids,
          *((unsigned int *)this + 64));
    }
  }
}

```

## disassembly

```asm
0x140022d00  mov     r11, rsp
0x140022d03  mov     [r11+10h], rbx
0x140022d07  mov     [r11+18h], rsi
0x140022d0b  push    rdi
0x140022d0c  sub     rsp, 30h
0x140022d10  mov     eax, 2BF20h
0x140022d15  lea     r9, [r11+8]
0x140022d19  xor     esi, esi
0x140022d1b  mov     [rcx+0F8h], eax
0x140022d21  mov     rbx, rcx
0x140022d24  mov     [rcx+0FCh], eax
0x140022d2a  mov     [rcx+100h], eax
0x140022d30  lea     rdx, aTimeoutcommand_1; "TimeoutCommand"
0x140022d37  mov     [r11-10h], rsi
0x140022d3b  xor     ecx, ecx
0x140022d3d  lea     edi, [rsi+4]
0x140022d40  mov     [rsp+38h+arg_0], esi
0x140022d44  mov     r8d, edi
0x140022d47  mov     [rsp+38h+var_18], edi
0x140022d4b  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140022d50  test    eax, eax
0x140022d52  jnz     short loc_140022D66
0x140022d54  mov     eax, [rsp+38h+arg_0]
0x140022d58  cmp     eax, [rbx+0F8h]
0x140022d5e  jbe     short loc_140022D66
0x140022d60  mov     [rbx+0F8h], eax
0x140022d66  mov     [rsp+38h+var_10], rsi
0x140022d6b  lea     r9, [rsp+38h+arg_0]
0x140022d70  mov     r8d, edi
0x140022d73  mov     [rsp+38h+var_18], edi
0x140022d77  lea     rdx, aTimeoutcommand; "TimeoutCommandCreate"
0x140022d7e  xor     ecx, ecx
0x140022d80  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140022d85  test    eax, eax
0x140022d87  jnz     short loc_140022D9B
0x140022d89  mov     eax, [rsp+38h+arg_0]
0x140022d8d  cmp     eax, [rbx+0FCh]
0x140022d93  jbe     short loc_140022D9B
0x140022d95  mov     [rbx+0FCh], eax
0x140022d9b  mov     [rsp+38h+var_10], rsi
0x140022da0  lea     r9, [rsp+38h+arg_0]
0x140022da5  mov     r8d, edi
0x140022da8  mov     [rsp+38h+var_18], edi
0x140022dac  lea     rdx, aTimeoutcommand_0; "TimeoutCommandCancel"
0x140022db3  xor     ecx, ecx
0x140022db5  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140022dba  test    eax, eax
0x140022dbc  jnz     short loc_140022DD0
0x140022dbe  mov     eax, [rsp+38h+arg_0]
0x140022dc2  cmp     eax, [rbx+100h]
0x140022dc8  jbe     short loc_140022DD0
0x140022dca  mov     [rbx+100h], eax
0x140022dd0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022dd7  lea     rsi, WPP_GLOBAL_Control
0x140022dde  cmp     rcx, rsi
0x140022de1  jz      loc_140022E6B
0x140022de7  mov     eax, [rcx+2Ch]
0x140022dea  test    dil, al
0x140022ded  jz      short loc_140022E0B
0x140022def  mov     r9d, [rbx+0F8h]
0x140022df6  lea     r8, WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids
0x140022dfd  mov     rcx, [rcx+18h]
0x140022e01  mov     edx, 0Eh
0x140022e06  call    WPP_SF_d
0x140022e0b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022e12  cmp     rcx, rsi
0x140022e15  jz      short loc_140022E6B
0x140022e17  mov     eax, [rcx+2Ch]
0x140022e1a  test    dil, al
0x140022e1d  jz      short loc_140022E3B
0x140022e1f  mov     r9d, [rbx+0FCh]
0x140022e26  lea     r8, WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids
0x140022e2d  mov     rcx, [rcx+18h]
0x140022e31  mov     edx, 0Fh
0x140022e36  call    WPP_SF_d
0x140022e3b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022e42  cmp     rcx, rsi
0x140022e45  jz      short loc_140022E6B
0x140022e47  mov     eax, [rcx+2Ch]
0x140022e4a  test    dil, al
0x140022e4d  jz      short loc_140022E6B
0x140022e4f  mov     r9d, [rbx+100h]
0x140022e56  lea     r8, WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids
0x140022e5d  mov     rcx, [rcx+18h]
0x140022e61  mov     edx, 10h
0x140022e66  call    WPP_SF_d
0x140022e6b  mov     rbx, [rsp+38h+arg_8]
0x140022e70  mov     rsi, [rsp+38h+arg_10]
0x140022e75  add     rsp, 30h
0x140022e79  pop     rdi
0x140022e7a  retn
```
