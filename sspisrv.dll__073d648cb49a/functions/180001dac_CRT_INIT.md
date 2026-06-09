# _CRT_INIT

- ea: `0x180001dac`
- end: `0x180001e8a`
- name: `_CRT_INIT`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001ed4`

## callees

- `0x180001dac`
- `0x180001fe8`
- `0x180001ff8`
- `0x1800020eb`
- `0x1800020f7`
- `0x180003430`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001e57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001e57`

## pseudocode

```c
__int64 __fastcall CRT_INIT(__int64 a1, int a2)
{
  PVOID *v3; // rdi
  PVOID *i; // rbx
  void (*v5)(void); // rax
  HANDLE ProcessHeap; // rax

  if ( a2 == 1 )
  {
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 0;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    ++dword_18000A0A0;
  }
  else if ( !a2 )
  {
    if ( dword_18000A0D8 )
    {
      v3 = (PVOID *)decode_pointer(_dllonexit_data);
      for ( i = (PVOID *)((char *)decode_pointer(Ptr) - 8); i >= v3; --i )
      {
        v5 = (void (*)(void))decode_pointer(*i);
        if ( v5 )
          v5();
      }
      if ( (unsigned int)dword_18000A0D8 > 4 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
      }
      Ptr = (PVOID)encoded_null();
      _dllonexit_data = Ptr;
    }
    dword_18000A0A0 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001dac  mov     [rsp+arg_0], rbx
0x180001db1  push    rdi
0x180001db2  sub     rsp, 20h
0x180001db6  cmp     edx, 1
0x180001db9  jnz     short loc_180001DF7
0x180001dbb  lea     rdx, __xi_z; Last
0x180001dc2  lea     rcx, __xi_a; First
0x180001dc9  call    _initterm_e_0
0x180001dce  test    eax, eax
0x180001dd0  jz      short loc_180001DD9
0x180001dd2  xor     eax, eax
0x180001dd4  jmp     loc_180001E7F
0x180001dd9  lea     rdx, __xc_z; Last
0x180001de0  lea     rcx, __xc_a; First
0x180001de7  call    _initterm_0
0x180001dec  inc     cs:dword_18000A0A0
0x180001df2  jmp     loc_180001E7A
0x180001df7  test    edx, edx
0x180001df9  jnz     short loc_180001E7A
0x180001dfb  cmp     cs:dword_18000A0D8, edx
0x180001e01  jz      short loc_180001E70
0x180001e03  mov     rcx, cs:__dllonexit_data; Ptr
0x180001e0a  call    _decode_pointer
0x180001e0f  mov     rcx, cs:Ptr; Ptr
0x180001e16  mov     rdi, rax
0x180001e19  call    _decode_pointer
0x180001e1e  lea     rbx, [rax-8]
0x180001e22  jmp     short loc_180001E3B
0x180001e24  mov     rcx, [rbx]; Ptr
0x180001e27  call    _decode_pointer
0x180001e2c  test    rax, rax
0x180001e2f  jz      short loc_180001E37
0x180001e31  call    cs:__guard_dispatch_icall_fptr
0x180001e37  sub     rbx, 8
0x180001e3b  cmp     rbx, rdi
0x180001e3e  jnb     short loc_180001E24
0x180001e40  cmp     cs:dword_18000A0D8, 4
0x180001e47  jbe     short loc_180001E5D
0x180001e49  call    cs:__imp_GetProcessHeap
0x180001e4f  mov     r8, rdi; lpMem
0x180001e52  xor     edx, edx; dwFlags
0x180001e54  mov     rcx, rax; hHeap
0x180001e57  call    cs:__imp_HeapFree
0x180001e5d  call    _encoded_null
0x180001e62  mov     cs:Ptr, rax
0x180001e69  mov     cs:__dllonexit_data, rax
0x180001e70  mov     cs:dword_18000A0A0, 0
0x180001e7a  mov     eax, 1
0x180001e7f  mov     rbx, [rsp+28h+arg_0]
0x180001e84  add     rsp, 20h
0x180001e88  pop     rdi
0x180001e89  retn
```
