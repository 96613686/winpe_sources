# SetupListenerComplete

- ea: `0x18000a35c`
- end: `0x18000a440`
- name: `SetupListenerComplete`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a0d4`

## callees

- `0x180005230`
- `0x18000827c`
- `0x180008360`
- `0x18000a35c`
- `0x18001bcba`
- `0x18001bcf0`

## string_xrefs

- `0x18000a3ea`: `SyncDevIo for IOCTL_SSTPDRV_SETUP_LISTENER_COMPLETE fails with %d [%d]`

## pseudocode

```c
DWORD __fastcall SetupListenerComplete(unsigned int a1)
{
  DWORD result; // eax
  DWORD v3; // [rsp+40h] [rbp-828h] BYREF
  int v4[3]; // [rsp+44h] [rbp-824h] BYREF
  int v5; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+54h] [rbp-814h] BYREF

  v3 = 0;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  v4[0] = a1;
  result = SyncDeviceControl(*((void **)SstpSvcGlobals + 35), 0x128004u, v4, 4u, 0, 0, &v3);
  if ( result && (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v5) = 0;
    result = FormatRRASErrorString(
               &v5,
               L"SyncDevIo for IOCTL_SSTPDRV_SETUP_LISTENER_COMPLETE fails with %d [%d]",
               a1,
               a1);
    if ( (byte_18002D803 & 8) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000a35c  push    rbx
0x18000a35e  sub     rsp, 860h
0x18000a365  mov     rax, cs:__security_cookie
0x18000a36c  xor     rax, rsp
0x18000a36f  mov     [rsp+868h+var_18], rax
0x18000a377  mov     ebx, ecx
0x18000a379  mov     [rsp+868h+var_828], 0
0x18000a381  xor     eax, eax
0x18000a383  lea     rcx, [rsp+868h+var_814]; void *
0x18000a388  xor     edx, edx; Val
0x18000a38a  mov     [rsp+868h+var_818], eax
0x18000a38e  mov     r8d, 7FCh; Size
0x18000a394  call    memset_0
0x18000a399  mov     rcx, cs:SstpSvcGlobals
0x18000a3a0  lea     rax, [rsp+868h+var_828]
0x18000a3a5  mov     [rsp+868h+var_838], rax; LPDWORD
0x18000a3aa  lea     r8, [rsp+868h+var_824]; int
0x18000a3af  mov     [rsp+868h+var_840], 0; DWORD
0x18000a3b7  mov     r9d, 4; int
0x18000a3bd  mov     edx, 128004h; int
0x18000a3c2  mov     [rsp+868h+var_824], ebx
0x18000a3c6  mov     rcx, [rcx+118h]; int
0x18000a3cd  mov     [rsp+868h+var_848], 0; LPVOID
0x18000a3d6  call    SyncDeviceControl
0x18000a3db  test    eax, eax
0x18000a3dd  jz      short loc_18000A427
0x18000a3df  test    cs:byte_18002D803, 8
0x18000a3e6  jz      short loc_18000A427
0x18000a3e8  xor     eax, eax
0x18000a3ea  lea     rdx, aSyncdevioForIo_0; "SyncDevIo for IOCTL_SSTPDRV_SETUP_LISTE"...
0x18000a3f1  mov     r9d, ebx
0x18000a3f4  mov     word ptr [rsp+868h+var_818], ax
0x18000a3f9  mov     r8d, ebx
0x18000a3fc  lea     rcx, [rsp+868h+var_818]
0x18000a401  call    FormatRRASErrorString
0x18000a406  test    cs:byte_18002D803, 8
0x18000a40d  jz      short loc_18000A427
0x18000a40f  lea     r8, [rsp+868h+var_818]
0x18000a414  lea     rdx, RasSSTPSvcTraceError
0x18000a41b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a422  call    McTemplateU0z_EventWriteTransfer
0x18000a427  mov     rcx, [rsp+868h+var_18]
0x18000a42f  xor     rcx, rsp; StackCookie
0x18000a432  call    __security_check_cookie
0x18000a437  add     rsp, 860h
0x18000a43e  pop     rbx
0x18000a43f  retn
```
