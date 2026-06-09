# PlugPlayServiceControlHandlerEx

- ea: `0x18000e750`
- end: `0x18000e7ae`
- name: `PlugPlayServiceControlHandlerEx`
- size: `94`
- prototype: `__int64 __fastcall(__int64 dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18000e750`
- `0x1800136f8`
- `0x1800160dc`

## pseudocode

```c
__int64 __fastcall PlugPlayServiceControlHandlerEx(
        __int64 dwControl,
        __int64 dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  if ( (_DWORD)dwControl == 1 || (_DWORD)dwControl == 5 )
  {
    PlugPlayServiceStop(dwControl, dwEventType, lpEventData, (unsigned int)dwControl);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_240d98e9dfc731e5b4648e232cb969e2_Traceguids,
        (unsigned int)dwControl,
        1052);
    return 1052;
  }
}

```

## disassembly

```asm
0x18000e750  sub     rsp, 38h
0x18000e754  mov     eax, ecx
0x18000e756  mov     r9d, ecx
0x18000e759  sub     eax, 1
0x18000e75c  jz      short loc_18000E7A5
0x18000e75e  cmp     eax, 4
0x18000e761  jz      short loc_18000E7A5
0x18000e763  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e76a  lea     rdx, WPP_GLOBAL_Control
0x18000e771  cmp     rcx, rdx
0x18000e774  jz      short loc_18000E77C
0x18000e776  test    byte ptr [rcx+1Ch], 1
0x18000e77a  jnz     short loc_18000E786
0x18000e77c  mov     eax, 41Ch
0x18000e781  add     rsp, 38h
0x18000e785  retn
0x18000e786  mov     rcx, [rcx+10h]
0x18000e78a  lea     r8, WPP_240d98e9dfc731e5b4648e232cb969e2_Traceguids
0x18000e791  mov     edx, 0Ah
0x18000e796  mov     [rsp+38h+var_18], 41Ch
0x18000e79e  call    WPP_SF_dd
0x18000e7a3  jmp     short loc_18000E77C
0x18000e7a5  call    PlugPlayServiceStop
0x18000e7aa  xor     eax, eax
0x18000e7ac  jmp     short loc_18000E781
```
