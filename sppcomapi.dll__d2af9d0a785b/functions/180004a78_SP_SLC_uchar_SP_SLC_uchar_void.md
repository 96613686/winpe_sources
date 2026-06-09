# SP_SLC<uchar>::~SP_SLC<uchar>(void)

- ea: `0x180004a78`
- end: `0x180004aa3`
- name: `??1?$SP_SLC@E@@QEAA@XZ`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## callees

- `0x180004a78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a89`

## pseudocode

```c
HLOCAL __fastcall SP_SLC<unsigned char>::~SP_SLC<unsigned char>(void **a1)
{
  void *v2; // rcx
  HLOCAL result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = LocalFree(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004a78  push    rbx
0x180004a7a  sub     rsp, 20h
0x180004a7e  mov     rbx, rcx
0x180004a81  mov     rcx, [rcx]; hMem
0x180004a84  test    rcx, rcx
0x180004a87  jz      short loc_180004A9C
0x180004a89  call    cs:__imp_LocalFree
0x180004a90  nop     dword ptr [rax+rax+00h]
0x180004a95  mov     qword ptr [rbx], 0
0x180004a9c  add     rsp, 20h
0x180004aa0  pop     rbx
0x180004aa1  retn
```
