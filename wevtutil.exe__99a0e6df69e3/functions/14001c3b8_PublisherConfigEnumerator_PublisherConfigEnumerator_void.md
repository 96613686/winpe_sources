# PublisherConfigEnumerator::~PublisherConfigEnumerator(void)

- ea: `0x14001c3b8`
- end: `0x14001c3cf`
- name: `??1PublisherConfigEnumerator@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(PublisherConfigEnumerator *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140031fc8`
- `0x140032b56`
- `0x140032dab`
- `0x140033420`
- `0x1400334d0`
- `0x1400337f6`

## callees

- `0x14001c3b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c3c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c3c4`

## pseudocode

```c
void __fastcall PublisherConfigEnumerator::~PublisherConfigEnumerator(HKEY *this)
{
  HKEY v1; // rcx

  v1 = *this;
  if ( v1 )
    RegCloseKey(v1);
}

```

## disassembly

```asm
0x14001c3b8  sub     rsp, 28h
0x14001c3bc  mov     rcx, [rcx]; hKey
0x14001c3bf  test    rcx, rcx
0x14001c3c2  jz      short loc_14001C3CA
0x14001c3c4  call    cs:__imp_RegCloseKey
0x14001c3ca  add     rsp, 28h
0x14001c3ce  retn
```
