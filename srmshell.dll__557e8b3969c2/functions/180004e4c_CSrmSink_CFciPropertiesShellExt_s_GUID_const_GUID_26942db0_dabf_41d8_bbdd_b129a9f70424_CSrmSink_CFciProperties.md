# CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::~CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>(void)

- ea: `0x180004e4c`
- end: `0x180004e7d`
- name: `??1?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001c242`
- `0x18001c792`

## callees

- `0x180004e4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004e71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004e71`

## pseudocode

```c
void __fastcall CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::~CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>(
        __int64 a1)
{
  __int64 v1; // rcx

  v1 = a1 + 16;
  if ( *(_BYTE *)(v1 + 40) )
  {
    *(_BYTE *)(v1 + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)v1);
  }
}

```

## disassembly

```asm
0x180004e4c  mov     [rsp+arg_0], rcx
0x180004e51  sub     rsp, 28h
0x180004e55  lea     rax, [rcx+8]
0x180004e59  mov     [rsp+28h+arg_8], rax
0x180004e5e  lea     rcx, [rax+8]; lpCriticalSection
0x180004e62  mov     [rsp+28h+arg_10], rcx
0x180004e67  cmp     byte ptr [rcx+28h], 0
0x180004e6b  jz      short loc_180004E78
0x180004e6d  mov     byte ptr [rcx+28h], 0
0x180004e71  call    cs:__imp_DeleteCriticalSection
0x180004e77  nop
0x180004e78  add     rsp, 28h
0x180004e7c  retn
```
