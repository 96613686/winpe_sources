# UmpoTraceSmartPresenceStateRundown

- ea: `0x18000909c`
- end: `0x180009192`
- name: `UmpoTraceSmartPresenceStateRundown`
- size: `246`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008c80`

## callees

- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180009177`
- `ntdll!EtwEventWrite` at `0x180009177`

## pseudocode

```c
__int64 UmpoTraceSmartPresenceStateRundown()
{
  char v1; // [rsp+20h] [rbp-59h] BYREF
  BOOL v2; // [rsp+28h] [rbp-51h] BYREF
  BOOL v3; // [rsp+2Ch] [rbp-4Dh] BYREF
  BOOL v4; // [rsp+30h] [rbp-49h] BYREF
  int v5; // [rsp+38h] [rbp-41h] BYREF
  __int64 v6; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v7[12]; // [rsp+50h] [rbp-29h] BYREF

  v6 = UmpoSmartPresenceLastPublishedAwayTime;
  v5 = UmpoSmartPresenceSuspendCount;
  v1 = UmpoSmartPresenceMinConfidence;
  v7[1] = 4;
  v4 = UmpoSmartPresenceModeDisabled == 0;
  v7[3] = 4;
  v2 = UmpoSmartPresenceEnabled != 0;
  v7[5] = 4;
  v3 = UmpoGlobalUserPresent != 0;
  v7[7] = 1;
  v7[0] = &v2;
  v7[2] = &v3;
  v7[4] = &v4;
  v7[6] = &v1;
  v7[8] = &v5;
  v7[10] = &v6;
  v7[9] = 4;
  v7[11] = 8;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SMART_USER_PRESENCE_STATE_RUNDOWN, 6, v7);
}

```

## disassembly

```asm
0x18000909c  push    rbp
0x18000909e  lea     rbp, [rsp-47h]
0x1800090a3  sub     rsp, 0C0h
0x1800090aa  mov     rax, cs:__security_cookie
0x1800090b1  xor     rax, rsp
0x1800090b4  mov     [rbp+47h+var_10], rax
0x1800090b8  mov     rax, cs:UmpoSmartPresenceLastPublishedAwayTime
0x1800090bf  lea     r9, [rbp+47h+var_70]
0x1800090c3  mov     rcx, cs:UmpoProviderHandle
0x1800090ca  xor     edx, edx
0x1800090cc  cmp     cs:UmpoSmartPresenceModeDisabled, dl
0x1800090d2  mov     [rbp+47h+var_80], rax
0x1800090d6  mov     eax, cs:UmpoSmartPresenceSuspendCount
0x1800090dc  mov     [rbp+47h+var_88], eax
0x1800090df  lea     r8d, [rdx+6]
0x1800090e3  mov     al, cs:UmpoSmartPresenceMinConfidence
0x1800090e9  mov     [rbp+47h+var_A0], al
0x1800090ec  mov     eax, edx
0x1800090ee  setz    al
0x1800090f1  mov     [rbp+47h+var_68], 4
0x1800090f9  cmp     cs:UmpoSmartPresenceEnabled, dl
0x1800090ff  mov     [rbp+47h+var_90], eax
0x180009102  mov     eax, edx
0x180009104  setnz   al
0x180009107  mov     [rbp+47h+var_58], 4
0x18000910f  cmp     cs:UmpoGlobalUserPresent, dl
0x180009115  mov     [rbp+47h+var_98], eax
0x180009118  mov     eax, edx
0x18000911a  setnz   al
0x18000911d  mov     [rbp+47h+var_48], 4
0x180009125  mov     [rbp+47h+var_94], eax
0x180009128  lea     rdx, UMPO_EVT_SMART_USER_PRESENCE_STATE_RUNDOWN
0x18000912f  lea     rax, [rbp+47h+var_98]
0x180009133  mov     [rbp+47h+var_38], 1
0x18000913b  mov     [rbp+47h+var_70], rax
0x18000913f  lea     rax, [rbp+47h+var_94]
0x180009143  mov     [rbp+47h+var_60], rax
0x180009147  lea     rax, [rbp+47h+var_90]
0x18000914b  mov     [rbp+47h+var_50], rax
0x18000914f  lea     rax, [rbp+47h+var_A0]
0x180009153  mov     [rbp+47h+var_40], rax
0x180009157  lea     rax, [rbp+47h+var_88]
0x18000915b  mov     [rbp+47h+var_30], rax
0x18000915f  lea     rax, [rbp+47h+var_80]
0x180009163  mov     [rbp+47h+var_20], rax
0x180009167  mov     [rbp+47h+var_28], 4
0x18000916f  mov     [rbp+47h+var_18], 8
0x180009177  call    cs:__imp_EtwEventWrite
0x18000917d  mov     rcx, [rbp+47h+var_10]
0x180009181  xor     rcx, rsp; StackCookie
0x180009184  call    __security_check_cookie
0x180009189  add     rsp, 0C0h
0x180009190  pop     rbp
0x180009191  retn
```
