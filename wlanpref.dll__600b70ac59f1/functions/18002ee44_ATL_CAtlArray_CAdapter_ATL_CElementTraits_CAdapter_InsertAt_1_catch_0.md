# _ATL::CAtlArray_CAdapter_ATL::CElementTraits_CAdapter___::InsertAt_::_1_::catch$0

- ea: `0x18002ee44`
- end: `0x18002ee92`
- name: `_ATL::CAtlArray_CAdapter_ATL::CElementTraits_CAdapter___::InsertAt_::_1_::catch$0`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004c00`
- `0x18002c3ac`
- `0x18002d6dc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002ee6f`
- `msvcrt!memmove_s` at `0x18002ee6f`

## pseudocode

```c
void __fastcall __noreturn ATL::CAtlArray_CAdapter_ATL::CElementTraits_CAdapter___::InsertAt_::_1_::catch_0(
        __int64 a1,
        _QWORD *a2)
{
  void *const *v3; // rbx
  errno_t v4; // eax

  v3 = (void *const *)a2[8];
  v4 = memmove_s(*v3, 32LL * a2[9], (char *)*v3 + 32 * a2[11], 32LL * a2[9]);
  ATL::AtlCrtErrorCheck(v4);
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(v3, a2[9]);
  throw;
}

```

## disassembly

```asm
0x18002ee44  mov     [rsp+arg_8], rdx
0x18002ee49  push    rbx
0x18002ee4a  push    rbp
0x18002ee4b  sub     rsp, 28h
0x18002ee4f  mov     rbp, rdx
0x18002ee52  mov     rdx, [rbp+48h]
0x18002ee56  shl     rdx, 5; DestinationSize
0x18002ee5a  mov     r8, [rbp+58h]
0x18002ee5e  shl     r8, 5
0x18002ee62  mov     rbx, [rbp+40h]
0x18002ee66  add     r8, [rbx]; Source
0x18002ee69  mov     r9, rdx; SourceSize
0x18002ee6c  mov     rcx, [rbx]; Destination
0x18002ee6f  call    cs:__imp_memmove_s
0x18002ee75  mov     ecx, eax; int
0x18002ee77  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002ee7c  mov     rdx, [rbp+48h]
0x18002ee80  mov     rcx, rbx
0x18002ee83  call    ?SetCount@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(unsigned __int64,int)
0x18002ee88  xor     edx, edx; pThrowInfo
0x18002ee8a  xor     ecx, ecx; pExceptionObject
0x18002ee8c  call    _CxxThrowException_0
```
