# CRegistryKey::~CRegistryKey(void)

- ea: `0x18000bd24`
- end: `0x18000bd6f`
- name: `??1CRegistryKey@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005e94`
- `0x180006430`
- `0x1800064b0`
- `0x1800066a8`
- `0x180007264`
- `0x180007754`
- `0x1800078e0`
- `0x180008b6c`
- `0x180008bf0`
- `0x180008f48`
- `0x1800090d4`
- `0x180009424`
- `0x180009748`
- `0x180010254`
- `0x180010278`
- `0x1800102d2`
- `0x1800102e4`
- `0x18001031e`
- `0x18001046a`

## callees

- `0x180004060`
- `0x18000bd24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd30`

## pseudocode

```c
void __fastcall CRegistryKey::~CRegistryKey(HKEY *this)
{
  char *v2; // rcx

  RegCloseKey(*this);
  v2 = (char *)this[1];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, 2 * (((char *)this[3] - v2) >> 1));
    this[1] = 0;
    this[2] = 0;
    this[3] = 0;
  }
}

```

## disassembly

```asm
0x18000bd24  push    rbx
0x18000bd26  sub     rsp, 20h
0x18000bd2a  mov     rbx, rcx
0x18000bd2d  mov     rcx, [rcx]; hKey
0x18000bd30  call    cs:__imp_RegCloseKey
0x18000bd36  mov     rcx, [rbx+8]
0x18000bd3a  test    rcx, rcx
0x18000bd3d  jz      short loc_18000BD69
0x18000bd3f  mov     rdx, [rbx+18h]
0x18000bd43  sub     rdx, rcx
0x18000bd46  sar     rdx, 1
0x18000bd49  add     rdx, rdx
0x18000bd4c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bd51  mov     qword ptr [rbx+8], 0
0x18000bd59  mov     qword ptr [rbx+10h], 0
0x18000bd61  mov     qword ptr [rbx+18h], 0
0x18000bd69  add     rsp, 20h
0x18000bd6d  pop     rbx
0x18000bd6e  retn
```
