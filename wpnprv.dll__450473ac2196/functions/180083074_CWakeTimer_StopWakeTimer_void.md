# CWakeTimer::StopWakeTimer(void * *)

- ea: `0x180083074`
- end: `0x180083160`
- name: `?StopWakeTimer@CWakeTimer@@SAXPEAPEAX@Z`
- size: `236`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180022dcc`
- `0x18006cc58`
- `0x180082894`
- `0x18008ad90`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x180083074`

## import_xrefs

- `EventAggregation!EaDeleteAggregatedEvent` at `0x1800830cc`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x1800830cc`
- `ntdll!RtlNtStatusToDosError` at `0x1800830f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800830f0`

## pseudocode

```c
void __fastcall CWakeTimer::StopWakeTimer(void **a1)
{
  PVOID *v2; // rcx
  NTSTATUS v3; // eax
  signed int v4; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && *a1 )
  {
    v3 = EaDeleteAggregatedEvent(*a1, 0);
    if ( v3 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RtlNtStatusToDosError(v3);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids,
        (unsigned int)v4);
    }
    *a1 = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 26, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids);
}

```

## disassembly

```asm
0x180083074  mov     [rsp+arg_0], rbx
0x180083079  push    rsi
0x18008307a  sub     rsp, 20h
0x18008307e  mov     rbx, rcx
0x180083081  mov     rcx, cs:WPP_GLOBAL_Control
0x180083088  lea     rsi, WPP_GLOBAL_Control
0x18008308f  cmp     rcx, rsi
0x180083092  jz      short loc_1800830BC
0x180083094  test    byte ptr [rcx+1Ch], 8
0x180083098  jz      short loc_1800830BC
0x18008309a  cmp     byte ptr [rcx+19h], 6
0x18008309e  jb      short loc_1800830BC
0x1800830a0  mov     rcx, [rcx+10h]
0x1800830a4  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x1800830ab  mov     edx, 18h
0x1800830b0  call    WPP_SF_
0x1800830b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800830bc  test    rbx, rbx
0x1800830bf  jz      short loc_18008312F
0x1800830c1  cmp     qword ptr [rbx], 0
0x1800830c5  jz      short loc_18008312F
0x1800830c7  mov     rcx, [rbx]
0x1800830ca  xor     edx, edx
0x1800830cc  call    cs:__imp_EaDeleteAggregatedEvent
0x1800830d2  test    eax, eax
0x1800830d4  jns     short loc_180083121
0x1800830d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800830dd  cmp     rcx, rsi
0x1800830e0  jz      short loc_180083121
0x1800830e2  test    byte ptr [rcx+1Ch], 8
0x1800830e6  jz      short loc_180083121
0x1800830e8  cmp     byte ptr [rcx+19h], 2
0x1800830ec  jb      short loc_180083121
0x1800830ee  mov     ecx, eax; Status
0x1800830f0  call    cs:__imp_RtlNtStatusToDosError
0x1800830f6  test    eax, eax
0x1800830f8  jle     short loc_180083102
0x1800830fa  movzx   eax, ax
0x1800830fd  or      eax, 80070000h
0x180083102  mov     rcx, cs:WPP_GLOBAL_Control
0x180083109  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180083110  mov     edx, 19h
0x180083115  mov     r9d, eax
0x180083118  mov     rcx, [rcx+10h]
0x18008311c  call    WPP_SF_d
0x180083121  mov     qword ptr [rbx], 0
0x180083128  mov     rcx, cs:WPP_GLOBAL_Control
0x18008312f  cmp     rcx, rsi
0x180083132  jz      short loc_180083155
0x180083134  test    byte ptr [rcx+1Ch], 8
0x180083138  jz      short loc_180083155
0x18008313a  cmp     byte ptr [rcx+19h], 6
0x18008313e  jb      short loc_180083155
0x180083140  mov     rcx, [rcx+10h]
0x180083144  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x18008314b  mov     edx, 1Ah
0x180083150  call    WPP_SF_
0x180083155  mov     rbx, [rsp+28h+arg_0]
0x18008315a  add     rsp, 20h
0x18008315e  pop     rsi
0x18008315f  retn
```
