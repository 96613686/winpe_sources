# TetheringService::UninitializeCellularWnfSubscriptions(void)

- ea: `0x180020bd8`
- end: `0x180020cae`
- name: `?UninitializeCellularWnfSubscriptions@TetheringService@@AEAAXXZ`
- size: `214`
- prototype: `void __fastcall(TetheringService *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015e30`
- `0x180019ec0`

## callees

- `0x18000bf4c`
- `0x180020bd8`
- `0x180029c10`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020c28`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020c45`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020c62`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020c28`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020c45`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020c62`

## pseudocode

```c
void __fastcall TetheringService::UninitializeCellularWnfSubscriptions(TetheringService *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( IsMobile() )
  {
    v2 = *((_QWORD *)this + 210);
    if ( v2 )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion(v2);
      *((_QWORD *)this + 210) = 0;
    }
    v3 = *((_QWORD *)this + 211);
    if ( v3 )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion(v3);
      *((_QWORD *)this + 211) = 0;
    }
    v4 = *((_QWORD *)this + 209);
    if ( v4 )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion(v4);
      *((_QWORD *)this + 209) = 0;
    }
    *((_WORD *)this + 832) = 0;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 330, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
}

```

## disassembly

```asm
0x180020bd8  mov     [rsp+arg_0], rbx
0x180020bdd  push    rsi
0x180020bde  sub     rsp, 20h
0x180020be2  mov     rbx, rcx
0x180020be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bec  lea     rsi, WPP_GLOBAL_Control
0x180020bf3  cmp     rcx, rsi
0x180020bf6  jz      short loc_180020C13
0x180020bf8  test    byte ptr [rcx+1Ch], 8
0x180020bfc  jz      short loc_180020C13
0x180020bfe  mov     rcx, [rcx+10h]
0x180020c02  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020c09  mov     edx, 149h
0x180020c0e  call    WPP_SF_
0x180020c13  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x180020c18  test    al, al
0x180020c1a  jz      short loc_180020C7C
0x180020c1c  mov     rcx, [rbx+690h]
0x180020c23  test    rcx, rcx
0x180020c26  jz      short loc_180020C39
0x180020c28  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180020c2e  mov     qword ptr [rbx+690h], 0
0x180020c39  mov     rcx, [rbx+698h]
0x180020c40  test    rcx, rcx
0x180020c43  jz      short loc_180020C56
0x180020c45  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180020c4b  mov     qword ptr [rbx+698h], 0
0x180020c56  mov     rcx, [rbx+688h]
0x180020c5d  test    rcx, rcx
0x180020c60  jz      short loc_180020C73
0x180020c62  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180020c68  mov     qword ptr [rbx+688h], 0
0x180020c73  mov     word ptr [rbx+680h], 0
0x180020c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c83  cmp     rcx, rsi
0x180020c86  jz      short loc_180020CA3
0x180020c88  test    byte ptr [rcx+1Ch], 8
0x180020c8c  jz      short loc_180020CA3
0x180020c8e  mov     rcx, [rcx+10h]
0x180020c92  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020c99  mov     edx, 14Ah
0x180020c9e  call    WPP_SF_
0x180020ca3  mov     rbx, [rsp+28h+arg_0]
0x180020ca8  add     rsp, 20h
0x180020cac  pop     rsi
0x180020cad  retn
```
