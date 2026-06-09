# ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release(void)

- ea: `0x1800087d0`
- end: `0x180008843`
- name: `?Release@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008850`
- `0x180008860`
- `0x180008870`

## callees

- `0x1800087d0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[8];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[8] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 88LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800087d0  mov     [rsp+arg_0], rbx
0x1800087d5  push    rdi
0x1800087d6  sub     rsp, 20h
0x1800087da  mov     ebx, [rcx+20h]
0x1800087dd  mov     rdi, rcx
0x1800087e0  cmp     ebx, 7FFFFFFFh
0x1800087e6  jnz     short loc_1800087EF
0x1800087e8  mov     ebx, 7FFFFFFEh
0x1800087ed  jmp     short loc_180008836
0x1800087ef  sub     ebx, 1
0x1800087f2  mov     [rcx+20h], ebx
0x1800087f5  jnz     short loc_180008836
0x1800087f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800087fe  mov     rax, [rcx]
0x180008801  mov     rax, [rax+8]
0x180008805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880a  test    rdi, rdi
0x18000880d  jz      short loc_180008823
0x18000880f  mov     rax, [rdi]
0x180008812  mov     edx, 1
0x180008817  mov     rcx, rdi
0x18000881a  mov     rax, [rax+58h]
0x18000881e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008823  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000882a  mov     rdx, [rcx]
0x18000882d  mov     rax, [rdx+10h]
0x180008831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008836  mov     eax, ebx
0x180008838  mov     rbx, [rsp+28h+arg_0]
0x18000883d  add     rsp, 20h
0x180008841  pop     rdi
0x180008842  retn
```
