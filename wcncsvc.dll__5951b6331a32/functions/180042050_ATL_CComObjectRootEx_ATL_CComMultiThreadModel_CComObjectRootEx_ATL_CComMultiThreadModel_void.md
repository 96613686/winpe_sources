# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x180042050`
- end: `0x18004206d`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800590c1`

## callees

- `0x180042050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042062`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042062`

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
0x180042050  sub     rsp, 28h
0x180042054  add     rcx, 8; lpCriticalSection
0x180042058  cmp     byte ptr [rcx+28h], 0
0x18004205c  jz      short loc_180042068
0x18004205e  mov     byte ptr [rcx+28h], 0
0x180042062  call    cs:__imp_DeleteCriticalSection
0x180042068  add     rsp, 28h
0x18004206c  retn
```
