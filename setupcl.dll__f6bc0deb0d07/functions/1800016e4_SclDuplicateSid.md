# SclDuplicateSid

- ea: `0x1800016e4`
- end: `0x18000175b`
- name: `SclDuplicateSid`
- size: `119`
- prototype: `__int64 __fastcall(void *Src, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001848`
- `0x1800073c4`

## callees

- `0x1800016e4`
- `0x1800179ad`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000171d`
- `ntdll!RtlAllocateHeap` at `0x18000171d`
- `ntdll!RtlLengthSid` at `0x180001703`
- `ntdll!RtlLengthSid` at `0x180001703`

## pseudocode

```c
__int64 __fastcall SclDuplicateSid(void *Src, _QWORD *a2)
{
  ULONG v4; // esi
  PVOID Heap; // rax
  unsigned int v6; // ebx

  if ( !Src || !a2 )
    return 3221225485LL;
  v4 = RtlLengthSid(Src);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  *a2 = Heap;
  if ( Heap )
  {
    v6 = 0;
    memcpy_0(Heap, Src, v4);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v6;
}

```

## disassembly

```asm
0x1800016e4  mov     [rsp+arg_0], rbx
0x1800016e9  mov     [rsp+arg_8], rsi
0x1800016ee  push    rdi
0x1800016ef  sub     rsp, 20h
0x1800016f3  mov     rbx, rdx
0x1800016f6  mov     rdi, rcx
0x1800016f9  test    rcx, rcx
0x1800016fc  jz      short loc_180001746
0x1800016fe  test    rdx, rdx
0x180001701  jz      short loc_180001746
0x180001703  call    cs:__imp_RtlLengthSid
0x180001709  mov     rcx, gs:60h
0x180001712  xor     edx, edx; Flags
0x180001714  mov     r8d, eax; Size
0x180001717  mov     esi, eax
0x180001719  mov     rcx, [rcx+30h]; HeapHandle
0x18000171d  call    cs:__imp_RtlAllocateHeap
0x180001723  mov     [rbx], rax
0x180001726  test    rax, rax
0x180001729  jz      short loc_18000173D
0x18000172b  xor     ebx, ebx
0x18000172d  mov     r8d, esi; Size
0x180001730  mov     rdx, rdi; Src
0x180001733  mov     rcx, rax; void *
0x180001736  call    memcpy_0
0x18000173b  jmp     short loc_180001742
0x18000173d  mov     ebx, 0C0000017h
0x180001742  mov     eax, ebx
0x180001744  jmp     short loc_18000174B
0x180001746  mov     eax, 0C000000Dh
0x18000174b  mov     rbx, [rsp+28h+arg_0]
0x180001750  mov     rsi, [rsp+28h+arg_8]
0x180001755  add     rsp, 20h
0x180001759  pop     rdi
0x18000175a  retn
```
