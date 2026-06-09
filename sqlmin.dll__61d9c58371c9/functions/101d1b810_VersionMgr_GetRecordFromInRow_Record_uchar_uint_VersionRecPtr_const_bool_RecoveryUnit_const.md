# VersionMgr::GetRecordFromInRow(Record &,uchar *,uint,VersionRecPtr const &,bool,RecoveryUnit const *)

- ea: `0x101d1b810`
- end: `0x101d1d95f`
- name: `?GetRecordFromInRow@VersionMgr@@CAXAEAVRecord@@PEAEIAEBVVersionRecPtr@@_NPEBVRecoveryUnit@@@Z`
- size: `8527`
- prototype: `void __fastcall(struct Record *, unsigned __int8 *, unsigned int, const struct VersionRecPtr *, bool, const struct RecoveryUnit *)`
- caller_count: `3`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x10041a060`
- `0x10049b060`
- `0x1004a1c30`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x1004025c0`
- `0x100415e90`
- `0x10043e110`
- `0x100441e00`
- `0x10049bfd0`
- `0x10049c6c0`
- `0x10190d1b0`
- `0x101d1b810`
- `0x1021d8a90`
- `0x1021dad70`
- `0x1021db830`
- `0x1021e1bc0`
- `0x1021e7bb0`
- `0x1021eab40`
- `0x1021ecfd0`

## import_xrefs

- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d1c237`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d1d58f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1b890`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1b9a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1ba74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1bb45`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1bde1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1bea0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c0c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c15a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c430`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c502`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c5d3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c881`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c946`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cba1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cc0f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cc93`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cdf6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cec6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cf98`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d21d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d2dd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d4ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d574`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d65f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d85f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d90a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d936`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1b890`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1b9a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1ba74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1bb45`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1bde1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1bea0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c0c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c15a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c430`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c502`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c5d3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c881`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1c946`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cba1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cc0f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cc93`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cdf6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cec6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1cf98`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d21d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d2dd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d4ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d574`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d65f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d85f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d90a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1d936`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1b97e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1ba50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1bb21`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1bdbd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1be7c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c215`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c40c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c4de`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c5af`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c85d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c922`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1cdd2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1cea2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1cf74`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1d1f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1d2b9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1b97e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1ba50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1bb21`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1bdbd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1be7c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c215`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c40c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c4de`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c5af`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c85d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1c922`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1cdd2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1cea2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1cf74`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1d1f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1d2b9`
- `sqldk!SystemThread_TlsIndex` at `0x101d1b928`
- `sqldk!SystemThread_TlsIndex` at `0x101d1b9fa`
- `sqldk!SystemThread_TlsIndex` at `0x101d1bacb`
- `sqldk!SystemThread_TlsIndex` at `0x101d1bd67`
- `sqldk!SystemThread_TlsIndex` at `0x101d1be26`
- `sqldk!SystemThread_TlsIndex` at `0x101d1c3b6`
- `sqldk!SystemThread_TlsIndex` at `0x101d1c488`
- `sqldk!SystemThread_TlsIndex` at `0x101d1c559`
- `sqldk!SystemThread_TlsIndex` at `0x101d1c807`
- `sqldk!SystemThread_TlsIndex` at `0x101d1c8cc`
- `sqldk!SystemThread_TlsIndex` at `0x101d1cd7c`
- `sqldk!SystemThread_TlsIndex` at `0x101d1ce4c`
- `sqldk!SystemThread_TlsIndex` at `0x101d1cf1e`
- `sqldk!SystemThread_TlsIndex` at `0x101d1d1a3`
- `sqldk!SystemThread_TlsIndex` at `0x101d1d263`
- `sqldk!SystemThread_TlsOffset` at `0x101d1b931`
- `sqldk!SystemThread_TlsOffset` at `0x101d1ba03`
- `sqldk!SystemThread_TlsOffset` at `0x101d1bad4`
- `sqldk!SystemThread_TlsOffset` at `0x101d1bd70`
- `sqldk!SystemThread_TlsOffset` at `0x101d1be2f`
- `sqldk!SystemThread_TlsOffset` at `0x101d1c3bf`
- `sqldk!SystemThread_TlsOffset` at `0x101d1c491`
- `sqldk!SystemThread_TlsOffset` at `0x101d1c562`
- `sqldk!SystemThread_TlsOffset` at `0x101d1c810`
- `sqldk!SystemThread_TlsOffset` at `0x101d1c8d5`
- `sqldk!SystemThread_TlsOffset` at `0x101d1cd85`
- `sqldk!SystemThread_TlsOffset` at `0x101d1ce55`
- `sqldk!SystemThread_TlsOffset` at `0x101d1cf27`
- `sqldk!SystemThread_TlsOffset` at `0x101d1d1ac`
- `sqldk!SystemThread_TlsOffset` at `0x101d1d26c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101d1c9ee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101d1ca05`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101d1c9ee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101d1ca05`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101d1ca11`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101d1ca11`

## pseudocode

```c

```
