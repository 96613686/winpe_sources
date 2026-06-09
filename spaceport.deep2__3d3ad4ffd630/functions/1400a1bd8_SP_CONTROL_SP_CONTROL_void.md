# SP_CONTROL::~SP_CONTROL(void)

- ea: `0x1400a1bd8`
- end: `0x1400a1ef8`
- name: `??1SP_CONTROL@@QEAA@XZ`
- size: `800`
- prototype: `void __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140033590`
- `0x1400a4294`

## callees

- `0x14001e4a0`
- `0x14002c430`
- `0x140031ef8`
- `0x140068000`
- `0x1400a1bd8`
- `0x1400a3d48`
- `0x1400a5210`
- `0x1400aa638`
- `0x1400b9bc0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400a1dd4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a1dd4`
- `ntoskrnl!IoDetachDevice` at `0x1400a1e47`
- `ntoskrnl!IoDetachDevice` at `0x1400a1e47`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400a1dfa`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400a1dfa`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1c2e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1c71`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1cb7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1c2e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1c71`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1cb7`
- `ntoskrnl!SeDeassignSecurity` at `0x1400a1bfc`
- `ntoskrnl!SeDeassignSecurity` at `0x1400a1bfc`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a1e64`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a1e64`

## pseudocode

```c
void __fastcall SP_CONTROL::~SP_CONTROL(SP_CONTROL *this)
{
  unsigned int v2; // edx
  unsigned int i; // edi
  unsigned int j; // edi
  unsigned int k; // edi
  _QWORD **v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  _QWORD **v9; // rdi
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD **v12; // rdi
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  void **v15; // rsi
  void *v16; // rdi
  void **v17; // rax
  struct SP_POOL_DEVICE *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  struct _DEVICE_OBJECT *v23; // rcx
  void *v24; // rcx

  SP_CONTROL::Remove(this);
  if ( *((_QWORD *)this + 48) )
    SeDeassignSecurity((PSECURITY_DESCRIPTOR *)this + 48);
  if ( *((_QWORD *)this + 43) )
  {
    for ( i = 0; i < *((_DWORD *)this + 84); ++i )
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)this + 43) + ((unsigned __int64)i << 7)));
    SC_ENV_ALLOCATOR::operator delete[](*((void **)this + 43));
  }
  if ( *((_QWORD *)this + 44) )
  {
    for ( j = 0; j < *((_DWORD *)this + 84); ++j )
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)this + 44) + ((unsigned __int64)j << 7)));
    SC_ENV_ALLOCATOR::operator delete[](*((void **)this + 44));
  }
  if ( *((_QWORD *)this + 45) )
  {
    for ( k = 0; k < 7 * *((_DWORD *)this + 84); ++k )
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)this + 45) + ((unsigned __int64)k << 7)));
    SC_ENV_ALLOCATOR::operator delete[](*((void **)this + 45));
  }
  v6 = (_QWORD **)((char *)this + 256);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( (_QWORD **)v7[1] != v6 || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
LABEL_41:
      __fastfail(3u);
    *v6 = v8;
    v8[1] = v6;
    if ( v7 != (_QWORD *)8 )
      (*(void (__fastcall **)(_QWORD *, __int64))*(v7 - 1))(v7 - 1, 1);
  }
  v9 = (_QWORD **)((char *)this + 240);
  while ( 1 )
  {
    v10 = *v9;
    if ( *v9 == v9 )
      break;
    if ( (_QWORD **)v10[1] != v9 )
      goto LABEL_41;
    v11 = (_QWORD *)*v10;
    if ( *(_QWORD **)(*v10 + 8LL) != v10 )
      goto LABEL_41;
    *v9 = v11;
    v11[1] = v9;
    if ( v10 != (_QWORD *)592 )
      (*(void (__fastcall **)(_QWORD *, __int64))*(v10 - 74))(v10 - 74, 1);
  }
  v12 = (_QWORD **)((char *)this + 224);
  while ( 1 )
  {
    v13 = *v12;
    if ( *v12 == v12 )
      break;
    if ( (_QWORD **)v13[1] != v12 )
      goto LABEL_41;
    v14 = (_QWORD *)*v13;
    if ( *(_QWORD **)(*v13 + 8LL) != v13 )
      goto LABEL_41;
    *v12 = v14;
    v14[1] = v12;
    if ( v13 )
      SP_ENCLOSURE::`scalar deleting destructor'(v13, v2);
  }
  v15 = (void **)((char *)this + 208);
  while ( 1 )
  {
    v16 = *v15;
    if ( *v15 == v15 )
      break;
    if ( *((void ***)v16 + 1) != v15 )
      goto LABEL_41;
    v17 = *(void ***)v16;
    if ( *(void **)(*(_QWORD *)v16 + 8LL) != v16 )
      goto LABEL_41;
    *v15 = v17;
    v17[1] = v15;
    v18 = (struct SP_POOL_DEVICE *)*((_QWORD *)v16 + 7);
    if ( v18 )
    {
      SpDeletePoolDevice(v18);
      ObfDereferenceObject(**((PVOID **)v16 + 7));
    }
    if ( v16 )
      SP_POOL::`scalar deleting destructor'(v16, v2);
  }
  ExDeleteResourceLite((PERESOURCE)((char *)this + 96));
  v19 = (void *)*((_QWORD *)this + 11);
  if ( v19 )
    SC_ENV_ALLOCATOR::operator delete[](v19);
  v20 = (void *)*((_QWORD *)this + 9);
  if ( v20 )
    SC_ENV_ALLOCATOR::operator delete[](v20);
  v21 = (void *)*((_QWORD *)this + 7);
  if ( v21 )
    SC_ENV_ALLOCATOR::operator delete[](v21);
  v22 = (void *)*((_QWORD *)this + 5);
  if ( v22 )
    SC_ENV_ALLOCATOR::operator delete[](v22);
  v23 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 2);
  if ( v23 )
    IoDetachDevice(v23);
  v24 = (void *)*((_QWORD *)this + 365);
  if ( v24 )
  {
    ObfDereferenceObjectWithTag(v24, 0x6B577053u);
    *((_QWORD *)this + 365) = 0;
  }
  SP_ATTRIBUTES::~SP_ATTRIBUTES((PRTL_AVL_TABLE)((char *)this + 2448));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 2240));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 2032));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 1824));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 1616));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 1400));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 1192));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 984));
  SP_WORKITEM::~SP_WORKITEM((SP_CONTROL *)((char *)this + 776));
}

