# CWmpDecoderFrame::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x1800317f0`
- end: `0x18003183f`
- name: `?CopyPixels@CWmpDecoderFrame@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `79`
- prototype: `int(CWmpDecoderFrame *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180031850`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::CopyPixels(
        CWmpDecoderFrame *this,
        const struct WICRect *a2,
        unsigned int a3,
        UINT a4,
        unsigned __int8 *a5)
{
  return CWmpDecoderFrame::CopyPixels(
           (CWmpDecoderFrame *)((char *)this + 8),
           a2,
           *((_DWORD *)this - 16555),
           *((_DWORD *)this - 16554),
           (struct _GUID *)((char *)this - 66296),
           WICBitmapTransformRotate0,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x1800317f0  sub     rsp, 58h
0x1800317f4  mov     rax, [rsp+58h+arg_20]
0x1800317fc  lea     r10, [rcx-102F8h]
0x180031803  mov     [rsp+58h+var_18], rax; unsigned __int8 *
0x180031808  mov     r11, rcx
0x18003180b  mov     [rsp+58h+var_20], r9d; unsigned int
0x180031810  add     rcx, 8; this
0x180031814  mov     [rsp+58h+var_28], r8d; unsigned int
0x180031819  mov     [rsp+58h+var_30], 0; WICBitmapTransformOptions
0x180031821  mov     r9d, [r11-102A8h]; unsigned int
0x180031828  mov     r8d, [r11-102ACh]; unsigned int
0x18003182f  mov     [rsp+58h+var_38], r10; struct _GUID *
0x180031834  call    ?CopyPixels@CWmpDecoderFrame@@UEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z; CWmpDecoderFrame::CopyPixels(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)
0x180031839  add     rsp, 58h
0x18003183d  retn
```
