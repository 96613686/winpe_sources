# CGroupMap::CreateInstance(CGroupMap * *)

- ea: `0x1800071f0`
- end: `0x1800072af`
- name: `?CreateInstance@CGroupMap@@SAJPEAPEAV1@@Z`
- size: `191`
- prototype: `__int64 __fastcall(LPVOID **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800089f4`

## callees

- `0x180001348`
- `0x1800071f0`
- `0x180007a24`
- `0x18000e1c8`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180007283`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180007283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007246`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007246`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007258`

## pseudocode

```c
__int64 __fastcall CGroupMap::CreateInstance(LPVOID **a1)
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
      CSxRefMap<CGroupMap,CGroupEntry>::DeleteAll(v2);
      CoTaskMemFree(*TableContext);
      *TableContext = 0;
    }
    v4 = (struct _RTL_AVL_TABLE *)CoTaskMemAlloc(0x68u);
    *TableContext = v4;
    if ( v4 )
    {
      RtlInitializeGenericTableAvl(
        v4,
        (PRTL_AVL_COMPARE_ROUTINE)CSxRefMap<CGroupMap,CGroupEntry>::_CompareRoutine,
        (PRTL_AVL_ALLOCATE_ROUTINE)CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::_AllocateRoutine,
        (PRTL_AVL_FREE_ROUTINE)CSxRefMap<CSppStringMap,CSppStringMapEntry>::_FreeRoutine,
        TableContext);
      result = 0;
      *a1 = TableContext;
      return result;
    }
    CGroupMap::Release((CGroupMap *)TableContext);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800071f0  mov     [rsp+arg_0], rbx
0x1800071f5  push    rdi
0x1800071f6  sub     rsp, 30h
0x1800071fa  mov     rdi, rcx
0x1800071fd  test    rcx, rcx
0x180007200  jz      loc_18000729F
0x180007206  mov     qword ptr [rcx], 0
0x18000720d  mov     ecx, 18h; Size
0x180007212  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007217  mov     rbx, rax
0x18000721a  test    rax, rax
0x18000721d  jz      short loc_180007298
0x18000721f  mov     qword ptr [rax], 0
0x180007226  mov     eax, 1
0x18000722b  mov     [rbx+8], eax
0x18000722e  mov     [rbx+10h], eax
0x180007231  lock add [rbx+8], eax
0x180007235  cmp     qword ptr [rbx], 0
0x180007239  jz      short loc_180007253
0x18000723b  mov     rcx, rbx
0x18000723e  call    ?DeleteAll@?$CSxRefMap@VCGroupMap@@VCGroupEntry@@@@QEAAXXZ; CSxRefMap<CGroupMap,CGroupEntry>::DeleteAll(void)
0x180007243  mov     rcx, [rbx]; pv
0x180007246  call    cs:__imp_CoTaskMemFree
0x18000724c  mov     qword ptr [rbx], 0
0x180007253  mov     ecx, 68h ; 'h'; cb
0x180007258  call    cs:__imp_CoTaskMemAlloc
0x18000725e  mov     [rbx], rax
0x180007261  test    rax, rax
0x180007264  jz      short loc_180007290
0x180007266  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18000726d  mov     [rsp+38h+TableContext], rbx; TableContext
0x180007272  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180007279  mov     rcx, rax; Table
0x18000727c  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCGroupMap@@VCGroupEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180007283  call    cs:__imp_RtlInitializeGenericTableAvl
0x180007289  xor     eax, eax
0x18000728b  mov     [rdi], rbx
0x18000728e  jmp     short loc_1800072A4
0x180007290  mov     rcx, rbx; this
0x180007293  call    ?Release@CGroupMap@@QEAAKXZ; CGroupMap::Release(void)
0x180007298  mov     eax, 8007000Eh
0x18000729d  jmp     short loc_1800072A4
0x18000729f  mov     eax, 80070057h
0x1800072a4  mov     rbx, [rsp+38h+arg_0]
0x1800072a9  add     rsp, 30h
0x1800072ad  pop     rdi
0x1800072ae  retn
```
