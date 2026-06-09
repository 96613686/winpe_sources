# PanEnableSurface(DHPDEV__ *)

- ea: `0x140298f30`
- end: `0x1402991de`
- name: `?PanEnableSurface@@YAPEAUHSURF__@@PEAUDHPDEV__@@@Z`
- size: `686`
- prototype: `HSURF __fastcall(struct DHPDEV__ *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140289500`
- `0x140298f30`
- `0x1402991e4`
- `0x1403420d0`

## import_xrefs

- `win32kbase!EngAcquireSemaphore` at `0x140298f7a`
- `win32kbase!EngAcquireSemaphore` at `0x140298f7a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140299141`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140299151`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140299161`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140299141`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140299151`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140299161`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402990b5`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402990c5`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402990d5`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402990b5`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402990c5`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402990d5`
- `win32kbase!EngLockSurface` at `0x140298fa2`
- `win32kbase!EngLockSurface` at `0x140299077`
- `win32kbase!EngLockSurface` at `0x140298fa2`
- `win32kbase!EngLockSurface` at `0x140299077`
- `win32kbase!EngUnlockSurface` at `0x140299170`
- `win32kbase!EngUnlockSurface` at `0x14029919d`
- `win32kbase!EngUnlockSurface` at `0x140299170`
- `win32kbase!EngUnlockSurface` at `0x14029919d`
- `win32kbase!EngCreateBitmap` at `0x140299065`
- `win32kbase!EngCreateBitmap` at `0x140299065`
- `win32kbase!EngDeleteSurface` at `0x14029917f`
- `win32kbase!EngDeleteSurface` at `0x14029918e`
- `win32kbase!EngDeleteSurface` at `0x14029917f`
- `win32kbase!EngDeleteSurface` at `0x14029918e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1402990fa`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14029910a`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1402990fa`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14029910a`
- `win32kbase!EngModifySurface` at `0x140299037`
- `win32kbase!EngModifySurface` at `0x140299037`
- `win32kbase!EngCreateDeviceSurface` at `0x140298fe6`
- `win32kbase!EngCreateDeviceSurface` at `0x140298fe6`
- `win32kbase!EngAssociateSurface` at `0x14029909d`
- `win32kbase!EngAssociateSurface` at `0x14029909d`

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
  LODWORD(v9[1].pvScan0) &= ~0x1000u;
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
0x140298f30  push    rbp
0x140298f32  push    rbx
0x140298f33  push    rsi
0x140298f34  push    rdi
0x140298f35  push    r14
0x140298f37  push    r15
0x140298f39  mov     rbp, rsp
0x140298f3c  sub     rsp, 48h
0x140298f40  mov     r8d, [rcx]
0x140298f43  mov     rbx, rcx
0x140298f46  mov     eax, [rcx+8]
0x140298f49  mov     edx, [rcx+4]
0x140298f4c  sub     eax, r8d
0x140298f4f  sar     eax, 1
0x140298f51  mov     [rcx+10h], eax
0x140298f54  add     eax, r8d
0x140298f57  mov     ecx, [rcx+0Ch]
0x140298f5a  sub     ecx, edx
0x140298f5c  mov     [rbx+18h], eax
0x140298f5f  sar     ecx, 1
0x140298f61  mov     [rbx+14h], ecx
0x140298f64  mov     qword ptr [rbp+sizl.cx], 0
0x140298f6c  lea     eax, [rcx+rdx]
0x140298f6f  mov     rcx, [rbx+70h]; hsem
0x140298f73  mov     [rbp+arg_18], rcx
0x140298f77  mov     [rbx+1Ch], eax
0x140298f7a  call    cs:__imp_EngAcquireSemaphore
0x140298f81  nop     dword ptr [rax+rax+00h]
0x140298f86  mov     rax, [rbx+330h]
0x140298f8d  mov     rcx, [rbx+20h]
0x140298f91  call    _guard_dispatch_icall
0x140298f96  test    rax, rax
0x140298f99  jz      loc_1402991C2
0x140298f9f  mov     rcx, rax; hsurf
0x140298fa2  call    cs:__imp_EngLockSurface
0x140298fa9  nop     dword ptr [rax+rax+00h]
0x140298fae  mov     rsi, rax
0x140298fb1  test    rax, rax
0x140298fb4  jz      loc_1402991A9
0x140298fba  btr     dword ptr [rax+88h], 0Ch
0x140298fc2  mov     rcx, [rbx+20h]
0x140298fc6  mov     [rbx+48h], rax
0x140298fca  mov     [rax+10h], rcx
0x140298fce  mov     ecx, [rbx+0Ch]
0x140298fd1  mov     r14d, [rbx+8]
0x140298fd5  mov     r8d, [rbx+28h]; iFormatCompat
0x140298fd9  mov     [rbp+sizl.cy], ecx
0x140298fdc  xor     ecx, ecx; dhsurf
0x140298fde  mov     [rbp+sizl.cx], r14d
0x140298fe2  mov     rdx, qword ptr [rbp+sizl.cx]; sizl
0x140298fe6  call    cs:__imp_EngCreateDeviceSurface
0x140298fed  nop     dword ptr [rax+rax+00h]
0x140298ff2  mov     rdi, rax
0x140298ff5  test    rax, rax
0x140298ff8  jz      loc_14029919A
0x140298ffe  mov     rdx, [rbx+30h]; hdev
0x140299002  lea     rcx, [rbx+38h]
0x140299006  mov     [rsp+48h+pvReserved], 0; pvReserved
0x14029900f  mov     r9d, 3; flSurface
0x140299015  mov     [rsp+48h+lDelta], 0; lDelta
0x14029901d  mov     r8d, 394ABh; flHooks
0x140299023  mov     [rcx], rax
0x140299026  mov     [rsp+48h+pvScan0], 0; pvScan0
0x14029902f  mov     [rsp+48h+dhsurf], rcx; dhsurf
0x140299034  mov     rcx, rax; hsurf
0x140299037  call    cs:__imp_EngModifySurface
0x14029903e  nop     dword ptr [rax+rax+00h]
0x140299043  test    eax, eax
0x140299045  jz      loc_14029918B
0x14029904b  mov     r8d, [rbx+28h]; iFormat
0x14029904f  mov     r9d, 1; fl
0x140299055  mov     rcx, qword ptr [rbp+sizl.cx]; sizl
0x140299059  mov     edx, r14d; lWidth
0x14029905c  mov     [rsp+48h+dhsurf], 0; pvBits
0x140299065  call    cs:__imp_EngCreateBitmap
0x14029906c  nop     dword ptr [rax+rax+00h]
0x140299071  mov     rcx, rax; hsurf
0x140299074  mov     r14, rax
0x140299077  call    cs:__imp_EngLockSurface
0x14029907e  nop     dword ptr [rax+rax+00h]
0x140299083  mov     r15, rax
0x140299086  test    rax, rax
0x140299089  jz      loc_14029916D
0x14029908f  mov     rdx, [rbx+30h]; hdev
0x140299093  xor     r8d, r8d; flHooks
0x140299096  mov     rcx, r14; hsurf
0x140299099  mov     [rbx+40h], rax
0x14029909d  call    cs:__imp_EngAssociateSurface
0x1402990a4  nop     dword ptr [rax+rax+00h]
0x1402990a9  test    eax, eax
0x1402990ab  jz      loc_14029916D
0x1402990b1  lea     rcx, [rbp+arg_8]
0x1402990b5  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1402990bc  nop     dword ptr [rax+rax+00h]
0x1402990c1  lea     rcx, [rbp+sizl]
0x1402990c5  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1402990cc  nop     dword ptr [rax+rax+00h]
0x1402990d1  lea     rcx, [rbp+arg_10]
0x1402990d5  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1402990dc  nop     dword ptr [rax+rax+00h]
0x1402990e1  cmp     qword ptr [rbp+sizl.cx], 0
0x1402990e6  jz      short loc_14029913D
0x1402990e8  cmp     [rbp+arg_8], 0
0x1402990ed  jz      short loc_14029913D
0x1402990ef  cmp     [rbp+arg_10], 0
0x1402990f4  jz      short loc_14029913D
0x1402990f6  lea     rcx, [rbp+arg_8]
0x1402990fa  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140299101  nop     dword ptr [rax+rax+00h]
0x140299106  lea     rcx, [rbp+sizl]
0x14029910a  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140299111  nop     dword ptr [rax+rax+00h]
0x140299116  mov     rax, [rbp+arg_8]
0x14029911a  xor     edx, edx; struct _RECTL *
0x14029911c  mov     [rbx+50h], rax
0x140299120  mov     rcx, rbx; struct DHPDEV__ *
0x140299123  mov     rax, qword ptr [rbp+sizl.cx]
0x140299127  mov     [rbx+58h], rax
0x14029912b  mov     rax, [rbp+arg_10]
0x14029912f  mov     [rbx+60h], rax
0x140299133  call    ?PanSynchronize@@YAXPEAUDHPDEV__@@PEAU_RECTL@@@Z; PanSynchronize(DHPDEV__ *,_RECTL *)
0x140299138  jmp     loc_1402991C4
0x14029913d  lea     rcx, [rbp+sizl]
0x140299141  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140299148  nop     dword ptr [rax+rax+00h]
0x14029914d  lea     rcx, [rbp+arg_8]
0x140299151  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140299158  nop     dword ptr [rax+rax+00h]
0x14029915d  lea     rcx, [rbp+arg_10]
0x140299161  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140299168  nop     dword ptr [rax+rax+00h]
0x14029916d  mov     rcx, r15; pso
0x140299170  call    cs:__imp_EngUnlockSurface
0x140299177  nop     dword ptr [rax+rax+00h]
0x14029917c  mov     rcx, r14; hsurf
0x14029917f  call    cs:__imp_EngDeleteSurface
0x140299186  nop     dword ptr [rax+rax+00h]
0x14029918b  mov     rcx, rdi; hsurf
0x14029918e  call    cs:__imp_EngDeleteSurface
0x140299195  nop     dword ptr [rax+rax+00h]
0x14029919a  mov     rcx, rsi; pso
0x14029919d  call    cs:__imp_EngUnlockSurface
0x1402991a4  nop     dword ptr [rax+rax+00h]
0x1402991a9  lea     rcx, [rbp+arg_18]; this
0x1402991ad  call    ?vUnLock@PANDEVLOCK@@QEAAXXZ; PANDEVLOCK::vUnLock(void)
0x1402991b2  mov     rax, [rbx+338h]
0x1402991b9  mov     rcx, [rbx+20h]
0x1402991bd  call    _guard_dispatch_icall
0x1402991c2  xor     edi, edi
0x1402991c4  lea     rcx, [rbp+arg_18]; this
0x1402991c8  call    ?vUnLock@PANDEVLOCK@@QEAAXXZ; PANDEVLOCK::vUnLock(void)
0x1402991cd  mov     rax, rdi
0x1402991d0  add     rsp, 48h
0x1402991d4  pop     r15
0x1402991d6  pop     r14
0x1402991d8  pop     rdi
0x1402991d9  pop     rsi
0x1402991da  pop     rbx
0x1402991db  pop     rbp
0x1402991dc  retn
```
