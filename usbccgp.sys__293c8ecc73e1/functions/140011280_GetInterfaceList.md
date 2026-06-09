# GetInterfaceList

- ea: `0x140011280`
- end: `0x1400114cf`
- name: `GetInterfaceList`
- size: `591`
- prototype: `__int64 __fastcall(int, void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028f7c`

## callees

- `0x1400088b4`
- `0x14000f664`
- `0x140011280`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001138b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001138b`
- `ntoskrnl!ExAllocatePool2` at `0x1400112b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400112b4`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140011311`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140011311`

## pseudocode

```c
_QWORD *__fastcall GetInterfaceList(__int64 a1, struct _USB_CONFIGURATION_DESCRIPTOR *Src)
{
  __int64 bNumInterfaces; // rax
  struct _USB_CONFIGURATION_DESCRIPTOR *v3; // rbp
  int v5; // edx
  _QWORD *Pool2; // rbx
  unsigned int v7; // r12d
  unsigned int v8; // r15d
  PUSB_INTERFACE_DESCRIPTOR v9; // rax
  PUSB_INTERFACE_DESCRIPTOR v10; // rdx
  __int64 v11; // rax
  int v12; // edx
  __int64 v14; // rax
  size_t InterfaceProtocol; // [rsp+30h] [rbp-48h]
  size_t InterfaceProtocola; // [rsp+30h] [rbp-48h]

  bNumInterfaces = Src->bNumInterfaces;
  v3 = Src;
  if ( !(_BYTE)bNumInterfaces )
  {
    Pool2 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(Src) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(a1 + 1368),
        (_DWORD)Src,
        8,
        13,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
    }
    LODWORD(InterfaceProtocol) = 9;
    RecordStartFailData(a1, -1073741668, 0, -1610612730, 811748937, v3, InterfaceProtocol);
    return Pool2;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 16 * (bNumInterfaces + 1), 1130525525);
  if ( !Pool2 )
  {
    Pool2 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v5, 8, 12, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
    }
    LODWORD(InterfaceProtocol) = 0;
    RecordStartFailData(a1, -1073741670, 0, -1610612731, 1229870156, 0, InterfaceProtocol);
    return Pool2;
  }
  v7 = 0;
  v8 = 0;
  do
  {
    if ( v8 >= v3->bNumInterfaces )
    {
      v14 = 2LL * v8;
      Pool2[v14] = 0;
      Pool2[v14 + 1] = 0;
      return Pool2;
    }
    v9 = USBD_ParseConfigurationDescriptorEx(v3, v3, v7, 0, -1, -1, -1);
    v10 = v9;
    if ( v9 )
    {
      if ( (unsigned __int64)v3 + v3->wTotalLength - (_QWORD)v9 >= 9 )
      {
        v11 = 2LL * v8++;
        Pool2[v11] = v10;
        Pool2[v11 + 1] = 0;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(a1 + 1368),
          (_DWORD)v10,
          8,
          10,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
      }
    }
    ++v7;
  }
  while ( v7 <= 0x100 );
  ExFreePoolWithTag(Pool2, 0x43627355u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v12, 8, 11, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
  }
  LODWORD(InterfaceProtocola) = 9;
  RecordStartFailData(a1, -1073741668, 0, -1610612730, 1229870159, v3, InterfaceProtocola);
  return 0;
}

