# RemoveListenerComplete

- ea: `0x18000a270`
- end: `0x18000a353`
- name: `RemoveListenerComplete`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a0d4`

## callees

- `0x180005230`
- `0x18000827c`
- `0x180008360`
- `0x18000a270`
- `0x18001bcba`
- `0x18001bcf0`

## string_xrefs

- `0x18000a2fe`: `SyncDevIo for IOCTL_SSTPDRV_REMOVE_LISTENER_COMPLETE fails with %d [%d]`

## pseudocode

```c
DWORD RemoveListenerComplete()
{
  DWORD result; // eax
  DWORD v1; // [rsp+40h] [rbp-828h] BYREF
  int v2[3]; // [rsp+44h] [rbp-824h] BYREF
  int v3; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v4[2044]; // [rsp+54h] [rbp-814h] BYREF

  v1 = 0;
  v3 = 0;
  memset_0(v4, 0, sizeof(v4));
  v2[0] = 0;
  result = SyncDeviceControl(*((void **)SstpSvcGlobals + 35), 0x12800Cu, v2, 4u, 0, 0, &v1);
  if ( result && (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v3) = 0;
    result = FormatRRASErrorString(
               &v3,
               L"SyncDevIo for IOCTL_SSTPDRV_REMOVE_LISTENER_COMPLETE fails with %d [%d]",
               0,
               0);
    if ( (byte_18002D803 & 8) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000a270  sub     rsp, 868h
0x18000a277  mov     rax, cs:__security_cookie
0x18000a27e  xor     rax, rsp
0x18000a281  mov     [rsp+868h+var_18], rax
0x18000a289  xor     eax, eax
0x18000a28b  mov     [rsp+868h+var_828], 0
0x18000a293  xor     edx, edx; Val
0x18000a295  mov     [rsp+868h+var_818], eax
0x18000a299  mov     r8d, 7FCh; Size
0x18000a29f  lea     rcx, [rsp+868h+var_814]; void *
0x18000a2a4  call    memset_0
0x18000a2a9  mov     rcx, cs:SstpSvcGlobals
0x18000a2b0  lea     rax, [rsp+868h+var_828]
0x18000a2b5  mov     [rsp+868h+var_838], rax; LPDWORD
0x18000a2ba  lea     r8, [rsp+868h+var_824]; int
0x18000a2bf  mov     [rsp+868h+var_840], 0; DWORD
0x18000a2c7  mov     r9d, 4; int
0x18000a2cd  mov     edx, 12800Ch; int
0x18000a2d2  mov     [rsp+868h+var_824], 0
0x18000a2da  mov     rcx, [rcx+118h]; int
0x18000a2e1  mov     [rsp+868h+var_848], 0; LPVOID
0x18000a2ea  call    SyncDeviceControl
0x18000a2ef  test    eax, eax
0x18000a2f1  jz      short loc_18000A33B
0x18000a2f3  test    cs:byte_18002D803, 8
0x18000a2fa  jz      short loc_18000A33B
0x18000a2fc  xor     eax, eax
0x18000a2fe  lea     rdx, aSyncdevioForIo; "SyncDevIo for IOCTL_SSTPDRV_REMOVE_LIST"...
0x18000a305  xor     r9d, r9d
0x18000a308  mov     word ptr [rsp+868h+var_818], ax
0x18000a30d  xor     r8d, r8d
0x18000a310  lea     rcx, [rsp+868h+var_818]
0x18000a315  call    FormatRRASErrorString
0x18000a31a  test    cs:byte_18002D803, 8
0x18000a321  jz      short loc_18000A33B
0x18000a323  lea     r8, [rsp+868h+var_818]
0x18000a328  lea     rdx, RasSSTPSvcTraceError
0x18000a32f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a336  call    McTemplateU0z_EventWriteTransfer
0x18000a33b  mov     rcx, [rsp+868h+var_18]
0x18000a343  xor     rcx, rsp; StackCookie
0x18000a346  call    __security_check_cookie
0x18000a34b  add     rsp, 868h
0x18000a352  retn
```
