# VmpCompleteConversion(VM_VOLUME_EXTENSION *,_DEVICE_OBJECT *)

- ea: `0x140010ad8`
- end: `0x140010d76`
- name: `?VmpCompleteConversion@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _DEVICE_OBJECT *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e888`
- `0x14000f3b0`

## callees

- `0x140002db0`
- `0x140003b00`
- `0x140003c50`
- `0x140005050`
- `0x140005540`
- `0x14000f19c`
- `0x14000f6fc`
- `0x140010ad8`
- `0x140011920`
- `0x1400123e8`
- `0x140015c30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140010ba7`
- `ntoskrnl!ObfDereferenceObject` at `0x140010ba7`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140010b95`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140010b95`

## pseudocode

```c
__int64 __fastcall VmpCompleteConversion(struct VM_VOLUME_EXTENSION *a1, struct _DEVICE_OBJECT *a2)
{
  int v4; // ecx
  int v5; // r8d
  struct _DEVICE_OBJECT *v6; // rsi
  NTSTATUS v7; // edi
  PDEVICE_OBJECT *DeviceExtension; // r14
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // r15
  __int128 v10; // xmm0
  int v11; // ecx
  int v12; // r8d
  _QWORD v14[14]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+B0h] [rbp-50h] BYREF
  int v16; // [rsp+B8h] [rbp-48h]
  _BYTE v17[40]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v18; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int8 v19[54]; // [rsp+EAh] [rbp-16h] BYREF

  memset(v14, 0, 0x68u);
  v6 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 44);
  *(_QWORD *)&v17[32] = 0;
  *((_QWORD *)a1 + 44) = 0;
  memset(v17, 0, 32);
  if ( v6 )
  {
    if ( v6 == a2 )
    {
      v7 = 0;
      if ( (Microsoft_Windows_StorageVolumeEnableBits & 1) != 0 )
        McTemplateK0qzqx_EtwWriteTransfer(
          v4,
          (unsigned int)VolumeConversionCancel,
          v5,
          *((_DWORD *)a1 + 41),
          *((_QWORD *)a1 + 47),
          *((_DWORD *)a1 + 96),
          *((_QWORD *)a1 + 49));
    }
    else
    {
      DeviceExtension = (PDEVICE_OBJECT *)v6->DeviceExtension;
      DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(DeviceExtension[2]);
      ObfDereferenceObject(DeviceAttachmentBaseRef);
      v15 = 0;
      v16 = 0;
      if ( VmpSendDeviceControl(v6, 0x2D1084u, 0, 0, v17, 0x28u) < 0 )
      {
        v7 = VmpSendDeviceControl(v6, 0x2D1080u, 0, 0, &v15, 0xCu);
        if ( v7 < 0 )
          return (unsigned int)v7;
        *(_QWORD *)&v17[12] = v15;
        *(_DWORD *)&v17[36] = v16;
        *(_QWORD *)&v17[4] = 40;
        *(_OWORD *)&v17[20] = 0;
        *(_DWORD *)v17 = 40;
      }
      VmpDeleteLegacyNameLinks(a1, 1);
      LOBYTE(v14[0]) = *((_BYTE *)a1 + 426);
      v14[1] = v6;
      v14[2] = DeviceAttachmentBaseRef;
      v14[3] = DeviceExtension[2];
      LODWORD(v14[4]) = *(_DWORD *)&v17[16];
      LODWORD(v14[6]) = *(_DWORD *)&v17[36];
      v14[7] = DeviceExtension[22];
      v14[8] = DeviceExtension[23];
      v10 = *((_OWORD *)DeviceExtension + 4);
      LOWORD(v14[11]) = *((_WORD *)a1 + 212);
      v14[12] = *((_QWORD *)a1 + 54);
      *(_OWORD *)&v14[9] = v10;
      VmpGetInstancePath(DeviceAttachmentBaseRef, (unsigned __int16 **)&v14[5]);
      VmpZeroRefCallback(a1, VmpSetTargetCallback, v14);
      VmpCreateLegacyNameLinks(a1, 1);
      if ( (Microsoft_Windows_StorageVolumeEnableBits & 1) != 0 )
        McTemplateK0qzqx_EtwWriteTransfer(
          v11,
          (unsigned int)VolumeConversionComplete,
          v12,
          *((_DWORD *)a1 + 41),
          *((_QWORD *)a1 + 47),
          *((_DWORD *)a1 + 96),
          *((_QWORD *)a1 + 49));
      v18 = 48;
      v7 = VmpQueryUniqueIdInternal(a1, &v18, v19);
      if ( v7 >= 0 )
        VmpNotify(a1, &GUID_IO_VOLUME_UNIQUE_ID_CHANGE, v18 + 2, &v18);
      else
        return 0;
    }
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140010ad8  push    rbp
0x140010ada  push    rbx
0x140010adb  push    rsi
0x140010adc  push    rdi
0x140010add  push    r14
0x140010adf  push    r15
0x140010ae1  lea     rbp, [rsp-38h]
0x140010ae6  sub     rsp, 138h
0x140010aed  mov     rax, cs:__security_cookie
0x140010af4  xor     rax, rsp
0x140010af7  mov     [rbp+60h+var_40], rax
0x140010afb  mov     rdi, rdx
0x140010afe  mov     rbx, rcx
0x140010b01  xor     edx, edx; Val
0x140010b03  lea     rcx, [rsp+160h+var_120]; void *
0x140010b08  lea     r8d, [rdx+68h]; Size
0x140010b0c  call    memset
0x140010b11  mov     rsi, [rbx+160h]
0x140010b18  xor     eax, eax
0x140010b1a  mov     [rbp+60h+var_80], rax
0x140010b1e  xorps   xmm0, xmm0
0x140010b21  mov     [rbx+160h], rax
0x140010b28  movups  [rbp+60h+var_A0], xmm0
0x140010b2c  movups  [rbp+60h+var_90], xmm0
0x140010b30  test    rsi, rsi
0x140010b33  jnz     short loc_140010B3F
0x140010b35  mov     edi, 0C0000225h
0x140010b3a  jmp     loc_140010D57
0x140010b3f  cmp     rsi, rdi
0x140010b42  jnz     short loc_140010B8D
0x140010b44  xor     edi, edi
0x140010b46  test    cs:Microsoft_Windows_StorageVolumeEnableBits, 1
0x140010b4d  jz      loc_140010D57
0x140010b53  mov     rax, [rbx+188h]
0x140010b5a  lea     rdx, VolumeConversionCancel
0x140010b61  mov     r9d, [rbx+0A4h]
0x140010b68  mov     [rsp+160h+var_130], rax
0x140010b6d  mov     eax, [rbx+180h]
0x140010b73  mov     [rsp+160h+var_138], eax
0x140010b77  mov     rax, [rbx+178h]
0x140010b7e  mov     [rsp+160h+var_140], rax
0x140010b83  call    McTemplateK0qzqx_EtwWriteTransfer
0x140010b88  jmp     loc_140010D57
0x140010b8d  mov     r14, [rsi+40h]
0x140010b91  mov     rcx, [r14+10h]; DeviceObject
0x140010b95  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140010b9c  nop     dword ptr [rax+rax+00h]
0x140010ba1  mov     rcx, rax; Object
0x140010ba4  mov     r15, rax
0x140010ba7  call    cs:__imp_ObfDereferenceObject
0x140010bae  nop     dword ptr [rax+rax+00h]
0x140010bb3  xor     eax, eax
0x140010bb5  mov     [rsp+160h+var_138], 28h ; '('; ULONG
0x140010bbd  mov     [rbp+60h+var_B0], rax
0x140010bc1  xor     r9d, r9d; InputBufferLength
0x140010bc4  mov     [rbp+60h+var_A8], eax
0x140010bc7  xor     r8d, r8d; InputBuffer
0x140010bca  lea     rax, [rbp+60h+var_A0]
0x140010bce  mov     edx, 2D1084h; IoControlCode
0x140010bd3  mov     rcx, rsi; DeviceObject
0x140010bd6  mov     [rsp+160h+var_140], rax; PVOID
0x140010bdb  call    VmpSendDeviceControl
0x140010be0  test    eax, eax
0x140010be2  jns     short loc_140010C3B
0x140010be4  lea     rax, [rbp+60h+var_B0]
0x140010be8  mov     [rsp+160h+var_138], 0Ch; ULONG
0x140010bf0  xor     r9d, r9d; InputBufferLength
0x140010bf3  mov     [rsp+160h+var_140], rax; PVOID
0x140010bf8  xor     r8d, r8d; InputBuffer
0x140010bfb  mov     edx, 2D1080h; IoControlCode
0x140010c00  mov     rcx, rsi; DeviceObject
0x140010c03  call    VmpSendDeviceControl
0x140010c08  mov     edi, eax
0x140010c0a  test    eax, eax
0x140010c0c  js      loc_140010D57
0x140010c12  mov     eax, dword ptr [rbp+60h+var_B0]
0x140010c15  xorps   xmm0, xmm0
0x140010c18  mov     dword ptr [rbp+60h+var_A0+0Ch], eax
0x140010c1b  mov     eax, dword ptr [rbp+60h+var_B0+4]
0x140010c1e  mov     dword ptr [rbp+60h+var_90], eax
0x140010c21  mov     eax, [rbp+60h+var_A8]
0x140010c24  mov     dword ptr [rbp+60h+var_80+4], eax
0x140010c27  mov     qword ptr [rbp+60h+var_A0+4], 28h ; '('
0x140010c2f  movdqu  [rbp+60h+var_90+4], xmm0
0x140010c34  mov     dword ptr [rbp+60h+var_A0], 28h ; '('
0x140010c3b  mov     dl, 1; unsigned __int8
0x140010c3d  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140010c40  call    ?VmpDeleteLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z; VmpDeleteLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)
0x140010c45  mov     al, [rbx+1AAh]
0x140010c4b  lea     rdx, [rsp+160h+var_F8]; unsigned __int16 **
0x140010c50  mov     [rsp+160h+var_120], al
0x140010c54  mov     rcx, r15; Pdo
0x140010c57  mov     [rsp+160h+var_118], rsi
0x140010c5c  mov     [rsp+160h+var_110], r15
0x140010c61  mov     rax, [r14+10h]
0x140010c65  mov     [rsp+160h+var_108], rax
0x140010c6a  mov     eax, dword ptr [rbp+60h+var_90]
0x140010c6d  mov     [rsp+160h+var_100], eax
0x140010c71  mov     eax, dword ptr [rbp+60h+var_80+4]
0x140010c74  mov     [rsp+160h+var_F0], eax
0x140010c78  mov     rax, [r14+0B0h]
0x140010c7f  mov     [rsp+160h+var_E8], rax
0x140010c84  mov     rax, [r14+0B8h]
0x140010c8b  mov     [rbp+60h+var_E0], rax
0x140010c8f  movups  xmm0, xmmword ptr [r14+40h]
0x140010c94  mov     al, [rbx+1A8h]
0x140010c9a  mov     [rbp+60h+var_C8], al
0x140010c9d  mov     al, [rbx+1A9h]
0x140010ca3  mov     [rbp+60h+var_C7], al
0x140010ca6  mov     rax, [rbx+1B0h]
0x140010cad  mov     [rbp+60h+var_C0], rax
0x140010cb1  movdqu  [rbp+60h+var_D8], xmm0
0x140010cb6  call    ?VmpGetInstancePath@@YAJPEAU_DEVICE_OBJECT@@PEAPEAG@Z; VmpGetInstancePath(_DEVICE_OBJECT *,ushort * *)
0x140010cbb  lea     r8, [rsp+160h+var_120]; void *
0x140010cc0  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140010cc3  lea     rdx, ?VmpSetTargetCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x140010cca  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x140010ccf  mov     dl, 1; unsigned __int8
0x140010cd1  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140010cd4  call    ?VmpCreateLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z; VmpCreateLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)
0x140010cd9  test    cs:Microsoft_Windows_StorageVolumeEnableBits, 1
0x140010ce0  jz      short loc_140010D17
0x140010ce2  mov     rax, [rbx+188h]
0x140010ce9  lea     rdx, VolumeConversionComplete
0x140010cf0  mov     r9d, [rbx+0A4h]
0x140010cf7  mov     [rsp+160h+var_130], rax
0x140010cfc  mov     eax, [rbx+180h]
0x140010d02  mov     [rsp+160h+var_138], eax
0x140010d06  mov     rax, [rbx+178h]
0x140010d0d  mov     [rsp+160h+var_140], rax
0x140010d12  call    McTemplateK0qzqx_EtwWriteTransfer
0x140010d17  mov     eax, 30h ; '0'
0x140010d1c  lea     r8, [rbp+60h+var_76]; unsigned __int8 *
0x140010d20  lea     rdx, [rbp+60h+var_78]; unsigned __int16 *
0x140010d24  mov     [rbp+60h+var_78], ax
0x140010d28  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140010d2b  call    ?VmpQueryUniqueIdInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEAGPEAE@Z; VmpQueryUniqueIdInternal(VM_VOLUME_EXTENSION *,ushort *,uchar *)
0x140010d30  mov     edi, eax
0x140010d32  test    eax, eax
0x140010d34  jns     short loc_140010D3A
0x140010d36  xor     edi, edi
0x140010d38  jmp     short loc_140010D57
0x140010d3a  movzx   r8d, [rbp+60h+var_78]
0x140010d3f  lea     r9, [rbp+60h+var_78]; void *
0x140010d43  add     r8w, 2; unsigned __int16
0x140010d48  lea     rdx, GUID_IO_VOLUME_UNIQUE_ID_CHANGE; struct _GUID *
0x140010d4f  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140010d52  call    ?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z; VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)
0x140010d57  mov     eax, edi
0x140010d59  mov     rcx, [rbp+60h+var_40]
0x140010d5d  xor     rcx, rsp; StackCookie
0x140010d60  call    __security_check_cookie
0x140010d65  add     rsp, 138h
0x140010d6c  pop     r15
0x140010d6e  pop     r14
0x140010d70  pop     rdi
0x140010d71  pop     rsi
0x140010d72  pop     rbx
0x140010d73  pop     rbp
0x140010d74  retn
```
