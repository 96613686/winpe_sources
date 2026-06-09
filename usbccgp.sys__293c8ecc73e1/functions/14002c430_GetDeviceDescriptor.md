# GetDeviceDescriptor

- ea: `0x14002c430`
- end: `0x14002c5fe`
- name: `GetDeviceDescriptor`
- size: `462`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x140028f7c`

## callees

- `0x140009450`
- `0x14000a6cc`
- `0x14000b0ec`
- `0x14000b1f0`
- `0x14000b40c`
- `0x14000f664`
- `0x14002c430`

## pseudocode

```c
__int64 __fastcall GetDeviceDescriptor(__int64 a1)
{
  void *v1; // rsi
  NTSTATUS v3; // eax
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // edi
  int v8; // eax
  int v9; // edx
  unsigned int TransferBufferLength; // edx
  size_t Size; // [rsp+30h] [rbp-18h]
  PURB Urb; // [rsp+70h] [rbp+28h] BYREF

  v1 = (void *)(a1 + 96);
  Urb = 0;
  *(_OWORD *)(a1 + 96) = 0;
  *(_WORD *)(a1 + 112) = 0;
  v3 = USBD_UrbAllocate(*(USBD_HANDLE *)(a1 + 1344), &Urb);
  v7 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v4, 8, 32, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids, v3);
    }
  }
  else
  {
    Urb->UrbHeader.Function = 11;
    Urb->UrbHeader.Length = 136;
    Urb->UrbControlTransfer.TransferBufferLength = 18;
    Urb->UrbSelectConfiguration.Interface.InterfaceHandle = 0;
    Urb->UrbSelectInterface.Interface.InterfaceHandle = v1;
    Urb->UrbControlTransfer.SetupPacket[3] = 1;
    Urb->UrbControlTransfer.SetupPacket[2] = 0;
    Urb->UrbControlDescriptorRequest.LanguageId = 0;
    Urb->UrbControlTransfer.UrbLink = 0;
    v8 = SubmitUrb(a1, (_DWORD)Urb, v5, v6);
    v7 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 1368),
          v9,
          8,
          34,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          v8);
      }
      LODWORD(Size) = 0;
      RecordStartFailData(a1, v7, Urb->UrbHeader.Status, -1610612734, 1195656262, 0, Size);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      TransferBufferLength = Urb->UrbControlTransfer.TransferBufferLength;
      LOBYTE(TransferBufferLength) = 4;
      WPP_RECORDER_SF_qDD(
        *(_QWORD *)(a1 + 1368),
        TransferBufferLength,
        1,
        33,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        (char)v1,
        Urb->UrbControlTransfer.TransferBufferLength,
        18);
    }
    USBD_UrbFree(*(USBD_HANDLE *)(a1 + 1344), Urb);
  }
  return v7;
}

