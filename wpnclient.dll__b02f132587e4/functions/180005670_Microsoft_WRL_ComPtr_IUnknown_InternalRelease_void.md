# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180005670`
- end: `0x18000569a`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `42`
- prototype: ``
- caller_count: `92`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b70`
- `0x180005080`
- `0x180006a10`
- `0x180006ad0`
- `0x180006d30`
- `0x18000735c`
- `0x180007760`
- `0x180007d34`
- `0x180008560`
- `0x1800089a0`
- `0x180009380`
- `0x180009890`
- `0x18000a460`
- `0x18000b440`
- `0x18000bbf0`
- `0x18000c7d0`
- `0x18000cb68`
- `0x18000d0d0`
- `0x18000da20`
- `0x18000ddcc`
- `0x18000de8c`
- `0x18000df1c`
- `0x18000dfdc`
- `0x18000e054`
- `0x18000e23c`
- `0x18000e2ac`
- `0x18000e2dc`
- `0x18000e30c`
- `0x18000e3b0`
- `0x18000ed18`
- `0x18000f750`
- `0x180010270`
- `0x180010a54`
- `0x180010f1c`
- `0x1800119b0`
- `0x180015d14`
- `0x180015e40`
- `0x180016334`
- `0x18001780c`
- `0x180018094`
- `0x180018158`
- `0x180018210`
- `0x180018298`
- `0x18001849c`
- `0x1800186f0`
- `0x180018d90`
- `0x1800192d4`
- `0x1800199dc`
- `0x180019b4c`
- `0x180019d04`

## callees

- `0x180005670`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x180005670  sub     rsp, 28h
0x180005674  mov     rax, rcx
0x180005677  xor     edx, edx
0x180005679  mov     rcx, [rcx]
0x18000567c  test    rcx, rcx
0x18000567f  jz      short loc_180005696
0x180005681  mov     [rax], rdx
0x180005684  mov     rax, [rcx]
0x180005687  mov     rax, [rax+10h]
0x18000568b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005690  nop
0x180005691  add     rsp, 28h
0x180005695  retn
0x180005696  mov     eax, edx
0x180005698  jmp     short loc_180005691
```
