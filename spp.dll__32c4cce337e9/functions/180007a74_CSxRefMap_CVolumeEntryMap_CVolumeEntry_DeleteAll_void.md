# CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(void)

- ea: `0x180007a74`
- end: `0x180007abc`
- name: `?DeleteAll@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAXXZ`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800028c0`
- `0x180002ad0`
- `0x180007650`
- `0x180017dfc`
- `0x180018328`
- `0x18001ac40`
- `0x180023874`

## callees

- `0x180007a74`
- `0x18000e308`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180007aa6`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180007aa6`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007a93`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007a93`

## pseudocode

```c
CVolumeEntry **__fastcall CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(__int64 a1)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeEntry *v3; // rbx
  CVolumeEntry **result; // rax

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  for ( i = *(struct _RTL_AVL_TABLE **)a1; ; i = *(struct _RTL_AVL_TABLE **)a1 )
  {
    result = (CVolumeEntry **)RtlEnumerateGenericTableAvl(i, 1u);
    if ( !result )
      break;
    v3 = *result;
    RtlDeleteElementGenericTableAvl(*(PRTL_AVL_TABLE *)a1, result);
    CVolumeEntry::Release(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007a74  mov     [rsp+arg_0], rbx
0x180007a79  push    rdi
0x180007a7a  sub     rsp, 20h
0x180007a7e  mov     rdi, rcx
0x180007a81  lock inc dword ptr [rcx+8]
0x180007a85  mov     rcx, [rcx]
0x180007a88  jmp     short loc_180007AA4
0x180007a8a  mov     rcx, [rdi]; Table
0x180007a8d  mov     rdx, rax; Buffer
0x180007a90  mov     rbx, [rax]
0x180007a93  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180007a99  mov     rcx, rbx; this
0x180007a9c  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180007aa1  mov     rcx, [rdi]; Table
0x180007aa4  mov     dl, 1; Restart
0x180007aa6  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180007aac  test    rax, rax
0x180007aaf  jnz     short loc_180007A8A
0x180007ab1  mov     rbx, [rsp+28h+arg_0]
0x180007ab6  add     rsp, 20h
0x180007aba  pop     rdi
0x180007abb  retn
```
