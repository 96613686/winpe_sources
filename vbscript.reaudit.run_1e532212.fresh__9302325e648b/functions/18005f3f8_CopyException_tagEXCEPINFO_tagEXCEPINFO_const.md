# CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)

- ea: `0x18005f3f8`
- end: `0x18005f490`
- name: `?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z`
- size: `152`
- prototype: `void __fastcall(struct tagEXCEPINFO *, const struct tagEXCEPINFO *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18003da7c`
- `0x180041fa4`
- `0x180053d90`
- `0x180054480`
- `0x18005f530`
- `0x18005f7c0`
- `0x180066378`

## callees

- `0x180022e44`
- `0x180035154`
- `0x18005f3f8`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18005f434`
- `OLEAUT32!__imp_SysStringLen` at `0x18005f452`
- `OLEAUT32!__imp_SysStringLen` at `0x18005f470`
- `OLEAUT32!__imp_SysStringLen` at `0x18005f434`
- `OLEAUT32!__imp_SysStringLen` at `0x18005f452`
- `OLEAUT32!__imp_SysStringLen` at `0x18005f470`

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
0x18005f3f8  mov     [rsp+arg_0], rbx
0x18005f3fd  push    rdi
0x18005f3fe  sub     rsp, 20h
0x18005f402  mov     rbx, rdx
0x18005f405  mov     rdi, rcx
0x18005f408  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18005f40d  movups  xmm0, xmmword ptr [rbx]
0x18005f410  movups  xmmword ptr [rdi], xmm0
0x18005f413  movups  xmm1, xmmword ptr [rbx+10h]
0x18005f417  movups  xmmword ptr [rdi+10h], xmm1
0x18005f41b  movups  xmm0, xmmword ptr [rbx+20h]
0x18005f41f  movups  xmmword ptr [rdi+20h], xmm0
0x18005f423  movups  xmm1, xmmword ptr [rbx+30h]
0x18005f427  movups  xmmword ptr [rdi+30h], xmm1
0x18005f42b  mov     rcx, [rbx+8]; pbstr
0x18005f42f  test    rcx, rcx
0x18005f432  jz      short loc_18005F449
0x18005f434  call    cs:__imp_SysStringLen
0x18005f43a  mov     rcx, [rbx+8]; unsigned __int16 *
0x18005f43e  mov     edx, eax; unsigned int
0x18005f440  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18005f445  mov     [rdi+8], rax
0x18005f449  mov     rcx, [rbx+10h]; pbstr
0x18005f44d  test    rcx, rcx
0x18005f450  jz      short loc_18005F467
0x18005f452  call    cs:__imp_SysStringLen
0x18005f458  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18005f45c  mov     edx, eax; unsigned int
0x18005f45e  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18005f463  mov     [rdi+10h], rax
0x18005f467  mov     rcx, [rbx+18h]; pbstr
0x18005f46b  test    rcx, rcx
0x18005f46e  jz      short loc_18005F485
0x18005f470  call    cs:__imp_SysStringLen
0x18005f476  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18005f47a  mov     edx, eax; unsigned int
0x18005f47c  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18005f481  mov     [rdi+18h], rax
0x18005f485  mov     rbx, [rsp+28h+arg_0]
0x18005f48a  add     rsp, 20h
0x18005f48e  pop     rdi
0x18005f48f  retn
```
