# ActivationPropertiesOut::~ActivationPropertiesOut(void)

- ea: `0x180030880`
- end: `0x180030da5`
- name: `??1ActivationPropertiesOut@@UEAA@XZ`
- size: `1317`
- prototype: `void __fastcall(ActivationPropertiesOut *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180030200`
- `0x180030240`
- `0x18003031c`

## callees

- `0x180030880`
- `0x18009eac8`
- `0x1800b2bb0`
- `0x180103474`
- `0x18010b010`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x180030af1`
- `RPCRT4!MesHandleFree` at `0x180030af1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030907`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030968`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003098b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800309b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030a1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030a73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030b4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030b64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030bb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030bf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030c2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030c48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030907`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030968`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003098b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800309b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030a1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030a73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030b4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030b64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030bb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030bf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030c2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030c48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800309ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800309c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800309d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800309ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800309c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800309d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030cdb`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180030cce`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180030cce`

## pseudocode

```c
void __fastcall ActivationPropertiesOut::~ActivationPropertiesOut(ActivationPropertiesOut *this)
{
  int *v2; // rax
  void *v3; // rdi
  __int64 v4; // rdi
  HANDLE v5; // rcx
  void *v6; // rsi
  void *v7; // r8
  HANDLE v8; // rcx
  __int64 v9; // r8
  unsigned int *v10; // rdi
  void *v11; // r8
  char *v12; // r8
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rdi
  void *v15; // rcx
  __int64 v16; // rcx
  void *v17; // r8
  unsigned int v18; // esi
  void **i; // r14
  __int64 v20; // r15
  __int64 v21; // rcx
  void *v22; // r8
  HANDLE v23; // rcx
  unsigned int v24; // edi
  void **v25; // [rsp+20h] [rbp-48h] BYREF
  void **v26; // [rsp+28h] [rbp-40h]
  __int64 v27; // [rsp+30h] [rbp-38h]
  int v28; // [rsp+38h] [rbp-30h]
  int v29; // [rsp+3Ch] [rbp-2Ch]
  __int64 v30; // [rsp+40h] [rbp-28h]
  int v31; // [rsp+48h] [rbp-20h]
  int v32; // [rsp+4Ch] [rbp-1Ch]

  *(_QWORD *)this = &ActivationPropertiesOut::`vftable'{for `IActivationProperties'};
  *((_QWORD *)this + 1) = &ActivationPropertiesOut::`vftable'{for `ISerializableParent'};
  *((_QWORD *)this + 2) = &ActivationPropertiesOut::`vftable'{for `IGetCatalogObject'};
  *((_QWORD *)this + 71) = &ActivationPropertiesOut::`vftable'{for `IPrivActivationPropertiesOut'};
  *((_QWORD *)this + 72) = &ActivationPropertiesOut::`vftable'{for `IActivationPropOutClean'};
  v2 = (int *)*((_QWORD *)this + 118);
  if ( v2 )
  {
    v30 = *((_QWORD *)this + 118);
    v25 = &GenericStreamBase<IStream,CoTaskMemAllocAllocator>::`vftable'{for `IStream'};
    v26 = &GenericStreamBase<IStream,CoTaskMemAllocAllocator>::`vftable'{for `IBufferInternal'};
    v27 = 1;
    v28 = 0;
    v31 = 0;
    v32 = 1;
    v29 = *v2;
    v25 = &GenericCoTaskMemStream::`vftable'{for `IStream'};
    v26 = &GenericStreamBase<IStream,CoTaskMemAllocAllocator>::`vftable'{for `IBufferInternal'};
    CoReleaseMarshalData((LPSTREAM)&v25);
    CoTaskMemFree(*((LPVOID *)this + 118));
    *((_QWORD *)this + 118) = 0;
    GenericStreamBase<IStream,CoTaskMemAllocAllocator>::~GenericStreamBase<IStream,CoTaskMemAllocAllocator>(&v25);
  }
  v3 = (void *)*((_QWORD *)this + 116);
  if ( v3 )
  {
    ClearOrpcExtentArray(*((struct tagORPC_EXTENT_ARRAY **)this + 116));
    HeapFree(g_hHeap, 0, v3);
  }
  *((_OWORD *)this + 57) = 0;
  *((_QWORD *)this + 116) = 0;
  v4 = *((_QWORD *)this + 111);
  *((_QWORD *)this + 107) = &ScmReplyInfo::`vftable'{for `IScmReplyInfo'};
  *((_QWORD *)this + 108) = &ScmReplyInfo::`vftable'{for `SerializableProperty'};
  if ( v4 )
  {
    v5 = g_hHeap;
    *((_QWORD *)this + 111) = 0;
    HeapFree(v5, 0, *(LPVOID *)(v4 + 8));
    v6 = *(void **)(v4 + 48);
    if ( v6 )
    {
      ClearOrpcExtentArray(*(struct tagORPC_EXTENT_ARRAY **)(v4 + 48));
      HeapFree(g_hHeap, 0, v6);
    }
    *(_OWORD *)(v4 + 32) = 0;
    *(_QWORD *)(v4 + 48) = 0;
    v7 = *(void **)(v4 + 80);
    if ( v7 )
      HeapFree(g_hHeap, 0, v7);
    WindowsDeleteString(*(HSTRING *)(v4 + 120));
    WindowsDeleteString(*(HSTRING *)(v4 + 128));
    WindowsDeleteString(*(HSTRING *)(v4 + 136));
    v8 = g_hHeap;
    *(_OWORD *)(v4 + 16) = 0;
    *(_OWORD *)(v4 + 32) = 0;
    *(_OWORD *)(v4 + 48) = 0;
    *(_OWORD *)(v4 + 64) = 0;
    *(_OWORD *)(v4 + 80) = 0;
    *(_OWORD *)(v4 + 96) = 0;
    *(_OWORD *)(v4 + 112) = 0;
    *(_OWORD *)(v4 + 128) = 0;
    *(_OWORD *)(v4 + 144) = 0;
    *(_QWORD *)(v4 + 160) = 0;
    HeapFree(v8, 0, (LPVOID)v4);
  }
  v9 = *((_QWORD *)this + 112);
  if ( v9 )
  {
    HeapFree(g_hHeap, 0, *(LPVOID *)(v9 + 8));
    HeapFree(g_hHeap, 0, *((LPVOID *)this + 112));
  }
  v10 = (unsigned int *)((char *)this + 616);
  *((_QWORD *)this + 74) = &ActivationPropertiesOut::OutSerializer::`vftable';
  if ( *((_QWORD *)this + 80) )
  {
    v18 = 0;
    for ( i = (void **)((char *)this + 648); v18 < *v10; ++v18 )
    {
      v20 = 8LL * v18;
      HeapFree(g_hHeap, 0, *(LPVOID *)(v20 + *((_QWORD *)this + 80)));
      if ( *i )
      {
        v21 = *(_QWORD *)((char *)*i + v20);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    HeapFree(g_hHeap, 0, *((LPVOID *)this + 80));
    v22 = *i;
    v23 = g_hHeap;
    *((_QWORD *)this + 80) = 0;
    HeapFree(v23, 0, v22);
    *i = 0;
  }
  v11 = (void *)*((_QWORD *)this + 79);
  *v10 = 0;
  if ( v11 )
  {
    HeapFree(g_hHeap, 0, v11);
    *((_QWORD *)this + 79) = 0;
  }
  v12 = (char *)*((_QWORD *)this + 78);
  if ( v12 && v12 != (char *)this + 680 )
  {
    HeapFree(g_hHeap, 0, v12);
    *((_QWORD *)this + 78) = 0;
  }
  v13 = *((_QWORD *)this + 105);
  if ( v13 && !*((_DWORD *)this + 212) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  *((_QWORD *)this + 105) = 0;
  *((_DWORD *)this + 213) = 0;
  v14 = (volatile signed __int32 *)*((_QWORD *)this + 69);
  *(_QWORD *)this = &ActivationProperties::`vftable'{for `IActivationProperties'};
  *((_QWORD *)this + 1) = &ActivationProperties::`vftable'{for `ISerializableParent'};
  *((_QWORD *)this + 2) = &ActivationProperties::`vftable'{for `IGetCatalogObject'};
  if ( v14 && _InterlockedExchangeAdd(v14 + 14, 0xFFFFFFFF) == 1 )
  {
    v15 = (void *)*((_QWORD *)v14 + 6);
    if ( v15 )
    {
      MesHandleFree(v15);
      *((_QWORD *)v14 + 6) = 0;
    }
    if ( *(_QWORD *)v14 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 + 2) + 16LL))(*((_QWORD *)v14 + 2));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 16LL))(*(_QWORD *)v14);
    }
    v16 = *((_QWORD *)v14 + 1);
    if ( v16 && v16 != *(_QWORD *)v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    operator delete((void *)v14, 0x58u);
  }
  if ( *((_DWORD *)this + 11) )
  {
    HeapFree(g_hHeap, 0, *((LPVOID *)this + 20));
    HeapFree(g_hHeap, 0, *((LPVOID *)this + 21));
  }
  if ( *((_DWORD *)this + 16) && *((_QWORD *)this + 14) )
  {
    v24 = 0;
    do
      HeapFree(g_hHeap, 0, *(LPVOID *)(*((_QWORD *)this + 14) + 40LL * v24++ + 32));
    while ( v24 < *((_DWORD *)this + 16) );
  }
  v17 = (void *)*((_QWORD *)this + 14);
  if ( v17 )
    HeapFree(g_hHeap, 0, v17);
}

