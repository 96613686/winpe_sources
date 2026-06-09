# CWerService::OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)

- ea: `0x18001672c`
- end: `0x18001679b`
- name: `?OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z`
- size: `111`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, __int64, int)`
- caller_count: `10`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180019178`
- `0x18001924c`
- `0x180019578`
- `0x18001965c`
- `0x180019b34`
- `0x180019c08`
- `0x180019fc8`
- `0x18001a324`
- `0x18001a410`
- `0x18001a4cc`

## callees

- `0x18001caf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016746`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016746`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001678a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001678a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::OpenSenderProcessThread(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        unsigned int a3,
        void **a4,
        int a5,
        void **a6,
        int a7)
{
  EnterCriticalSection(lpCriticalSection);
  LODWORD(a4) = CWerService::_OpenSenderProcessThread((__int64)lpCriticalSection, a2, a3, a4, a5, a6, a7);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x18001672c  push    rbx
0x18001672e  push    rbp
0x18001672f  push    rsi
0x180016730  push    rdi
0x180016731  sub     rsp, 58h
0x180016735  mov     rbx, r9
0x180016738  mov     edi, r8d
0x18001673b  mov     rsi, rdx
0x18001673e  mov     rbp, rcx
0x180016741  mov     [rsp+78h+var_38], rcx
0x180016746  call    cs:__imp_EnterCriticalSection
0x18001674c  mov     [rsp+78h+var_30], 1
0x180016751  mov     eax, [rsp+78h+arg_30]
0x180016758  mov     [rsp+78h+var_48], eax
0x18001675c  mov     rax, [rsp+78h+arg_28]
0x180016764  mov     [rsp+78h+var_50], rax
0x180016769  mov     eax, [rsp+78h+arg_20]
0x180016770  mov     [rsp+78h+var_58], eax
0x180016774  mov     r9, rbx
0x180016777  mov     r8d, edi
0x18001677a  mov     rdx, rsi
0x18001677d  mov     rcx, rbp
0x180016780  call    ?_OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::_OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x180016785  mov     ebx, eax
0x180016787  mov     rcx, rbp; lpCriticalSection
0x18001678a  call    cs:__imp_LeaveCriticalSection
0x180016790  mov     eax, ebx
0x180016792  add     rsp, 58h
0x180016796  pop     rdi
0x180016797  pop     rsi
0x180016798  pop     rbp
0x180016799  pop     rbx
0x18001679a  retn
```
