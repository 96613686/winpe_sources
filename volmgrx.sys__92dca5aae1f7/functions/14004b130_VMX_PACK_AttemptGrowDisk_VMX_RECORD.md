# VMX_PACK::AttemptGrowDisk(VMX_RECORD *)

- ea: `0x14004b130`
- end: `0x14004b2d1`
- name: `?AttemptGrowDisk@VMX_PACK@@AEAAXPEAVVMX_RECORD@@@Z`
- size: `417`
- prototype: `void __fastcall(VMX_PACK *this, struct VMX_RECORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400330a4`
- `0x140053af0`

## callees

- `0x1400099d8`
- `0x140009fcc`
- `0x14001b960`
- `0x140033854`
- `0x14004b130`
- `0x14004b2d8`
- `0x14004b3dc`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004b2a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b2a7`

## pseudocode

```c
void __fastcall VMX_PACK::AttemptGrowDisk(VMX_PACK *this, struct VMX_RECORD *a2)
{
  __int64 v4; // rcx
  VMX_DISK_DEVICE *v5; // rbx
  int DriveGeometry; // eax
  __int64 v7; // r9
  VMX_NOTIFICATION_QUEUE *v8; // r10
  __int64 v9; // rdx
  int DriveLayout; // eax
  VMX_PACK *v11; // rcx
  PVOID v12; // rbx
  PVOID P; // [rsp+20h] [rbp-38h] BYREF
  struct _DISK_GEOMETRY v14; // [rsp+28h] [rbp-30h] BYREF

  memset(&v14, 0, sizeof(v14));
  P = 0;
  if ( !*((_BYTE *)this + 56) )
    return;
  v4 = *(_QWORD *)(*((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5) + 128LL);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 219, WPP_b525482092043ba595507d12d78e6f73_Traceguids);
    }
    return;
  }
  v5 = *(VMX_DISK_DEVICE **)(v4 + 16);
  DriveGeometry = VMX_DISK_DEVICE::GetDriveGeometry(v5, &v14);
  v7 = (unsigned int)DriveGeometry;
  if ( DriveGeometry < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      return;
    }
    v9 = 220;
    goto LABEL_12;
  }
  DriveLayout = VMX_DISK_DEVICE::GetDriveLayoutEx(v5, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
  v7 = (unsigned int)DriveLayout;
  if ( DriveLayout < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      return;
    }
    v9 = 221;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v8 + 3), v9, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v7);
    return;
  }
  v12 = P;
  if ( *(_DWORD *)P )
  {
    if ( *(_DWORD *)P == 1 )
      VMX_PACK::AttemptGrowDiskGpt(v11, a2, &v14, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
  }
  else
  {
    VMX_PACK::AttemptGrowDiskMbr(this, a2, &v14, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
  }
  ExFreePoolWithTag(v12, 0);
}

```

## disassembly

```asm
0x14004b130  mov     r11, rsp
0x14004b133  mov     [r11+18h], rbx
0x14004b137  mov     [r11+20h], rsi
0x14004b13b  push    rdi
0x14004b13c  sub     rsp, 50h
0x14004b140  mov     rax, cs:__security_cookie
0x14004b147  xor     rax, rsp
0x14004b14a  mov     [rsp+58h+var_18], rax
0x14004b14f  xor     eax, eax
0x14004b151  xorps   xmm0, xmm0
0x14004b154  mov     rdi, rdx
0x14004b157  mov     rsi, rcx
0x14004b15a  movups  xmmword ptr [rsp+58h+var_30.Cylinders], xmm0
0x14004b15f  mov     [r11-20h], rax
0x14004b163  mov     [r11-38h], rax
0x14004b167  cmp     [rcx+38h], al
0x14004b16a  jz      loc_14004B2B3
0x14004b170  movzx   eax, word ptr [rdx+40h]
0x14004b174  and     eax, 1
0x14004b177  mov     rax, [rdx+rax*8+28h]
0x14004b17c  mov     rcx, [rax+80h]
0x14004b183  test    rcx, rcx
0x14004b186  jnz     short loc_14004B1CE
0x14004b188  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b18f  lea     rax, WPP_GLOBAL_Control
0x14004b196  cmp     rcx, rax
0x14004b199  jz      loc_14004B2B3
0x14004b19f  mov     eax, [rcx+2Ch]
0x14004b1a2  test    al, 8
0x14004b1a4  jz      loc_14004B2B3
0x14004b1aa  cmp     byte ptr [rcx+29h], 3
0x14004b1ae  jb      loc_14004B2B3
0x14004b1b4  mov     rcx, [rcx+18h]
0x14004b1b8  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004b1bf  mov     edx, 0DBh
0x14004b1c4  call    WPP_SF_
0x14004b1c9  jmp     loc_14004B2B3
0x14004b1ce  mov     rbx, [rcx+10h]
0x14004b1d2  lea     rdx, [rsp+58h+var_30]; PVOID
0x14004b1d7  mov     rcx, rbx; this
0x14004b1da  call    ?GetDriveGeometry@VMX_DISK_DEVICE@@QEAAJPEAU_DISK_GEOMETRY@@@Z; VMX_DISK_DEVICE::GetDriveGeometry(_DISK_GEOMETRY *)
0x14004b1df  mov     r9d, eax
0x14004b1e2  test    eax, eax
0x14004b1e4  jns     short loc_14004B22F
0x14004b1e6  mov     r10, cs:WPP_GLOBAL_Control
0x14004b1ed  lea     rax, WPP_GLOBAL_Control
0x14004b1f4  cmp     r10, rax
0x14004b1f7  jz      loc_14004B2B3
0x14004b1fd  mov     ecx, [r10+2Ch]
0x14004b201  test    cl, 8
0x14004b204  jz      loc_14004B2B3
0x14004b20a  cmp     byte ptr [r10+29h], 3
0x14004b20f  jb      loc_14004B2B3
0x14004b215  mov     edx, 0DCh
0x14004b21a  mov     rcx, [r10+18h]
0x14004b21e  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004b225  call    WPP_SF_d
0x14004b22a  jmp     loc_14004B2B3
0x14004b22f  lea     rdx, [rsp+58h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14004b234  mov     rcx, rbx; this
0x14004b237  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14004b23c  mov     r9d, eax
0x14004b23f  test    eax, eax
0x14004b241  jns     short loc_14004B26D
0x14004b243  mov     r10, cs:WPP_GLOBAL_Control
0x14004b24a  lea     rax, WPP_GLOBAL_Control
0x14004b251  cmp     r10, rax
0x14004b254  jz      short loc_14004B2B3
0x14004b256  mov     ecx, [r10+2Ch]
0x14004b25a  test    cl, 8
0x14004b25d  jz      short loc_14004B2B3
0x14004b25f  cmp     byte ptr [r10+29h], 3
0x14004b264  jb      short loc_14004B2B3
0x14004b266  mov     edx, 0DDh
0x14004b26b  jmp     short loc_14004B21A
0x14004b26d  mov     rbx, [rsp+58h+P]
0x14004b272  mov     eax, [rbx]
0x14004b274  test    eax, eax
0x14004b276  jnz     short loc_14004B28D
0x14004b278  mov     r9, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14004b27b  lea     r8, [rsp+58h+var_30]; struct _DISK_GEOMETRY *
0x14004b280  mov     rdx, rdi; struct VMX_RECORD *
0x14004b283  mov     rcx, rsi; this
0x14004b286  call    ?AttemptGrowDiskMbr@VMX_PACK@@AEAAXPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PACK::AttemptGrowDiskMbr(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14004b28b  jmp     short loc_14004B2A2
0x14004b28d  cmp     eax, 1
0x14004b290  jnz     short loc_14004B2A2
0x14004b292  mov     r9, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14004b295  lea     r8, [rsp+58h+var_30]; struct _DISK_GEOMETRY *
0x14004b29a  mov     rdx, rdi; struct VMX_RECORD *
0x14004b29d  call    ?AttemptGrowDiskGpt@VMX_PACK@@AEAAXPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PACK::AttemptGrowDiskGpt(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14004b2a2  xor     edx, edx; Tag
0x14004b2a4  mov     rcx, rbx; P
0x14004b2a7  call    cs:__imp_ExFreePoolWithTag
0x14004b2ae  nop     dword ptr [rax+rax+00h]
0x14004b2b3  mov     rcx, [rsp+58h+var_18]
0x14004b2b8  xor     rcx, rsp; StackCookie
0x14004b2bb  call    __security_check_cookie
0x14004b2c0  mov     rbx, [rsp+58h+arg_10]
0x14004b2c5  mov     rsi, [rsp+58h+arg_18]
0x14004b2ca  add     rsp, 50h
0x14004b2ce  pop     rdi
0x14004b2cf  retn
```
