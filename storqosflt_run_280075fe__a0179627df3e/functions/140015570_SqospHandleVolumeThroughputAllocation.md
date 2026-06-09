# SqospHandleVolumeThroughputAllocation

- ea: `0x140015570`
- end: `0x140015806`
- name: `SqospHandleVolumeThroughputAllocation`
- size: `662`
- prototype: `__int64 __fastcall(PVOID VirtualAddress, ULONG Length)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140012a70`

## callees

- `0x140004340`
- `0x140007344`
- `0x140007f00`
- `0x140008d20`
- `0x140009240`
- `0x140015570`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x1400157ab`
- `ntoskrnl!MmUnlockPages` at `0x1400157ab`
- `ntoskrnl!MmProbeAndLockPages` at `0x140015725`
- `ntoskrnl!MmProbeAndLockPages` at `0x140015725`
- `ntoskrnl!IoAllocateMdl` at `0x140015704`
- `ntoskrnl!IoAllocateMdl` at `0x140015704`
- `ntoskrnl!IoFreeMdl` at `0x1400157ba`
- `ntoskrnl!IoFreeMdl` at `0x1400157ba`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001575d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001575d`
- `FLTMGR!FltReleaseContext` at `0x1400157ce`
- `FLTMGR!FltReleaseContext` at `0x1400157ce`

## pseudocode

```c
__int64 __fastcall SqospHandleVolumeThroughputAllocation(_OWORD *VirtualAddress, ULONG Length)
{
  __int64 v4; // r8
  void *DeviceByVolumeId; // rsi
  struct _MDL *v6; // rdi
  unsigned int v7; // ebx
  _OWORD *v8; // rax
  _OWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  struct _MDL *Mdl; // rax
  PVOID MappedSystemVa; // rax
  char v16; // [rsp+30h] [rbp-2A8h]
  _BYTE v17[600]; // [rsp+50h] [rbp-288h] BYREF

  memset(v17, 0, 0x256u);
  DeviceByVolumeId = 0;
  v6 = 0;
  v16 = 0;
  if ( Length < 0x258 )
    goto LABEL_2;
  v8 = VirtualAddress;
  v9 = v17;
  v10 = 4;
  do
  {
    *v9 = *v8;
    v9[1] = v8[1];
    v9[2] = v8[2];
    v9[3] = v8[3];
    v9[4] = v8[4];
    v9[5] = v8[5];
    v9[6] = v8[6];
    v9[7] = v8[7];
    v9 += 8;
    v8 += 8;
    --v10;
  }
  while ( v10 );
  *v9 = *v8;
  v9[1] = v8[1];
  v9[2] = v8[2];
  v9[3] = v8[3];
  v9[4] = v8[4];
  *((_QWORD *)v9 + 10) = *((_QWORD *)v8 + 10);
  v11 = 72LL * *(unsigned int *)&v17[596];
  if ( v11 > 0xFFFFFFFF
    || (v12 = (unsigned int)(v11 + *(_DWORD *)&v17[592]), (unsigned int)v12 < *(_DWORD *)&v17[592])
    || (unsigned int)v12 > Length )
  {
LABEL_2:
    v7 = -1073741811;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, v12, v4, &v17[528]);
    }
    DeviceByVolumeId = (void *)SqospFindDeviceByVolumeId(&v17[528]);
    if ( DeviceByVolumeId )
    {
      Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 0, 0);
      v6 = Mdl;
      if ( Mdl
        && ((MmProbeAndLockPages(Mdl, 0, IoReadAccess), v16 = 1, (v6->MdlFlags & 5) == 0)
          ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u))
          : (MappedSystemVa = v6->MappedSystemVa),
            MappedSystemVa) )
      {
        v7 = SqospAssignFlowIoRates(DeviceByVolumeId, MappedSystemVa);
      }
      else
      {
        v7 = -1073741670;
      }
    }
    else
    {
      v7 = -1073741275;
    }
  }
  if ( v6 )
  {
    if ( v16 )
      MmUnlockPages(v6);
    IoFreeMdl(v6);
  }
  if ( DeviceByVolumeId )
    FltReleaseContext(DeviceByVolumeId);
  return v7;
}

```

## disassembly

