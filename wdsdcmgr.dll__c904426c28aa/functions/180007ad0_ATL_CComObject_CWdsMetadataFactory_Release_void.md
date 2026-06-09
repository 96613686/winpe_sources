# ATL::CComObject<CWdsMetadataFactory>::Release(void)

- ea: `0x180007ad0`
- end: `0x180007b3a`
- name: `?Release@?$CComObject@VCWdsMetadataFactory@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007ad0`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsMetadataFactory>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 40LL))(a1);
    _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  return v2;
}

```

## disassembly

```asm
0x180007ad0  push    rbx
0x180007ad2  sub     rsp, 20h
0x180007ad6  mov     r8d, [rcx+8]
0x180007ada  mov     r9, rcx
0x180007add  mov     ecx, 7FFFFFFFh
0x180007ae2  jmp     short loc_180007AF7
0x180007ae4  lea     edx, [r8-1]
0x180007ae8  mov     eax, r8d
0x180007aeb  lock cmpxchg [r9+8], edx
0x180007af1  jz      short loc_180007AFC
0x180007af3  mov     r8d, [r9+8]
0x180007af7  cmp     r8d, ecx
0x180007afa  jnz     short loc_180007AE4
0x180007afc  lea     ebx, [r8-1]
0x180007b00  test    ebx, ebx
0x180007b02  jnz     short loc_180007B32
0x180007b04  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b0b  lea     edx, [rbx+1]
0x180007b0e  lock add [rax+0Ch], edx
0x180007b12  test    r9, r9
0x180007b15  jz      short loc_180007B27
0x180007b17  mov     rcx, [r9]
0x180007b1a  mov     rax, [rcx+28h]
0x180007b1e  mov     rcx, r9
0x180007b21  call    cs:__guard_dispatch_icall_fptr
0x180007b27  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b2e  lock dec dword ptr [rcx+0Ch]
0x180007b32  mov     eax, ebx
0x180007b34  add     rsp, 20h
0x180007b38  pop     rbx
0x180007b39  retn
```
