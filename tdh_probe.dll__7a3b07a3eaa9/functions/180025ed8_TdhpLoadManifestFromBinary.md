# TdhpLoadManifestFromBinary

- ea: `0x180025ed8`
- end: `0x1800260db`
- name: `TdhpLoadManifestFromBinary`
- size: `515`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180024210`

## callees

- `0x180007c48`
- `0x1800207c0`
- `0x180024374`
- `0x180024568`
- `0x180025558`
- `0x180025ed8`
- `0x18002b9d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025f8d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025f8d`
- `ntdll!RtlReleaseSRWLockShared` at `0x180025f6b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180025f6b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180025f4c`
- `ntdll!RtlAcquireSRWLockShared` at `0x180025f4c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026080`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026080`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002605c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002605c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025ff7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025fdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800260a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025fdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800260a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025fce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025fe2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026094`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025fce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025fe2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026094`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TdhpLoadManifestFromBinary(wchar_t *a1)
{
  unsigned int v2; // r14d
  struct TDH_CACHE *v3; // rcx
  struct TDH_PROVIDER_BINARY_ENTRY *v4; // rbx
  const wchar_t *v5; // r8
  const wchar_t *v6; // r9
  struct _GUID *v7; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  unsigned int ProviderGuids; // eax
  unsigned int v11; // ebx
  struct TDH_CACHE *v12; // rcx
  HANDLE v13; // rax
  unsigned int v15[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  __int128 v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+90h] [rbp-70h]
  _BYTE Mem[80]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[528]; // [rsp+F0h] [rbp-10h] BYREF

  v16[0] = 0;
  v17 = 0;
  v2 = 5;
  v18 = 0;
  v15[0] = 5;
  v19 = 0;
  v20 = 0;
  RtlAcquireSRWLockShared((char *)g_TdhCache + 0x4000);
  v4 = TdhpCacheLookupBinary(v3, a1);
  RtlReleaseSRWLockShared((char *)g_TdhCache + 0x4000);
  if ( v4 )
  {
    LODWORD(v4) = 0;
  }
  else
  {
    if ( !(unsigned int)_o__wcsnicmp(a1, L"\\Device\\", 8) )
    {
      LODWORD(v4) = ConvertToVolumeNamePath(a1, v22);
      if ( (_DWORD)v4 )
      {
        LODWORD(v4) = 2;
        goto LABEL_23;
      }
      a1 = (wchar_t *)v22;
    }
    v7 = (struct _GUID *)Mem;
    while ( 1 )
    {
      if ( (_DWORD)v4 == 122 )
      {
        if ( v7 != (struct _GUID *)Mem && v7 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
        }
        v9 = GetProcessHeap();
        v7 = (struct _GUID *)HeapAlloc(v9, 8u, 16LL * v2);
        if ( !v7 )
        {
          LODWORD(v4) = 14;
          goto LABEL_23;
        }
      }
      ProviderGuids = ResourceHolder::GetProviderGuidsEx((ResourceHolder *)v16, a1, v5, v6, v2, v7, v15);
      LODWORD(v4) = ProviderGuids;
      if ( ProviderGuids != 122 )
        break;
      v2 = v15[0];
    }
    if ( !ProviderGuids )
    {
      v11 = v15[0];
      if ( !v15[0] )
      {
        LODWORD(v4) = 5007;
        goto LABEL_23;
      }
      RtlAcquireSRWLockExclusive((char *)g_TdhCache + 0x4000);
      LODWORD(v4) = TdhpCacheInsertBinary(v12, a1, v11, v7);
      RtlReleaseSRWLockExclusive((char *)g_TdhCache + 0x4000);
    }
    if ( v7 != (struct _GUID *)Mem && v7 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v7);
    }
  }
