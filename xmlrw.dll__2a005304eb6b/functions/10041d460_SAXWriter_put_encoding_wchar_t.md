# SAXWriter::put_encoding(wchar_t *)

- ea: `0x10041d460`
- end: `0x10041d509`
- name: `?put_encoding@SAXWriter@@UEAAJPEA_W@Z`
- size: `169`
- prototype: `int(SAXWriter *__hidden this, wchar_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x100401780`
- `0x10041d130`
- `0x10041d460`
- `0x10041d8a0`
- `0x100420450`
- `0x100423dd0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::put_encoding(SAXWriter *this, wchar_t *a2)
{
  unsigned int v5; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v6; // [rsp+78h] [rbp+20h] BYREF

  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 16LL))((char *)this - 16);
  if ( a2 && *a2 )
  {
    if ( (unsigned int)CharEncoder::getCharsetInfo(a2, &v6, &v5) == -2 )
    {
      MXRRaiseException(-2147024809);
      __debugbreak();
      JUMPOUT(0x10041D509LL);
    }
    SAXWriter::setEncoding((SAXWriter *)((char *)this - 16), a2, *((_BYTE *)this + 210));
    SAXWriter::saveEncoding((SAXWriter *)((char *)this - 16), a2);
  }
  else
  {
    SAXWriter::setEncoding((SAXWriter *)((char *)this - 16), 0, *((_BYTE *)this + 210));
    **((_WORD **)this + 18) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x10041d460  mov     [rsp+arg_0], rbx
0x10041d465  push    rsi
0x10041d466  push    rdi
0x10041d467  push    r14
0x10041d469  sub     rsp, 40h
0x10041d46d  mov     rbx, rdx
0x10041d470  mov     r14, rcx
0x10041d473  xor     edi, edi
0x10041d475  mov     rax, [rcx-10h]
0x10041d479  add     rcx, 0FFFFFFFFFFFFFFF0h
0x10041d47d  mov     rax, [rax+10h]
0x10041d481  call    cs:__guard_dispatch_icall_fptr
0x10041d487  test    rbx, rbx
0x10041d48a  jz      short loc_10041D4CA
0x10041d48c  cmp     [rbx], di
0x10041d48f  jz      short loc_10041D4CA
0x10041d491  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x10041d496  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x10041d49b  mov     rcx, rbx; wchar_t *
0x10041d49e  call    ?getCharsetInfo@CharEncoder@@SAHPEB_WPEAI1@Z; CharEncoder::getCharsetInfo(wchar_t const *,uint *,uint *)
0x10041d4a3  cmp     eax, 0FFFFFFFEh
0x10041d4a6  jz      short loc_10041D4FD
0x10041d4a8  movzx   r8d, byte ptr [r14+0D2h]; bool
0x10041d4b0  mov     rdx, rbx; wchar_t *
0x10041d4b3  lea     rcx, [r14-10h]; this
0x10041d4b7  call    ?setEncoding@SAXWriter@@QEAAXPEB_W_N@Z; SAXWriter::setEncoding(wchar_t const *,bool)
0x10041d4bc  mov     rdx, rbx; wchar_t *
0x10041d4bf  lea     rcx, [r14-10h]; this
0x10041d4c3  call    ?saveEncoding@SAXWriter@@QEAAXPEB_W@Z; SAXWriter::saveEncoding(wchar_t const *)
0x10041d4c8  jmp     short loc_10041D4E7
0x10041d4ca  movzx   r8d, byte ptr [r14+0D2h]; bool
0x10041d4d2  xor     edx, edx; wchar_t *
0x10041d4d4  lea     rcx, [r14-10h]; this
0x10041d4d8  call    ?setEncoding@SAXWriter@@QEAAXPEB_W_N@Z; SAXWriter::setEncoding(wchar_t const *,bool)
0x10041d4dd  mov     rax, [r14+90h]
0x10041d4e4  mov     [rax], di
0x10041d4e7  jmp     short loc_10041D4ED
0x10041d4e9  mov     edi, [rsp+58h+var_38]
0x10041d4ed  mov     eax, edi
0x10041d4ef  mov     rbx, [rsp+58h+arg_0]
0x10041d4f4  add     rsp, 40h
0x10041d4f8  pop     r14
0x10041d4fa  pop     rdi
0x10041d4fb  pop     rsi
0x10041d4fc  retn
0x10041d4fd  mov     ecx, 80070057h; int
0x10041d502  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041d507  nop
0x10041d508  int     3; Trap to Debugger
0x100439f20  push    rbp
0x100439f22  sub     rsp, 20h
0x100439f26  mov     rbp, rdx
0x100439f29  mov     [rbp+38h], rcx
0x100439f2d  mov     [rbp+30h], rcx
0x100439f31  mov     rax, [rbp+30h]
0x100439f35  mov     rcx, [rax]
0x100439f38  mov     [rbp+28h], rcx
0x100439f3c  mov     rax, [rbp+28h]
0x100439f40  mov     eax, [rax]
0x100439f42  cmp     eax, 0C0000005h
0x100439f47  jz      short loc_100439F79
0x100439f49  add     eax, 1FFFFFFFh
0x100439f4e  cmp     eax, 1
0x100439f51  ja      short loc_100439F69
0x100439f53  mov     rax, [rbp+28h]
0x100439f57  cmp     dword ptr [rax+18h], 1
0x100439f5b  jnz     short loc_100439F69
0x100439f5d  mov     rax, [rbp+28h]
0x100439f61  mov     ecx, [rax+20h]
0x100439f64  mov     [rbp+20h], ecx
0x100439f67  jmp     short loc_100439F70
0x100439f69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439f70  mov     dword ptr [rbp+24h], 1
0x100439f77  jmp     short loc_100439F80
0x100439f79  mov     dword ptr [rbp+24h], 0
0x100439f80  mov     eax, [rbp+24h]
0x100439f83  add     rsp, 20h
0x100439f87  pop     rbp
0x100439f88  retn
```
