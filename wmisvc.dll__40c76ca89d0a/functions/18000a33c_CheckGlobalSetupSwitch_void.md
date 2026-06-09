# CheckGlobalSetupSwitch(void)

- ea: `0x18000a33c`
- end: `0x18000a39f`
- name: `?CheckGlobalSetupSwitch@@YAHXZ`
- size: `99`
- prototype: `_BOOL8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b760`
- `0x18000ba0c`

## callees

- `0x18000a33c`

## import_xrefs

- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18000a35e`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18000a35e`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18000a38c`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18000a38c`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a376`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a376`

## pseudocode

```c
_BOOL8 CheckGlobalSetupSwitch(void)
{
  BOOL v0; // ebx
  _BYTE v2[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v3; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  v3 = 0;
  Registry::Registry((Registry *)v2, L"system\\Setup", 1u);
  if ( !Registry::GetDWORD((Registry *)v2, L"SystemSetupInProgress", &v3) )
    v0 = v3 == 1;
  Registry::~Registry((Registry *)v2);
  return v0;
}

```

## disassembly

```asm
0x18000a33c  mov     [rsp+arg_8], rbx
0x18000a341  push    rdi
0x18000a342  sub     rsp, 40h
0x18000a346  xor     ebx, ebx
0x18000a348  mov     [rsp+48h+arg_0], ebx
0x18000a34c  lea     edi, [rbx+1]
0x18000a34f  mov     r8d, edi
0x18000a352  lea     rdx, aSystemSetup; "system\\Setup"
0x18000a359  lea     rcx, [rsp+48h+var_28]
0x18000a35e  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x18000a364  nop
0x18000a365  lea     r8, [rsp+48h+arg_0]
0x18000a36a  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18000a371  lea     rcx, [rsp+48h+var_28]
0x18000a376  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18000a37c  test    eax, eax
0x18000a37e  jnz     short loc_18000A387
0x18000a380  cmp     [rsp+48h+arg_0], edi
0x18000a384  cmovz   ebx, edi
0x18000a387  lea     rcx, [rsp+48h+var_28]
0x18000a38c  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18000a392  mov     eax, ebx
0x18000a394  mov     rbx, [rsp+48h+arg_8]
0x18000a399  add     rsp, 40h
0x18000a39d  pop     rdi
0x18000a39e  retn
```
