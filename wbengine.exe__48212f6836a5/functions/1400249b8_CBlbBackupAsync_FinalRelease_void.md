# CBlbBackupAsync::FinalRelease(void)

- ea: `0x1400249b8`
- end: `0x140024dd6`
- name: `?FinalRelease@CBlbBackupAsync@@QEAAXXZ`
- size: `1054`
- prototype: `void __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14003df58`

## callees

- `0x140006ca8`
- `0x140006d7c`
- `0x140006d88`
- `0x14000753c`
- `0x140008ac8`
- `0x140014c54`
- `0x1400249b8`
- `0x140025f3c`
- `0x1400f5ee4`
- `0x1400f5ff4`
- `0x140137010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140024bc9`
- `KERNEL32!CloseHandle` at `0x140024bc9`
- `KERNEL32!FreeLibrary` at `0x140024bb7`
- `KERNEL32!FreeLibrary` at `0x140024bb7`
- `msvcrt!free` at `0x140024b90`
- `msvcrt!free` at `0x140024b90`
- `ole32!CoTaskMemFree` at `0x1400249d5`
- `ole32!CoTaskMemFree` at `0x1400249e7`
- `ole32!CoTaskMemFree` at `0x1400249f9`
- `ole32!CoTaskMemFree` at `0x140024a0b`
- `ole32!CoTaskMemFree` at `0x140024a8c`
- `ole32!CoTaskMemFree` at `0x140024ac6`
- `ole32!CoTaskMemFree` at `0x140024ad3`
- `ole32!CoTaskMemFree` at `0x140024aff`
- `ole32!CoTaskMemFree` at `0x140024b11`
- `ole32!CoTaskMemFree` at `0x140024b23`
- `ole32!CoTaskMemFree` at `0x140024b35`
- `ole32!CoTaskMemFree` at `0x140024b47`
- `ole32!CoTaskMemFree` at `0x140024b59`
- `ole32!CoTaskMemFree` at `0x140024b6b`
- `ole32!CoTaskMemFree` at `0x140024b7d`
- `ole32!CoTaskMemFree` at `0x140024bf7`
- `ole32!CoTaskMemFree` at `0x140024c10`
- `ole32!CoTaskMemFree` at `0x140024c67`
- `ole32!CoTaskMemFree` at `0x140024c80`
- `ole32!CoTaskMemFree` at `0x140024c99`
- `ole32!CoTaskMemFree` at `0x140024cd5`
- `ole32!CoTaskMemFree` at `0x140024cf7`
- `ole32!CoTaskMemFree` at `0x140024d1a`
- `ole32!CoTaskMemFree` at `0x140024d42`
- `ole32!CoTaskMemFree` at `0x140024d9c`
- `ole32!CoTaskMemFree` at `0x1400249d5`
- `ole32!CoTaskMemFree` at `0x1400249e7`
- `ole32!CoTaskMemFree` at `0x1400249f9`
- `ole32!CoTaskMemFree` at `0x140024a0b`
- `ole32!CoTaskMemFree` at `0x140024a8c`
- `ole32!CoTaskMemFree` at `0x140024ac6`
- `ole32!CoTaskMemFree` at `0x140024ad3`
- `ole32!CoTaskMemFree` at `0x140024aff`
- `ole32!CoTaskMemFree` at `0x140024b11`
- `ole32!CoTaskMemFree` at `0x140024b23`
- `ole32!CoTaskMemFree` at `0x140024b35`
- `ole32!CoTaskMemFree` at `0x140024b47`
- `ole32!CoTaskMemFree` at `0x140024b59`
- `ole32!CoTaskMemFree` at `0x140024b6b`
- `ole32!CoTaskMemFree` at `0x140024b7d`
- `ole32!CoTaskMemFree` at `0x140024bf7`
- `ole32!CoTaskMemFree` at `0x140024c10`
- `ole32!CoTaskMemFree` at `0x140024c67`
- `ole32!CoTaskMemFree` at `0x140024c80`
- `ole32!CoTaskMemFree` at `0x140024c99`
- `ole32!CoTaskMemFree` at `0x140024cd5`
- `ole32!CoTaskMemFree` at `0x140024cf7`
- `ole32!CoTaskMemFree` at `0x140024d1a`
- `ole32!CoTaskMemFree` at `0x140024d42`
- `ole32!CoTaskMemFree` at `0x140024d9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBlbBackupAsync::FinalRelease(CBlbBackupAsync *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  char *v6; // rcx
  char *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  struct _SPP_GROUP_PROP *v10; // rcx
  char *v11; // rbx
  unsigned int v12; // ebp
  unsigned int i; // esi
  struct _SPP_METADATA_PROP *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  HMODULE v23; // rcx
  void *v24; // rcx
  void *v25; // rbx
  void *v26; // rcx
  void *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  unsigned int j; // esi
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  unsigned int v38; // esi
  unsigned int k; // ebx
  __int64 *v40; // rdx
  void *v41; // rbp
  __int64 v42; // rax

  v2 = (void *)*((_QWORD *)this + 39);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 43);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 44);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 45);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (char *)*((_QWORD *)this + 27);
  if ( v6 )
  {
    v7 = v6 - 8;
    `eh vector destructor iterator'(
      v6,
      0x170u,
      *((_QWORD *)v6 - 1),
      (void (*)(void *))CBlbVolumeBackupContext::~CBlbVolumeBackupContext);
    operator delete[](v7);
  }
  v8 = *((_QWORD *)this + 50);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 144LL))(v8);
  v9 = *((_QWORD *)this + 51);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 144LL))(v9);
  v10 = (struct _SPP_GROUP_PROP *)*((_QWORD *)this + 54);
  if ( v10 )
  {
    BlbCleanupSppGroup(v10);
    CoTaskMemFree(*((LPVOID *)this + 54));
  }
  v11 = (char *)*((_QWORD *)this + 53);
  if ( v11 )
  {
    v12 = *((_DWORD *)this + 104);
    for ( i = 0; i < v12; ++i )
      BlbCleanupSppGroup((struct _SPP_GROUP_PROP *)&v11[144 * i]);
    CoTaskMemFree(v11);
  }
  CoTaskMemFree(*((LPVOID *)this + 55));
  *((_QWORD *)this + 55) = 0;
  *((_DWORD *)this + 112) = 0;
  v14 = (struct _SPP_METADATA_PROP *)*((_QWORD *)this + 57);
  if ( v14 )
  {
    BlbCleanupSppMetadata(v14);
    CoTaskMemFree(*((LPVOID *)this + 57));
  }
  v15 = (void *)*((_QWORD *)this + 58);
  if ( v15 )
    CoTaskMemFree(v15);
  v16 = (void *)*((_QWORD *)this + 59);
  if ( v16 )
    CoTaskMemFree(v16);
  v17 = (void *)*((_QWORD *)this + 60);
  if ( v17 )
    CoTaskMemFree(v17);
  v18 = (void *)*((_QWORD *)this + 61);
  if ( v18 )
    CoTaskMemFree(v18);
  v19 = (void *)*((_QWORD *)this + 71);
  if ( v19 )
    CoTaskMemFree(v19);
  v20 = (void *)*((_QWORD *)this + 72);
  if ( v20 )
    CoTaskMemFree(v20);
  v21 = (void *)*((_QWORD *)this + 73);
  if ( v21 )
    CoTaskMemFree(v21);
  v22 = (void *)*((_QWORD *)this + 63);
  if ( v22 )
  {
    free(v22);
    *((_QWORD *)this + 63) = 0;
  }
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  v23 = (HMODULE)*((_QWORD *)this + 67);
  if ( v23 )
    FreeLibrary(v23);
  v24 = (void *)*((_QWORD *)this + 70);
  if ( v24 )
    CloseHandle(v24);
  v25 = (void *)*((_QWORD *)this + 101);
  if ( v25 )
  {
    CBlbComponentBackupHelper::~CBlbComponentBackupHelper(*((CBlbComponentBackupHelper **)this + 101));
    operator delete(v25);
  }
  v26 = (void *)*((_QWORD *)this + 131);
  if ( v26 )
  {
    CoTaskMemFree(v26);
    *((_QWORD *)this + 131) = 0;
  }
  v27 = (void *)*((_QWORD *)this + 132);
  if ( v27 )
  {
    CoTaskMemFree(v27);
    *((_QWORD *)this + 132) = 0;
  }
  v28 = *((_QWORD *)this + 103);
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    *((_QWORD *)this + 103) = 0;
  }
  v29 = *((_QWORD *)this + 104);
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    *((_QWORD *)this + 104) = 0;
  }
  v30 = (void *)*((_QWORD *)this + 76);
  if ( v30 )
  {
    CoTaskMemFree(v30);
    *((_QWORD *)this + 76) = 0;
  }
  v31 = (void *)*((_QWORD *)this + 102);
  if ( v31 )
  {
    CoTaskMemFree(v31);
    *((_QWORD *)this + 102) = 0;
  }
  v32 = (void *)*((_QWORD *)this + 107);
  if ( v32 )
  {
    CoTaskMemFree(v32);
    *((_QWORD *)this + 107) = 0;
  }
  if ( *((_QWORD *)this + 105) )
  {
    for ( j = 0; j < *((_DWORD *)this + 212); ++j )
    {
      v34 = *(void **)(*((_QWORD *)this + 105) + 24LL * j);
      if ( v34 )
      {
        CoTaskMemFree(v34);
        *(_QWORD *)(*((_QWORD *)this + 105) + 24LL * j) = 0;
      }
      v35 = *(void **)(*((_QWORD *)this + 105) + 24LL * j + 16);
      if ( v35 )
      {
        CoTaskMemFree(v35);
        *(_QWORD *)(*((_QWORD *)this + 105) + 24LL * j + 16) = 0;
      }
      v36 = *(void **)(*((_QWORD *)this + 105) + 24LL * j + 8);
      if ( v36 )
      {
        CoTaskMemFree(v36);
        *(_QWORD *)(*((_QWORD *)this + 105) + 24LL * j + 8) = 0;
      }
    }
    v37 = (void *)*((_QWORD *)this + 105);
    if ( v37 )
    {
      CoTaskMemFree(v37);
      *((_QWORD *)this + 105) = 0;
    }
  }
  v38 = *((_DWORD *)this + 254);
  for ( k = 0; k < v38; ++k )
  {
    v40 = (__int64 *)*((_QWORD *)this + 125);
    if ( !v40 )
    {
      BlbAssert("onecore\\external\\sdk\\inc\\atlmfc\\atlcoll.h", 0x64Au, "__atl_condVal");
      ATL::AtlThrowImpl(-2147467259);
    }
    v41 = (void *)v40[2];
    v42 = *v40;
    *((_QWORD *)this + 125) = *v40;
    if ( v42 )
      *(_QWORD *)(v42 + 8) = 0;
    else
      *((_QWORD *)this + 126) = 0;
    ATL::CAtlList<_BLB_VOLUME_INFO *,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::FreeNode((char *)this + 1000);
    if ( v41 )
      CoTaskMemFree(v41);
  }
}

