# QueueDeviceInstallEntry

- ea: `0x180009420`
- end: `0x180009687`
- name: `QueueDeviceInstallEntry`
- size: `615`
- prototype: `_BOOL8 __fastcall(int, __int64, WCHAR *, int, __int64, __int64, int, int, DEVNODE pdnDevInst, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800121f0`

## callees

- `0x180008d20`
- `0x180009420`
- `0x180009a20`
- `0x18000e4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967a`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800094a2`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800094a2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800094c1`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800094c1`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000954b`
- `DEVRTL!DevRtlWriteTextLog` at `0x180009637`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000954b`
- `DEVRTL!DevRtlWriteTextLog` at `0x180009637`

## string_xrefs

- `0x180009531`: `Device %ws does not need to be installed.`

## pseudocode

```c
_BOOL8 __fastcall QueueDeviceInstallEntry(
        int a1,
        __int64 a2,
        WCHAR *a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        DEVNODE pdnDevInst,
        int a10)
{
  DEVNODE v10; // edi
  int v11; // r12d
  int v14; // ebp
  DWORD LastError; // ebx
  __int64 v17; // rdx
  __int16 v18; // ax
  DEVNODE v20; // [rsp+28h] [rbp-60h]
  ULONG pulStatus; // [rsp+50h] [rbp-38h] BYREF
  ULONG pulProblemNumber; // [rsp+54h] [rbp-34h] BYREF
  ULONG v23; // [rsp+58h] [rbp-30h] BYREF
  ULONG v24; // [rsp+5Ch] [rbp-2Ch] BYREF

  v10 = pdnDevInst;
  v11 = 0;
  v14 = a2;
  if ( (pdnDevInst & 1) != 0 && !a2 )
  {
    LastError = 13;
    goto LABEL_20;
  }
  LastError = 0;
  if ( (PnpGlobalFlags & 9) != 0 )
    v10 = pdnDevInst | 0x20;
  pulProblemNumber = 0;
  pdnDevInst = 0;
  if ( (v10 & 1) != 0 )
  {
    if ( (unsigned int)GetDeviceStatus(a3, &pulProblemNumber, &pdnDevInst) )
    {
      if ( a6 )
        DevRtlWriteTextLog(a6, 0x2000000, 2, "Device %ws is not present.", a3);
    }
    else
    {
      v11 = 1;
    }
    if ( !v11 )
      goto LABEL_13;
    goto LABEL_18;
  }
  pulStatus = 0;
  if ( CM_Locate_DevNodeW(&pdnDevInst, a3, 5u)
    || CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, pdnDevInst, 0)
    || (pulStatus & 0x40000) != 0 )
  {
    goto LABEL_13;
  }
  if ( (pulStatus & 0x400) != 0 )
  {
    if ( pulProblemNumber != 22 )
    {
      if ( pulProblemNumber == 18 || pulProblemNumber == 1 )
        goto LABEL_18;
      goto LABEL_9;
    }
LABEL_13:
    if ( a6 )
      DevRtlWriteTextLog(a6, 0x2000000, 4, "Device %ws does not need to be installed.", a3);
    goto LABEL_20;
  }
LABEL_9:
  pdnDevInst = 0;
  v23 = 4;
  v24 = 0;
  if ( PnpGetDeviceRegProp(a3, v17, &v24, &pdnDevInst, &v23, v20) )
    v18 = 0;
  else
    v18 = pdnDevInst;
  if ( (v18 & 0x20) == 0 && (v18 & 0x400) == 0 )
    goto LABEL_13;
LABEL_18:
  if ( !(unsigned int)QueueServerInstallEntry(a1, v14, (_DWORD)a3, a4, a5, a6, a7, a8, v10, a10) )
    LastError = GetLastError();
