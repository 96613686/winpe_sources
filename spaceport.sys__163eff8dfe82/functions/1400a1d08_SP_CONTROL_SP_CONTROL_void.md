# SP_CONTROL::~SP_CONTROL(void)

- ea: `0x1400a1d08`
- end: `0x1400a2028`
- name: `??1SP_CONTROL@@QEAA@XZ`
- size: `800`
- prototype: `void __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140033640`
- `0x1400a43c4`

## callees

- `0x14001e4a0`
- `0x14002c430`
- `0x140031f68`
- `0x140068150`
- `0x1400a1d08`
- `0x1400a3e78`
- `0x1400a5340`
- `0x1400aa7d8`
- `0x1400b9d60`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400a1f04`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a1f04`
- `ntoskrnl!IoDetachDevice` at `0x1400a1f77`
- `ntoskrnl!IoDetachDevice` at `0x1400a1f77`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400a1f2a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400a1f2a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1d5e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1da1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1de7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1d5e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1da1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a1de7`
- `ntoskrnl!SeDeassignSecurity` at `0x1400a1d2c`
- `ntoskrnl!SeDeassignSecurity` at `0x1400a1d2c`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a1f94`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400a1f94`

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
0x1400a1d08  mov     [rsp+arg_0], rbx
0x1400a1d0d  mov     [rsp+arg_8], rsi
0x1400a1d12  push    rdi
0x1400a1d13  sub     rsp, 20h
0x1400a1d17  mov     rbx, rcx
0x1400a1d1a  call    ?Remove@SP_CONTROL@@QEAAXXZ; SP_CONTROL::Remove(void)
0x1400a1d1f  lea     rcx, [rbx+180h]; SecurityDescriptor
0x1400a1d26  cmp     qword ptr [rcx], 0
0x1400a1d2a  jz      short loc_1400A1D38
0x1400a1d2c  call    cs:__imp_SeDeassignSecurity
0x1400a1d33  nop     dword ptr [rax+rax+00h]
0x1400a1d38  cmp     qword ptr [rbx+158h], 0
0x1400a1d40  mov     esi, 1
0x1400a1d45  jz      short loc_1400A1D80
0x1400a1d47  xor     edi, edi
0x1400a1d49  cmp     [rbx+150h], edi
0x1400a1d4f  jbe     short loc_1400A1D74
0x1400a1d51  mov     ecx, edi
0x1400a1d53  shl     rcx, 7
0x1400a1d57  add     rcx, [rbx+158h]; Lookaside
0x1400a1d5e  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a1d65  nop     dword ptr [rax+rax+00h]
0x1400a1d6a  add     edi, esi
0x1400a1d6c  cmp     edi, [rbx+150h]
0x1400a1d72  jb      short loc_1400A1D51
0x1400a1d74  mov     rcx, [rbx+158h]; void *
0x1400a1d7b  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1d80  cmp     qword ptr [rbx+160h], 0
0x1400a1d88  jz      short loc_1400A1DC3
0x1400a1d8a  xor     edi, edi
0x1400a1d8c  cmp     [rbx+150h], edi
0x1400a1d92  jbe     short loc_1400A1DB7
0x1400a1d94  mov     ecx, edi
0x1400a1d96  shl     rcx, 7
0x1400a1d9a  add     rcx, [rbx+160h]; Lookaside
0x1400a1da1  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a1da8  nop     dword ptr [rax+rax+00h]
0x1400a1dad  add     edi, esi
0x1400a1daf  cmp     edi, [rbx+150h]
0x1400a1db5  jb      short loc_1400A1D94
0x1400a1db7  mov     rcx, [rbx+160h]; void *
0x1400a1dbe  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1dc3  cmp     qword ptr [rbx+168h], 0
0x1400a1dcb  jz      short loc_1400A1E0C
0x1400a1dcd  imul    eax, [rbx+150h], 7
0x1400a1dd4  xor     edi, edi
0x1400a1dd6  test    eax, eax
0x1400a1dd8  jz      short loc_1400A1E00
0x1400a1dda  mov     ecx, edi
0x1400a1ddc  shl     rcx, 7
0x1400a1de0  add     rcx, [rbx+168h]; Lookaside
0x1400a1de7  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a1dee  nop     dword ptr [rax+rax+00h]
0x1400a1df3  imul    eax, [rbx+150h], 7
0x1400a1dfa  add     edi, esi
0x1400a1dfc  cmp     edi, eax
0x1400a1dfe  jb      short loc_1400A1DDA
0x1400a1e00  mov     rcx, [rbx+168h]; void *
0x1400a1e07  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1e0c  lea     rdi, [rbx+100h]
0x1400a1e13  mov     rax, [rdi]
0x1400a1e16  cmp     rax, rdi
0x1400a1e19  jz      short loc_1400A1E51
0x1400a1e1b  cmp     [rax+8], rdi
0x1400a1e1f  jnz     loc_1400A1F1F
0x1400a1e25  mov     rcx, [rax]
0x1400a1e28  cmp     [rcx+8], rax
0x1400a1e2c  jnz     loc_1400A1F1F
0x1400a1e32  mov     [rdi], rcx
0x1400a1e35  mov     [rcx+8], rdi
0x1400a1e39  lea     rcx, [rax-8]
0x1400a1e3d  test    rcx, rcx
0x1400a1e40  jz      short loc_1400A1E13
0x1400a1e42  mov     rax, [rcx]
0x1400a1e45  mov     edx, esi
0x1400a1e47  mov     rax, [rax]
0x1400a1e4a  call    _guard_dispatch_icall
0x1400a1e4f  jmp     short loc_1400A1E13
0x1400a1e51  lea     rdi, [rbx+0F0h]
0x1400a1e58  mov     rax, [rdi]
0x1400a1e5b  cmp     rax, rdi
0x1400a1e5e  jz      short loc_1400A1E99
0x1400a1e60  cmp     [rax+8], rdi
0x1400a1e64  jnz     loc_1400A1F1F
0x1400a1e6a  mov     rcx, [rax]
0x1400a1e6d  cmp     [rcx+8], rax
0x1400a1e71  jnz     loc_1400A1F1F
0x1400a1e77  mov     [rdi], rcx
0x1400a1e7a  mov     [rcx+8], rdi
0x1400a1e7e  lea     rcx, [rax-250h]
0x1400a1e85  test    rcx, rcx
0x1400a1e88  jz      short loc_1400A1E58
0x1400a1e8a  mov     rax, [rcx]
0x1400a1e8d  mov     edx, esi
0x1400a1e8f  mov     rax, [rax]
0x1400a1e92  call    _guard_dispatch_icall
0x1400a1e97  jmp     short loc_1400A1E58
0x1400a1e99  lea     rdi, [rbx+0E0h]
0x1400a1ea0  mov     rcx, [rdi]; P
0x1400a1ea3  cmp     rcx, rdi
0x1400a1ea6  jz      short loc_1400A1ECA
0x1400a1ea8  cmp     [rcx+8], rdi
0x1400a1eac  jnz     short loc_1400A1F1F
0x1400a1eae  mov     rax, [rcx]
0x1400a1eb1  cmp     [rax+8], rcx
0x1400a1eb5  jnz     short loc_1400A1F1F
0x1400a1eb7  mov     [rdi], rax
0x1400a1eba  mov     [rax+8], rdi
0x1400a1ebe  test    rcx, rcx
0x1400a1ec1  jz      short loc_1400A1EA0
0x1400a1ec3  call    ??_GSP_ENCLOSURE@@QEAAPEAXI@Z; SP_ENCLOSURE::`scalar deleting destructor'(uint)
0x1400a1ec8  jmp     short loc_1400A1EA0
0x1400a1eca  lea     rsi, [rbx+0D0h]
0x1400a1ed1  mov     rdi, [rsi]
0x1400a1ed4  cmp     rdi, rsi
0x1400a1ed7  jz      short loc_1400A1F26
0x1400a1ed9  cmp     [rdi+8], rsi
0x1400a1edd  jnz     short loc_1400A1F1F
0x1400a1edf  mov     rax, [rdi]
0x1400a1ee2  cmp     [rax+8], rdi
0x1400a1ee6  jnz     short loc_1400A1F1F
0x1400a1ee8  mov     [rsi], rax
0x1400a1eeb  mov     [rax+8], rsi
0x1400a1eef  mov     rcx, [rdi+38h]; this
0x1400a1ef3  test    rcx, rcx
0x1400a1ef6  jz      short loc_1400A1F10
0x1400a1ef8  call    ?SpDeletePoolDevice@@YAXPEAVSP_POOL_DEVICE@@@Z; SpDeletePoolDevice(SP_POOL_DEVICE *)
0x1400a1efd  mov     rcx, [rdi+38h]
0x1400a1f01  mov     rcx, [rcx]; Object
0x1400a1f04  call    cs:__imp_ObfDereferenceObject
0x1400a1f0b  nop     dword ptr [rax+rax+00h]
0x1400a1f10  test    rdi, rdi
0x1400a1f13  jz      short loc_1400A1ED1
0x1400a1f15  mov     rcx, rdi; P
0x1400a1f18  call    ??_GSP_POOL@@QEAAPEAXI@Z; SP_POOL::`scalar deleting destructor'(uint)
0x1400a1f1d  jmp     short loc_1400A1ED1
0x1400a1f1f  mov     ecx, 3
0x1400a1f24  int     29h; Win8: RtlFailFast(ecx)
0x1400a1f26  lea     rcx, [rbx+60h]; Resource
0x1400a1f2a  call    cs:__imp_ExDeleteResourceLite
0x1400a1f31  nop     dword ptr [rax+rax+00h]
0x1400a1f36  mov     rcx, [rbx+58h]; void *
0x1400a1f3a  test    rcx, rcx
0x1400a1f3d  jz      short loc_1400A1F44
0x1400a1f3f  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1f44  mov     rcx, [rbx+48h]; void *
0x1400a1f48  test    rcx, rcx
0x1400a1f4b  jz      short loc_1400A1F52
0x1400a1f4d  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1f52  mov     rcx, [rbx+38h]; void *
0x1400a1f56  test    rcx, rcx
0x1400a1f59  jz      short loc_1400A1F60
0x1400a1f5b  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1f60  mov     rcx, [rbx+28h]; void *
0x1400a1f64  test    rcx, rcx
0x1400a1f67  jz      short loc_1400A1F6E
0x1400a1f69  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a1f6e  mov     rcx, [rbx+10h]; TargetDevice
0x1400a1f72  test    rcx, rcx
0x1400a1f75  jz      short loc_1400A1F83
0x1400a1f77  call    cs:__imp_IoDetachDevice
0x1400a1f7e  nop     dword ptr [rax+rax+00h]
0x1400a1f83  mov     rcx, [rbx+0B68h]; Object
0x1400a1f8a  test    rcx, rcx
0x1400a1f8d  jz      short loc_1400A1FAB
0x1400a1f8f  mov     edx, 6B577053h; Tag
0x1400a1f94  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400a1f9b  nop     dword ptr [rax+rax+00h]
0x1400a1fa0  mov     qword ptr [rbx+0B68h], 0
0x1400a1fab  lea     rcx, [rbx+990h]; Table
0x1400a1fb2  call    ??1SP_ATTRIBUTES@@QEAA@XZ; SP_ATTRIBUTES::~SP_ATTRIBUTES(void)
0x1400a1fb7  lea     rcx, [rbx+8C0h]; this
0x1400a1fbe  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1fc3  lea     rcx, [rbx+7F0h]; this
0x1400a1fca  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1fcf  lea     rcx, [rbx+720h]; this
0x1400a1fd6  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1fdb  lea     rcx, [rbx+650h]; this
0x1400a1fe2  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1fe7  lea     rcx, [rbx+578h]; this
0x1400a1fee  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1ff3  lea     rcx, [rbx+4A8h]; this
0x1400a1ffa  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a1fff  lea     rcx, [rbx+3D8h]; this
0x1400a2006  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a200b  lea     rcx, [rbx+308h]; this
0x1400a2012  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400a2017  mov     rbx, [rsp+28h+arg_0]
0x1400a201c  mov     rsi, [rsp+28h+arg_8]
0x1400a2021  add     rsp, 20h
0x1400a2025  pop     rdi
0x1400a2026  retn
```
