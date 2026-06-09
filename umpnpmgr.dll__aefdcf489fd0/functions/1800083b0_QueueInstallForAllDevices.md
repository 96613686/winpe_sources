# QueueInstallForAllDevices

- ea: `0x1800083b0`
- end: `0x18000864f`
- name: `QueueInstallForAllDevices`
- size: `671`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000a6b0`

## callees

- `0x180008220`
- `0x1800083b0`
- `0x180008bf0`
- `0x180008d20`
- `0x180009a20`
- `0x18000ff5c`
- `0x180011964`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180008644`
- `ntdll!RtlFreeHeap` at `0x180008644`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008567`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008629`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800084ac`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800084ac`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800084c9`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800084c9`

## pseudocode

```c
__int64 __fastcall QueueInstallForAllDevices(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  unsigned int DeviceIdList; // r15d
  DEVINSTID_W i; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  DEVNODE v7; // edi
  int v8; // esi
  DWORD LastError; // r14d
  __int64 v10; // rdx
  __int16 v11; // ax
  __int64 v12; // rax
  DEVNODE PropertyBuffer; // [rsp+28h] [rbp-11h]
  ULONG v16; // [rsp+50h] [rbp+17h] BYREF
  DEVINSTID_W pDeviceID; // [rsp+58h] [rbp+1Fh] BYREF
  DEVNODE pdnDevInst; // [rsp+A0h] [rbp+67h] BYREF
  ULONG pulStatus; // [rsp+A8h] [rbp+6Fh] BYREF
  ULONG pulProblemNumber; // [rsp+B0h] [rbp+77h] BYREF
  ULONG v21; // [rsp+B8h] [rbp+7Fh] BYREF

  pDeviceID = 0;
  DeviceIdList = GetDeviceIdList(a1, &pDeviceID);
  if ( DeviceIdList )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, DeviceIdList);
  }
  else
  {
    for ( i = pDeviceID; i; i += v12 + 1 )
    {
      if ( !*i )
        break;
      pulProblemNumber = 0;
      pdnDevInst = -1;
      pulStatus = 4;
      if ( (unsigned int)PnpGetObjectProp(
                           i,
                           v1,
                           v2,
                           &DEVPKEY_Device_SessionId,
                           &pulProblemNumber,
                           (PBYTE)&pdnDevInst,
                           &pulStatus) )
        v7 = -1;
      else
        v7 = pdnDevInst;
      if ( v7 == -1 )
        v7 = -2;
      PnpSetObjectProp(i, v5, v6, (const DEVPROPKEY *)DEVPKEY_Device_InstallInProgress, 0, 0, 0);
      v8 = 0;
      LastError = 0;
      if ( (PnpGlobalFlags & 9) != 0 )
        v8 = 32;
      pulStatus = 0;
      pulProblemNumber = 0;
      pdnDevInst = 0;
      if ( !CM_Locate_DevNodeW(&pdnDevInst, i, 5u)
        && !CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, pdnDevInst, 0)
        && (pulStatus & 0x40000) == 0 )
      {
        if ( (pulStatus & 0x400) != 0 )
        {
          if ( pulProblemNumber == 22 )
            goto LABEL_20;
          if ( pulProblemNumber == 18 || pulProblemNumber == 1 )
            goto LABEL_18;
        }
        pdnDevInst = 0;
        v21 = 4;
        v16 = 0;
        if ( PnpGetDeviceRegProp(i, v10, &v16, &pdnDevInst, &v21, PropertyBuffer) )
          v11 = 0;
        else
          v11 = pdnDevInst;
        if ( (v11 & 0x20) != 0 || (v11 & 0x400) != 0 )
        {
LABEL_18:
          if ( !(unsigned int)QueueServerInstallEntry(1, 0, (_DWORD)i, 0, 0, 0, v7, 0, v8, 1) )
            LastError = GetLastError();
        }
      }
LABEL_20:
      SetLastError(LastError);
      v12 = -1;
      while ( i[++v12] != 0 )
        ;
    }
  }
  if ( pDeviceID )
    RtlFreeHeap(PnpHeapHandle, 0, pDeviceID);
  return DeviceIdList;
}

```

## disassembly

