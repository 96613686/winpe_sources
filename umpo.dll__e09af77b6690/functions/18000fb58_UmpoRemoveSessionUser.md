# UmpoRemoveSessionUser

- ea: `0x18000fb58`
- end: `0x18000fbac`
- name: `UmpoRemoveSessionUser`
- size: `84`
- prototype: `BOOLEAN __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800171e4`

## callees

- `0x18000fb58`
- `0x18000fbb4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000fb9e`

## pseudocode

```c
BOOLEAN __fastcall UmpoRemoveSessionUser(_QWORD *a1)
{
  _QWORD *v2; // rcx
  void **v3; // rax

  UmpoTraceSessionUserLoginChange(0, a1[4], *((unsigned int *)a1 + 6), a1[2]);
  v2 = (_QWORD *)*a1;
  if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v3 = (void **)a1[1], *v3 != a1) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = v3;
  return RtlFreeHeap(UmpoHeapHandle, 0, a1);
}

```

## disassembly

```asm
0x18000fb58  push    rbx
0x18000fb5a  sub     rsp, 20h
0x18000fb5e  mov     r9, [rcx+10h]
0x18000fb62  mov     rbx, rcx
0x18000fb65  mov     r8d, [rcx+18h]
0x18000fb69  mov     rdx, [rcx+20h]
0x18000fb6d  xor     ecx, ecx
0x18000fb6f  call    UmpoTraceSessionUserLoginChange
0x18000fb74  mov     rcx, [rbx]
0x18000fb77  cmp     [rcx+8], rbx
0x18000fb7b  jnz     short loc_18000FBA5
0x18000fb7d  mov     rax, [rbx+8]
0x18000fb81  cmp     [rax], rbx
0x18000fb84  jnz     short loc_18000FBA5
0x18000fb86  mov     [rax], rcx
0x18000fb89  mov     r8, rbx
0x18000fb8c  mov     [rcx+8], rax
0x18000fb90  xor     edx, edx
0x18000fb92  mov     rcx, cs:UmpoHeapHandle
0x18000fb99  add     rsp, 20h
0x18000fb9d  pop     rbx
0x18000fb9e  jmp     cs:__imp_RtlFreeHeap
0x18000fba5  mov     ecx, 3
0x18000fbaa  int     29h; Win8: RtlFailFast(ecx)
```
