# GetStringDescriptor

- ea: `0x14000aed0`
- end: `0x14000b0e5`
- name: `GetStringDescriptor`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140025d6c`

## callees

- `0x14000a6cc`
- `0x14000aed0`
- `0x14000b0ec`
- `0x14000b1f0`
- `0x14000b40c`

## pseudocode

```c
__int64 __fastcall GetStringDescriptor(__int64 a1, char a2, unsigned __int16 a3, _DWORD *a4, unsigned int a5)
{
  USBD_HANDLE *v9; // rbx
  NTSTATUS v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // edx
  int v14; // edi
  int v15; // edx
  int v16; // r9d
  int v18; // r9d
  PURB Urb; // [rsp+30h] [rbp-18h] BYREF

  Urb = 0;
  if ( !a2 || !a4 || a5 < 4 )
  {
    v14 = -1073741811;
    v9 = (USBD_HANDLE *)(a1 + 1344);
    goto LABEL_13;
  }
  v9 = (USBD_HANDLE *)(a1 + 1344);
  *a4 = 768;
  v10 = USBD_UrbAllocate(*(USBD_HANDLE *)(a1 + 1344), &Urb);
  v13 = 0;
  v14 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v13,
        8,
        13,
        (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
        v10);
    }
    goto LABEL_13;
  }
  Urb->UrbHeader.Function = 11;
  Urb->UrbHeader.Length = 136;
  Urb->UrbControlTransfer.TransferBufferLength = a5;
  Urb->UrbSelectConfiguration.Interface.InterfaceHandle = 0;
  Urb->UrbSelectInterface.Interface.InterfaceHandle = a4;
  Urb->UrbControlTransfer.SetupPacket[3] = 3;
  Urb->UrbControlTransfer.SetupPacket[2] = a2;
  Urb->UrbControlDescriptorRequest.LanguageId = a3;
  Urb->UrbControlTransfer.UrbLink = 0;
  v14 = SubmitUrb(a1, (_DWORD)Urb, v11, v12);
  if ( v14 < 0 )
    goto LABEL_13;
  if ( *(_BYTE *)a4 < 4u )
  {
    v14 = -1073741668;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v16 = 14;
    goto LABEL_20;
  }
  if ( !*((_WORD *)a4 + 1) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_23:
      v14 = -1073741668;
      goto LABEL_13;
    }
    v18 = 15;
LABEL_25:
    LOBYTE(v15) = 4;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v15, 2, v18, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, a2);
    goto LABEL_23;
  }
  if ( (*(_BYTE *)a4 & 1) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_23;
    v18 = 16;
    goto LABEL_25;
  }
  if ( *((_BYTE *)a4 + 1) != 3 )
  {
    v14 = -1073741668;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 17;
LABEL_20:
      LOBYTE(v15) = 4;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v15,
        2,
        v16,
        (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
        a2);
    }
  }
LABEL_13:
  if ( Urb )
    USBD_UrbFree(*v9, Urb);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000aed0  push    rbp
