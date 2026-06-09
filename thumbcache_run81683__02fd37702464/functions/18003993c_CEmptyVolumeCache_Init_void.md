# CEmptyVolumeCache::_Init(void)

- ea: `0x18003993c`
- end: `0x1800399dc`
- name: `?_Init@CEmptyVolumeCache@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(CEmptyVolumeCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800388cc`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18003993c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003996e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800399bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003996e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800399bc`

## string_xrefs

- `0x180039984`: `onecoreuap\shell\ext\thumbnailcache\dll\emptyvolumecache.cpp`

## pseudocode

```c
__int64 __fastcall CEmptyVolumeCache::_Init(LPVOID *this)
{
  LPVOID *v1; // rbx
  HRESULT Instance; // ebx
  __int64 v4; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = this + 2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 2);
  Instance = CoCreateInstance(
               &GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f,
               0,
               3u,
               &GUID_3413b9cd_0db3_4e97_8bf4_68fb100d1815,
               v1);
  if ( Instance < 0 )
  {
    v4 = 154;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\dll\\emptyvolumecache.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 3);
  Instance = CoCreateInstance(
               &GUID_2155fee3_2419_4373_b102_6843707eb41f,
               0,
               3u,
               &GUID_3413b9cd_0db3_4e97_8bf4_68fb100d1815,
               this + 3);
  if ( Instance < 0 )
  {
    v4 = 155;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18003993c  mov     [rsp+arg_0], rbx
0x180039941  push    rdi
0x180039942  sub     rsp, 30h
0x180039946  lea     rbx, [rcx+10h]
0x18003994a  mov     rdi, rcx
0x18003994d  mov     rcx, rbx
0x180039950  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039955  xor     edx, edx; pUnkOuter
0x180039957  mov     qword ptr [rsp+38h+ppv], rbx; int
0x18003995c  lea     r9, _GUID_3413b9cd_0db3_4e97_8bf4_68fb100d1815; riid
0x180039963  lea     rcx, _GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f; rclsid
0x18003996a  lea     r8d, [rdx+3]; dwClsContext
0x18003996e  call    cs:__imp_CoCreateInstance
0x180039974  mov     ebx, eax
0x180039976  test    eax, eax
0x180039978  jns     short loc_180039997
0x18003997a  mov     edx, 9Ah; void *
0x18003997f  mov     rcx, [rsp+38h]; this
0x180039984  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003998b  mov     r9d, ebx; char *
0x18003998e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039993  mov     eax, ebx
0x180039995  jmp     short loc_1800399D1
0x180039997  lea     rbx, [rdi+18h]
0x18003999b  mov     rcx, rbx
0x18003999e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800399a3  xor     edx, edx; pUnkOuter
0x1800399a5  mov     qword ptr [rsp+38h+ppv], rbx; ppv
0x1800399aa  lea     r9, _GUID_3413b9cd_0db3_4e97_8bf4_68fb100d1815; riid
0x1800399b1  lea     rcx, _GUID_2155fee3_2419_4373_b102_6843707eb41f; rclsid
0x1800399b8  lea     r8d, [rdx+3]; dwClsContext
0x1800399bc  call    cs:__imp_CoCreateInstance
0x1800399c2  mov     ebx, eax
0x1800399c4  test    eax, eax
0x1800399c6  jns     short loc_1800399CF
0x1800399c8  mov     edx, 9Bh
0x1800399cd  jmp     short loc_18003997F
0x1800399cf  xor     eax, eax
0x1800399d1  mov     rbx, [rsp+38h+arg_0]
0x1800399d6  add     rsp, 30h
0x1800399da  pop     rdi
0x1800399db  retn
```
