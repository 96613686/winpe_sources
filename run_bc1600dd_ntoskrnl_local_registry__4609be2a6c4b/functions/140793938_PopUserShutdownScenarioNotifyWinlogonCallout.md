# PopUserShutdownScenarioNotifyWinlogonCallout

- ea: `0x140793938`
- end: `0x1407939ba`
- name: `PopUserShutdownScenarioNotifyWinlogonCallout`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140799df0`

## callees

- `0x140352370`
- `0x140446890`
- `0x140446930`
- `0x140793938`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14079394a`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140793997`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14079394a`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140793997`

## pseudocode

```c
void __fastcall PopUserShutdownScenarioNotifyWinlogonCallout(__int64 a1, __int64 a2)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( PopUserShutdownTaskClient )
  {
    LOBYTE(a2) = 1;
    PdcTaskClientRequest(PopUserShutdownTaskClient, a2);
    if ( PopUserShutdownPoBlockerHandle )
      SleepstudyHelperBlockerActiveReference(PopUserShutdownPoBlockerHandle);
    v2 = 0;
    if ( (unsigned __int8)((__int64 (__fastcall *)(__int64 *, __int64, _QWORD, __int128 *))KeSetTimer2)(
                            PopUserShutdownCalloutDelayTimer,
                            -900000000,
                            0,
                            &v2) )
    {
      PdcTaskClientRequest(PopUserShutdownTaskClient, 0);
      if ( PopUserShutdownPoBlockerHandle )
        SleepstudyHelperBlockerActiveDereference(PopUserShutdownPoBlockerHandle);
    }
  }
}

```

## disassembly

```asm
0x140793938  sub     rsp, 38h
0x14079393c  mov     rcx, cs:PopUserShutdownTaskClient
0x140793943  test    rcx, rcx
0x140793946  jz      short loc_1407939B4
0x140793948  mov     dl, 1
0x14079394a  call    cs:__imp_PdcTaskClientRequest
0x140793951  nop     dword ptr [rax+rax+00h]
0x140793956  mov     rcx, cs:PopUserShutdownPoBlockerHandle; SpinLock
0x14079395d  test    rcx, rcx
0x140793960  jz      short loc_140793967
0x140793962  call    SleepstudyHelperBlockerActiveReference
0x140793967  xorps   xmm0, xmm0
0x14079396a  lea     r9, [rsp+38h+var_18]
0x14079396f  xor     r8d, r8d
0x140793972  lea     rcx, PopUserShutdownCalloutDelayTimer
0x140793979  mov     rdx, 0FFFFFFFFCA5B1700h
0x140793980  movups  [rsp+38h+var_18], xmm0
0x140793985  call    KeSetTimer2
0x14079398a  test    al, al
0x14079398c  jz      short loc_1407939B4
0x14079398e  mov     rcx, cs:PopUserShutdownTaskClient
0x140793995  xor     edx, edx
0x140793997  call    cs:__imp_PdcTaskClientRequest
0x14079399e  nop     dword ptr [rax+rax+00h]
0x1407939a3  mov     rcx, cs:PopUserShutdownPoBlockerHandle; SpinLock
0x1407939aa  test    rcx, rcx
0x1407939ad  jz      short loc_1407939B4
0x1407939af  call    SleepstudyHelperBlockerActiveDereference
0x1407939b4  add     rsp, 38h
0x1407939b8  retn
```
