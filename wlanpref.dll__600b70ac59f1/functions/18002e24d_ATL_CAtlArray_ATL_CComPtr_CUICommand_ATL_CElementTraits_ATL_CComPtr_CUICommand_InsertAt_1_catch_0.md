# _ATL::CAtlArray_ATL::CComPtr_CUICommand__ATL::CElementTraits_ATL::CComPtr_CUICommand_____::InsertAt_::_1_::catch$0

- ea: `0x18002e24d`
- end: `0x18002e29f`
- name: `_ATL::CAtlArray_ATL::CComPtr_CUICommand__ATL::CElementTraits_ATL::CComPtr_CUICommand_____::InsertAt_::_1_::catch$0`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004c00`
- `0x180011418`
- `0x18002d6dc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002e27d`
- `msvcrt!memmove_s` at `0x18002e27d`

## pseudocode

```c
void __fastcall __noreturn ATL::CAtlArray_ATL::CComPtr_CUICommand__ATL::CElementTraits_ATL::CComPtr_CUICommand_____::InsertAt_::_1_::catch_0(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // rdi
  void *const *v3; // rbx
  errno_t v4; // eax

  v2 = a2[9];
  v3 = (void *const *)a2[8];
  v4 = memmove_s(*v3, 8 * v2, (char *)*v3 + 8 * a2[11], 8 * v2);
  ATL::AtlCrtErrorCheck(v4);
  ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(v3, v2);
  throw;
}

```

## disassembly

```asm
0x18002e24d  mov     [rsp+arg_8], rdx
0x18002e252  push    rbx
0x18002e253  push    rbp
0x18002e254  push    rdi
0x18002e255  sub     rsp, 20h
0x18002e259  mov     rbp, rdx
0x18002e25c  mov     rdi, [rbp+48h]
0x18002e260  lea     rdx, ds:0[rdi*8]; DestinationSize
0x18002e268  mov     rbx, [rbp+40h]
0x18002e26c  mov     r8, [rbx]
0x18002e26f  mov     rax, [rbp+58h]
0x18002e273  lea     r8, [r8+rax*8]; Source
0x18002e277  mov     r9, rdx; SourceSize
0x18002e27a  mov     rcx, [rbx]; Destination
0x18002e27d  call    cs:__imp_memmove_s
0x18002e283  mov     ecx, eax; int
0x18002e285  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002e28a  mov     rdx, rdi
0x18002e28d  mov     rcx, rbx
0x18002e290  call    ?SetCount@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(unsigned __int64,int)
0x18002e295  xor     edx, edx; pThrowInfo
0x18002e297  xor     ecx, ecx; pExceptionObject
0x18002e299  call    _CxxThrowException_0
```
