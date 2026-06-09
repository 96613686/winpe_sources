# ATL::CComObject<CWdsSimpleDeviceController>::Release(void)

- ea: `0x180004ea0`
- end: `0x180004f22`
- name: `?Release@?$CComObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004f30`

## callees

- `0x180004ea0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsSimpleDeviceController>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 4, i - 1, i);
        i = *((_DWORD *)a1 + 4) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180004ea0  mov     [rsp+arg_0], rbx
0x180004ea5  push    rdi
0x180004ea6  sub     rsp, 20h
0x180004eaa  mov     r8d, [rcx+10h]
0x180004eae  mov     rbx, rcx
0x180004eb1  mov     ecx, 7FFFFFFFh
0x180004eb6  jmp     short loc_180004ECA
0x180004eb8  lea     edx, [r8-1]
0x180004ebc  mov     eax, r8d
0x180004ebf  lock cmpxchg [rbx+10h], edx
0x180004ec4  jz      short loc_180004ECF
0x180004ec6  mov     r8d, [rbx+10h]
0x180004eca  cmp     r8d, ecx
0x180004ecd  jnz     short loc_180004EB8
0x180004ecf  lea     edi, [r8-1]
0x180004ed3  test    edi, edi
0x180004ed5  jnz     short loc_180004F14
0x180004ed7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004ede  mov     rax, [rcx]
0x180004ee1  mov     rax, [rax+8]
0x180004ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eea  test    rbx, rbx
0x180004eed  jz      short loc_180004F01
0x180004eef  mov     rax, [rbx]
0x180004ef2  lea     edx, [rdi+1]
0x180004ef5  mov     rcx, rbx
0x180004ef8  mov     rax, [rax+30h]
0x180004efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f01  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004f08  mov     rdx, [rcx]
0x180004f0b  mov     rax, [rdx+10h]
0x180004f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f14  mov     rbx, [rsp+28h+arg_0]
0x180004f19  mov     eax, edi
0x180004f1b  add     rsp, 20h
0x180004f1f  pop     rdi
0x180004f20  retn
```
