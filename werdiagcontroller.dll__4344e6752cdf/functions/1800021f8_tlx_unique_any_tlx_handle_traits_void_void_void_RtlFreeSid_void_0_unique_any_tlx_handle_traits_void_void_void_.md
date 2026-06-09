# tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&RtlFreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&RtlFreeSid(void *),0>>(void)

- ea: `0x1800021f8`
- end: `0x18000220f`
- name: `??1?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: `PVOID __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000654c`

## callees

- `0x1800021f8`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180002204`
- `ntdll!RtlFreeSid` at `0x180002204`

## pseudocode

```c
PVOID __fastcall tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * RtlFreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * RtlFreeSid(void *),0>>(
        void **a1)
{
  void *v1; // rcx
  PVOID result; // rax

  v1 = *a1;
  if ( v1 )
    return RtlFreeSid(v1);
  return result;
}

```

## disassembly

```asm
0x1800021f8  sub     rsp, 28h
0x1800021fc  mov     rcx, [rcx]; Sid
0x1800021ff  test    rcx, rcx
0x180002202  jz      short loc_18000220A
0x180002204  call    cs:__imp_RtlFreeSid
0x18000220a  add     rsp, 28h
0x18000220e  retn
```
