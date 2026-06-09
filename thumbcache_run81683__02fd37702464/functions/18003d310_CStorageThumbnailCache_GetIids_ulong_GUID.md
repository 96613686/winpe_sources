# CStorageThumbnailCache::GetIids(ulong *,_GUID * *)

- ea: `0x18003d310`
- end: `0x18003d36f`
- name: `?GetIids@CStorageThumbnailCache@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CStorageThumbnailCache *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003cd78`
- `0x18003d310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d332`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d332`

## pseudocode

```c
__int64 __fastcall CStorageThumbnailCache::GetIids(CStorageThumbnailCache *this, unsigned int *a2, struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Storage::ThumbnailCache::IThumbnailCache,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18003d310  mov     [rsp+arg_0], rbx
0x18003d315  push    rdi
0x18003d316  sub     rsp, 20h
0x18003d31a  mov     qword ptr [r8], 0
0x18003d321  mov     ecx, 20h ; ' '; cb
0x18003d326  mov     dword ptr [rdx], 0
0x18003d32c  mov     rbx, r8
0x18003d32f  mov     rdi, rdx
0x18003d332  call    cs:__imp_CoTaskMemAlloc
0x18003d338  mov     r8, rax
0x18003d33b  test    rax, rax
0x18003d33e  jnz     short loc_18003D347
0x18003d340  mov     eax, 8007000Eh
0x18003d345  jmp     short loc_18003D364
0x18003d347  lea     rdx, [rsp+28h+arg_8]
0x18003d34c  mov     [rsp+28h+arg_8], 0
0x18003d354  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIThumbnailCache@ThumbnailCache@Storage@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Storage::ThumbnailCache::IThumbnailCache,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003d359  mov     dword ptr [rdi], 2
0x18003d35f  xor     eax, eax
0x18003d361  mov     [rbx], r8
0x18003d364  mov     rbx, [rsp+28h+arg_0]
0x18003d369  add     rsp, 20h
0x18003d36d  pop     rdi
0x18003d36e  retn
```
