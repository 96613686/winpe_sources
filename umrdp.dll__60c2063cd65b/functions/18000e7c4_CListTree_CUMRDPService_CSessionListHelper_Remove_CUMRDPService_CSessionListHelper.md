# CListTree<CUMRDPService::CSessionListHelper>::Remove(CUMRDPService::CSessionListHelper *)

- ea: `0x18000e7c4`
- end: `0x18000e81c`
- name: `?Remove@?$CListTree@VCSessionListHelper@CUMRDPService@@@@QEAAHPEAVCSessionListHelper@CUMRDPService@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table, PVOID Buffer)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005280`
- `0x18000dfb0`

## callees

- `0x18000e784`
- `0x18000e7c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e7e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e7e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e80b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e80b`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000e7f3`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000e7f3`

## pseudocode

```c
__int64 __fastcall CListTree<CUMRDPService::CSessionListHelper>::Remove(PRTL_GENERIC_TABLE Table, CUmRdpDr **Buffer)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  CUmRdpDr *v6; // rbp
  BOOLEAN v7; // al
  unsigned int v8; // ebx

  if ( !LODWORD(Table[1].CompareRoutine) )
    return 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)&Table[1];
  EnterCriticalSection((LPCRITICAL_SECTION)&Table[1]);
  v6 = *Buffer;
  v7 = RtlDeleteElementGenericTable(Table, Buffer);
  v8 = v7;
  if ( v7 )
    CUmRdpDr::Release(v6);
  LeaveCriticalSection(v5);
  return v8;
}

```

## disassembly

```asm
0x18000e7c4  push    rbx
0x18000e7c6  push    rbp
0x18000e7c7  push    rsi
0x18000e7c8  push    rdi
0x18000e7c9  sub     rsp, 28h
0x18000e7cd  cmp     dword ptr [rcx+70h], 0
0x18000e7d1  mov     rsi, rdx
0x18000e7d4  mov     rbx, rcx
0x18000e7d7  jnz     short loc_18000E7DD
0x18000e7d9  xor     eax, eax
0x18000e7db  jmp     short loc_18000E813
0x18000e7dd  lea     rdi, [rcx+48h]
0x18000e7e1  mov     rcx, rdi; lpCriticalSection
0x18000e7e4  call    cs:__imp_EnterCriticalSection
0x18000e7ea  mov     rbp, [rsi]
0x18000e7ed  mov     rdx, rsi; Buffer
0x18000e7f0  mov     rcx, rbx; Table
0x18000e7f3  call    cs:__imp_RtlDeleteElementGenericTable
0x18000e7f9  movzx   ebx, al
0x18000e7fc  test    al, al
0x18000e7fe  jz      short loc_18000E808
0x18000e800  mov     rcx, rbp; this
0x18000e803  call    ?Release@CUmRdpDr@@QEAAJXZ; CUmRdpDr::Release(void)
0x18000e808  mov     rcx, rdi; lpCriticalSection
0x18000e80b  call    cs:__imp_LeaveCriticalSection
0x18000e811  mov     eax, ebx
0x18000e813  add     rsp, 28h
0x18000e817  pop     rdi
0x18000e818  pop     rsi
0x18000e819  pop     rbp
0x18000e81a  pop     rbx
0x18000e81b  retn
```
