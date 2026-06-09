# ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(void)

- ea: `0x140005f00`
- end: `0x140005f2e`
- name: `??1?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140005d04`
- `0x140005d50`
- `0x14000aba0`

## callees

- `0x140005f00`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
    result = (**v2)(v2, 1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140005f00  push    rbx
0x140005f02  sub     rsp, 20h
0x140005f06  mov     rbx, rcx
0x140005f09  mov     rcx, [rcx]
0x140005f0c  test    rcx, rcx
0x140005f0f  jz      short loc_140005F21
0x140005f11  mov     rax, [rcx]
0x140005f14  mov     edx, 1
0x140005f19  mov     rax, [rax]
0x140005f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f21  mov     qword ptr [rbx], 0
0x140005f28  add     rsp, 20h
0x140005f2c  pop     rbx
0x140005f2d  retn
```
