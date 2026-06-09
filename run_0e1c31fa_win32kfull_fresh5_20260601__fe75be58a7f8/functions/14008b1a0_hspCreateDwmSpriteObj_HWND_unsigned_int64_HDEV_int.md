# hspCreateDwmSpriteObj(HWND__ *,unsigned __int64,HDEV__ *,int)

- ea: `0x14008b1a0`
- end: `0x14008b5a4`
- name: `?hspCreateDwmSpriteObj@@YAPEAUHSPRITE__@@PEAUHWND__@@_KPEAUHDEV__@@H@Z`
- size: `1028`
- prototype: `HSPRITE __fastcall(HWND, unsigned __int64, HDEV, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14008acd0`
- `0x1401a46fc`

## callees

- `0x140087648`
- `0x14008a670`
- `0x14008b1a0`
- `0x14008b5ac`
- `0x14008b700`
- `0x14016a0a0`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTable` at `0x14008b3bd`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14008b3bd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b1e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b315`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b453`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b1e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b315`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b453`
- `win32kbase!PopThreadGuardedObject` at `0x14008b382`
- `win32kbase!PopThreadGuardedObject` at `0x14008b496`
- `win32kbase!PopThreadGuardedObject` at `0x14008b4db`
- `win32kbase!PopThreadGuardedObject` at `0x14008b382`
- `win32kbase!PopThreadGuardedObject` at `0x14008b496`
- `win32kbase!PopThreadGuardedObject` at `0x14008b4db`
- `win32kbase!PushThreadGuardedObject` at `0x14008b254`
- `win32kbase!PushThreadGuardedObject` at `0x14008b304`
- `win32kbase!PushThreadGuardedObject` at `0x14008b43d`
- `win32kbase!PushThreadGuardedObject` at `0x14008b254`
- `win32kbase!PushThreadGuardedObject` at `0x14008b304`
- `win32kbase!PushThreadGuardedObject` at `0x14008b43d`
- `win32kbase!GreInitializePushLock` at `0x14008b4f2`
- `win32kbase!GreInitializePushLock` at `0x14008b4f2`
- `win32kbase!AllocateObject` at `0x14008b204`
- `win32kbase!AllocateObject` at `0x14008b204`
- `win32kbase!HmgInsertObjectInternal` at `0x14008b276`
- `win32kbase!HmgInsertObjectInternal` at `0x14008b276`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008b32d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008b46b`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008b32d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008b46b`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008b3f1`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008b3f1`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008b4a6`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008b4a6`
- `win32kbase!HmgMarkUndeletable` at `0x14008b299`
- `win32kbase!HmgMarkUndeletable` at `0x14008b299`
- `win32kbase!EtwDwmSpriteCreateEvent` at `0x14008b3dd`
- `win32kbase!EtwDwmSpriteCreateEvent` at `0x14008b3dd`

## pseudocode

```c
__int64 __fastcall hspCreateDwmSpriteObj(Gre::Base *a1, __int64 a2, HDEV a3, int a4)
{
  int v4; // r15d
  __int64 v7; // r12
  struct Gre::Base::SESSION_GLOBALS *v8; // r14
  _QWORD *Object; // rax
  _QWORD *v10; // rbx
  _QWORD *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  HSPRITE v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rax
  HSPRITE NeighborSprite; // r15
  Gre::Base *v20; // rcx
  struct Gre::Base::SESSION_GLOBALS *v21; // rax
  __int64 v22; // r8
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  struct _RTL_GENERIC_TABLE *v26; // rcx
  HLSURF LogicalSurfaceObject; // rdi
  Gre::Base *v28; // rcx
  struct Gre::Base::SESSION_GLOBALS *v29; // rax
  __int64 v30; // r8
  HDEV v31; // rdx
  __int64 v33; // rax
  __int64 v34; // rcx
  unsigned __int8 NewElement[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v36; // [rsp+24h] [rbp-DCh]
  __int128 v37; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v38; // [rsp+38h] [rbp-C8h]
  struct SFMLOGICALSURFACE *v39; // [rsp+48h] [rbp-B8h]
  int v40; // [rsp+50h] [rbp-B0h]
  __int64 v41; // [rsp+58h] [rbp-A8h]
  _OWORD v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int16 *v43; // [rsp+80h] [rbp-80h]
  char v44; // [rsp+88h] [rbp-78h]
  _QWORD Buffer[2]; // [rsp+90h] [rbp-70h] BYREF
  Gre::Base *v46; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v47; // [rsp+A8h] [rbp-58h]
  _BYTE v48[96]; // [rsp+C0h] [rbp-40h] BYREF

  v36 = a4;
  v47 = 0;
  v4 = a4;
  v41 = a2;
  v7 = 0;
  v8 = Gre::Base::Globals(a1);
  Object = AllocateObject(v8, 0x98u, 0xFu);
  v10 = Object;
  if ( !Object )
    return v7;
  v11 = Object + 3;
  NewElement[0] = 0;
  Object[4] = Object + 3;
  Object[3] = Object + 3;
  v12 = *((_QWORD *)v8 + 28);
  v42[0] = 0;
  ++*(_DWORD *)(v12 + 96);
  v42[1] = 0;
  PushThreadGuardedObject(
    v42,
    v42,
    UnexpectedThreadTerminationHandler<HmgInsertObjectHelper>::OnUnexpectedThreadTerminationStatic);
  v43 = 0;
  v44 = 0;
  if ( !HmgInsertObjectInternal(v8, v10, 9u, 0xFu) )
  {
LABEL_18:
    if ( NewElement[0] )
      goto LABEL_19;
    goto LABEL_26;
  }
  v14 = *v10;
  LOBYTE(v13) = 15;
  v43 = (volatile signed __int16 *)v10;
  NewElement[0] = 1;
  HmgMarkUndeletable(v14, v13);
  v15 = *((_QWORD *)v8 + 28);
  v16 = *(HSPRITE *)(v15 + 144);
  if ( v16 )
  {
    NeighborSprite = hspGetNeighborSprite(v16, 0, 0);
    if ( NeighborSprite )
    {
      v37 = 0;
      v38 = 0;
      PushThreadGuardedObject(
        &v37,
        &v37,
        UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
      v39 = 0;
      v21 = Gre::Base::Globals(v20);
      LOBYTE(v22) = 15;
      v39 = (struct SFMLOGICALSURFACE *)HmgLock(v21, NeighborSprite, v22);
      v23 = ((unsigned __int64)v39 + 24) & -(__int64)(v39 != 0);
      v24 = *(_QWORD *)v23;
      if ( *(_QWORD *)(*(_QWORD *)v23 + 8LL) == v23 )
      {
        *v11 = v24;
        v11[1] = v23;
        *(_QWORD *)(v24 + 8) = v11;
        *(_QWORD *)v23 = v11;
        if ( v39 )
          _InterlockedDecrement16((volatile signed __int16 *)v39 + 6);
        v39 = 0;
        PopThreadGuardedObject(&v37);
        goto LABEL_11;
      }
    }
    else
    {
      v33 = *((_QWORD *)v8 + 28) + 80LL;
      v34 = *(_QWORD *)v33;
      if ( *(_QWORD *)(*(_QWORD *)v33 + 8LL) == v33 )
      {
        *v11 = v34;
        v11[1] = v33;
        *(_QWORD *)(v34 + 8) = v11;
        *(_QWORD *)v33 = v11;
LABEL_11:
        v4 = v36;
        goto LABEL_12;
      }
    }
LABEL_5:
    __fastfail(3u);
  }
  v17 = *(_QWORD **)(v15 + 88);
  v18 = v15 + 80;
  if ( *v17 != v18 )
    goto LABEL_5;
  *v11 = v18;
  v11[1] = v17;
  *v17 = v11;
  *(_QWORD *)(v18 + 8) = v11;
LABEL_12:
  if ( a1 )
  {
    v25 = *v10;
    v10[5] = a1;
    v26 = (struct _RTL_GENERIC_TABLE *)*((_QWORD *)v8 + 28);
    Buffer[1] = v25;
    Buffer[0] = a1;
    RtlInsertElementGenericTable(v26, Buffer, 0x10u, NewElement);
  }
  if ( NewElement[0] )
  {
    EtwDwmSpriteCreateEvent(a1, *v10);
    v46 = a1;
    ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v48);
    LogicalSurfaceObject = hlsurfCreateLogicalSurfaceObject(
                             a3,
                             (unsigned int)(v4 != 0) + 4,
                             (struct _CD_HLSURF_CREATIONCONTEXT *)&v46);
    if ( LogicalSurfaceObject )
    {
      v37 = 0;
      v38 = 0;
      PushThreadGuardedObject(
        &v37,
        &v37,
        UnexpectedThreadTerminationHandler<SFMLOGICALSURFACEREF>::OnUnexpectedThreadTerminationStatic);
      v39 = 0;
      v40 = 0;
      v29 = Gre::Base::Globals(v28);
      LOBYTE(v30) = 18;
      v39 = (struct SFMLOGICALSURFACE *)HmgLock(v29, LogicalSurfaceObject, v30);
      DWMSPRITE::SetLogicalSurface((DWMSPRITE *)v10, v31, v39);
      SFMLOGICALSURFACEREF_vDestructor(&v37);
      PopThreadGuardedObject(&v37);
    }
    else
    {
      NewElement[0] = 0;
    }
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v48);
    goto LABEL_18;
  }
LABEL_26:
  _InterlockedAdd16((volatile signed __int16 *)v10 + 6, 1u);
LABEL_19:
  if ( v43 && !v44 )
    _InterlockedDecrement16(v43 + 6);
  PopThreadGuardedObject(v42);
  if ( NewElement[0] )
  {
    GreInitializePushLock((struct W32_PUSH_LOCK *)(v10 + 11));
    v7 = *v10;
    v10[6] = v41;
  }
  else
  {
    vspDestroyDwmSpriteObjInternal(a3, 1, (struct DWMSPRITE *)v10);
  }
  return v7;
}