```

## disassembly

```asm
0x1400249b8  push    rbx
0x1400249ba  push    rbp
0x1400249bb  push    rsi
0x1400249bc  push    rdi
0x1400249bd  push    r14
0x1400249bf  sub     rsp, 20h
0x1400249c3  mov     rdi, rcx
0x1400249c6  mov     rcx, [rcx+138h]; pv
0x1400249cd  xor     r14d, r14d
0x1400249d0  test    rcx, rcx
0x1400249d3  jz      short loc_1400249DB
0x1400249d5  call    cs:__imp_CoTaskMemFree
0x1400249db  mov     rcx, [rdi+158h]; pv
0x1400249e2  test    rcx, rcx
0x1400249e5  jz      short loc_1400249ED
0x1400249e7  call    cs:__imp_CoTaskMemFree
0x1400249ed  mov     rcx, [rdi+160h]; pv
0x1400249f4  test    rcx, rcx
0x1400249f7  jz      short loc_1400249FF
0x1400249f9  call    cs:__imp_CoTaskMemFree
0x1400249ff  mov     rcx, [rdi+168h]; pv
0x140024a06  test    rcx, rcx
0x140024a09  jz      short loc_140024A11
0x140024a0b  call    cs:__imp_CoTaskMemFree
0x140024a11  mov     rcx, [rdi+0D8h]; void *
0x140024a18  test    rcx, rcx
0x140024a1b  jz      short loc_140024A3E
0x140024a1d  lea     rbx, [rcx-8]
0x140024a21  lea     r9, ??1CBlbVolumeBackupContext@@QEAA@XZ; void (*)(void *)
0x140024a28  mov     r8, [rbx]; unsigned __int64
0x140024a2b  mov     edx, 170h; unsigned __int64
0x140024a30  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140024a35  mov     rcx, rbx; Block
0x140024a38  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140024a3d  nop
0x140024a3e  mov     rcx, [rdi+190h]
0x140024a45  test    rcx, rcx
0x140024a48  jz      short loc_140024A59
0x140024a4a  mov     rax, [rcx]
0x140024a4d  mov     rax, [rax+90h]
0x140024a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024a59  mov     rcx, [rdi+198h]
0x140024a60  test    rcx, rcx
0x140024a63  jz      short loc_140024A74
0x140024a65  mov     rax, [rcx]
0x140024a68  mov     rax, [rax+90h]
0x140024a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024a74  mov     rcx, [rdi+1B0h]; struct _SPP_GROUP_PROP *
0x140024a7b  test    rcx, rcx
0x140024a7e  jz      short loc_140024A92
0x140024a80  call    ?BlbCleanupSppGroup@@YAXPEAU_SPP_GROUP_PROP@@@Z; BlbCleanupSppGroup(_SPP_GROUP_PROP *)
0x140024a85  mov     rcx, [rdi+1B0h]; pv
0x140024a8c  call    cs:__imp_CoTaskMemFree
0x140024a92  mov     rbx, [rdi+1A8h]
0x140024a99  test    rbx, rbx
0x140024a9c  jz      short loc_140024ACC
0x140024a9e  mov     ebp, [rdi+1A0h]
0x140024aa4  mov     esi, r14d
0x140024aa7  test    ebp, ebp
0x140024aa9  jz      short loc_140024AC3
0x140024aab  mov     eax, esi
0x140024aad  lea     rcx, [rax+rax*8]
0x140024ab1  shl     rcx, 4
0x140024ab5  add     rcx, rbx; struct _SPP_GROUP_PROP *
0x140024ab8  call    ?BlbCleanupSppGroup@@YAXPEAU_SPP_GROUP_PROP@@@Z; BlbCleanupSppGroup(_SPP_GROUP_PROP *)
0x140024abd  inc     esi
0x140024abf  cmp     esi, ebp
0x140024ac1  jb      short loc_140024AAB
0x140024ac3  mov     rcx, rbx; pv
0x140024ac6  call    cs:__imp_CoTaskMemFree
0x140024acc  mov     rcx, [rdi+1B8h]; pv
0x140024ad3  call    cs:__imp_CoTaskMemFree
0x140024ad9  mov     [rdi+1B8h], r14
0x140024ae0  mov     [rdi+1C0h], r14d
0x140024ae7  mov     rcx, [rdi+1C8h]; struct _SPP_METADATA_PROP *
0x140024aee  test    rcx, rcx
0x140024af1  jz      short loc_140024B05
0x140024af3  call    ?BlbCleanupSppMetadata@@YAXPEAU_SPP_METADATA_PROP@@@Z; BlbCleanupSppMetadata(_SPP_METADATA_PROP *)
0x140024af8  mov     rcx, [rdi+1C8h]; pv
0x140024aff  call    cs:__imp_CoTaskMemFree
0x140024b05  mov     rcx, [rdi+1D0h]; pv
0x140024b0c  test    rcx, rcx
0x140024b0f  jz      short loc_140024B17
0x140024b11  call    cs:__imp_CoTaskMemFree
0x140024b17  mov     rcx, [rdi+1D8h]; pv
0x140024b1e  test    rcx, rcx
0x140024b21  jz      short loc_140024B29
0x140024b23  call    cs:__imp_CoTaskMemFree
0x140024b29  mov     rcx, [rdi+1E0h]; pv
0x140024b30  test    rcx, rcx
0x140024b33  jz      short loc_140024B3B
0x140024b35  call    cs:__imp_CoTaskMemFree
0x140024b3b  mov     rcx, [rdi+1E8h]; pv
0x140024b42  test    rcx, rcx
0x140024b45  jz      short loc_140024B4D
0x140024b47  call    cs:__imp_CoTaskMemFree
0x140024b4d  mov     rcx, [rdi+238h]; pv
0x140024b54  test    rcx, rcx
0x140024b57  jz      short loc_140024B5F
0x140024b59  call    cs:__imp_CoTaskMemFree
0x140024b5f  mov     rcx, [rdi+240h]; pv
0x140024b66  test    rcx, rcx
0x140024b69  jz      short loc_140024B71
0x140024b6b  call    cs:__imp_CoTaskMemFree
0x140024b71  mov     rcx, [rdi+248h]; pv
0x140024b78  test    rcx, rcx
0x140024b7b  jz      short loc_140024B84
0x140024b7d  call    cs:__imp_CoTaskMemFree
0x140024b83  nop
0x140024b84  mov     rcx, [rdi+1F8h]; Block
0x140024b8b  test    rcx, rcx
0x140024b8e  jz      short loc_140024B9D
0x140024b90  call    cs:__imp_free
0x140024b96  mov     [rdi+1F8h], r14
0x140024b9d  mov     [rdi+200h], r14
0x140024ba4  mov     [rdi+208h], r14
0x140024bab  mov     rcx, [rdi+218h]; hLibModule
0x140024bb2  test    rcx, rcx
0x140024bb5  jz      short loc_140024BBD
0x140024bb7  call    cs:__imp_FreeLibrary
0x140024bbd  mov     rcx, [rdi+230h]; hObject
0x140024bc4  test    rcx, rcx
0x140024bc7  jz      short loc_140024BCF
0x140024bc9  call    cs:__imp_CloseHandle
0x140024bcf  mov     rbx, [rdi+328h]
0x140024bd6  test    rbx, rbx
0x140024bd9  jz      short loc_140024BEB
0x140024bdb  mov     rcx, rbx; this
0x140024bde  call    ??1CBlbComponentBackupHelper@@QEAA@XZ; CBlbComponentBackupHelper::~CBlbComponentBackupHelper(void)
0x140024be3  mov     rcx, rbx; Block
0x140024be6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140024beb  mov     rcx, [rdi+418h]; pv
0x140024bf2  test    rcx, rcx
0x140024bf5  jz      short loc_140024C04
0x140024bf7  call    cs:__imp_CoTaskMemFree
0x140024bfd  mov     [rdi+418h], r14
0x140024c04  mov     rcx, [rdi+420h]; pv
0x140024c0b  test    rcx, rcx
0x140024c0e  jz      short loc_140024C1D
0x140024c10  call    cs:__imp_CoTaskMemFree
0x140024c16  mov     [rdi+420h], r14
0x140024c1d  mov     rcx, [rdi+338h]
0x140024c24  test    rcx, rcx
0x140024c27  jz      short loc_140024C3C
0x140024c29  mov     rax, [rcx]
0x140024c2c  mov     rax, [rax+10h]
0x140024c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c35  mov     [rdi+338h], r14
0x140024c3c  mov     rcx, [rdi+340h]
0x140024c43  test    rcx, rcx
0x140024c46  jz      short loc_140024C5B
0x140024c48  mov     rax, [rcx]
0x140024c4b  mov     rax, [rax+10h]
0x140024c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c54  mov     [rdi+340h], r14
0x140024c5b  mov     rcx, [rdi+260h]; pv
0x140024c62  test    rcx, rcx
0x140024c65  jz      short loc_140024C74
0x140024c67  call    cs:__imp_CoTaskMemFree
0x140024c6d  mov     [rdi+260h], r14
0x140024c74  mov     rcx, [rdi+330h]; pv
0x140024c7b  test    rcx, rcx
0x140024c7e  jz      short loc_140024C8D
0x140024c80  call    cs:__imp_CoTaskMemFree
0x140024c86  mov     [rdi+330h], r14
0x140024c8d  mov     rcx, [rdi+358h]; pv
0x140024c94  test    rcx, rcx
0x140024c97  jz      short loc_140024CA6
0x140024c99  call    cs:__imp_CoTaskMemFree
0x140024c9f  mov     [rdi+358h], r14
0x140024ca6  cmp     [rdi+348h], r14
0x140024cad  jz      loc_140024D4F
0x140024cb3  mov     esi, r14d
0x140024cb6  cmp     [rdi+350h], r14d
0x140024cbd  jbe     short loc_140024D36
0x140024cbf  mov     eax, esi
0x140024cc1  lea     rbx, [rax+rax*2]
0x140024cc5  mov     rax, [rdi+348h]
0x140024ccc  mov     rcx, [rax+rbx*8]; pv
0x140024cd0  test    rcx, rcx
0x140024cd3  jz      short loc_140024CE6
0x140024cd5  call    cs:__imp_CoTaskMemFree
0x140024cdb  mov     rax, [rdi+348h]
0x140024ce2  mov     [rax+rbx*8], r14
0x140024ce6  mov     rax, [rdi+348h]
0x140024ced  mov     rcx, [rax+rbx*8+10h]; pv
0x140024cf2  test    rcx, rcx
0x140024cf5  jz      short loc_140024D09
0x140024cf7  call    cs:__imp_CoTaskMemFree
0x140024cfd  mov     rax, [rdi+348h]
0x140024d04  mov     [rax+rbx*8+10h], r14
0x140024d09  mov     rax, [rdi+348h]
0x140024d10  mov     rcx, [rax+rbx*8+8]; pv
0x140024d15  test    rcx, rcx
0x140024d18  jz      short loc_140024D2C
0x140024d1a  call    cs:__imp_CoTaskMemFree
0x140024d20  mov     rax, [rdi+348h]
0x140024d27  mov     [rax+rbx*8+8], r14
0x140024d2c  inc     esi
0x140024d2e  cmp     esi, [rdi+350h]
0x140024d34  jb      short loc_140024CBF
0x140024d36  mov     rcx, [rdi+348h]; pv
0x140024d3d  test    rcx, rcx
0x140024d40  jz      short loc_140024D4F
0x140024d42  call    cs:__imp_CoTaskMemFree
0x140024d48  mov     [rdi+348h], r14
0x140024d4f  mov     esi, [rdi+3F8h]
0x140024d55  mov     ebx, r14d
0x140024d58  test    esi, esi
0x140024d5a  jz      short loc_140024DA8
0x140024d5c  mov     rdx, [rdi+3E8h]
0x140024d63  test    rdx, rdx
0x140024d66  jz      short loc_140024DB3
0x140024d68  mov     rbp, [rdx+10h]
0x140024d6c  mov     rax, [rdx]
0x140024d6f  mov     [rdi+3E8h], rax
0x140024d76  test    rax, rax
0x140024d79  jz      short loc_140024D81
0x140024d7b  mov     [rax+8], r14
0x140024d7f  jmp     short loc_140024D88
0x140024d81  mov     [rdi+3F0h], r14
0x140024d88  lea     rcx, [rdi+3E8h]
0x140024d8f  call    ?FreeNode@?$CAtlList@PEAU_BLB_VOLUME_INFO@@V?$CElementTraits@PEAU_BLB_VOLUME_INFO@@@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<_BLB_VOLUME_INFO *,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::FreeNode(ATL::CAtlList<_BLB_VOLUME_INFO *,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::CNode *)
0x140024d94  test    rbp, rbp
0x140024d97  jz      short loc_140024DA2
0x140024d99  mov     rcx, rbp; pv
0x140024d9c  call    cs:__imp_CoTaskMemFree
0x140024da2  inc     ebx
0x140024da4  cmp     ebx, esi
0x140024da6  jb      short loc_140024D5C
0x140024da8  add     rsp, 20h
0x140024dac  pop     r14
0x140024dae  pop     rdi
0x140024daf  pop     rsi
0x140024db0  pop     rbp
0x140024db1  pop     rbx
0x140024db2  retn
0x140024db3  lea     r8, aAtlCondval; "__atl_condVal"
0x140024dba  mov     edx, 64Ah; unsigned int
0x140024dbf  lea     rcx, aOnecoreExterna_11; "onecore\\external\\sdk\\inc\\atlmfc\\at"...
0x140024dc6  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140024dcb  mov     ecx, 80004005h; int
0x140024dd0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
