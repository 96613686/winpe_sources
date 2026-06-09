# HUBUCX_UpdateDeviceExitLatencyUsingUCXIoctl

- ea: `0x140028fc0`
- end: `0x1400290fd`
- name: `HUBUCX_UpdateDeviceExitLatencyUsingUCXIoctl`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140024810`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x14000a53c`
- `0x1400284dc`
- `0x140028fc0`
- `0x140045570`
- `0x140045940`

## pseudocode

```c
_UNKNOWN **__fastcall HUBUCX_UpdateDeviceExitLatencyUsingUCXIoctl(__int64 a1)
{
  unsigned int v1; // edx
  unsigned __int16 *v2; // rsi
  unsigned int v4; // r8d
  _UNKNOWN **result; // rax
  _DWORD *v6; // rbx
  int v7; // edx
  int v8; // [rsp+28h] [rbp-20h]

  v1 = *(_DWORD *)(a1 + 2592);
  v2 = (unsigned __int16 *)(a1 + 2218);
  if ( v1 && (v4 = *v2, v4 > v1) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v1) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v1,
        5,
        35,
        (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
        v4,
        *(_DWORD *)(a1 + 2592));
    }
    return (_UNKNOWN **)HUBSM_AddEvent(a1 + 512, 4024);
  }
  else
  {
    v6 = (_DWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 1552))(
                     WdfDriverGlobals,
                     *(_QWORD *)(a1 + 440),
                     0);
    memset(v6, 0, 0x48u);
    v6[6] |= 4u;
    *v6 = 72;
    *((_QWORD *)v6 + 1) = *(_QWORD *)(*(_QWORD *)a1 + 248LL);
    *((_QWORD *)v6 + 2) = *(_QWORD *)(a1 + 24);
    v6[12] = *v2;
    result = (_UNKNOWN **)HUBUCX_SubmitUcxIoctl(a1, 4788259);
    v7 = (int)result;
    if ( (int)result < 0 )
    {
      result = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v8 = v7;
        LOBYTE(v7) = 2;
        return (_UNKNOWN **)WPP_RECORDER_SF_d(
                              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
                              v7,
                              5,
                              36,
                              (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
                              v8);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140028fc0  mov     r11, rsp
0x140028fc3  mov     [r11+8], rbx
0x140028fc7  mov     [r11+10h], rsi
0x140028fcb  push    rdi
0x140028fcc  sub     rsp, 40h
0x140028fd0  mov     edx, [rcx+0A20h]
0x140028fd6  lea     rsi, [rcx+8AAh]
0x140028fdd  mov     rdi, rcx
0x140028fe0  test    edx, edx
0x140028fe2  jz      short loc_140029042
0x140028fe4  movzx   r8d, word ptr [rsi]
0x140028fe8  cmp     r8d, edx
0x140028feb  jbe     short loc_140029042
0x140028fed  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140028ff4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028ffb  jz      short loc_14002902C
0x140028ffd  mov     rcx, [rcx+8]
0x140029001  lea     rax, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x140029008  mov     [rsp+48h+var_18], edx
0x14002900c  mov     r9d, 23h ; '#'
0x140029012  mov     [r11-20h], r8d
0x140029016  mov     dl, 2
0x140029018  mov     [r11-28h], rax
0x14002901c  mov     rcx, [rcx+598h]
0x140029023  lea     r8d, [r9-1Eh]
0x140029027  call    WPP_RECORDER_SF_dD
0x14002902c  lea     rcx, [rdi+200h]
0x140029033  mov     edx, 0FB8h
0x140029038  call    HUBSM_AddEvent
0x14002903d  jmp     loc_1400290EC
0x140029042  mov     rax, cs:WdfFunctions_01015
0x140029049  xor     r8d, r8d
0x14002904c  mov     rdx, [rcx+1B8h]
0x140029053  mov     rcx, cs:WdfDriverGlobals
0x14002905a  mov     rax, [rax+610h]
0x140029061  call    _guard_dispatch_icall
0x140029066  xor     edx, edx; Val
0x140029068  mov     rcx, rax; void *
0x14002906b  mov     rbx, rax
0x14002906e  lea     r8d, [rdx+48h]; Size
0x140029072  call    memset
0x140029077  or      dword ptr [rbx+18h], 4
0x14002907b  mov     dword ptr [rbx], 48h ; 'H'
0x140029081  mov     rcx, [rdi]
0x140029084  mov     rdx, [rcx+0F8h]
0x14002908b  mov     [rbx+8], rdx
0x14002908f  mov     edx, 491023h
0x140029094  mov     rcx, [rdi+18h]
0x140029098  mov     [rbx+10h], rcx
0x14002909c  movzx   ecx, word ptr [rsi]
0x14002909f  mov     [rbx+30h], ecx
0x1400290a2  mov     rcx, rdi
0x1400290a5  call    HUBUCX_SubmitUcxIoctl
0x1400290aa  mov     edx, eax
0x1400290ac  test    eax, eax
0x1400290ae  jns     short loc_1400290EC
0x1400290b0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400290b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400290be  jz      short loc_1400290EC
0x1400290c0  mov     rcx, [rdi+8]
0x1400290c4  lea     rax, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x1400290cb  mov     [rsp+48h+var_20], edx
0x1400290cf  mov     r9d, 24h ; '$'
0x1400290d5  mov     dl, 2
0x1400290d7  mov     [rsp+48h+var_28], rax
0x1400290dc  mov     rcx, [rcx+598h]
0x1400290e3  lea     r8d, [r9-1Fh]
0x1400290e7  call    WPP_RECORDER_SF_d
0x1400290ec  mov     rbx, [rsp+48h+arg_0]
0x1400290f1  mov     rsi, [rsp+48h+arg_8]
0x1400290f6  add     rsp, 40h
0x1400290fa  pop     rdi
0x1400290fb  retn
```
