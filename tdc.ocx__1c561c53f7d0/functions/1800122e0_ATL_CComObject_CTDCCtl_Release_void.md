# ATL::CComObject<CTDCCtl>::Release(void)

- ea: `0x1800122e0`
- end: `0x18001235c`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ`
- size: `124`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012370`
- `0x180012380`
- `0x180012390`
- `0x1800123a0`
- `0x1800123b0`
- `0x1800123c0`
- `0x1800123d0`
- `0x1800123e0`
- `0x1800123f0`
- `0x180012400`
- `0x180012410`

## callees

- `0x1800122e0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTDCCtl>::Release(__int64 a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = *(_DWORD *)(a1 + 128);
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    *(_DWORD *)(a1 + 128) = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 != 176 )
        (**(void (__fastcall ***)(__int64, __int64))(a1 - 176))(a1 - 176, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800122e0  mov     [rsp+arg_0], rbx
0x1800122e5  push    rdi
0x1800122e6  sub     rsp, 20h
0x1800122ea  mov     ebx, [rcx+80h]
0x1800122f0  mov     rdi, rcx
0x1800122f3  cmp     ebx, 7FFFFFFFh
0x1800122f9  jnz     short loc_180012302
0x1800122fb  mov     ebx, 7FFFFFFEh
0x180012300  jmp     short loc_18001234F
0x180012302  sub     ebx, 1
0x180012305  mov     [rcx+80h], ebx
0x18001230b  jnz     short loc_18001234F
0x18001230d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012314  mov     rax, [rcx]
0x180012317  mov     rax, [rax+8]
0x18001231b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012320  lea     rcx, [rdi-0B0h]
0x180012327  test    rcx, rcx
0x18001232a  jz      short loc_18001233C
0x18001232c  mov     rax, [rcx]
0x18001232f  mov     edx, 1
0x180012334  mov     rax, [rax]
0x180012337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001233c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012343  mov     rdx, [rcx]
0x180012346  mov     rax, [rdx+10h]
0x18001234a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001234f  mov     eax, ebx
0x180012351  mov     rbx, [rsp+28h+arg_0]
0x180012356  add     rsp, 20h
0x18001235a  pop     rdi
0x18001235b  retn
```
