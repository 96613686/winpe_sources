# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x180004c18`
- end: `0x180004c40`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c0d1`
- `0x18001c254`
- `0x18001c7a4`
- `0x18001e7ca`
- `0x18001e7f2`

## callees

- `0x180004c18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004c34`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004c34`

## pseudocode

```c
void __fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(
        __int64 a1)
{
  __int64 v1; // rcx

  v1 = a1 + 8;
  if ( *(_BYTE *)(v1 + 40) )
  {
    *(_BYTE *)(v1 + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)v1);
  }
}

```

## disassembly

```asm
0x180004c18  mov     [rsp+arg_0], rcx
0x180004c1d  sub     rsp, 28h
0x180004c21  add     rcx, 8; lpCriticalSection
0x180004c25  mov     [rsp+28h+arg_8], rcx
0x180004c2a  cmp     byte ptr [rcx+28h], 0
0x180004c2e  jz      short loc_180004C3B
0x180004c30  mov     byte ptr [rcx+28h], 0
0x180004c34  call    cs:__imp_DeleteCriticalSection
0x180004c3a  nop
0x180004c3b  add     rsp, 28h
0x180004c3f  retn
```
