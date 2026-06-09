# CVssDeletingWriter::IsSystemAccountSID(ushort const *)

- ea: `0x140011ae0`
- end: `0x1400137b4`
- name: `?IsSystemAccountSID@CVssDeletingWriter@@IEAA_NPEBG@Z`
- size: `7380`
- prototype: `bool(CVssDeletingWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140015fb0`

## callees

- `0x140006020`
- `0x140011a90`
- `0x140011ae0`
- `0x1400137c0`
- `0x1400138e0`
- `0x140013c60`
- `0x140014ff0`
- `0x140019e30`
- `0x140028b48`
- `0x14003a8f0`
- `0x140070fcc`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001327e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001327e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013409`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013084`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400130af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013084`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400130af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140011fd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140012295`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001255c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140011fd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140012295`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001255c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140012d29`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140012e8b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140012d29`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140012e8b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140011f9f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140011ffd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001226f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400122bf`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001252f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140012586`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140011f9f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140011ffd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001226f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400122bf`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001252f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140012586`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011ba3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011d16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011ee0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001204a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400121b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001230c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012474`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400125d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001273b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012837`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012987`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012b07`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012da9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011ba3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011d16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011ee0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001204a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400121b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001230c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012474`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400125d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001273b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012837`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012987`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012b07`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140012da9`
- `VssTrace!__imp_VssTraceMessage` at `0x1400134c2`
- `VssTrace!__imp_VssTraceMessage` at `0x140013500`
- `VssTrace!__imp_VssTraceMessage` at `0x1400135b3`
- `VssTrace!__imp_VssTraceMessage` at `0x140013666`
- `VssTrace!__imp_VssTraceMessage` at `0x140013719`
- `VssTrace!__imp_VssTraceMessage` at `0x14001375e`
- `VssTrace!__imp_VssTraceMessage` at `0x1400137a8`
- `VssTrace!__imp_VssTraceMessage` at `0x1400134c2`
- `VssTrace!__imp_VssTraceMessage` at `0x140013500`
- `VssTrace!__imp_VssTraceMessage` at `0x1400135b3`
- `VssTrace!__imp_VssTraceMessage` at `0x140013666`
- `VssTrace!__imp_VssTraceMessage` at `0x140013719`
- `VssTrace!__imp_VssTraceMessage` at `0x14001375e`
- `VssTrace!__imp_VssTraceMessage` at `0x1400137a8`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011de1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011e1b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012108`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400123ca`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012691`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400128f2`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012e66`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012ece`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012ef1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f14`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f37`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f5a`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f92`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011de1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011e1b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012108`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400123ca`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012691`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400128f2`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012e66`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012ece`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012ef1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f14`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f37`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f5a`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140012f92`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140011bf5`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140011f1f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400121f1`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400124b3`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001277a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400129c6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140012b50`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140011bf5`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140011f1f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400121f1`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400124b3`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001277a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400129c6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140012b50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011ce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011cf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011e04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400122d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400122e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400122f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001259f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400125ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400125bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400125c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001281f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001282d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011ce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011cf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011e04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400122d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400122e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400122f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001259f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400125ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400125bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400125c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001281f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001282d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012d9b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400127f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400127f1`

## string_xrefs