```

## disassembly

```asm
0x14008b1a0  mov     [rsp-8+arg_8], rbx
0x14008b1a5  push    rbp
0x14008b1a6  push    rsi
0x14008b1a7  push    rdi
0x14008b1a8  push    r12
0x14008b1aa  push    r13
0x14008b1ac  push    r14
0x14008b1ae  push    r15
0x14008b1b0  lea     rbp, [rsp-30h]
0x14008b1b5  sub     rsp, 130h
0x14008b1bc  mov     rax, cs:__security_cookie
0x14008b1c3  xor     rax, rsp
0x14008b1c6  mov     [rbp+60h+var_40], rax
0x14008b1ca  xorps   xmm0, xmm0
0x14008b1cd  mov     [rsp+160h+var_13C], r9d
0x14008b1d2  movdqu  [rbp+60h+var_B8], xmm0
0x14008b1d7  mov     r15d, r9d
0x14008b1da  mov     [rsp+160h+var_108], rdx
0x14008b1df  mov     r13, r8
0x14008b1e2  mov     rsi, rcx
0x14008b1e5  xor     r12d, r12d
0x14008b1e8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008b1ef  nop     dword ptr [rax+rax+00h]
0x14008b1f4  mov     edx, 98h
0x14008b1f9  lea     r8d, [r12+0Fh]
0x14008b1fe  mov     rcx, rax
0x14008b201  mov     r14, rax
0x14008b204  call    cs:__imp_?AllocateObject@@YAPEAXAEAUSESSION_GLOBALS@Base@Gre@@KK@Z; AllocateObject(Gre::Base::SESSION_GLOBALS &,ulong,ulong)
0x14008b20b  nop     dword ptr [rax+rax+00h]
0x14008b210  mov     rbx, rax
0x14008b213  test    rax, rax
0x14008b216  jz      loc_14008B50A
0x14008b21c  lea     rdi, [rax+18h]
0x14008b220  mov     [rsp+160h+NewElement], r12b
0x14008b225  mov     [rdi+8], rdi
0x14008b229  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VHmgInsertObjectHelper@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgInsertObjectHelper>::OnUnexpectedThreadTerminationStatic(void *)
0x14008b230  mov     [rdi], rdi
0x14008b233  lea     rdx, [rsp+160h+var_100]
0x14008b238  mov     rax, [r14+0E0h]
0x14008b23f  lea     rcx, [rsp+160h+var_100]
0x14008b244  xorps   xmm0, xmm0
0x14008b247  movups  [rsp+160h+var_100], xmm0
0x14008b24c  inc     dword ptr [rax+60h]
0x14008b24f  movups  [rsp+160h+var_F0], xmm0
0x14008b254  call    cs:__imp_PushThreadGuardedObject
0x14008b25b  nop     dword ptr [rax+rax+00h]
0x14008b260  mov     r9b, 0Fh
0x14008b263  mov     [rbp+60h+var_E0], r12
0x14008b267  lea     r8d, [r12+9]
0x14008b26c  mov     [rbp+60h+var_D8], r12b
0x14008b270  mov     rdx, rbx
0x14008b273  mov     rcx, r14
0x14008b276  call    cs:__imp_?HmgInsertObjectInternal@@YAPEAUHOBJ__@@AEAUSESSION_GLOBALS@Base@Gre@@PEAXKE@Z; HmgInsertObjectInternal(Gre::Base::SESSION_GLOBALS &,void *,ulong,uchar)
0x14008b27d  nop     dword ptr [rax+rax+00h]
0x14008b282  test    rax, rax
0x14008b285  jz      loc_14008B535
0x14008b28b  mov     rcx, [rbx]
0x14008b28e  mov     dl, 0Fh
0x14008b290  mov     [rbp+60h+var_E0], rbx
0x14008b294  mov     [rsp+160h+NewElement], 1
0x14008b299  call    cs:__imp_HmgMarkUndeletable
0x14008b2a0  nop     dword ptr [rax+rax+00h]
0x14008b2a5  mov     rax, [r14+0E0h]
0x14008b2ac  mov     rcx, [rax+90h]; HSPRITE
0x14008b2b3  test    rcx, rcx
0x14008b2b6  jnz     short loc_14008B2D0
0x14008b2b8  mov     rcx, [rax+58h]
0x14008b2bc  add     rax, 50h ; 'P'
0x14008b2c0  cmp     [rcx], rax
0x14008b2c3  jz      loc_14008B587
0x14008b2c9  mov     ecx, 3
0x14008b2ce  int     29h; Win8: RtlFailFast(ecx)
0x14008b2d0  xor     r8d, r8d; bool
0x14008b2d3  xor     edx, edx; bool
0x14008b2d5  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x14008b2da  mov     r15, rax
0x14008b2dd  test    rax, rax
0x14008b2e0  jz      loc_14008B55C
0x14008b2e6  xorps   xmm0, xmm0
0x14008b2e9  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14008b2f0  lea     rdx, [rsp+160h+var_138]
0x14008b2f5  lea     rcx, [rsp+160h+var_138]
0x14008b2fa  movups  [rsp+160h+var_138], xmm0
0x14008b2ff  movups  [rsp+160h+var_128], xmm0
0x14008b304  call    cs:__imp_PushThreadGuardedObject
0x14008b30b  nop     dword ptr [rax+rax+00h]
0x14008b310  mov     [rsp+160h+var_118], r12
0x14008b315  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008b31c  nop     dword ptr [rax+rax+00h]
0x14008b321  xor     r9d, r9d
0x14008b324  mov     r8b, 0Fh
0x14008b327  mov     rcx, rax
0x14008b32a  mov     rdx, r15
0x14008b32d  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14008b334  nop     dword ptr [rax+rax+00h]
0x14008b339  mov     rcx, rax
0x14008b33c  mov     [rsp+160h+var_118], rax
0x14008b341  add     rax, 18h
0x14008b345  neg     rcx
0x14008b348  sbb     rdx, rdx
0x14008b34b  and     rdx, rax
0x14008b34e  mov     rax, [rdx]
0x14008b351  cmp     [rax+8], rdx
0x14008b355  jnz     loc_14008B2C9
0x14008b35b  mov     [rdi], rax
0x14008b35e  mov     [rdi+8], rdx
0x14008b362  mov     [rax+8], rdi
0x14008b366  mov     [rdx], rdi
0x14008b369  mov     rax, [rsp+160h+var_118]
0x14008b36e  test    rax, rax
0x14008b371  jz      short loc_14008B378
0x14008b373  lock dec word ptr [rax+0Ch]
0x14008b378  lea     rcx, [rsp+160h+var_138]
0x14008b37d  mov     [rsp+160h+var_118], r12
0x14008b382  call    cs:__imp_PopThreadGuardedObject
0x14008b389  nop     dword ptr [rax+rax+00h]
0x14008b38e  mov     r15d, [rsp+160h+var_13C]
0x14008b393  test    rsi, rsi
0x14008b396  jz      short loc_14008B3C9
0x14008b398  mov     rax, [rbx]
0x14008b39b  lea     r9, [rsp+160h+NewElement]; NewElement
0x14008b3a0  mov     [rbx+28h], rsi
0x14008b3a4  lea     rdx, [rbp+60h+Buffer]; Buffer
0x14008b3a8  mov     rcx, [r14+0E0h]; Table
0x14008b3af  mov     r8d, 10h; BufferSize
0x14008b3b5  mov     [rbp+60h+var_C8], rax
0x14008b3b9  mov     [rbp+60h+Buffer], rsi
0x14008b3bd  call    cs:__imp_RtlInsertElementGenericTable
0x14008b3c4  nop     dword ptr [rax+rax+00h]
0x14008b3c9  xor     r14d, r14d
0x14008b3cc  cmp     [rsp+160h+NewElement], r14b
0x14008b3d1  jz      loc_14008B53D
0x14008b3d7  mov     rdx, [rbx]
0x14008b3da  mov     rcx, rsi
0x14008b3dd  call    cs:__imp_EtwDwmSpriteCreateEvent
0x14008b3e4  nop     dword ptr [rax+rax+00h]
0x14008b3e9  lea     rcx, [rbp+60h+var_A0]
0x14008b3ed  mov     [rbp+60h+var_C0], rsi
0x14008b3f1  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x14008b3f8  nop     dword ptr [rax+rax+00h]
0x14008b3fd  neg     r15d
0x14008b400  lea     r8, [rbp+60h+var_C0]; struct _CD_HLSURF_CREATIONCONTEXT *
0x14008b404  mov     rcx, r13; HDEV
0x14008b407  sbb     edx, edx
0x14008b409  neg     edx
0x14008b40b  add     edx, 4; unsigned int
0x14008b40e  call    ?hlsurfCreateLogicalSurfaceObject@@YAPEAUHLSURF__@@QEAUHDEV__@@KPEAU_CD_HLSURF_CREATIONCONTEXT@@@Z; hlsurfCreateLogicalSurfaceObject(HDEV__ * const,ulong,_CD_HLSURF_CREATIONCONTEXT *)
0x14008b413  mov     rdi, rax
0x14008b416  test    rax, rax
0x14008b419  jz      loc_14008B59A
0x14008b41f  xorps   xmm0, xmm0
0x14008b422  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VSFMLOGICALSURFACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<SFMLOGICALSURFACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14008b429  lea     rdx, [rsp+160h+var_138]
0x14008b42e  lea     rcx, [rsp+160h+var_138]
0x14008b433  movups  [rsp+160h+var_138], xmm0
0x14008b438  movups  [rsp+160h+var_128], xmm0
0x14008b43d  call    cs:__imp_PushThreadGuardedObject
0x14008b444  nop     dword ptr [rax+rax+00h]
0x14008b449  mov     [rsp+160h+var_118], r14
0x14008b44e  mov     [rsp+160h+var_110], r14d
0x14008b453  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008b45a  nop     dword ptr [rax+rax+00h]
0x14008b45f  xor     r9d, r9d
0x14008b462  mov     r8b, 12h
0x14008b465  mov     rcx, rax
0x14008b468  mov     rdx, rdi
0x14008b46b  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14008b472  nop     dword ptr [rax+rax+00h]
0x14008b477  mov     r8, rax; struct SFMLOGICALSURFACE *
0x14008b47a  mov     [rsp+160h+var_118], rax
0x14008b47f  mov     rcx, rbx; this
0x14008b482  call    ?SetLogicalSurface@DWMSPRITE@@QEAAXPEAUHDEV__@@PEAVSFMLOGICALSURFACE@@@Z; DWMSPRITE::SetLogicalSurface(HDEV__ *,SFMLOGICALSURFACE *)
0x14008b487  lea     rcx, [rsp+160h+var_138]
0x14008b48c  call    SFMLOGICALSURFACEREF_vDestructor
0x14008b491  lea     rcx, [rsp+160h+var_138]
0x14008b496  call    cs:__imp_PopThreadGuardedObject
0x14008b49d  nop     dword ptr [rax+rax+00h]
0x14008b4a2  lea     rcx, [rbp+60h+var_A0]
0x14008b4a6  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14008b4ad  nop     dword ptr [rax+rax+00h]
0x14008b4b2  cmp     [rsp+160h+NewElement], r14b
0x14008b4b7  jz      loc_14008B53D
0x14008b4bd  mov     edi, 1
0x14008b4c2  mov     rax, [rbp+60h+var_E0]
0x14008b4c6  test    rax, rax
0x14008b4c9  jz      short loc_14008B4D6
0x14008b4cb  cmp     [rbp+60h+var_D8], r14b
0x14008b4cf  jnz     short loc_14008B4D6
0x14008b4d1  lock dec word ptr [rax+0Ch]
0x14008b4d6  lea     rcx, [rsp+160h+var_100]
0x14008b4db  call    cs:__imp_PopThreadGuardedObject
0x14008b4e2  nop     dword ptr [rax+rax+00h]
0x14008b4e7  cmp     [rsp+160h+NewElement], r14b
0x14008b4ec  jz      short loc_14008B54C
0x14008b4ee  lea     rcx, [rbx+58h]
0x14008b4f2  call    cs:__imp_?GreInitializePushLock@@YAXPEAVW32_PUSH_LOCK@@@Z; GreInitializePushLock(W32_PUSH_LOCK *)
0x14008b4f9  nop     dword ptr [rax+rax+00h]
0x14008b4fe  mov     rax, [rsp+160h+var_108]
0x14008b503  mov     r12, [rbx]
0x14008b506  mov     [rbx+30h], rax
0x14008b50a  mov     rax, r12
0x14008b50d  mov     rcx, [rbp+60h+var_40]
0x14008b511  xor     rcx, rsp; StackCookie
0x14008b514  call    __security_check_cookie
0x14008b519  mov     rbx, [rsp+160h+arg_8]
0x14008b521  add     rsp, 130h
0x14008b528  pop     r15
0x14008b52a  pop     r14
0x14008b52c  pop     r13
0x14008b52e  pop     r12
0x14008b530  pop     rdi
0x14008b531  pop     rsi
0x14008b532  pop     rbp
0x14008b533  retn
0x14008b535  xor     r14d, r14d
0x14008b538  jmp     loc_14008B4B2
0x14008b53d  mov     edi, 1
0x14008b542  lock add [rbx+0Ch], di
0x14008b547  jmp     loc_14008B4C2
0x14008b54c  mov     r8, rbx; struct DWMSPRITE *
0x14008b54f  mov     dl, dil; bool
0x14008b552  mov     rcx, r13; HDEV
0x14008b555  call    ?vspDestroyDwmSpriteObjInternal@@YAXPEAUHDEV__@@_NPEAVDWMSPRITE@@@Z; vspDestroyDwmSpriteObjInternal(HDEV__ *,bool,DWMSPRITE *)
0x14008b55a  jmp     short loc_14008B50A
0x14008b55c  mov     rax, [r14+0E0h]
0x14008b563  add     rax, 50h ; 'P'
0x14008b567  mov     rcx, [rax]
0x14008b56a  cmp     [rcx+8], rax
0x14008b56e  jnz     loc_14008B2C9
0x14008b574  mov     [rdi], rcx
0x14008b577  mov     [rdi+8], rax
0x14008b57b  mov     [rcx+8], rdi
0x14008b57f  mov     [rax], rdi
0x14008b582  jmp     loc_14008B38E
0x14008b587  mov     [rdi], rax
0x14008b58a  mov     [rdi+8], rcx
0x14008b58e  mov     [rcx], rdi
0x14008b591  mov     [rax+8], rdi
0x14008b595  jmp     loc_14008B393
0x14008b59a  mov     [rsp+160h+NewElement], r14b
0x14008b59f  jmp     loc_14008B4A2
```