```asm
0x1800083b0  push    rbp
0x1800083b2  push    r15
0x1800083b4  lea     rbp, [rsp-4Fh]
0x1800083b9  sub     rsp, 88h
0x1800083c0  mov     [rsp+90h+var_28], r13
0x1800083c5  lea     rdx, [rbp+57h+pDeviceID]
0x1800083c9  xor     r13d, r13d
0x1800083cc  mov     [rbp+57h+pDeviceID], r13
0x1800083d0  call    GetDeviceIdList
0x1800083d5  mov     r15d, eax
0x1800083d8  test    eax, eax
0x1800083da  jnz     loc_1800085C3
0x1800083e0  mov     [rsp+90h+var_10], rbx
0x1800083e8  mov     rbx, [rbp+57h+pDeviceID]
0x1800083ec  test    rbx, rbx
0x1800083ef  jz      loc_18000859D
0x1800083f5  mov     [rsp+90h+var_18], rsi
0x1800083fa  mov     [rsp+90h+var_20], rdi
0x1800083ff  mov     [rsp+90h+var_30], r14
0x180008404  cmp     [rbx], r13w
0x180008408  jz      loc_18000858E
0x18000840e  lea     rax, [rbp+57h+pulStatus]
0x180008412  mov     [rbp+57h+pulProblemNumber], r13d
0x180008416  mov     qword ptr [rsp+90h+var_60], rax; PULONG
0x18000841b  lea     r9, DEVPKEY_Device_SessionId
0x180008422  lea     rax, [rbp+57h+pdnDevInst]
0x180008426  mov     [rbp+57h+pdnDevInst], 0FFFFFFFFh
0x18000842d  mov     [rsp+90h+PropertyBuffer], rax; PropertyBuffer
0x180008432  mov     rcx, rbx; pDeviceID
0x180008435  lea     rax, [rbp+57h+pulProblemNumber]
0x180008439  mov     [rbp+57h+pulStatus], 4
0x180008440  mov     qword ptr [rsp+90h+PropertyType], rax; PropertyType
0x180008445  call    PnpGetObjectProp
0x18000844a  test    eax, eax
0x18000844c  jz      loc_1800085F6
0x180008452  mov     edi, 0FFFFFFFFh
0x180008457  cmp     edi, 0FFFFFFFFh
0x18000845a  jnz     short loc_180008461
0x18000845c  mov     edi, 0FFFFFFFEh
0x180008461  mov     [rsp+90h+var_60], r13d; ULONG
0x180008466  lea     r9, DEVPKEY_Device_InstallInProgress
0x18000846d  mov     [rsp+90h+PropertyBuffer], r13; pdnDevInst
0x180008472  mov     rcx, rbx; pDeviceID
0x180008475  mov     [rsp+90h+PropertyType], r13d; PropertyType
0x18000847a  call    PnpSetObjectProp
0x18000847f  test    byte ptr cs:PnpGlobalFlags, 9
0x180008486  mov     esi, r13d
0x180008489  mov     r14d, r13d
0x18000848c  jz      short loc_180008493
0x18000848e  mov     esi, 20h ; ' '
0x180008493  mov     r8d, 5; ulFlags
0x180008499  mov     [rbp+57h+pulStatus], r13d
0x18000849d  mov     rdx, rbx; pDeviceID
0x1800084a0  mov     [rbp+57h+pulProblemNumber], r13d
0x1800084a4  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x1800084a8  mov     [rbp+57h+pdnDevInst], r13d
0x1800084ac  call    cs:__imp_CM_Locate_DevNodeW
0x1800084b2  test    eax, eax
0x1800084b4  jnz     loc_180008564
0x1800084ba  mov     r8d, [rbp+57h+pdnDevInst]; dnDevInst
0x1800084be  lea     rdx, [rbp+57h+pulProblemNumber]; pulProblemNumber
0x1800084c2  xor     r9d, r9d; ulFlags
0x1800084c5  lea     rcx, [rbp+57h+pulStatus]; pulStatus
0x1800084c9  call    cs:__imp_CM_Get_DevNode_Status
0x1800084cf  test    eax, eax
0x1800084d1  jnz     loc_180008564
0x1800084d7  mov     eax, [rbp+57h+pulStatus]
0x1800084da  bt      eax, 12h
0x1800084de  jb      loc_180008564
0x1800084e4  bt      eax, 0Ah
0x1800084e8  jb      loc_1800085FE
0x1800084ee  lea     rax, [rbp+57h+arg_18]
0x1800084f2  mov     [rbp+57h+pdnDevInst], r13d
0x1800084f6  lea     r9, [rbp+57h+pdnDevInst]
0x1800084fa  mov     qword ptr [rsp+90h+PropertyType], rax; PULONG
0x1800084ff  lea     r8, [rbp+57h+var_40]
0x180008503  mov     [rbp+57h+arg_18], 4
0x18000850a  mov     rcx, rbx; pDeviceID
0x18000850d  mov     [rbp+57h+var_40], r13d
0x180008511  call    PnpGetDeviceRegProp
0x180008516  test    eax, eax
0x180008518  jz      loc_180008621
0x18000851e  mov     eax, r13d
0x180008521  test    al, 20h
0x180008523  jnz     short loc_18000852B
0x180008525  bt      eax, 0Ah
0x180008529  jnb     short loc_180008564
0x18000852b  mov     [rsp+90h+var_48], 1
0x180008533  xor     r9d, r9d
0x180008536  mov     [rsp+90h+var_50], esi
0x18000853a  mov     r8, rbx
0x18000853d  mov     [rsp+90h+var_58], r13d
0x180008542  xor     edx, edx
0x180008544  mov     [rsp+90h+var_60], edi
0x180008548  mov     ecx, 1
0x18000854d  mov     [rsp+90h+PropertyBuffer], r13
0x180008552  mov     qword ptr [rsp+90h+PropertyType], r13
0x180008557  call    QueueServerInstallEntry
0x18000855c  test    eax, eax
0x18000855e  jz      loc_180008629
0x180008564  mov     ecx, r14d; dwErrCode
0x180008567  call    cs:__imp_SetLastError
0x18000856d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008574  cmp     [rbx+rax*2+2], r13w
0x18000857a  lea     rax, [rax+1]
0x18000857e  jnz     short loc_180008574
0x180008580  lea     rbx, [rbx+rax*2]
0x180008584  add     rbx, 2
0x180008588  jnz     loc_180008404
0x18000858e  mov     rdi, [rsp+90h+var_20]
0x180008593  mov     rsi, [rsp+90h+var_18]
0x180008598  mov     r14, [rsp+90h+var_30]
0x18000859d  mov     rbx, [rsp+90h+var_10]
0x1800085a5  cmp     [rbp+57h+pDeviceID], 0
0x1800085aa  mov     r13, [rsp+90h+var_28]
0x1800085af  jnz     loc_180008637
0x1800085b5  mov     eax, r15d
0x1800085b8  add     rsp, 88h
0x1800085bf  pop     r15
0x1800085c1  pop     rbp
0x1800085c2  retn
0x1800085c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085ca  lea     rax, WPP_GLOBAL_Control
0x1800085d1  cmp     rcx, rax
0x1800085d4  jz      short loc_1800085A5
0x1800085d6  test    byte ptr [rcx+1Ch], 1
0x1800085da  jz      short loc_1800085A5
0x1800085dc  mov     rcx, [rcx+10h]
0x1800085e0  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x1800085e7  mov     edx, 3Ah ; ':'
0x1800085ec  mov     r9d, r15d
0x1800085ef  call    WPP_SF_d
0x1800085f4  jmp     short loc_1800085A5
0x1800085f6  mov     edi, [rbp+57h+pdnDevInst]
0x1800085f9  jmp     loc_180008457
0x1800085fe  mov     eax, [rbp+57h+pulProblemNumber]
0x180008601  cmp     eax, 16h
0x180008604  jz      loc_180008564
0x18000860a  cmp     eax, 12h
0x18000860d  jz      loc_18000852B
0x180008613  cmp     eax, 1
0x180008616  jz      loc_18000852B
0x18000861c  jmp     loc_1800084EE
0x180008621  mov     eax, [rbp+57h+pdnDevInst]
0x180008624  jmp     loc_180008521
0x180008629  call    cs:__imp_GetLastError
0x18000862f  mov     r14d, eax
0x180008632  jmp     loc_180008564
0x180008637  mov     r8, [rbp+57h+pDeviceID]; P
0x18000863b  xor     edx, edx; Flags
0x18000863d  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180008644  call    cs:__imp_RtlFreeHeap
0x18000864a  jmp     loc_1800085B5
```
