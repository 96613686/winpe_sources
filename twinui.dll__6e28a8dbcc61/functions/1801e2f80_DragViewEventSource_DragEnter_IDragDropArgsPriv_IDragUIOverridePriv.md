# DragViewEventSource::DragEnter(IDragDropArgsPriv *,IDragUIOverridePriv * *)

- ea: `0x1801e2f80`
- end: `0x1801e335b`
- name: `?DragEnter@DragViewEventSource@@UEAAJPEAUIDragDropArgsPriv@@PEAPEAUIDragUIOverridePriv@@@Z`
- size: `987`
- prototype: `__int64 __fastcall(DragViewEventSource *__hidden this, struct IDragDropArgsPriv *, struct IDragUIOverridePriv **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000cf94`
- `0x180038274`
- `0x18003c5e4`
- `0x1800542a8`
- `0x180074b74`
- `0x18013d330`
- `0x1801e21e4`
- `0x1801e2f80`
- `0x1801e3d1c`
- `0x1801e4374`
- `0x1801e447c`
- `0x1801e4580`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e30ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3224`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e32e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e331b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e30ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3224`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e32e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e331b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DragViewEventSource::DragEnter(
        DragViewEventSource *this,
        struct IDragDropArgsPriv *a2,
        struct IDragUIOverridePriv **a3)
{
  DragViewEventSource *v5; // rcx
  int OperationType; // edi
  int OperationId; // eax
  unsigned int v8; // ebx
  DragViewEventSource *v10; // rcx
  int SourceAppId; // eax
  int v12; // eax
  __int64 (__fastcall *v13)(struct IDragDropArgsPriv *, GUID *, __int64 *); // rbx
  int v14; // eax
  struct tagPOINT *v15; // r9
  __int64 v16; // rdi
  int v17; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-49h]
  unsigned int v20; // [rsp+30h] [rbp-39h] BYREF
  struct IDragDropArgsPriv *v21; // [rsp+38h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+48h] [rbp-21h] BYREF
  int v24; // [rsp+50h] [rbp-19h] BYREF
  __int64 v25; // [rsp+58h] [rbp-11h] BYREF
  __int64 v26; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v27[8]; // [rsp+68h] [rbp-1h] BYREF
  struct IDragDropArgsPriv **v28; // [rsp+70h] [rbp+7h]
  unsigned int *v29; // [rsp+78h] [rbp+Fh]
  char v30; // [rsp+80h] [rbp+17h]
  struct _GUID v31; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v21 = a2;
  *a3 = 0;
  OperationType = DragViewEventSource::GetOperationType((char *)this - 8);
  if ( OperationType )
  {
    v20 = 0;
    v28 = &v21;
    v29 = &v20;
    v30 = 1;
    v31 = 0;
    OperationId = DragViewEventSource::_GetOperationId(v5, v21, &v31);
    v8 = OperationId;
    if ( OperationId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"shell\\twinui\\dragdrop\\lib\\dragview.cpp",
        (const char *)(unsigned int)OperationId,
        v19);
      (*(void (__fastcall **)(struct IDragDropArgsPriv *, _QWORD))(*(_QWORD *)v21 + 48LL))(v21, v20);
      return v8;
    }
    pv = 0;
    if ( OperationType == 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        0);
      SourceAppId = DragViewEventSource::_GetSourceAppId(v10, v21, (unsigned __int16 **)&pv);
      v8 = SourceAppId;
      if ( SourceAppId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17F,
          (unsigned int)"shell\\twinui\\dragdrop\\lib\\dragview.cpp",
          (const char *)(unsigned int)SourceAppId,
          v19);
        if ( pv )
          CoTaskMemFree(pv);
