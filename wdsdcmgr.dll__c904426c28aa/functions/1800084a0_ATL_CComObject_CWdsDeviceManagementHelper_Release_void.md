# ATL::CComObject<CWdsDeviceManagementHelper>::Release(void)

- ea: `0x1800084a0`
- end: `0x18000850a`
- name: `?Release@?$CComObject@VCWdsDeviceManagementHelper@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800084a0`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsDeviceManagementHelper>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v2; // ebx

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v2 = i - 1;
  if ( i == 1 )
  {
    _InterlockedAdd((volatile signed __int32 *)ATL::_pAtlModule + 3, 1u);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 32LL))(a1);
    _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  return v2;
}

```

## disassembly

```asm
0x1800084a0  push    rbx
0x1800084a2  sub     rsp, 20h
0x1800084a6  mov     r8d, [rcx+8]
0x1800084aa  mov     r9, rcx
0x1800084ad  mov     ecx, 7FFFFFFFh
0x1800084b2  jmp     short loc_1800084C7
0x1800084b4  lea     edx, [r8-1]
0x1800084b8  mov     eax, r8d
0x1800084bb  lock cmpxchg [r9+8], edx
0x1800084c1  jz      short loc_1800084CC
0x1800084c3  mov     r8d, [r9+8]
0x1800084c7  cmp     r8d, ecx
0x1800084ca  jnz     short loc_1800084B4
0x1800084cc  lea     ebx, [r8-1]
0x1800084d0  test    ebx, ebx
0x1800084d2  jnz     short loc_180008502
0x1800084d4  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800084db  lea     edx, [rbx+1]
0x1800084de  lock add [rax+0Ch], edx
0x1800084e2  test    r9, r9
0x1800084e5  jz      short loc_1800084F7
0x1800084e7  mov     rcx, [r9]
0x1800084ea  mov     rax, [rcx+20h]
0x1800084ee  mov     rcx, r9
0x1800084f1  call    cs:__guard_dispatch_icall_fptr
0x1800084f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800084fe  lock dec dword ptr [rcx+0Ch]
0x180008502  mov     eax, ebx
0x180008504  add     rsp, 20h
0x180008508  pop     rbx
0x180008509  retn
```
