# SpReleaseStreamId(SP_DEVICE *,_IRP *)

- ea: `0x140034898`
- end: `0x140034a64`
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
- `0x140034898`
- `0x1400b68c0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400349bb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400349bb`
- `ntoskrnl!RtlTestBit` at `0x140034956`
- `ntoskrnl!RtlTestBit` at `0x140034956`

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
0x140034898  push    rbx
0x14003489a  push    rbp
0x14003489b  push    rsi
0x14003489c  push    rdi
0x14003489d  push    r14
0x14003489f  push    r15
0x1400348a1  sub     rsp, 38h
0x1400348a5  mov     rsi, [rdx+0B8h]
0x1400348ac  mov     rbx, rdx
0x1400348af  mov     rdi, rcx
0x1400348b2  mov     [rsp+68h+BitNumber], 0
0x1400348bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400348c2  lea     rbp, WPP_GLOBAL_Control
0x1400348c9  cmp     rcx, rbp
0x1400348cc  jz      short loc_1400348F0
0x1400348ce  mov     eax, [rcx+2Ch]
0x1400348d1  test    al, 1
0x1400348d3  jz      short loc_1400348F0
0x1400348d5  cmp     byte ptr [rcx+29h], 3
0x1400348d9  jb      short loc_1400348F0
0x1400348db  mov     rcx, [rcx+18h]
0x1400348df  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400348e6  mov     edx, 10h
0x1400348eb  call    WPP_SF_
0x1400348f0  cmp     dword ptr [rsi+10h], 0Ch
0x1400348f4  jnb     short loc_140034900
0x1400348f6  mov     ebx, 0C0000004h
0x1400348fb  jmp     loc_1400349E2
0x140034900  mov     r14, [rbx+18h]
0x140034904  cmp     dword ptr [r14], 1
0x140034908  jz      short loc_140034914
0x14003490a  mov     ebx, 0C000000Dh
0x14003490f  jmp     loc_1400349E2
0x140034914  mov     rdx, rbx; struct _IRP *
0x140034917  mov     rcx, rdi; this
0x14003491a  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x14003491f  mov     ebx, eax
0x140034921  test    eax, eax
0x140034923  jnz     loc_1400349CE
0x140034929  mov     rsi, [rdi+0C98h]
0x140034930  mov     rcx, rsi; this
0x140034933  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x140034938  lea     rdx, [rsp+68h+BitNumber]; unsigned __int64 *
0x14003493d  mov     rcx, [rax+110h]; this
0x140034944  call    ?FindFirstObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindFirstObject(unsigned __int64 *)
0x140034949  jmp     short loc_1400349AC
0x14003494b  mov     edx, dword ptr [rsp+68h+BitNumber]; BitNumber
0x14003494f  lea     rcx, [rsi+100h]; BitMapHeader
0x140034956  call    cs:__imp_RtlTestBit
0x14003495d  nop     dword ptr [rax+rax+00h]
0x140034962  test    al, al
0x140034964  jz      short loc_140034993
0x140034966  mov     rcx, [rbp+8]; this
0x14003496a  mov     r9d, 0Ch; unsigned int
0x140034970  mov     [rsp+68h+var_40], 0; ULONG
0x140034978  mov     r8, r14; void *
0x14003497b  mov     edx, 2D2830h; unsigned int
0x140034980  mov     [rsp+68h+var_48], 0; PVOID
0x140034989  call    ?Control@SP_DRIVE@@UEAAJKPEAXK0K@Z; SP_DRIVE::Control(ulong,void *,ulong,void *,ulong)
0x14003498e  test    eax, eax
0x140034990  cmovs   ebx, eax
0x140034993  mov     rcx, rsi; this
0x140034996  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x14003499b  lea     rdx, [rsp+68h+BitNumber]; unsigned __int64 *
0x1400349a0  mov     rcx, [rax+110h]; this
0x1400349a7  call    ?FindNextObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindNextObject(unsigned __int64 *)
0x1400349ac  mov     rbp, rax
0x1400349af  test    rax, rax
0x1400349b2  jnz     short loc_14003494B
0x1400349b4  mov     rcx, [rdi+0F0h]; RunRefCacheAware
0x1400349bb  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400349c2  nop     dword ptr [rax+rax+00h]
0x1400349c7  lea     rbp, WPP_GLOBAL_Control
0x1400349ce  test    ebx, ebx
0x1400349d0  jns     short loc_140034A01
0x1400349d2  cmp     ebx, 80000005h
0x1400349d8  jz      short loc_140034A01
0x1400349da  cmp     ebx, 0C0000023h
0x1400349e0  jz      short loc_140034A01
0x1400349e2  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400349e8  cmp     ecx, 1
0x1400349eb  jz      short loc_1400349F8
0x1400349ed  mov     ecx, 1
0x1400349f2  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400349f8  lea     r9, aError; "Error"
0x1400349ff  jmp     short loc_140034A1E
0x140034a01  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140034a07  cmp     ecx, 3
0x140034a0a  jz      short loc_140034A17
0x140034a0c  mov     ecx, 3
0x140034a11  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140034a17  lea     r9, aExit; "Exit "
0x140034a1e  mov     r10, cs:WPP_GLOBAL_Control
0x140034a25  cmp     r10, rbp
0x140034a28  jz      short loc_140034A54
0x140034a2a  mov     eax, [r10+2Ch]
0x140034a2e  test    al, 1
0x140034a30  jz      short loc_140034A54
0x140034a32  movzx   eax, byte ptr [r10+29h]
0x140034a37  cmp     eax, ecx
0x140034a39  jb      short loc_140034A54
0x140034a3b  mov     rcx, [r10+18h]
0x140034a3f  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140034a46  mov     edx, 11h
0x140034a4b  mov     dword ptr [rsp+68h+var_48], ebx
0x140034a4f  call    WPP_SF_sd
0x140034a54  mov     eax, ebx
0x140034a56  add     rsp, 38h
0x140034a5a  pop     r15
0x140034a5c  pop     r14
0x140034a5e  pop     rdi
0x140034a5f  pop     rsi
0x140034a60  pop     rbp
0x140034a61  pop     rbx
0x140034a62  retn
```
