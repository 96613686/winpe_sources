# SpReleaseStreamId(SP_DEVICE *,_IRP *)

- ea: `0x1400347d8`
- end: `0x1400349a4`
- name: `?SpReleaseStreamId@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct SP_DEVICE *this, struct _IRP *)`
- caller_count: `1`
- callee_count: `8`
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
- `0x1400347d8`
- `0x1400b6720`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400348fb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400348fb`
- `ntoskrnl!RtlTestBit` at `0x140034896`
- `ntoskrnl!RtlTestBit` at `0x140034896`

## pseudocode

```c
__int64 __fastcall SpReleaseStreamId(PEX_RUNDOWN_REF_CACHE_AWARE *this, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int v5; // ebx
  struct _IRP *MasterIrp; // r14
  struct _RTL_BITMAP *v7; // rsi
  struct SIO_SPACE *TopLevel; // rax
  SP_DRIVE **i; // rax
  int v10; // eax
  struct SIO_SPACE *v11; // rax
  SP_DRIVE **v12; // rbp
  ULONG DeviceType; // ecx
  const char *v14; // r9
  unsigned __int64 BitNumber; // [rsp+78h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  BitNumber = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids);
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0xC )
  {
    v5 = -1073741820;
LABEL_20:
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v14 = "Error";
    goto LABEL_26;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 1 )
  {
    v5 = -1073741811;
    goto LABEL_20;
  }
  v5 = SP_DEVICE::AcquireRundownShared((SP_DEVICE *)this, a2);
  if ( !v5 )
  {
    v7 = (struct _RTL_BITMAP *)this[403];
    TopLevel = SIO_SPACE::GetTopLevel((SIO_SPACE *)v7);
    for ( i = (SP_DRIVE **)SC_SPARSE::FindFirstObject(*((SC_SPARSE **)TopLevel + 34), &BitNumber);
          ;
          i = (SP_DRIVE **)SC_SPARSE::FindNextObject(*((SC_SPARSE **)v11 + 34), &BitNumber) )
    {
      v12 = i;
      if ( !i )
        break;
      if ( RtlTestBit(v7 + 16, BitNumber) )
      {
        v10 = SP_DRIVE::Control(v12[1], 0x2D2830u, MasterIrp, 0xCu, 0, 0);
        if ( v10 < 0 )
          v5 = v10;
      }
      v11 = SIO_SPACE::GetTopLevel((SIO_SPACE *)v7);
    }
    ExReleaseRundownProtectionCacheAware(this[30]);
  }
  if ( v5 < 0 && v5 != -2147483643 && v5 != -1073741789 )
    goto LABEL_20;
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v14 = "Exit ";
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v14,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400347d8  push    rbx
0x1400347da  push    rbp
0x1400347db  push    rsi
0x1400347dc  push    rdi
0x1400347dd  push    r14
0x1400347df  push    r15
0x1400347e1  sub     rsp, 38h
0x1400347e5  mov     rsi, [rdx+0B8h]
0x1400347ec  mov     rbx, rdx
0x1400347ef  mov     rdi, rcx
0x1400347f2  mov     [rsp+68h+BitNumber], 0
0x1400347fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140034802  lea     rbp, WPP_GLOBAL_Control
0x140034809  cmp     rcx, rbp
0x14003480c  jz      short loc_140034830
0x14003480e  mov     eax, [rcx+2Ch]
0x140034811  test    al, 1
0x140034813  jz      short loc_140034830
0x140034815  cmp     byte ptr [rcx+29h], 3
0x140034819  jb      short loc_140034830
0x14003481b  mov     rcx, [rcx+18h]
0x14003481f  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140034826  mov     edx, 10h
0x14003482b  call    WPP_SF_
0x140034830  cmp     dword ptr [rsi+10h], 0Ch
0x140034834  jnb     short loc_140034840
0x140034836  mov     ebx, 0C0000004h
0x14003483b  jmp     loc_140034922
0x140034840  mov     r14, [rbx+18h]
0x140034844  cmp     dword ptr [r14], 1
0x140034848  jz      short loc_140034854
0x14003484a  mov     ebx, 0C000000Dh
0x14003484f  jmp     loc_140034922
0x140034854  mov     rdx, rbx; struct _IRP *
0x140034857  mov     rcx, rdi; this
0x14003485a  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x14003485f  mov     ebx, eax
0x140034861  test    eax, eax
0x140034863  jnz     loc_14003490E
0x140034869  mov     rsi, [rdi+0C98h]
0x140034870  mov     rcx, rsi; this
0x140034873  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x140034878  lea     rdx, [rsp+68h+BitNumber]; unsigned __int64 *
0x14003487d  mov     rcx, [rax+110h]; this
0x140034884  call    ?FindFirstObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindFirstObject(unsigned __int64 *)
0x140034889  jmp     short loc_1400348EC
0x14003488b  mov     edx, dword ptr [rsp+68h+BitNumber]; BitNumber
0x14003488f  lea     rcx, [rsi+100h]; BitMapHeader
0x140034896  call    cs:__imp_RtlTestBit
0x14003489d  nop     dword ptr [rax+rax+00h]
0x1400348a2  test    al, al
0x1400348a4  jz      short loc_1400348D3
0x1400348a6  mov     rcx, [rbp+8]; this
0x1400348aa  mov     r9d, 0Ch; unsigned int
0x1400348b0  mov     [rsp+68h+var_40], 0; ULONG
0x1400348b8  mov     r8, r14; void *
0x1400348bb  mov     edx, 2D2830h; unsigned int
0x1400348c0  mov     [rsp+68h+var_48], 0; PVOID
0x1400348c9  call    ?Control@SP_DRIVE@@UEAAJKPEAXK0K@Z; SP_DRIVE::Control(ulong,void *,ulong,void *,ulong)
0x1400348ce  test    eax, eax
0x1400348d0  cmovs   ebx, eax
0x1400348d3  mov     rcx, rsi; this
0x1400348d6  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x1400348db  lea     rdx, [rsp+68h+BitNumber]; unsigned __int64 *
0x1400348e0  mov     rcx, [rax+110h]; this
0x1400348e7  call    ?FindNextObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindNextObject(unsigned __int64 *)
0x1400348ec  mov     rbp, rax
0x1400348ef  test    rax, rax
0x1400348f2  jnz     short loc_14003488B
0x1400348f4  mov     rcx, [rdi+0F0h]; RunRefCacheAware
0x1400348fb  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140034902  nop     dword ptr [rax+rax+00h]
0x140034907  lea     rbp, WPP_GLOBAL_Control
0x14003490e  test    ebx, ebx
0x140034910  jns     short loc_140034941
0x140034912  cmp     ebx, 80000005h
0x140034918  jz      short loc_140034941
0x14003491a  cmp     ebx, 0C0000023h
0x140034920  jz      short loc_140034941
0x140034922  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140034928  cmp     ecx, 1
0x14003492b  jz      short loc_140034938
0x14003492d  mov     ecx, 1
0x140034932  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140034938  lea     r9, aError; "Error"
0x14003493f  jmp     short loc_14003495E
0x140034941  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140034947  cmp     ecx, 3
0x14003494a  jz      short loc_140034957
0x14003494c  mov     ecx, 3
0x140034951  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140034957  lea     r9, aExit; "Exit "
0x14003495e  mov     r10, cs:WPP_GLOBAL_Control
0x140034965  cmp     r10, rbp
0x140034968  jz      short loc_140034994
0x14003496a  mov     eax, [r10+2Ch]
0x14003496e  test    al, 1
0x140034970  jz      short loc_140034994
0x140034972  movzx   eax, byte ptr [r10+29h]
0x140034977  cmp     eax, ecx
0x140034979  jb      short loc_140034994
0x14003497b  mov     rcx, [r10+18h]
0x14003497f  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140034986  mov     edx, 11h
0x14003498b  mov     dword ptr [rsp+68h+var_48], ebx
0x14003498f  call    WPP_SF_sd
0x140034994  mov     eax, ebx
0x140034996  add     rsp, 38h
0x14003499a  pop     r15
0x14003499c  pop     r14
0x14003499e  pop     rdi
0x14003499f  pop     rsi
0x1400349a0  pop     rbp
0x1400349a1  pop     rbx
0x1400349a2  retn
```