```

## disassembly

```asm
0x140011280  push    rbx
0x140011282  push    rbp
0x140011283  push    rsi
0x140011284  push    rdi
0x140011285  push    r12
0x140011287  push    r14
0x140011289  push    r15
0x14001128b  sub     rsp, 40h
0x14001128f  movzx   eax, byte ptr [rdx+4]
0x140011293  mov     rbp, rdx
0x140011296  mov     rsi, rcx
0x140011299  test    al, al
0x14001129b  jz      loc_14001145D
0x1400112a1  lea     rdx, [rax+1]
0x1400112a5  mov     ecx, 40h ; '@'
0x1400112aa  shl     rdx, 4
0x1400112ae  mov     r8d, 43627355h
0x1400112b4  call    cs:__imp_ExAllocatePool2
0x1400112bb  nop     dword ptr [rax+rax+00h]
0x1400112c0  mov     rbx, rax
0x1400112c3  test    rax, rax
0x1400112c6  jz      loc_14001140B
0x1400112cc  xor     r12d, r12d
0x1400112cf  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400112d6  xor     r15d, r15d
0x1400112d9  lea     r14, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x1400112e0  movzx   eax, byte ptr [rbp+4]
0x1400112e4  cmp     r15d, eax
0x1400112e7  jnb     loc_1400113EF
0x1400112ed  mov     dword ptr [rsp+78h+InterfaceProtocol], 0FFFFFFFFh; InterfaceProtocol
0x1400112f5  xor     r9d, r9d; AlternateSetting
0x1400112f8  mov     [rsp+78h+InterfaceSubClass], 0FFFFFFFFh; InterfaceSubClass
0x140011300  mov     r8d, r12d; InterfaceNumber
0x140011303  mov     rdx, rbp; StartPosition
0x140011306  mov     [rsp+78h+InterfaceClass], 0FFFFFFFFh; InterfaceClass
0x14001130e  mov     rcx, rbp; ConfigurationDescriptor
0x140011311  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140011318  nop     dword ptr [rax+rax+00h]
0x14001131d  mov     rdx, rax
0x140011320  test    rax, rax
0x140011323  jz      short loc_140011373
0x140011325  movzx   ecx, word ptr [rbp+2]
0x140011329  sub     rcx, rax
0x14001132c  add     rcx, rbp
0x14001132f  cmp     rcx, 9
0x140011333  jnb     short loc_14001135D
0x140011335  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001133c  jz      short loc_140011373
0x14001133e  mov     rcx, [rsi+558h]
0x140011345  mov     r9d, 0Ah
0x14001134b  mov     dl, 2
0x14001134d  mov     qword ptr [rsp+78h+InterfaceClass], r14
0x140011352  lea     r8d, [r9-2]
0x140011356  call    WPP_RECORDER_SF_
0x14001135b  jmp     short loc_140011373
0x14001135d  mov     eax, r15d
0x140011360  add     rax, rax
0x140011363  inc     r15d
0x140011366  mov     [rbx+rax*8], rdx
0x14001136a  mov     qword ptr [rbx+rax*8+8], 0
0x140011373  inc     r12d
0x140011376  cmp     r12d, 100h
0x14001137d  jbe     loc_1400112E0
0x140011383  mov     edx, 43627355h; Tag
0x140011388  mov     rcx, rbx; P
0x14001138b  call    cs:__imp_ExFreePoolWithTag
0x140011392  nop     dword ptr [rax+rax+00h]
0x140011397  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001139e  jz      short loc_1400113BD
0x1400113a0  mov     rcx, [rsi+558h]
0x1400113a7  mov     r9d, 0Bh
0x1400113ad  mov     dl, 2
0x1400113af  mov     qword ptr [rsp+78h+InterfaceClass], r14
0x1400113b4  lea     r8d, [r9-3]
0x1400113b8  call    WPP_RECORDER_SF_
0x1400113bd  mov     dword ptr [rsp+78h+InterfaceProtocol], 9; Size
0x1400113c5  mov     r9d, 0A0000006h; int
0x1400113cb  mov     qword ptr [rsp+78h+InterfaceSubClass], rbp; Src
0x1400113d0  xor     r8d, r8d; int
0x1400113d3  mov     edx, 0C000009Ch; int
0x1400113d8  mov     [rsp+78h+InterfaceClass], 494E544Fh; int
0x1400113e0  mov     rcx, rsi; int
0x1400113e3  call    RecordStartFailData
0x1400113e8  xor     eax, eax
0x1400113ea  jmp     loc_1400114BF
0x1400113ef  mov     eax, r15d
0x1400113f2  add     rax, rax
0x1400113f5  mov     qword ptr [rbx+rax*8], 0
0x1400113fd  mov     qword ptr [rbx+rax*8+8], 0
0x140011406  jmp     loc_1400114BC
0x14001140b  xor     ebx, ebx
0x14001140d  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140011414  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001141b  jz      short loc_14001143F
0x14001141d  mov     rcx, [rsi+558h]
0x140011424  lea     r14, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14001142b  lea     r9d, [rbx+0Ch]
0x14001142f  mov     qword ptr [rsp+78h+InterfaceClass], r14
0x140011434  lea     r8d, [rbx+8]
0x140011438  mov     dl, 2
0x14001143a  call    WPP_RECORDER_SF_
0x14001143f  mov     dword ptr [rsp+78h+InterfaceProtocol], ebx
0x140011443  mov     r9d, 0A0000005h
0x140011449  mov     qword ptr [rsp+78h+InterfaceSubClass], rbx
0x14001144e  mov     edx, 0C000009Ah
0x140011453  mov     [rsp+78h+InterfaceClass], 494E544Ch
0x14001145b  jmp     short loc_1400114B1
0x14001145d  xor     ebx, ebx
0x14001145f  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140011466  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001146d  jz      short loc_140011491
0x14001146f  mov     rcx, [rcx+558h]
0x140011476  lea     r14, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14001147d  lea     r9d, [rbx+0Dh]
0x140011481  mov     qword ptr [rsp+78h+InterfaceClass], r14
0x140011486  lea     r8d, [rbx+8]
0x14001148a  mov     dl, 2
0x14001148c  call    WPP_RECORDER_SF_
0x140011491  mov     dword ptr [rsp+78h+InterfaceProtocol], 9; Size
0x140011499  mov     r9d, 0A0000006h; int
0x14001149f  mov     qword ptr [rsp+78h+InterfaceSubClass], rbp; Src
0x1400114a4  mov     edx, 0C000009Ch; int
0x1400114a9  mov     [rsp+78h+InterfaceClass], 30624E49h; int
0x1400114b1  xor     r8d, r8d; int
0x1400114b4  mov     rcx, rsi; int
0x1400114b7  call    RecordStartFailData
0x1400114bc  mov     rax, rbx
0x1400114bf  add     rsp, 40h
0x1400114c3  pop     r15
0x1400114c5  pop     r14
0x1400114c7  pop     r12
0x1400114c9  pop     rdi
0x1400114ca  pop     rsi
0x1400114cb  pop     rbp
0x1400114cc  pop     rbx
0x1400114cd  retn
```