- `0x140011b07`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x140011b13`: `CVssDeletingWriter::IsSystemAccountSID`
- `0x140011e51`: `base\stor\vss\modules\sec\security.cxx`
- `0x140011fb6`: `base\stor\vss\modules\sec\security.cxx`
- `0x140012123`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400123e5`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400126ac`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400128f8`: `base\stor\vss\modules\sec\security.cxx`
- `0x140012a8c`: `base\stor\vss\modules\sec\security.cxx`
- `0x14001310c`: `base\stor\vss\modules\sec\security.cxx`
- `0x14001320c`: `base\stor\vss\modules\sec\security.cxx`
- `0x140013297`: `base\stor\vss\modules\sec\security.cxx`
- `0x14001331a`: `base\stor\vss\modules\sec\security.cxx`
- `0x14001339e`: `base\stor\vss\modules\sec\security.cxx`
- `0x14001341f`: `base\stor\vss\modules\sec\security.cxx`
- `0x140012903`: `CAutoSid::operator ==`
- `0x140012e73`: `CAutoSid::operator ==`
- `0x14001346c`: `ConvertStringSidToSid(%s)`
- `0x1400126b7`: `CAutoSid::CreateFromString`
- `0x140011e5c`: `CAutoSid::CreateBasicSid`
- `0x14001212e`: `CAutoSid::CreateBasicSid`
- `0x1400123f0`: `CAutoSid::CreateBasicSid`
- `0x140013194`: `CAutoSid::CreateBasicSid`
- `0x140013217`: `CAutoSid::CreateBasicSid`
- `0x1400132a2`: `CAutoSid::CreateBasicSid`
- `0x14001351b`: `CreateWellKnownSidType`
- `0x140013561`: `CreateWellKnownSidType`
- `0x1400135ce`: `CreateWellKnownSidType`
- `0x140013614`: `CreateWellKnownSidType`
- `0x140013681`: `CreateWellKnownSidType`
- `0x1400136c7`: `CreateWellKnownSidType`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
char __fastcall CVssDeletingWriter::IsSystemAccountSID(CVssDeletingWriter *this, const unsigned __int16 *a2)
{
  CVssDeletingWriter *v3; // rax
  unsigned int v4; // r15d
  unsigned int v5; // ebx
  __int64 i; // rbx
  void *v7; // rcx
  __int64 v8; // rax
  DWORD v9; // edi
  const unsigned __int16 **v11; // rax
  int v12; // ebx
  __int64 j; // rbx
  void *v14; // rcx
  signed int LastError; // eax
  signed int v16; // ebx
  HLOCAL v17; // rax
  void *v18; // r13
  DWORD v19; // edi
  unsigned int v20; // r10d
  const unsigned __int16 **v21; // rax
  int v22; // ebx
  __int64 k; // rbx
  void *v24; // rcx
  signed int v25; // eax
  signed int v26; // ebx
  HLOCAL v27; // rax
  HLOCAL v28; // rdi
  DWORD v29; // esi
  unsigned int v30; // r10d
  const unsigned __int16 **v31; // rax
  int v32; // ebx
  __int64 m; // rbx
  void *v34; // rcx
  signed int v35; // eax
  signed int v36; // ebx
  HLOCAL v37; // rax
  HLOCAL v38; // rbx
  DWORD v39; // esi
  unsigned int v40; // r10d
  CVssDeletingWriter *v41; // rax
  int v42; // ebx
  __int64 n; // rbx
  void *v44; // rcx
  DWORD v45; // esi
  unsigned int v46; // r8d
  CVssDeletingWriter *v47; // rax
  int v48; // ebx
  __int64 ii; // rbx
  void *v50; // rcx
  bool v51; // r13
  const wchar_t *v52; // rax
  CVssDeletingWriter *v53; // rax
  __int64 jj; // rbx
  void *v55; // rcx
  HLOCAL v56; // rdi
  bool v57; // bl
  const wchar_t *v58; // rax
  BOOL v59; // eax
  const wchar_t *v60; // rcx
  DWORD v61; // r14d
  unsigned int v62; // r8d
  BOOL v63; // ebx
  const wchar_t *v64; // rcx
  bool v65; // bl
  signed int v66; // eax
  signed int v67; // ebx
  signed int v68; // eax
  signed int v69; // ebx
  signed int v70; // eax
  signed int v71; // edi
  signed int v72; // eax
  CVssDebugInfo *v73; // rax
  CVssDebugInfo *v74; // rax
  CVssDebugInfo *v75; // rax
  CVssDebugInfo *v76; // rax
  CVssDebugInfo *v77; // rax
  CVssDebugInfo *v78; // rax
  __int64 v79; // [rsp+20h] [rbp-E0h]
  __int64 v80; // [rsp+20h] [rbp-E0h]
  __int64 v81; // [rsp+20h] [rbp-E0h]
  __int64 v82; // [rsp+20h] [rbp-E0h]
  __int64 v83; // [rsp+20h] [rbp-E0h]
  __int64 v84; // [rsp+20h] [rbp-E0h]
  __int64 v85; // [rsp+28h] [rbp-D8h]
  __int64 v86; // [rsp+28h] [rbp-D8h]
  __int64 v87; // [rsp+28h] [rbp-D8h]
  __int64 v88; // [rsp+28h] [rbp-D8h]
  __int64 v89; // [rsp+28h] [rbp-D8h]
  __int64 v90; // [rsp+30h] [rbp-D0h]
  __int64 v91; // [rsp+30h] [rbp-D0h]
  __int64 v92; // [rsp+30h] [rbp-D0h]
  __int64 v93; // [rsp+30h] [rbp-D0h]
  __int64 v94; // [rsp+30h] [rbp-D0h]
  __int64 v95; // [rsp+38h] [rbp-C8h]
  __int64 v96; // [rsp+38h] [rbp-C8h]
  __int64 v97; // [rsp+38h] [rbp-C8h]
  __int64 v98; // [rsp+38h] [rbp-C8h]
  __int64 v99; // [rsp+38h] [rbp-C8h]
  __int64 v100; // [rsp+40h] [rbp-C0h]
  __int64 v101; // [rsp+40h] [rbp-C0h]
  __int64 v102; // [rsp+40h] [rbp-C0h]
  __int64 v103; // [rsp+40h] [rbp-C0h]
  __int64 v104; // [rsp+40h] [rbp-C0h]
  __int64 v105; // [rsp+48h] [rbp-B8h]
  __int64 v106; // [rsp+48h] [rbp-B8h]
  __int64 v107; // [rsp+48h] [rbp-B8h]
  __int64 v108; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v109; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v110; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v111; // [rsp+60h] [rbp-A0h]
  __int64 v112; // [rsp+68h] [rbp-98h]
  __int64 v113; // [rsp+70h] [rbp-90h]
  LPVOID v114[2]; // [rsp+78h] [rbp-88h]
  LPVOID v115[6]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v116; // [rsp+B8h] [rbp-48h]
  __int128 v117; // [rsp+C8h] [rbp-38h]
  __int128 v118; // [rsp+D8h] [rbp-28h]
  __int64 v119; // [rsp+E8h] [rbp-18h]
  __int64 v120; // [rsp+F0h] [rbp-10h]
  const unsigned __int16 *v121; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v122; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v123; // [rsp+110h] [rbp+10h]
  __int64 v124; // [rsp+118h] [rbp+18h]
  int v125; // [rsp+120h] [rbp+20h]
  LPVOID v126[2]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v127; // [rsp+138h] [rbp+38h]
  __int128 v128; // [rsp+148h] [rbp+48h]
  __int128 v129; // [rsp+158h] [rbp+58h]
  __int128 v130; // [rsp+168h] [rbp+68h]
  __int128 v131; // [rsp+178h] [rbp+78h]
  __int128 v132; // [rsp+188h] [rbp+88h]
  __int64 v133; // [rsp+198h] [rbp+98h]
  int v134; // [rsp+1A0h] [rbp+A0h]
  void **v135; // [rsp+1A8h] [rbp+A8h] BYREF
  PSID Sid; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int64 v137; // [rsp+1C0h] [rbp+C0h] BYREF
  int v138; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v139; // [rsp+1D0h] [rbp+D0h]
  const unsigned __int16 *v140; // [rsp+1D8h] [rbp+D8h]
  unsigned int v141; // [rsp+1E0h] [rbp+E0h]
  unsigned int v142; // [rsp+1E4h] [rbp+E4h]
  const wchar_t *v143; // [rsp+1E8h] [rbp+E8h]
  unsigned int v144; // [rsp+1F0h] [rbp+F0h]
  DWORD TickCount; // [rsp+1F4h] [rbp+F4h]
  unsigned int v146; // [rsp+1F8h] [rbp+F8h]
  LPVOID pv[2]; // [rsp+200h] [rbp+100h]
  LPVOID v148[2]; // [rsp+210h] [rbp+110h]
  CVssDeletingWriter *v149; // [rsp+220h] [rbp+120h]
  void **v150; // [rsp+230h] [rbp+130h]
  HLOCAL pSid2; // [rsp+238h] [rbp+138h]
  void **v152; // [rsp+240h] [rbp+140h]
  HLOCAL hMem; // [rsp+248h] [rbp+148h]
  void **v154; // [rsp+250h] [rbp+150h]
  HLOCAL v155; // [rsp+258h] [rbp+158h]
  void **v156; // [rsp+260h] [rbp+160h] BYREF
  HLOCAL v157; // [rsp+268h] [rbp+168h]
  void **v158; // [rsp+270h] [rbp+170h] BYREF
  HLOCAL v159; // [rsp+278h] [rbp+178h]
  void **v160; // [rsp+280h] [rbp+180h] BYREF
  void *v161; // [rsp+288h] [rbp+188h]
  _BYTE v162[224]; // [rsp+290h] [rbp+190h] BYREF
  CVssDeletingWriter *cbSid; // [rsp+380h] [rbp+280h] BYREF
  const unsigned __int16 **pExceptionObject; // [rsp+388h] [rbp+288h] BYREF

  cbSid = this;
  v109 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v110 = L"CVssDeletingWriter::IsSystemAccountSID";
  v111 = L"WRTDELET";
  v112 = 0x400000553LL;
  LODWORD(v113) = 255;
  LODWORD(v120) = 0x1000000;
  *(_OWORD *)v114 = 0;
  memset(v115, 0, sizeof(v115));
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v138 = 0;
  v143 = L"CVssDeletingWriter::IsSystemAccountSID";
  v139 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v140 = L"WRTDELET";
  v141 = 1363;
  v142 = 4;
  TickCount = GetTickCount();
  v146 = 255;
  v137 = 0xFFFFFFFF00000000uLL;
  v149 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v148 = 0;
  cbSid = 0;
  if ( (int)VssGetTracingContextPerThread(&cbSid) < 0 || (int)VssSetTracingContextPerThread(&v137) < 0 )
  {
    v3 = v149;
  }
  else
  {
    v3 = cbSid;
    v149 = cbSid;
  }
  if ( v3 )
    v144 = *((_DWORD *)v3 + 12) + 1;
  else
    v144 = 0;
  v4 = 160;
  v5 = 160;
  if ( v146 != 255 )
    v5 = v146;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v137, v142) )
    VssTraceMessage(v139, v140, v141, v144, v142, v143, L"ENTER", v5, 0);
  for ( i = 0; i != 15; ++i )
  {
    v7 = v114[i];
    if ( v7 )
    {
      CoTaskMemFree(v7);
      v114[i] = 0;
    }
  }
  if ( !a2 )
    goto LABEL_17;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( !v8 )
  {
LABEL_17:
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v137,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v148[0]);
    v148[0] = 0;
    CoTaskMemFree(v148[1]);
    v148[1] = 0;
    v9 = GetTickCount() - TickCount;
    if ( v146 != 255 )
      v4 = v146;
    LODWORD(v100) = v9;
    LODWORD(v95) = v9 % 0x3E8;
    LODWORD(v90) = v9 / 0x3E8 % 0x3C;
    LODWORD(v85) = v9 / 0xEA60 % 0x3C;
    LODWORD(v80) = v9 / 0x36EE80 % 0x3C;
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v137,
      L"EXIT",
      v4,
      L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
      v80,
      v85,
      v90,
      v95,
      v100,
      v138,
      v109,
      v110,
      v111,
      v112,
      v113,
      v114[0],
      v114[1],
      v115[0],
      v115[1],
      v115[2],
      v115[3],
      v115[4],
      v115[5],
      v116,
      v117,
      v118,
      v119,
      v120);
    VssSetTracingContextPerThread(v149);
    return 0;
  }
  v161 = 0;
  v160 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v122 = L"CAutoSid::CreateBasicSid";
  v123 = L"SECSECRC";
  v124 = 0xB0000036FLL;
  v125 = 255;
  v134 = 0x1000000;
  *(_OWORD *)v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  LODWORD(v110) = 0;
  v114[0] = L"CAutoSid::CreateBasicSid";
  v111 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v112 = (__int64)L"SECSECRC";
  v113 = 0xB0000036FLL;
  HIDWORD(v114[1]) = GetTickCount();
  LODWORD(v115[0]) = 255;
  v109 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  memset(&v115[1], 0, 40);
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v109) < 0 )
  {
    v11 = (const unsigned __int16 **)v115[5];
  }
  else
  {
    v11 = pExceptionObject;
    v115[5] = pExceptionObject;
  }
  if ( v11 )
    LODWORD(v114[1]) = *((_DWORD *)v11 + 12) + 1;
  else
    LODWORD(v114[1]) = 0;
  v12 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v12 = (int)v115[0];
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v109, HIDWORD(v113)) )
    VssTraceMessage(v111, v112, (unsigned int)v113, LODWORD(v114[1]), HIDWORD(v113), v114[0], L"ENTER", v12, 0);
  for ( j = 0; j != 15; ++j )
  {
    v14 = v126[j];
    if ( v14 )
    {
      CoTaskMemFree(v14);
      v126[j] = 0;
    }
  }
  LODWORD(cbSid) = 0;
  CreateWellKnownSid(WinLocalSystemSid, 0, 0, (DWORD *)&cbSid);
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v110) = v16;
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::CreateBasicSid";
    v123 = L"SECSECRC";
    v124 = 0xB0000037CLL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    pExceptionObject = &v121;
    if ( v16 < 0 )
    {
      v73 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v162, (const struct CVssDebugInfo *)&v121);
      CVssFunctionTracer::TranslateError(&v109, v73, (unsigned int)v16, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v121);
  }
  v154 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v17 = LocalAlloc(0, (unsigned int)cbSid);
  v18 = v17;
  v155 = v17;
  if ( !v17 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, v17, (DWORD *)&cbSid) )
  {
    v66 = GetLastError();
    v67 = v66;
    if ( v66 > 0 )
      v67 = (unsigned __int16)v66 | 0x80070000;
    LODWORD(v110) = v67;
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::CreateBasicSid";
    v123 = L"SECSECRC";
    v124 = 0xB00000385LL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    pExceptionObject = &v121;
    if ( v67 < 0 )
    {
      v74 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v162, (const struct CVssDebugInfo *)&v121);
      CVssFunctionTracer::TranslateError(&v109, v74, (unsigned int)v67, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v121);
  }
  v161 = v18;
  CoTaskMemFree(v115[1]);
  v115[1] = 0;
  CoTaskMemFree(v115[2]);
  v115[2] = 0;
  CoTaskMemFree(v115[3]);
  v115[3] = 0;
  CoTaskMemFree(v115[4]);
  v115[4] = 0;
  v19 = GetTickCount() - HIDWORD(v114[1]);
  v20 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v20 = (unsigned int)v115[0];
  LODWORD(v100) = v19;
  LODWORD(v95) = v19 % 0x3E8;
  LODWORD(v90) = v19 / 0x3E8 % 0x3C;
  LODWORD(v85) = v19 / 0xEA60 % 0x3C;
  LODWORD(v79) = v19 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v109,
    L"EXIT",
    v20,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v79,
    v85,
    v90,
    v95,
    v100,
    (_DWORD)v110);
  VssSetTracingContextPerThread(v115[5]);
  v159 = 0;
  v158 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v122 = L"CAutoSid::CreateBasicSid";
  v123 = L"SECSECRC";
  v124 = 0xB0000036FLL;
  v125 = 255;
  v134 = 0x1000000;
  *(_OWORD *)v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  LODWORD(v110) = 0;
  v114[0] = L"CAutoSid::CreateBasicSid";
  v111 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v112 = (__int64)L"SECSECRC";
  v113 = 0xB0000036FLL;
  HIDWORD(v114[1]) = GetTickCount();
  LODWORD(v115[0]) = 255;
  v109 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  memset(&v115[1], 0, 40);
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v109) < 0 )
  {
    v21 = (const unsigned __int16 **)v115[5];
  }
  else
  {
    v21 = pExceptionObject;
    v115[5] = pExceptionObject;
  }
  if ( v21 )
    LODWORD(v114[1]) = *((_DWORD *)v21 + 12) + 1;
  else
    LODWORD(v114[1]) = 0;
  v22 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v22 = (int)v115[0];
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v109, HIDWORD(v113)) )
    VssTraceMessage(v111, v112, (unsigned int)v113, LODWORD(v114[1]), HIDWORD(v113), v114[0], L"ENTER", v22, 0);
  for ( k = 0; k != 15; ++k )
  {
    v24 = v126[k];
    if ( v24 )
    {
      CoTaskMemFree(v24);
      v126[k] = 0;
    }
  }
  LODWORD(cbSid) = 0;
  CreateWellKnownSid(WinLocalServiceSid, 0, 0, (DWORD *)&cbSid);
  v25 = GetLastError();
  v26 = v25;
  if ( v25 != 122 )
  {
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    LODWORD(v110) = v26;
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::CreateBasicSid";
    v123 = L"SECSECRC";
    v124 = 0xB0000037CLL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    pExceptionObject = &v121;
    if ( v26 < 0 )
    {
      v75 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v162, (const struct CVssDebugInfo *)&v121);
      CVssFunctionTracer::TranslateError(&v109, v75, (unsigned int)v26, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v121);
  }
  v150 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v27 = LocalAlloc(0, (unsigned int)cbSid);
  v28 = v27;
  pSid2 = v27;
  if ( !v27 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !CreateWellKnownSid(WinLocalServiceSid, 0, v27, (DWORD *)&cbSid) )
  {
    v68 = GetLastError();
    v69 = v68;
    if ( v68 > 0 )
      v69 = (unsigned __int16)v68 | 0x80070000;
    LODWORD(v110) = v69;
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::CreateBasicSid";
    v123 = L"SECSECRC";
    v124 = 0xB00000385LL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    pExceptionObject = &v121;
    if ( v69 < 0 )
    {
      v76 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v162, (const struct CVssDebugInfo *)&v121);
      CVssFunctionTracer::TranslateError(&v109, v76, (unsigned int)v69, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v121);
  }
  v159 = v28;
  CoTaskMemFree(v115[1]);
  v115[1] = 0;
  CoTaskMemFree(v115[2]);
  v115[2] = 0;
  CoTaskMemFree(v115[3]);
  v115[3] = 0;
  CoTaskMemFree(v115[4]);
  v115[4] = 0;
  v29 = GetTickCount() - HIDWORD(v114[1]);
  v30 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v30 = (unsigned int)v115[0];
  LODWORD(v105) = (_DWORD)v110;
  LODWORD(v101) = v29;
  LODWORD(v96) = v29 % 0x3E8;
  LODWORD(v91) = v29 / 0x3E8 % 0x3C;
  LODWORD(v86) = v29 / 0xEA60 % 0x3C;
  LODWORD(v81) = v29 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v109,
    L"EXIT",
    v30,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v81,
    v86,
    v91,
    v96,
    v101,
    v105);
  VssSetTracingContextPerThread(v115[5]);
  v157 = 0;
  v156 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v122 = L"CAutoSid::CreateBasicSid";
  v123 = L"SECSECRC";
  v124 = 0xB0000036FLL;
  v125 = 255;
  v134 = 0x1000000;
  *(_OWORD *)v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  LODWORD(v110) = 0;
  v114[0] = L"CAutoSid::CreateBasicSid";
  v111 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v112 = (__int64)L"SECSECRC";
  v113 = 0xB0000036FLL;
  HIDWORD(v114[1]) = GetTickCount();
  LODWORD(v115[0]) = 255;
  v109 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  memset(&v115[1], 0, 40);
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v109) < 0 )
  {
    v31 = (const unsigned __int16 **)v115[5];
  }
  else
  {
    v31 = pExceptionObject;
    v115[5] = pExceptionObject;
  }
  if ( v31 )
    LODWORD(v114[1]) = *((_DWORD *)v31 + 12) + 1;
  else
    LODWORD(v114[1]) = 0;
  v32 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v32 = (int)v115[0];
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v109, HIDWORD(v113)) )
    VssTraceMessage(v111, v112, (unsigned int)v113, LODWORD(v114[1]), HIDWORD(v113), v114[0], L"ENTER", v32, 0);
  for ( m = 0; m != 15; ++m )
  {
    v34 = v126[m];
    if ( v34 )
    {
      CoTaskMemFree(v34);
      v126[m] = 0;
    }
  }
  LODWORD(cbSid) = 0;
  CreateWellKnownSid(WinNetworkServiceSid, 0, 0, (DWORD *)&cbSid);
  v35 = GetLastError();
  v36 = v35;
  if ( v35 != 122 )
  {
    if ( v35 > 0 )
      v36 = (unsigned __int16)v35 | 0x80070000;
    LODWORD(v110) = v36;
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::CreateBasicSid";
    v123 = L"SECSECRC";
    v124 = 0xB0000037CLL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    pExceptionObject = &v121;
    if ( v36 < 0 )
    {
      v77 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v162, (const struct CVssDebugInfo *)&v121);
      CVssFunctionTracer::TranslateError(&v109, v77, (unsigned int)v36, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v121);
  }
  v152 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v37 = LocalAlloc(0, (unsigned int)cbSid);
  v38 = v37;
  hMem = v37;
  if ( !v37 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !CreateWellKnownSid(WinNetworkServiceSid, 0, v37, (DWORD *)&cbSid) )
  {
    v70 = GetLastError();
    v71 = v70;
    if ( v70 > 0 )
      v71 = (unsigned __int16)v70 | 0x80070000;
    LODWORD(v110) = v71;
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::CreateBasicSid";
    v123 = L"SECSECRC";
    v124 = 0xB00000385LL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    pExceptionObject = &v121;
    if ( v71 < 0 )
    {
      v78 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v162, (const struct CVssDebugInfo *)&v121);
      CVssFunctionTracer::TranslateError(&v109, v78, (unsigned int)v71, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v121);
  }
  v157 = v38;
  CoTaskMemFree(v115[1]);
  v115[1] = 0;
  CoTaskMemFree(v115[2]);
  v115[2] = 0;
  CoTaskMemFree(v115[3]);
  v115[3] = 0;
  CoTaskMemFree(v115[4]);
  v115[4] = 0;
  v39 = GetTickCount() - HIDWORD(v114[1]);
  v40 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v40 = (unsigned int)v115[0];
  LODWORD(v106) = (_DWORD)v110;
  LODWORD(v102) = v39;
  LODWORD(v97) = v39 % 0x3E8;
  LODWORD(v92) = v39 / 0x3E8 % 0x3C;
  LODWORD(v87) = v39 / 0xEA60 % 0x3C;
  LODWORD(v82) = v39 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v109,
    L"EXIT",
    v40,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v82,
    v87,
    v92,
    v97,
    v102,
    v106);
  VssSetTracingContextPerThread(v115[5]);
  Sid = 0;
  v135 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v122 = L"CAutoSid::CreateFromString";
  v123 = L"SECSECRC";
  v124 = 0xB00000392LL;
  v125 = 255;
  v134 = 0x1000000;
  *(_OWORD *)v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  LODWORD(v110) = 0;
  v114[0] = L"CAutoSid::CreateFromString";
  v111 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v112 = (__int64)L"SECSECRC";
  v113 = 0xB00000392LL;
  HIDWORD(v114[1]) = GetTickCount();
  LODWORD(v115[0]) = 255;
  v109 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  memset(&v115[1], 0, 40);
  cbSid = 0;
  if ( (int)VssGetTracingContextPerThread(&cbSid) < 0 || (int)VssSetTracingContextPerThread(&v109) < 0 )
  {
    v41 = (CVssDeletingWriter *)v115[5];
  }
  else
  {
    v41 = cbSid;
    v115[5] = cbSid;
  }
  if ( v41 )
    LODWORD(v114[1]) = *((_DWORD *)v41 + 12) + 1;
  else
    LODWORD(v114[1]) = 0;
  v42 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v42 = (int)v115[0];
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v109, HIDWORD(v113)) )
    VssTraceMessage(v111, v112, (unsigned int)v113, LODWORD(v114[1]), HIDWORD(v113), v114[0], L"ENTER", v42, 0);
  for ( n = 0; n != 15; ++n )
  {
    v44 = v126[n];
    if ( v44 )
    {
      CoTaskMemFree(v44);
      v126[n] = 0;
    }
  }
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    v72 = GetLastError();
    if ( v72 > 0 )
      v72 = (unsigned __int16)v72 | 0x80070000;
    LODWORD(v110) = v72;
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::CreateFromString";
    v123 = L"SECSECRC";
    v124 = 0xB00000399LL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(&v109, &v121, L"ConvertStringSidToSid(%s)", a2);
  }
  CoTaskMemFree(v115[1]);
  v115[1] = 0;
  CoTaskMemFree(v115[2]);
  v115[2] = 0;
  CoTaskMemFree(v115[3]);
  v115[3] = 0;
  CoTaskMemFree(v115[4]);
  v115[4] = 0;
  v45 = GetTickCount() - HIDWORD(v114[1]);
  v46 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v46 = (unsigned int)v115[0];
  LODWORD(v107) = (_DWORD)v110;
  LODWORD(v103) = v45;
  LODWORD(v98) = v45 % 0x3E8;
  LODWORD(v93) = v45 / 0x3E8 % 0x3C;
  LODWORD(v88) = v45 / 0xEA60 % 0x3C;
  LODWORD(v83) = v45 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v109,
    L"EXIT",
    v46,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v83,
    v88,
    v93,
    v98,
    v103,
    v107);
  VssSetTracingContextPerThread(v115[5]);
  v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v122 = L"CAutoSid::operator ==";
  v123 = L"SECSECRC";
  v124 = 0xB000003A4LL;
  v125 = 255;
  v134 = 0x1000000;
  *(_OWORD *)v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  LODWORD(v110) = 0;
  v114[0] = L"CAutoSid::operator ==";
  v111 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v112 = (__int64)L"SECSECRC";
  v113 = 0xB000003A4LL;
  HIDWORD(v114[1]) = GetTickCount();
  LODWORD(v115[0]) = 255;
  v109 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  memset(&v115[1], 0, 40);
  cbSid = 0;
  if ( (int)VssGetTracingContextPerThread(&cbSid) < 0 || (int)VssSetTracingContextPerThread(&v109) < 0 )
  {
    v47 = (CVssDeletingWriter *)v115[5];
  }
  else
  {
    v47 = cbSid;
    v115[5] = cbSid;
  }
  if ( v47 )
    LODWORD(v114[1]) = *((_DWORD *)v47 + 12) + 1;
  else
    LODWORD(v114[1]) = 0;
  v48 = 160;
  if ( LODWORD(v115[0]) != 255 )
    v48 = (int)v115[0];
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v109, HIDWORD(v113)) )
    VssTraceMessage(v111, v112, (unsigned int)v113, LODWORD(v114[1]), HIDWORD(v113), v114[0], L"ENTER", v48, 0);
  for ( ii = 0; ii != 15; ++ii )
  {
    v50 = v126[ii];
    if ( v50 )
    {
      CoTaskMemFree(v50);
      v126[ii] = 0;
    }
  }
  if ( Sid )
  {
    if ( v18 )
    {
      v59 = EqualSid(Sid, v18);
      v51 = v59;
      v60 = L"TRUE";
      if ( !v59 )
        v60 = L"FALSE";
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)&v109,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        v60);
      CoTaskMemFree(v115[1]);
      v115[1] = 0;
      CoTaskMemFree(v115[2]);
      v115[2] = 0;
      CoTaskMemFree(v115[3]);
      v115[3] = 0;
      CoTaskMemFree(v115[4]);
      v115[4] = 0;
      v61 = GetTickCount() - HIDWORD(v114[1]);
      v62 = 160;
      if ( LODWORD(v115[0]) != 255 )
        v62 = (unsigned int)v115[0];
      LODWORD(v108) = (_DWORD)v110;
      LODWORD(v104) = v61;
      LODWORD(v99) = v61 % 0x3E8;
      LODWORD(v94) = v61 / 0x3E8 % 0x3C;
      LODWORD(v89) = v61 / 0xEA60 % 0x3C;
      LODWORD(v84) = v61 / 0x36EE80 % 0x3C;
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)&v109,
        L"EXIT",
        v62,
        L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
        v84,
        v89,
        v94,
        v99,
        v104,
        v108);
      VssSetTracingContextPerThread(v115[5]);
      goto LABEL_105;
    }
    v51 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v109, 0);
  }
  else
  {
    v51 = v18 == 0;
    v52 = L"TRUE";
    if ( !v51 )
      v52 = L"FALSE";
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v109,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      v52);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v109);
LABEL_105:
  if ( v51 )
  {
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v137,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    v135 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    if ( Sid )
      LocalFree(Sid);
    Sid = 0;
    v135 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
    if ( hMem )
      LocalFree(hMem);
    v56 = pSid2;
  }
  else
  {
    v121 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v122 = L"CAutoSid::operator ==";
    v123 = L"SECSECRC";
    v124 = 0xB000003A4LL;
    v125 = 255;
    v134 = 0x1000000;
    memset_0(v126, 0, 0x78u);
    LODWORD(v110) = 0;
    v114[0] = (LPVOID)v122;
    v111 = v121;
    v112 = (__int64)v123;
    v113 = v124;
    HIDWORD(v114[1]) = GetTickCount();
    LODWORD(v115[0]) = v125;
    v109 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
    memset(&v115[1], 0, 40);
    cbSid = 0;
    if ( (int)VssGetTracingContextPerThread(&cbSid) < 0 || (int)VssSetTracingContextPerThread(&v109) < 0 )
    {
      v53 = (CVssDeletingWriter *)v115[5];
    }
    else
    {
      v53 = cbSid;
      v115[5] = cbSid;
    }
    if ( v53 )
      LODWORD(v114[1]) = *((_DWORD *)v53 + 12) + 1;
    else
      LODWORD(v114[1]) = 0;
    if ( LODWORD(v115[0]) != 255 )
      v4 = (unsigned int)v115[0];
    if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v109, HIDWORD(v113)) )
      VssTraceMessage(v111, v112, (unsigned int)v113, LODWORD(v114[1]), HIDWORD(v113), v114[0], L"ENTER", v4, 0);
    if ( HIBYTE(v134) )
    {
      for ( jj = 0; jj != 15; ++jj )
      {
        v55 = v126[jj];
        if ( v55 )
        {
          CoTaskMemFree(v55);
          v126[jj] = 0;
        }
      }
    }
    v56 = pSid2;
    if ( Sid )
    {
      if ( pSid2 )
      {
        v63 = EqualSid(Sid, pSid2);
        v64 = L"TRUE";
        if ( !v63 )
          v64 = L"FALSE";
        CVssFunctionTracer::TraceInternalWithFormat(
          (CVssFunctionTracer *)&v109,
          L"RETURN",
          0xAAu,
          L"Returning BOOL: %s",
          v64);
        v57 = v63;
      }
      else
      {
        v57 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v109, 0);
      }
    }
    else
    {
      v57 = pSid2 == 0;
      v58 = L"TRUE";
      if ( pSid2 )
        v58 = L"FALSE";
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)&v109,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        v58);
    }
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v109);
    if ( !v57 && !CAutoSid::operator==((__int64)&v135, (__int64)&v156) )
    {
      v65 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v137, 0);
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v135);
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v156);
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v158);
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v160);
      CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v137);
      return v65;
    }
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v137,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    v135 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    if ( Sid )
      LocalFree(Sid);
    v135 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
    Sid = 0;
    if ( hMem )
      LocalFree(hMem);
  }
  if ( v56 )
    LocalFree(v56);
  if ( v155 )
    LocalFree(v155);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v137);
  return 1;
}

