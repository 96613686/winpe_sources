# WanpRemoveWfpCallOuts

- ea: `0x140014ddc`
- end: `0x140014e7b`
- name: `WanpRemoveWfpCallOuts`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140014e84`
- `0x140017550`

## callees

- `0x140014ddc`

## import_xrefs

- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014df9`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014e13`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014e2d`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014e47`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014df9`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014e13`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014e2d`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140014e47`
- `fwpkclnt!FwpmEngineClose0` at `0x140014e5a`
- `fwpkclnt!FwpmEngineClose0` at `0x140014e5a`

## pseudocode

```c
NTSTATUS WanpRemoveWfpCallOuts()
{
  NTSTATUS result; // eax

  result = 0;
  if ( engineHandle )
  {
    FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_140007668);
    FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_140007688);
    FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_140007658);
    FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_140007678);
    result = FwpmEngineClose0(engineHandle);
    if ( result >= 0 )
      engineHandle = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140014ddc  sub     rsp, 28h
0x140014de0  mov     rcx, cs:engineHandle
0x140014de7  xor     eax, eax
0x140014de9  test    rcx, rcx
0x140014dec  jz      loc_140014E75
0x140014df2  lea     rdx, xmmword_140007668
0x140014df9  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140014e00  nop     dword ptr [rax+rax+00h]
0x140014e05  mov     rcx, cs:engineHandle
0x140014e0c  lea     rdx, xmmword_140007688
0x140014e13  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140014e1a  nop     dword ptr [rax+rax+00h]
0x140014e1f  mov     rcx, cs:engineHandle
0x140014e26  lea     rdx, xmmword_140007658
0x140014e2d  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140014e34  nop     dword ptr [rax+rax+00h]
0x140014e39  mov     rcx, cs:engineHandle
0x140014e40  lea     rdx, xmmword_140007678
0x140014e47  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140014e4e  nop     dword ptr [rax+rax+00h]
0x140014e53  mov     rcx, cs:engineHandle; engineHandle
0x140014e5a  call    cs:__imp_FwpmEngineClose0
0x140014e61  nop     dword ptr [rax+rax+00h]
0x140014e66  test    eax, eax
0x140014e68  js      short loc_140014E75
0x140014e6a  mov     cs:engineHandle, 0
0x140014e75  add     rsp, 28h
0x140014e79  retn
```