LABEL_32:
        (*(void (__fastcall **)(struct IDragDropArgsPriv *, _QWORD))(*(_QWORD *)v21 + 48LL))(v21, v20);
        return v8;
      }
    }
    v25 = 0;
    v24 = 0;
    v12 = (*(__int64 (__fastcall **)(struct IDragDropArgsPriv *, __int64 *, int *))(*(_QWORD *)v21 + 24LL))(
            v21,
            &v25,
            &v24);
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"shell\\twinui\\dragdrop\\lib\\dragview.cpp",
        (const char *)(unsigned int)v12,
        v19);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_32;
    }
    v23 = 0;
    v13 = *(__int64 (__fastcall **)(struct IDragDropArgsPriv *, GUID *, __int64 *))(*(_QWORD *)v21 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v14 = v13(v21, &GUID_7b840471_5900_4d85_a90b_10cb85fe3552, &v23);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"shell\\twinui\\dragdrop\\lib\\dragview.cpp",
        (const char *)(unsigned int)v14,
        v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_32;
    }
    if ( OperationType == 1 )
    {
      wil::AcquireSRWLockExclusive(v27, (char *)this + 72);
      v26 = *((_QWORD *)this + 6);
      v16 = v26;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
      v8 = -2147023728;
      if ( v16 )
        v8 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, LPVOID, __int64))(*(_QWORD *)v16 + 24LL))(
               v16,
               &v31,
               pv,
               v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v27);
      if ( (v8 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x191,
          (unsigned int)"shell\\twinui\\dragdrop\\lib\\dragview.cpp",
          (const char *)v8,
          v19);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_32;
      }
    }
    v17 = DragViewEventSource::_RequestDataForOperation((DragViewEventSource *)((char *)this - 8), v21, &v31, v15);
    v8 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"shell\\twinui\\dragdrop\\lib\\dragview.cpp",
        (const char *)(unsigned int)v17,
        v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_32;
    }
    v18 = Microsoft::WRL::Details::MakeAndInitialize<ShellDragUIOverride,IDragUIOverridePriv,>(a3);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"shell\\twinui\\dragdrop\\lib\\dragview.cpp",
        (const char *)(unsigned int)v18,
        v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_32;
    }
    v20 = 2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    if ( pv )
      CoTaskMemFree(pv);
    (*(void (__fastcall **)(struct IDragDropArgsPriv *, _QWORD))(*(_QWORD *)v21 + 48LL))(v21, v20);
  }
  return 0;
}

