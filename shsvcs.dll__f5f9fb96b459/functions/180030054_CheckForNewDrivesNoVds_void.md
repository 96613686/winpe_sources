# CheckForNewDrivesNoVds(void)

- ea: `0x180030054`
- end: `0x1800301a0`
- name: `?CheckForNewDrivesNoVds@@YAHXZ`
- size: `332`
- prototype: `HANDLE(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002fcc0`

## callees

- `0x180030054`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003016e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003016e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003008f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003008f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030182`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18003015a`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18003015a`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180030178`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180030178`

## pseudocode

```c
HANDLE CheckForNewDrivesNoVds(void)
{
  HANDLE result; // rax
  char v1; // [rsp+50h] [rbp-49h] BYREF
  __int64 v2; // [rsp+58h] [rbp-41h] BYREF
  HANDLE hHandle[2]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v4; // [rsp+70h] [rbp-29h] BYREF
  DEVPROPKEY v5; // [rsp+78h] [rbp-21h]
  int v6; // [rsp+8Ch] [rbp-Dh]
  __int64 v7; // [rsp+90h] [rbp-9h]
  int v8; // [rsp+98h] [rbp-1h]
  int v9; // [rsp+9Ch] [rbp+3h]
  GUID *v10; // [rsp+A0h] [rbp+7h]
  __int64 v11; // [rsp+A8h] [rbp+Fh]
  DEVPROPKEY v12; // [rsp+B0h] [rbp+17h]
  int v13; // [rsp+C4h] [rbp+2Bh]
  __int64 v14; // [rsp+C8h] [rbp+2Fh]
  int v15; // [rsp+D0h] [rbp+37h]
  int v16; // [rsp+D4h] [rbp+3Bh]
  char *v17; // [rsp+D8h] [rbp+3Fh]

  v2 = 0;
  v1 = -1;
  *(_OWORD *)hHandle = 0;
  result = CreateEventW(0, 1, 0, 0);
  hHandle[0] = result;
  if ( result )
  {
    v4 = 2;
    v7 = 0;
    v14 = 0;
    v5 = DEVPKEY_DeviceInterface_ClassGuid;
    v10 = &GUID_DEVINTERFACE_DISK;
    v12 = DEVPKEY_DeviceInterface_Enabled;
    v17 = &v1;
    v11 = 2;
    v6 = 0;
    v8 = 13;
    v9 = 16;
    v13 = 0;
    v15 = 17;
    v16 = 1;
    if ( (int)DevCreateObjectQuery(1, 0, 0, 0, 2, &v4, InterfaceEnumCallback, hHandle, &v2) >= 0 )
    {
      WaitForSingleObjectEx(hHandle[0], 0xFFFFFFFF, 0);
      DevCloseObjectQuery(v2);
    }
    CloseHandle(hHandle[0]);
    return (HANDLE)LODWORD(hHandle[1]);
  }
  return result;
}

```

## disassembly

```asm
0x180030054  push    rbp
0x180030056  lea     rbp, [rsp-57h]
0x18003005b  sub     rsp, 0F0h
0x180030062  mov     rax, cs:__security_cookie
0x180030069  xor     rax, rsp
0x18003006c  mov     [rbp+57h+var_10], rax
0x180030070  xor     r9d, r9d; lpName
0x180030073  mov     [rbp+57h+var_98], 0
0x18003007b  xorps   xmm0, xmm0
0x18003007e  mov     [rbp+57h+var_A0], 0FFh
0x180030082  xor     r8d, r8d; bInitialState
0x180030085  xor     ecx, ecx; lpEventAttributes
0x180030087  movups  xmmword ptr [rbp+57h+hHandle], xmm0
0x18003008b  lea     edx, [r9+1]; bManualReset
0x18003008f  call    cs:__imp_CreateEventW
0x180030095  mov     [rbp+57h+hHandle], rax
0x180030099  test    rax, rax
0x18003009c  jz      loc_18003018B
0x1800300a2  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x1800300a9  xor     eax, eax
0x1800300ab  mov     [rbp+57h+var_80], 2
0x1800300b3  mov     [rbp+57h+var_60], rax
0x1800300b7  xor     r9d, r9d
0x1800300ba  mov     [rbp+57h+var_28], rax
0x1800300be  xor     r8d, r8d
0x1800300c1  movups  [rbp+57h+var_78], xmm0
0x1800300c5  lea     edx, [rax+2]
0x1800300c8  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x1800300ce  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x1800300d5  mov     [rbp+57h+var_68], eax
0x1800300d8  lea     rax, GUID_DEVINTERFACE_DISK
0x1800300df  mov     [rbp+57h+var_50], rax
0x1800300e3  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x1800300e9  mov     [rbp+57h+var_30], eax
0x1800300ec  lea     rax, [rbp+57h+var_A0]
0x1800300f0  mov     [rbp+57h+var_18], rax
0x1800300f4  lea     rax, [rbp+57h+var_98]
0x1800300f8  mov     [rsp+0F0h+var_B0], rax
0x1800300fd  lea     rax, [rbp+57h+hHandle]
0x180030101  mov     [rsp+0F0h+var_B8], rax
0x180030106  lea     rax, InterfaceEnumCallback
0x18003010d  mov     [rsp+0F0h+var_C0], rax
0x180030112  lea     rax, [rbp+57h+var_80]
0x180030116  mov     [rsp+0F0h+var_C8], rax
0x18003011b  mov     [rsp+0F0h+var_D0], edx
0x18003011f  xor     edx, edx
0x180030121  mov     [rbp+57h+var_48], 2
0x180030129  mov     [rbp+57h+var_64], 0
0x180030130  mov     [rbp+57h+var_58], 0Dh
0x180030137  lea     ecx, [rdx+1]
0x18003013a  mov     [rbp+57h+var_54], 10h
0x180030141  movaps  [rbp+57h+var_40], xmm0
0x180030145  mov     [rbp+57h+var_2C], 0
0x18003014c  mov     [rbp+57h+var_20], 11h
0x180030153  mov     [rbp+57h+var_1C], 1
0x18003015a  call    cs:__imp_DevCreateObjectQuery
0x180030160  test    eax, eax
0x180030162  js      short loc_18003017E
0x180030164  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180030168  xor     r8d, r8d; bAlertable
0x18003016b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003016e  call    cs:__imp_WaitForSingleObjectEx
0x180030174  mov     rcx, [rbp+57h+var_98]
0x180030178  call    cs:__imp_DevCloseObjectQuery
0x18003017e  mov     rcx, [rbp+57h+hHandle]; hObject
0x180030182  call    cs:__imp_CloseHandle
0x180030188  mov     eax, dword ptr [rbp+57h+hHandle+8]
0x18003018b  mov     rcx, [rbp+57h+var_10]
0x18003018f  xor     rcx, rsp; StackCookie
0x180030192  call    __security_check_cookie
0x180030197  add     rsp, 0F0h
0x18003019e  pop     rbp
0x18003019f  retn
```
