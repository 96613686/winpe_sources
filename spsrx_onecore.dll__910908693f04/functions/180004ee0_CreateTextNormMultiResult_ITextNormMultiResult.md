# CreateTextNormMultiResult(ITextNormMultiResult * *)

- ea: `0x180004ee0`
- end: `0x180004f55`
- name: `?CreateTextNormMultiResult@@YAJPEAPEAUITextNormMultiResult@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(struct ITextNormMultiResult **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800052f4`

## callees

- `0x180004dd0`
- `0x180004ee0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CreateTextNormMultiResult(struct ITextNormMultiResult **a1)
{
  int Instance; // eax
  struct ITextNormMultiResult *v3; // rbx
  int v4; // edi
  struct ITextNormMultiResult *v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  Instance = ATL::CComObject<CTextNormMultiResult>::CreateInstance((int **)&v6);
  v3 = v6;
  v4 = Instance;
  if ( v6 )
    (*(void (__fastcall **)(struct ITextNormMultiResult *))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v4 < 0 )
  {
    *a1 = 0;
    if ( v3 )
      (*(void (__fastcall **)(struct ITextNormMultiResult *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  else
  {
    *a1 = v3;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004ee0  mov     rax, rsp
0x180004ee3  mov     [rax+8], rbx
0x180004ee7  mov     [rax+18h], rsi
0x180004eeb  push    rdi
0x180004eec  sub     rsp, 20h
0x180004ef0  mov     rsi, rcx
0x180004ef3  mov     qword ptr [rax+10h], 0
0x180004efb  lea     rcx, [rax+10h]
0x180004eff  call    ?CreateInstance@?$CComObject@VCTextNormMultiResult@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CTextNormMultiResult>::CreateInstance(ATL::CComObject<CTextNormMultiResult> * *)
0x180004f04  mov     rbx, [rsp+28h+arg_8]
0x180004f09  mov     edi, eax
0x180004f0b  test    rbx, rbx
0x180004f0e  jz      short loc_180004F1F
0x180004f10  mov     rdx, [rbx]
0x180004f13  mov     rcx, rbx
0x180004f16  mov     rax, [rdx+8]
0x180004f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f1f  test    edi, edi
0x180004f21  js      short loc_180004F28
0x180004f23  mov     [rsi], rbx
0x180004f26  jmp     short loc_180004F43
0x180004f28  mov     qword ptr [rsi], 0
0x180004f2f  test    rbx, rbx
0x180004f32  jz      short loc_180004F43
0x180004f34  mov     rax, [rbx]
0x180004f37  mov     rcx, rbx
0x180004f3a  mov     rax, [rax+10h]
0x180004f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f43  mov     rbx, [rsp+28h+arg_0]
0x180004f48  mov     eax, edi
0x180004f4a  mov     rsi, [rsp+28h+arg_10]
0x180004f4f  add     rsp, 20h
0x180004f53  pop     rdi
0x180004f54  retn
```
