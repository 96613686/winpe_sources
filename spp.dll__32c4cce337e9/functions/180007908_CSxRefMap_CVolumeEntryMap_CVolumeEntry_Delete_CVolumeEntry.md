# CSxRefMap<CVolumeEntryMap,CVolumeEntry>::Delete(CVolumeEntry *)

- ea: `0x180007908`
- end: `0x180007976`
- name: `?Delete@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAJPEAVCVolumeEntry@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180019bb4`
- `0x18001ac40`
- `0x18001f060`

## callees

- `0x180007908`
- `0x18000e308`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x180007933`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180007933`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007950`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007950`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CVolumeEntryMap,CVolumeEntry>::Delete(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  CVolumeEntry **v4; // rax
  CVolumeEntry *v5; // rsi
  __int64 Buffer; // [rsp+38h] [rbp+10h] BYREF

  Buffer = a2;
  if ( a2 )
  {
    v4 = (CVolumeEntry **)RtlLookupElementGenericTableAvl(*(PRTL_AVL_TABLE *)a1, &Buffer);
    v3 = 1;
    if ( v4 )
    {
      _InterlockedAdd((volatile signed __int32 *)(a1 + 8), 1u);
      v5 = *v4;
      if ( RtlDeleteElementGenericTableAvl(*(PRTL_AVL_TABLE *)a1, v4) == 1 )
      {
        v3 = 0;
        CVolumeEntry::Release(v5);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180007908  mov     [rsp+arg_0], rbx
0x18000790d  mov     [rsp+arg_10], rsi
0x180007912  mov     [rsp+Buffer], rdx
0x180007917  push    rdi
0x180007918  sub     rsp, 20h
0x18000791c  mov     rdi, rcx
0x18000791f  test    rdx, rdx
0x180007922  jnz     short loc_18000792B
0x180007924  mov     ebx, 80070057h
0x180007929  jmp     short loc_180007964
0x18000792b  mov     rcx, [rcx]; Table
0x18000792e  lea     rdx, [rsp+28h+Buffer]; Buffer
0x180007933  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180007939  mov     ebx, 1
0x18000793e  test    rax, rax
0x180007941  jz      short loc_180007964
0x180007943  lock add [rdi+8], ebx
0x180007947  mov     rcx, [rdi]; Table
0x18000794a  mov     rdx, rax; Buffer
0x18000794d  mov     rsi, [rax]
0x180007950  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180007956  cmp     al, bl
0x180007958  jnz     short loc_180007964
0x18000795a  xor     ebx, ebx
0x18000795c  mov     rcx, rsi; this
0x18000795f  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180007964  mov     rsi, [rsp+28h+arg_10]
0x180007969  mov     eax, ebx
0x18000796b  mov     rbx, [rsp+28h+arg_0]
0x180007970  add     rsp, 20h
0x180007974  pop     rdi
0x180007975  retn
```
