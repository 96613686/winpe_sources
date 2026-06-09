# CBin::CreateItem(void *,unsigned __int64,void *,unsigned __int64)

- ea: `0x180011264`
- end: `0x1800114de`
- name: `?CreateItem@CBin@@QEAAHPEAX_K01@Z`
- size: `634`
- prototype: `__int64 __usercall@<rax>(CBin *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180013b28`
- `0x1800142c8`

## callees

- `0x18000fcf0`
- `0x180011264`
- `0x1800126c4`
- `0x1800132f8`
- `0x1800134ec`
- `0x180013550`
- `0x180016574`
- `0x180016694`
- `0x180018638`
- `0x1800186b4`
- `0x180027510`

## pseudocode

```c
__int64 __fastcall CBin::CreateItem(CBin *this, void *a2, unsigned __int64 a3, void *a4, unsigned __int64 a5)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rdx
  CMemoryManager *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rsi
  struct SMainPageHeader *v18; // rax
  void *v19; // [rsp+40h] [rbp-51h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-49h] BYREF
  void *v21; // [rsp+50h] [rbp-41h]
  _BYTE v22[16]; // [rsp+58h] [rbp-39h] BYREF
  __int128 v23; // [rsp+68h] [rbp-29h]
  _QWORD v24[2]; // [rsp+80h] [rbp-11h] BYREF

  v21 = a2;
  if ( !a2 )
    return 0;
  if ( !a3 )
    return 0;
  if ( !(unsigned int)CBin::IsReadyToCreate(this) )
    return 0;
  v10 = *(_QWORD *)(v8 + 120);
  if ( !v10 )
    return 0;
  if ( ~v9 < a5 )
    return 0;
  if ( ~v9 - a5 < 0x10 )
    return 0;
  v11 = v9 + a5 + 16;
  if ( v11 != v10 && v11 > v10 )
    return 0;
  *((_QWORD *)this + 15) = 0;
  CBin::EnumFlushView(this);
  if ( *((_QWORD *)this + 16) < v11 )
  {
    v12 = *((_QWORD *)this + 10);
    v13 = (CMemoryManager *)*((_QWORD *)this + 12);
    v23 = 0;
    if ( !CMemoryManager::Allocate(v13, v12, v11, 0, 0, (struct SMainPageHeader *)v22) )
      return 0;
    v14 = v23;
    v15 = *((_QWORD *)&v23 + 1) - 1LL;
    ++*((_DWORD *)this + 18);
    *((_QWORD *)this + 14) = 16 * (16 * v14 - v15) - 40;
    if ( !(unsigned int)CBin::UpdateEnumState(this, this) )
      return 0;
  }
  v16 = (_QWORD *)((char *)this + 136);
  if ( !CBin::EnumSetPointer(this, *((_QWORD *)this + 17), (CBin *)((char *)this + 152)) )
    return 0;
  v24[1] = *((_QWORD *)this + 18);
  v24[0] = v11;
  v20 = 0;
  v19 = 0;
  if ( !(unsigned int)CBin::EnumReadWrite(this, 0, v24, 0x10u, &v19, &v20, 0)
    || !(unsigned int)CBin::EnumReadWrite(this, 0, v21, a3, &v19, &v20, 0)
    || a4 && !(unsigned int)CBin::EnumReadWrite(this, 0, a4, a5, &v19, &v20, 0) )
  {
    return 0;
  }
  if ( *v16 )
  {
    CBin::EnumRestoreState(this, (CBin *)((char *)this + 152));
    v19 = 0;
    v20 = 0;
    if ( !(unsigned int)CBin::EnumReadWrite(this, 0, (char *)this + 136, 8u, &v19, &v20, 8u) )
      return 0;
  }
  else
  {
    v19 = 0;
    v18 = CBin::MapPageHeader(this, &v19);
    if ( !v18 )
      return 0;
    *((_QWORD *)v18 + 4) = *v16;
    CBin::UnmapPageHeader(this, v19);
  }
  CBin::EnumFlushView(this);
  return 1;
}

```

## disassembly

