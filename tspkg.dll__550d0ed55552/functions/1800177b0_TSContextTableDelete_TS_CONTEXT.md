# TSContextTableDelete(_TS_CONTEXT *)

- ea: `0x1800177b0`
- end: `0x1800177fa`
- name: `?TSContextTableDelete@@YAXPEAU_TS_CONTEXT@@@Z`
- size: `74`
- prototype: `void __fastcall(struct _TS_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003d30`

## callees

- `0x180003e00`
- `0x1800177b0`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800177d4`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800177d4`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800177c2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800177c2`
- `ntdll!RtlReleaseResource` at `0x1800177ef`
- `ntdll!RtlReleaseResource` at `0x1800177ef`

## pseudocode

```c
void __fastcall TSContextTableDelete(struct _TS_CONTEXT *a1)
{
  struct _TS_CONTEXT *Buffer; // [rsp+30h] [rbp+8h] BYREF

  Buffer = a1;
  RtlAcquireResourceExclusive(&Resource, 1u);
  if ( RtlDeleteElementGenericTableAvl(&Table, &Buffer) )
    TSDereferenceContext(Buffer);
  RtlReleaseResource(&Resource);
}

```

## disassembly

```asm
0x1800177b0  sub     rsp, 28h
0x1800177b4  mov     [rsp+28h+Buffer], rcx
0x1800177b9  mov     dl, 1; Wait
0x1800177bb  lea     rcx, Resource; Resource
0x1800177c2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800177c8  lea     rdx, [rsp+28h+Buffer]; Buffer
0x1800177cd  lea     rcx, Table; Table
0x1800177d4  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800177da  test    al, al
0x1800177dc  jz      short loc_1800177E8
0x1800177de  mov     rcx, [rsp+28h+Buffer]; struct _TS_CONTEXT *
0x1800177e3  call    ?TSDereferenceContext@@YAXPEAU_TS_CONTEXT@@@Z; TSDereferenceContext(_TS_CONTEXT *)
0x1800177e8  lea     rcx, Resource; Resource
0x1800177ef  call    cs:__imp_RtlReleaseResource
0x1800177f5  add     rsp, 28h
0x1800177f9  retn
```
