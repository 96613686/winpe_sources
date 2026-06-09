# CGallery::_StartThumbnailWorkerThread(DirectUI::Element *,bool,IUnknown *)

- ea: `0x180021d6c`
- end: `0x180021ea1`
- name: `?_StartThumbnailWorkerThread@CGallery@@AEAAJPEAVElement@DirectUI@@_NPEAUIUnknown@@@Z`
- size: `309`
- prototype: `int(CGallery *__hidden this, struct DirectUI::Element *, bool, struct IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800214d8`

## callees

- `0x18000268c`
- `0x18001fd48`
- `0x18002033c`
- `0x180021d6c`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180021e02`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180021e02`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180021e1d`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180021e1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGallery::_StartThumbnailWorkerThread(
        CGallery *this,
        struct DirectUI::Element *a2,
        char a3,
        struct IUnknown *a4)
{
  int v8; // edi
  HBITMAP (*v9)(struct IUnknown *, bool); // r15
  void *v10; // rax
  bool v11; // r8
  CGalleryThumbnailWorkItem *v12; // rbx
  const struct _GUID *v13; // rdx
  const struct _GUID *v14; // r8
  const struct _GUID *v15; // r9
  DirectUI::Element *v16; // rcx
  void *v18; // [rsp+70h] [rbp+8h] BYREF

  v8 = -2147024882;
  v9 = (HBITMAP (*)(struct IUnknown *, bool))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 88LL))(*((_QWORD *)this + 1));
  v10 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v10;
  if ( v10 )
  {
    v11 = a3 || *((_BYTE *)this + 40);
    v12 = CGalleryThumbnailWorkItem::CGalleryThumbnailWorkItem((CGalleryThumbnailWorkItem *)v10, a2, v11, a4, v9);
  }
  else
  {
    v12 = 0;
  }
  if ( v12 )
  {
    IUnknown_QueryService(
      *((IUnknown **)this + 2),
      &IID_ITrackEvents,
      &GUID_f002a70d_e74b_4721_9243_5704338cfc2f,
      (void **)v12 + 15);
    v8 = 0;
    v16 = (DirectUI::Element *)*((_QWORD *)v12 + 9);
    if ( v16 )
      v8 = DirectUI::Element::AddListener(v16, (CGalleryThumbnailWorkItem *)((char *)v12 + 64));
    if ( v8 >= 0 )
    {
      v18 = 0;
      v8 = IUnknown_QueryServiceObject(*((struct IUnknown **)this + 2), v13, v14, v15, &v18);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(void *, CGalleryThumbnailWorkItem *, GUID *, _QWORD))(*(_QWORD *)v18 + 24LL))(
               v18,
               v12,
               &GUID_f1654bc8_39e6_4d6d_99b9_af3b31eb247f,
               0);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
      }
      (*(void (__fastcall **)(CGalleryThumbnailWorkItem *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021d6c  push    rbx
0x180021d6e  push    rbp
0x180021d6f  push    rsi
0x180021d70  push    rdi
0x180021d71  push    r14
0x180021d73  push    r15
0x180021d75  sub     rsp, 38h
0x180021d79  mov     rbp, r9
0x180021d7c  mov     bl, r8b
0x180021d7f  mov     r14, rdx
0x180021d82  mov     rsi, rcx
0x180021d85  mov     edi, 8007000Eh
0x180021d8a  mov     rcx, [rcx+8]
0x180021d8e  mov     rax, [rcx]
0x180021d91  mov     rax, [rax+58h]
0x180021d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d9a  mov     r15, rax
0x180021d9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021da4  mov     ecx, 80h; unsigned __int64
0x180021da9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021dae  mov     [rsp+68h+arg_0], rax
0x180021db3  test    rax, rax
0x180021db6  jz      short loc_180021DE1
0x180021db8  test    bl, bl
0x180021dba  jnz     short loc_180021DC6
0x180021dbc  cmp     [rsi+28h], bl
0x180021dbf  jnz     short loc_180021DC6
0x180021dc1  xor     r8d, r8d
0x180021dc4  jmp     short loc_180021DC9
0x180021dc6  mov     r8b, 1; bool
0x180021dc9  mov     [rsp+68h+var_48], r15; HBITMAP (*)(struct IUnknown *, bool)
0x180021dce  mov     r9, rbp; struct IUnknown *
0x180021dd1  mov     rdx, r14; struct DirectUI::Element *
0x180021dd4  mov     rcx, rax; this
0x180021dd7  call    ??0CGalleryThumbnailWorkItem@@QEAA@PEAVElement@DirectUI@@_NPEAUIUnknown@@P6APEAUHBITMAP__@@21@Z@Z; CGalleryThumbnailWorkItem::CGalleryThumbnailWorkItem(DirectUI::Element *,bool,IUnknown *,HBITMAP__ * (*)(IUnknown *,bool))
0x180021ddc  mov     rbx, rax
0x180021ddf  jmp     short loc_180021DE3
0x180021de1  xor     ebx, ebx
0x180021de3  test    rbx, rbx
0x180021de6  jz      loc_180021E91
0x180021dec  lea     r9, [rbx+78h]; ppvOut
0x180021df0  lea     r8, _GUID_f002a70d_e74b_4721_9243_5704338cfc2f; riid
0x180021df7  lea     rdx, IID_ITrackEvents; guidService
0x180021dfe  mov     rcx, [rsi+10h]; punk
0x180021e02  call    cs:__imp_IUnknown_QueryService
0x180021e09  nop     dword ptr [rax+rax+00h]
0x180021e0e  xor     edi, edi
0x180021e10  mov     rcx, [rbx+48h]
0x180021e14  test    rcx, rcx
0x180021e17  jz      short loc_180021E2B
0x180021e19  lea     rdx, [rbx+40h]
0x180021e1d  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180021e24  nop     dword ptr [rax+rax+00h]
0x180021e29  mov     edi, eax
0x180021e2b  test    edi, edi
0x180021e2d  js      short loc_180021E91
0x180021e2f  mov     [rsp+68h+arg_0], 0
0x180021e38  lea     rax, [rsp+68h+arg_0]
0x180021e3d  mov     [rsp+68h+var_48], rax; void **
0x180021e42  mov     rcx, [rsi+10h]; struct IUnknown *
0x180021e46  call    ?IUnknown_QueryServiceObject@@YAJPEAUIUnknown@@AEBU_GUID@@11PEAPEAX@Z; IUnknown_QueryServiceObject(IUnknown *,_GUID const &,_GUID const &,_GUID const &,void * *)
0x180021e4b  mov     edi, eax
0x180021e4d  test    eax, eax
0x180021e4f  js      short loc_180021E82
0x180021e51  mov     rcx, [rsp+68h+arg_0]
0x180021e56  mov     rax, [rcx]
0x180021e59  xor     r9d, r9d
0x180021e5c  lea     r8, _GUID_f1654bc8_39e6_4d6d_99b9_af3b31eb247f
0x180021e63  mov     rdx, rbx
0x180021e66  mov     rax, [rax+18h]
0x180021e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e6f  mov     edi, eax
0x180021e71  mov     rcx, [rsp+68h+arg_0]
0x180021e76  mov     rax, [rcx]
0x180021e79  mov     rax, [rax+10h]
0x180021e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e82  mov     rax, [rbx]
0x180021e85  mov     rcx, rbx
0x180021e88  mov     rax, [rax+10h]
0x180021e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e91  mov     eax, edi
0x180021e93  add     rsp, 38h
0x180021e97  pop     r15
0x180021e99  pop     r14
0x180021e9b  pop     rdi
0x180021e9c  pop     rsi
0x180021e9d  pop     rbp
0x180021e9e  pop     rbx
0x180021e9f  retn
```
