# TdxDereferenceDeviceObjectContext

- ea: `0x14000daa0`
- end: `0x14000db02`
- name: `TdxDereferenceDeviceObjectContext`
- size: `98`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cfc0`
- `0x14000d790`
- `0x14000eba0`
- `0x140015038`

## callees

- `0x14000daa0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000dadd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dadd`

## pseudocode

```c
__int64 __fastcall TdxDereferenceDeviceObjectContext(volatile signed __int32 *a1)
{
  _QWORD *v1; // rax
  void **v2; // rdx
  __int64 v3; // rbx

  if ( _InterlockedExchangeAdd(a1 + 4, 0xFFFFFFFF) != 1 )
    return 0;
  v1 = *(_QWORD **)a1;
  if ( *(volatile signed __int32 **)(*(_QWORD *)a1 + 8LL) != a1 || (v2 = (void **)*((_QWORD *)a1 + 1), *v2 != a1) )
    __fastfail(3u);
  v3 = *((_QWORD *)a1 + 35);
  *v2 = v1;
  v1[1] = v2;
  ExFreePoolWithTag((PVOID)a1, 0x6F786454u);
  return v3;
}

```

## disassembly

```asm
0x14000daa0  sub     rsp, 28h
0x14000daa4  mov     eax, 0FFFFFFFFh
0x14000daa9  lock xadd [rcx+10h], eax
0x14000daae  cmp     eax, 1
0x14000dab1  jnz     short loc_14000DAF7
0x14000dab3  mov     rax, [rcx]
0x14000dab6  cmp     [rax+8], rcx
0x14000daba  jnz     short loc_14000DAFB
0x14000dabc  mov     rdx, [rcx+8]
0x14000dac0  cmp     [rdx], rcx
0x14000dac3  jnz     short loc_14000DAFB
0x14000dac5  mov     [rsp+28h+var_8], rbx
0x14000daca  mov     rbx, [rcx+118h]
0x14000dad1  mov     [rdx], rax
0x14000dad4  mov     [rax+8], rdx
0x14000dad8  mov     edx, 6F786454h; Tag
0x14000dadd  call    cs:__imp_ExFreePoolWithTag
0x14000dae4  nop     dword ptr [rax+rax+00h]
0x14000dae9  mov     rax, rbx
0x14000daec  mov     rbx, [rsp+28h+var_8]
0x14000daf1  add     rsp, 28h
0x14000daf5  retn
0x14000daf7  xor     eax, eax
0x14000daf9  jmp     short loc_14000DAF1
0x14000dafb  mov     ecx, 3
0x14000db00  int     29h; Win8: RtlFailFast(ecx)
```
