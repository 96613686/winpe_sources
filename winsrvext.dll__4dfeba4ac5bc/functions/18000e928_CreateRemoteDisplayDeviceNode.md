# CreateRemoteDisplayDeviceNode

- ea: `0x18000e928`
- end: `0x18000ef74`
- name: `CreateRemoteDisplayDeviceNode`
- size: `1612`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ff10`

## callees

- `0x180001090`
- `0x18000e928`
- `0x18000f954`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18000ec98`
- `ntdll!NtWaitForSingleObject` at `0x18000ec98`
- `ntdll!NtCreateEvent` at `0x18000ead0`
- `ntdll!NtCreateEvent` at `0x18000ead0`
- `ntdll!NtClose` at `0x18000edfd`
- `ntdll!NtClose` at `0x18000edfd`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000eba4`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000eba4`

## string_xrefs

- `0x18000eb3e`: `Failed to create device creation event`
- `0x18000eef4`: `Device node was successfully created`

## pseudocode

```c
__int64 __fastcall CreateRemoteDisplayDeviceNode(__int64 a1)
{
  _QWORD *v2; // r12
  _OWORD *v3; // rsi
  __int64 *v4; // r14
  __int64 *v5; // r15
  __int128 v6; // xmm0
  NTSTATUS Event; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // edi
  __int64 v11; // r9
  int v12; // ebx
  char *v13; // rdx
  __int64 *v14; // rax
  int v15; // eax
  const char *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // ecx
  void **v21; // [rsp+30h] [rbp-D0h]
  __int64 *v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+88h] [rbp-78h]
  void *EventHandle[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[32]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD *v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  __int64 *v35; // [rsp+100h] [rbp+0h]
  __int64 v36; // [rsp+108h] [rbp+8h]
  const char *v37; // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+118h] [rbp+18h]
  __int64 *v39; // [rsp+120h] [rbp+20h]
  __int64 v40; // [rsp+128h] [rbp+28h]
  int *v41; // [rsp+130h] [rbp+30h]
  __int64 v42; // [rsp+138h] [rbp+38h]
  const char *v43; // [rsp+140h] [rbp+40h]
  __int64 v44; // [rsp+148h] [rbp+48h]
  __int64 *v45; // [rsp+150h] [rbp+50h]
  __int64 v46; // [rsp+158h] [rbp+58h]
  DEVPROPKEY v47; // [rsp+160h] [rbp+60h] BYREF
  int v48; // [rsp+174h] [rbp+74h]
  __int64 v49; // [rsp+178h] [rbp+78h]
  int v50; // [rsp+180h] [rbp+80h]
  int v51; // [rsp+184h] [rbp+84h]
  int *v52; // [rsp+188h] [rbp+88h]
  __int128 v53; // [rsp+190h] [rbp+90h]
  int v54; // [rsp+1A0h] [rbp+A0h]
  int v55; // [rsp+1A4h] [rbp+A4h]
  __int64 v56; // [rsp+1A8h] [rbp+A8h]
  int v57; // [rsp+1B0h] [rbp+B0h]
  int v58; // [rsp+1B4h] [rbp+B4h]
  __int64 v59; // [rsp+1B8h] [rbp+B8h]
  __int128 v60; // [rsp+1C0h] [rbp+C0h]
  int v61; // [rsp+1D0h] [rbp+D0h]
  int v62; // [rsp+1D4h] [rbp+D4h]
  __int64 v63; // [rsp+1D8h] [rbp+D8h]
  int v64; // [rsp+1E0h] [rbp+E0h]
  int v65; // [rsp+1E4h] [rbp+E4h]
  __int64 v66; // [rsp+1E8h] [rbp+E8h]
  __int128 v67; // [rsp+1F0h] [rbp+F0h]
  int v68; // [rsp+200h] [rbp+100h]
  int v69; // [rsp+204h] [rbp+104h]
  __int64 v70; // [rsp+208h] [rbp+108h]
  int v71; // [rsp+210h] [rbp+110h]
  int v72; // [rsp+214h] [rbp+114h]
  __int64 v73; // [rsp+218h] [rbp+118h]

  v50 = 7;
  v49 = 0;
  v56 = 0;
  v63 = 0;
  v70 = 0;
  v2 = (_QWORD *)(a1 + 1096);
  v47 = DEVPKEY_Device_SessionId;
  v52 = &gSessionId;
  v3 = (_OWORD *)(a1 + 1108);
  v54 = 2;
  v53 = DEVPKEY_Device_TerminalLuid;
  v61 = 3;
  v57 = 4099;
  v60 = DEVPKEY_Device_AdapterLuid;
  v58 = 8;
  v64 = 4099;
  v65 = 8;
  v66 = a1 + 288;
  v71 = 4099;
  v67 = DEVPKEY_Device_ActivityId;
  v48 = 0;
  v51 = 4;
  v55 = 0;
  v59 = a1 + 1096;
  v62 = 0;
  v68 = 4;
  v69 = 0;
  v72 = 16;
  v73 = a1 + 1108;
  memset_0(&v26, 0, 0x48u);
  v26 = 72;
  memset(EventHandle, 0, sizeof(EventHandle));
  v4 = (__int64 *)(a1 + 296);
  v5 = (__int64 *)(a1 + 696);
  v6 = *v3;
  v29 = a1 + 296;
  v28 = a1 + 296;
  *(_OWORD *)((char *)&EventHandle[1] + 4) = v6;
  v27 = a1 + 696;
  v30 = 11;
  Event = NtCreateEvent(EventHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
  v10 = 2;
  v11 = 0x400000000000LL;
  v12 = Event;
  if ( Event >= 0 )
  {
    v22 = &ghSwDevice;
    v21 = EventHandle;
    v15 = SwDeviceCreate(L"RemoteDisplayEnum", L"HTREE\\ROOT\\0", &v26, 4, &v47, RemoteDisplayCreationCallback);
    v9 = (unsigned int)v15;
    if ( v15 >= 0 )
    {
      v12 = NtWaitForSingleObject(EventHandle[0], 0, 0);
      if ( v12 >= 0 )
      {
        if ( SLODWORD(EventHandle[1]) >= 0 )
          goto LABEL_24;
        v12 = (__int64)EventHandle[1] & 0xEFFFFFFF;
        if ( (unsigned int)dword_18001D0D8 <= 2 )
          goto LABEL_24;
        v11 = 0x400000000000LL;
        if ( (qword_18001D0E8 & 0x400000000000LL) == 0 || (qword_18001D0F0 & 0x400000000000LL) != qword_18001D0F0 )
          goto LABEL_24;
        v13 = byte_18001861D;
        v23 = gSessionId;
        v35 = (__int64 *)&v23;
        v16 = "Device creation result";
        v38 = 23;
      }
      else
      {
        if ( (unsigned int)dword_18001D0D8 <= 2 )
          goto LABEL_24;
        v11 = 0x400000000000LL;
        if ( (qword_18001D0E8 & 0x400000000000LL) == 0 || (qword_18001D0F0 & 0x400000000000LL) != qword_18001D0F0 )
          goto LABEL_24;
        v13 = (char *)word_18001877A;
        v23 = gSessionId;
        v35 = (__int64 *)&v23;
        v16 = "Failed to wait on device creation event";
        v38 = 40;
      }
      v37 = v16;
      v14 = &v24;
      LODWORD(v24) = v12;
      goto LABEL_23;
    }
    if ( (unsigned int)dword_18001D0D8 > 2 )
    {
      v8 = qword_18001D0F0;
      v11 = 0x400000000000LL;
      if ( (qword_18001D0E8 & 0x400000000000LL) != 0 && (qword_18001D0F0 & 0x400000000000LL) == qword_18001D0F0 )
      {
        v23 = gSessionId;
        LODWORD(v24) = v15;
        v35 = (__int64 *)&v23;
        v33 = v3;
        v37 = "Device creation failed";
        v34 = 16;
        v39 = &v24;
        v41 = (int *)v25;
        v36 = 4;
        v38 = 23;
        v40 = 4;
        v25[0] = 0x1000000;
        v42 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          &dword_18001D0D8,
          word_180018712,
          0,
          0,
          7,
          v32,
          EventHandle,
          (unsigned int)&ghSwDevice);
      }
    }
    v12 = -1073741823;
  }
  else if ( (unsigned int)dword_18001D0D8 > 2 )
  {
    v8 = qword_18001D0F0;
    if ( (qword_18001D0E8 & 0x400000000000LL) != 0 && (qword_18001D0F0 & 0x400000000000LL) == qword_18001D0F0 )
    {
      v13 = byte_1800187E1;
      LODWORD(v24) = gSessionId;
      v35 = &v24;
      v37 = "Failed to create device creation event";
      v14 = (__int64 *)&v23;
      v38 = 39;
      v23 = v12;
LABEL_23:
      v39 = v14;
      v42 = 8;
      v41 = (int *)v25;
      v25[0] = 0x1000000;
      v40 = 4;
      v36 = 4;
      v34 = 16;
      v33 = v3;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001D0D8, v13, 0, 0, 7, v32, v21, (_DWORD)v22);
    }
  }
LABEL_24:
  if ( !EventHandle[0] )
    NtClose(0);
  if ( v12 >= 0 )
  {
    if ( (unsigned int)dword_18001D0D8 > 4
      && (qword_18001D0E8 & 0x400000000000LL) != 0
      && (qword_18001D0F0 & 0x400000000000LL) == qword_18001D0F0 )
    {
      v17 = -1;
      v33 = v3;
      v34 = 16;
      if ( v4 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)v4 + v18) );
        v19 = 2 * v18 + 2;
      }
      else
      {
        v4 = &qword_180017108;
        v19 = 2;
      }
      v35 = v4;
      v36 = v19;
      if ( v5 )
      {
        do
          ++v17;
        while ( *((_WORD *)v5 + v17) );
        v10 = 2 * v17 + 2;
      }
      else
      {
        v5 = &qword_180017108;
      }
      v25[0] = *v2;
      v37 = (const char *)v5;
      v39 = v25;
      v23 = gSessionId;
      v41 = &v23;
      v43 = "Device node was successfully created";
      v45 = &v24;
      v38 = v10;
      v40 = 8;
      v42 = 4;
      v44 = 37;
      v24 = 0x1000000;
      v46 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001D0D8, &dword_180018684, 0, 0, 9, v32, v21, (_DWORD)v22);
    }
  }
  else
  {
    RemoveRemoteDisplayDeviceNode(v3, v8, v9, v11);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000e928  push    rbp
0x18000e92a  push    rbx
0x18000e92b  push    rsi
0x18000e92c  push    rdi
0x18000e92d  push    r12
0x18000e92f  push    r13
0x18000e931  push    r14
0x18000e933  push    r15
0x18000e935  lea     rbp, [rsp-138h]
0x18000e93d  sub     rsp, 238h
0x18000e944  mov     rax, cs:__security_cookie
0x18000e94b  xor     rax, rsp
0x18000e94e  mov     [rbp+170h+var_50], rax
0x18000e955  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data1
0x18000e95c  xor     eax, eax
0x18000e95e  mov     [rbp+170h+var_F0], 7
0x18000e968  mov     [rbp+170h+var_F8], rax
0x18000e96c  mov     rbx, rcx
0x18000e96f  mov     [rbp+170h+var_C8], rax
0x18000e976  xor     r13d, r13d
0x18000e979  mov     [rbp+170h+var_98], rax
0x18000e980  mov     ecx, 1003h
0x18000e985  mov     [rbp+170h+var_68], rax
0x18000e98c  mov     eax, cs:DEVPKEY_Device_SessionId.pid
0x18000e992  lea     r12, [rbx+448h]
0x18000e999  mov     [rbp+170h+var_100], eax
0x18000e99c  lea     edx, [r13+8]
0x18000e9a0  movaps  [rbp+170h+var_110], xmm0
0x18000e9a4  lea     rax, gSessionId
0x18000e9ab  movups  xmm0, cs:DEVPKEY_Device_TerminalLuid
0x18000e9b2  mov     [rbp+170h+var_E8], rax
0x18000e9b9  lea     edi, [rdx+40h]
0x18000e9bc  mov     eax, cs:dword_180016D28
0x18000e9c2  lea     rsi, [rbx+454h]
0x18000e9c9  mov     [rbp+170h+var_D0], eax
0x18000e9cf  mov     r8d, edi; Size
0x18000e9d2  mov     eax, cs:dword_180016D10
0x18000e9d8  movaps  [rbp+170h+var_E0], xmm0
0x18000e9df  movups  xmm0, cs:DEVPKEY_Device_AdapterLuid
0x18000e9e6  mov     [rbp+170h+var_A0], eax
0x18000e9ec  lea     rax, [rbx+120h]
0x18000e9f3  mov     [rbp+170h+var_C0], ecx
0x18000e9f9  movaps  [rbp+170h+var_B0], xmm0
0x18000ea00  movups  xmm0, cs:DEVPKEY_Device_ActivityId
0x18000ea07  mov     [rbp+170h+var_BC], edx
0x18000ea0d  mov     [rbp+170h+var_90], ecx
0x18000ea13  mov     [rbp+170h+var_8C], edx
0x18000ea19  xor     edx, edx; Val
0x18000ea1b  mov     [rbp+170h+var_88], rax
0x18000ea22  mov     eax, cs:dword_180016D58
0x18000ea28  mov     [rbp+170h+var_60], ecx
0x18000ea2e  lea     rcx, [rsp+270h+var_210]; void *
0x18000ea33  movaps  [rbp+170h+var_80], xmm0
0x18000ea3a  mov     [rbp+170h+var_FC], r13d
0x18000ea3e  mov     [rbp+170h+var_EC], 4
0x18000ea48  mov     [rbp+170h+var_CC], r13d
0x18000ea4f  mov     [rbp+170h+var_B8], r12
0x18000ea56  mov     [rbp+170h+var_9C], r13d
0x18000ea5d  mov     [rbp+170h+var_70], eax
0x18000ea63  mov     [rbp+170h+var_6C], r13d
0x18000ea6a  mov     [rbp+170h+var_5C], 10h
0x18000ea74  mov     [rbp+170h+var_58], rsi
0x18000ea7b  call    memset_0
0x18000ea80  xorps   xmm0, xmm0
0x18000ea83  mov     [rsp+270h+var_210], edi
0x18000ea87  movups  xmmword ptr [rbp+170h+EventHandle], xmm0
0x18000ea8b  lea     r14, [rbx+128h]
0x18000ea92  xor     r8d, r8d; ObjectAttributes
0x18000ea95  movups  [rbp+170h+var_1B0], xmm0
0x18000ea99  lea     r15, [rbx+2B8h]
0x18000eaa0  mov     edx, 1F0003h; DesiredAccess
0x18000eaa5  movups  xmm0, xmmword ptr [rsi]
0x18000eaa8  lea     r9d, [r13+1]; EventType
0x18000eaac  mov     [rsp+270h+var_1F8], r14
0x18000eab1  lea     rcx, [rbp+170h+EventHandle]; EventHandle
0x18000eab5  mov     [rsp+270h+var_200], r14
0x18000eaba  movdqu  xmmword ptr [rbp+170h+EventHandle+0Ch], xmm0
0x18000eabf  mov     [rsp+270h+var_208], r15
0x18000eac4  mov     [rbp+170h+var_1E8], 0Bh
0x18000eacb  mov     [rsp+270h+InitialState], r13b; InitialState
0x18000ead0  call    cs:__imp_NtCreateEvent
0x18000ead7  nop     dword ptr [rax+rax+00h]
0x18000eadc  lea     edi, [r13+2]
0x18000eae0  mov     r9, 400000000000h
0x18000eaea  mov     ebx, eax
0x18000eaec  test    eax, eax
0x18000eaee  jns     short loc_18000EB5F
0x18000eaf0  mov     ecx, cs:dword_18001D0D8
0x18000eaf6  cmp     ecx, edi
0x18000eaf8  jbe     loc_18000EDF5
0x18000eafe  mov     rdx, cs:qword_18001D0F0
0x18000eb05  mov     rcx, cs:qword_18001D0E8
0x18000eb0c  test    r9, rcx
0x18000eb0f  jz      loc_18000EDF5
0x18000eb15  mov     rax, rdx
0x18000eb18  and     rax, r9
0x18000eb1b  cmp     rax, rdx
0x18000eb1e  jnz     loc_18000EDF5
0x18000eb24  mov     eax, cs:gSessionId
0x18000eb2a  lea     rdx, byte_1800187E1
0x18000eb31  mov     dword ptr [rsp+270h+var_228], eax
0x18000eb35  lea     rax, [rsp+270h+var_228]
0x18000eb3a  mov     [rbp+170h+var_170], rax
0x18000eb3e  lea     rax, aFailedToCreate; "Failed to create device creation event"
0x18000eb45  mov     [rbp+170h+var_160], rax
0x18000eb49  lea     rax, [rsp+270h+var_230]
0x18000eb4e  mov     [rbp+170h+var_158], 27h ; '''
0x18000eb56  mov     [rsp+270h+var_230], ebx
0x18000eb5a  jmp     loc_18000ED98
0x18000eb5f  lea     rax, ghSwDevice
0x18000eb66  mov     ebx, 4
0x18000eb6b  mov     [rsp+270h+var_238], rax
0x18000eb70  lea     r8, [rsp+270h+var_210]
0x18000eb75  lea     rax, [rbp+170h+EventHandle]
0x18000eb79  mov     r9d, ebx
0x18000eb7c  mov     [rsp+270h+var_240], rax
0x18000eb81  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18000eb88  lea     rax, RemoteDisplayCreationCallback
0x18000eb8f  mov     [rsp+270h+var_248], rax
0x18000eb94  lea     rcx, aRemotedisplaye; "RemoteDisplayEnum"
0x18000eb9b  lea     rax, [rbp+170h+var_110]
0x18000eb9f  mov     qword ptr [rsp+270h+InitialState], rax
0x18000eba4  call    cs:__imp_SwDeviceCreate
0x18000ebab  nop     dword ptr [rax+rax+00h]
0x18000ebb0  mov     r8d, eax
0x18000ebb3  test    eax, eax
0x18000ebb5  jns     loc_18000EC8F
0x18000ebbb  mov     ecx, cs:dword_18001D0D8
0x18000ebc1  cmp     ecx, edi
0x18000ebc3  jbe     loc_18000EC85
0x18000ebc9  mov     rdx, cs:qword_18001D0F0
0x18000ebd0  mov     r9, 400000000000h
0x18000ebda  mov     rcx, cs:qword_18001D0E8
0x18000ebe1  test    r9, rcx
0x18000ebe4  jz      loc_18000EC85
0x18000ebea  mov     rax, rdx
0x18000ebed  and     rax, r9
0x18000ebf0  cmp     rax, rdx
0x18000ebf3  jnz     loc_18000EC85
0x18000ebf9  mov     eax, cs:gSessionId
0x18000ebff  lea     rdx, word_180018712
0x18000ec06  mov     [rsp+270h+var_230], eax
0x18000ec0a  lea     rcx, dword_18001D0D8
0x18000ec11  lea     rax, [rsp+270h+var_230]
0x18000ec16  mov     dword ptr [rsp+270h+var_228], r8d
0x18000ec1b  mov     [rbp+170h+var_170], rax
0x18000ec1f  xor     r9d, r9d
0x18000ec22  lea     rax, aDeviceCreation; "Device creation failed"
0x18000ec29  mov     [rbp+170h+var_180], rsi
0x18000ec2d  mov     [rbp+170h+var_160], rax
0x18000ec31  xor     r8d, r8d
0x18000ec34  lea     rax, [rsp+270h+var_228]
0x18000ec39  mov     [rbp+170h+var_178], 10h
0x18000ec41  mov     [rbp+170h+var_150], rax
0x18000ec45  lea     rax, [rsp+270h+var_220]
0x18000ec4a  mov     [rbp+170h+var_140], rax
0x18000ec4e  lea     rax, [rbp+170h+var_1A0]
0x18000ec52  mov     [rsp+270h+var_248], rax
0x18000ec57  mov     dword ptr [rsp+270h+InitialState], 7
0x18000ec5f  mov     [rbp+170h+var_168], rbx
0x18000ec63  mov     [rbp+170h+var_158], 17h
0x18000ec6b  mov     [rbp+170h+var_148], rbx
0x18000ec6f  mov     [rsp+270h+var_220], 1000000h
0x18000ec78  mov     [rbp+170h+var_138], 8
0x18000ec80  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ec85  mov     ebx, 0C0000001h
0x18000ec8a  jmp     loc_18000EDF5
0x18000ec8f  mov     rcx, [rbp+170h+EventHandle]; Handle
0x18000ec93  xor     r8d, r8d; Timeout
0x18000ec96  xor     edx, edx; Alertable
0x18000ec98  call    cs:__imp_NtWaitForSingleObject
0x18000ec9f  nop     dword ptr [rax+rax+00h]
0x18000eca4  mov     ebx, eax
0x18000eca6  test    eax, eax
0x18000eca8  jns     short loc_18000ED13
0x18000ecaa  mov     eax, cs:dword_18001D0D8
0x18000ecb0  cmp     eax, edi
0x18000ecb2  jbe     loc_18000EDF5
0x18000ecb8  mov     rcx, cs:qword_18001D0F0
0x18000ecbf  mov     r9, 400000000000h
0x18000ecc9  mov     rax, cs:qword_18001D0E8
0x18000ecd0  test    r9, rax
0x18000ecd3  jz      loc_18000EDF5
0x18000ecd9  mov     rax, rcx
0x18000ecdc  and     rax, r9
0x18000ecdf  cmp     rax, rcx
0x18000ece2  jnz     loc_18000EDF5
0x18000ece8  mov     eax, cs:gSessionId
0x18000ecee  lea     rdx, word_18001877A
0x18000ecf5  mov     [rsp+270h+var_230], eax
0x18000ecf9  lea     rax, [rsp+270h+var_230]
0x18000ecfe  mov     [rbp+170h+var_170], rax
0x18000ed02  lea     rax, aFailedToWaitOn; "Failed to wait on device creation event"
0x18000ed09  mov     [rbp+170h+var_158], 28h ; '('
0x18000ed11  jmp     short loc_18000ED8B
0x18000ed13  mov     eax, dword ptr [rbp+170h+EventHandle+8]
0x18000ed16  test    eax, eax
0x18000ed18  jns     loc_18000EDF5
0x18000ed1e  mov     ebx, eax
0x18000ed20  mov     eax, cs:dword_18001D0D8
0x18000ed26  btr     ebx, 1Ch
0x18000ed2a  cmp     eax, edi
0x18000ed2c  jbe     loc_18000EDF5
0x18000ed32  mov     rcx, cs:qword_18001D0F0
0x18000ed39  mov     r9, 400000000000h
0x18000ed43  mov     rax, cs:qword_18001D0E8
0x18000ed4a  test    r9, rax
0x18000ed4d  jz      loc_18000EDF5
0x18000ed53  mov     rax, rcx
0x18000ed56  and     rax, r9
0x18000ed59  cmp     rax, rcx
0x18000ed5c  jnz     loc_18000EDF5
0x18000ed62  mov     eax, cs:gSessionId
0x18000ed68  lea     rdx, byte_18001861D
0x18000ed6f  mov     [rsp+270h+var_230], eax
0x18000ed73  lea     rax, [rsp+270h+var_230]
0x18000ed78  mov     [rbp+170h+var_170], rax
0x18000ed7c  lea     rax, aDeviceCreation_0; "Device creation result"
0x18000ed83  mov     [rbp+170h+var_158], 17h
0x18000ed8b  mov     [rbp+170h+var_160], rax
0x18000ed8f  lea     rax, [rsp+270h+var_228]
0x18000ed94  mov     dword ptr [rsp+270h+var_228], ebx
0x18000ed98  mov     [rbp+170h+var_150], rax
0x18000ed9c  xor     r9d, r9d
0x18000ed9f  lea     rax, [rsp+270h+var_220]
0x18000eda4  mov     [rbp+170h+var_138], 8
0x18000edac  mov     [rbp+170h+var_140], rax
0x18000edb0  xor     r8d, r8d
0x18000edb3  lea     rax, [rbp+170h+var_1A0]
0x18000edb7  mov     [rsp+270h+var_220], 1000000h
0x18000edc0  mov     [rsp+270h+var_248], rax
0x18000edc5  mov     dword ptr [rsp+270h+InitialState], 7
0x18000edcd  mov     [rbp+170h+var_148], 4
0x18000edd5  mov     [rbp+170h+var_168], 4
0x18000eddd  mov     [rbp+170h+var_178], 10h
0x18000ede5  lea     rcx, dword_18001D0D8
0x18000edec  mov     [rbp+170h+var_180], rsi
0x18000edf0  call    _tlgWriteTransfer_EventWriteTransfer
0x18000edf5  cmp     [rbp+170h+EventHandle], r13
0x18000edf9  jnz     short loc_18000EE09
0x18000edfb  xor     ecx, ecx; Handle
0x18000edfd  call    cs:__imp_NtClose
0x18000ee04  nop     dword ptr [rax+rax+00h]
0x18000ee09  test    ebx, ebx
0x18000ee0b  jns     short loc_18000EE1A
0x18000ee0d  mov     rcx, rsi
0x18000ee10  call    RemoveRemoteDisplayDeviceNode
0x18000ee15  jmp     loc_18000EF4E
0x18000ee1a  mov     eax, cs:dword_18001D0D8
0x18000ee20  cmp     eax, 4
0x18000ee23  jbe     loc_18000EF4E
0x18000ee29  mov     rcx, cs:qword_18001D0F0
0x18000ee30  mov     rdx, 400000000000h
0x18000ee3a  mov     rax, cs:qword_18001D0E8
0x18000ee41  test    rdx, rax
0x18000ee44  jz      loc_18000EF4E
0x18000ee4a  mov     rax, rcx
0x18000ee4d  and     rax, rdx
0x18000ee50  cmp     rax, rcx
0x18000ee53  jnz     loc_18000EF4E
0x18000ee59  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ee5d  mov     [rbp+170h+var_180], rsi
0x18000ee61  mov     [rbp+170h+var_178], 10h
0x18000ee69  test    r14, r14
0x18000ee6c  jz      short loc_18000EE84
0x18000ee6e  mov     rcx, rax
0x18000ee71  inc     rcx
0x18000ee74  cmp     [r14+rcx*2], r13w
0x18000ee79  jnz     short loc_18000EE71
0x18000ee7b  lea     ecx, ds:2[rcx*2]
0x18000ee82  jmp     short loc_18000EE8D
0x18000ee84  lea     r14, qword_180017108
0x18000ee8b  mov     ecx, edi
0x18000ee8d  mov     [rbp+170h+var_170], r14
0x18000ee91  mov     dword ptr [rbp+170h+var_168], ecx
0x18000ee94  mov     dword ptr [rbp+170h+var_168+4], r13d
0x18000ee98  test    r15, r15
0x18000ee9b  jz      short loc_18000EEB0
0x18000ee9d  inc     rax
0x18000eea0  cmp     [r15+rax*2], r13w
0x18000eea5  jnz     short loc_18000EE9D
0x18000eea7  lea     edi, ds:2[rax*2]
0x18000eeae  jmp     short loc_18000EEB7
0x18000eeb0  lea     r15, qword_180017108
0x18000eeb7  mov     rax, [r12]
0x18000eebb  lea     rdx, dword_180018684
0x18000eec2  mov     [rsp+270h+var_220], rax
0x18000eec7  lea     rcx, dword_18001D0D8
0x18000eece  lea     rax, [rsp+270h+var_220]
0x18000eed3  mov     [rbp+170h+var_160], r15
0x18000eed7  mov     [rbp+170h+var_150], rax
0x18000eedb  xor     r9d, r9d
0x18000eede  mov     eax, cs:gSessionId
0x18000eee4  xor     r8d, r8d
0x18000eee7  mov     [rsp+270h+var_230], eax
0x18000eeeb  lea     rax, [rsp+270h+var_230]
0x18000eef0  mov     [rbp+170h+var_140], rax
0x18000eef4  lea     rax, aDeviceNodeWasS_0; "Device node was successfully created"
0x18000eefb  mov     [rbp+170h+var_130], rax
0x18000eeff  lea     rax, [rsp+270h+var_228]
  ... truncated ...
```
