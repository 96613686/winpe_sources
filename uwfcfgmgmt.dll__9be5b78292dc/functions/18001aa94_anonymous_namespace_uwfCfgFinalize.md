# _anonymous_namespace_::uwfCfgFinalize

- ea: `0x18001aa94`
- end: `0x18001aacb`
- name: `_anonymous_namespace_::uwfCfgFinalize`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `36`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017d50`
- `0x180017df0`
- `0x180017e90`
- `0x180017fa0`
- `0x180018080`
- `0x1800182e0`
- `0x180018390`
- `0x180018430`
- `0x180018540`
- `0x1800185f0`
- `0x180018720`
- `0x1800188d0`
- `0x180018950`
- `0x180018bf0`
- `0x180018c70`
- `0x180018cf0`
- `0x180018d90`
- `0x180018e40`
- `0x180019070`
- `0x1800191a0`
- `0x180019260`
- `0x180019310`
- `0x1800193c0`
- `0x180019690`
- `0x180019730`
- `0x1800197d0`
- `0x180019a30`
- `0x180019e70`
- `0x180019fa0`
- `0x18001a010`
- `0x18001a080`
- `0x18001a110`
- `0x18001a2d0`
- `0x18001a4e0`
- `0x18001a580`
- `0x18001a620`

## callees

- `0x180008cf0`
- `0x180015af0`
- `0x18001aa94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aabf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aabf`

## pseudocode

```c
void __fastcall anonymous_namespace_::uwfCfgFinalize(__int64 a1, CUwfStaticConfiguration *a2)
{
  if ( a2 )
    CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(a2);
  if ( a1 )
  {
    CUwfManagement::Finalize((CUwfManagement *)(a1 + 8), (__int64)a2);
    LeaveCriticalSection(&CUwfProvider::s_CritSec);
  }
}

```

## disassembly

```asm
0x18001aa94  push    rbx
0x18001aa96  sub     rsp, 20h
0x18001aa9a  mov     rbx, rcx
0x18001aa9d  test    rdx, rdx
0x18001aaa0  jz      short loc_18001AAAA
0x18001aaa2  mov     rcx, rdx; this
0x18001aaa5  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18001aaaa  test    rbx, rbx
0x18001aaad  jz      short loc_18001AAC5
0x18001aaaf  lea     rcx, [rbx+8]; this
0x18001aab3  call    ?Finalize@CUwfManagement@@QEAAJXZ; CUwfManagement::Finalize(void)
0x18001aab8  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001aabf  call    cs:__imp_LeaveCriticalSection
0x18001aac5  add     rsp, 20h
0x18001aac9  pop     rbx
0x18001aaca  retn
```
