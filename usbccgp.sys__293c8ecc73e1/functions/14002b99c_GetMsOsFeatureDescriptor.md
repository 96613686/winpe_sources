# GetMsOsFeatureDescriptor

- ea: `0x14002b99c`
- end: `0x14002baed`
- name: `GetMsOsFeatureDescriptor`
- size: `337`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400242a4`
- `0x140026294`
- `0x1400265cc`

## callees

- `0x14000a6cc`
- `0x14000b0ec`
- `0x14000b1f0`
- `0x14000b40c`
- `0x140015100`
- `0x14002b99c`

## pseudocode

```c
__int64 __fastcall GetMsOsFeatureDescriptor(
        __int64 a1,
        char a2,
        unsigned __int8 a3,
        unsigned __int16 a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned int *v7; // rbx
  int v12; // edx
  NTSTATUS v13; // edi
  unsigned int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // eax
  struct _URB *v19; // rdx
  PURB Urb; // [rsp+60h] [rbp+30h] BYREF

  v7 = a7;
  Urb = 0;
  if ( a7 )
    *a7 = 0;
  v13 = USBD_UrbAllocate(*(USBD_HANDLE *)(a1 + 1344), &Urb);
  if ( v13 >= 0 )
  {
    memset(Urb, 0, 0x88u);
    v15 = a6;
    Urb->UrbHeader.Function = 42;
    Urb->UrbHeader.Length = 136;
    Urb->UrbControlTransfer.TransferBufferLength = v15;
    Urb->UrbSelectInterface.Interface.InterfaceHandle = a5;
    Urb->UrbControlTransfer.SetupPacket[0] ^= (a2 ^ Urb->UrbControlTransfer.SetupPacket[0]) & 0x1F;
    Urb->UrbControlTransfer.SetupPacket[2] = a3;
    Urb->UrbControlDescriptorRequest.LanguageId = a4;
    v18 = SubmitUrb(a1, (_DWORD)Urb, v16, v17);
    v19 = Urb;
    v13 = v18;
    if ( v18 >= 0 && v7 )
      *v7 = Urb->UrbControlTransfer.TransferBufferLength;
    USBD_UrbFree(*(USBD_HANDLE *)(a1 + 1344), v19);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v12, 8, 19, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002b99c  mov     [rsp-28h+arg_8], rbx
0x14002b9a1  mov     [rsp-28h+arg_10], rsi
0x14002b9a6  push    rbp
0x14002b9a7  push    rdi
0x14002b9a8  push    r12
0x14002b9aa  push    r14
0x14002b9ac  push    r15
0x14002b9ae  mov     rbp, rsp
0x14002b9b1  sub     rsp, 30h
0x14002b9b5  mov     rbx, [rbp+arg_30]
0x14002b9b9  movzx   r14d, r9w
0x14002b9bd  mov     [rbp+Urb], 0
0x14002b9c5  mov     r15b, r8b
0x14002b9c8  mov     r12b, dl
0x14002b9cb  mov     rsi, rcx
0x14002b9ce  test    rbx, rbx
0x14002b9d1  jz      short loc_14002B9D9
0x14002b9d3  mov     dword ptr [rbx], 0
0x14002b9d9  mov     rcx, [rcx+540h]; USBDHandle
0x14002b9e0  lea     rdx, [rbp+Urb]; Urb
0x14002b9e4  call    USBD_UrbAllocate
0x14002b9e9  mov     edi, eax
0x14002b9eb  test    eax, eax
0x14002b9ed  jns     short loc_14002BA1D
0x14002b9ef  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002b9f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b9fd  jnz     loc_14002BAC0
0x14002ba03  mov     rbx, [rsp+30h+arg_8]
0x14002ba08  mov     eax, edi
0x14002ba0a  mov     rsi, [rsp+30h+arg_10]
0x14002ba0f  add     rsp, 30h
0x14002ba13  pop     r15
0x14002ba15  pop     r14
0x14002ba17  pop     r12
0x14002ba19  pop     rdi
0x14002ba1a  pop     rbp
0x14002ba1b  retn
0x14002ba1d  mov     rcx, [rbp+Urb]; void *
0x14002ba21  mov     edi, 88h
0x14002ba26  mov     r8d, edi; Size
0x14002ba29  xor     edx, edx; Val
0x14002ba2b  call    memset
0x14002ba30  mov     rax, [rbp+Urb]
0x14002ba34  mov     ecx, [rbp+arg_28]
0x14002ba37  mov     byte ptr [rsp+30h+var_8], 1
0x14002ba3c  mov     word ptr [rax+2], 2Ah ; '*'
0x14002ba42  mov     rax, [rbp+Urb]
0x14002ba46  mov     [rax], di
0x14002ba49  mov     rax, [rbp+Urb]
0x14002ba4d  mov     [rax+24h], ecx
0x14002ba50  mov     rax, [rbp+Urb]
0x14002ba54  mov     rcx, [rbp+arg_20]
0x14002ba58  mov     [rax+28h], rcx
0x14002ba5c  mov     rdx, [rbp+Urb]
0x14002ba60  mov     al, [rdx+80h]
0x14002ba66  mov     cl, al
0x14002ba68  xor     cl, r12b
0x14002ba6b  and     cl, 1Fh
0x14002ba6e  xor     cl, al
0x14002ba70  mov     [rdx+80h], cl
0x14002ba76  mov     rcx, rsi
0x14002ba79  mov     rax, [rbp+Urb]
0x14002ba7d  mov     [rax+82h], r15b
0x14002ba84  mov     rax, [rbp+Urb]
0x14002ba88  mov     [rax+84h], r14w
0x14002ba90  mov     rdx, [rbp+Urb]
0x14002ba94  call    SubmitUrb
0x14002ba99  mov     rdx, [rbp+Urb]; Urb
0x14002ba9d  mov     edi, eax
0x14002ba9f  test    eax, eax
0x14002baa1  jns     short loc_14002BAB4
0x14002baa3  mov     rcx, [rsi+540h]; USBDHandle
0x14002baaa  call    USBD_UrbFree
0x14002baaf  jmp     loc_14002BA03
0x14002bab4  test    rbx, rbx
0x14002bab7  jz      short loc_14002BAA3
0x14002bab9  mov     eax, [rdx+24h]
0x14002babc  mov     [rbx], eax
0x14002babe  jmp     short loc_14002BAA3
0x14002bac0  mov     rcx, [rsi+558h]
0x14002bac7  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14002bace  mov     r9d, 13h
0x14002bad4  mov     [rsp+30h+var_8], edi
0x14002bad8  mov     dl, 2
0x14002bada  mov     [rsp+30h+var_10], rax
0x14002badf  lea     r8d, [r9-0Bh]
0x14002bae3  call    WPP_RECORDER_SF_d
0x14002bae8  jmp     loc_14002BA03
```
