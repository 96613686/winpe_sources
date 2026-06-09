# CWin32ServiceRecord::SendControl(ushort *,ulong,ulong,_CONTROL_ARGS *,ulong,ulong *,int,int,ulong,ushort const *,ulong * *,ulong *,int)

- ea: `0x14000d900`
- end: `0x14000dc15`
- name: `?SendControl@CWin32ServiceRecord@@UEAAKPEAGKKPEAT_CONTROL_ARGS@@KPEAKHHKPEBGPEAPEAK2H@Z`
- size: `789`
- prototype: `unsigned int __usercall@<eax>(CWin32ServiceRecord *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, union _CONTROL_ARGS *, unsigned int, unsigned int *, int, int, unsigned int, const unsigned __int16 *, unsigned int **, unsigned int *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x140002890`
- `0x140003e54`
- `0x14000cf60`
- `0x14000d900`
- `0x14001e710`
- `0x14001e800`
- `0x1400575b0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000d995`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000d995`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000da29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000dab2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000da29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000dab2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000da87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000db76`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000da87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000db76`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000da76`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000db60`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000da76`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000db60`
- `ntdll!RtlReleaseResource` at `0x14000da36`
- `ntdll!RtlReleaseResource` at `0x14000dabf`
- `ntdll!RtlReleaseResource` at `0x14000dbde`
- `ntdll!RtlReleaseResource` at `0x14000da36`
- `ntdll!RtlReleaseResource` at `0x14000dabf`
- `ntdll!RtlReleaseResource` at `0x14000dbde`
- `ntdll!RtlAcquireResourceShared` at `0x14000d985`
- `ntdll!RtlAcquireResourceShared` at `0x14000d985`

## pseudocode

```c

```
