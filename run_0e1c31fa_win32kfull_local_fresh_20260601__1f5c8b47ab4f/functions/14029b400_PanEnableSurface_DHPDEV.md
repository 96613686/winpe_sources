# PanEnableSurface(DHPDEV__ *)

- ea: `0x14029b400`
- end: `0x14029b6ab`
- name: `?PanEnableSurface@@YAPEAUHSURF__@@PEAUDHPDEV__@@@Z`
- size: `683`
- prototype: `HSURF __fastcall(struct DHPDEV__ *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14028b9f0`
- `0x14029b400`
- `0x14029b6b4`
- `0x140343080`

## import_xrefs

- `win32kbase!EngAcquireSemaphore` at `0x14029b44a`
- `win32kbase!EngAcquireSemaphore` at `0x14029b44a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14029b60e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14029b61e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14029b62e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14029b60e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14029b61e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14029b62e`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14029b582`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14029b592`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14029b5a2`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14029b582`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14029b592`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14029b5a2`
- `win32kbase!EngLockSurface` at `0x14029b472`
- `win32kbase!EngLockSurface` at `0x14029b544`
- `win32kbase!EngLockSurface` at `0x14029b472`
- `win32kbase!EngLockSurface` at `0x14029b544`
- `win32kbase!EngUnlockSurface` at `0x14029b63d`
- `win32kbase!EngUnlockSurface` at `0x14029b66a`
- `win32kbase!EngUnlockSurface` at `0x14029b63d`
- `win32kbase!EngUnlockSurface` at `0x14029b66a`
- `win32kbase!EngCreateBitmap` at `0x14029b532`
- `win32kbase!EngCreateBitmap` at `0x14029b532`
- `win32kbase!EngDeleteSurface` at `0x14029b64c`
- `win32kbase!EngDeleteSurface` at `0x14029b65b`
- `win32kbase!EngDeleteSurface` at `0x14029b64c`
- `win32kbase!EngDeleteSurface` at `0x14029b65b`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14029b5c7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14029b5d7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14029b5c7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14029b5d7`
- `win32kbase!EngModifySurface` at `0x14029b504`
- `win32kbase!EngModifySurface` at `0x14029b504`
- `win32kbase!EngCreateDeviceSurface` at `0x14029b4b3`
- `win32kbase!EngCreateDeviceSurface` at `0x14029b4b3`
- `win32kbase!EngAssociateSurface` at `0x14029b56a`
- `win32kbase!EngAssociateSurface` at `0x14029b56a`

## pseudocode

```c
HSURF __fastcall PanEnableSurface(SIZEL *a1)
{
  LONG cx; // r8d
  LONG cy; // edx
  int v4; // eax
  int v5; // ecx
  LONG v6; // eax
  HSEMAPHORE v7; // rcx
  HSURF v8; // rax
  SURFOBJ *v9; // rax
  SURFOBJ *v10; // rsi
  DHPDEV v11; // rcx
  LONG v12; // r14d
  ULONG v13; // r8d
  HSURF DeviceSurface; // rax
  HSURF v15; // rdi
  HDEV v16; // rdx
  HBITMAP Bitmap; // r14
  SURFOBJ *v18; // rax
  SURFOBJ *v19; // r15
  HDEV v20; // rdx
  SIZEL sizl; // [rsp+80h] [rbp+38h] BYREF
  SIZEL v23; // [rsp+88h] [rbp+40h] BYREF
  SIZEL v24; // [rsp+90h] [rbp+48h] BYREF
  HSEMAPHORE v25; // [rsp+98h] [rbp+50h] BYREF

  cx = a1->cx;
  cy = a1->cy;
  v4 = (a1[1].cx - a1->cx) >> 1;
  a1[2].cx = v4;
  v5 = a1[1].cy - cy;
  a1[3].cx = cx + v4;
  v5 >>= 1;
  a1[2].cy = v5;
  sizl = 0;
  v6 = v5 + cy;
  v25 = (HSEMAPHORE)a1[14];
  v7 = v25;
  a1[3].cy = v6;
  EngAcquireSemaphore(v7);
  v8 = (HSURF)((__int64 (__fastcall *)(_QWORD))a1[102])(*(_QWORD *)&a1[4]);
  if ( !v8 )
    goto LABEL_16;
  v9 = EngLockSurface(v8);
  v10 = v9;
  if ( !v9 )
  {
LABEL_15:
    PANDEVLOCK::vUnLock((PANDEVLOCK *)&v25);
    ((void (__fastcall *)(_QWORD))a1[103])(*(_QWORD *)&a1[4]);
LABEL_16:
    v15 = 0;
    goto LABEL_17;
  }
  v9[1].cjBits &= ~0x1000u;
  v11 = (DHPDEV)a1[4];
  a1[9] = (SIZEL)v9;
  v9->dhpdev = v11;
  v12 = a1[1].cx;
  v13 = a1[5].cx;
  sizl.cy = a1[1].cy;
  sizl.cx = v12;
  DeviceSurface = EngCreateDeviceSurface(0, sizl, v13);
  v15 = DeviceSurface;
  if ( !DeviceSurface )
  {
LABEL_14:
    EngUnlockSurface(v10);
    goto LABEL_15;
  }
  v16 = (HDEV)a1[6];
  a1[7] = (SIZEL)DeviceSurface;
  if ( !EngModifySurface(DeviceSurface, v16, 0x394ABu, 3u, (DHSURF)&a1[7], 0, 0, 0) )
  {
LABEL_13:
    EngDeleteSurface(v15);
    goto LABEL_14;
  }
  Bitmap = EngCreateBitmap(sizl, v12, a1[5].cx, 1u, 0);
  v18 = EngLockSurface((HSURF)Bitmap);
  v19 = v18;
  if ( !v18 || (v20 = (HDEV)a1[6], a1[8] = (SIZEL)v18, !EngAssociateSurface((HSURF)Bitmap, v20, 0)) )
  {
LABEL_12:
    EngUnlockSurface(v19);
    EngDeleteSurface((HSURF)Bitmap);
    goto LABEL_13;
  }
  RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v23);
  RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&sizl);
  RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v24);
  if ( !*(_QWORD *)&sizl || !*(_QWORD *)&v23 || !*(_QWORD *)&v24 )
  {
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&sizl);
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v23);
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v24);
    goto LABEL_12;
  }
  RGNOBJ::vSet((RGNOBJ *)&v23);
  RGNOBJ::vSet((RGNOBJ *)&sizl);
  a1[10] = v23;
  a1[11] = sizl;
  a1[12] = v24;
  PanSynchronize((struct DHPDEV__ *)a1, 0);