```

## disassembly

```asm
0x1400a1bd8  mov     [rsp+arg_0], rbx
0x1400a1bdd  mov     [rsp+arg_8], rsi
0x1400a1be2  push    rdi
0x1400a1be3  sub     rsp, 20h
0x1400a1be7  mov     rbx, rcx
0x1400a1bea  call    ?Remove@SP_CONTROL@@QEAAXXZ; SP_CONTROL::Remove(void)
0x1400a1bef  lea     rcx, [rbx+180h]; SecurityDescriptor
0x1400a1bf6  cmp     qword ptr [rcx], 0
0x1400a1bfa  jz      short loc_1400A1C08
0x1400a1bfc  call    cs:__imp_SeDeassignSecurity
0x1400a1c03  nop     dword ptr [rax+rax+00h]
0x1400a1c08  cmp     qword ptr [rbx+158h], 0
0x1400a1c10  mov     esi, 1
0x1400a1c15  jz      short loc_1400A1C50
0x1400a1c17  xor     edi, edi
0x1400a1c19  cmp     [rbx+150h], edi
0x1400a1c1f  jbe     short loc_1400A1C44
0x1400a1c21  mov     ecx, edi
0x1400a1c23  shl     rcx, 7
0x1400a1c27  add     rcx, [rbx+158h]; Lookaside
0x1400a1c2e  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a1c35  nop     dword ptr [rax+rax+00h]
0x1400a1c3a  add     edi, esi
0x1400a1c3c  cmp     edi, [rbx+150h]
0x1400a1c42  jb      short loc_1400A1C21
0x1400a1c44  mov     rcx, [rbx+158h]; void *
0x1400a1c4b  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1c50  cmp     qword ptr [rbx+160h], 0
0x1400a1c58  jz      short loc_1400A1C93
0x1400a1c5a  xor     edi, edi
0x1400a1c5c  cmp     [rbx+150h], edi
0x1400a1c62  jbe     short loc_1400A1C87
0x1400a1c64  mov     ecx, edi
0x1400a1c66  shl     rcx, 7
0x1400a1c6a  add     rcx, [rbx+160h]; Lookaside
0x1400a1c71  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a1c78  nop     dword ptr [rax+rax+00h]
0x1400a1c7d  add     edi, esi
0x1400a1c7f  cmp     edi, [rbx+150h]
0x1400a1c85  jb      short loc_1400A1C64
0x1400a1c87  mov     rcx, [rbx+160h]; void *
0x1400a1c8e  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1c93  cmp     qword ptr [rbx+168h], 0
0x1400a1c9b  jz      short loc_1400A1CDC
0x1400a1c9d  imul    eax, [rbx+150h], 7
0x1400a1ca4  xor     edi, edi
0x1400a1ca6  test    eax, eax
0x1400a1ca8  jz      short loc_1400A1CD0
0x1400a1caa  mov     ecx, edi
0x1400a1cac  shl     rcx, 7
0x1400a1cb0  add     rcx, [rbx+168h]; Lookaside
0x1400a1cb7  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a1cbe  nop     dword ptr [rax+rax+00h]
0x1400a1cc3  imul    eax, [rbx+150h], 7
0x1400a1cca  add     edi, esi
0x1400a1ccc  cmp     edi, eax
0x1400a1cce  jb      short loc_1400A1CAA
0x1400a1cd0  mov     rcx, [rbx+168h]; void *
0x1400a1cd7  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1cdc  lea     rdi, [rbx+100h]
0x1400a1ce3  mov     rax, [rdi]
0x1400a1ce6  cmp     rax, rdi
0x1400a1ce9  jz      short loc_1400A1D21
0x1400a1ceb  cmp     [rax+8], rdi
0x1400a1cef  jnz     loc_1400A1DEF
0x1400a1cf5  mov     rcx, [rax]
0x1400a1cf8  cmp     [rcx+8], rax
0x1400a1cfc  jnz     loc_1400A1DEF
0x1400a1d02  mov     [rdi], rcx
0x1400a1d05  mov     [rcx+8], rdi
0x1400a1d09  lea     rcx, [rax-8]
0x1400a1d0d  test    rcx, rcx
0x1400a1d10  jz      short loc_1400A1CE3
0x1400a1d12  mov     rax, [rcx]
0x1400a1d15  mov     edx, esi
0x1400a1d17  mov     rax, [rax]
0x1400a1d1a  call    _guard_dispatch_icall
0x1400a1d1f  jmp     short loc_1400A1CE3
0x1400a1d21  lea     rdi, [rbx+0F0h]
0x1400a1d28  mov     rax, [rdi]
0x1400a1d2b  cmp     rax, rdi
0x1400a1d2e  jz      short loc_1400A1D69
0x1400a1d30  cmp     [rax+8], rdi
0x1400a1d34  jnz     loc_1400A1DEF
0x1400a1d3a  mov     rcx, [rax]
0x1400a1d3d  cmp     [rcx+8], rax
0x1400a1d41  jnz     loc_1400A1DEF
0x1400a1d47  mov     [rdi], rcx
0x1400a1d4a  mov     [rcx+8], rdi
0x1400a1d4e  lea     rcx, [rax-250h]
0x1400a1d55  test    rcx, rcx
0x1400a1d58  jz      short loc_1400A1D28
0x1400a1d5a  mov     rax, [rcx]
0x1400a1d5d  mov     edx, esi
0x1400a1d5f  mov     rax, [rax]
0x1400a1d62  call    _guard_dispatch_icall
0x1400a1d67  jmp     short loc_1400A1D28
0x1400a1d69  lea     rdi, [rbx+0E0h]
0x1400a1d70  mov     rcx, [rdi]; P
0x1400a1d73  cmp     rcx, rdi
0x1400a1d76  jz      short loc_1400A1D9A
0x1400a1d78  cmp     [rcx+8], rdi
0x1400a1d7c  jnz     short loc_1400A1DEF
0x1400a1d7e  mov     rax, [rcx]
0x1400a1d81  cmp     [rax+8], rcx
0x1400a1d85  jnz     short loc_1400A1DEF
0x1400a1d87  mov     [rdi], rax
0x1400a1d8a  mov     [rax+8], rdi
0x1400a1d8e  test    rcx, rcx
0x1400a1d91  jz      short loc_1400A1D70
0x1400a1d93  call    ??_GSP_ENCLOSURE@@QEAAPEAXI@Z; SP_ENCLOSURE::`scalar deleting destructor'(uint)
0x1400a1d98  jmp     short loc_1400A1D70
0x1400a1d9a  lea     rsi, [rbx+0D0h]
0x1400a1da1  mov     rdi, [rsi]
0x1400a1da4  cmp     rdi, rsi
0x1400a1da7  jz      short loc_1400A1DF6
0x1400a1da9  cmp     [rdi+8], rsi
0x1400a1dad  jnz     short loc_1400A1DEF
0x1400a1daf  mov     rax, [rdi]
0x1400a1db2  cmp     [rax+8], rdi
0x1400a1db6  jnz     short loc_1400A1DEF
0x1400a1db8  mov     [rsi], rax
0x1400a1dbb  mov     [rax+8], rsi
0x1400a1dbf  mov     rcx, [rdi+38h]; this
0x1400a1dc3  test    rcx, rcx
0x1400a1dc6  jz      short loc_1400A1DE0
0x1400a1dc8  call    ?SpDeletePoolDevice@@YAXPEAVSP_POOL_DEVICE@@@Z; SpDeletePoolDevice(SP_POOL_DEVICE *)
0x1400a1dcd  mov     rcx, [rdi+38h]
0x1400a1dd1  mov     rcx, [rcx]; Object
0x1400a1dd4  call    cs:__imp_ObfDereferenceObject
0x1400a1ddb  nop     dword ptr [rax+rax+00h]
0x1400a1de0  test    rdi, rdi
0x1400a1de3  jz      short loc_1400A1DA1
0x1400a1de5  mov     rcx, rdi; P
0x1400a1de8  call    ??_GSP_POOL@@QEAAPEAXI@Z; SP_POOL::`scalar deleting destructor'(uint)
0x1400a1ded  jmp     short loc_1400A1DA1
0x1400a1def  mov     ecx, 3
0x1400a1df4  int     29h; Win8: RtlFailFast(ecx)
0x1400a1df6  lea     rcx, [rbx+60h]; Resource
0x1400a1dfa  call    cs:__imp_ExDeleteResourceLite
0x1400a1e01  nop     dword ptr [rax+rax+00h]
0x1400a1e06  mov     rcx, [rbx+58h]; void *
0x1400a1e0a  test    rcx, rcx
0x1400a1e0d  jz      short loc_1400A1E14
0x1400a1e0f  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1e14  mov     rcx, [rbx+48h]; void *
0x1400a1e18  test    rcx, rcx
0x1400a1e1b  jz      short loc_1400A1E22
0x1400a1e1d  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1e22  mov     rcx, [rbx+38h]; void *
0x1400a1e26  test    rcx, rcx
0x1400a1e29  jz      short loc_1400A1E30
0x1400a1e2b  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1e30  mov     rcx, [rbx+28h]; void *
0x1400a1e34  test    rcx, rcx
0x1400a1e37  jz      short loc_1400A1E3E
0x1400a1e39  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1e3e  mov     rcx, [rbx+10h]; TargetDevice
0x1400a1e42  test    rcx, rcx
0x1400a1e45  jz      short loc_1400A1E53
0x1400a1e47  call    cs:__imp_IoDetachDevice
0x1400a1e4e  nop     dword ptr [rax+rax+00h]
0x1400a1e53  mov     rcx, [rbx+0B68h]; Object
0x1400a1e5a  test    rcx, rcx
0x1400a1e5d  jz      short loc_1400A1E7B
0x1400a1e5f  mov     edx, 6B577053h; Tag
0x1400a1e64  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400a1e6b  nop     dword ptr [rax+rax+00h]
0x1400a1e70  mov     qword ptr [rbx+0B68h], 0
0x1400a1e7b  lea     rcx, [rbx+990h]; Table
0x1400a1e82  call    ??1SP_ATTRIBUTES@@QEAA@XZ; SP_ATTRIBUTES::~SP_ATTRIBUTES(void)
0x1400a1e87  lea     rcx, [rbx+8C0h]; this
0x1400a1e8e  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1e93  lea     rcx, [rbx+7F0h]; this
0x1400a1e9a  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1e9f  lea     rcx, [rbx+720h]; this
0x1400a1ea6  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1eab  lea     rcx, [rbx+650h]; this
0x1400a1eb2  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1eb7  lea     rcx, [rbx+578h]; this
0x1400a1ebe  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1ec3  lea     rcx, [rbx+4A8h]; this
0x1400a1eca  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1ecf  lea     rcx, [rbx+3D8h]; this
0x1400a1ed6  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1edb  lea     rcx, [rbx+308h]; this
0x1400a1ee2  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1ee7  mov     rbx, [rsp+28h+arg_0]
0x1400a1eec  mov     rsi, [rsp+28h+arg_8]
0x1400a1ef1  add     rsp, 20h
0x1400a1ef5  pop     rdi
0x1400a1ef6  retn
```
