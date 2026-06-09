# ATL::CComObject<CWdsComMetadataEntry>::Release(void)

- ea: `0x180012540`
- end: `0x1800125ad`
- name: `?Release@?$CComObject@VCWdsComMetadataEntry@@@ATL@@UEAAKXZ`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012540`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsComMetadataEntry>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 128LL))(a1);
    _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  return v2;
}

```

## disassembly

```asm
0x180012540  push    rbx
0x180012542  sub     rsp, 20h
0x180012546  mov     r8d, [rcx+8]
0x18001254a  mov     r9, rcx
0x18001254d  mov     ecx, 7FFFFFFFh
0x180012552  jmp     short loc_180012567
0x180012554  lea     edx, [r8-1]
0x180012558  mov     eax, r8d
0x18001255b  lock cmpxchg [r9+8], edx
0x180012561  jz      short loc_18001256C
0x180012563  mov     r8d, [r9+8]
0x180012567  cmp     r8d, ecx
0x18001256a  jnz     short loc_180012554
0x18001256c  lea     ebx, [r8-1]
0x180012570  test    ebx, ebx
0x180012572  jnz     short loc_1800125A5
0x180012574  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001257b  lea     edx, [rbx+1]
0x18001257e  lock add [rax+0Ch], edx
0x180012582  test    r9, r9
0x180012585  jz      short loc_18001259A
0x180012587  mov     rcx, [r9]
0x18001258a  mov     rax, [rcx+80h]
0x180012591  mov     rcx, r9
0x180012594  call    cs:__guard_dispatch_icall_fptr
0x18001259a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800125a1  lock dec dword ptr [rcx+0Ch]
0x1800125a5  mov     eax, ebx
0x1800125a7  add     rsp, 20h
0x1800125ab  pop     rbx
0x1800125ac  retn
```