LABEL_17:
  PANDEVLOCK::vUnLock((PANDEVLOCK *)&v25);
  return v15;
}

```

## disassembly

```asm
0x14029b400  push    rbp
0x14029b402  push    rbx
0x14029b403  push    rsi
0x14029b404  push    rdi
0x14029b405  push    r14
0x14029b407  push    r15
0x14029b409  mov     rbp, rsp
0x14029b40c  sub     rsp, 48h
0x14029b410  mov     r8d, [rcx]
0x14029b413  mov     rbx, rcx
0x14029b416  mov     eax, [rcx+8]
0x14029b419  mov     edx, [rcx+4]
0x14029b41c  sub     eax, r8d
0x14029b41f  sar     eax, 1
0x14029b421  mov     [rcx+10h], eax
0x14029b424  add     eax, r8d
0x14029b427  mov     ecx, [rcx+0Ch]
0x14029b42a  sub     ecx, edx
0x14029b42c  mov     [rbx+18h], eax
0x14029b42f  sar     ecx, 1
0x14029b431  mov     [rbx+14h], ecx
0x14029b434  mov     qword ptr [rbp+sizl.cx], 0
0x14029b43c  lea     eax, [rcx+rdx]
0x14029b43f  mov     rcx, [rbx+70h]; hsem
0x14029b443  mov     [rbp+arg_18], rcx
0x14029b447  mov     [rbx+1Ch], eax
0x14029b44a  call    cs:__imp_EngAcquireSemaphore
0x14029b451  nop     dword ptr [rax+rax+00h]
0x14029b456  mov     rax, [rbx+330h]
0x14029b45d  mov     rcx, [rbx+20h]
0x14029b461  call    _guard_dispatch_icall
0x14029b466  test    rax, rax
0x14029b469  jz      loc_14029B68F
0x14029b46f  mov     rcx, rax; hsurf
0x14029b472  call    cs:__imp_EngLockSurface
0x14029b479  nop     dword ptr [rax+rax+00h]
0x14029b47e  mov     rsi, rax
0x14029b481  test    rax, rax
0x14029b484  jz      loc_14029B676
0x14029b48a  btr     dword ptr [rax+78h], 0Ch
0x14029b48f  mov     rcx, [rbx+20h]
0x14029b493  mov     [rbx+48h], rax
0x14029b497  mov     [rax+10h], rcx
0x14029b49b  mov     ecx, [rbx+0Ch]
0x14029b49e  mov     r14d, [rbx+8]
0x14029b4a2  mov     r8d, [rbx+28h]; iFormatCompat
0x14029b4a6  mov     [rbp+sizl.cy], ecx
0x14029b4a9  xor     ecx, ecx; dhsurf
0x14029b4ab  mov     [rbp+sizl.cx], r14d
0x14029b4af  mov     rdx, qword ptr [rbp+sizl.cx]; sizl
0x14029b4b3  call    cs:__imp_EngCreateDeviceSurface
0x14029b4ba  nop     dword ptr [rax+rax+00h]
0x14029b4bf  mov     rdi, rax
0x14029b4c2  test    rax, rax
0x14029b4c5  jz      loc_14029B667
0x14029b4cb  mov     rdx, [rbx+30h]; hdev
0x14029b4cf  lea     rcx, [rbx+38h]
0x14029b4d3  mov     [rsp+48h+pvReserved], 0; pvReserved
0x14029b4dc  mov     r9d, 3; flSurface
0x14029b4e2  mov     [rsp+48h+lDelta], 0; lDelta
0x14029b4ea  mov     r8d, 394ABh; flHooks
0x14029b4f0  mov     [rcx], rax
0x14029b4f3  mov     [rsp+48h+pvScan0], 0; pvScan0
0x14029b4fc  mov     [rsp+48h+dhsurf], rcx; dhsurf
0x14029b501  mov     rcx, rax; hsurf
0x14029b504  call    cs:__imp_EngModifySurface
0x14029b50b  nop     dword ptr [rax+rax+00h]
0x14029b510  test    eax, eax
0x14029b512  jz      loc_14029B658
0x14029b518  mov     r8d, [rbx+28h]; iFormat
0x14029b51c  mov     r9d, 1; fl
0x14029b522  mov     rcx, qword ptr [rbp+sizl.cx]; sizl
0x14029b526  mov     edx, r14d; lWidth
0x14029b529  mov     [rsp+48h+dhsurf], 0; pvBits
0x14029b532  call    cs:__imp_EngCreateBitmap
0x14029b539  nop     dword ptr [rax+rax+00h]
0x14029b53e  mov     rcx, rax; hsurf
0x14029b541  mov     r14, rax
0x14029b544  call    cs:__imp_EngLockSurface
0x14029b54b  nop     dword ptr [rax+rax+00h]
0x14029b550  mov     r15, rax
0x14029b553  test    rax, rax
0x14029b556  jz      loc_14029B63A
0x14029b55c  mov     rdx, [rbx+30h]; hdev
0x14029b560  xor     r8d, r8d; flHooks
0x14029b563  mov     rcx, r14; hsurf
0x14029b566  mov     [rbx+40h], rax
0x14029b56a  call    cs:__imp_EngAssociateSurface
0x14029b571  nop     dword ptr [rax+rax+00h]
0x14029b576  test    eax, eax
0x14029b578  jz      loc_14029B63A
0x14029b57e  lea     rcx, [rbp+arg_8]
0x14029b582  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14029b589  nop     dword ptr [rax+rax+00h]
0x14029b58e  lea     rcx, [rbp+sizl]
0x14029b592  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14029b599  nop     dword ptr [rax+rax+00h]
0x14029b59e  lea     rcx, [rbp+arg_10]
0x14029b5a2  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14029b5a9  nop     dword ptr [rax+rax+00h]
0x14029b5ae  cmp     qword ptr [rbp+sizl.cx], 0
0x14029b5b3  jz      short loc_14029B60A
0x14029b5b5  cmp     [rbp+arg_8], 0
0x14029b5ba  jz      short loc_14029B60A
0x14029b5bc  cmp     [rbp+arg_10], 0
0x14029b5c1  jz      short loc_14029B60A
0x14029b5c3  lea     rcx, [rbp+arg_8]
0x14029b5c7  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x14029b5ce  nop     dword ptr [rax+rax+00h]
0x14029b5d3  lea     rcx, [rbp+sizl]
0x14029b5d7  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x14029b5de  nop     dword ptr [rax+rax+00h]
0x14029b5e3  mov     rax, [rbp+arg_8]
0x14029b5e7  xor     edx, edx; struct _RECTL *
0x14029b5e9  mov     [rbx+50h], rax
0x14029b5ed  mov     rcx, rbx; struct DHPDEV__ *
0x14029b5f0  mov     rax, qword ptr [rbp+sizl.cx]
0x14029b5f4  mov     [rbx+58h], rax
0x14029b5f8  mov     rax, [rbp+arg_10]
0x14029b5fc  mov     [rbx+60h], rax
0x14029b600  call    ?PanSynchronize@@YAXPEAUDHPDEV__@@PEAU_RECTL@@@Z; PanSynchronize(DHPDEV__ *,_RECTL *)
0x14029b605  jmp     loc_14029B691
0x14029b60a  lea     rcx, [rbp+sizl]
0x14029b60e  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14029b615  nop     dword ptr [rax+rax+00h]
0x14029b61a  lea     rcx, [rbp+arg_8]
0x14029b61e  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14029b625  nop     dword ptr [rax+rax+00h]
0x14029b62a  lea     rcx, [rbp+arg_10]
0x14029b62e  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14029b635  nop     dword ptr [rax+rax+00h]
0x14029b63a  mov     rcx, r15; pso
0x14029b63d  call    cs:__imp_EngUnlockSurface
0x14029b644  nop     dword ptr [rax+rax+00h]
0x14029b649  mov     rcx, r14; hsurf
0x14029b64c  call    cs:__imp_EngDeleteSurface
0x14029b653  nop     dword ptr [rax+rax+00h]
0x14029b658  mov     rcx, rdi; hsurf
0x14029b65b  call    cs:__imp_EngDeleteSurface
0x14029b662  nop     dword ptr [rax+rax+00h]
0x14029b667  mov     rcx, rsi; pso
0x14029b66a  call    cs:__imp_EngUnlockSurface
0x14029b671  nop     dword ptr [rax+rax+00h]
0x14029b676  lea     rcx, [rbp+arg_18]; this
0x14029b67a  call    ?vUnLock@PANDEVLOCK@@QEAAXXZ; PANDEVLOCK::vUnLock(void)
0x14029b67f  mov     rax, [rbx+338h]
0x14029b686  mov     rcx, [rbx+20h]
0x14029b68a  call    _guard_dispatch_icall
0x14029b68f  xor     edi, edi
0x14029b691  lea     rcx, [rbp+arg_18]; this
0x14029b695  call    ?vUnLock@PANDEVLOCK@@QEAAXXZ; PANDEVLOCK::vUnLock(void)
0x14029b69a  mov     rax, rdi
0x14029b69d  add     rsp, 48h
0x14029b6a1  pop     r15
0x14029b6a3  pop     r14
0x14029b6a5  pop     rdi
0x14029b6a6  pop     rsi
0x14029b6a7  pop     rbx
0x14029b6a8  pop     rbp
0x14029b6a9  retn
```
