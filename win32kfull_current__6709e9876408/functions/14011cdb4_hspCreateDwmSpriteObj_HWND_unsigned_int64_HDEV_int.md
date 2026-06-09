# hspCreateDwmSpriteObj(HWND__ *,unsigned __int64,HDEV__ *,int)

- ea: `0x14011cdb4`
- end: `0x14011d1b8`
- name: `?hspCreateDwmSpriteObj@@YAPEAUHSPRITE__@@PEAUHWND__@@_KPEAUHDEV__@@H@Z`
- size: `1028`
- prototype: `HSPRITE(HWND, unsigned __int64, HDEV, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14011c8e4`
- `0x14012273c`

## callees

- `0x140016bb4`
- `0x140112d58`
- `0x14011cdb4`
- `0x14011d1c0`
- `0x14011d314`
- `0x14011dee4`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTable` at `0x14011cfd1`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14011cfd1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011cdfc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011cf29`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d067`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011cdfc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011cf29`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d067`
- `win32kbase!PopThreadGuardedObject` at `0x14011cf96`
- `win32kbase!PopThreadGuardedObject` at `0x14011d0aa`
- `win32kbase!PopThreadGuardedObject` at `0x14011d0ef`
- `win32kbase!PopThreadGuardedObject` at `0x14011cf96`
- `win32kbase!PopThreadGuardedObject` at `0x14011d0aa`
- `win32kbase!PopThreadGuardedObject` at `0x14011d0ef`
- `win32kbase!PushThreadGuardedObject` at `0x14011ce68`
- `win32kbase!PushThreadGuardedObject` at `0x14011cf18`
- `win32kbase!PushThreadGuardedObject` at `0x14011d051`
- `win32kbase!PushThreadGuardedObject` at `0x14011ce68`
- `win32kbase!PushThreadGuardedObject` at `0x14011cf18`
- `win32kbase!PushThreadGuardedObject` at `0x14011d051`
- `win32kbase!GreInitializePushLock` at `0x14011d106`
- `win32kbase!GreInitializePushLock` at `0x14011d106`
- `win32kbase!AllocateObject` at `0x14011ce18`
- `win32kbase!AllocateObject` at `0x14011ce18`
- `win32kbase!HmgInsertObjectInternal` at `0x14011ce8a`
- `win32kbase!HmgInsertObjectInternal` at `0x14011ce8a`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011cf41`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011d07f`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011cf41`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011d07f`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011d005`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011d005`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011d0ba`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011d0ba`
- `win32kbase!HmgMarkUndeletable` at `0x14011cead`
- `win32kbase!HmgMarkUndeletable` at `0x14011cead`
- `win32kbase!EtwDwmSpriteCreateEvent` at `0x14011cff1`
- `win32kbase!EtwDwmSpriteCreateEvent` at `0x14011cff1`

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
0x14011cdb4  mov     [rsp-8+arg_8], rbx
0x14011cdb9  push    rbp
0x14011cdba  push    rsi
0x14011cdbb  push    rdi
0x14011cdbc  push    r12
0x14011cdbe  push    r13
0x14011cdc0  push    r14
0x14011cdc2  push    r15
0x14011cdc4  lea     rbp, [rsp-30h]
0x14011cdc9  sub     rsp, 130h
0x14011cdd0  mov     rax, cs:__security_cookie
0x14011cdd7  xor     rax, rsp
0x14011cdda  mov     [rbp+60h+var_40], rax
0x14011cdde  xorps   xmm0, xmm0
0x14011cde1  mov     [rsp+160h+var_13C], r9d
0x14011cde6  movdqu  [rbp+60h+var_B8], xmm0
0x14011cdeb  mov     r15d, r9d
0x14011cdee  mov     [rsp+160h+var_108], rdx
0x14011cdf3  mov     r13, r8
0x14011cdf6  mov     rsi, rcx
0x14011cdf9  xor     r12d, r12d
0x14011cdfc  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011ce03  nop     dword ptr [rax+rax+00h]
0x14011ce08  mov     edx, 98h
0x14011ce0d  lea     r8d, [r12+0Fh]
0x14011ce12  mov     rcx, rax
0x14011ce15  mov     r14, rax
0x14011ce18  call    cs:__imp_?AllocateObject@@YAPEAXAEAUSESSION_GLOBALS@Base@Gre@@KK@Z; AllocateObject(Gre::Base::SESSION_GLOBALS &,ulong,ulong)
0x14011ce1f  nop     dword ptr [rax+rax+00h]
0x14011ce24  mov     rbx, rax
0x14011ce27  test    rax, rax
0x14011ce2a  jz      loc_14011D11E
0x14011ce30  lea     rdi, [rax+18h]
0x14011ce34  mov     [rsp+160h+NewElement], r12b
0x14011ce39  mov     [rdi+8], rdi
0x14011ce3d  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VHmgInsertObjectHelper@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgInsertObjectHelper>::OnUnexpectedThreadTerminationStatic(void *)
0x14011ce44  mov     [rdi], rdi
0x14011ce47  lea     rdx, [rsp+160h+var_100]
0x14011ce4c  mov     rax, [r14+0E0h]
0x14011ce53  lea     rcx, [rsp+160h+var_100]
0x14011ce58  xorps   xmm0, xmm0
0x14011ce5b  movups  [rsp+160h+var_100], xmm0
0x14011ce60  inc     dword ptr [rax+60h]
0x14011ce63  movups  [rsp+160h+var_F0], xmm0
0x14011ce68  call    cs:__imp_PushThreadGuardedObject
0x14011ce6f  nop     dword ptr [rax+rax+00h]
0x14011ce74  mov     r9b, 0Fh
0x14011ce77  mov     [rbp+60h+var_E0], r12
0x14011ce7b  lea     r8d, [r12+9]
0x14011ce80  mov     [rbp+60h+var_D8], r12b
0x14011ce84  mov     rdx, rbx
0x14011ce87  mov     rcx, r14
0x14011ce8a  call    cs:__imp_?HmgInsertObjectInternal@@YAPEAUHOBJ__@@AEAUSESSION_GLOBALS@Base@Gre@@PEAXKE@Z; HmgInsertObjectInternal(Gre::Base::SESSION_GLOBALS &,void *,ulong,uchar)
0x14011ce91  nop     dword ptr [rax+rax+00h]
0x14011ce96  test    rax, rax
0x14011ce99  jz      loc_14011D149
0x14011ce9f  mov     rcx, [rbx]
0x14011cea2  mov     dl, 0Fh
0x14011cea4  mov     [rbp+60h+var_E0], rbx
0x14011cea8  mov     [rsp+160h+NewElement], 1
0x14011cead  call    cs:__imp_HmgMarkUndeletable
0x14011ceb4  nop     dword ptr [rax+rax+00h]
0x14011ceb9  mov     rax, [r14+0E0h]
0x14011cec0  mov     rcx, [rax+90h]; HSPRITE
0x14011cec7  test    rcx, rcx
0x14011ceca  jnz     short loc_14011CEE4
0x14011cecc  mov     rcx, [rax+58h]
0x14011ced0  add     rax, 50h ; 'P'
0x14011ced4  cmp     [rcx], rax
0x14011ced7  jz      loc_14011D19B
0x14011cedd  mov     ecx, 3
0x14011cee2  int     29h; Win8: RtlFailFast(ecx)
0x14011cee4  xor     r8d, r8d; bool
0x14011cee7  xor     edx, edx; bool
0x14011cee9  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x14011ceee  mov     r15, rax
0x14011cef1  test    rax, rax
0x14011cef4  jz      loc_14011D170
0x14011cefa  xorps   xmm0, xmm0
0x14011cefd  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14011cf04  lea     rdx, [rsp+160h+var_138]
0x14011cf09  lea     rcx, [rsp+160h+var_138]
0x14011cf0e  movups  [rsp+160h+var_138], xmm0
0x14011cf13  movups  [rsp+160h+var_128], xmm0
0x14011cf18  call    cs:__imp_PushThreadGuardedObject
0x14011cf1f  nop     dword ptr [rax+rax+00h]
0x14011cf24  mov     [rsp+160h+var_118], r12
0x14011cf29  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011cf30  nop     dword ptr [rax+rax+00h]
0x14011cf35  xor     r9d, r9d
0x14011cf38  mov     r8b, 0Fh
0x14011cf3b  mov     rcx, rax
0x14011cf3e  mov     rdx, r15
0x14011cf41  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14011cf48  nop     dword ptr [rax+rax+00h]
0x14011cf4d  mov     rcx, rax
0x14011cf50  mov     [rsp+160h+var_118], rax
0x14011cf55  add     rax, 18h
0x14011cf59  neg     rcx
0x14011cf5c  sbb     rdx, rdx
0x14011cf5f  and     rdx, rax
0x14011cf62  mov     rax, [rdx]
0x14011cf65  cmp     [rax+8], rdx
0x14011cf69  jnz     loc_14011CEDD
0x14011cf6f  mov     [rdi], rax
0x14011cf72  mov     [rdi+8], rdx
0x14011cf76  mov     [rax+8], rdi
0x14011cf7a  mov     [rdx], rdi
0x14011cf7d  mov     rax, [rsp+160h+var_118]
0x14011cf82  test    rax, rax
0x14011cf85  jz      short loc_14011CF8C
0x14011cf87  lock dec word ptr [rax+0Ch]
0x14011cf8c  lea     rcx, [rsp+160h+var_138]
0x14011cf91  mov     [rsp+160h+var_118], r12
0x14011cf96  call    cs:__imp_PopThreadGuardedObject
0x14011cf9d  nop     dword ptr [rax+rax+00h]
0x14011cfa2  mov     r15d, [rsp+160h+var_13C]
0x14011cfa7  test    rsi, rsi
0x14011cfaa  jz      short loc_14011CFDD
0x14011cfac  mov     rax, [rbx]
0x14011cfaf  lea     r9, [rsp+160h+NewElement]; NewElement
0x14011cfb4  mov     [rbx+28h], rsi
0x14011cfb8  lea     rdx, [rbp+60h+Buffer]; Buffer
0x14011cfbc  mov     rcx, [r14+0E0h]; Table
0x14011cfc3  mov     r8d, 10h; BufferSize
0x14011cfc9  mov     [rbp+60h+var_C8], rax
0x14011cfcd  mov     [rbp+60h+Buffer], rsi
0x14011cfd1  call    cs:__imp_RtlInsertElementGenericTable
0x14011cfd8  nop     dword ptr [rax+rax+00h]
0x14011cfdd  xor     r14d, r14d
0x14011cfe0  cmp     [rsp+160h+NewElement], r14b
0x14011cfe5  jz      loc_14011D151
0x14011cfeb  mov     rdx, [rbx]
0x14011cfee  mov     rcx, rsi
0x14011cff1  call    cs:__imp_EtwDwmSpriteCreateEvent
0x14011cff8  nop     dword ptr [rax+rax+00h]
0x14011cffd  lea     rcx, [rbp+60h+var_A0]
0x14011d001  mov     [rbp+60h+var_C0], rsi
0x14011d005  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x14011d00c  nop     dword ptr [rax+rax+00h]
0x14011d011  neg     r15d
0x14011d014  lea     r8, [rbp+60h+var_C0]; struct _CD_HLSURF_CREATIONCONTEXT *
0x14011d018  mov     rcx, r13; HDEV
0x14011d01b  sbb     edx, edx
0x14011d01d  neg     edx
0x14011d01f  add     edx, 4; unsigned int
0x14011d022  call    ?hlsurfCreateLogicalSurfaceObject@@YAPEAUHLSURF__@@QEAUHDEV__@@KPEAU_CD_HLSURF_CREATIONCONTEXT@@@Z; hlsurfCreateLogicalSurfaceObject(HDEV__ * const,ulong,_CD_HLSURF_CREATIONCONTEXT *)
0x14011d027  mov     rdi, rax
0x14011d02a  test    rax, rax
0x14011d02d  jz      loc_14011D1AE
0x14011d033  xorps   xmm0, xmm0
0x14011d036  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VSFMLOGICALSURFACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<SFMLOGICALSURFACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14011d03d  lea     rdx, [rsp+160h+var_138]
0x14011d042  lea     rcx, [rsp+160h+var_138]
0x14011d047  movups  [rsp+160h+var_138], xmm0
0x14011d04c  movups  [rsp+160h+var_128], xmm0
0x14011d051  call    cs:__imp_PushThreadGuardedObject
0x14011d058  nop     dword ptr [rax+rax+00h]
0x14011d05d  mov     [rsp+160h+var_118], r14
0x14011d062  mov     [rsp+160h+var_110], r14d
0x14011d067  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011d06e  nop     dword ptr [rax+rax+00h]
0x14011d073  xor     r9d, r9d
0x14011d076  mov     r8b, 12h
0x14011d079  mov     rcx, rax
0x14011d07c  mov     rdx, rdi
0x14011d07f  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14011d086  nop     dword ptr [rax+rax+00h]
0x14011d08b  mov     r8, rax; struct SFMLOGICALSURFACE *
0x14011d08e  mov     [rsp+160h+var_118], rax
0x14011d093  mov     rcx, rbx; this
0x14011d096  call    ?SetLogicalSurface@DWMSPRITE@@QEAAXPEAUHDEV__@@PEAVSFMLOGICALSURFACE@@@Z; DWMSPRITE::SetLogicalSurface(HDEV__ *,SFMLOGICALSURFACE *)
0x14011d09b  lea     rcx, [rsp+160h+var_138]
0x14011d0a0  call    SFMLOGICALSURFACEREF_vDestructor
0x14011d0a5  lea     rcx, [rsp+160h+var_138]
0x14011d0aa  call    cs:__imp_PopThreadGuardedObject
0x14011d0b1  nop     dword ptr [rax+rax+00h]
0x14011d0b6  lea     rcx, [rbp+60h+var_A0]
0x14011d0ba  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14011d0c1  nop     dword ptr [rax+rax+00h]
0x14011d0c6  cmp     [rsp+160h+NewElement], r14b
0x14011d0cb  jz      loc_14011D151
0x14011d0d1  mov     edi, 1
0x14011d0d6  mov     rax, [rbp+60h+var_E0]
0x14011d0da  test    rax, rax
0x14011d0dd  jz      short loc_14011D0EA
0x14011d0df  cmp     [rbp+60h+var_D8], r14b
0x14011d0e3  jnz     short loc_14011D0EA
0x14011d0e5  lock dec word ptr [rax+0Ch]
0x14011d0ea  lea     rcx, [rsp+160h+var_100]
0x14011d0ef  call    cs:__imp_PopThreadGuardedObject
0x14011d0f6  nop     dword ptr [rax+rax+00h]
0x14011d0fb  cmp     [rsp+160h+NewElement], r14b
0x14011d100  jz      short loc_14011D160
0x14011d102  lea     rcx, [rbx+58h]
0x14011d106  call    cs:__imp_?GreInitializePushLock@@YAXPEAVW32_PUSH_LOCK@@@Z; GreInitializePushLock(W32_PUSH_LOCK *)
0x14011d10d  nop     dword ptr [rax+rax+00h]
0x14011d112  mov     rax, [rsp+160h+var_108]
0x14011d117  mov     r12, [rbx]
0x14011d11a  mov     [rbx+30h], rax
0x14011d11e  mov     rax, r12
0x14011d121  mov     rcx, [rbp+60h+var_40]
0x14011d125  xor     rcx, rsp; StackCookie
0x14011d128  call    __security_check_cookie
0x14011d12d  mov     rbx, [rsp+160h+arg_8]
0x14011d135  add     rsp, 130h
0x14011d13c  pop     r15
0x14011d13e  pop     r14
0x14011d140  pop     r13
0x14011d142  pop     r12
0x14011d144  pop     rdi
0x14011d145  pop     rsi
0x14011d146  pop     rbp
0x14011d147  retn
0x14011d149  xor     r14d, r14d
0x14011d14c  jmp     loc_14011D0C6
0x14011d151  mov     edi, 1
0x14011d156  lock add [rbx+0Ch], di
0x14011d15b  jmp     loc_14011D0D6
0x14011d160  mov     r8, rbx; struct DWMSPRITE *
0x14011d163  mov     dl, dil; bool
0x14011d166  mov     rcx, r13; HDEV
0x14011d169  call    ?vspDestroyDwmSpriteObjInternal@@YAXPEAUHDEV__@@_NPEAVDWMSPRITE@@@Z; vspDestroyDwmSpriteObjInternal(HDEV__ *,bool,DWMSPRITE *)
0x14011d16e  jmp     short loc_14011D11E
0x14011d170  mov     rax, [r14+0E0h]
0x14011d177  add     rax, 50h ; 'P'
0x14011d17b  mov     rcx, [rax]
0x14011d17e  cmp     [rcx+8], rax
0x14011d182  jnz     loc_14011CEDD
0x14011d188  mov     [rdi], rcx
0x14011d18b  mov     [rdi+8], rax
0x14011d18f  mov     [rcx+8], rdi
0x14011d193  mov     [rax], rdi
0x14011d196  jmp     loc_14011CFA2
0x14011d19b  mov     [rdi], rax
0x14011d19e  mov     [rdi+8], rcx
0x14011d1a2  mov     [rcx], rdi
0x14011d1a5  mov     [rax+8], rdi
0x14011d1a9  jmp     loc_14011CFA7
0x14011d1ae  mov     [rsp+160h+NewElement], r14b
0x14011d1b3  jmp     loc_14011D0B6
```