0x14000aed2  push    rbx
0x14000aed3  push    rsi
0x14000aed4  push    rdi
0x14000aed5  push    r12
0x14000aed7  push    r13
0x14000aed9  push    r14
0x14000aedb  push    r15
0x14000aedd  mov     rbp, rsp
0x14000aee0  sub     rsp, 48h
0x14000aee4  movzx   r15d, dl
0x14000aee8  mov     rsi, r9
0x14000aeeb  xor     edx, edx
0x14000aeed  movzx   r13d, r8w
0x14000aef1  mov     [rbp+Urb], rdx
0x14000aef5  mov     r14, rcx
0x14000aef8  test    r15b, r15b
0x14000aefb  jz      loc_14000AFEC
0x14000af01  test    r9, r9
0x14000af04  jz      loc_14000AFEC
0x14000af0a  mov     r12d, [rbp+arg_20]
0x14000af0e  cmp     r12d, 4
0x14000af12  jb      loc_14000AFEC
0x14000af18  lea     rbx, [rcx+540h]
0x14000af1f  mov     dword ptr [r9], 300h
0x14000af26  mov     rcx, [rbx]; USBDHandle
0x14000af29  lea     rdx, [rbp+Urb]; Urb
0x14000af2d  call    USBD_UrbAllocate
0x14000af32  xor     edx, edx
0x14000af34  mov     edi, eax
0x14000af36  test    eax, eax
0x14000af38  js      loc_14000B01D
0x14000af3e  mov     rax, [rbp+Urb]
0x14000af42  mov     rcx, r14
0x14000af45  mov     byte ptr [rsp+48h+var_20], 1
0x14000af4a  mov     word ptr [rax+2], 0Bh
0x14000af50  mov     rax, [rbp+Urb]
0x14000af54  mov     word ptr [rax], 88h
0x14000af59  mov     rax, [rbp+Urb]
0x14000af5d  mov     [rax+24h], r12d
0x14000af61  mov     rax, [rbp+Urb]
0x14000af65  mov     [rax+30h], rdx
0x14000af69  mov     rax, [rbp+Urb]
0x14000af6d  mov     [rax+28h], rsi
0x14000af71  mov     rax, [rbp+Urb]
0x14000af75  mov     byte ptr [rax+83h], 3
0x14000af7c  mov     rax, [rbp+Urb]
0x14000af80  mov     [rax+82h], r15b
0x14000af87  mov     rax, [rbp+Urb]
0x14000af8b  mov     [rax+84h], r13w
0x14000af93  mov     rax, [rbp+Urb]
0x14000af97  mov     [rax+38h], rdx
0x14000af9b  mov     rdx, [rbp+Urb]
0x14000af9f  call    SubmitUrb
0x14000afa4  xor     r12d, r12d
0x14000afa7  mov     edi, eax
0x14000afa9  test    eax, eax
0x14000afab  js      short loc_14000AFF8
0x14000afad  mov     al, [rsi]
0x14000afaf  cmp     al, 4
0x14000afb1  jb      loc_14000B03F
0x14000afb7  cmp     [rsi+2], r12w
0x14000afbc  jz      loc_14000B084
0x14000afc2  test    al, 1
0x14000afc4  jnz     loc_14000B0D3
0x14000afca  cmp     byte ptr [rsi+1], 3
0x14000afce  jz      short loc_14000AFF8
0x14000afd0  mov     edi, 0C000009Ch
0x14000afd5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000afdc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000afe3  jz      short loc_14000AFF8
0x14000afe5  lea     r9d, [r12+11h]
0x14000afea  jmp     short loc_14000B05A
0x14000afec  mov     edi, 0C000000Dh
0x14000aff1  lea     rbx, [rcx+540h]
0x14000aff8  mov     rdx, [rbp+Urb]; Urb
0x14000affc  test    rdx, rdx
0x14000afff  jz      short loc_14000B009
0x14000b001  mov     rcx, [rbx]; USBDHandle
0x14000b004  call    USBD_UrbFree
0x14000b009  mov     eax, edi
0x14000b00b  add     rsp, 48h
0x14000b00f  pop     r15
0x14000b011  pop     r14
0x14000b013  pop     r13
0x14000b015  pop     r12
0x14000b017  pop     rdi
0x14000b018  pop     rsi
0x14000b019  pop     rbx
0x14000b01a  pop     rbp
0x14000b01b  retn
0x14000b01d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b024  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b02b  jz      short loc_14000AFF8
0x14000b02d  mov     r9d, 0Dh
0x14000b033  mov     [rsp+48h+var_20], edi
0x14000b037  mov     dl, 2
0x14000b039  lea     r8d, [r9-5]
0x14000b03d  jmp     short loc_14000B067
0x14000b03f  mov     edi, 0C000009Ch
0x14000b044  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b04b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b052  jz      short loc_14000AFF8
0x14000b054  mov     r9d, 0Eh
0x14000b05a  mov     [rsp+48h+var_20], r15d
0x14000b05f  mov     r8d, 2
0x14000b065  mov     dl, 4
0x14000b067  mov     rcx, [r14+558h]
0x14000b06e  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000b075  mov     [rsp+48h+var_28], rax
0x14000b07a  call    WPP_RECORDER_SF_d
0x14000b07f  jmp     loc_14000AFF8
0x14000b084  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b08b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b092  jnz     short loc_14000B09E
0x14000b094  mov     edi, 0C000009Ch
0x14000b099  jmp     loc_14000AFF8
0x14000b09e  mov     r9d, 0Fh
0x14000b0a4  jmp     short loc_14000B0AC
0x14000b0a6  mov     r9d, 10h
0x14000b0ac  mov     rcx, [r14+558h]
0x14000b0b3  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000b0ba  mov     [rsp+48h+var_20], r15d
0x14000b0bf  mov     r8d, 2
0x14000b0c5  mov     dl, 4
0x14000b0c7  mov     [rsp+48h+var_28], rax
0x14000b0cc  call    WPP_RECORDER_SF_d
0x14000b0d1  jmp     short loc_14000B094
0x14000b0d3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b0da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b0e1  jz      short loc_14000B094
0x14000b0e3  jmp     short loc_14000B0A6
```
