# ATL::CComObject<CFciPropertiesShellExt>::Release(void)

- ea: `0x18000cc50`
- end: `0x18000ccc5`
- name: `?Release@?$CComObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ`
- size: `117`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ccd0`

## callees

- `0x18000cc50`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFciPropertiesShellExt>::Release(_DWORD *a1)
{
  int v2; // ebx
  unsigned int v3; // ebx

  v2 = a1[4];
  if ( v2 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v2 - 1;
    a1[4] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000cc50  mov     [rsp+arg_0], rbx
0x18000cc55  push    rdi
0x18000cc56  sub     rsp, 30h
0x18000cc5a  mov     rdi, rcx
0x18000cc5d  mov     ebx, [rcx+10h]
0x18000cc60  cmp     ebx, 7FFFFFFFh
0x18000cc66  jnz     short loc_18000CC6F
0x18000cc68  mov     ebx, 7FFFFFFEh
0x18000cc6d  jmp     short loc_18000CCB8
0x18000cc6f  sub     ebx, 1
0x18000cc72  mov     [rcx+10h], ebx
0x18000cc75  jnz     short loc_18000CCB8
0x18000cc77  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cc7e  mov     rax, [rcx]
0x18000cc81  mov     rax, [rax+8]
0x18000cc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc8a  nop
0x18000cc8b  test    rdi, rdi
0x18000cc8e  jz      short loc_18000CCA5
0x18000cc90  mov     rax, [rdi]
0x18000cc93  mov     edx, 1
0x18000cc98  mov     rcx, rdi
0x18000cc9b  mov     rax, [rax+20h]
0x18000cc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca4  nop
0x18000cca5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ccac  mov     rdx, [rcx]
0x18000ccaf  mov     rax, [rdx+10h]
0x18000ccb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccb8  mov     eax, ebx
0x18000ccba  mov     rbx, [rsp+38h+arg_0]
0x18000ccbf  add     rsp, 30h
0x18000ccc3  pop     rdi
0x18000ccc4  retn
```
