# CThumbnailCacheAPI::~CThumbnailCacheAPI(void)

- ea: `0x1800193ac`
- end: `0x180019472`
- name: `??1CThumbnailCacheAPI@@EEAA@XZ`
- size: `198`
- prototype: `void __fastcall(CThumbnailCacheAPI *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019370`

## callees

- `0x180003624`
- `0x1800193ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001945f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001945f`

## pseudocode

```c
void __fastcall CThumbnailCacheAPI::~CThumbnailCacheAPI(CThumbnailCacheAPI *this)
{
  unsigned __int64 *v2; // rdi
  unsigned __int64 i; // rsi

  *(_QWORD *)this = &CThumbnailCacheAPI::`vftable'{for `Microsoft::WRL::ChainInterfaces<IThumbnailCache3,IThumbnailCache2,IThumbnailCache,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 1) = &CThumbnailCacheAPI::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailCachePrivate,IThumbnailCachePrimer,IImageStore>'};
  *((_QWORD *)this + 2) = &CThumbnailCacheAPI::`vftable'{for `IThumbnailCachePrimer'};
  *((_QWORD *)this + 3) = &CThumbnailCacheAPI::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IImageStore>'};
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 600);
  v2 = (unsigned __int64 *)((char *)this + 576);
  if ( *((_QWORD *)this + 71) )
  {
    for ( i = 0; i < *v2; ++i )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*((_QWORD *)this + 71) + 8LL + 16 * i);
    CoTaskMemFree(*((LPVOID *)this + 71));
    *((_QWORD *)this + 71) = 0;
  }
  *((_QWORD *)this + 74) = 0;
  *v2 = 0;
  *((_DWORD *)this + 9) = -1073741823;
}

```

## disassembly

```asm
0x1800193ac  mov     [rsp+arg_0], rbx
0x1800193b1  mov     [rsp+arg_8], rsi
0x1800193b6  push    rdi
0x1800193b7  sub     rsp, 20h
0x1800193bb  lea     rax, ??_7CThumbnailCacheAPI@@6B?$ChainInterfaces@UIThumbnailCache3@@UIThumbnailCache2@@UIThumbnailCache@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@WRL@Microsoft@@@; const CThumbnailCacheAPI::`vftable'{for `Microsoft::WRL::ChainInterfaces<IThumbnailCache3,IThumbnailCache2,IThumbnailCache,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800193c2  mov     rbx, rcx
0x1800193c5  mov     [rcx], rax
0x1800193c8  lea     rax, ??_7CThumbnailCacheAPI@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIThumbnailCachePrivate@@UIThumbnailCachePrimer@@UIImageStore@@@Details@WRL@Microsoft@@@; const CThumbnailCacheAPI::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailCachePrivate,IThumbnailCachePrimer,IImageStore>'}
0x1800193cf  mov     [rcx+8], rax
0x1800193d3  lea     rax, ??_7CThumbnailCacheAPI@@6BIThumbnailCachePrimer@@@; const CThumbnailCacheAPI::`vftable'{for `IThumbnailCachePrimer'}
0x1800193da  mov     [rcx+10h], rax
0x1800193de  lea     rax, ??_7CThumbnailCacheAPI@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIImageStore@@@Details@WRL@Microsoft@@@; const CThumbnailCacheAPI::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IImageStore>'}
0x1800193e5  mov     [rcx+18h], rax
0x1800193e9  add     rcx, 258h
0x1800193f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800193f5  cmp     qword ptr [rbx+238h], 0
0x1800193fd  lea     rdi, [rbx+240h]
0x180019404  jnz     short loc_18001942F
0x180019406  mov     rsi, [rsp+28h+arg_8]
0x18001940b  mov     qword ptr [rbx+250h], 0
0x180019416  mov     qword ptr [rdi], 0
0x18001941d  mov     dword ptr [rbx+24h], 0C0000001h
0x180019424  mov     rbx, [rsp+28h+arg_0]
0x180019429  add     rsp, 20h
0x18001942d  pop     rdi
0x18001942e  retn
0x18001942f  xor     esi, esi
0x180019431  cmp     [rdi], rsi
0x180019434  jbe     short loc_180019458
0x180019436  mov     rax, [rbx+238h]
0x18001943d  mov     rcx, rsi
0x180019440  shl     rcx, 4
0x180019444  add     rax, 8
0x180019448  add     rcx, rax
0x18001944b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019450  inc     rsi
0x180019453  cmp     rsi, [rdi]
0x180019456  jb      short loc_180019436
0x180019458  mov     rcx, [rbx+238h]; pv
0x18001945f  call    cs:__imp_CoTaskMemFree
0x180019465  mov     qword ptr [rbx+238h], 0
0x180019470  jmp     short loc_180019406
```
