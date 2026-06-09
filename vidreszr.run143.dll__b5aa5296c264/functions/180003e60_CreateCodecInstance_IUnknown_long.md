# CreateCodecInstance(IUnknown *,long *)

- ea: `0x180003e60`
- end: `0x180003eaf`
- name: `?CreateCodecInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `79`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001974`
- `0x180002780`
- `0x180003e60`

## pseudocode

```c
struct CComBase *__fastcall CreateCodecInstance(struct IUnknown *a1, int *a2)
{
  CWMResizeDMO *v4; // rax
  CWMResizeDMO *v5; // rdx
  struct CComBase *result; // rax

  v4 = (CWMResizeDMO *)operator new(0x5F0u);
  if ( v4 )
    v5 = CWMResizeDMO::CWMResizeDMO(v4, a1, a2);
  else
    v5 = 0;
  result = (CWMResizeDMO *)((char *)v5 + 416);
  if ( !v5 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180003e60  mov     [rsp+arg_0], rbx
0x180003e65  push    rdi
0x180003e66  sub     rsp, 20h
0x180003e6a  mov     rdi, rcx
0x180003e6d  mov     rbx, rdx
0x180003e70  mov     ecx, 5F0h; Size
0x180003e75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e7a  test    rax, rax
0x180003e7d  jz      short loc_180003E92
0x180003e7f  mov     r8, rbx; int *
0x180003e82  mov     rdx, rdi; struct IUnknown *
0x180003e85  mov     rcx, rax; this
0x180003e88  call    ??0CWMResizeDMO@@QEAA@PEAUIUnknown@@PEAJ@Z; CWMResizeDMO::CWMResizeDMO(IUnknown *,long *)
0x180003e8d  mov     rdx, rax
0x180003e90  jmp     short loc_180003E94
0x180003e92  xor     edx, edx
0x180003e94  mov     rbx, [rsp+28h+arg_0]
0x180003e99  lea     rax, [rdx+1A0h]
0x180003ea0  xor     ecx, ecx
0x180003ea2  test    rdx, rdx
0x180003ea5  cmovz   rax, rcx
0x180003ea9  add     rsp, 20h
0x180003ead  pop     rdi
0x180003eae  retn
```
