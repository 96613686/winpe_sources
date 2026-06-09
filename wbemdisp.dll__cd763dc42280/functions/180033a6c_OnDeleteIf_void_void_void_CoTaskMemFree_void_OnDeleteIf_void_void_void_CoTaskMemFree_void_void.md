# OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)

- ea: `0x180033a6c`
- end: `0x180033a84`
- name: `??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033b34`
- `0x180035ab5`
- `0x180035ac7`
- `0x180035ad9`

## callees

- `0x180033a6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a79`

## pseudocode

```c
void __fastcall OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(
        __int64 a1)
{
  if ( !*(_BYTE *)(a1 + 8) )
    CoTaskMemFree(*(LPVOID *)a1);
}

```

## disassembly

```asm
0x180033a6c  sub     rsp, 28h
0x180033a70  cmp     byte ptr [rcx+8], 0
0x180033a74  jnz     short loc_180033A7F
0x180033a76  mov     rcx, [rcx]; pv
0x180033a79  call    cs:__imp_CoTaskMemFree
0x180033a7f  add     rsp, 28h
0x180033a83  retn
```
