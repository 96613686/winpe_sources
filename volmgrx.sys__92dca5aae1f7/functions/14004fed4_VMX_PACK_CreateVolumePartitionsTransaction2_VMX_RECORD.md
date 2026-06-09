# VMX_PACK::CreateVolumePartitionsTransaction2(VMX_RECORD *)

- ea: `0x14004fed4`
- end: `0x140050136`
- name: `?CreateVolumePartitionsTransaction2@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(VMX_PACK *__hidden this, struct VMX_RECORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400362a8`

## callees

- `0x1400099d8`
- `0x14002aed4`
- `0x14004037c`
- `0x14004fed4`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ff7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005007a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ff7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005007a`

## pseudocode

```c
__int64 __fastcall VMX_PACK::CreateVolumePartitionsTransaction2(struct VMX_TRANSACTION **this, struct VMX_RECORD *a2)
{
  __int64 v2; // rax
  __int64 i; // rdx
  __int64 v5; // rdi
  __int64 v6; // rsi
  _QWORD *v7; // r14
  __int64 v8; // r15
  unsigned int *v9; // rcx
  unsigned __int64 v10; // rbp
  unsigned int DriveLayout; // ebx
  __int64 v12; // rbx
  unsigned int v13; // r8d
  unsigned int v14; // eax
  int v15; // r11d
  __int64 v16; // rax
  VMX_NOTIFICATION_QUEUE *v17; // rcx
  __int64 v18; // rdx
  PVOID P; // [rsp+58h] [rbp+10h] BYREF

  v2 = *((_QWORD *)a2 + 6);
  P = 0;
  for ( i = *(_QWORD *)(v2 + 264); i; i = *(_QWORD *)(v5 + 144) )
  {
    v5 = *(_QWORD *)(i + 8LL * (*(_WORD *)(i + 64) & 1) + 40);
    if ( *(_BYTE *)(v5 + 87) != 2 || *(_DWORD *)(v5 + 92) != 1 )
    {
      v17 = WPP_GLOBAL_Control;
      DriveLayout = -1070071744;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v18 = 118;
LABEL_35:
        WPP_SF_d(*((_QWORD *)v17 + 3), v18, WPP_b525482092043ba595507d12d78e6f73_Traceguids, DriveLayout);
      }
      return DriveLayout;
    }
    v6 = *(_QWORD *)(v5 + 152);
    v7 = *(_QWORD **)(v6 + 8LL * (*(_WORD *)(v6 + 64) & 1) + 40);
    v8 = *(_QWORD *)(*(_QWORD *)(v7[19] + 8LL * (*(_WORD *)(v7[19] + 64LL) & 1) + 40) + 128LL);
    v9 = *(unsigned int **)(v8 + 16);
    v10 = v9[9];
    DriveLayout = VMX_DISK_DEVICE::GetDriveLayoutEx((VMX_DISK_DEVICE *)v9, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
    if ( (DriveLayout & 0x80000000) != 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v18 = 119;
        goto LABEL_35;
      }
      return DriveLayout;
    }
    if ( *(_DWORD *)P )
    {
      ExFreePoolWithTag(P, 0);
    }
    else
    {
      v12 = 0;
      v13 = *((_DWORD *)P + 1);
      if ( v13 )
      {
        while ( 1 )
        {
          v14 = *((unsigned __int8 *)P + 144 * v12 + 80);
          if ( (unsigned __int8)v14 > 0xFu || (v15 = 32801, !_bittest(&v15, v14)) )
          {
            if ( (v7[10] << 9) + *(_QWORD *)(*(_QWORD *)(v8 + 88) + 136LL) * v10 == *((_QWORD *)P + 18 * v12 + 7)
              && v7[12] << 9 == *((_QWORD *)P + 18 * v12 + 8) )
            {
              break;
            }
          }
          v12 = (unsigned int)(v12 + 1);
          if ( (unsigned int)v12 >= v13 )
            goto LABEL_14;
        }
      }
      else
      {
LABEL_14:
        if ( (_DWORD)v12 == v13 )
        {
          ExFreePoolWithTag(P, 0);
          v17 = WPP_GLOBAL_Control;
          DriveLayout = -1070071753;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v18 = 120;
            goto LABEL_35;
          }
          return DriveLayout;
        }
      }
      ExFreePoolWithTag(P, 0);
      if ( (unsigned int)v12 >= 4 )
      {
        DriveLayout = VMX_RECORD::PreTouch((VMX_RECORD *)v6);
        if ( (DriveLayout & 0x80000000) != 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v18 = 121;
            goto LABEL_35;
          }
          return DriveLayout;
        }
        v16 = *(_QWORD *)(v6 + 48);
        *(_DWORD *)(v16 + 72) |= 0x40u;
        *(_QWORD *)(v16 + 136) = v10 >> 9;
        VMX_RECORD::Touch((VMX_RECORD *)v6, this[6]);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14004fed4  mov     [rsp+arg_0], rbx
0x14004fed9  mov     [rsp+arg_10], rbp
0x14004fede  push    rsi
0x14004fedf  push    rdi
0x14004fee0  push    r13
0x14004fee2  push    r14
0x14004fee4  push    r15
0x14004fee6  sub     rsp, 20h
0x14004feea  mov     rax, [rdx+30h]
0x14004feee  mov     r13, rcx
0x14004fef1  mov     [rsp+48h+P], 0
0x14004fefa  mov     rdx, [rax+108h]
0x14004ff01  test    rdx, rdx
0x14004ff04  jz      loc_14005011C
0x14004ff0a  movzx   eax, word ptr [rdx+40h]
0x14004ff0e  and     eax, 1
0x14004ff11  mov     rdi, [rdx+rax*8+28h]
0x14004ff16  cmp     byte ptr [rdi+57h], 2
0x14004ff1a  jnz     loc_1400500DA
0x14004ff20  cmp     dword ptr [rdi+5Ch], 1
0x14004ff24  jnz     loc_1400500DA
0x14004ff2a  mov     rsi, [rdi+98h]
0x14004ff31  lea     rdx, [rsp+48h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14004ff36  movzx   eax, word ptr [rsi+40h]
0x14004ff3a  and     eax, 1
0x14004ff3d  mov     r14, [rsi+rax*8+28h]
0x14004ff42  mov     rcx, [r14+98h]
0x14004ff49  movzx   eax, word ptr [rcx+40h]
0x14004ff4d  and     eax, 1
0x14004ff50  mov     rax, [rcx+rax*8+28h]
0x14004ff55  mov     r15, [rax+80h]
0x14004ff5c  mov     rcx, [r15+10h]; this
0x14004ff60  mov     ebp, [rcx+24h]
0x14004ff63  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14004ff68  mov     ebx, eax
0x14004ff6a  test    eax, eax
0x14004ff6c  js      loc_1400500B3
0x14004ff72  mov     rcx, [rsp+48h+P]; P
0x14004ff77  cmp     dword ptr [rcx], 0
0x14004ff7a  jz      short loc_14004FF8F
0x14004ff7c  xor     edx, edx; Tag
0x14004ff7e  call    cs:__imp_ExFreePoolWithTag
0x14004ff85  nop     dword ptr [rax+rax+00h]
0x14004ff8a  jmp     loc_140050036
0x14004ff8f  mov     rax, [r15+58h]
0x14004ff93  mov     r9, rbp
0x14004ff96  mov     r10, [r14+60h]
0x14004ff9a  xor     ebx, ebx
0x14004ff9c  mov     r8d, [rcx+4]
0x14004ffa0  shl     r10, 9
0x14004ffa4  imul    r9, [rax+88h]
0x14004ffac  mov     rax, [r14+50h]
0x14004ffb0  shl     rax, 9
0x14004ffb4  add     r9, rax
0x14004ffb7  test    r8d, r8d
0x14004ffba  jz      short loc_14004FFED
0x14004ffbc  lea     rdx, [rbx+rbx*8]
0x14004ffc0  add     rdx, rdx
0x14004ffc3  movzx   eax, byte ptr [rcx+rdx*8+50h]
0x14004ffc8  cmp     al, 0Fh
0x14004ffca  ja      short loc_14004FFD8
0x14004ffcc  mov     r11d, 8021h
0x14004ffd2  bt      r11d, eax
0x14004ffd6  jb      short loc_14004FFE6
0x14004ffd8  cmp     r9, [rcx+rdx*8+38h]
0x14004ffdd  jnz     short loc_14004FFE6
0x14004ffdf  cmp     r10, [rcx+rdx*8+40h]
0x14004ffe4  jz      short loc_14004FFF6
0x14004ffe6  inc     ebx
0x14004ffe8  cmp     ebx, r8d
0x14004ffeb  jb      short loc_14004FFBC
0x14004ffed  cmp     ebx, r8d
0x14004fff0  jz      loc_140050078
0x14004fff6  xor     edx, edx; Tag
0x14004fff8  call    cs:__imp_ExFreePoolWithTag
0x14004ffff  nop     dword ptr [rax+rax+00h]
0x140050004  cmp     ebx, 4
0x140050007  jb      short loc_140050036
0x140050009  mov     rcx, rsi; this
0x14005000c  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x140050011  mov     ebx, eax
0x140050013  test    eax, eax
0x140050015  js      short loc_140050042
0x140050017  mov     rax, [rsi+30h]
0x14005001b  mov     rcx, rsi; this
0x14005001e  shr     rbp, 9
0x140050022  or      dword ptr [rax+48h], 40h
0x140050026  mov     [rax+88h], rbp
0x14005002d  mov     rdx, [r13+30h]; struct VMX_TRANSACTION *
0x140050031  call    ?Touch@VMX_RECORD@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RECORD::Touch(VMX_TRANSACTION *)
0x140050036  mov     rdx, [rdi+90h]
0x14005003d  jmp     loc_14004FF01
0x140050042  mov     rcx, cs:WPP_GLOBAL_Control
0x140050049  lea     rax, WPP_GLOBAL_Control
0x140050050  cmp     rcx, rax
0x140050053  jz      loc_140050118
0x140050059  mov     eax, [rcx+2Ch]
0x14005005c  test    al, 8
0x14005005e  jz      loc_140050118
0x140050064  cmp     byte ptr [rcx+29h], 2
0x140050068  jb      loc_140050118
0x14005006e  mov     edx, 79h ; 'y'
0x140050073  jmp     loc_140050105
0x140050078  xor     edx, edx; Tag
0x14005007a  call    cs:__imp_ExFreePoolWithTag
0x140050081  nop     dword ptr [rax+rax+00h]
0x140050086  mov     rcx, cs:WPP_GLOBAL_Control
0x14005008d  lea     rax, WPP_GLOBAL_Control
0x140050094  mov     ebx, 0C0380037h
0x140050099  cmp     rcx, rax
0x14005009c  jz      short loc_140050118
0x14005009e  mov     edx, [rcx+2Ch]
0x1400500a1  test    dl, 8
0x1400500a4  jz      short loc_140050118
0x1400500a6  cmp     byte ptr [rcx+29h], 2
0x1400500aa  jb      short loc_140050118
0x1400500ac  mov     edx, 78h ; 'x'
0x1400500b1  jmp     short loc_140050105
0x1400500b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400500ba  lea     rax, WPP_GLOBAL_Control
0x1400500c1  cmp     rcx, rax
0x1400500c4  jz      short loc_140050118
0x1400500c6  mov     eax, [rcx+2Ch]
0x1400500c9  test    al, 8
0x1400500cb  jz      short loc_140050118
0x1400500cd  cmp     byte ptr [rcx+29h], 2
0x1400500d1  jb      short loc_140050118
0x1400500d3  mov     edx, 77h ; 'w'
0x1400500d8  jmp     short loc_140050105
0x1400500da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400500e1  lea     rax, WPP_GLOBAL_Control
0x1400500e8  mov     ebx, 0C0380040h
0x1400500ed  cmp     rcx, rax
0x1400500f0  jz      short loc_140050118
0x1400500f2  mov     edx, [rcx+2Ch]
0x1400500f5  test    dl, 8
0x1400500f8  jz      short loc_140050118
0x1400500fa  cmp     byte ptr [rcx+29h], 2
0x1400500fe  jb      short loc_140050118
0x140050100  mov     edx, 76h ; 'v'
0x140050105  mov     rcx, [rcx+18h]
0x140050109  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140050110  mov     r9d, ebx
0x140050113  call    WPP_SF_d
0x140050118  mov     eax, ebx
0x14005011a  jmp     short loc_14005011E
0x14005011c  xor     eax, eax
0x14005011e  mov     rbx, [rsp+48h+arg_0]
0x140050123  mov     rbp, [rsp+48h+arg_10]
0x140050128  add     rsp, 20h
0x14005012c  pop     r15
0x14005012e  pop     r14
0x140050130  pop     r13
0x140050132  pop     rdi
0x140050133  pop     rsi
0x140050134  retn
```