```asm
0x180011264  push    rbp
0x180011266  push    rbx
0x180011267  push    rsi
0x180011268  push    rdi
0x180011269  push    r12
0x18001126b  push    r13
0x18001126d  push    r14
0x18001126f  push    r15
0x180011271  lea     rbp, [rsp-17h]
0x180011276  sub     rsp, 0A8h
0x18001127d  mov     rax, cs:__security_cookie
0x180011284  xor     rax, rsp
0x180011287  mov     [rbp+4Fh+var_50], rax
0x18001128b  mov     [rbp+4Fh+var_90], rdx
0x18001128f  mov     r13, r9
0x180011292  mov     r15, r8
0x180011295  mov     rbx, rcx
0x180011298  test    rdx, rdx
0x18001129b  jz      loc_180011487
0x1800112a1  test    r8, r8
0x1800112a4  jz      loc_180011487
0x1800112aa  call    ?IsReadyToCreate@CBin@@QEAAHXZ; CBin::IsReadyToCreate(void)
0x1800112af  test    eax, eax
0x1800112b1  jz      loc_180011487
0x1800112b7  mov     rcx, [rcx+78h]
0x1800112bb  test    rcx, rcx
0x1800112be  jz      loc_180011487
0x1800112c4  mov     r14, [rbp+4Fh+arg_20]
0x1800112c8  mov     rax, r8
0x1800112cb  not     rax
0x1800112ce  cmp     rax, r14
0x1800112d1  jb      loc_180011487
0x1800112d7  sub     rax, r14
0x1800112da  cmp     rax, 10h
0x1800112de  jb      loc_180011487
0x1800112e4  lea     rdi, [r14+10h]
0x1800112e8  add     rdi, r8
0x1800112eb  cmp     rdi, rcx
0x1800112ee  jz      short loc_1800112F6
0x1800112f0  ja      loc_180011487
0x1800112f6  mov     rcx, rbx; this
0x1800112f9  mov     qword ptr [rbx+78h], 0
0x180011301  call    ?EnumFlushView@CBin@@QEAAHXZ; CBin::EnumFlushView(void)
0x180011306  cmp     [rbx+80h], rdi
0x18001130d  jnb     short loc_180011377
0x18001130f  mov     rdx, [rbx+50h]; unsigned __int64
0x180011313  lea     rax, [rbp+4Fh+var_88]
0x180011317  mov     rcx, [rbx+60h]; this
0x18001131b  xorps   xmm0, xmm0
0x18001131e  mov     [rsp+0E0h+var_B8], rax; struct SMainPageHeader *
0x180011323  xor     r9d, r9d; int
0x180011326  mov     r8, rdi; unsigned __int64
0x180011329  mov     dword ptr [rsp+0E0h+var_C0], 0; int
0x180011331  movups  [rbp+4Fh+var_78], xmm0
0x180011335  call    ?Allocate@CMemoryManager@@QEAA_K_K0HHPEAUSMainPageHeader@@@Z; CMemoryManager::Allocate(unsigned __int64,unsigned __int64,int,int,SMainPageHeader *)
0x18001133a  test    rax, rax
0x18001133d  jz      loc_180011487
0x180011343  mov     rax, qword ptr [rbp+4Fh+var_78+8]
0x180011347  mov     rdx, rbx; struct SBinEnumState *
0x18001134a  mov     rcx, qword ptr [rbp+4Fh+var_78]
0x18001134e  dec     rax
0x180011351  inc     dword ptr [rbx+48h]
0x180011354  shl     rcx, 4
0x180011358  sub     rcx, rax
0x18001135b  shl     rcx, 4
0x18001135f  sub     rcx, 28h ; '('
0x180011363  mov     [rbx+70h], rcx
0x180011367  mov     rcx, rbx; this
0x18001136a  call    ?UpdateEnumState@CBin@@QEAAHAEAUSBinEnumState@@@Z; CBin::UpdateEnumState(SBinEnumState &)
0x18001136f  test    eax, eax
0x180011371  jz      loc_180011487
0x180011377  lea     r12, [rbx+98h]
0x18001137e  mov     rcx, rbx; this
0x180011381  lea     rsi, [rbx+88h]
0x180011388  mov     r8, r12; struct SBinEnumState *
0x18001138b  mov     rdx, [rsi]; unsigned __int64
0x18001138e  call    ?EnumSetPointer@CBin@@QEAAH_KPEAUSBinEnumState@@@Z; CBin::EnumSetPointer(unsigned __int64,SBinEnumState *)
0x180011393  test    eax, eax
0x180011395  jz      loc_180011487
0x18001139b  mov     rax, [rbx+90h]
0x1800113a2  lea     r8, [rbp+4Fh+var_60]; void *
0x1800113a6  mov     [rbp+4Fh+var_58], rax
0x1800113aa  xor     edx, edx; int
0x1800113ac  mov     [rbp+4Fh+var_60], rdi
0x1800113b0  lea     rax, [rbp+4Fh+var_98]
0x1800113b4  xor     edi, edi
0x1800113b6  mov     rcx, rbx; this
0x1800113b9  mov     [rsp+0E0h+var_B0], rdi; unsigned __int64
0x1800113be  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
0x1800113c3  lea     rax, [rbp+4Fh+var_A0]
0x1800113c7  mov     [rsp+0E0h+var_C0], rax; void **
0x1800113cc  lea     r9d, [rdi+10h]; unsigned __int64
0x1800113d0  mov     [rbp+4Fh+var_98], rdi
0x1800113d4  mov     [rbp+4Fh+var_A0], rdi
0x1800113d8  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x1800113dd  test    eax, eax
0x1800113df  jz      loc_180011487
0x1800113e5  mov     r8, [rbp+4Fh+var_90]; void *
0x1800113e9  lea     rax, [rbp+4Fh+var_98]
0x1800113ed  mov     [rsp+0E0h+var_B0], rdi; unsigned __int64
0x1800113f2  mov     r9, r15; unsigned __int64
0x1800113f5  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
0x1800113fa  xor     edx, edx; int
0x1800113fc  lea     rax, [rbp+4Fh+var_A0]
0x180011400  mov     rcx, rbx; this
0x180011403  mov     [rsp+0E0h+var_C0], rax; void **
0x180011408  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x18001140d  test    eax, eax
0x18001140f  jz      short loc_180011487
0x180011411  test    r13, r13
0x180011414  jz      short loc_180011441
0x180011416  lea     rax, [rbp+4Fh+var_98]
0x18001141a  mov     [rsp+0E0h+var_B0], rdi; unsigned __int64
0x18001141f  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
0x180011424  mov     r9, r14; unsigned __int64
0x180011427  lea     rax, [rbp+4Fh+var_A0]
0x18001142b  mov     r8, r13; void *
0x18001142e  xor     edx, edx; int
0x180011430  mov     [rsp+0E0h+var_C0], rax; void **
0x180011435  mov     rcx, rbx; this
0x180011438  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x18001143d  test    eax, eax
0x18001143f  jz      short loc_180011487
0x180011441  mov     rcx, rbx; this
0x180011444  cmp     [rsi], rdi
0x180011447  jz      short loc_1800114AA
0x180011449  mov     rdx, r12; struct SBinEnumState *
0x18001144c  call    ?EnumRestoreState@CBin@@QEAAHAEAUSBinEnumState@@@Z; CBin::EnumRestoreState(SBinEnumState &)
0x180011451  mov     r9d, 8; unsigned __int64
0x180011457  mov     [rbp+4Fh+var_A0], rdi
0x18001145b  mov     [rsp+0E0h+var_B0], r9; unsigned __int64
0x180011460  lea     rax, [rbp+4Fh+var_98]
0x180011464  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
0x180011469  mov     r8, rsi; void *
0x18001146c  lea     rax, [rbp+4Fh+var_A0]
0x180011470  mov     [rbp+4Fh+var_98], rdi
0x180011474  xor     edx, edx; int
0x180011476  mov     [rsp+0E0h+var_C0], rax; void **
0x18001147b  mov     rcx, rbx; this
0x18001147e  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x180011483  test    eax, eax
0x180011485  jnz     short loc_1800114CF
0x180011487  xor     eax, eax
0x180011489  mov     rcx, [rbp+4Fh+var_50]
0x18001148d  xor     rcx, rsp; StackCookie
0x180011490  call    __security_check_cookie
0x180011495  add     rsp, 0A8h
0x18001149c  pop     r15
0x18001149e  pop     r14
0x1800114a0  pop     r13
0x1800114a2  pop     r12
0x1800114a4  pop     rdi
0x1800114a5  pop     rsi
0x1800114a6  pop     rbx
0x1800114a7  pop     rbp
0x1800114a8  retn
0x1800114aa  lea     rdx, [rbp+4Fh+var_A0]; void **
0x1800114ae  mov     [rbp+4Fh+var_A0], rdi
0x1800114b2  call    ?MapPageHeader@CBin@@AEAAPEAUSMainPageHeader@@PEAPEAX@Z; CBin::MapPageHeader(void * *)
0x1800114b7  test    rax, rax
0x1800114ba  jz      short loc_180011487
0x1800114bc  mov     rdx, [rsi]
0x1800114bf  mov     rcx, rbx; this
0x1800114c2  mov     [rax+20h], rdx
0x1800114c6  mov     rdx, [rbp+4Fh+var_A0]; void *
0x1800114ca  call    ?UnmapPageHeader@CBin@@AEAAHPEAX@Z; CBin::UnmapPageHeader(void *)
0x1800114cf  mov     rcx, rbx; this
0x1800114d2  call    ?EnumFlushView@CBin@@QEAAHXZ; CBin::EnumFlushView(void)
0x1800114d7  mov     eax, 1
0x1800114dc  jmp     short loc_180011489
```
