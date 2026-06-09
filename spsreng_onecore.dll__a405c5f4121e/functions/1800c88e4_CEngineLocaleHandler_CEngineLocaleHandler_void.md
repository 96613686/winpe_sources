# CEngineLocaleHandler::~CEngineLocaleHandler(void)

- ea: `0x1800c88e4`
- end: `0x1800c8a3c`
- name: `??1CEngineLocaleHandler@@UEAA@XZ`
- size: `344`
- prototype: `void __fastcall(CEngineLocaleHandler *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800157b8`
- `0x1800157e4`
- `0x1800ce9f8`
- `0x1800da574`

## callees

- `0x180002db8`
- `0x1800034d4`
- `0x18001b800`
- `0x1800c88e4`
- `0x1800d0f0c`
- `0x1800d2cd4`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c89ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c89ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c89d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c89d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CEngineLocaleHandler::~CEngineLocaleHandler(CEngineLocaleHandler *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 v6; // rcx
  struct ILangDataPack *v7; // rcx
  void *v8; // rdi
  __int64 v9; // rcx

  v2 = *((_QWORD *)this + 11);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 12);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 13);
  if ( v4 )
    (**v4)(v4, 1);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 15);
  if ( v5 )
    (**v5)(v5, 1);
  v6 = *((_QWORD *)this + 16);
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 80LL))(v6, 1);
  v7 = (struct ILangDataPack *)*((_QWORD *)this + 17);
  if ( v7 )
  {
    ILangDataPack::Destroy(v7);
    *((_QWORD *)this + 17) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 14);
  if ( v8 )
  {
    CShortcutTF::~CShortcutTF(*((CShortcutTF **)this + 14));
    operator delete(v8, 0x18u);
  }
  v9 = *((_QWORD *)this + 26);
  if ( v9 )
  {
    *((_QWORD *)this + 26) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  CoTaskMemFree(*((LPVOID *)this + 29));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 216);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 208);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 80);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 72);
  ReleaseSharedObject(*((const struct CShareable **)this + 8));
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 56);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 48);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 32);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 24);
}

```

## disassembly

```asm
0x1800c88e4  mov     [rsp+arg_0], rbx
0x1800c88e9  push    rdi
0x1800c88ea  sub     rsp, 20h
0x1800c88ee  mov     rbx, rcx
0x1800c88f1  mov     rcx, [rcx+58h]
0x1800c88f5  test    rcx, rcx
0x1800c88f8  jz      short loc_1800C8906
0x1800c88fa  mov     rax, [rcx]
0x1800c88fd  mov     rax, [rax+10h]
0x1800c8901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8906  mov     rcx, [rbx+60h]
0x1800c890a  test    rcx, rcx
0x1800c890d  jz      short loc_1800C891B
0x1800c890f  mov     rax, [rcx]
0x1800c8912  mov     rax, [rax+10h]
0x1800c8916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c891b  mov     rcx, [rbx+68h]
0x1800c891f  mov     edi, 1
0x1800c8924  test    rcx, rcx
0x1800c8927  jz      short loc_1800C8936
0x1800c8929  mov     rax, [rcx]
0x1800c892c  mov     edx, edi
0x1800c892e  mov     rax, [rax]
0x1800c8931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8936  mov     rcx, [rbx+78h]
0x1800c893a  test    rcx, rcx
0x1800c893d  jz      short loc_1800C894C
0x1800c893f  mov     rax, [rcx]
0x1800c8942  mov     edx, edi
0x1800c8944  mov     rax, [rax]
0x1800c8947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c894c  mov     rcx, [rbx+80h]
0x1800c8953  test    rcx, rcx
0x1800c8956  jz      short loc_1800C8966
0x1800c8958  mov     rax, [rcx]
0x1800c895b  mov     edx, edi
0x1800c895d  mov     rax, [rax+50h]
0x1800c8961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8966  mov     rcx, [rbx+88h]; struct ILangDataPack *
0x1800c896d  test    rcx, rcx
0x1800c8970  jz      short loc_1800C8982
0x1800c8972  call    ?Destroy@ILangDataPack@@SAXPEAV1@@Z; ILangDataPack::Destroy(ILangDataPack *)
0x1800c8977  mov     qword ptr [rbx+88h], 0
0x1800c8982  mov     rdi, [rbx+70h]
0x1800c8986  test    rdi, rdi
0x1800c8989  jz      short loc_1800C89A0
0x1800c898b  mov     rcx, rdi; this
0x1800c898e  call    ??1CShortcutTF@@QEAA@XZ; CShortcutTF::~CShortcutTF(void)
0x1800c8993  mov     edx, 18h; unsigned __int64
0x1800c8998  mov     rcx, rdi; void *
0x1800c899b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c89a0  lea     rdi, [rbx+0D0h]
0x1800c89a7  mov     rcx, [rdi]
0x1800c89aa  test    rcx, rcx
0x1800c89ad  jz      short loc_1800C89C3
0x1800c89af  mov     qword ptr [rdi], 0
0x1800c89b6  mov     rax, [rcx]
0x1800c89b9  mov     rax, [rax+10h]
0x1800c89bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c89c2  nop
0x1800c89c3  mov     rcx, [rbx+0E8h]; pv
0x1800c89ca  call    cs:__imp_CoTaskMemFree
0x1800c89d0  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800c89d7  call    cs:__imp_DeleteCriticalSection
0x1800c89dd  lea     rcx, [rbx+0D8h]
0x1800c89e4  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c89e9  mov     rcx, rdi
0x1800c89ec  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c89f1  lea     rcx, [rbx+50h]
0x1800c89f5  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c89fa  lea     rcx, [rbx+48h]
0x1800c89fe  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c8a03  nop
0x1800c8a04  mov     rcx, [rbx+40h]; struct CShareable *
0x1800c8a08  call    ?ReleaseSharedObject@@YAXPEBVCShareable@@@Z; ReleaseSharedObject(CShareable const *)
0x1800c8a0d  nop
0x1800c8a0e  lea     rcx, [rbx+38h]
0x1800c8a12  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c8a17  lea     rcx, [rbx+30h]
0x1800c8a1b  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c8a20  lea     rcx, [rbx+20h]
0x1800c8a24  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c8a29  lea     rcx, [rbx+18h]
0x1800c8a2d  mov     rbx, [rsp+28h+arg_0]
0x1800c8a32  add     rsp, 20h
0x1800c8a36  pop     rdi
0x1800c8a37  jmp     ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
```
