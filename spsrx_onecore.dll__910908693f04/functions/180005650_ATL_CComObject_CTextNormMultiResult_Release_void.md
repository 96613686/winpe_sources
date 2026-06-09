# ATL::CComObject<CTextNormMultiResult>::Release(void)

- ea: `0x180005650`
- end: `0x1800056b9`
- name: `?Release@?$CComObject@VCTextNormMultiResult@@@ATL@@UEAAKXZ`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005294`
- `0x180005650`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTextNormMultiResult>::Release(int *a1)
{
  unsigned int v2; // edi

  v2 = ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(a1 + 2);
  if ( !v2 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(int *, _QWORD))(*(_QWORD *)a1 + 240LL))(a1, v2 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180005650  mov     [rsp+arg_0], rbx
0x180005655  push    rdi
0x180005656  sub     rsp, 20h
0x18000565a  mov     rbx, rcx
0x18000565d  add     rcx, 8
0x180005661  call    ?InternalRelease@?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(void)
0x180005666  mov     edi, eax
0x180005668  test    eax, eax
0x18000566a  jnz     short loc_1800056AC
0x18000566c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005673  mov     rdx, [rcx]
0x180005676  mov     rax, [rdx+8]
0x18000567a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000567f  test    rbx, rbx
0x180005682  jz      short loc_180005699
0x180005684  mov     rax, [rbx]
0x180005687  lea     edx, [rdi+1]
0x18000568a  mov     rcx, rbx
0x18000568d  mov     rax, [rax+0F0h]
0x180005694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005699  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800056a0  mov     rax, [rcx]
0x1800056a3  mov     rax, [rax+10h]
0x1800056a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ac  mov     rbx, [rsp+28h+arg_0]
0x1800056b1  mov     eax, edi
0x1800056b3  add     rsp, 20h
0x1800056b7  pop     rdi
0x1800056b8  retn
```
