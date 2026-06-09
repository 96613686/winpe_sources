# WaitServiceState

- ea: `0x180010510`
- end: `0x18001070b`
- name: `WaitServiceState`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180010510`
- `0x180010a80`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800105a6`
- `ntdll!RtlNtStatusToDosError` at `0x1800105a6`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001061d`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001061d`
- `ntdll!RtlQueryWnfStateData` at `0x18001059a`
- `ntdll!RtlQueryWnfStateData` at `0x18001059a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180010660`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800106c8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180010660`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800106c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800106f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800106f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106d7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010654`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010654`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800105dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800105dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800106e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800106e5`

## pseudocode

```c
__int64 __fastcall WaitServiceState(__int64 a1, unsigned int a2, DWORD a3, void *a4)
{
  unsigned int i; // edi
  DWORD v8; // eax
  _QWORD *v9; // r14
  DWORD v10; // ebx
  NTSTATUS v11; // eax
  ULONG LastError; // eax
  int v13; // ecx
  unsigned int v15; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handles[2]; // [rsp+58h] [rbp-28h] BYREF
  HANDLE hObject[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v20; // [rsp+78h] [rbp-8h]

  hMem = 0;
  v20 = 0;
  v16 = 0;
  v15 = 0;
  i = 0;
  *(_OWORD *)hObject = 0;
  *(_OWORD *)Handles = 0;
  v8 = I_ScQueryServiceConfig(a1, 3, &hMem);
  v9 = hMem;
  v10 = v8;
  if ( !v8 )
  {
    LODWORD(hObject[0]) = 858874707;
    hObject[1] = 0;
    v20 = a2 | 0x300LL;
    v11 = RtlQueryWnfStateData(&v15, *(_QWORD *)hMem, ScWaitServiceStateCallback, hObject, 0);
    if ( v11 < 0 )
    {
LABEL_3:
      LastError = RtlNtStatusToDosError(v11);
LABEL_4:
      v10 = LastError;
      goto LABEL_26;
    }
    v13 = HIDWORD(v20);
    if ( !HIDWORD(v20) )
    {
      if ( !a3 )
      {
        v10 = 1460;
        goto LABEL_26;
      }
      hObject[1] = CreateEventW(0, 0, 0, 0);
      if ( !hObject[1] )
      {
LABEL_9:
        LastError = GetLastError();
        goto LABEL_4;
      }
      v11 = RtlSubscribeWnfStateChangeNotification(&v16, *v9, v15, ScWaitServiceStateCallback, hObject, 0, 0, 1);
      if ( v11 < 0 )
        goto LABEL_3;
      Handles[0] = hObject[1];
      if ( a4 )
        Handles[1] = a4;
      v10 = WaitForMultipleObjectsEx((a4 != 0) + 1, Handles, 0, a3, 0);
      RtlUnsubscribeWnfNotificationWaitForCompletion(v16);
      v16 = 0;
      if ( v10 )
      {
        if ( v10 == 1 )
        {
          v10 = 1223;
          goto LABEL_28;
        }
        if ( v10 == 258 )
        {
          v10 = 1460;
          goto LABEL_28;
        }
        goto LABEL_9;
      }
      v13 = HIDWORD(v20);
    }
    if ( (v13 & 0x300) != 0 )
    {
      v10 = 1072;
    }
    else
    {
      for ( i = 1; i < 8; ++i )
      {
        if ( *((_DWORD *)qword_1800613D0 + i) == v13 )
          goto LABEL_26;
      }
      i = 0;
      v10 = 13;
    }
  }
LABEL_26:
  if ( v16 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v16);
LABEL_28:
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  if ( v9 )
    LocalFree(v9);
  if ( !i )
    SetLastError(v10);
  return i;
}

```

## disassembly

