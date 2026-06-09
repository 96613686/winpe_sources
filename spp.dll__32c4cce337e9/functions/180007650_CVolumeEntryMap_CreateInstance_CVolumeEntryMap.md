# CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)

- ea: `0x180007650`
- end: `0x18000770f`
- name: `?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z`
- size: `191`
- prototype: `__int64 __fastcall(LPVOID **)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006730`
- `0x1800092e0`
- `0x18000a920`
- `0x18000b8c0`
- `0x18000c070`
- `0x180010800`
- `0x180013c7c`
- `0x180014ef0`
- `0x180016258`
- `0x180023fc4`

## callees

- `0x180001348`
- `0x180007650`
- `0x180007a74`
- `0x18000e48c`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800076e3`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800076e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800076b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800076b8`

## pseudocode

```c
__int64 __fastcall CVolumeEntryMap::CreateInstance(LPVOID **a1)
{
  void *v2; // rax
  LPVOID *TableContext; // rbx
  struct _RTL_AVL_TABLE *v4; // rax
  __int64 result; // rax

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  v2 = operator new(0x18u);
  TableContext = (LPVOID *)v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = 0;
    *((_DWORD *)v2 + 2) = 1;
    *((_DWORD *)v2 + 4) = 1;
    _InterlockedAdd((volatile signed __int32 *)v2 + 2, 1u);
    if ( *(_QWORD *)v2 )
    {
      CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(v2);
      CoTaskMemFree(*TableContext);
      *TableContext = 0;
    }
    v4 = (struct _RTL_AVL_TABLE *)CoTaskMemAlloc(0x68u);
    *TableContext = v4;
    if ( v4 )
    {
      RtlInitializeGenericTableAvl(
        v4,
        (PRTL_AVL_COMPARE_ROUTINE)CSxRefMap<CSxStringMap,CSxStringEntry>::_CompareRoutine,
        (PRTL_AVL_ALLOCATE_ROUTINE)CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::_AllocateRoutine,
        (PRTL_AVL_FREE_ROUTINE)CSxRefMap<CSppStringMap,CSppStringMapEntry>::_FreeRoutine,
        TableContext);
      result = 0;
      *a1 = TableContext;
      return result;
    }
    CVolumeEntryMap::Release((CVolumeEntryMap *)TableContext);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180007650  mov     [rsp+arg_0], rbx
0x180007655  push    rdi
0x180007656  sub     rsp, 30h
0x18000765a  mov     rdi, rcx
0x18000765d  test    rcx, rcx
0x180007660  jz      loc_1800076FF
0x180007666  mov     qword ptr [rcx], 0
0x18000766d  mov     ecx, 18h; Size
0x180007672  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007677  mov     rbx, rax
0x18000767a  test    rax, rax
0x18000767d  jz      short loc_1800076F8
0x18000767f  mov     qword ptr [rax], 0
0x180007686  mov     eax, 1
0x18000768b  mov     [rbx+8], eax
0x18000768e  mov     [rbx+10h], eax
0x180007691  lock add [rbx+8], eax
0x180007695  cmp     qword ptr [rbx], 0
0x180007699  jz      short loc_1800076B3
0x18000769b  mov     rcx, rbx
0x18000769e  call    ?DeleteAll@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAXXZ; CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(void)
0x1800076a3  mov     rcx, [rbx]; pv
0x1800076a6  call    cs:__imp_CoTaskMemFree
0x1800076ac  mov     qword ptr [rbx], 0
0x1800076b3  mov     ecx, 68h ; 'h'; cb
0x1800076b8  call    cs:__imp_CoTaskMemAlloc
0x1800076be  mov     [rbx], rax
0x1800076c1  test    rax, rax
0x1800076c4  jz      short loc_1800076F0
0x1800076c6  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800076cd  mov     [rsp+38h+TableContext], rbx; TableContext
0x1800076d2  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800076d9  mov     rcx, rax; Table
0x1800076dc  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800076e3  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800076e9  xor     eax, eax
0x1800076eb  mov     [rdi], rbx
0x1800076ee  jmp     short loc_180007704
0x1800076f0  mov     rcx, rbx; this
0x1800076f3  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x1800076f8  mov     eax, 8007000Eh
0x1800076fd  jmp     short loc_180007704
0x1800076ff  mov     eax, 80070057h
0x180007704  mov     rbx, [rsp+38h+arg_0]
0x180007709  add     rsp, 30h
0x18000770d  pop     rdi
0x18000770e  retn
```
