# SpGetStreamParameters(SP_DEVICE *,_IRP *)

- ea: `0x140033c50`
- end: `0x140033f77`
- name: `?SpGetStreamParameters@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(struct SP_DEVICE *this, struct _IRP *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001ad10`

## callees

- `0x14000b080`
- `0x14000ec40`
- `0x14000ed90`
- `0x1400108f0`
- `0x14002ce90`
- `0x14002e43c`
- `0x140033c50`
- `0x140067fc0`
- `0x1400684c0`
- `0x1400b6720`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140033f22`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140033f22`
- `ntoskrnl!RtlTestBit` at `0x140033e15`
- `ntoskrnl!RtlTestBit` at `0x140033e15`

## pseudocode

```c
__int64 __fastcall SpGetStreamParameters(PEX_RUNDOWN_REF_CACHE_AWARE *this, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v5; // ebx
  ULONG DeviceType; // ecx
  const char *v7; // r9
  struct _IRP *MasterIrp; // rdi
  ULONG_PTR Length; // r14
  struct _RTL_BITMAP *v11; // r13
  struct SIO_SPACE *TopLevel; // rax
  SP_DRIVE **i; // rax
  SP_DRIVE **v14; // r14
  int MdlAddress; // ecx
  unsigned int MdlAddress_high; // eax
  unsigned int v17; // ecx
  ULONG Flags; // eax
  ULONG v19; // ecx
  ULONG v20; // eax
  ULONG v21; // ecx
  unsigned int IrpCount; // eax
  LONG v23; // ecx
  unsigned int SystemBuffer_high; // eax
  unsigned int v25; // ecx
  unsigned int Flink; // eax
  unsigned int v27; // ecx
  unsigned int Flink_high; // eax
  unsigned int v29; // ecx
  unsigned int Blink; // eax
  unsigned int v31; // ecx
  unsigned int Blink_high; // eax
  unsigned int v33; // ecx
  struct SIO_SPACE *v34; // rax
  ULONG BitNumber[2]; // [rsp+30h] [rbp-40h] BYREF
  int v36; // [rsp+38h] [rbp-38h] BYREF
  __int128 v37; // [rsp+3Ch] [rbp-34h]
  _BYTE v38[28]; // [rsp+4Ch] [rbp-24h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(v38, 0, sizeof(v38));
  *(_QWORD *)BitNumber = 0;
  v36 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids);
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 8 )
  {
    v5 = -1073741820;
LABEL_53:
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v7 = "Error";
    goto LABEL_14;
  }
  if ( *(_DWORD *)a2->AssociatedIrp.MasterIrp != 1 )
  {
    v5 = -1073741811;
    goto LABEL_53;
  }
  if ( CurrentStackLocation->Parameters.Read.Length >= 8 )
  {
    v5 = SP_DEVICE::AcquireRundownShared((SP_DEVICE *)this, a2);
    if ( !v5 )
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      Length = CurrentStackLocation->Parameters.Read.Length;
      memset(MasterIrp, 0, (unsigned int)Length);
      *(_DWORD *)&MasterIrp->Type = 1;
      *(_DWORD *)(&MasterIrp->Size + 1) = 48;
      if ( (unsigned int)Length >= 0x30 )
      {
        MasterIrp->AssociatedIrp.IrpCount = -1;
        LODWORD(MasterIrp->ThreadListEntry.Flink) = -1;
        HIDWORD(MasterIrp->ThreadListEntry.Flink) = -1;
        HIDWORD(MasterIrp->ThreadListEntry.Blink) = -1;
        v11 = (struct _RTL_BITMAP *)this[403];
        TopLevel = SIO_SPACE::GetTopLevel((SIO_SPACE *)v11);
        for ( i = (SP_DRIVE **)SC_SPARSE::FindFirstObject(*((SC_SPARSE **)TopLevel + 34), (unsigned __int64 *)BitNumber);
              ;
              i = (SP_DRIVE **)SC_SPARSE::FindNextObject(*((SC_SPARSE **)v34 + 34), (unsigned __int64 *)BitNumber) )
        {
          v14 = i;
          if ( !i )
            break;
          if ( RtlTestBit(v11 + 16, BitNumber[0]) )
          {
            v36 = 1;
            LODWORD(v37) = 48;
            v5 = SP_DRIVE::Control(v14[1], 0x2D2828u, &v36, 0x30u, &v36, 0x30u);
            if ( v5 < 0 )
              goto LABEL_49;
            MdlAddress = DWORD1(v37);
            if ( LODWORD(MasterIrp->MdlAddress) > DWORD1(v37) )
              MdlAddress = (int)MasterIrp->MdlAddress;
            MdlAddress_high = HIDWORD(MasterIrp->MdlAddress);
            LODWORD(MasterIrp->MdlAddress) = MdlAddress;
            v17 = DWORD2(v37);
            if ( MdlAddress_high > DWORD2(v37) )
              v17 = MdlAddress_high;
            Flags = MasterIrp->Flags;
            HIDWORD(MasterIrp->MdlAddress) = v17;
            v19 = HIDWORD(v37);
            if ( Flags > HIDWORD(v37) )
              v19 = Flags;
            v20 = *(&MasterIrp->Flags + 1);
            MasterIrp->Flags = v19;
            v21 = *(_DWORD *)v38;
            if ( v20 > *(_DWORD *)v38 )
              v21 = v20;
            IrpCount = MasterIrp->AssociatedIrp.IrpCount;
            *(&MasterIrp->Flags + 1) = v21;
            v23 = *(_DWORD *)&v38[4];
            if ( IrpCount < *(_DWORD *)&v38[4] )
              v23 = IrpCount;
            SystemBuffer_high = HIDWORD(MasterIrp->AssociatedIrp.SystemBuffer);
            MasterIrp->AssociatedIrp.IrpCount = v23;
            v25 = *(_DWORD *)&v38[8];
            if ( SystemBuffer_high > *(_DWORD *)&v38[8] )
              v25 = SystemBuffer_high;
            Flink = (unsigned int)MasterIrp->ThreadListEntry.Flink;
            HIDWORD(MasterIrp->AssociatedIrp.SystemBuffer) = v25;
            v27 = *(_DWORD *)&v38[12];
            if ( Flink < *(_DWORD *)&v38[12] )
              v27 = Flink;
            Flink_high = HIDWORD(MasterIrp->ThreadListEntry.Flink);
            LODWORD(MasterIrp->ThreadListEntry.Flink) = v27;
            v29 = *(_DWORD *)&v38[16];
            if ( Flink_high < *(_DWORD *)&v38[16] )
              v29 = Flink_high;
            Blink = (unsigned int)MasterIrp->ThreadListEntry.Blink;
            HIDWORD(MasterIrp->ThreadListEntry.Flink) = v29;
            v31 = *(_DWORD *)&v38[20];
            if ( Blink > *(_DWORD *)&v38[20] )
              v31 = Blink;
            Blink_high = HIDWORD(MasterIrp->ThreadListEntry.Blink);
            LODWORD(MasterIrp->ThreadListEntry.Blink) = v31;
            v33 = *(_DWORD *)&v38[24];
            if ( Blink_high < *(_DWORD *)&v38[24] )
              v33 = Blink_high;
            HIDWORD(MasterIrp->ThreadListEntry.Blink) = v33;
          }
          v34 = SIO_SPACE::GetTopLevel((SIO_SPACE *)v11);
        }
        a2->IoStatus.Information = 48;
      }
      else
      {
        a2->IoStatus.Information = Length;
        v5 = -2147483643;
      }
LABEL_49:
      ExReleaseRundownProtectionCacheAware(this[30]);
    }
    if ( v5 < 0 && v5 != -2147483643 && v5 != -1073741789 )
      goto LABEL_53;
  }
  else
  {
    v5 = -1073741789;
  }
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v7 = "Exit ";
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v7,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140033c50  mov     [rsp-28h+arg_10], rbx
0x140033c55  mov     [rsp-28h+arg_18], rsi
0x140033c5a  push    rbp
0x140033c5b  push    rdi
0x140033c5c  push    r13
0x140033c5e  push    r14
0x140033c60  push    r15
0x140033c62  mov     rbp, rsp
0x140033c65  sub     rsp, 70h
0x140033c69  mov     rax, cs:__security_cookie
0x140033c70  xor     rax, rsp
0x140033c73  mov     [rbp+var_8], rax
0x140033c77  mov     r14, [rdx+0B8h]
0x140033c7e  xorps   xmm0, xmm0
0x140033c81  movups  [rbp+var_24], xmm0
0x140033c85  mov     rsi, rdx
0x140033c88  mov     r15, rcx
0x140033c8b  movups  [rbp+var_24+0Ch], xmm0
0x140033c8f  mov     qword ptr [rbp+BitNumber], 0
0x140033c97  mov     [rbp+var_38], 0
0x140033c9e  movups  [rbp+var_34], xmm0
0x140033ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140033ca9  lea     rdi, WPP_GLOBAL_Control
0x140033cb0  cmp     rcx, rdi
0x140033cb3  jz      short loc_140033CD7
0x140033cb5  mov     eax, [rcx+2Ch]
0x140033cb8  test    al, 1
0x140033cba  jz      short loc_140033CD7
0x140033cbc  cmp     byte ptr [rcx+29h], 3
0x140033cc0  jb      short loc_140033CD7
0x140033cc2  mov     rcx, [rcx+18h]
0x140033cc6  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140033ccd  mov     edx, 0Eh
0x140033cd2  call    WPP_SF_
0x140033cd7  cmp     dword ptr [r14+10h], 8
0x140033cdc  jnb     short loc_140033CE8
0x140033cde  mov     ebx, 0C0000004h
0x140033ce3  jmp     loc_140033F55
0x140033ce8  mov     rax, [rsi+18h]
0x140033cec  cmp     dword ptr [rax], 1
0x140033cef  jz      short loc_140033CFB
0x140033cf1  mov     ebx, 0C000000Dh
0x140033cf6  jmp     loc_140033F55
0x140033cfb  cmp     dword ptr [r14+8], 8
0x140033d00  jnb     loc_140033D86
0x140033d06  mov     ebx, 0C0000023h
0x140033d0b  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140033d11  cmp     ecx, 3
0x140033d14  jz      short loc_140033D21
0x140033d16  mov     ecx, 3
0x140033d1b  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140033d21  lea     r9, aExit; "Exit "
0x140033d28  mov     r10, cs:WPP_GLOBAL_Control
0x140033d2f  cmp     r10, rdi
0x140033d32  jz      short loc_140033D5E
0x140033d34  mov     eax, [r10+2Ch]
0x140033d38  test    al, 1
0x140033d3a  jz      short loc_140033D5E
0x140033d3c  movzx   eax, byte ptr [r10+29h]
0x140033d41  cmp     eax, ecx
0x140033d43  jb      short loc_140033D5E
0x140033d45  mov     rcx, [r10+18h]
0x140033d49  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140033d50  mov     edx, 0Fh
0x140033d55  mov     dword ptr [rsp+70h+var_50], ebx
0x140033d59  call    WPP_SF_sd
0x140033d5e  mov     eax, ebx
0x140033d60  mov     rcx, [rbp+var_8]
0x140033d64  xor     rcx, rsp; StackCookie
0x140033d67  call    __security_check_cookie
0x140033d6c  lea     r11, [rsp+70h+var_s0]
0x140033d71  mov     rbx, [r11+40h]
0x140033d75  mov     rsi, [r11+48h]
0x140033d79  mov     rsp, r11
0x140033d7c  pop     r15
0x140033d7e  pop     r14
0x140033d80  pop     r13
0x140033d82  pop     rdi
0x140033d83  pop     rbp
0x140033d84  retn
0x140033d86  mov     rdx, rsi; struct _IRP *
0x140033d89  mov     rcx, r15; this
0x140033d8c  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x140033d91  mov     ebx, eax
0x140033d93  test    eax, eax
0x140033d95  jnz     loc_140033F35
0x140033d9b  mov     rdi, [rsi+18h]
0x140033d9f  xor     edx, edx; Val
0x140033da1  mov     r14d, [r14+8]
0x140033da5  mov     rcx, rdi; void *
0x140033da8  mov     r8d, r14d; Size
0x140033dab  call    memset
0x140033db0  mov     dword ptr [rdi], 1
0x140033db6  mov     dword ptr [rdi+4], 30h ; '0'
0x140033dbd  cmp     r14d, 30h ; '0'
0x140033dc1  jnb     short loc_140033DD1
0x140033dc3  mov     [rsi+38h], r14
0x140033dc7  mov     ebx, 80000005h
0x140033dcc  jmp     loc_140033F1B
0x140033dd1  or      eax, 0FFFFFFFFh
0x140033dd4  mov     [rdi+18h], eax
0x140033dd7  mov     [rdi+20h], eax
0x140033dda  mov     [rdi+24h], eax
0x140033ddd  mov     [rdi+2Ch], eax
0x140033de0  mov     r13, [r15+0C98h]
0x140033de7  mov     rcx, r13; this
0x140033dea  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x140033def  lea     rdx, [rbp+BitNumber]; unsigned __int64 *
0x140033df3  mov     rcx, [rax+110h]; this
0x140033dfa  call    ?FindFirstObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindFirstObject(unsigned __int64 *)
0x140033dff  mov     r14, rax
0x140033e02  test    rax, rax
0x140033e05  jz      loc_140033F13
0x140033e0b  mov     edx, [rbp+BitNumber]; BitNumber
0x140033e0e  lea     rcx, [r13+100h]; BitMapHeader
0x140033e15  call    cs:__imp_RtlTestBit
0x140033e1c  nop     dword ptr [rax+rax+00h]
0x140033e21  test    al, al
0x140033e23  jz      loc_140033EF6
0x140033e29  mov     [rbp+var_38], 1
0x140033e30  lea     rax, [rbp+var_38]
0x140033e34  mov     dword ptr [rbp+var_34], 30h ; '0'
0x140033e3b  lea     r8, [rbp+var_38]; void *
0x140033e3f  mov     rcx, [r14+8]; this
0x140033e43  mov     r9d, 30h ; '0'; unsigned int
0x140033e49  mov     [rsp+70h+var_48], 30h ; '0'; ULONG
0x140033e51  mov     edx, 2D2828h; unsigned int
0x140033e56  mov     [rsp+70h+var_50], rax; PVOID
0x140033e5b  call    ?Control@SP_DRIVE@@UEAAJKPEAXK0K@Z; SP_DRIVE::Control(ulong,void *,ulong,void *,ulong)
0x140033e60  mov     ebx, eax
0x140033e62  test    eax, eax
0x140033e64  js      loc_140033F1B
0x140033e6a  mov     ecx, dword ptr [rbp+var_34+4]
0x140033e6d  mov     eax, [rdi+8]
0x140033e70  cmp     eax, ecx
0x140033e72  cmova   ecx, eax
0x140033e75  mov     eax, [rdi+0Ch]
0x140033e78  mov     [rdi+8], ecx
0x140033e7b  mov     ecx, dword ptr [rbp+var_34+8]
0x140033e7e  cmp     eax, ecx
0x140033e80  cmova   ecx, eax
0x140033e83  mov     eax, [rdi+10h]
0x140033e86  mov     [rdi+0Ch], ecx
0x140033e89  mov     ecx, dword ptr [rbp+var_34+0Ch]
0x140033e8c  cmp     eax, ecx
0x140033e8e  cmova   ecx, eax
0x140033e91  mov     eax, [rdi+14h]
0x140033e94  mov     [rdi+10h], ecx
0x140033e97  mov     ecx, dword ptr [rbp+var_24]
0x140033e9a  cmp     eax, ecx
0x140033e9c  cmova   ecx, eax
0x140033e9f  mov     eax, [rdi+18h]
0x140033ea2  mov     [rdi+14h], ecx
0x140033ea5  mov     ecx, dword ptr [rbp+var_24+4]
0x140033ea8  cmp     eax, ecx
0x140033eaa  cmovb   ecx, eax
0x140033ead  mov     eax, [rdi+1Ch]
0x140033eb0  mov     [rdi+18h], ecx
0x140033eb3  mov     ecx, dword ptr [rbp+var_24+8]
0x140033eb6  cmp     eax, ecx
0x140033eb8  cmova   ecx, eax
0x140033ebb  mov     eax, [rdi+20h]
0x140033ebe  mov     [rdi+1Ch], ecx
0x140033ec1  mov     ecx, dword ptr [rbp+var_24+0Ch]
0x140033ec4  cmp     eax, ecx
0x140033ec6  cmovb   ecx, eax
0x140033ec9  mov     eax, [rdi+24h]
0x140033ecc  mov     [rdi+20h], ecx
0x140033ecf  mov     ecx, [rbp+var_14]
0x140033ed2  cmp     eax, ecx
0x140033ed4  cmovb   ecx, eax
0x140033ed7  mov     eax, [rdi+28h]
0x140033eda  mov     [rdi+24h], ecx
0x140033edd  mov     ecx, [rbp+var_10]
0x140033ee0  cmp     eax, ecx
0x140033ee2  cmova   ecx, eax
0x140033ee5  mov     eax, [rdi+2Ch]
0x140033ee8  mov     [rdi+28h], ecx
0x140033eeb  mov     ecx, [rbp+var_C]
0x140033eee  cmp     eax, ecx
0x140033ef0  cmovb   ecx, eax
0x140033ef3  mov     [rdi+2Ch], ecx
0x140033ef6  mov     rcx, r13; this
0x140033ef9  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x140033efe  lea     rdx, [rbp+BitNumber]; unsigned __int64 *
0x140033f02  mov     rcx, [rax+110h]; this
0x140033f09  call    ?FindNextObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindNextObject(unsigned __int64 *)
0x140033f0e  jmp     loc_140033DFF
0x140033f13  mov     qword ptr [rsi+38h], 30h ; '0'
0x140033f1b  mov     rcx, [r15+0F0h]; RunRefCacheAware
0x140033f22  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140033f29  nop     dword ptr [rax+rax+00h]
0x140033f2e  lea     rdi, WPP_GLOBAL_Control
0x140033f35  test    ebx, ebx
0x140033f37  jns     loc_140033D0B
0x140033f3d  cmp     ebx, 80000005h
0x140033f43  jz      loc_140033D0B
0x140033f49  cmp     ebx, 0C0000023h
0x140033f4f  jz      loc_140033D0B
0x140033f55  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140033f5b  cmp     ecx, 1
0x140033f5e  jz      short loc_140033F6B
0x140033f60  mov     ecx, 1
0x140033f65  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140033f6b  lea     r9, aError; "Error"
0x140033f72  jmp     loc_140033D28
```
