# CLogConfigurableFilter::Init(void *,ILogContext *)

- ea: `0x180025ae0`
- end: `0x180025b2e`
- name: `?Init@CLogConfigurableFilter@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180025a4c`
- `0x180025ae0`
- `0x180026110`

## pseudocode

```c
_BOOL8 __fastcall CLogConfigurableFilter::Init(CLogConfigurableFilter *a1, wchar_t **a2, struct ILogContext *a3)
{
  wchar_t *v5; // rbx

  if ( !a2 )
    return 0;
  v5 = *a2;
  CLogConfigurableFilter::DestroyRules(a1);
  return (unsigned int)CLogConfigurableFilter::SimpleConfigParser(a1, v5, a3) != 0;
}

```

## disassembly

```asm
0x180025ae0  mov     [rsp+arg_0], rbx
0x180025ae5  mov     [rsp+arg_8], rsi
0x180025aea  push    rdi
0x180025aeb  sub     rsp, 20h
0x180025aef  mov     rsi, r8
0x180025af2  mov     rdi, rcx
0x180025af5  test    rdx, rdx
0x180025af8  jz      short loc_180025B1B
0x180025afa  mov     rbx, [rdx]
0x180025afd  call    ?DestroyRules@CLogConfigurableFilter@@IEAAXXZ; CLogConfigurableFilter::DestroyRules(void)
0x180025b02  mov     r8, rsi; struct ILogContext *
0x180025b05  mov     rdx, rbx; FileName
0x180025b08  mov     rcx, rdi; this
0x180025b0b  call    ?SimpleConfigParser@CLogConfigurableFilter@@IEAAHPEBGPEAVILogContext@@@Z; CLogConfigurableFilter::SimpleConfigParser(ushort const *,ILogContext *)
0x180025b10  xor     ecx, ecx
0x180025b12  test    eax, eax
0x180025b14  setnz   cl
0x180025b17  mov     eax, ecx
0x180025b19  jmp     short loc_180025B1D
0x180025b1b  xor     eax, eax
0x180025b1d  mov     rbx, [rsp+28h+arg_0]
0x180025b22  mov     rsi, [rsp+28h+arg_8]
0x180025b27  add     rsp, 20h
0x180025b2b  pop     rdi
0x180025b2c  retn
```