```

## disassembly

```asm
0x1801e2f80  mov     [rsp-8+arg_18], rbx
0x1801e2f85  push    rbp
0x1801e2f86  push    rsi
0x1801e2f87  push    rdi
0x1801e2f88  push    r14
0x1801e2f8a  push    r15
0x1801e2f8c  lea     rbp, [rsp-37h]
0x1801e2f91  sub     rsp, 0A0h
0x1801e2f98  mov     rax, cs:__security_cookie
0x1801e2f9f  xor     rax, rsp
0x1801e2fa2  mov     [rbp+57h+var_28], rax
0x1801e2fa6  mov     r14, r8
0x1801e2fa9  mov     rsi, rcx
0x1801e2fac  mov     [rbp+57h+var_88], rdx
0x1801e2fb0  mov     qword ptr [r8], 0
0x1801e2fb7  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1801e2fbb  call    ?GetOperationType@DragViewEventSource@@AEBA?AW4OperationType@1@PEAUIDragDropArgsPriv@@@Z; DragViewEventSource::GetOperationType(IDragDropArgsPriv *)
0x1801e2fc0  mov     edi, eax
0x1801e2fc2  test    eax, eax
0x1801e2fc4  jz      loc_1801E3336
0x1801e2fca  mov     [rbp+57h+var_90], 0
0x1801e2fd1  lea     rax, [rbp+57h+var_88]
0x1801e2fd5  mov     [rbp+57h+var_50], rax
0x1801e2fd9  lea     rax, [rbp+57h+var_90]
0x1801e2fdd  mov     [rbp+57h+var_48], rax
0x1801e2fe1  mov     [rbp+57h+var_40], 1
0x1801e2fe5  xorps   xmm0, xmm0
0x1801e2fe8  movups  xmmword ptr [rbp+57h+var_38.Data1], xmm0
0x1801e2fec  lea     r8, [rbp+57h+var_38]; struct _GUID *
0x1801e2ff0  mov     rdx, [rbp+57h+var_88]; struct IDragDropArgsPriv *
0x1801e2ff4  call    ?_GetOperationId@DragViewEventSource@@AEBAJPEAUIDragDropArgsPriv@@PEAU_GUID@@@Z; DragViewEventSource::_GetOperationId(IDragDropArgsPriv *,_GUID *)
0x1801e2ff9  mov     ebx, eax
0x1801e2ffb  test    eax, eax
0x1801e2ffd  jns     short loc_1801E3033
0x1801e2fff  mov     rcx, [rbp+5Fh]; this
0x1801e3003  mov     r9d, eax; char *
0x1801e3006  lea     r8, aShellTwinuiDra; "shell\\twinui\\dragdrop\\lib\\dragview."...
0x1801e300d  mov     edx, 179h; void *
0x1801e3012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3017  nop
0x1801e3018  mov     rcx, [rbp+57h+var_88]
0x1801e301c  mov     rdx, [rcx]
0x1801e301f  mov     rax, [rdx+30h]
0x1801e3023  mov     edx, [rbp+57h+var_90]
0x1801e3026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e302b  nop
0x1801e302c  mov     eax, ebx
0x1801e302e  jmp     loc_1801E3338
0x1801e3033  mov     [rbp+57h+pv], 0
0x1801e303b  cmp     edi, 1
0x1801e303e  jnz     short loc_1801E309D
0x1801e3040  xor     edx, edx
0x1801e3042  lea     rcx, [rbp+57h+pv]
0x1801e3046  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801e304b  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x1801e304f  mov     rdx, [rbp+57h+var_88]; struct IDragDropArgsPriv *
0x1801e3053  call    ?_GetSourceAppId@DragViewEventSource@@AEBAJPEAUIDragDropArgsPriv@@PEAPEAG@Z; DragViewEventSource::_GetSourceAppId(IDragDropArgsPriv *,ushort * *)
0x1801e3058  mov     ebx, eax
0x1801e305a  test    eax, eax
0x1801e305c  jns     short loc_1801E309D
0x1801e305e  mov     rcx, [rbp+5Fh]; this
0x1801e3062  mov     r9d, eax; char *
0x1801e3065  lea     r8, aShellTwinuiDra; "shell\\twinui\\dragdrop\\lib\\dragview."...
0x1801e306c  mov     edx, 17Fh; void *
0x1801e3071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3076  nop
0x1801e3077  mov     rcx, [rbp+57h+pv]; pv
0x1801e307b  test    rcx, rcx
0x1801e307e  jz      short loc_1801E3087
0x1801e3080  call    cs:__imp_CoTaskMemFree
0x1801e3086  nop
0x1801e3087  mov     rcx, [rbp+57h+var_88]
0x1801e308b  mov     rax, [rcx]
0x1801e308e  mov     edx, [rbp+57h+var_90]
0x1801e3091  mov     rax, [rax+30h]
0x1801e3095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e309a  nop
0x1801e309b  jmp     short loc_1801E302C
0x1801e309d  mov     [rbp+57h+var_68], 0
0x1801e30a5  mov     [rbp+57h+var_70], 0
0x1801e30ac  mov     rcx, [rbp+57h+var_88]
0x1801e30b0  mov     rax, [rcx]
0x1801e30b3  lea     r8, [rbp+57h+var_70]
0x1801e30b7  lea     rdx, [rbp+57h+var_68]
0x1801e30bb  mov     rax, [rax+18h]
0x1801e30bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e30c4  mov     ebx, eax
0x1801e30c6  test    eax, eax
0x1801e30c8  jns     short loc_1801E310C
0x1801e30ca  mov     rcx, [rbp+5Fh]; this
0x1801e30ce  mov     r9d, eax; char *
0x1801e30d1  lea     r8, aShellTwinuiDra; "shell\\twinui\\dragdrop\\lib\\dragview."...
0x1801e30d8  mov     edx, 185h; void *
0x1801e30dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e30e2  nop
0x1801e30e3  mov     rcx, [rbp+57h+pv]; pv
0x1801e30e7  test    rcx, rcx
0x1801e30ea  jz      short loc_1801E30F3
0x1801e30ec  call    cs:__imp_CoTaskMemFree
0x1801e30f2  nop
0x1801e30f3  mov     rcx, [rbp+57h+var_88]
0x1801e30f7  mov     rax, [rcx]
0x1801e30fa  mov     edx, [rbp+57h+var_90]
0x1801e30fd  mov     rax, [rax+30h]
0x1801e3101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3106  nop
0x1801e3107  jmp     loc_1801E302C
0x1801e310c  mov     [rbp+57h+var_78], 0
0x1801e3114  mov     rax, [rbp+57h+var_88]
0x1801e3118  mov     rcx, [rax]
0x1801e311b  mov     rbx, [rcx+20h]
0x1801e311f  lea     rcx, [rbp+57h+var_78]
0x1801e3123  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e3128  lea     r8, [rbp+57h+var_78]
0x1801e312c  lea     rdx, _GUID_7b840471_5900_4d85_a90b_10cb85fe3552
0x1801e3133  mov     rcx, [rbp+57h+var_88]
0x1801e3137  mov     rax, rbx
0x1801e313a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e313f  mov     ebx, eax
0x1801e3141  test    eax, eax
0x1801e3143  jns     short loc_1801E3191
0x1801e3145  mov     rcx, [rbp+5Fh]; this
0x1801e3149  mov     r9d, eax; char *
0x1801e314c  lea     r8, aShellTwinuiDra; "shell\\twinui\\dragdrop\\lib\\dragview."...
0x1801e3153  mov     edx, 189h; void *
0x1801e3158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e315d  nop
0x1801e315e  lea     rcx, [rbp+57h+var_78]
0x1801e3162  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e3167  nop
0x1801e3168  mov     rcx, [rbp+57h+pv]; pv
0x1801e316c  test    rcx, rcx
0x1801e316f  jz      short loc_1801E3178
0x1801e3171  call    cs:__imp_CoTaskMemFree
0x1801e3177  nop
0x1801e3178  mov     rcx, [rbp+57h+var_88]
0x1801e317c  mov     rax, [rcx]
0x1801e317f  mov     edx, [rbp+57h+var_90]
0x1801e3182  mov     rax, [rax+30h]
0x1801e3186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e318b  nop
0x1801e318c  jmp     loc_1801E302C
0x1801e3191  cmp     edi, 1
0x1801e3194  jnz     loc_1801E3244
0x1801e319a  lea     rdx, [rsi+48h]
0x1801e319e  lea     rcx, [rbp+57h+var_58]
0x1801e31a2  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801e31a7  nop
0x1801e31a8  mov     rdi, [rsi+30h]
0x1801e31ac  mov     [rbp+57h+var_60], rdi
0x1801e31b0  lea     rcx, [rbp+57h+var_60]
0x1801e31b4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1801e31b9  nop
0x1801e31ba  mov     ebx, 80070490h
0x1801e31bf  test    rdi, rdi
0x1801e31c2  jz      short loc_1801E31E1
0x1801e31c4  mov     rax, [rdi]
0x1801e31c7  mov     r9, [rbp+57h+var_68]
0x1801e31cb  mov     r8, [rbp+57h+pv]
0x1801e31cf  lea     rdx, [rbp+57h+var_38]
0x1801e31d3  mov     rcx, rdi
0x1801e31d6  mov     rax, [rax+18h]
0x1801e31da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e31df  mov     ebx, eax
0x1801e31e1  lea     rcx, [rbp+57h+var_60]
0x1801e31e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e31ea  nop
0x1801e31eb  lea     rcx, [rbp+57h+var_58]; this
0x1801e31ef  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801e31f4  test    ebx, ebx
0x1801e31f6  jns     short loc_1801E3244
0x1801e31f8  mov     rcx, [rbp+5Fh]; this
0x1801e31fc  mov     r9d, ebx; char *
0x1801e31ff  lea     r8, aShellTwinuiDra; "shell\\twinui\\dragdrop\\lib\\dragview."...
0x1801e3206  mov     edx, 191h; void *
0x1801e320b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3210  nop
0x1801e3211  lea     rcx, [rbp+57h+var_78]
0x1801e3215  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e321a  nop
0x1801e321b  mov     rcx, [rbp+57h+pv]; pv
0x1801e321f  test    rcx, rcx
0x1801e3222  jz      short loc_1801E322B
0x1801e3224  call    cs:__imp_CoTaskMemFree
0x1801e322a  nop
0x1801e322b  mov     rcx, [rbp+57h+var_88]
0x1801e322f  mov     rax, [rcx]
0x1801e3232  mov     edx, [rbp+57h+var_90]
0x1801e3235  mov     rax, [rax+30h]
0x1801e3239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e323e  nop
0x1801e323f  jmp     loc_1801E302C
0x1801e3244  lea     r8, [rbp+57h+var_38]; struct _GUID *
0x1801e3248  mov     rdx, [rbp+57h+var_88]; struct IDragDropArgsPriv *
0x1801e324c  lea     rcx, [rsi-8]; this
0x1801e3250  call    ?_RequestDataForOperation@DragViewEventSource@@AEAAJPEAUIDragDropArgsPriv@@AEBU_GUID@@AEAUtagPOINT@@@Z; DragViewEventSource::_RequestDataForOperation(IDragDropArgsPriv *,_GUID const &,tagPOINT &)
0x1801e3255  mov     ebx, eax
0x1801e3257  test    eax, eax
0x1801e3259  jns     short loc_1801E32A7
0x1801e325b  mov     rcx, [rbp+5Fh]; this
0x1801e325f  mov     r9d, eax; char *
0x1801e3262  lea     r8, aShellTwinuiDra; "shell\\twinui\\dragdrop\\lib\\dragview."...
0x1801e3269  mov     edx, 194h; void *
0x1801e326e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3273  nop
0x1801e3274  lea     rcx, [rbp+57h+var_78]
0x1801e3278  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e327d  nop
0x1801e327e  mov     rcx, [rbp+57h+pv]; pv
0x1801e3282  test    rcx, rcx
0x1801e3285  jz      short loc_1801E328E
0x1801e3287  call    cs:__imp_CoTaskMemFree
0x1801e328d  nop
0x1801e328e  mov     rcx, [rbp+57h+var_88]
0x1801e3292  mov     rax, [rcx]
0x1801e3295  mov     edx, [rbp+57h+var_90]
0x1801e3298  mov     rax, [rax+30h]
0x1801e329c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e32a1  nop
0x1801e32a2  jmp     loc_1801E302C
0x1801e32a7  mov     rcx, r14
0x1801e32aa  call    ??$MakeAndInitialize@VShellDragUIOverride@@UIDragUIOverridePriv@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIDragUIOverridePriv@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ShellDragUIOverride,IDragUIOverridePriv,>(IDragUIOverridePriv * *)
0x1801e32af  mov     ebx, eax
0x1801e32b1  test    eax, eax
0x1801e32b3  jns     short loc_1801E3301
0x1801e32b5  mov     rcx, [rbp+5Fh]; this
0x1801e32b9  mov     r9d, eax; char *
0x1801e32bc  lea     r8, aShellTwinuiDra; "shell\\twinui\\dragdrop\\lib\\dragview."...
0x1801e32c3  mov     edx, 197h; void *
0x1801e32c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e32cd  nop
0x1801e32ce  lea     rcx, [rbp+57h+var_78]
0x1801e32d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e32d7  nop
0x1801e32d8  mov     rcx, [rbp+57h+pv]; pv
0x1801e32dc  test    rcx, rcx
0x1801e32df  jz      short loc_1801E32E8
0x1801e32e1  call    cs:__imp_CoTaskMemFree
0x1801e32e7  nop
0x1801e32e8  mov     rcx, [rbp+57h+var_88]
0x1801e32ec  mov     rax, [rcx]
0x1801e32ef  mov     edx, [rbp+57h+var_90]
0x1801e32f2  mov     rax, [rax+30h]
0x1801e32f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e32fb  nop
0x1801e32fc  jmp     loc_1801E302C
0x1801e3301  mov     [rbp+57h+var_90], 2
0x1801e3308  lea     rcx, [rbp+57h+var_78]
0x1801e330c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e3311  nop
0x1801e3312  mov     rcx, [rbp+57h+pv]; pv
0x1801e3316  test    rcx, rcx
0x1801e3319  jz      short loc_1801E3322
0x1801e331b  call    cs:__imp_CoTaskMemFree
0x1801e3321  nop
0x1801e3322  mov     rcx, [rbp+57h+var_88]
0x1801e3326  mov     rax, [rcx]
0x1801e3329  mov     edx, [rbp+57h+var_90]
0x1801e332c  mov     rax, [rax+30h]
0x1801e3330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3335  nop
0x1801e3336  xor     eax, eax
0x1801e3338  mov     rcx, [rbp+57h+var_28]
0x1801e333c  xor     rcx, rsp; StackCookie
0x1801e333f  call    __security_check_cookie
0x1801e3344  mov     rbx, [rsp+0C0h+arg_18]
0x1801e334c  add     rsp, 0A0h
0x1801e3353  pop     r15
0x1801e3355  pop     r14
0x1801e3357  pop     rdi
0x1801e3358  pop     rsi
0x1801e3359  pop     rbp
0x1801e335a  retn
```
