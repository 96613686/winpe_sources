# SetupListenerComplete

- ea: `0x18000accc`
- end: `0x18000adb1`
- name: `SetupListenerComplete`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000aa44`

## callees

- `0x180005680`
- `0x1800089dc`
- `0x180008b90`
- `0x18000accc`
- `0x18001d1da`
- `0x18001d210`

## string_xrefs

- `0x18000ad5a`: `SyncDevIo for IOCTL_SSTPDRV_SETUP_LISTENER_COMPLETE fails with %d [%d]`

## pseudocode

```c
__int64 __fastcall SetupListenerComplete(unsigned int a1)
{
  __int64 result; // rax
  DWORD v3; // [rsp+40h] [rbp-828h] BYREF
  int v4; // [rsp+44h] [rbp-824h] BYREF
  int v5; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+54h] [rbp-814h] BYREF

  v3 = 0;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  v4 = a1;
  result = SyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212420, (int)&v4, 4, 0, 0, &v3);
  if ( (_DWORD)result && (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v5) = 0;
    result = FormatRRASErrorString(
               &v5,
               L"SyncDevIo for IOCTL_SSTPDRV_SETUP_LISTENER_COMPLETE fails with %d [%d]",
               a1,
               a1);
    if ( (byte_18002E903 & 8) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000accc  push    rbx
0x18000acce  sub     rsp, 860h
0x18000acd5  mov     rax, cs:__security_cookie
0x18000acdc  xor     rax, rsp
0x18000acdf  mov     [rsp+868h+var_18], rax
0x18000ace7  mov     ebx, ecx
0x18000ace9  mov     [rsp+868h+var_828], 0
0x18000acf1  xor     eax, eax
0x18000acf3  lea     rcx, [rsp+868h+var_814]; void *
0x18000acf8  xor     edx, edx; Val
0x18000acfa  mov     [rsp+868h+var_818], eax
0x18000acfe  mov     r8d, 7FCh; Size
0x18000ad04  call    memset_0
0x18000ad09  mov     rcx, cs:SstpSvcGlobals
0x18000ad10  lea     rax, [rsp+868h+var_828]
0x18000ad15  mov     [rsp+868h+var_838], rax; LPDWORD
0x18000ad1a  lea     r8, [rsp+868h+var_824]; int
0x18000ad1f  mov     [rsp+868h+var_840], 0; DWORD
0x18000ad27  mov     r9d, 4; int
0x18000ad2d  mov     edx, 128004h; int
0x18000ad32  mov     [rsp+868h+var_824], ebx
0x18000ad36  mov     rcx, [rcx+118h]; int
0x18000ad3d  mov     [rsp+868h+var_848], 0; LPVOID
0x18000ad46  call    SyncDeviceControl
0x18000ad4b  test    eax, eax
0x18000ad4d  jz      short loc_18000AD97
0x18000ad4f  test    cs:byte_18002E903, 8
0x18000ad56  jz      short loc_18000AD97
0x18000ad58  xor     eax, eax
0x18000ad5a  lea     rdx, aSyncdevioForIo_0; "SyncDevIo for IOCTL_SSTPDRV_SETUP_LISTE"...
0x18000ad61  mov     r9d, ebx
0x18000ad64  mov     word ptr [rsp+868h+var_818], ax
0x18000ad69  mov     r8d, ebx
0x18000ad6c  lea     rcx, [rsp+868h+var_818]
0x18000ad71  call    FormatRRASErrorString
0x18000ad76  test    cs:byte_18002E903, 8
0x18000ad7d  jz      short loc_18000AD97
0x18000ad7f  lea     r8, [rsp+868h+var_818]
0x18000ad84  lea     rdx, RasSSTPSvcTraceError
0x18000ad8b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ad92  call    McTemplateU0z_EventWriteTransfer
0x18000ad97  mov     rcx, [rsp+868h+var_18]
0x18000ad9f  xor     rcx, rsp; StackCookie
0x18000ada2  call    __security_check_cookie
0x18000ada7  add     rsp, 860h
0x18000adae  pop     rbx
0x18000adaf  retn
```
