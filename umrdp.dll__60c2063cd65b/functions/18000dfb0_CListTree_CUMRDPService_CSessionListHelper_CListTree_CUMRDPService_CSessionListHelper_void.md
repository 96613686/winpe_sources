# CListTree<CUMRDPService::CSessionListHelper>::~CListTree<CUMRDPService::CSessionListHelper>(void)

- ea: `0x18000dfb0`
- end: `0x18000dff9`
- name: `??1?$CListTree@VCSessionListHelper@CUMRDPService@@@@QEAA@XZ`
- size: `73`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e000`

## callees

- `0x18000dfb0`
- `0x18000e7c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dfe6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dfe6`
- `ntdll!RtlEnumerateGenericTable` at `0x18000dfc4`
- `ntdll!RtlEnumerateGenericTable` at `0x18000dfc4`

## pseudocode

```c
void __fastcall CListTree<CUMRDPService::CSessionListHelper>::~CListTree<CUMRDPService::CSessionListHelper>(
        PRTL_GENERIC_TABLE Table)
{
  CUmRdpDr **v2; // rax

  if ( HIDWORD(Table[1].CompareRoutine) )
  {
    while ( 1 )
    {
      v2 = (CUmRdpDr **)RtlEnumerateGenericTable(Table, 1u);
      if ( !v2 )
        break;
      CListTree<CUMRDPService::CSessionListHelper>::Remove(Table, v2);
    }
  }
  if ( LODWORD(Table[1].CompareRoutine) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&Table[1]);
    LODWORD(Table[1].CompareRoutine) = 0;
  }
}

```

## disassembly

```asm
0x18000dfb0  push    rbx
0x18000dfb2  sub     rsp, 20h
0x18000dfb6  cmp     dword ptr [rcx+74h], 0
0x18000dfba  mov     rbx, rcx
0x18000dfbd  jz      short loc_18000DFDC
0x18000dfbf  mov     dl, 1; Restart
0x18000dfc1  mov     rcx, rbx; Table
0x18000dfc4  call    cs:__imp_RtlEnumerateGenericTable
0x18000dfca  test    rax, rax
0x18000dfcd  jz      short loc_18000DFDC
0x18000dfcf  mov     rdx, rax; Buffer
0x18000dfd2  mov     rcx, rbx; Table
0x18000dfd5  call    ?Remove@?$CListTree@VCSessionListHelper@CUMRDPService@@@@QEAAHPEAVCSessionListHelper@CUMRDPService@@@Z; CListTree<CUMRDPService::CSessionListHelper>::Remove(CUMRDPService::CSessionListHelper *)
0x18000dfda  jmp     short loc_18000DFBF
0x18000dfdc  cmp     dword ptr [rbx+70h], 0
0x18000dfe0  jz      short loc_18000DFF3
0x18000dfe2  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000dfe6  call    cs:__imp_DeleteCriticalSection
0x18000dfec  mov     dword ptr [rbx+70h], 0
0x18000dff3  add     rsp, 20h
0x18000dff7  pop     rbx
0x18000dff8  retn
```
