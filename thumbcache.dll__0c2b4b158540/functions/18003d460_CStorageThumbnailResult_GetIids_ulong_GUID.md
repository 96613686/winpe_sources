# CStorageThumbnailResult::GetIids(ulong *,_GUID * *)

- ea: `0x18003d460`
- end: `0x18003d4bf`
- name: `?GetIids@CStorageThumbnailResult@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CStorageThumbnailResult *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003cde4`
- `0x18003d460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d482`

## pseudocode

```c
__int64 __fastcall CStorageThumbnailResult::GetIids(CStorageThumbnailResult *this, unsigned int *a2, struct _GUID **a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Storage::ThumbnailCache::IThumbnailResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003d460  mov     [rsp+arg_0], rbx
0x18003d465  push    rdi
0x18003d466  sub     rsp, 20h
0x18003d46a  mov     qword ptr [r8], 0
0x18003d471  mov     ecx, 20h ; ' '; cb
0x18003d476  mov     dword ptr [rdx], 0
0x18003d47c  mov     rbx, r8
0x18003d47f  mov     rdi, rdx
0x18003d482  call    cs:__imp_CoTaskMemAlloc
0x18003d488  mov     r8, rax
0x18003d48b  test    rax, rax
0x18003d48e  jnz     short loc_18003D497
0x18003d490  mov     eax, 8007000Eh
0x18003d495  jmp     short loc_18003D4B4
0x18003d497  lea     rdx, [rsp+28h+arg_8]
0x18003d49c  mov     [rsp+28h+arg_8], 0
0x18003d4a4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIThumbnailResult@ThumbnailCache@Storage@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Storage::ThumbnailCache::IThumbnailResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003d4a9  mov     dword ptr [rdi], 2
0x18003d4af  xor     eax, eax
0x18003d4b1  mov     [rbx], r8
0x18003d4b4  mov     rbx, [rsp+28h+arg_0]
0x18003d4b9  add     rsp, 20h
0x18003d4bd  pop     rdi
0x18003d4be  retn
```
