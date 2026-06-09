# CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)

- ea: `0x180061068`
- end: `0x180061113`
- name: `?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z`
- size: `171`
- prototype: `void __fastcall(struct tagEXCEPINFO *, const struct tagEXCEPINFO *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18003ecec`
- `0x1800435f4`
- `0x180055660`
- `0x180055d80`
- `0x1800611b8`
- `0x180061440`
- `0x180068258`

## callees

- `0x180011650`
- `0x18001e32c`
- `0x180061068`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800610a4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800610c8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800610ec`
- `OLEAUT32!__imp_SysStringLen` at `0x1800610a4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800610c8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800610ec`

## pseudocode

```c
void __fastcall CopyException(struct tagEXCEPINFO *a1, const struct tagEXCEPINFO *a2)
{
  OLECHAR *bstrSource; // rcx
  UINT v5; // eax
  OLECHAR *bstrDescription; // rcx
  UINT v7; // eax
  OLECHAR *bstrHelpFile; // rcx
  UINT v9; // eax

  FreeExcepInfo(a1);
  *a1 = *a2;
  bstrSource = a2->bstrSource;
  if ( bstrSource )
  {
    v5 = SysStringLen(bstrSource);
    a1->bstrSource = _SysAllocStringLen(a2->bstrSource, v5);
  }
  bstrDescription = a2->bstrDescription;
  if ( bstrDescription )
  {
    v7 = SysStringLen(bstrDescription);
    a1->bstrDescription = _SysAllocStringLen(a2->bstrDescription, v7);
  }
  bstrHelpFile = a2->bstrHelpFile;
  if ( bstrHelpFile )
  {
    v9 = SysStringLen(bstrHelpFile);
    a1->bstrHelpFile = _SysAllocStringLen(a2->bstrHelpFile, v9);
  }
}

```

## disassembly

```asm
0x180061068  mov     [rsp+arg_0], rbx
0x18006106d  push    rdi
0x18006106e  sub     rsp, 20h
0x180061072  mov     rbx, rdx
0x180061075  mov     rdi, rcx
0x180061078  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18006107d  movups  xmm0, xmmword ptr [rbx]
0x180061080  movups  xmmword ptr [rdi], xmm0
0x180061083  movups  xmm1, xmmword ptr [rbx+10h]
0x180061087  movups  xmmword ptr [rdi+10h], xmm1
0x18006108b  movups  xmm0, xmmword ptr [rbx+20h]
0x18006108f  movups  xmmword ptr [rdi+20h], xmm0
0x180061093  movups  xmm1, xmmword ptr [rbx+30h]
0x180061097  movups  xmmword ptr [rdi+30h], xmm1
0x18006109b  mov     rcx, [rbx+8]; pbstr
0x18006109f  test    rcx, rcx
0x1800610a2  jz      short loc_1800610BF
0x1800610a4  call    cs:__imp_SysStringLen
0x1800610ab  nop     dword ptr [rax+rax+00h]
0x1800610b0  mov     rcx, [rbx+8]; unsigned __int16 *
0x1800610b4  mov     edx, eax; unsigned int
0x1800610b6  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800610bb  mov     [rdi+8], rax
0x1800610bf  mov     rcx, [rbx+10h]; pbstr
0x1800610c3  test    rcx, rcx
0x1800610c6  jz      short loc_1800610E3
0x1800610c8  call    cs:__imp_SysStringLen
0x1800610cf  nop     dword ptr [rax+rax+00h]
0x1800610d4  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800610d8  mov     edx, eax; unsigned int
0x1800610da  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800610df  mov     [rdi+10h], rax
0x1800610e3  mov     rcx, [rbx+18h]; pbstr
0x1800610e7  test    rcx, rcx
0x1800610ea  jz      short loc_180061107
0x1800610ec  call    cs:__imp_SysStringLen
0x1800610f3  nop     dword ptr [rax+rax+00h]
0x1800610f8  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1800610fc  mov     edx, eax; unsigned int
0x1800610fe  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180061103  mov     [rdi+18h], rax
0x180061107  mov     rbx, [rsp+28h+arg_0]
0x18006110c  add     rsp, 20h
0x180061110  pop     rdi
0x180061111  retn
```
