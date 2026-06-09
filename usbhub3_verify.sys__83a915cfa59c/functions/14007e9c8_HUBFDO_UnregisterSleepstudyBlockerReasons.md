# HUBFDO_UnregisterSleepstudyBlockerReasons

- ea: `0x14007e9c8`
- end: `0x14007ea41`
- name: `HUBFDO_UnregisterSleepstudyBlockerReasons`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14007a4e0`
- `0x14007e678`

## callees

- `0x14007e9c8`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007e9dd`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007ea00`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007ea23`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007e9dd`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007ea00`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007ea23`

## pseudocode

```c
__int64 __fastcall HUBFDO_UnregisterSleepstudyBlockerReasons(_QWORD *a1)
{
  __int64 result; // rax

  if ( a1[329] )
  {
    result = SleepstudyHelper_UnregisterComponent();
    a1[329] = 0;
  }
  if ( a1[330] )
  {
    result = SleepstudyHelper_UnregisterComponent();
    a1[330] = 0;
  }
  if ( a1[331] )
  {
    result = SleepstudyHelper_UnregisterComponent();
    a1[331] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14007e9c8  push    rbx
0x14007e9ca  sub     rsp, 20h
0x14007e9ce  mov     rbx, rcx
0x14007e9d1  mov     rcx, [rcx+0A48h]
0x14007e9d8  test    rcx, rcx
0x14007e9db  jz      short loc_14007E9F4
0x14007e9dd  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14007e9e4  nop     dword ptr [rax+rax+00h]
0x14007e9e9  mov     qword ptr [rbx+0A48h], 0
0x14007e9f4  mov     rcx, [rbx+0A50h]
0x14007e9fb  test    rcx, rcx
0x14007e9fe  jz      short loc_14007EA17
0x14007ea00  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14007ea07  nop     dword ptr [rax+rax+00h]
0x14007ea0c  mov     qword ptr [rbx+0A50h], 0
0x14007ea17  mov     rcx, [rbx+0A58h]
0x14007ea1e  test    rcx, rcx
0x14007ea21  jz      short loc_14007EA3A
0x14007ea23  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14007ea2a  nop     dword ptr [rax+rax+00h]
0x14007ea2f  mov     qword ptr [rbx+0A58h], 0
0x14007ea3a  add     rsp, 20h
0x14007ea3e  pop     rbx
0x14007ea3f  retn
```
