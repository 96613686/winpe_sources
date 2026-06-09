# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x18000fc4c`
- end: `0x18000fc69`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001556b`

## callees

- `0x18000fc4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fc5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fc5e`

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
0x18000fc4c  sub     rsp, 28h
0x18000fc50  add     rcx, 8; lpCriticalSection
0x18000fc54  cmp     byte ptr [rcx+28h], 0
0x18000fc58  jz      short loc_18000FC64
0x18000fc5a  mov     byte ptr [rcx+28h], 0
0x18000fc5e  call    cs:__imp_DeleteCriticalSection
0x18000fc64  add     rsp, 28h
0x18000fc68  retn
```
