# SclFreeRequest

- ea: `0x180001f70`
- end: `0x180002004`
- name: `SclFreeRequest`
- size: `148`
- prototype: `void *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002010`
- `0x1800065f8`
- `0x1800073c4`

## callees

- `0x180001f70`
- `0x1800179c5`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001f99`
- `ntdll!RtlFreeHeap` at `0x180001fbf`
- `ntdll!RtlFreeHeap` at `0x180001fe8`
- `ntdll!RtlFreeHeap` at `0x180001f99`
- `ntdll!RtlFreeHeap` at `0x180001fbf`
- `ntdll!RtlFreeHeap` at `0x180001fe8`

## pseudocode

```c
void *__fastcall SclFreeRequest(_QWORD *a1)
{
  void *v1; // r8
  void *v3; // r8
  void *v4; // r8
  void *result; // rax

  if ( a1 )
  {
    v1 = (void *)a1[1];
    if ( v1 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
      a1[1] = 0;
    }
    v3 = (void *)a1[2];
    if ( v3 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
      a1[2] = 0;
    }
    v4 = (void *)a1[133];
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    return memset_0(a1, 0, 0x478u);
  }
  return result;
}

```

## disassembly

```asm
0x180001f70  test    rcx, rcx
0x180001f73  jz      locret_180002003
0x180001f79  push    rbx
0x180001f7a  sub     rsp, 20h
0x180001f7e  mov     r8, [rcx+8]; P
0x180001f82  mov     rbx, rcx
0x180001f85  test    r8, r8
0x180001f88  jz      short loc_180001FA7
0x180001f8a  mov     rcx, gs:60h
0x180001f93  xor     edx, edx; Flags
0x180001f95  mov     rcx, [rcx+30h]; HeapHandle
0x180001f99  call    cs:__imp_RtlFreeHeap
0x180001f9f  mov     qword ptr [rbx+8], 0
0x180001fa7  mov     r8, [rbx+10h]; P
0x180001fab  test    r8, r8
0x180001fae  jz      short loc_180001FCD
0x180001fb0  mov     rcx, gs:60h
0x180001fb9  xor     edx, edx; Flags
0x180001fbb  mov     rcx, [rcx+30h]; HeapHandle
0x180001fbf  call    cs:__imp_RtlFreeHeap
0x180001fc5  mov     qword ptr [rbx+10h], 0
0x180001fcd  mov     r8, [rbx+428h]; P
0x180001fd4  test    r8, r8
0x180001fd7  jz      short loc_180001FEE
0x180001fd9  mov     rcx, gs:60h
0x180001fe2  xor     edx, edx; Flags
0x180001fe4  mov     rcx, [rcx+30h]; HeapHandle
0x180001fe8  call    cs:__imp_RtlFreeHeap
0x180001fee  xor     edx, edx; Val
0x180001ff0  mov     r8d, 478h; Size
0x180001ff6  mov     rcx, rbx; void *
0x180001ff9  call    memset_0
0x180001ffe  add     rsp, 20h
0x180002002  pop     rbx
0x180002003  retn
```
