# VPNIKEIOCTLHelper::PostDeviceIoctl(ulong,void *,ulong)

- ea: `0x18000b1d0`
- end: `0x18000b41d`
- name: `?PostDeviceIoctl@VPNIKEIOCTLHelper@@MEAAKKPEAXK@Z`
- size: `589`
- prototype: `__int64 __fastcall(VPNIKEIOCTLHelper *this, DWORD, void *, DWORD)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007590`
- `0x1800077bc`
- `0x18000b1d0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b31a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b36a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b31a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b36a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b35f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b35f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000b24f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000b24f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b30c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b30c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3bd`

## string_xrefs

- `0x18000b299`: `PostDeviceIoctl: CreateEvent failed %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VPNIKEIOCTLHelper::PostDeviceIoctl(VPNIKEIOCTLHelper *this, DWORD a2, void *a3, DWORD a4)
{
  HANDLE EventA; // rdi
  DWORD v9; // eax
  DWORD LastError; // ebx
  void *v11; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids, a2);
  }
  BytesReturned = 0;
  v15 = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  memset(&Overlapped, 0, sizeof(Overlapped));
  memset_0(v16, 0, sizeof(v16));
  if ( EventA )
  {
    v11 = (void *)*((_QWORD *)this + 1);
    LastError = 0;
    Overlapped.hEvent = EventA;
    if ( !DeviceIoControl(v11, a2, a3, a4, 0, 0, &BytesReturned, &Overlapped) )
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        LastError = 0;
        if ( WaitForSingleObject(EventA, 0xFFFFFFFF) == -1 )
        {
          LastError = GetLastError();
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v15) = 0;
            FormatRRASErrorString(&v15, L"WaitForSingleObject failed %d for IOCTL id %d", LastError, a2);
LABEL_16:
            if ( (byte_1800AA941 & 4) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v15);
          }
        }
      }
      else if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v15, L"DeviceIoControl failed %d", LastError);
        goto LABEL_16;
      }
    }
    CloseHandle(EventA);
    goto LABEL_19;
  }
  v9 = GetLastError();
  LastError = v9;
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"PostDeviceIoctl: CreateEvent failed %d", v9);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v15);
  }
LABEL_19:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b1d0  push    rbp
0x18000b1d2  push    rbx
0x18000b1d3  push    rsi
0x18000b1d4  push    rdi
0x18000b1d5  push    r12
0x18000b1d7  push    r14
0x18000b1d9  push    r15
0x18000b1db  lea     rbp, [rsp-780h]
0x18000b1e3  sub     rsp, 880h
0x18000b1ea  mov     rax, cs:__security_cookie
0x18000b1f1  xor     rax, rsp
0x18000b1f4  mov     [rbp+7B0h+var_40], rax
0x18000b1fb  mov     r12d, r9d
0x18000b1fe  mov     r15, r8
0x18000b201  mov     esi, edx
0x18000b203  mov     r14, rcx
0x18000b206  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b20d  lea     rax, WPP_GLOBAL_Control
0x18000b214  cmp     rcx, rax
0x18000b217  jz      short loc_18000B23D
0x18000b219  test    byte ptr [rcx+1Ch], 1
0x18000b21d  jz      short loc_18000B23D
0x18000b21f  cmp     byte ptr [rcx+19h], 6
0x18000b223  jb      short loc_18000B23D
0x18000b225  mov     rcx, [rcx+10h]
0x18000b229  lea     r8, WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids
0x18000b230  mov     edx, 26h ; '&'
0x18000b235  mov     r9d, esi
0x18000b238  call    WPP_SF_d
0x18000b23d  xor     r9d, r9d; lpName
0x18000b240  mov     [rsp+8B0h+BytesReturned], 0
0x18000b248  xor     r8d, r8d; bInitialState
0x18000b24b  xor     edx, edx; bManualReset
0x18000b24d  xor     ecx, ecx; lpEventAttributes
0x18000b24f  call    cs:__imp_CreateEventA
0x18000b255  xor     ecx, ecx
0x18000b257  xorps   xmm0, xmm0
0x18000b25a  mov     [rsp+8B0h+var_840], ecx
0x18000b25e  xor     edx, edx; Val
0x18000b260  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18000b265  mov     r8d, 7FCh; Size
0x18000b26b  mov     rdi, rax
0x18000b26e  movups  xmmword ptr [rsp+8B0h+Overlapped.Internal], xmm0
0x18000b273  movups  xmmword ptr [rsp+8B0h+Overlapped.10h], xmm0
0x18000b278  call    memset_0
0x18000b27d  test    rdi, rdi
0x18000b280  jnz     short loc_18000B2DC
0x18000b282  call    cs:__imp_GetLastError
0x18000b288  test    cs:byte_1800AA941, 4
0x18000b28f  mov     ebx, eax
0x18000b291  jz      loc_18000B3C3
0x18000b297  xor     ecx, ecx
0x18000b299  lea     rdx, aPostdeviceioct; "PostDeviceIoctl: CreateEvent failed %d"
0x18000b2a0  mov     word ptr [rsp+8B0h+var_840], cx
0x18000b2a5  mov     r8d, eax
0x18000b2a8  lea     rcx, [rsp+8B0h+var_840]
0x18000b2ad  call    FormatRRASErrorString
0x18000b2b2  test    cs:byte_1800AA941, 4
0x18000b2b9  jz      loc_18000B3C3
0x18000b2bf  lea     r8, [rsp+8B0h+var_840]
0x18000b2c4  lea     rdx, RasVpnIkeTraceError
0x18000b2cb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b2d2  call    McTemplateU0z_EventWriteTransfer
0x18000b2d7  jmp     loc_18000B3C3
0x18000b2dc  mov     rcx, [r14+8]; hDevice
0x18000b2e0  lea     rax, [rsp+8B0h+Overlapped]
0x18000b2e5  mov     [rsp+8B0h+lpOverlapped], rax; lpOverlapped
0x18000b2ea  xor     ebx, ebx
0x18000b2ec  lea     rax, [rsp+8B0h+BytesReturned]
0x18000b2f1  mov     [rsp+8B0h+Overlapped.hEvent], rdi
0x18000b2f6  mov     [rsp+8B0h+lpBytesReturned], rax; lpBytesReturned
0x18000b2fb  mov     r9d, r12d; nInBufferSize
0x18000b2fe  mov     [rsp+8B0h+nOutBufferSize], ebx; nOutBufferSize
0x18000b302  mov     r8, r15; lpInBuffer
0x18000b305  mov     edx, esi; dwIoControlCode
0x18000b307  mov     [rsp+8B0h+lpOutBuffer], rbx; lpOutBuffer
0x18000b30c  call    cs:__imp_DeviceIoControl
0x18000b312  test    eax, eax
0x18000b314  jnz     loc_18000B3BA
0x18000b31a  call    cs:__imp_GetLastError
0x18000b320  mov     ebx, eax
0x18000b322  cmp     eax, 3E5h
0x18000b327  jz      short loc_18000B353
0x18000b329  test    cs:byte_1800AA941, 4
0x18000b330  jz      loc_18000B3BA
0x18000b336  xor     eax, eax
0x18000b338  lea     rdx, aDeviceiocontro_0; "DeviceIoControl failed %d"
0x18000b33f  mov     r8d, ebx
0x18000b342  mov     word ptr [rsp+8B0h+var_840], ax
0x18000b347  lea     rcx, [rsp+8B0h+var_840]
0x18000b34c  call    FormatRRASErrorString
0x18000b351  jmp     short loc_18000B399
0x18000b353  or      r14d, 0FFFFFFFFh
0x18000b357  mov     rcx, rdi; hHandle
0x18000b35a  mov     edx, r14d; dwMilliseconds
0x18000b35d  xor     ebx, ebx
0x18000b35f  call    cs:__imp_WaitForSingleObject
0x18000b365  cmp     eax, r14d
0x18000b368  jnz     short loc_18000B3BA
0x18000b36a  call    cs:__imp_GetLastError
0x18000b370  test    cs:byte_1800AA941, 4
0x18000b377  mov     ebx, eax
0x18000b379  jz      short loc_18000B3BA
0x18000b37b  xor     eax, eax
0x18000b37d  lea     rdx, aWaitforsingleo; "WaitForSingleObject failed %d for IOCTL"...
0x18000b384  mov     r9d, esi
0x18000b387  mov     word ptr [rsp+8B0h+var_840], ax
0x18000b38c  mov     r8d, ebx
0x18000b38f  lea     rcx, [rsp+8B0h+var_840]
0x18000b394  call    FormatRRASErrorString
0x18000b399  test    cs:byte_1800AA941, 4
0x18000b3a0  jz      short loc_18000B3BA
0x18000b3a2  lea     r8, [rsp+8B0h+var_840]
0x18000b3a7  lea     rdx, RasVpnIkeTraceError
0x18000b3ae  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b3b5  call    McTemplateU0z_EventWriteTransfer
0x18000b3ba  mov     rcx, rdi; hObject
0x18000b3bd  call    cs:__imp_CloseHandle
0x18000b3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3ca  lea     rax, WPP_GLOBAL_Control
0x18000b3d1  cmp     rcx, rax
0x18000b3d4  jz      short loc_18000B3FA
0x18000b3d6  test    byte ptr [rcx+1Ch], 1
0x18000b3da  jz      short loc_18000B3FA
0x18000b3dc  cmp     byte ptr [rcx+19h], 6
0x18000b3e0  jb      short loc_18000B3FA
0x18000b3e2  mov     rcx, [rcx+10h]
0x18000b3e6  lea     r8, WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids
0x18000b3ed  mov     edx, 27h ; '''
0x18000b3f2  mov     r9d, ebx
0x18000b3f5  call    WPP_SF_d
0x18000b3fa  mov     eax, ebx
0x18000b3fc  mov     rcx, [rbp+7B0h+var_40]
0x18000b403  xor     rcx, rsp; StackCookie
0x18000b406  call    __security_check_cookie
0x18000b40b  add     rsp, 880h
0x18000b412  pop     r15
0x18000b414  pop     r14
0x18000b416  pop     r12
0x18000b418  pop     rdi
0x18000b419  pop     rsi
0x18000b41a  pop     rbx
0x18000b41b  pop     rbp
0x18000b41c  retn
```
