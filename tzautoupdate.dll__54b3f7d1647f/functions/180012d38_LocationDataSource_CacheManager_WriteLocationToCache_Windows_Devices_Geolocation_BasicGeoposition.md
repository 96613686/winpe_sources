# LocationDataSource::CacheManager::WriteLocationToCache(Windows::Devices::Geolocation::BasicGeoposition &)

- ea: `0x180012d38`
- end: `0x180012df2`
- name: `?WriteLocationToCache@CacheManager@LocationDataSource@@QEAAXAEAUBasicGeoposition@Geolocation@Devices@Windows@@@Z`
- size: `186`
- prototype: `void __fastcall(struct Cache **this, struct Windows::Devices::Geolocation::BasicGeoposition *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001126c`

## callees

- `0x18000cfec`
- `0x180011b0c`
- `0x180011e2c`
- `0x180012d38`

## pseudocode

```c
void __fastcall LocationDataSource::CacheManager::WriteLocationToCache(
        struct Cache **this,
        struct Windows::Devices::Geolocation::BasicGeoposition *a2)
{
  __int64 v4; // xmm1_8
  __int64 v5; // rax
  _BYTE v6[16]; // [rsp+20h] [rbp-98h] BYREF
  __int64 v7; // [rsp+30h] [rbp-88h]
  __int64 v8; // [rsp+38h] [rbp-80h]
  _QWORD v9[13]; // [rsp+50h] [rbp-68h] BYREF
  char v10; // [rsp+C0h] [rbp+8h] BYREF

  Cache::Lock(*this, (Cache::Proxy *)v6);
  if ( !*(_BYTE *)(v7 + 24)
    || (COERCE_DOUBLE(v4 = _mm_load_si128((const __m128i *)&_xmm).m128i_i64[0]),
        COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)a2 - *(double *)v7) & v4) >= 0.0001)
    || COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*((double *)a2 + 1) - *(double *)(v7 + 8)) & v4) >= 0.0001 )
  {
    *(_BYTE *)(v7 + 24) = 1;
    v5 = v7;
    *(_OWORD *)v7 = *(_OWORD *)a2;
    *(_QWORD *)(v5 + 16) = *((_QWORD *)a2 + 2);
    *(_BYTE *)(v8 + 120) = 1;
  }
  v10 = 1;
  Cache::ValueProxy<bool>::SetValue(v9, &v10);
  *((_BYTE *)this + 8) = 1;
  Cache::Proxy::~Proxy((Cache::Proxy *)v6);
}

```

## disassembly

```asm
0x180012d38  mov     [rsp+arg_8], rbx
0x180012d3d  push    rdi
0x180012d3e  sub     rsp, 0B0h
0x180012d45  mov     rbx, rdx
0x180012d48  mov     rdi, rcx
0x180012d4b  mov     rcx, [rcx]
0x180012d4e  lea     rdx, [rsp+0B8h+var_98]
0x180012d53  call    ?Lock@Cache@@QEAA?AVProxy@1@XZ; Cache::Lock(void)
0x180012d58  mov     rax, [rsp+0B8h+var_88]
0x180012d5d  cmp     byte ptr [rax+18h], 0
0x180012d61  jz      short loc_180012D97
0x180012d63  movsd   xmm0, qword ptr [rbx]
0x180012d67  subsd   xmm0, qword ptr [rax]
0x180012d6b  movdqa  xmm1, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x180012d73  movsd   xmm2, cs:__real@3f1a36e2eb1c432d
0x180012d7b  andps   xmm0, xmm1
0x180012d7e  comisd  xmm2, xmm0
0x180012d82  jbe     short loc_180012D97
0x180012d84  movsd   xmm0, qword ptr [rbx+8]
0x180012d89  subsd   xmm0, qword ptr [rax+8]
0x180012d8e  andps   xmm0, xmm1
0x180012d91  comisd  xmm2, xmm0
0x180012d95  ja      short loc_180012DB9
0x180012d97  mov     byte ptr [rax+18h], 1
0x180012d9b  mov     rax, [rsp+0B8h+var_88]
0x180012da0  movups  xmm0, xmmword ptr [rbx]
0x180012da3  movups  xmmword ptr [rax], xmm0
0x180012da6  movsd   xmm1, qword ptr [rbx+10h]
0x180012dab  movsd   qword ptr [rax+10h], xmm1
0x180012db0  mov     rax, [rsp+0B8h+var_80]
0x180012db5  mov     byte ptr [rax+78h], 1
0x180012db9  lea     rdx, [rsp+0B8h+arg_0]
0x180012dc1  mov     [rsp+0B8h+arg_0], 1
0x180012dc9  lea     rcx, [rsp+0B8h+var_68]
0x180012dce  call    ?SetValue@?$ValueProxy@_N@Cache@@QEAAXAEB_N@Z; Cache::ValueProxy<bool>::SetValue(bool const &)
0x180012dd3  lea     rcx, [rsp+0B8h+var_98]; this
0x180012dd8  mov     byte ptr [rdi+8], 1
0x180012ddc  call    ??1Proxy@Cache@@QEAA@XZ; Cache::Proxy::~Proxy(void)
0x180012de1  mov     rbx, [rsp+0B8h+arg_8]
0x180012de9  add     rsp, 0B0h
0x180012df0  pop     rdi
0x180012df1  retn
```
