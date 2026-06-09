# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180001660`
- end: `0x1800016ad`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001660`
- `0x180005294`
- `0x18000597c`
- `0x180010010`

## pseudocode

```c
unsigned int __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(__int64 a1)
{
  unsigned int result; // eax
  _DWORD *v2; // r10
  unsigned int v3; // ebx

  result = ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease((int *)(a1 + 8));
  v3 = result;
  if ( result )
  {
    if ( result == 1 )
    {
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
      return 1;
    }
  }
  else if ( v2 )
  {
    ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v2);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180001660  push    rbx
0x180001662  sub     rsp, 20h
0x180001666  mov     r10, rcx
0x180001669  add     rcx, 8
0x18000166d  call    ?InternalRelease@?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(void)
0x180001672  mov     ebx, eax
0x180001674  test    eax, eax
0x180001676  jnz     short loc_18000168D
0x180001678  test    r10, r10
0x18000167b  jz      short loc_1800016A7
0x18000167d  mov     rcx, r10; void *
0x180001680  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180001685  mov     eax, ebx
0x180001687  add     rsp, 20h
0x18000168b  pop     rbx
0x18000168c  retn
0x18000168d  cmp     ebx, 1
0x180001690  jnz     short loc_1800016A7
0x180001692  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001699  mov     rax, [rcx]
0x18000169c  mov     rax, [rax+10h]
0x1800016a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016a5  mov     eax, ebx
0x1800016a7  add     rsp, 20h
0x1800016ab  pop     rbx
0x1800016ac  retn
```
