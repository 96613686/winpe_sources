# SpGetStreamParameters(SP_DEVICE *,_IRP *)

- ea: `0x140033d00`
- end: `0x140034027`
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
- `0x140033d00`
- `0x140068110`
- `0x140068600`
- `0x1400b68c0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140033fd2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140033fd2`
- `ntoskrnl!RtlTestBit` at `0x140033ec5`
- `ntoskrnl!RtlTestBit` at `0x140033ec5`

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
0x140033d00  mov     [rsp-28h+arg_10], rbx
0x140033d05  mov     [rsp-28h+arg_18], rsi
0x140033d0a  push    rbp
0x140033d0b  push    rdi
0x140033d0c  push    r13
0x140033d0e  push    r14
0x140033d10  push    r15
0x140033d12  mov     rbp, rsp
0x140033d15  sub     rsp, 70h
0x140033d19  mov     rax, cs:__security_cookie
0x140033d20  xor     rax, rsp
0x140033d23  mov     [rbp+var_8], rax
0x140033d27  mov     r14, [rdx+0B8h]
0x140033d2e  xorps   xmm0, xmm0
0x140033d31  movups  [rbp+var_24], xmm0
0x140033d35  mov     rsi, rdx
0x140033d38  mov     r15, rcx
0x140033d3b  movups  [rbp+var_24+0Ch], xmm0
0x140033d3f  mov     qword ptr [rbp+BitNumber], 0
0x140033d47  mov     [rbp+var_38], 0
0x140033d4e  movups  [rbp+var_34], xmm0
0x140033d52  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d59  lea     rdi, WPP_GLOBAL_Control
0x140033d60  cmp     rcx, rdi
0x140033d63  jz      short loc_140033D87
0x140033d65  mov     eax, [rcx+2Ch]
0x140033d68  test    al, 1
0x140033d6a  jz      short loc_140033D87
0x140033d6c  cmp     byte ptr [rcx+29h], 3
0x140033d70  jb      short loc_140033D87
0x140033d72  mov     rcx, [rcx+18h]
0x140033d76  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140033d7d  mov     edx, 0Eh
0x140033d82  call    WPP_SF_
0x140033d87  cmp     dword ptr [r14+10h], 8
0x140033d8c  jnb     short loc_140033D98
0x140033d8e  mov     ebx, 0C0000004h
0x140033d93  jmp     loc_140034005
0x140033d98  mov     rax, [rsi+18h]
0x140033d9c  cmp     dword ptr [rax], 1
0x140033d9f  jz      short loc_140033DAB
0x140033da1  mov     ebx, 0C000000Dh
0x140033da6  jmp     loc_140034005
0x140033dab  cmp     dword ptr [r14+8], 8
0x140033db0  jnb     loc_140033E36
0x140033db6  mov     ebx, 0C0000023h
0x140033dbb  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140033dc1  cmp     ecx, 3
0x140033dc4  jz      short loc_140033DD1
0x140033dc6  mov     ecx, 3
0x140033dcb  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140033dd1  lea     r9, aExit; "Exit "
0x140033dd8  mov     r10, cs:WPP_GLOBAL_Control
0x140033ddf  cmp     r10, rdi
0x140033de2  jz      short loc_140033E0E
0x140033de4  mov     eax, [r10+2Ch]
0x140033de8  test    al, 1
0x140033dea  jz      short loc_140033E0E
0x140033dec  movzx   eax, byte ptr [r10+29h]
0x140033df1  cmp     eax, ecx
0x140033df3  jb      short loc_140033E0E
0x140033df5  mov     rcx, [r10+18h]
0x140033df9  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140033e00  mov     edx, 0Fh
0x140033e05  mov     dword ptr [rsp+70h+var_50], ebx
0x140033e09  call    WPP_SF_sd
0x140033e0e  mov     eax, ebx
0x140033e10  mov     rcx, [rbp+var_8]
0x140033e14  xor     rcx, rsp; StackCookie
0x140033e17  call    __security_check_cookie
0x140033e1c  lea     r11, [rsp+70h+var_s0]
0x140033e21  mov     rbx, [r11+40h]
0x140033e25  mov     rsi, [r11+48h]
0x140033e29  mov     rsp, r11
0x140033e2c  pop     r15
0x140033e2e  pop     r14
0x140033e30  pop     r13
0x140033e32  pop     rdi
0x140033e33  pop     rbp
0x140033e34  retn
0x140033e36  mov     rdx, rsi; struct _IRP *
0x140033e39  mov     rcx, r15; this
0x140033e3c  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x140033e41  mov     ebx, eax
0x140033e43  test    eax, eax
0x140033e45  jnz     loc_140033FE5
0x140033e4b  mov     rdi, [rsi+18h]
0x140033e4f  xor     edx, edx; Val
0x140033e51  mov     r14d, [r14+8]
0x140033e55  mov     rcx, rdi; void *
0x140033e58  mov     r8d, r14d; Size
0x140033e5b  call    memset
0x140033e60  mov     dword ptr [rdi], 1
0x140033e66  mov     dword ptr [rdi+4], 30h ; '0'
0x140033e6d  cmp     r14d, 30h ; '0'
0x140033e71  jnb     short loc_140033E81
0x140033e73  mov     [rsi+38h], r14
0x140033e77  mov     ebx, 80000005h
0x140033e7c  jmp     loc_140033FCB
0x140033e81  or      eax, 0FFFFFFFFh
0x140033e84  mov     [rdi+18h], eax
0x140033e87  mov     [rdi+20h], eax
0x140033e8a  mov     [rdi+24h], eax
0x140033e8d  mov     [rdi+2Ch], eax
0x140033e90  mov     r13, [r15+0C98h]
0x140033e97  mov     rcx, r13; this
0x140033e9a  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x140033e9f  lea     rdx, [rbp+BitNumber]; unsigned __int64 *
0x140033ea3  mov     rcx, [rax+110h]; this
0x140033eaa  call    ?FindFirstObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindFirstObject(unsigned __int64 *)
0x140033eaf  mov     r14, rax
0x140033eb2  test    rax, rax
0x140033eb5  jz      loc_140033FC3
0x140033ebb  mov     edx, [rbp+BitNumber]; BitNumber
0x140033ebe  lea     rcx, [r13+100h]; BitMapHeader
0x140033ec5  call    cs:__imp_RtlTestBit
0x140033ecc  nop     dword ptr [rax+rax+00h]
0x140033ed1  test    al, al
0x140033ed3  jz      loc_140033FA6
0x140033ed9  mov     [rbp+var_38], 1
0x140033ee0  lea     rax, [rbp+var_38]
0x140033ee4  mov     dword ptr [rbp+var_34], 30h ; '0'
0x140033eeb  lea     r8, [rbp+var_38]; void *
0x140033eef  mov     rcx, [r14+8]; this
0x140033ef3  mov     r9d, 30h ; '0'; unsigned int
0x140033ef9  mov     [rsp+70h+var_48], 30h ; '0'; ULONG
0x140033f01  mov     edx, 2D2828h; unsigned int
0x140033f06  mov     [rsp+70h+var_50], rax; PVOID
0x140033f0b  call    ?Control@SP_DRIVE@@UEAAJKPEAXK0K@Z; SP_DRIVE::Control(ulong,void *,ulong,void *,ulong)
0x140033f10  mov     ebx, eax
0x140033f12  test    eax, eax
0x140033f14  js      loc_140033FCB
0x140033f1a  mov     ecx, dword ptr [rbp+var_34+4]
0x140033f1d  mov     eax, [rdi+8]
0x140033f20  cmp     eax, ecx
0x140033f22  cmova   ecx, eax
0x140033f25  mov     eax, [rdi+0Ch]
0x140033f28  mov     [rdi+8], ecx
0x140033f2b  mov     ecx, dword ptr [rbp+var_34+8]
0x140033f2e  cmp     eax, ecx
0x140033f30  cmova   ecx, eax
0x140033f33  mov     eax, [rdi+10h]
0x140033f36  mov     [rdi+0Ch], ecx
0x140033f39  mov     ecx, dword ptr [rbp+var_34+0Ch]
0x140033f3c  cmp     eax, ecx
0x140033f3e  cmova   ecx, eax
0x140033f41  mov     eax, [rdi+14h]
0x140033f44  mov     [rdi+10h], ecx
0x140033f47  mov     ecx, dword ptr [rbp+var_24]
0x140033f4a  cmp     eax, ecx
0x140033f4c  cmova   ecx, eax
0x140033f4f  mov     eax, [rdi+18h]
0x140033f52  mov     [rdi+14h], ecx
0x140033f55  mov     ecx, dword ptr [rbp+var_24+4]
0x140033f58  cmp     eax, ecx
0x140033f5a  cmovb   ecx, eax
0x140033f5d  mov     eax, [rdi+1Ch]
0x140033f60  mov     [rdi+18h], ecx
0x140033f63  mov     ecx, dword ptr [rbp+var_24+8]
0x140033f66  cmp     eax, ecx
0x140033f68  cmova   ecx, eax
0x140033f6b  mov     eax, [rdi+20h]
0x140033f6e  mov     [rdi+1Ch], ecx
0x140033f71  mov     ecx, dword ptr [rbp+var_24+0Ch]
0x140033f74  cmp     eax, ecx
0x140033f76  cmovb   ecx, eax
0x140033f79  mov     eax, [rdi+24h]
0x140033f7c  mov     [rdi+20h], ecx
0x140033f7f  mov     ecx, [rbp+var_14]
0x140033f82  cmp     eax, ecx
0x140033f84  cmovb   ecx, eax
0x140033f87  mov     eax, [rdi+28h]
0x140033f8a  mov     [rdi+24h], ecx
0x140033f8d  mov     ecx, [rbp+var_10]
0x140033f90  cmp     eax, ecx
0x140033f92  cmova   ecx, eax
0x140033f95  mov     eax, [rdi+2Ch]
0x140033f98  mov     [rdi+28h], ecx
0x140033f9b  mov     ecx, [rbp+var_C]
0x140033f9e  cmp     eax, ecx
0x140033fa0  cmovb   ecx, eax
0x140033fa3  mov     [rdi+2Ch], ecx
0x140033fa6  mov     rcx, r13; this
0x140033fa9  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x140033fae  lea     rdx, [rbp+BitNumber]; unsigned __int64 *
0x140033fb2  mov     rcx, [rax+110h]; this
0x140033fb9  call    ?FindNextObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindNextObject(unsigned __int64 *)
0x140033fbe  jmp     loc_140033EAF
0x140033fc3  mov     qword ptr [rsi+38h], 30h ; '0'
0x140033fcb  mov     rcx, [r15+0F0h]; RunRefCacheAware
0x140033fd2  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140033fd9  nop     dword ptr [rax+rax+00h]
0x140033fde  lea     rdi, WPP_GLOBAL_Control
0x140033fe5  test    ebx, ebx
0x140033fe7  jns     loc_140033DBB
0x140033fed  cmp     ebx, 80000005h
0x140033ff3  jz      loc_140033DBB
0x140033ff9  cmp     ebx, 0C0000023h
0x140033fff  jz      loc_140033DBB
0x140034005  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14003400b  cmp     ecx, 1
0x14003400e  jz      short loc_14003401B
0x140034010  mov     ecx, 1
0x140034015  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14003401b  lea     r9, aError; "Error"
0x140034022  jmp     loc_140033DD8
```
