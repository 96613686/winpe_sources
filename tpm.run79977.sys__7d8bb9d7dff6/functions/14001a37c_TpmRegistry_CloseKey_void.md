# TpmRegistry::CloseKey(void *)

- ea: `0x14001a37c`
- end: `0x14001a397`
- name: `?CloseKey@TpmRegistry@@CAXPEAX@Z`
- size: `27`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400055dc`
- `0x1400059fc`
- `0x14001a2e0`
- `0x14002fe48`

## callees

- `0x14001a37c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001a385`
- `ntoskrnl!ZwClose` at `0x14001a385`

## pseudocode

```c
void __fastcall TpmRegistry::CloseKey(void *a1)
{
  if ( a1 )
    ZwClose(a1);
}

```

## disassembly

```asm
0x14001a37c  sub     rsp, 28h
0x14001a380  test    rcx, rcx
0x14001a383  jz      short loc_14001A391
0x14001a385  call    cs:__imp_ZwClose
0x14001a38c  nop     dword ptr [rax+rax+00h]
0x14001a391  add     rsp, 28h
0x14001a395  retn
```
