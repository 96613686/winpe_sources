# ReclaimClonedVidPnTarget(_DXGDMM_INTERFACE const *,void * const,D3DKMDT_HVIDPNTOPOLOGY__ * const,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const *,uchar,uint * const,uint * const)

- ea: `0x1401a4b5c`
- end: `0x1401a525b`
- name: `?ReclaimClonedVidPnTarget@@YAJPEBU_DXGDMM_INTERFACE@@QEAXQEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@EQEAI4@Z`
- size: `1791`
- prototype: `__int64 __fastcall(const struct _DXGDMM_INTERFACE *, void *const, struct D3DKMDT_HVIDPNTOPOLOGY__ *const, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *, char, unsigned int *const, unsigned int *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14022bb00`

## callees

- `0x14001b9c0`
- `0x140047b60`
- `0x1400a0cb0`
- `0x1401a4b5c`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401a511a`
- `watchdog!WdLogSingleEntry4` at `0x1401a511a`
- `watchdog!WdLogSingleEntry2` at `0x1401a4da4`
- `watchdog!WdLogSingleEntry2` at `0x1401a4e31`
- `watchdog!WdLogSingleEntry2` at `0x1401a4da4`
- `watchdog!WdLogSingleEntry2` at `0x1401a4e31`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401a51ea`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401a51ea`
- `watchdog!WdLogSingleEntry3` at `0x1401a4fe6`
- `watchdog!WdLogSingleEntry3` at `0x1401a5068`
- `watchdog!WdLogSingleEntry3` at `0x1401a517b`
- `watchdog!WdLogSingleEntry3` at `0x1401a4fe6`
- `watchdog!WdLogSingleEntry3` at `0x1401a5068`
- `watchdog!WdLogSingleEntry3` at `0x1401a517b`
- `watchdog!WdLogSingleEntry0` at `0x1401a4b96`
- `watchdog!WdLogSingleEntry0` at `0x1401a4be4`
- `watchdog!WdLogSingleEntry0` at `0x1401a4c32`
- `watchdog!WdLogSingleEntry0` at `0x1401a4c80`
- `watchdog!WdLogSingleEntry0` at `0x1401a4cd4`
- `watchdog!WdLogSingleEntry0` at `0x1401a4d26`
- `watchdog!WdLogSingleEntry0` at `0x1401a4e8e`
- `watchdog!WdLogSingleEntry0` at `0x1401a4f34`
- `watchdog!WdLogSingleEntry0` at `0x1401a509c`
- `watchdog!WdLogSingleEntry0` at `0x1401a4b96`
- `watchdog!WdLogSingleEntry0` at `0x1401a4be4`
- `watchdog!WdLogSingleEntry0` at `0x1401a4c32`
- `watchdog!WdLogSingleEntry0` at `0x1401a4c80`
- `watchdog!WdLogSingleEntry0` at `0x1401a4cd4`
- `watchdog!WdLogSingleEntry0` at `0x1401a4d26`
- `watchdog!WdLogSingleEntry0` at `0x1401a4e8e`
- `watchdog!WdLogSingleEntry0` at `0x1401a4f34`
- `watchdog!WdLogSingleEntry0` at `0x1401a509c`

## string_xrefs

- `0x1401a5187`: `Failed to get the number of paths in topology 0x%I64x originating from source 0x%I64x (status = 0x%I64x)`
- `0x1401a5074`: `Failed to get target of the second path in topology 0x%I64x originating from source 0x%I64x (status = 0x%I64x)`
- `0x1401a5129`: `Failed to remove path (0x%I64x, 0x%I64x) from topology 0x%I64x which is the second path originating from that source (status = 0x%I64x)`
- `0x1401a4d37`: `o_pReclaimedPathSourceId != NULL`
- `0x1401a4f45`: `sztNumPathsFromSource == 0`

## pseudocode

```c

```