```

## disassembly

```asm
0x14002c430  push    rbp
0x14002c432  push    rbx
0x14002c433  push    rsi
0x14002c434  push    rdi
0x14002c435  mov     rbp, rsp
0x14002c438  sub     rsp, 48h
0x14002c43c  lea     rsi, [rcx+60h]
0x14002c440  mov     [rbp+Urb], 0
0x14002c448  xorps   xmm0, xmm0
0x14002c44b  lea     rdx, [rbp+Urb]; Urb
0x14002c44f  movups  xmmword ptr [rsi], xmm0
0x14002c452  xor     eax, eax
0x14002c454  mov     rbx, rcx
0x14002c457  mov     [rsi+10h], ax
0x14002c45b  mov     rcx, [rcx+540h]; USBDHandle
0x14002c462  call    USBD_UrbAllocate
0x14002c467  mov     edi, eax
0x14002c469  test    eax, eax
0x14002c46b  js      loc_14002C515
0x14002c471  mov     rax, [rbp+Urb]
0x14002c475  xor     ecx, ecx
0x14002c477  mov     byte ptr [rsp+48h+Src], 1
0x14002c47c  mov     word ptr [rax+2], 0Bh
0x14002c482  mov     rax, [rbp+Urb]
0x14002c486  mov     word ptr [rax], 88h
0x14002c48b  mov     rax, [rbp+Urb]
0x14002c48f  mov     dword ptr [rax+24h], 12h
0x14002c496  mov     rax, [rbp+Urb]
0x14002c49a  mov     qword ptr [rax+30h], 0
0x14002c4a2  mov     rax, [rbp+Urb]
0x14002c4a6  mov     [rax+28h], rsi
0x14002c4aa  mov     rax, [rbp+Urb]
0x14002c4ae  mov     byte ptr [rax+83h], 1
0x14002c4b5  mov     rax, [rbp+Urb]
0x14002c4b9  mov     byte ptr [rax+82h], 0
0x14002c4c0  mov     rax, [rbp+Urb]
0x14002c4c4  mov     [rax+84h], cx
0x14002c4cb  mov     rax, [rbp+Urb]
0x14002c4cf  mov     [rax+38h], rcx
0x14002c4d3  mov     rcx, rbx
0x14002c4d6  mov     rdx, [rbp+Urb]
0x14002c4da  call    SubmitUrb
0x14002c4df  mov     edi, eax
0x14002c4e1  test    eax, eax
0x14002c4e3  js      loc_14002C590
0x14002c4e9  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002c4f0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002c4f7  jnz     short loc_14002C54F
0x14002c4f9  mov     rdx, [rbp+Urb]; Urb
0x14002c4fd  mov     rcx, [rbx+540h]; USBDHandle
0x14002c504  call    USBD_UrbFree
0x14002c509  mov     eax, edi
0x14002c50b  add     rsp, 48h
0x14002c50f  pop     rdi
0x14002c510  pop     rsi
0x14002c511  pop     rbx
0x14002c512  pop     rbp
0x14002c513  retn
0x14002c515  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002c51c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002c523  jz      short loc_14002C509
0x14002c525  mov     r9d, 20h ; ' '
0x14002c52b  mov     dword ptr [rsp+48h+Src], edi
0x14002c52f  lea     rcx, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002c536  mov     dl, 2
0x14002c538  mov     qword ptr [rsp+48h+var_28], rcx
0x14002c53d  mov     rcx, [rbx+558h]
0x14002c544  lea     r8d, [r9-18h]
0x14002c548  call    WPP_RECORDER_SF_d
0x14002c54d  jmp     short loc_14002C509
0x14002c54f  mov     rcx, [rbp+Urb]
0x14002c553  mov     r9d, 21h ; '!'
0x14002c559  mov     [rsp+48h+var_10], 12h
0x14002c561  mov     edx, [rcx+24h]
0x14002c564  lea     r8d, [r9-20h]
0x14002c568  mov     dword ptr [rsp+48h+Size], edx
0x14002c56c  lea     rcx, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002c573  mov     [rsp+48h+Src], rsi
0x14002c578  mov     dl, 4
0x14002c57a  mov     qword ptr [rsp+48h+var_28], rcx
0x14002c57f  mov     rcx, [rbx+558h]
0x14002c586  call    WPP_RECORDER_SF_qDD
0x14002c58b  jmp     loc_14002C4F9
0x14002c590  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002c597  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002c59e  jz      short loc_14002C5C8
0x14002c5a0  mov     r9d, 22h ; '"'
0x14002c5a6  mov     dword ptr [rsp+48h+Src], edi
0x14002c5aa  lea     rcx, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002c5b1  mov     dl, 2
0x14002c5b3  mov     qword ptr [rsp+48h+var_28], rcx
0x14002c5b8  mov     rcx, [rbx+558h]
0x14002c5bf  lea     r8d, [r9-1Ah]
0x14002c5c3  call    WPP_RECORDER_SF_d
0x14002c5c8  mov     r8, [rbp+Urb]
0x14002c5cc  mov     r9d, 0A0000002h; int
0x14002c5d2  mov     dword ptr [rsp+48h+Size], 0; Size
0x14002c5da  mov     edx, edi; int
0x14002c5dc  mov     [rsp+48h+Src], 0; Src
0x14002c5e5  mov     rcx, rbx; int
0x14002c5e8  mov     [rsp+48h+var_28], 47444446h; int
0x14002c5f0  mov     r8d, [r8+4]; int
0x14002c5f4  call    RecordStartFailData
0x14002c5f9  jmp     loc_14002C4F9
```