```

## disassembly

```asm
0x140011ae0  mov     [rsp-8+arg_18], rbx
0x140011ae5  mov     [rsp-8+cbSid], rcx
0x140011aea  push    rbp
0x140011aeb  push    rsi
0x140011aec  push    rdi
0x140011aed  push    r12
0x140011aef  push    r13
0x140011af1  push    r14
0x140011af3  push    r15
0x140011af5  lea     rbp, [rsp-240h]
0x140011afd  sub     rsp, 340h
0x140011b04  mov     r14, rdx
0x140011b07  lea     r8, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140011b0e  mov     [rsp+370h+var_320], r8
0x140011b13  lea     rcx, aCvssdeletingwr_5; "CVssDeletingWriter::IsSystemAccountSID"
0x140011b1a  mov     [rsp+370h+var_318], rcx
0x140011b1f  lea     rdx, aWrtdelet; "WRTDELET"
0x140011b26  mov     [rsp+370h+var_310], rdx
0x140011b2b  mov     dword ptr [rsp+370h+var_308], 553h
0x140011b33  mov     dword ptr [rsp+370h+var_308+4], 4
0x140011b3b  mov     [rsp+370h+var_300], 0FFh
0x140011b43  xor     r12d, r12d
0x140011b46  mov     dword ptr [rbp+270h+var_280], 1000000h
0x140011b4d  xorps   xmm0, xmm0
0x140011b50  xor     eax, eax
0x140011b52  movups  xmmword ptr [rsp+370h+var_2F8], xmm0
0x140011b57  movups  xmmword ptr [rbp+270h+var_2E8], xmm0
0x140011b5b  movups  xmmword ptr [rbp+270h+var_2D8], xmm0
0x140011b5f  movups  xmmword ptr [rbp+270h+var_2C8], xmm0
0x140011b63  movups  [rbp+270h+var_2B8], xmm0
0x140011b67  movups  [rbp+270h+var_2A8], xmm0
0x140011b6b  movups  [rbp+270h+var_298], xmm0
0x140011b6f  mov     [rbp+270h+var_288], rax
0x140011b73  mov     [rbp+270h+var_1A8], r12d
0x140011b7a  mov     [rbp+270h+var_188], rcx
0x140011b81  mov     [rbp+270h+var_1A0], r8
0x140011b88  mov     [rbp+270h+var_198], rdx
0x140011b8f  mov     [rbp+270h+var_190], 553h
0x140011b99  mov     [rbp+270h+var_18C], 4
0x140011ba3  call    cs:__imp_GetTickCount
0x140011ba9  mov     [rbp+270h+var_17C], eax
0x140011baf  mov     [rbp+270h+var_1AC], 0FFFFFFFFh
0x140011bb9  mov     [rbp+270h+var_178], 0FFh
0x140011bc3  mov     [rbp+270h+var_1B0], r12d
0x140011bca  mov     [rbp+270h+var_150], r12
0x140011bd1  xorps   xmm0, xmm0
0x140011bd4  movdqa  xmmword ptr [rbp+270h+pv], xmm0
0x140011bdc  xorps   xmm1, xmm1
0x140011bdf  movdqa  xmmword ptr [rbp+270h+var_160], xmm1
0x140011be7  mov     [rbp+270h+cbSid], r12
0x140011bee  lea     rcx, [rbp+270h+cbSid]
0x140011bf5  call    cs:__imp_VssGetTracingContextPerThread
0x140011bfb  test    eax, eax
0x140011bfd  jns     loc_140011E14
0x140011c03  mov     rax, [rbp+270h+var_150]
0x140011c0a  test    rax, rax
0x140011c0d  jz      loc_140013038
0x140011c13  mov     eax, [rax+30h]
0x140011c16  inc     eax
0x140011c18  mov     [rbp+270h+var_180], eax
0x140011c1e  mov     r15d, 0A0h
0x140011c24  mov     ebx, r15d
0x140011c27  cmp     [rbp+270h+var_178], 0FFh
0x140011c31  cmovnz  ebx, [rbp+270h+var_178]
0x140011c38  mov     edx, [rbp+270h+var_18C]; unsigned int
0x140011c3e  lea     rcx, [rbp+270h+var_1B0]; this
0x140011c45  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140011c4a  lea     rsi, aEnter; "ENTER"
0x140011c51  test    eax, eax
0x140011c53  jnz     loc_140013482
0x140011c59  mov     rbx, r12
0x140011c5c  nop     dword ptr [rax+00h]
0x140011c60  mov     rcx, [rsp+rbx*8+370h+var_2F8]; pv
0x140011c65  test    rcx, rcx
0x140011c68  jnz     loc_140011E04
0x140011c6e  inc     rbx
0x140011c71  cmp     rbx, 0Fh
0x140011c75  jnz     short loc_140011C60
0x140011c77  test    r14, r14
0x140011c7a  jz      short loc_140011C97
0x140011c7c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140011c83  inc     rax
0x140011c86  cmp     word ptr [r14+rax*2], 0
0x140011c8c  jnz     short loc_140011C83
0x140011c8e  test    rax, rax
0x140011c91  jnz     loc_140011E3C
0x140011c97  lea     r12, aFalse; "FALSE"
0x140011c9e  mov     [rsp+370h+var_350], r12
0x140011ca3  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140011caa  mov     r8d, 0AAh; unsigned int
0x140011cb0  lea     rdx, aReturn; "RETURN"
0x140011cb7  lea     rcx, [rbp+270h+var_1B0]; this
0x140011cbe  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140011cc3  nop
0x140011cc4  mov     rcx, [rbp+270h+pv]; pv
0x140011ccb  call    cs:__imp_CoTaskMemFree
0x140011cd1  xor     ebx, ebx
0x140011cd3  mov     [rbp+270h+pv], rbx
0x140011cda  mov     rcx, [rbp+270h+pv+8]; pv
0x140011ce1  call    cs:__imp_CoTaskMemFree
0x140011ce7  mov     [rbp+270h+pv+8], rbx
0x140011cee  mov     rcx, [rbp+270h+var_160]; pv
0x140011cf5  call    cs:__imp_CoTaskMemFree
0x140011cfb  mov     [rbp+270h+var_160], rbx
0x140011d02  mov     rcx, [rbp+270h+var_160+8]; pv
0x140011d09  call    cs:__imp_CoTaskMemFree
0x140011d0f  mov     [rbp+270h+var_160+8], rbx
0x140011d16  call    cs:__imp_GetTickCount
0x140011d1c  mov     edi, eax
0x140011d1e  sub     edi, [rbp+270h+var_17C]
0x140011d24  mov     eax, 10624DD3h
0x140011d29  mul     edi
0x140011d2b  mov     ecx, edx
0x140011d2d  shr     ecx, 6
0x140011d30  mov     eax, 88888889h
0x140011d35  mul     ecx
0x140011d37  shr     edx, 5
0x140011d3a  imul    eax, edx, 3Ch ; '<'
0x140011d3d  mov     ebx, ecx
0x140011d3f  sub     ebx, eax
0x140011d41  mov     eax, 45E7B273h
0x140011d46  mul     edi
0x140011d48  mov     r11d, edx
0x140011d4b  shr     r11d, 0Eh
0x140011d4f  mov     eax, 88888889h
0x140011d54  mul     r11d
0x140011d57  shr     edx, 5
0x140011d5a  imul    eax, edx, 3Ch ; '<'
0x140011d5d  sub     r11d, eax
0x140011d60  mov     eax, 95217CB1h
0x140011d65  mul     edi
0x140011d67  mov     r10d, edx
0x140011d6a  shr     r10d, 15h
0x140011d6e  mov     eax, 88888889h
0x140011d73  mul     r10d
0x140011d76  shr     edx, 5
0x140011d79  imul    eax, edx, 3Ch ; '<'
0x140011d7c  sub     r10d, eax
0x140011d7f  mov     r9d, [rbp+270h+var_1A8]
0x140011d86  cmp     [rbp+270h+var_178], 0FFh
0x140011d90  cmovnz  r15d, [rbp+270h+var_178]
0x140011d98  imul    eax, ecx, 3E8h
0x140011d9e  mov     ecx, edi
0x140011da0  sub     ecx, eax
0x140011da2  mov     dword ptr [rsp+370h+var_328], r9d
0x140011da7  mov     dword ptr [rsp+370h+var_330], edi
0x140011dab  mov     dword ptr [rsp+370h+var_338], ecx
0x140011daf  mov     dword ptr [rsp+370h+var_340], ebx
0x140011db3  mov     dword ptr [rsp+370h+var_348], r11d
0x140011db8  mov     dword ptr [rsp+370h+var_350], r10d
0x140011dbd  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140011dc4  mov     r8d, r15d; unsigned int
0x140011dc7  lea     rdx, aExit; "EXIT"
0x140011dce  lea     rcx, [rbp+270h+var_1B0]; this
0x140011dd5  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140011dda  mov     rcx, [rbp+270h+var_150]
0x140011de1  call    cs:__imp_VssSetTracingContextPerThread
0x140011de7  xor     al, al
0x140011de9  mov     rbx, [rsp+370h+arg_18]
0x140011df1  add     rsp, 340h
0x140011df8  pop     r15
0x140011dfa  pop     r14
0x140011dfc  pop     r13
0x140011dfe  pop     r12
0x140011e00  pop     rdi
0x140011e01  pop     rsi
0x140011e02  pop     rbp
0x140011e03  retn
0x140011e04  call    cs:__imp_CoTaskMemFree
0x140011e0a  mov     [rsp+rbx*8+370h+var_2F8], r12
0x140011e0f  jmp     loc_140011C6E
0x140011e14  lea     rcx, [rbp+270h+var_1B0]
0x140011e1b  call    cs:__imp_VssSetTracingContextPerThread
0x140011e21  test    eax, eax
0x140011e23  js      loc_140011C03
0x140011e29  mov     rax, [rbp+270h+cbSid]
0x140011e30  mov     [rbp+270h+var_150], rax
0x140011e37  jmp     loc_140011C0A
0x140011e3c  mov     [rbp+270h+var_E8], r12
0x140011e43  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140011e4a  mov     [rbp+270h+var_F0], rax
0x140011e51  lea     rcx, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140011e58  mov     [rbp+270h+var_270], rcx
0x140011e5c  lea     r13, aCautosidCreate; "CAutoSid::CreateBasicSid"
0x140011e63  mov     [rbp+270h+var_268], r13
0x140011e67  lea     rdx, aSecsecrc; "SECSECRC"
0x140011e6e  mov     [rbp+270h+var_260], rdx
0x140011e72  mov     [rbp+270h+var_258], 36Fh
0x140011e79  mov     [rbp+270h+var_254], 0Bh
0x140011e80  mov     [rbp+270h+var_250], 0FFh
0x140011e87  mov     [rbp+270h+var_1D0], 1000000h
0x140011e91  xorps   xmm0, xmm0
0x140011e94  xor     eax, eax
0x140011e96  movups  xmmword ptr [rbp+270h+var_248], xmm0
0x140011e9a  movups  [rbp+270h+var_238], xmm0
0x140011e9e  movups  [rbp+270h+var_228], xmm0
0x140011ea2  movups  [rbp+270h+var_218], xmm0
0x140011ea6  movups  [rbp+270h+var_208], xmm0
0x140011eaa  movups  [rbp+270h+var_1F8], xmm0
0x140011eae  movups  [rbp+270h+var_1E8], xmm0
0x140011eb5  mov     [rbp+270h+var_1D8], rax
0x140011ebc  mov     dword ptr [rsp+370h+var_318], r12d
0x140011ec1  mov     [rsp+370h+var_2F8], r13
0x140011ec6  mov     [rsp+370h+var_310], rcx
0x140011ecb  mov     [rsp+370h+var_308], rdx
0x140011ed0  mov     [rsp+370h+var_300], 36Fh
0x140011ed8  mov     [rsp+370h+var_2FC], 0Bh
0x140011ee0  call    cs:__imp_GetTickCount
0x140011ee6  mov     dword ptr [rbp+270h+var_2F8+0Ch], eax
0x140011ee9  mov     dword ptr [rsp+370h+var_320+4], 0FFFFFFFFh
0x140011ef1  mov     dword ptr [rbp+270h+var_2E8], 0FFh
0x140011ef8  mov     dword ptr [rsp+370h+var_320], r12d
0x140011efd  mov     [rbp+270h+var_2C8+8], r12
0x140011f01  xorps   xmm0, xmm0
0x140011f04  movdqa  xmmword ptr [rbp+270h+var_2E8+8], xmm0
0x140011f09  xorps   xmm1, xmm1
0x140011f0c  movdqa  xmmword ptr [rbp+270h+var_2D8+8], xmm1
0x140011f11  mov     [rbp+270h+pExceptionObject], r12
0x140011f18  lea     rcx, [rbp+270h+pExceptionObject]
0x140011f1f  call    cs:__imp_VssGetTracingContextPerThread
0x140011f25  test    eax, eax
0x140011f27  jns     loc_140012EC9
0x140011f2d  mov     rax, [rbp+270h+var_2C8+8]
0x140011f31  test    rax, rax
0x140011f34  jz      loc_1400130C2
0x140011f3a  mov     eax, [rax+30h]
0x140011f3d  inc     eax
0x140011f3f  mov     dword ptr [rbp+270h+var_2F8+8], eax
0x140011f42  mov     ebx, r15d
0x140011f45  cmp     dword ptr [rbp+270h+var_2E8], 0FFh
0x140011f4c  cmovnz  ebx, dword ptr [rbp+270h+var_2E8]
0x140011f50  mov     edx, [rsp+370h+var_2FC]; unsigned int
0x140011f54  lea     rcx, [rsp+370h+var_320]; this
0x140011f59  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140011f5e  test    eax, eax
0x140011f60  jnz     loc_1400134CD
0x140011f66  mov     rbx, r12
0x140011f69  nop     dword ptr [rax+00000000h]
0x140011f70  mov     rcx, [rbp+rbx*8+270h+var_248]; pv
0x140011f75  test    rcx, rcx
0x140011f78  jnz     loc_140012CB9
0x140011f7e  inc     rbx
0x140011f81  cmp     rbx, 0Fh
0x140011f85  jnz     short loc_140011F70
0x140011f87  mov     dword ptr [rbp+270h+cbSid], r12d
0x140011f8e  lea     r9, [rbp+270h+cbSid]; cbSid
0x140011f95  xor     r8d, r8d; pSid
0x140011f98  xor     edx, edx; DomainSid
0x140011f9a  mov     ecx, 16h; WellKnownSidType
0x140011f9f  call    cs:__imp_CreateWellKnownSid
0x140011fa5  call    cs:__imp_GetLastError
0x140011fab  mov     ebx, eax
0x140011fad  cmp     eax, 7Ah ; 'z'
0x140011fb0  jnz     loc_1400130FB
0x140011fb6  lea     rdi, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140011fbd  lea     rsi, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140011fc4  mov     [rbp+270h+var_120], rsi
0x140011fcb  mov     edx, dword ptr [rbp+270h+cbSid]; uBytes
0x140011fd1  xor     ecx, ecx; uFlags
0x140011fd3  call    cs:__imp_LocalAlloc
0x140011fd9  mov     r13, rax
0x140011fdc  mov     [rbp+270h+var_118], rax
0x140011fe3  test    rax, rax
0x140011fe6  jz      loc_140013533
0x140011fec  lea     r9, [rbp+270h+cbSid]; cbSid
0x140011ff3  mov     r8, rax; pSid
0x140011ff6  xor     edx, edx; DomainSid
0x140011ff8  mov     ecx, 16h; WellKnownSidType
0x140011ffd  call    cs:__imp_CreateWellKnownSid
0x140012003  test    eax, eax
0x140012005  jz      loc_140013177
0x14001200b  mov     [rbp+270h+var_E8], r13
0x140012012  mov     rcx, [rbp+270h+var_2E8+8]; pv
0x140012016  call    cs:__imp_CoTaskMemFree
0x14001201c  mov     [rbp+270h+var_2E8+8], r12
0x140012020  mov     rcx, [rbp+270h+var_2D8]; pv
0x140012024  call    cs:__imp_CoTaskMemFree
0x14001202a  mov     [rbp+270h+var_2D8], r12
0x14001202e  mov     rcx, [rbp+270h+var_2D8+8]; pv
0x140012032  call    cs:__imp_CoTaskMemFree
0x140012038  mov     [rbp+270h+var_2D8+8], r12
0x14001203c  mov     rcx, [rbp+270h+var_2C8]; pv
0x140012040  call    cs:__imp_CoTaskMemFree
0x140012046  mov     [rbp+270h+var_2C8], r12
0x14001204a  call    cs:__imp_GetTickCount
0x140012050  mov     edi, eax
0x140012052  sub     edi, dword ptr [rbp+270h+var_2F8+0Ch]
0x140012055  mov     eax, 10624DD3h
0x14001205a  mul     edi
0x14001205c  mov     ecx, edx
0x14001205e  shr     ecx, 6
0x140012061  mov     eax, 88888889h
0x140012066  mul     ecx
0x140012068  shr     edx, 5
0x14001206b  imul    eax, edx, 3Ch ; '<'
0x14001206e  mov     ebx, ecx
0x140012070  sub     ebx, eax
0x140012072  mov     eax, 45E7B273h
0x140012077  mul     edi
0x140012079  mov     r11d, edx
  ... truncated ...
```