```asm
0x180010510  push    rbp
0x180010512  push    rbx
0x180010513  push    rsi
0x180010514  push    rdi
0x180010515  push    r12
0x180010517  push    r14
0x180010519  push    r15
0x18001051b  mov     rbp, rsp
0x18001051e  sub     rsp, 80h
0x180010525  xor     eax, eax
0x180010527  mov     [rbp+hMem], 0
0x18001052f  xorps   xmm0, xmm0
0x180010532  mov     [rbp+var_8], rax
0x180010536  mov     r12d, r8d
0x180010539  mov     [rbp+var_38], rax
0x18001053d  mov     r15d, edx
0x180010540  mov     [rbp+var_40], eax
0x180010543  xor     edi, edi
0x180010545  lea     r8, [rbp+hMem]
0x180010549  mov     rsi, r9
0x18001054c  movups  xmmword ptr [rbp+hObject], xmm0
0x180010550  lea     edx, [rdi+3]
0x180010553  movups  xmmword ptr [rbp+Handles], xmm0
0x180010557  call    I_ScQueryServiceConfig
0x18001055c  mov     r14, [rbp+hMem]
0x180010560  mov     ebx, eax
0x180010562  test    eax, eax
0x180010564  jnz     loc_1800106BF
0x18001056a  mov     dword ptr [rbp+hObject], 33316353h
0x180010571  lea     r9, [rbp+hObject]
0x180010575  mov     [rbp+hObject+8], rdi
0x180010579  lea     r8, ?ScWaitServiceStateCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ScWaitServiceStateCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180010580  mov     dword ptr [rbp+var_8+4], edi
0x180010583  lea     rcx, [rbp+var_40]
0x180010587  or      r15d, 300h
0x18001058e  mov     qword ptr [rsp+80h+bAlertable], rdi
0x180010593  mov     dword ptr [rbp+var_8], r15d
0x180010597  mov     rdx, [r14]
0x18001059a  call    cs:__imp_RtlQueryWnfStateData
0x1800105a0  test    eax, eax
0x1800105a2  jns     short loc_1800105B3
0x1800105a4  mov     ecx, eax; Status
0x1800105a6  call    cs:__imp_RtlNtStatusToDosError
0x1800105ac  mov     ebx, eax
0x1800105ae  jmp     loc_1800106BF
0x1800105b3  mov     ecx, dword ptr [rbp+var_8+4]
0x1800105b6  mov     r15d, 1
0x1800105bc  test    ecx, ecx
0x1800105be  jnz     loc_180010690
0x1800105c4  test    r12d, r12d
0x1800105c7  jnz     short loc_1800105D3
0x1800105c9  mov     ebx, 5B4h
0x1800105ce  jmp     loc_1800106BF
0x1800105d3  xor     r9d, r9d; lpName
0x1800105d6  xor     r8d, r8d; bInitialState
0x1800105d9  xor     edx, edx; bManualReset
0x1800105db  xor     ecx, ecx; lpEventAttributes
0x1800105dd  call    cs:__imp_CreateEventW
0x1800105e3  mov     [rbp+hObject+8], rax
0x1800105e7  test    rax, rax
0x1800105ea  jnz     short loc_1800105F4
0x1800105ec  call    cs:__imp_GetLastError
0x1800105f2  jmp     short loc_1800105AC
0x1800105f4  mov     r8d, [rbp+var_40]
0x1800105f8  lea     rax, [rbp+hObject]
0x1800105fc  mov     rdx, [r14]
0x1800105ff  lea     r9, ?ScWaitServiceStateCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ScWaitServiceStateCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180010606  mov     [rsp+80h+var_48], r15d
0x18001060b  lea     rcx, [rbp+var_38]
0x18001060f  mov     [rsp+80h+var_50], edi
0x180010613  mov     [rsp+80h+var_58], rdi
0x180010618  mov     qword ptr [rsp+80h+bAlertable], rax
0x18001061d  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010623  test    eax, eax
0x180010625  js      loc_1800105A4
0x18001062b  mov     rax, [rbp+hObject+8]
0x18001062f  mov     [rbp+Handles], rax
0x180010633  test    rsi, rsi
0x180010636  jz      short loc_18001063C
0x180010638  mov     [rbp+Handles+8], rsi
0x18001063c  neg     rsi
0x18001063f  mov     [rsp+80h+bAlertable], edi; bAlertable
0x180010643  mov     r9d, r12d; dwMilliseconds
0x180010646  lea     rdx, [rbp+Handles]; lpHandles
0x18001064a  sbb     ecx, ecx
0x18001064c  xor     r8d, r8d; bWaitAll
0x18001064f  neg     ecx
0x180010651  add     ecx, r15d; nCount
0x180010654  call    cs:__imp_WaitForMultipleObjectsEx
0x18001065a  mov     rcx, [rbp+var_38]
0x18001065e  mov     ebx, eax
0x180010660  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180010666  mov     [rbp+var_38], rdi
0x18001066a  test    ebx, ebx
0x18001066c  jz      short loc_18001068D
0x18001066e  cmp     ebx, r15d
0x180010671  jnz     short loc_18001067A
0x180010673  mov     ebx, 4C7h
0x180010678  jmp     short loc_1800106CE
0x18001067a  cmp     ebx, 102h
0x180010680  jnz     loc_1800105EC
0x180010686  mov     ebx, 5B4h
0x18001068b  jmp     short loc_1800106CE
0x18001068d  mov     ecx, dword ptr [rbp+var_8+4]
0x180010690  test    ecx, 300h
0x180010696  jz      short loc_18001069F
0x180010698  mov     ebx, 430h
0x18001069d  jmp     short loc_1800106BF
0x18001069f  mov     edi, r15d
0x1800106a2  cmp     edi, 8
0x1800106a5  jnb     short loc_1800106BA
0x1800106a7  mov     eax, edi
0x1800106a9  lea     rdx, qword_1800613D0
0x1800106b0  cmp     [rdx+rax*4], ecx
0x1800106b3  jz      short loc_1800106BF
0x1800106b5  add     edi, r15d
0x1800106b8  jmp     short loc_1800106A2
0x1800106ba  xor     edi, edi
0x1800106bc  lea     ebx, [rdi+0Dh]
0x1800106bf  mov     rcx, [rbp+var_38]
0x1800106c3  test    rcx, rcx
0x1800106c6  jz      short loc_1800106CE
0x1800106c8  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800106ce  mov     rcx, [rbp+hObject+8]; hObject
0x1800106d2  test    rcx, rcx
0x1800106d5  jz      short loc_1800106DD
0x1800106d7  call    cs:__imp_CloseHandle
0x1800106dd  test    r14, r14
0x1800106e0  jz      short loc_1800106EB
0x1800106e2  mov     rcx, r14; hMem
0x1800106e5  call    cs:__imp_LocalFree
0x1800106eb  test    edi, edi
0x1800106ed  jnz     short loc_1800106F7
0x1800106ef  mov     ecx, ebx; dwErrCode
0x1800106f1  call    cs:__imp_SetLastError
0x1800106f7  mov     eax, edi
0x1800106f9  add     rsp, 80h
0x180010700  pop     r15
0x180010702  pop     r14
0x180010704  pop     r12
0x180010706  pop     rdi
0x180010707  pop     rsi
0x180010708  pop     rbx
0x180010709  pop     rbp
0x18001070a  retn
```
