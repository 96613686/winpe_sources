# ATL::CComObject<CRecoExt>::`scalar deleting destructor'(uint)

- ea: `0x180005940`
- end: `0x180005974`
- name: `??_G?$CComObject@VCRecoExt@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002594`
- `0x1800057f8`
- `0x180005940`

## pseudocode

```c
void *__fastcall ATL::CComObject<CRecoExt>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CRecoExt>::~CComObject<CRecoExt>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180005940  mov     [rsp+arg_0], rbx
0x180005945  push    rdi
0x180005946  sub     rsp, 20h
0x18000594a  mov     ebx, edx
0x18000594c  mov     rdi, rcx
0x18000594f  call    ??1?$CComObject@VCRecoExt@@@ATL@@UEAA@XZ; ATL::CComObject<CRecoExt>::~CComObject<CRecoExt>(void)
0x180005954  test    bl, 1
0x180005957  jz      short loc_180005966
0x180005959  mov     edx, 88h; unsigned __int64
0x18000595e  mov     rcx, rdi; void *
0x180005961  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005966  mov     rbx, [rsp+28h+arg_0]
0x18000596b  mov     rax, rdi
0x18000596e  add     rsp, 20h
0x180005972  pop     rdi
0x180005973  retn
```
