# LocationDataSource::CacheManager::~CacheManager(void)

- ea: `0x180010afc`
- end: `0x180010b4c`
- name: `??1CacheManager@LocationDataSource@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(LocationDataSource::CacheManager *this, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180011100`
- `0x180011b60`
- `0x18001bfc8`

## callees

- `0x18000cfec`
- `0x180010afc`
- `0x180011b0c`
- `0x180011e2c`

## pseudocode

```c
void __fastcall LocationDataSource::CacheManager::~CacheManager(
        LocationDataSource::CacheManager *this,
        __int64 a2,
        __int64 a3)
{
  _BYTE v4[48]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v5[104]; // [rsp+50h] [rbp-68h] BYREF
  char v6; // [rsp+C0h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 8) )
  {
    Cache::Lock(*(_QWORD *)this, v4, a3);
    v6 = 1;
    Cache::ValueProxy<bool>::SetValue(v5, &v6);
    *((_BYTE *)this + 8) = 1;
    Cache::Proxy::~Proxy((Cache::Proxy *)v4);
  }
}

```

## disassembly

```asm
0x180010afc  push    rbx
0x180010afe  sub     rsp, 0B0h
0x180010b05  cmp     byte ptr [rcx+8], 0
0x180010b09  mov     rbx, rcx
0x180010b0c  jnz     short loc_180010B43
0x180010b0e  mov     rcx, [rcx]
0x180010b11  lea     rdx, [rsp+0B8h+var_98]
0x180010b16  call    ?Lock@Cache@@QEAA?AVProxy@1@XZ; Cache::Lock(void)
0x180010b1b  lea     rdx, [rsp+0B8h+arg_0]
0x180010b23  mov     [rsp+0B8h+arg_0], 1
0x180010b2b  lea     rcx, [rsp+0B8h+var_68]
0x180010b30  call    ?SetValue@?$ValueProxy@_N@Cache@@QEAAXAEB_N@Z; Cache::ValueProxy<bool>::SetValue(bool const &)
0x180010b35  lea     rcx, [rsp+0B8h+var_98]; this
0x180010b3a  mov     byte ptr [rbx+8], 1
0x180010b3e  call    ??1Proxy@Cache@@QEAA@XZ; Cache::Proxy::~Proxy(void)
0x180010b43  add     rsp, 0B0h
0x180010b4a  pop     rbx
0x180010b4b  retn
```