```asm
0x140015570  mov     [rsp+arg_10], rbx
0x140015575  mov     [rsp+arg_18], rsi
0x14001557a  push    rdi
0x14001557b  push    r14
0x14001557d  push    r15
0x14001557f  sub     rsp, 2C0h
0x140015586  mov     rax, cs:__security_cookie
0x14001558d  xor     rax, rsp
0x140015590  mov     [rsp+2D8h+var_28], rax
0x140015598  mov     ebx, edx
0x14001559a  mov     r14, rcx
0x14001559d  xor     eax, eax
0x14001559f  mov     [rsp+2D8h+var_286], ax
0x1400155a4  xor     edx, edx; Val
0x1400155a6  mov     r8d, 256h; Size
0x1400155ac  lea     rcx, [rsp+2D8h+var_288]; void *
0x1400155b1  call    memset
0x1400155b6  xor     r15d, r15d
0x1400155b9  mov     esi, r15d
0x1400155bc  mov     [rsp+2D8h+var_2A0], r15
0x1400155c1  mov     edi, r15d
0x1400155c4  mov     [rsp+2D8h+var_2A8], sil
0x1400155c9  cmp     ebx, 258h
0x1400155cf  jnb     short loc_1400155DB
0x1400155d1  mov     ebx, 0C000000Dh
0x1400155d6  jmp     loc_14001579C
0x1400155db  mov     rax, r14
0x1400155de  lea     rcx, [rsp+2D8h+var_288]
0x1400155e3  mov     edx, 4
0x1400155e8  movups  xmm0, xmmword ptr [rax]
0x1400155eb  movups  xmmword ptr [rcx], xmm0
0x1400155ee  movups  xmm1, xmmword ptr [rax+10h]
0x1400155f2  movups  xmmword ptr [rcx+10h], xmm1
0x1400155f6  movups  xmm0, xmmword ptr [rax+20h]
0x1400155fa  movups  xmmword ptr [rcx+20h], xmm0
0x1400155fe  movups  xmm1, xmmword ptr [rax+30h]
0x140015602  movups  xmmword ptr [rcx+30h], xmm1
0x140015606  movups  xmm0, xmmword ptr [rax+40h]
0x14001560a  movups  xmmword ptr [rcx+40h], xmm0
0x14001560e  movups  xmm1, xmmword ptr [rax+50h]
0x140015612  movups  xmmword ptr [rcx+50h], xmm1
0x140015616  movups  xmm0, xmmword ptr [rax+60h]
0x14001561a  movups  xmmword ptr [rcx+60h], xmm0
0x14001561e  movups  xmm1, xmmword ptr [rax+70h]
0x140015622  movups  xmmword ptr [rcx+70h], xmm1
0x140015626  lea     rcx, [rcx+80h]
0x14001562d  lea     rax, [rax+80h]
0x140015634  sub     rdx, 1
0x140015638  jnz     short loc_1400155E8
0x14001563a  movups  xmm0, xmmword ptr [rax]
0x14001563d  movups  xmmword ptr [rcx], xmm0
0x140015640  movups  xmm1, xmmword ptr [rax+10h]
0x140015644  movups  xmmword ptr [rcx+10h], xmm1
0x140015648  movups  xmm0, xmmword ptr [rax+20h]
0x14001564c  movups  xmmword ptr [rcx+20h], xmm0
0x140015650  movups  xmm1, xmmword ptr [rax+30h]
0x140015654  movups  xmmword ptr [rcx+30h], xmm1
0x140015658  movups  xmm0, xmmword ptr [rax+40h]
0x14001565c  movups  xmmword ptr [rcx+40h], xmm0
0x140015660  mov     rax, [rax+50h]
0x140015664  mov     [rcx+50h], rax
0x140015668  mov     eax, [rsp+2D8h+var_34]
0x14001566f  lea     rcx, [rax+rax*8]
0x140015673  shl     rcx, 3
0x140015677  mov     eax, 0FFFFFFFFh
0x14001567c  cmp     rcx, rax
0x14001567f  ja      loc_1400155D1
0x140015685  mov     eax, [rsp+2D8h+var_38]
0x14001568c  lea     edx, [rcx+rax]
0x14001568f  cmp     edx, eax
0x140015691  jb      loc_1400155D1
0x140015697  cmp     edx, ebx
0x140015699  ja      loc_1400155D1
0x14001569f  lea     rax, WPP_GLOBAL_Control
0x1400156a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156ad  cmp     rcx, rax
0x1400156b0  jz      short loc_1400156D0
0x1400156b2  mov     eax, [rcx+2Ch]
0x1400156b5  test    al, 40h
0x1400156b7  jz      short loc_1400156D0
0x1400156b9  cmp     byte ptr [rcx+29h], 4
0x1400156bd  jb      short loc_1400156D0
0x1400156bf  lea     r9, [rsp+2D8h+var_78]
0x1400156c7  mov     rcx, [rcx+18h]
0x1400156cb  call    WPP_SF__guid_
0x1400156d0  lea     rcx, [rsp+2D8h+var_78]
0x1400156d8  call    SqospFindDeviceByVolumeId
0x1400156dd  mov     rsi, rax
0x1400156e0  mov     [rsp+2D8h+var_2A0], rax
0x1400156e5  test    rax, rax
0x1400156e8  jnz     short loc_1400156F4
0x1400156ea  mov     ebx, 0C0000225h
0x1400156ef  jmp     loc_14001579C
0x1400156f4  mov     [rsp+2D8h+Irp], r15; Irp
0x1400156f9  xor     r9d, r9d; ChargeQuota
0x1400156fc  xor     r8d, r8d; SecondaryBuffer
0x1400156ff  mov     edx, ebx; Length
0x140015701  mov     rcx, r14; VirtualAddress
0x140015704  call    cs:__imp_IoAllocateMdl
0x14001570b  nop     dword ptr [rax+rax+00h]
0x140015710  mov     rdi, rax
0x140015713  mov     [rsp+2D8h+var_298], rax
0x140015718  test    rax, rax
0x14001571b  jz      short loc_140015797
0x14001571d  xor     r8d, r8d; Operation
0x140015720  xor     edx, edx; AccessMode
0x140015722  mov     rcx, rax; MemoryDescriptorList
0x140015725  call    cs:__imp_MmProbeAndLockPages
0x14001572c  nop     dword ptr [rax+rax+00h]
0x140015731  mov     [rsp+2D8h+var_2A8], 1
0x140015736  test    byte ptr [rdi+0Ah], 5
0x14001573a  jz      short loc_140015742
0x14001573c  mov     rax, [rdi+18h]
0x140015740  jmp     short loc_140015769
0x140015742  mov     [rsp+2D8h+Priority], 40000010h; Priority
0x14001574a  mov     dword ptr [rsp+2D8h+Irp], r15d; BugCheckOnFailure
0x14001574f  xor     r9d, r9d; RequestedAddress
0x140015752  xor     edx, edx; AccessMode
0x140015754  mov     r8d, 1; CacheType
0x14001575a  mov     rcx, rdi; MemoryDescriptorList
0x14001575d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140015764  nop     dword ptr [rax+rax+00h]
0x140015769  test    rax, rax
0x14001576c  jz      short loc_140015797
0x14001576e  mov     rdx, rax
0x140015771  mov     rcx, rsi
0x140015774  call    SqospAssignFlowIoRates
0x140015779  mov     ebx, eax
0x14001577b  jmp     short loc_14001579C
0x14001577d  mov     ebx, eax
0x14001577f  mov     rsi, [rsp+2D8h+var_2A0]
0x140015784  mov     rdi, [rsp+2D8h+var_298]
0x140015789  jmp     short loc_14001579C
0x14001578b  mov     ebx, eax
0x14001578d  mov     rsi, [rsp+2D8h+var_2A0]
0x140015792  mov     rdi, rsi
0x140015795  jmp     short loc_14001579C
0x140015797  mov     ebx, 0C000009Ah
0x14001579c  test    rdi, rdi
0x14001579f  jz      short loc_1400157C6
0x1400157a1  cmp     [rsp+2D8h+var_2A8], 0
0x1400157a6  jz      short loc_1400157B7
0x1400157a8  mov     rcx, rdi; MemoryDescriptorList
0x1400157ab  call    cs:__imp_MmUnlockPages
0x1400157b2  nop     dword ptr [rax+rax+00h]
0x1400157b7  mov     rcx, rdi; Mdl
0x1400157ba  call    cs:__imp_IoFreeMdl
0x1400157c1  nop     dword ptr [rax+rax+00h]
0x1400157c6  test    rsi, rsi
0x1400157c9  jz      short loc_1400157DA
0x1400157cb  mov     rcx, rsi; Context
0x1400157ce  call    cs:__imp_FltReleaseContext
0x1400157d5  nop     dword ptr [rax+rax+00h]
0x1400157da  mov     eax, ebx
0x1400157dc  mov     rcx, [rsp+2D8h+var_28]
0x1400157e4  xor     rcx, rsp; StackCookie
0x1400157e7  call    __security_check_cookie
0x1400157ec  lea     r11, [rsp+2D8h+var_18]
0x1400157f4  mov     rbx, [r11+30h]
0x1400157f8  mov     rsi, [r11+38h]
0x1400157fc  mov     rsp, r11
0x1400157ff  pop     r15
0x140015801  pop     r14
0x140015803  pop     rdi
0x140015804  retn
```
