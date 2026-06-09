# HUBREG_UpdateSqmHubOvercurrentDetected

- ea: `0x1400347a4`
- end: `0x1400348c3`
- name: `HUBREG_UpdateSqmHubOvercurrentDetected`
- size: `287`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400036c0`
- `0x140003a80`
- `0x1400047d8`
- `0x140004a88`
- `0x1400084d0`
- `0x140011ff0`
- `0x1400120d0`

## callees

- `0x1400024b8`
- `0x1400347a4`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBREG_UpdateSqmHubOvercurrentDetected(__int64 a1)
{
  __int64 result; // rax
  unsigned __int64 v3; // rax
  int v4; // edx
  __int128 v5; // [rsp+30h] [rbp-50h] BYREF
  __int64 v6; // [rsp+40h] [rbp-40h]
  __int128 v7; // [rsp+48h] [rbp-38h] BYREF
  __int128 v8; // [rsp+58h] [rbp-28h]
  __int128 v9; // [rsp+68h] [rbp-18h]
  __int64 v10; // [rsp+78h] [rbp-8h]
  __int64 v11; // [rsp+90h] [rbp+10h] BYREF

  result = 0;
  LODWORD(v10) = 0;
  LODWORD(v6) = 0;
  v7 = 0;
  v11 = 0;
  v8 = 0;
  v9 = 0;
  v5 = 0;
  if ( (*(_DWORD *)(a1 + 40) & 0x20000000) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(a1 + 40), 0x20000000u);
    v10 = 0;
    v3 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)&v5 = 24;
    *(_QWORD *)&v8 = 0;
    *((_QWORD *)&v8 + 1) = 0x100000001LL;
    v9 = v3;
    *((_QWORD *)&v5 + 1) = HUBREG_EvtWorkItemUpdateSqmHubOvercurrentDetected;
    v7 = 0;
    v6 = 1;
    LODWORD(v7) = 56;
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64 *))(WdfFunctions_01015
                                                                                               + 3032))(
               WdfDriverGlobals,
               &v5,
               &v7,
               &v11);
    if ( (int)result >= 0 )
    {
      return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3040))(
               WdfDriverGlobals,
               v11);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      return WPP_RECORDER_SF_d(
               *(_QWORD *)(a1 + 2536),
               v4,
               3,
               58,
               (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
               result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400347a4  mov     [rsp-8+arg_8], rbx
0x1400347a9  push    rbp
0x1400347aa  mov     rbp, rsp
0x1400347ad  sub     rsp, 80h
0x1400347b4  xor     eax, eax
0x1400347b6  xorps   xmm0, xmm0
0x1400347b9  mov     rbx, rcx
0x1400347bc  mov     dword ptr [rbp+var_8], eax
0x1400347bf  mov     ecx, 20000000h
0x1400347c4  mov     dword ptr [rbp+var_40], eax
0x1400347c7  movups  [rbp+var_38], xmm0
0x1400347cb  mov     [rbp+arg_0], rax
0x1400347cf  movups  [rbp+var_28], xmm0
0x1400347d3  movups  [rbp+var_18], xmm0
0x1400347d7  movups  [rbp+var_50], xmm0
0x1400347db  test    [rbx+28h], ecx
0x1400347de  jnz     loc_1400348B1
0x1400347e4  lock or [rbx+28h], ecx
0x1400347e8  lea     ecx, [rax+1]
0x1400347eb  mov     [rbp+var_8], rax
0x1400347ef  mov     rax, [rbx+10h]
0x1400347f3  lea     r9, [rbp+arg_0]
0x1400347f7  movups  [rbp+var_50], xmm0
0x1400347fb  mov     dword ptr [rbp+var_50], 18h
0x140034802  lea     r8, [rbp+var_38]
0x140034806  movups  [rbp+var_28], xmm0
0x14003480a  mov     dword ptr [rbp+var_28+8], ecx
0x14003480d  lea     rdx, [rbp+var_50]
0x140034811  movups  [rbp+var_18], xmm0
0x140034815  mov     qword ptr [rbp+var_18], rax
0x140034819  xor     eax, eax
0x14003481b  mov     [rbp+var_40], rax
0x14003481f  lea     rax, HUBREG_EvtWorkItemUpdateSqmHubOvercurrentDetected
0x140034826  mov     qword ptr [rbp+var_50+8], rax
0x14003482a  mov     rax, cs:WdfFunctions_01015
0x140034831  movups  [rbp+var_38], xmm0
0x140034835  mov     dword ptr [rbp+var_28+0Ch], ecx
0x140034838  mov     byte ptr [rbp+var_40], cl
0x14003483b  mov     rcx, cs:WdfDriverGlobals
0x140034842  mov     dword ptr [rbp+var_38], 38h ; '8'
0x140034849  mov     rax, [rax+0BD8h]
0x140034850  call    _guard_dispatch_icall
0x140034855  test    eax, eax
0x140034857  jns     short loc_140034893
0x140034859  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140034860  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140034867  jz      short loc_1400348B1
0x140034869  mov     rcx, [rbx+9E8h]
0x140034870  mov     r9d, 3Ah ; ':'
0x140034876  mov     [rsp+80h+var_58], eax
0x14003487a  mov     dl, 2
0x14003487c  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140034883  mov     [rsp+80h+var_60], rax
0x140034888  lea     r8d, [r9-37h]
0x14003488c  call    WPP_RECORDER_SF_d
0x140034891  jmp     short loc_1400348B1
0x140034893  mov     rax, cs:WdfFunctions_01015
0x14003489a  mov     rdx, [rbp+arg_0]
0x14003489e  mov     rcx, cs:WdfDriverGlobals
0x1400348a5  mov     rax, [rax+0BE0h]
0x1400348ac  call    _guard_dispatch_icall
0x1400348b1  mov     rbx, [rsp+80h+arg_8]
0x1400348b9  add     rsp, 80h
0x1400348c0  pop     rbp
0x1400348c1  retn
```