```

## disassembly

```asm
0x180030880  sub     rsp, 68h
0x180030884  mov     [rsp+68h+arg_8], rbx
0x180030889  lea     rax, ??_7ActivationPropertiesOut@@6BIActivationProperties@@@; const ActivationPropertiesOut::`vftable'{for `IActivationProperties'}
0x180030890  mov     [rcx], rax
0x180030893  mov     rbx, rcx
0x180030896  lea     rax, ??_7ActivationPropertiesOut@@6BISerializableParent@@@; const ActivationPropertiesOut::`vftable'{for `ISerializableParent'}
0x18003089d  mov     [rsp+68h+arg_10], rbp
0x1800308a5  mov     [rcx+8], rax
0x1800308a9  xor     ebp, ebp
0x1800308ab  lea     rax, ??_7ActivationPropertiesOut@@6BIGetCatalogObject@@@; const ActivationPropertiesOut::`vftable'{for `IGetCatalogObject'}
0x1800308b2  mov     [rsp+68h+var_8], rdi
0x1800308b7  mov     [rcx+10h], rax
0x1800308bb  lea     rax, ??_7ActivationPropertiesOut@@6BIPrivActivationPropertiesOut@@@; const ActivationPropertiesOut::`vftable'{for `IPrivActivationPropertiesOut'}
0x1800308c2  mov     [rcx+238h], rax
0x1800308c9  lea     rax, ??_7ActivationPropertiesOut@@6BIActivationPropOutClean@@@; const ActivationPropertiesOut::`vftable'{for `IActivationPropOutClean'}
0x1800308d0  mov     [rcx+240h], rax
0x1800308d7  mov     rax, [rcx+3B0h]
0x1800308de  test    rax, rax
0x1800308e1  jnz     loc_180030C75
0x1800308e7  mov     rdi, [rbx+3A0h]
0x1800308ee  test    rdi, rdi
0x1800308f1  jz      short loc_18003090D
0x1800308f3  mov     rcx, rdi; struct tagORPC_EXTENT_ARRAY *
0x1800308f6  call    ?ClearOrpcExtentArray@@YAXPEAUtagORPC_EXTENT_ARRAY@@@Z; ClearOrpcExtentArray(tagORPC_EXTENT_ARRAY *)
0x1800308fb  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030902  mov     r8, rdi; lpMem
0x180030905  xor     edx, edx; dwFlags
0x180030907  call    cs:__imp_HeapFree
0x18003090d  xor     eax, eax
0x18003090f  mov     [rsp+68h+arg_18], rsi
0x180030917  xorps   xmm0, xmm0
0x18003091a  movups  xmmword ptr [rbx+390h], xmm0
0x180030921  mov     [rbx+3A0h], rax
0x180030928  lea     rax, ??_7ScmReplyInfo@@6BIScmReplyInfo@@@; const ScmReplyInfo::`vftable'{for `IScmReplyInfo'}
0x18003092f  mov     rdi, [rbx+378h]
0x180030936  mov     [rbx+358h], rax
0x18003093d  lea     rax, ??_7ScmReplyInfo@@6BSerializableProperty@@@; const ScmReplyInfo::`vftable'{for `SerializableProperty'}
0x180030944  mov     [rbx+360h], rax
0x18003094b  test    rdi, rdi
0x18003094e  jz      loc_180030A22
0x180030954  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003095b  xor     edx, edx; dwFlags
0x18003095d  mov     [rbx+378h], rbp
0x180030964  mov     r8, [rdi+8]; lpMem
0x180030968  call    cs:__imp_HeapFree
0x18003096e  mov     rsi, [rdi+30h]
0x180030972  test    rsi, rsi
0x180030975  jz      short loc_180030991
0x180030977  mov     rcx, rsi; struct tagORPC_EXTENT_ARRAY *
0x18003097a  call    ?ClearOrpcExtentArray@@YAXPEAUtagORPC_EXTENT_ARRAY@@@Z; ClearOrpcExtentArray(tagORPC_EXTENT_ARRAY *)
0x18003097f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030986  mov     r8, rsi; lpMem
0x180030989  xor     edx, edx; dwFlags
0x18003098b  call    cs:__imp_HeapFree
0x180030991  xor     eax, eax
0x180030993  xorps   xmm0, xmm0
0x180030996  movups  xmmword ptr [rdi+20h], xmm0
0x18003099a  mov     [rdi+30h], rax
0x18003099e  mov     r8, [rdi+50h]; lpMem
0x1800309a2  test    r8, r8
0x1800309a5  jz      short loc_1800309B6
0x1800309a7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800309ae  xor     edx, edx; dwFlags
0x1800309b0  call    cs:__imp_HeapFree
0x1800309b6  mov     rcx, [rdi+78h]; string
0x1800309ba  call    cs:__imp_WindowsDeleteString
0x1800309c0  mov     rcx, [rdi+80h]; string
0x1800309c7  call    cs:__imp_WindowsDeleteString
0x1800309cd  mov     rcx, [rdi+88h]; string
0x1800309d4  call    cs:__imp_WindowsDeleteString
0x1800309da  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800309e1  xorps   xmm0, xmm0
0x1800309e4  movups  xmmword ptr [rdi+10h], xmm0
0x1800309e8  xor     eax, eax
0x1800309ea  mov     r8, rdi; lpMem
0x1800309ed  movups  xmmword ptr [rdi+20h], xmm0
0x1800309f1  xor     edx, edx; dwFlags
0x1800309f3  movups  xmmword ptr [rdi+30h], xmm0
0x1800309f7  movups  xmmword ptr [rdi+40h], xmm0
0x1800309fb  movups  xmmword ptr [rdi+50h], xmm0
0x1800309ff  movups  xmmword ptr [rdi+60h], xmm0
0x180030a03  movups  xmmword ptr [rdi+70h], xmm0
0x180030a07  movups  xmmword ptr [rdi+80h], xmm0
0x180030a0e  movups  xmmword ptr [rdi+90h], xmm0
0x180030a15  mov     [rdi+0A0h], rax
0x180030a1c  call    cs:__imp_HeapFree
0x180030a22  mov     r8, [rbx+380h]
0x180030a29  test    r8, r8
0x180030a2c  jnz     loc_180030CF7
0x180030a32  lea     rax, ??_7OutSerializer@ActivationPropertiesOut@@6B@; const ActivationPropertiesOut::OutSerializer::`vftable'
0x180030a39  lea     rdi, [rbx+268h]
0x180030a40  mov     [rbx+250h], rax
0x180030a47  cmp     [rbx+280h], rbp
0x180030a4e  jnz     loc_180030BC4
0x180030a54  mov     r8, [rbx+278h]; lpMem
0x180030a5b  mov     rsi, [rsp+68h+arg_18]
0x180030a63  mov     [rdi], ebp
0x180030a65  test    r8, r8
0x180030a68  jz      short loc_180030A80
0x180030a6a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030a71  xor     edx, edx; dwFlags
0x180030a73  call    cs:__imp_HeapFree
0x180030a79  mov     [rbx+278h], rbp
0x180030a80  mov     r8, [rbx+270h]; lpMem
0x180030a87  test    r8, r8
0x180030a8a  jnz     loc_180030B99
0x180030a90  mov     rcx, [rbx+348h]
0x180030a97  test    rcx, rcx
0x180030a9a  jnz     loc_180030D36
0x180030aa0  mov     [rbx+348h], rbp
0x180030aa7  lea     rax, ??_7ActivationProperties@@6BIActivationProperties@@@; const ActivationProperties::`vftable'{for `IActivationProperties'}
0x180030aae  mov     [rbx+354h], ebp
0x180030ab4  mov     rdi, [rbx+228h]
0x180030abb  mov     [rbx], rax
0x180030abe  lea     rax, ??_7ActivationProperties@@6BISerializableParent@@@; const ActivationProperties::`vftable'{for `ISerializableParent'}
0x180030ac5  mov     [rbx+8], rax
0x180030ac9  lea     rax, ??_7ActivationProperties@@6BIGetCatalogObject@@@; const ActivationProperties::`vftable'{for `IGetCatalogObject'}
0x180030ad0  mov     [rbx+10h], rax
0x180030ad4  test    rdi, rdi
0x180030ad7  jz      short loc_180030B39
0x180030ad9  mov     eax, 0FFFFFFFFh
0x180030ade  lock xadd [rdi+38h], eax
0x180030ae3  cmp     eax, 1
0x180030ae6  jnz     short loc_180030B39
0x180030ae8  mov     rcx, [rdi+30h]; Handle
0x180030aec  test    rcx, rcx
0x180030aef  jz      short loc_180030AFB
0x180030af1  call    cs:__imp_MesHandleFree
0x180030af7  mov     [rdi+30h], rbp
0x180030afb  cmp     [rdi], rbp
0x180030afe  jz      short loc_180030B1F
0x180030b00  mov     rcx, [rdi+10h]
0x180030b04  mov     rax, [rcx]
0x180030b07  mov     rax, [rax+10h]
0x180030b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b10  mov     rcx, [rdi]
0x180030b13  mov     rax, [rcx]
0x180030b16  mov     rax, [rax+10h]
0x180030b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b1f  mov     rcx, [rdi+8]
0x180030b23  test    rcx, rcx
0x180030b26  jnz     loc_180030C5B
0x180030b2c  mov     edx, 58h ; 'X'; unsigned __int64
0x180030b31  mov     rcx, rdi; void *
0x180030b34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180030b39  cmp     [rbx+2Ch], ebp
0x180030b3c  jz      short loc_180030B6A
0x180030b3e  mov     r8, [rbx+0A0h]; lpMem
0x180030b45  xor     edx, edx; dwFlags
0x180030b47  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030b4e  call    cs:__imp_HeapFree
0x180030b54  mov     r8, [rbx+0A8h]; lpMem
0x180030b5b  xor     edx, edx; dwFlags
0x180030b5d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030b64  call    cs:__imp_HeapFree
0x180030b6a  mov     eax, [rbx+40h]
0x180030b6d  test    eax, eax
0x180030b6f  jnz     loc_180030D53
0x180030b75  mov     r8, [rbx+70h]; lpMem
0x180030b79  mov     rdi, [rsp+68h+var_8]
0x180030b7e  mov     rbp, [rsp+68h+arg_10]
0x180030b86  mov     rbx, [rsp+68h+arg_8]
0x180030b8b  test    r8, r8
0x180030b8e  jnz     loc_180030D91
0x180030b94  add     rsp, 68h
0x180030b98  retn
0x180030b99  lea     rax, [rbx+2A8h]
0x180030ba0  cmp     r8, rax
0x180030ba3  jz      loc_180030A90
0x180030ba9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030bb0  xor     edx, edx; dwFlags
0x180030bb2  call    cs:__imp_HeapFree
0x180030bb8  mov     [rbx+270h], rbp
0x180030bbf  jmp     loc_180030A90
0x180030bc4  mov     esi, ebp
0x180030bc6  mov     [rsp+68h+var_10], r14
0x180030bcb  lea     r14, [rbx+288h]
0x180030bd2  cmp     [rdi], ebp
0x180030bd4  jbe     short loc_180030C1F
0x180030bd6  mov     [rsp+68h+var_18], r15
0x180030bdb  mov     r8, [rbx+280h]
0x180030be2  xor     edx, edx; dwFlags
0x180030be4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030beb  mov     eax, esi
0x180030bed  lea     r15, ds:0[rax*8]
0x180030bf5  mov     r8, [r15+r8]; lpMem
0x180030bf9  call    cs:__imp_HeapFree
0x180030bff  mov     rcx, [r14]
0x180030c02  test    rcx, rcx
0x180030c05  jz      short loc_180030C14
0x180030c07  mov     rcx, [r15+rcx]
0x180030c0b  test    rcx, rcx
0x180030c0e  jnz     loc_180030D25
0x180030c14  inc     esi
0x180030c16  cmp     esi, [rdi]
0x180030c18  jb      short loc_180030BDB
0x180030c1a  mov     r15, [rsp+68h+var_18]
0x180030c1f  mov     r8, [rbx+280h]; lpMem
0x180030c26  xor     edx, edx; dwFlags
0x180030c28  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030c2f  call    cs:__imp_HeapFree
0x180030c35  mov     r8, [r14]; lpMem
0x180030c38  xor     edx, edx; dwFlags
0x180030c3a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030c41  mov     [rbx+280h], rbp
0x180030c48  call    cs:__imp_HeapFree
0x180030c4e  mov     [r14], rbp
0x180030c51  mov     r14, [rsp+68h+var_10]
0x180030c56  jmp     loc_180030A54
0x180030c5b  cmp     rcx, [rdi]
0x180030c5e  jz      loc_180030B2C
0x180030c64  mov     rax, [rcx]
0x180030c67  mov     rax, [rax+10h]
0x180030c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c70  jmp     loc_180030B2C
0x180030c75  mov     [rsp+68h+var_28], rax
0x180030c7a  lea     rcx, ??_7?$GenericStreamBase@UIStream@@UCoTaskMemAllocAllocator@@@@6BIStream@@@; const GenericStreamBase<IStream,CoTaskMemAllocAllocator>::`vftable'{for `IStream'}
0x180030c81  mov     [rsp+68h+var_48], rcx
0x180030c86  lea     rcx, ??_7?$GenericStreamBase@UIStream@@UCoTaskMemAllocAllocator@@@@6BIBufferInternal@@@; const GenericStreamBase<IStream,CoTaskMemAllocAllocator>::`vftable'{for `IBufferInternal'}
0x180030c8d  mov     [rsp+68h+var_40], rcx
0x180030c92  lea     rcx, [rsp+68h+var_48]; pStm
0x180030c97  mov     [rsp+68h+var_38], 1
0x180030ca0  mov     [rsp+68h+var_30], ebp
0x180030ca4  mov     [rsp+68h+var_20], ebp
0x180030ca8  mov     [rsp+68h+var_1C], 1
0x180030cb0  mov     eax, [rax]
0x180030cb2  mov     [rsp+68h+var_2C], eax
0x180030cb6  lea     rax, ??_7GenericCoTaskMemStream@@6BIStream@@@; const GenericCoTaskMemStream::`vftable'{for `IStream'}
0x180030cbd  mov     [rsp+68h+var_48], rax
0x180030cc2  lea     rax, ??_7?$GenericStreamBase@UIStream@@UCoTaskMemAllocAllocator@@@@6BIBufferInternal@@@; const GenericStreamBase<IStream,CoTaskMemAllocAllocator>::`vftable'{for `IBufferInternal'}
0x180030cc9  mov     [rsp+68h+var_40], rax
0x180030cce  call    cs:__imp_CoReleaseMarshalData
0x180030cd4  mov     rcx, [rbx+3B0h]; pv
0x180030cdb  call    cs:__imp_CoTaskMemFree
0x180030ce1  lea     rcx, [rsp+68h+var_48]
0x180030ce6  mov     [rbx+3B0h], rbp
0x180030ced  call    ??1?$GenericStreamBase@UIStream@@UCoTaskMemAllocAllocator@@@@UEAA@XZ; GenericStreamBase<IStream,CoTaskMemAllocAllocator>::~GenericStreamBase<IStream,CoTaskMemAllocAllocator>(void)
0x180030cf2  jmp     loc_1800308E7
0x180030cf7  mov     r8, [r8+8]; lpMem
0x180030cfb  xor     edx, edx; dwFlags
0x180030cfd  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030d04  call    cs:__imp_HeapFree
0x180030d0a  mov     r8, [rbx+380h]; lpMem
0x180030d11  xor     edx, edx; dwFlags
0x180030d13  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030d1a  call    cs:__imp_HeapFree
0x180030d20  jmp     loc_180030A32
0x180030d25  mov     rax, [rcx]
0x180030d28  mov     rax, [rax+10h]
0x180030d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d31  jmp     loc_180030C14
0x180030d36  cmp     [rbx+350h], ebp
0x180030d3c  jnz     loc_180030AA0
0x180030d42  mov     rax, [rcx]
0x180030d45  mov     rax, [rax+10h]
0x180030d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d4e  jmp     loc_180030AA0
0x180030d53  cmp     [rbx+70h], rbp
0x180030d57  jz      loc_180030B75
0x180030d5d  mov     edi, ebp
0x180030d5f  test    eax, eax
0x180030d61  jz      loc_180030B75
0x180030d67  mov     r8, [rbx+70h]
0x180030d6b  xor     edx, edx; dwFlags
0x180030d6d  mov     eax, edi
0x180030d6f  lea     rcx, [rax+rax*4]
0x180030d73  mov     r8, [r8+rcx*8+20h]; lpMem
0x180030d78  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030d7f  call    cs:__imp_HeapFree
0x180030d85  inc     edi
0x180030d87  cmp     edi, [rbx+40h]
0x180030d8a  jb      short loc_180030D67
0x180030d8c  jmp     loc_180030B75
0x180030d91  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180030d98  xor     edx, edx; dwFlags
0x180030d9a  call    cs:__imp_HeapFree
0x180030da0  jmp     loc_180030B94
```
