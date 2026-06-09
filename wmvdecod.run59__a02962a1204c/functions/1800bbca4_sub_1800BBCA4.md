# sub_1800BBCA4

- ea: `0x1800bbca4`
- end: `0x1800bbcf9`
- name: `sub_1800BBCA4`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800bbd00`
- `0x1800bce14`
- `0x1800be424`

## callees

- `0x180099040`
- `0x1800bb030`
- `0x1800bbca4`
- `0x1800bbd60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bbcc0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bbcc0`

## pseudocode

```c
__int64 __fastcall sub_1800BBCA4(__int64 a1)
{
  __int64 v2; // rcx

  *(_QWORD *)a1 = off_1802111C0;
  sub_1800BBD60();
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  v2 = *(_QWORD *)(a1 + 792);
  if ( v2 )
  {
    j_j__o_free(v2);
    *(_QWORD *)(a1 + 792) = 0;
  }
  return sub_1800BB030(a1 + 704);
}

```

## disassembly

```asm
0x1800bbca4  push    rbx
0x1800bbca6  sub     rsp, 20h
0x1800bbcaa  lea     rax, off_1802111C0
0x1800bbcb1  mov     rbx, rcx
0x1800bbcb4  mov     [rcx], rax
0x1800bbcb7  call    sub_1800BBD60
0x1800bbcbc  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800bbcc0  call    cs:DeleteCriticalSection
0x1800bbcc7  nop     dword ptr [rax+rax+00h]
0x1800bbccc  mov     rcx, [rbx+318h]
0x1800bbcd3  test    rcx, rcx
0x1800bbcd6  jz      short loc_1800BBCE8
0x1800bbcd8  call    j_j__o_free
0x1800bbcdd  mov     qword ptr [rbx+318h], 0
0x1800bbce8  lea     rcx, [rbx+2C0h]
0x1800bbcef  add     rsp, 20h
0x1800bbcf3  pop     rbx
0x1800bbcf4  jmp     sub_1800BB030
```
