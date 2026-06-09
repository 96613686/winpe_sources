# WdfDriverManager::RestartFailedDevice(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x14008aaf0`
- end: `0x14008ad23`
- name: `?RestartFailedDevice@WdfDriverManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `563`
- prototype: `static void(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140004c58`
- `0x14002ebf0`
- `0x140032c78`
- `0x1400575b0`
- `0x14008aaf0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ab5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008abd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ab5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008abd3`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x14008ab16`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x14008ab16`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14008ac49`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14008ac49`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14008ac2b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14008ac2b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14008ab4c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14008ab4c`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x14008abc7`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x14008abc7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14008acce`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14008acce`

## pseudocode

```c
void __fastcall WdfDriverManager::RestartFailedDevice(struct _TP_CALLBACK_INSTANCE *a1, struct WdfDevNode *a2)
{
  __int64 DeviceInfoList; // r14
  DWORD LastError; // eax
  WdfDriverManager *v5; // rcx
  __int64 v6; // rdx
  int v7; // edi
  DWORD v8; // eax
  HANDLE hThread; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // edi
  CONFIGRET DevNode_Status; // eax
  WdfDriverManager *v14; // rcx
  ULONG pulStatus; // [rsp+30h] [rbp-40h] BYREF
  ULONG pulProblemNumber; // [rsp+34h] [rbp-3Ch] BYREF
  __int128 v17; // [rsp+38h] [rbp-38h] BYREF
  DEVINST dnDevInst[4]; // [rsp+48h] [rbp-28h]
  __int128 v19; // [rsp+58h] [rbp-18h]

  CallbackMayRunLong(a1);
  pulStatus = 0;
  pulProblemNumber = 0;
  v17 = 0;
  *(_OWORD *)dnDevInst = 0;
  v19 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v5 = (WdfDriverManager *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 53, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, LastError);
    }
LABEL_27:
    WdfDriverManager::DrvMgrDeviceRemoval(v5, a2);
    goto LABEL_28;
  }
  v6 = *((_QWORD *)a2 + 12);
  LODWORD(v17) = 48;
  v7 = DevObjOpenDeviceInfo(DeviceInfoList, v6, 0, 0, &v17);
  if ( v7 )
  {
    v12 = 30;
    while ( 1 )
    {
      DevNode_Status = CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, dnDevInst[1], 0);
      v11 = DevNode_Status;
      if ( DevNode_Status )
        break;
      if ( (pulStatus & 0x400) != 0 || (--v12, !v12) )
      {
        v14 = (WdfDriverManager *)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->u.APC.hThread,
            56,
            &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids,
            (unsigned int)(100 * (30 - v12)));
        }
        v7 = WdfDriverManager::EnableDevice(v14, dnDevInst[1]);
        goto LABEL_26;
      }
      Sleep(0x64u);
    }
    v7 = 0;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
    {
      hThread = WPP_GLOBAL_Control->u.APC.hThread;
      v10 = 55;
      goto LABEL_25;
    }
  }
  else
  {
    v8 = GetLastError();
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
    {
      hThread = WPP_GLOBAL_Control->u.APC.hThread;
      v10 = (unsigned int)(v7 + 54);
      v11 = v8;
LABEL_25:
      WPP_SF_d(hThread, v10, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, v11);
    }
  }
LABEL_26:
  DevObjDestroyDeviceInfoList(DeviceInfoList);
  if ( !v7 )
    goto LABEL_27;
LABEL_28:
  (*(void (__fastcall **)(struct WdfDevNode *))(*(_QWORD *)a2 + 8LL))(a2);
  (*(void (__fastcall **)(WdfDriverManager *))(*(_QWORD *)DrvMgrExt + 8LL))(DrvMgrExt);
}