LABEL_20:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180009420  mov     [rsp+arg_8], rbx
0x180009425  mov     [rsp+arg_10], rbp
0x18000942a  push    rsi
0x18000942b  push    rdi
0x18000942c  push    r12
0x18000942e  push    r14
0x180009430  push    r15
0x180009432  sub     rsp, 60h
0x180009436  mov     edi, [rsp+88h+pdnDevInst]
0x18000943d  xor     r12d, r12d
0x180009440  mov     r14, r9
0x180009443  mov     rsi, r8
0x180009446  mov     rbp, rdx
0x180009449  mov     r15d, ecx
0x18000944c  test    dil, 1
0x180009450  jnz     loc_180009553
0x180009456  test    byte ptr cs:PnpGlobalFlags, 9
0x18000945d  mov     ebx, r12d
0x180009460  mov     [rsp+88h+arg_0], r13
0x180009468  jz      short loc_18000946D
0x18000946a  or      edi, 20h
0x18000946d  mov     r13, [rsp+88h+arg_28]
0x180009475  mov     [rsp+88h+pulProblemNumber], r12d
0x18000947a  mov     [rsp+88h+pdnDevInst], r12d
0x180009482  test    dil, 1
0x180009486  jnz     loc_1800095F0
0x18000948c  mov     r8d, 5; ulFlags
0x180009492  mov     [rsp+88h+pulStatus], r12d
0x180009497  mov     rdx, rsi; pDeviceID
0x18000949a  lea     rcx, [rsp+88h+pdnDevInst]; pdnDevInst
0x1800094a2  call    cs:__imp_CM_Locate_DevNodeW
0x1800094a8  test    eax, eax
0x1800094aa  jnz     short loc_180009528
0x1800094ac  mov     r8d, [rsp+88h+pdnDevInst]; dnDevInst
0x1800094b4  lea     rdx, [rsp+88h+pulProblemNumber]; pulProblemNumber
0x1800094b9  xor     r9d, r9d; ulFlags
0x1800094bc  lea     rcx, [rsp+88h+pulStatus]; pulStatus
0x1800094c1  call    cs:__imp_CM_Get_DevNode_Status
0x1800094c7  test    eax, eax
0x1800094c9  jnz     short loc_180009528
0x1800094cb  mov     eax, [rsp+88h+pulStatus]
0x1800094cf  bt      eax, 12h
0x1800094d3  jb      short loc_180009528
0x1800094d5  bt      eax, 0Ah
0x1800094d9  jb      loc_18000964A
0x1800094df  lea     rax, [rsp+88h+var_30]
0x1800094e4  mov     [rsp+88h+pdnDevInst], r12d
0x1800094ec  lea     r9, [rsp+88h+pdnDevInst]
0x1800094f4  mov     [rsp+88h+var_68], rax; PULONG
0x1800094f9  lea     r8, [rsp+88h+var_2C]
0x1800094fe  mov     [rsp+88h+var_30], 4
0x180009506  mov     rcx, rsi; pDeviceID
0x180009509  mov     [rsp+88h+var_2C], r12d
0x18000950e  call    PnpGetDeviceRegProp
0x180009513  test    eax, eax
0x180009515  jz      loc_18000966E
0x18000951b  mov     eax, r12d
0x18000951e  test    al, 20h
0x180009520  jnz     short loc_18000956F
0x180009522  bt      eax, 0Ah
0x180009526  jb      short loc_18000956F
0x180009528  test    r13, r13
0x18000952b  jz      loc_1800095BF
0x180009531  lea     r9, aDeviceWsDoesNo; "Device %ws does not need to be installe"...
0x180009538  mov     [rsp+88h+var_68], rsi
0x18000953d  mov     edx, 2000000h
0x180009542  mov     r8d, 4
0x180009548  mov     rcx, r13
0x18000954b  call    cs:__imp_DevRtlWriteTextLog
0x180009551  jmp     short loc_1800095BF
0x180009553  test    rbp, rbp
0x180009556  jnz     loc_180009456
0x18000955c  mov     ebx, 0Dh
0x180009561  jmp     short loc_1800095C7
0x180009563  test    r12d, r12d
0x180009566  jz      loc_180009642
0x18000956c  xor     r12d, r12d
0x18000956f  mov     eax, [rsp+88h+arg_48]
0x180009576  mov     r9, r14
0x180009579  mov     [rsp+88h+var_40], eax
0x18000957d  mov     r8, rsi
0x180009580  mov     eax, [rsp+88h+arg_38]
0x180009587  mov     rdx, rbp
0x18000958a  mov     [rsp+88h+var_48], edi
0x18000958e  mov     ecx, r15d
0x180009591  mov     [rsp+88h+var_50], eax
0x180009595  mov     eax, [rsp+88h+arg_30]
0x18000959c  mov     [rsp+88h+var_58], eax
0x1800095a0  mov     rax, [rsp+88h+arg_20]
0x1800095a8  mov     [rsp+88h+var_60], r13
0x1800095ad  mov     [rsp+88h+var_68], rax
0x1800095b2  call    QueueServerInstallEntry
0x1800095b7  test    eax, eax
0x1800095b9  jz      loc_18000967A
0x1800095bf  mov     r13, [rsp+88h+arg_0]
0x1800095c7  mov     ecx, ebx; dwErrCode
0x1800095c9  call    cs:__imp_SetLastError
0x1800095cf  test    ebx, ebx
0x1800095d1  lea     r11, [rsp+88h+var_28]
0x1800095d6  mov     rbx, [r11+38h]
0x1800095da  mov     eax, r12d
0x1800095dd  mov     rbp, [r11+40h]
0x1800095e1  setz    al
0x1800095e4  mov     rsp, r11
0x1800095e7  pop     r15
0x1800095e9  pop     r14
0x1800095eb  pop     r12
0x1800095ed  pop     rdi
0x1800095ee  pop     rsi
0x1800095ef  retn
0x1800095f0  lea     r8, [rsp+88h+pdnDevInst]; pulProblemNumber
0x1800095f8  mov     rcx, rsi; pDeviceID
0x1800095fb  lea     rdx, [rsp+88h+pulProblemNumber]; pulStatus
0x180009600  call    GetDeviceStatus
0x180009605  test    eax, eax
0x180009607  jnz     short loc_180009614
0x180009609  mov     r12d, 1
0x18000960f  jmp     loc_180009563
0x180009614  test    r13, r13
0x180009617  jz      loc_180009563
0x18000961d  lea     r9, aDeviceWsIsNotP; "Device %ws is not present."
0x180009624  mov     [rsp+88h+var_68], rsi
0x180009629  mov     edx, 2000000h
0x18000962e  mov     r8d, 2
0x180009634  mov     rcx, r13
0x180009637  call    cs:__imp_DevRtlWriteTextLog
0x18000963d  jmp     loc_180009563
0x180009642  xor     r12d, r12d
0x180009645  jmp     loc_180009528
0x18000964a  mov     eax, [rsp+88h+pulProblemNumber]
0x18000964e  cmp     eax, 16h
0x180009651  jz      loc_180009528
0x180009657  cmp     eax, 12h
0x18000965a  jz      loc_18000956F
0x180009660  cmp     eax, 1
0x180009663  jz      loc_18000956F
0x180009669  jmp     loc_1800094DF
0x18000966e  mov     eax, [rsp+88h+pdnDevInst]
0x180009675  jmp     loc_18000951E
0x18000967a  call    cs:__imp_GetLastError
0x180009680  mov     ebx, eax
0x180009682  jmp     loc_1800095BF
```
