# RemoveListenerComplete

- ea: `0x18000abe0`
- end: `0x18000acc4`
- name: `RemoveListenerComplete`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000aa44`

## callees

- `0x180005680`
- `0x1800089dc`
- `0x180008b90`
- `0x18000abe0`
- `0x18001d1da`
- `0x18001d210`

## string_xrefs

- `0x18000ac6e`: `SyncDevIo for IOCTL_SSTPDRV_REMOVE_LISTENER_COMPLETE fails with %d [%d]`

## pseudocode

```c
__int64 RemoveListenerComplete()
{
  __int64 result; // rax
  DWORD v1; // [rsp+40h] [rbp-828h] BYREF
  int v2; // [rsp+44h] [rbp-824h] BYREF
  int v3; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v4[2044]; // [rsp+54h] [rbp-814h] BYREF

  v1 = 0;
  v3 = 0;
  memset_0(v4, 0, sizeof(v4));
  v2 = 0;
  result = SyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212428, (int)&v2, 4, 0, 0, &v1);
  if ( (_DWORD)result && (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v3) = 0;
    result = FormatRRASErrorString(
               &v3,
               L"SyncDevIo for IOCTL_SSTPDRV_REMOVE_LISTENER_COMPLETE fails with %d [%d]",
               0,
               0);
    if ( (byte_18002E903 & 8) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000abe0  sub     rsp, 868h
0x18000abe7  mov     rax, cs:__security_cookie
0x18000abee  xor     rax, rsp
0x18000abf1  mov     [rsp+868h+var_18], rax
0x18000abf9  xor     eax, eax
0x18000abfb  mov     [rsp+868h+var_828], 0
0x18000ac03  xor     edx, edx; Val
0x18000ac05  mov     [rsp+868h+var_818], eax
0x18000ac09  mov     r8d, 7FCh; Size
0x18000ac0f  lea     rcx, [rsp+868h+var_814]; void *
0x18000ac14  call    memset_0
0x18000ac19  mov     rcx, cs:SstpSvcGlobals
0x18000ac20  lea     rax, [rsp+868h+var_828]
0x18000ac25  mov     [rsp+868h+var_838], rax; LPDWORD
0x18000ac2a  lea     r8, [rsp+868h+var_824]; int
0x18000ac2f  mov     [rsp+868h+var_840], 0; DWORD
0x18000ac37  mov     r9d, 4; int
0x18000ac3d  mov     edx, 12800Ch; int
0x18000ac42  mov     [rsp+868h+var_824], 0
0x18000ac4a  mov     rcx, [rcx+118h]; int
0x18000ac51  mov     [rsp+868h+var_848], 0; LPVOID
0x18000ac5a  call    SyncDeviceControl
0x18000ac5f  test    eax, eax
0x18000ac61  jz      short loc_18000ACAB
0x18000ac63  test    cs:byte_18002E903, 8
0x18000ac6a  jz      short loc_18000ACAB
0x18000ac6c  xor     eax, eax
0x18000ac6e  lea     rdx, aSyncdevioForIo; "SyncDevIo for IOCTL_SSTPDRV_REMOVE_LIST"...
0x18000ac75  xor     r9d, r9d
0x18000ac78  mov     word ptr [rsp+868h+var_818], ax
0x18000ac7d  xor     r8d, r8d
0x18000ac80  lea     rcx, [rsp+868h+var_818]
0x18000ac85  call    FormatRRASErrorString
0x18000ac8a  test    cs:byte_18002E903, 8
0x18000ac91  jz      short loc_18000ACAB
0x18000ac93  lea     r8, [rsp+868h+var_818]
0x18000ac98  lea     rdx, RasSSTPSvcTraceError
0x18000ac9f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aca6  call    McTemplateU0z_EventWriteTransfer
0x18000acab  mov     rcx, [rsp+868h+var_18]
0x18000acb3  xor     rcx, rsp; StackCookie
0x18000acb6  call    __security_check_cookie
0x18000acbb  add     rsp, 868h
0x18000acc2  retn
```
