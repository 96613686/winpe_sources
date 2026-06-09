# CNsiInterfaceMonitor::StopMonitor(void)

- ea: `0x180026930`
- end: `0x180026a2b`
- name: `?StopMonitor@CNsiInterfaceMonitor@@QEAAXXZ`
- size: `251`
- prototype: `void __fastcall(CNsiInterfaceMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180014ab0`
- `0x18001f740`
- `0x1800266b8`

## callees

- `0x18000bf4c`
- `0x180026930`

## import_xrefs

- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x1800269ab`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x1800269ab`
- `WINNSI!NsiDisconnectFromServer` at `0x1800269eb`
- `WINNSI!NsiDisconnectFromServer` at `0x1800269eb`

## pseudocode

```c
void __fastcall CNsiInterfaceMonitor::StopMonitor(CNsiInterfaceMonitor *this)
{
  TetheringServiceTelemetry *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v2 + 2), 19, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_NDIS_MODULEID, 0, *((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 2) )
  {
    if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v2 + 2), 20, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
    NsiDisconnectFromServer(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v2 + 2), 21, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
}

```

## disassembly

```asm
0x180026930  mov     [rsp+arg_0], rbx
0x180026935  push    rsi
0x180026936  sub     rsp, 20h
0x18002693a  mov     rbx, rcx
0x18002693d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026944  lea     rsi, WPP_GLOBAL_Control
0x18002694b  cmp     rcx, rsi
0x18002694e  jz      short loc_180026972
0x180026950  test    byte ptr [rcx+1Ch], 8
0x180026954  jz      short loc_180026972
0x180026956  mov     rcx, [rcx+10h]
0x18002695a  lea     r8, WPP_25f318119957394f188ed969a8444d7a_Traceguids
0x180026961  mov     edx, 12h
0x180026966  call    WPP_SF_
0x18002696b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026972  cmp     qword ptr [rbx+18h], 0
0x180026977  jz      short loc_1800269C0
0x180026979  cmp     rcx, rsi
0x18002697c  jz      short loc_180026999
0x18002697e  test    byte ptr [rcx+1Ch], 8
0x180026982  jz      short loc_180026999
0x180026984  mov     rcx, [rcx+10h]
0x180026988  lea     r8, WPP_25f318119957394f188ed969a8444d7a_Traceguids
0x18002698f  mov     edx, 13h
0x180026994  call    WPP_SF_
0x180026999  mov     r9, [rbx+18h]
0x18002699d  lea     rdx, NPI_MS_NDIS_MODULEID
0x1800269a4  mov     rcx, [rbx+10h]
0x1800269a8  xor     r8d, r8d
0x1800269ab  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x1800269b1  mov     qword ptr [rbx+18h], 0
0x1800269b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269c0  cmp     qword ptr [rbx+10h], 0
0x1800269c5  jz      short loc_180026A00
0x1800269c7  cmp     rcx, rsi
0x1800269ca  jz      short loc_1800269E7
0x1800269cc  test    byte ptr [rcx+1Ch], 8
0x1800269d0  jz      short loc_1800269E7
0x1800269d2  mov     rcx, [rcx+10h]
0x1800269d6  lea     r8, WPP_25f318119957394f188ed969a8444d7a_Traceguids
0x1800269dd  mov     edx, 14h
0x1800269e2  call    WPP_SF_
0x1800269e7  mov     rcx, [rbx+10h]
0x1800269eb  call    cs:__imp_NsiDisconnectFromServer
0x1800269f1  mov     qword ptr [rbx+10h], 0
0x1800269f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a00  cmp     rcx, rsi
0x180026a03  jz      short loc_180026A20
0x180026a05  test    byte ptr [rcx+1Ch], 8
0x180026a09  jz      short loc_180026A20
0x180026a0b  mov     rcx, [rcx+10h]
0x180026a0f  lea     r8, WPP_25f318119957394f188ed969a8444d7a_Traceguids
0x180026a16  mov     edx, 15h
0x180026a1b  call    WPP_SF_
0x180026a20  mov     rbx, [rsp+28h+arg_0]
0x180026a25  add     rsp, 20h
0x180026a29  pop     rsi
0x180026a2a  retn
```