LABEL_23:
  ResourceHolder::Close((ResourceHolder *)v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025ed8  mov     [rsp-8+arg_8], rbx
0x180025edd  mov     [rsp-8+arg_10], rsi
0x180025ee2  push    rbp
0x180025ee3  push    rdi
0x180025ee4  push    r14
0x180025ee6  lea     rbp, [rsp-210h]
0x180025eee  sub     rsp, 310h
0x180025ef5  mov     rax, cs:__security_cookie
0x180025efc  xor     rax, rsp
0x180025eff  mov     [rbp+220h+var_20], rax
0x180025f06  mov     rsi, rcx
0x180025f09  mov     [rsp+320h+var_2D0], 0
0x180025f12  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180025f19  xorps   xmm0, xmm0
0x180025f1c  xorps   xmm1, xmm1
0x180025f1f  mov     [rsp+320h+var_2B8], 0
0x180025f27  mov     r14d, 5
0x180025f2d  movdqa  [rsp+320h+var_2B0], xmm0
0x180025f33  add     rcx, 4000h
0x180025f3a  mov     [rsp+320h+var_2E0], r14d
0x180025f3f  movdqa  [rbp+220h+var_2A0], xmm1
0x180025f44  mov     [rbp+220h+var_290], 0
0x180025f4c  call    cs:__imp_RtlAcquireSRWLockShared
0x180025f52  mov     rdx, rsi; wchar_t *
0x180025f55  call    ?TdhpCacheLookupBinary@@YAPEAUTDH_PROVIDER_BINARY_ENTRY@@PEAUTDH_CACHE@@PEB_W@Z; TdhpCacheLookupBinary(TDH_CACHE *,wchar_t const *)
0x180025f5a  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180025f61  mov     rbx, rax
0x180025f64  add     rcx, 4000h
0x180025f6b  call    cs:__imp_RtlReleaseSRWLockShared
0x180025f71  test    rbx, rbx
0x180025f74  jz      short loc_180025F7D
0x180025f76  xor     ebx, ebx
0x180025f78  jmp     loc_1800260A8
0x180025f7d  mov     r8d, 8
0x180025f83  lea     rdx, aDevice; "\\Device\\"
0x180025f8a  mov     rcx, rsi
0x180025f8d  call    cs:__imp__o__wcsnicmp
0x180025f93  test    eax, eax
0x180025f95  jnz     short loc_180025FB7
0x180025f97  lea     rdx, [rbp+220h+var_230]
0x180025f9b  mov     rcx, rsi
0x180025f9e  call    ConvertToVolumeNamePath
0x180025fa3  mov     ebx, eax
0x180025fa5  test    eax, eax
0x180025fa7  jz      short loc_180025FB3
0x180025fa9  mov     ebx, 2
0x180025fae  jmp     loc_1800260A8
0x180025fb3  lea     rsi, [rbp+220h+var_230]
0x180025fb7  lea     rdi, [rbp+220h+Mem]
0x180025fbb  cmp     ebx, 7Ah ; 'z'
0x180025fbe  jnz     short loc_180026005
0x180025fc0  lea     rax, [rbp+220h+Mem]
0x180025fc4  cmp     rdi, rax
0x180025fc7  jz      short loc_180025FE2
0x180025fc9  test    rdi, rdi
0x180025fcc  jz      short loc_180025FE2
0x180025fce  call    cs:__imp_GetProcessHeap
0x180025fd4  mov     r8, rdi; lpMem
0x180025fd7  xor     edx, edx; dwFlags
0x180025fd9  mov     rcx, rax; hHeap
0x180025fdc  call    cs:__imp_HeapFree
0x180025fe2  call    cs:__imp_GetProcessHeap
0x180025fe8  mov     r8d, r14d
0x180025feb  mov     edx, 8; dwFlags
0x180025ff0  shl     r8, 4; dwBytes
0x180025ff4  mov     rcx, rax; hHeap
0x180025ff7  call    cs:__imp_HeapAlloc
0x180025ffd  mov     rdi, rax
0x180026000  test    rax, rax
0x180026003  jz      short loc_180026034
0x180026005  lea     rax, [rsp+320h+var_2E0]
0x18002600a  mov     rdx, rsi; wchar_t *
0x18002600d  mov     [rsp+320h+var_2F0], rax; unsigned int *
0x180026012  lea     rcx, [rsp+320h+var_2D0]; this
0x180026017  mov     [rsp+320h+var_2F8], rdi; struct _GUID *
0x18002601c  mov     [rsp+320h+var_300], r14d; unsigned int
0x180026021  call    ?GetProviderGuidsEx@ResourceHolder@@QEAAKPEB_W00KPEAU_GUID@@PEAK@Z; ResourceHolder::GetProviderGuidsEx(wchar_t const *,wchar_t const *,wchar_t const *,ulong,_GUID *,ulong *)
0x180026026  mov     ebx, eax
0x180026028  cmp     eax, 7Ah ; 'z'
0x18002602b  jnz     short loc_18002603B
0x18002602d  mov     r14d, [rsp+320h+var_2E0]
0x180026032  jmp     short loc_180025FBB
0x180026034  mov     ebx, 0Eh
0x180026039  jmp     short loc_1800260A8
0x18002603b  test    eax, eax
0x18002603d  jnz     short loc_180026086
0x18002603f  mov     ebx, [rsp+320h+var_2E0]
0x180026043  test    ebx, ebx
0x180026045  jnz     short loc_18002604E
0x180026047  mov     ebx, 138Fh
0x18002604c  jmp     short loc_1800260A8
0x18002604e  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180026055  add     rcx, 4000h
0x18002605c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180026062  mov     r9, rdi; struct _GUID *
0x180026065  mov     r8d, ebx; unsigned int
0x180026068  mov     rdx, rsi; wchar_t *
0x18002606b  call    ?TdhpCacheInsertBinary@@YAKPEAUTDH_CACHE@@PEA_WKPEAU_GUID@@@Z; TdhpCacheInsertBinary(TDH_CACHE *,wchar_t *,ulong,_GUID *)
0x180026070  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180026077  mov     ebx, eax
0x180026079  add     rcx, 4000h
0x180026080  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180026086  lea     rax, [rbp+220h+Mem]
0x18002608a  cmp     rdi, rax
0x18002608d  jz      short loc_1800260A8
0x18002608f  test    rdi, rdi
0x180026092  jz      short loc_1800260A8
0x180026094  call    cs:__imp_GetProcessHeap
0x18002609a  mov     r8, rdi; lpMem
0x18002609d  xor     edx, edx; dwFlags
0x18002609f  mov     rcx, rax; hHeap
0x1800260a2  call    cs:__imp_HeapFree
0x1800260a8  lea     rcx, [rsp+320h+var_2D0]; this
0x1800260ad  call    ?Close@ResourceHolder@@QEAAXXZ; ResourceHolder::Close(void)
0x1800260b2  mov     eax, ebx
0x1800260b4  mov     rcx, [rbp+220h+var_20]
0x1800260bb  xor     rcx, rsp; StackCookie
0x1800260be  call    __security_check_cookie
0x1800260c3  lea     r11, [rsp+320h+var_10]
0x1800260cb  mov     rbx, [r11+28h]
0x1800260cf  mov     rsi, [r11+30h]
0x1800260d3  mov     rsp, r11
0x1800260d6  pop     r14
0x1800260d8  pop     rdi
0x1800260d9  pop     rbp
0x1800260da  retn
```
