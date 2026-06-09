# AslLogDelete

- ea: `0x14000bff8`
- end: `0x14000c0a5`
- name: `AslLogDelete`
- size: `173`
- prototype: `BOOLEAN __fastcall(char *P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400031e8`
- `0x14000b574`
- `0x14002ec10`

## callees

- `0x1400016aa`
- `0x14000bff8`
- `0x14002e3e2`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x14000c05c`
- `ntdll!RtlDeleteCriticalSection` at `0x14000c05c`
- `ntdll!RtlFreeHeap` at `0x14000c03a`
- `ntdll!RtlFreeHeap` at `0x14000c099`
- `ntdll!RtlFreeHeap` at `0x14000c03a`
- `ntdll!RtlFreeHeap` at `0x14000c099`
- `ntdll!EtwEventUnregister` at `0x14000c081`
- `ntdll!EtwEventUnregister` at `0x14000c081`

## pseudocode

```c
BOOLEAN __fastcall AslLogDelete(char *P)
{
  HMODULE v2; // rcx
  void *v3; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v2 = (HMODULE)*((_QWORD *)P + 90);
    if ( v2 )
    {
      FreeLibrary_0(v2);
      *((_QWORD *)P + 90) = 0;
    }
    v3 = (void *)*((_QWORD *)P + 23);
    if ( v3 )
      RtlFreeHeap(*((HANDLE *)P + 18), 0, v3);
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    *((_OWORD *)P + 11) = 0;
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 104));
    if ( *(_QWORD *)P )
      memset_0(*(void **)P, 0, 0x5Cu);
    if ( *((_QWORD *)P + 89) )
      EtwEventUnregister();
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x14000bff8  test    rcx, rcx
0x14000bffb  jz      locret_14000C0A4
0x14000c001  push    rbx
0x14000c002  sub     rsp, 20h
0x14000c006  mov     rbx, rcx
0x14000c009  mov     rcx, [rcx+2D0h]; hLibModule
0x14000c010  test    rcx, rcx
0x14000c013  jz      short loc_14000C025
0x14000c015  call    FreeLibrary_0
0x14000c01a  mov     qword ptr [rbx+2D0h], 0
0x14000c025  mov     r8, [rbx+0B8h]; P
0x14000c02c  test    r8, r8
0x14000c02f  jz      short loc_14000C040
0x14000c031  mov     rcx, [rbx+90h]; HeapHandle
0x14000c038  xor     edx, edx; Flags
0x14000c03a  call    cs:__imp_RtlFreeHeap
0x14000c040  xorps   xmm0, xmm0
0x14000c043  lea     rcx, [rbx+68h]; CriticalSection
0x14000c047  movups  xmmword ptr [rbx+90h], xmm0
0x14000c04e  movups  xmmword ptr [rbx+0A0h], xmm0
0x14000c055  movups  xmmword ptr [rbx+0B0h], xmm0
0x14000c05c  call    cs:__imp_RtlDeleteCriticalSection
0x14000c062  mov     rcx, [rbx]; void *
0x14000c065  test    rcx, rcx
0x14000c068  jz      short loc_14000C075
0x14000c06a  xor     edx, edx; Val
0x14000c06c  lea     r8d, [rdx+5Ch]; Size
0x14000c070  call    memset_0
0x14000c075  mov     rcx, [rbx+2C8h]
0x14000c07c  test    rcx, rcx
0x14000c07f  jz      short loc_14000C087
0x14000c081  call    cs:__imp_EtwEventUnregister
0x14000c087  mov     rcx, gs:60h
0x14000c090  mov     r8, rbx; P
0x14000c093  xor     edx, edx; Flags
0x14000c095  mov     rcx, [rcx+30h]; HeapHandle
0x14000c099  call    cs:__imp_RtlFreeHeap
0x14000c09f  add     rsp, 20h
0x14000c0a3  pop     rbx
0x14000c0a4  retn
```
