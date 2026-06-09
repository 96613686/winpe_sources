# CVolumeLocationCache::CVolumeLocationCache(void)

- ea: `0x18000a12c`
- end: `0x18000a188`
- name: `??0CVolumeLocationCache@@QEAA@XZ`
- size: `92`
- prototype: `CVolumeLocationCache *__fastcall(CVolumeLocationCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003684`

## callees

- `0x180008cb4`
- `0x18000a12c`
- `0x18000a190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a148`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a148`

## pseudocode

```c
CVolumeLocationCache *__fastcall CVolumeLocationCache::CVolumeLocationCache(CVolumeLocationCache *this)
{
  VolumeLocation *v2; // rdi
  __int64 v3; // rsi

  *(_DWORD *)this = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = (CVolumeLocationCache *)((char *)this + 56);
  v3 = 32;
  do
  {
    VolumeLocation::VolumeLocation(v2);
    v2 = (VolumeLocation *)((char *)v2 + 40);
    --v3;
  }
  while ( v3 );
  CFILETIME::SetToUTC((LPFILETIME)this + 167);
  return this;
}

```

## disassembly

```asm
0x18000a12c  mov     [rsp+arg_0], rbx
0x18000a131  mov     [rsp+arg_8], rsi
0x18000a136  push    rdi
0x18000a137  sub     rsp, 20h
0x18000a13b  mov     rbx, rcx
0x18000a13e  mov     dword ptr [rcx], 0
0x18000a144  add     rcx, 8; lpCriticalSection
0x18000a148  call    cs:__imp_InitializeCriticalSection
0x18000a14e  lea     rdi, [rbx+38h]
0x18000a152  mov     esi, 20h ; ' '
0x18000a157  mov     rcx, rdi; this
0x18000a15a  call    ??0VolumeLocation@@QEAA@XZ; VolumeLocation::VolumeLocation(void)
0x18000a15f  add     rdi, 28h ; '('
0x18000a163  sub     rsi, 1
0x18000a167  jnz     short loc_18000A157
0x18000a169  lea     rcx, [rbx+538h]; lpFileTime
0x18000a170  call    ?SetToUTC@CFILETIME@@QEAAXXZ; CFILETIME::SetToUTC(void)
0x18000a175  mov     rsi, [rsp+28h+arg_8]
0x18000a17a  mov     rax, rbx
0x18000a17d  mov     rbx, [rsp+28h+arg_0]
0x18000a182  add     rsp, 20h
0x18000a186  pop     rdi
0x18000a187  retn
```