```

## disassembly

```asm
0x14008aaf0  mov     [rsp-18h+arg_10], rbx
0x14008aaf5  mov     [rsp-18h+arg_18], rsi
0x14008aafa  push    rbp
0x14008aafb  push    rdi
0x14008aafc  push    r14
0x14008aafe  mov     rbp, rsp
0x14008ab01  sub     rsp, 70h
0x14008ab05  mov     rax, cs:__security_cookie
0x14008ab0c  xor     rax, rsp
0x14008ab0f  mov     [rbp+var_8], rax
0x14008ab13  mov     rbx, rdx
0x14008ab16  call    cs:__imp_CallbackMayRunLong
0x14008ab1c  xorps   xmm0, xmm0
0x14008ab1f  mov     [rbp+pulStatus], 0
0x14008ab26  xor     r9d, r9d
0x14008ab29  mov     [rbp+pulProblemNumber], 0
0x14008ab30  xor     r8d, r8d
0x14008ab33  mov     [rsp+70h+var_50], 0
0x14008ab3c  xor     edx, edx
0x14008ab3e  xor     ecx, ecx
0x14008ab40  movups  [rbp+var_38], xmm0
0x14008ab44  movups  xmmword ptr [rbp+dnDevInst], xmm0
0x14008ab48  movups  [rbp+var_18], xmm0
0x14008ab4c  call    cs:__imp_DevObjCreateDeviceInfoList
0x14008ab52  mov     r14, rax
0x14008ab55  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008ab59  jnz     short loc_14008ABAA
0x14008ab5b  call    cs:__imp_GetLastError
0x14008ab61  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ab68  lea     rcx, WPP_GLOBAL_Control
0x14008ab6f  cmp     r10, rcx
0x14008ab72  jz      loc_14008ACD8
0x14008ab78  test    byte ptr [r10+44h], 1
0x14008ab7d  jz      loc_14008ACD8
0x14008ab83  cmp     byte ptr [r10+41h], 3
0x14008ab88  jb      loc_14008ACD8
0x14008ab8e  mov     rcx, [r10+38h]
0x14008ab92  lea     edx, [r14+36h]
0x14008ab96  mov     r9d, eax
0x14008ab99  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14008aba0  call    WPP_SF_d
0x14008aba5  jmp     loc_14008ACD8
0x14008abaa  mov     rdx, [rbx+60h]
0x14008abae  lea     rax, [rbp+var_38]
0x14008abb2  xor     r9d, r9d
0x14008abb5  mov     [rsp+70h+var_50], rax
0x14008abba  xor     r8d, r8d
0x14008abbd  mov     dword ptr [rbp+var_38], 30h ; '0'
0x14008abc4  mov     rcx, r14
0x14008abc7  call    cs:__imp_DevObjOpenDeviceInfo
0x14008abcd  mov     edi, eax
0x14008abcf  test    eax, eax
0x14008abd1  jnz     short loc_14008AC15
0x14008abd3  call    cs:__imp_GetLastError
0x14008abd9  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008abe0  lea     rcx, WPP_GLOBAL_Control
0x14008abe7  cmp     r10, rcx
0x14008abea  jz      loc_14008ACCB
0x14008abf0  test    byte ptr [r10+44h], 1
0x14008abf5  jz      loc_14008ACCB
0x14008abfb  cmp     byte ptr [r10+41h], 3
0x14008ac00  jb      loc_14008ACCB
0x14008ac06  mov     rcx, [r10+38h]
0x14008ac0a  lea     edx, [rdi+36h]
0x14008ac0d  mov     r9d, eax
0x14008ac10  jmp     loc_14008ACBF
0x14008ac15  mov     esi, 1Eh
0x14008ac1a  mov     edi, esi
0x14008ac1c  mov     r8d, [rbp+dnDevInst+4]; dnDevInst
0x14008ac20  lea     rdx, [rbp+pulProblemNumber]; pulProblemNumber
0x14008ac24  xor     r9d, r9d; ulFlags
0x14008ac27  lea     rcx, [rbp+pulStatus]; pulStatus
0x14008ac2b  call    cs:__imp_CM_Get_DevNode_Status
0x14008ac31  mov     r9d, eax
0x14008ac34  test    eax, eax
0x14008ac36  jnz     short loc_14008AC97
0x14008ac38  test    [rbp+pulStatus], 400h
0x14008ac3f  jnz     short loc_14008AC51
0x14008ac41  add     edi, 0FFFFFFFFh
0x14008ac44  jz      short loc_14008AC51
0x14008ac46  lea     ecx, [rax+64h]; dwMilliseconds
0x14008ac49  call    cs:__imp_Sleep
0x14008ac4f  jmp     short loc_14008AC1C
0x14008ac51  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ac58  lea     rcx, WPP_GLOBAL_Control
0x14008ac5f  cmp     rax, rcx
0x14008ac62  jz      short loc_14008AC8B
0x14008ac64  test    byte ptr [rax+44h], 1
0x14008ac68  jz      short loc_14008AC8B
0x14008ac6a  cmp     byte ptr [rax+41h], 5
0x14008ac6e  jb      short loc_14008AC8B
0x14008ac70  mov     rcx, [rax+38h]
0x14008ac74  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14008ac7b  sub     esi, edi
0x14008ac7d  mov     edx, 38h ; '8'
0x14008ac82  imul    r9d, esi, 64h ; 'd'
0x14008ac86  call    WPP_SF_d
0x14008ac8b  mov     edx, [rbp+dnDevInst+4]; unsigned int
0x14008ac8e  call    ?EnableDevice@WdfDriverManager@@AEAAHK@Z; WdfDriverManager::EnableDevice(ulong)
0x14008ac93  mov     edi, eax
0x14008ac95  jmp     short loc_14008ACCB
0x14008ac97  xor     edi, edi
0x14008ac99  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008aca0  lea     rcx, WPP_GLOBAL_Control
0x14008aca7  cmp     rax, rcx
0x14008acaa  jz      short loc_14008ACCB
0x14008acac  test    byte ptr [rax+44h], 1
0x14008acb0  jz      short loc_14008ACCB
0x14008acb2  cmp     byte ptr [rax+41h], 3
0x14008acb6  jb      short loc_14008ACCB
0x14008acb8  mov     rcx, [rax+38h]
0x14008acbc  lea     edx, [rdi+37h]
0x14008acbf  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14008acc6  call    WPP_SF_d
0x14008accb  mov     rcx, r14
0x14008acce  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14008acd4  test    edi, edi
0x14008acd6  jnz     short loc_14008ACE0
0x14008acd8  mov     rdx, rbx; struct WdfDevNode *
0x14008acdb  call    ?DrvMgrDeviceRemoval@WdfDriverManager@@QEAAXPEAVWdfDevNode@@@Z; WdfDriverManager::DrvMgrDeviceRemoval(WdfDevNode *)
0x14008ace0  mov     rax, [rbx]
0x14008ace3  mov     rcx, rbx
0x14008ace6  mov     rax, [rax+8]
0x14008acea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008acef  mov     rcx, cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA; WdfDriverManager * DrvMgrExt
0x14008acf6  mov     rax, [rcx]
0x14008acf9  mov     rax, [rax+8]
0x14008acfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ad02  mov     rcx, [rbp+var_8]
0x14008ad06  xor     rcx, rsp; StackCookie
0x14008ad09  call    __security_check_cookie
0x14008ad0e  lea     r11, [rsp+70h+var_s0]
0x14008ad13  mov     rbx, [r11+30h]
0x14008ad17  mov     rsi, [r11+38h]
0x14008ad1b  mov     rsp, r11
0x14008ad1e  pop     r14
0x14008ad20  pop     rdi
0x14008ad21  pop     rbp
0x14008ad22  retn
```
