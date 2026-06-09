# CSrmFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x180017ad0`
- end: `0x180017bc2`
- name: `?HandleComException@CSrmFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z`
- size: `242`
- prototype: `void __fastcall __noreturn(CSrmFunctionTracer *__hidden this, struct _com_error *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `18`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b9d1`
- `0x18001bb81`
- `0x18001c33a`
- `0x18001c544`
- `0x18001c908`
- `0x18001ca88`
- `0x18001cc08`
- `0x18001ce04`
- `0x18001cfde`
- `0x18001d34a`
- `0x18001d559`
- `0x18001d736`
- `0x18001d8da`
- `0x18001da54`
- `0x18001ddec`
- `0x18001dfb4`
- `0x18001edcb`
- `0x18001f0d1`

## callees

- `0x1800193ec`
- `0x180019850`
- `0x18001b3ee`

## string_xrefs

- `0x180017b41`: `Unexpected COM exception caught: hr: 0x%x`
- `0x180017b9a`: `COM error caught: hr: 0x%x`

## pseudocode

```c
void __fastcall __noreturn CSrmFunctionTracer::HandleComException(
        CSrmFunctionTracer *this,
        struct _com_error *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v8; // ebx
  _QWORD v9[3]; // [rsp+20h] [rbp-91h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-79h]
  unsigned int v11; // [rsp+3Ch] [rbp-75h]
  int v12; // [rsp+40h] [rbp-71h]
  _BYTE v13[96]; // [rsp+48h] [rbp-69h] BYREF
  int v14; // [rsp+A8h] [rbp-9h]

  v8 = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 2) = v8;
  v9[0] = a3;
  v9[1] = a5;
  v9[2] = a4;
  v10 = a6;
  v11 = a7;
  v12 = 255;
  v14 = 0x1000000;
  memset_0(v13, 0, sizeof(v13));
  CSrmFunctionTracer::TranslateComErrorNoThrow(this, v9, L"Unexpected COM exception caught: hr: 0x%x", v8);
}

```

## disassembly

```asm
0x180017ad0  push    rbp
0x180017ad2  push    rbx
0x180017ad3  push    rsi
0x180017ad4  push    rdi
0x180017ad5  push    r12
0x180017ad7  push    r13
0x180017ad9  push    r14
0x180017adb  push    r15
0x180017add  lea     rbp, [rsp-7]
0x180017ae2  sub     rsp, 0B8h
0x180017ae9  mov     r12, r9
0x180017aec  mov     r15, r8
0x180017aef  mov     r13, rcx
0x180017af2  mov     ebx, [rdx+8]
0x180017af5  mov     [rcx+8], ebx
0x180017af8  lea     rax, [rsp+0F0h+var_D0]
0x180017afd  mov     [rbp+3Fh+arg_0], rax
0x180017b01  mov     [rsp+0F0h+var_D0], r8
0x180017b06  mov     r14, [rbp+3Fh+arg_20]
0x180017b0a  mov     [rsp+0F0h+var_C8], r14
0x180017b0f  mov     [rsp+0F0h+var_C0], r9
0x180017b14  mov     esi, [rbp+3Fh+arg_28]
0x180017b17  mov     [rbp+3Fh+var_B8], esi
0x180017b1a  mov     edi, [rbp+3Fh+arg_30]
0x180017b1d  mov     [rbp+3Fh+var_B4], edi
0x180017b20  mov     [rbp+3Fh+var_B0], 0FFh
0x180017b27  mov     [rbp+3Fh+var_48], 1000000h
0x180017b2e  xor     edx, edx; Val
0x180017b30  lea     r8d, [rdx+60h]; Size
0x180017b34  lea     rcx, [rbp+3Fh+var_A8]; void *
0x180017b38  call    memset_0
0x180017b3d  nop
0x180017b3e  mov     r9d, ebx
0x180017b41  lea     r8, aUnexpectedComE; "Unexpected COM exception caught: hr: 0x"...
0x180017b48  lea     rdx, [rsp+0F0h+var_D0]
0x180017b4d  mov     rcx, r13
0x180017b50  call    ?TranslateComErrorNoThrow@CSrmFunctionTracer@@QEAAJUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateComErrorNoThrow(CSrmDebugInfo,ushort const *,...)
0x180017b55  mov     ebx, eax
0x180017b57  mov     [r13+8], eax
0x180017b5b  lea     rax, [rsp+0F0h+var_D0]
0x180017b60  mov     [rbp+3Fh+arg_20], rax
0x180017b64  mov     [rsp+0F0h+var_D0], r15
0x180017b69  mov     [rsp+0F0h+var_C8], r14
0x180017b6e  mov     [rsp+0F0h+var_C0], r12
0x180017b73  mov     [rbp+3Fh+var_B8], esi
0x180017b76  mov     [rbp+3Fh+var_B4], edi
0x180017b79  mov     [rbp+3Fh+var_B0], 0FFh
0x180017b80  mov     [rbp+3Fh+var_48], 1000000h
0x180017b87  xor     edx, edx; Val
0x180017b89  lea     r8d, [rdx+60h]; Size
0x180017b8d  lea     rcx, [rbp+3Fh+var_A8]; void *
0x180017b91  call    memset_0
0x180017b96  nop
0x180017b97  mov     r9d, ebx
0x180017b9a  lea     r8, aComErrorCaught; "COM error caught: hr: 0x%x"
0x180017ba1  lea     rdx, [rsp+0F0h+var_D0]
0x180017ba6  mov     rcx, r13
0x180017ba9  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180017bae  add     rsp, 0B8h
0x180017bb5  pop     r15
0x180017bb7  pop     r14
0x180017bb9  pop     r13
0x180017bbb  pop     r12
0x180017bbd  pop     rdi
0x180017bbe  pop     rsi
0x180017bbf  pop     rbx
0x180017bc0  pop     rbp
0x180017bc1  retn
```
