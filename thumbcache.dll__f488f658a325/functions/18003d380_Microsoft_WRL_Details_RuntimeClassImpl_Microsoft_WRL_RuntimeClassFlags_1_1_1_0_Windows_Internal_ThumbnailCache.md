# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::ThumbnailCache::IThumbnailCacheInternal,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18003d380`
- end: `0x18003d3df`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIThumbnailCacheInternal@ThumbnailCache@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003cd9c`
- `0x18003d380`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d3a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::ThumbnailCache::IThumbnailCacheInternal,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::ThumbnailCache::IThumbnailCacheInternal,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003d380  mov     [rsp+arg_0], rbx
0x18003d385  push    rdi
0x18003d386  sub     rsp, 20h
0x18003d38a  mov     qword ptr [r8], 0
0x18003d391  mov     ecx, 20h ; ' '; cb
0x18003d396  mov     dword ptr [rdx], 0
0x18003d39c  mov     rbx, r8
0x18003d39f  mov     rdi, rdx
0x18003d3a2  call    cs:__imp_CoTaskMemAlloc
0x18003d3a8  mov     r8, rax
0x18003d3ab  test    rax, rax
0x18003d3ae  jnz     short loc_18003D3B7
0x18003d3b0  mov     eax, 8007000Eh
0x18003d3b5  jmp     short loc_18003D3D4
0x18003d3b7  lea     rdx, [rsp+28h+arg_8]
0x18003d3bc  mov     [rsp+28h+arg_8], 0
0x18003d3c4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIThumbnailCacheInternal@ThumbnailCache@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::ThumbnailCache::IThumbnailCacheInternal,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003d3c9  mov     dword ptr [rdi], 2
0x18003d3cf  xor     eax, eax
0x18003d3d1  mov     [rbx], r8
0x18003d3d4  mov     rbx, [rsp+28h+arg_0]
0x18003d3d9  add     rsp, 20h
0x18003d3dd  pop     rdi
0x18003d3de  retn
```
