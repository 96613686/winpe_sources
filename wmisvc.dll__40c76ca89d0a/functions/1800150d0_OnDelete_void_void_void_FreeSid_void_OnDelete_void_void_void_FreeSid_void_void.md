# OnDelete<void *,void * (*)(void *),&FreeSid(void *)>::~OnDelete<void *,void * (*)(void *),&FreeSid(void *)>(void)

- ea: `0x1800150d0`
- end: `0x1800150e3`
- name: `??1?$OnDelete@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z@@QEAA@XZ`
- size: `19`
- prototype: `PVOID __fastcall(PSID *)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ea0b`
- `0x18001ea1d`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800150d7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800150d7`

## pseudocode

```c
PVOID __fastcall OnDelete<void *,void * (*)(void *),&void * FreeSid(void *)>::~OnDelete<void *,void * (*)(void *),&void * FreeSid(void *)>(
        PSID *a1)
{
  return FreeSid(*a1);
}

```

## disassembly

```asm
0x1800150d0  sub     rsp, 28h
0x1800150d4  mov     rcx, [rcx]; pSid
0x1800150d7  call    cs:__imp_FreeSid
0x1800150dd  nop
0x1800150de  add     rsp, 28h
0x1800150e2  retn
```
