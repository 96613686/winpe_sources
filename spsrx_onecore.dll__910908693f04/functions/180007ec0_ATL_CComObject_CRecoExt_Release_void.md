# ATL::CComObject<CRecoExt>::Release(void)

- ea: `0x180007ec0`
- end: `0x180007f29`
- name: `?Release@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ`
- size: `105`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003470`
- `0x180003480`
- `0x180003490`
- `0x1800034a0`
- `0x1800034b0`
- `0x1800034c0`
- `0x1800034d0`

## callees

- `0x180005294`
- `0x180007ec0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRecoExt>::Release(__int64 a1)
{
  unsigned int v2; // edi

  v2 = ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(a1 + 64);
  if ( !v2 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 376LL))(a1, v2 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180007ec0  mov     [rsp+arg_0], rbx
0x180007ec5  push    rdi
0x180007ec6  sub     rsp, 20h
0x180007eca  mov     rbx, rcx
0x180007ecd  add     rcx, 40h ; '@'
0x180007ed1  call    ?InternalRelease@?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(void)
0x180007ed6  mov     edi, eax
0x180007ed8  test    eax, eax
0x180007eda  jnz     short loc_180007F1C
0x180007edc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007ee3  mov     rdx, [rcx]
0x180007ee6  mov     rax, [rdx+8]
0x180007eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eef  test    rbx, rbx
0x180007ef2  jz      short loc_180007F09
0x180007ef4  mov     rax, [rbx]
0x180007ef7  lea     edx, [rdi+1]
0x180007efa  mov     rcx, rbx
0x180007efd  mov     rax, [rax+178h]
0x180007f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f09  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007f10  mov     rax, [rcx]
0x180007f13  mov     rax, [rax+10h]
0x180007f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1c  mov     rbx, [rsp+28h+arg_0]
0x180007f21  mov     eax, edi
0x180007f23  add     rsp, 20h
0x180007f27  pop     rdi
0x180007f28  retn
```
