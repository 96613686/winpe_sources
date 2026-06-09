# SAXWriter::newOutputHelper(void)

- ea: `0x10041d960`
- end: `0x10041da5d`
- name: `?newOutputHelper@SAXWriter@@MEAAXXZ`
- size: `253`
- prototype: `void __fastcall(SAXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x100401780`
- `0x10041bf50`
- `0x10041d960`
- `0x100421280`
- `0x100421440`
- `0x100439df0`

## pseudocode

```c
void __fastcall SAXWriter::newOutputHelper(SAXWriter *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  XMLOutputHelper *v3; // rdi
  int v4; // esi
  struct IStream *v5; // r15
  struct IMalloc *v6; // r14
  XMLOutputHelper *v7; // rax
  const wchar_t *v8; // rdx
  const wchar_t *v9; // [rsp+20h] [rbp-58h]
  bool v10; // [rsp+28h] [rbp-50h]

  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 13);
  if ( v2 )
  {
    (**v2)(v2, 1);
    v3 = 0;
    *((_QWORD *)this + 13) = 0;
  }
  else
  {
    v3 = 0;
  }
  v4 = -(*((_BYTE *)this + 217) != 0);
  v5 = (struct IStream *)*((_QWORD *)this + 12);
  v6 = (struct IMalloc *)*((_QWORD *)this + 1);
  v7 = (XMLOutputHelper *)Base::operator new(6424, v6);
  if ( v7 )
    v3 = XMLOutputHelper::XMLOutputHelper(v7, v6, v5, v4 + 2, v9, v10, 0, 0);
  *((_QWORD *)this + 13) = v3;
  if ( v3 )
  {
    v8 = CodeStringPtr::utf16;
    if ( **((_WORD **)this + 20) )
      v8 = (const wchar_t *)*((_QWORD *)this + 20);
    XMLOutputHelper::setEncoding(v3, v8, *((_BYTE *)this + 226));
  }
}

```

## disassembly

```asm
0x10041d960  mov     [rsp+arg_8], rbx
0x10041d965  mov     [rsp+arg_10], rsi
0x10041d96a  mov     [rsp+arg_0], rcx
0x10041d96f  push    rdi
0x10041d970  push    r14
0x10041d972  push    r15
0x10041d974  sub     rsp, 60h
0x10041d978  mov     rbx, rcx
0x10041d97b  mov     rcx, [rcx+68h]
0x10041d97f  test    rcx, rcx
0x10041d982  jz      short loc_10041D99D
0x10041d984  mov     rax, [rcx]
0x10041d987  mov     edx, 1
0x10041d98c  mov     rax, [rax]
0x10041d98f  call    cs:__guard_dispatch_icall_fptr
0x10041d995  xor     edi, edi
0x10041d997  mov     [rbx+68h], rdi
0x10041d99b  jmp     short loc_10041D99F
0x10041d99d  xor     edi, edi
0x10041d99f  movzx   eax, byte ptr [rbx+0D9h]
0x10041d9a6  neg     al
0x10041d9a8  sbb     esi, esi
0x10041d9aa  mov     r15, [rbx+60h]
0x10041d9ae  mov     r14, [rbx+8]
0x10041d9b2  mov     rdx, r14
0x10041d9b5  mov     ecx, 1918h
0x10041d9ba  call    ??2Base@@SAPEAX_KPEAUIMalloc@@W4NewZeroMemoryEnum@@@Z; Base::operator new(unsigned __int64,IMalloc *,NewZeroMemoryEnum)
0x10041d9bf  test    rax, rax
0x10041d9c2  jz      short loc_10041D9E3
0x10041d9c4  mov     [rsp+78h+var_40], 0; bool
0x10041d9c9  mov     [rsp+78h+var_48], 0; bool
0x10041d9ce  lea     r9d, [rsi+2]; int
0x10041d9d2  mov     r8, r15; struct IStream *
0x10041d9d5  mov     rdx, r14; struct IMalloc *
0x10041d9d8  mov     rcx, rax; this
0x10041d9db  call    ??0XMLOutputHelper@@IEAA@PEAUIMalloc@@PEAUIStream@@HPEB_W_N33@Z; XMLOutputHelper::XMLOutputHelper(IMalloc *,IStream *,int,wchar_t const *,bool,bool,bool)
0x10041d9e0  mov     rdi, rax
0x10041d9e3  mov     [rbx+68h], rdi
0x10041d9e7  test    rdi, rdi
0x10041d9ea  jz      short loc_10041DA13
0x10041d9ec  mov     rax, [rbx+0A0h]
0x10041d9f3  mov     rdx, cs:?utf16@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::utf16
0x10041d9fa  cmp     word ptr [rax], 0
0x10041d9fe  cmovnz  rdx, rax; wchar_t *
0x10041da02  movzx   r8d, byte ptr [rbx+0E2h]; bool
0x10041da0a  mov     rcx, rdi; this
0x10041da0d  call    ?setEncoding@XMLOutputHelper@@QEAAXPEB_W_N@Z; XMLOutputHelper::setEncoding(wchar_t const *,bool)
0x10041da12  nop
0x10041da13  lea     r11, [rsp+78h+var_18]
0x10041da18  mov     rbx, [r11+28h]
0x10041da1c  mov     rsi, [r11+30h]
0x10041da20  mov     rsp, r11
0x10041da23  pop     r15
0x10041da25  pop     r14
0x10041da27  pop     rdi
0x10041da28  retn
0x10041da29  mov     rbx, [rsp+78h+arg_0]
0x10041da31  mov     rcx, [rbx+68h]
0x10041da35  test    rcx, rcx
0x10041da38  jz      short loc_10041DA53
0x10041da3a  mov     rax, [rcx]
0x10041da3d  mov     edx, 1
0x10041da42  mov     rax, [rax]
0x10041da45  call    cs:__guard_dispatch_icall_fptr
0x10041da4b  mov     qword ptr [rbx+68h], 0
0x10041da53  mov     ecx, [rsp+78h+var_38]; int
0x10041da57  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041da5c  nop
0x10043a2a0  push    rbp
0x10043a2a2  sub     rsp, 40h
0x10043a2a6  mov     rbp, rdx
0x10043a2a9  mov     [rbp+58h], rcx
0x10043a2ad  mov     [rbp+50h], rcx
0x10043a2b1  mov     rax, [rbp+50h]
0x10043a2b5  mov     rcx, [rax]
0x10043a2b8  mov     [rbp+48h], rcx
0x10043a2bc  mov     rax, [rbp+48h]
0x10043a2c0  mov     eax, [rax]
0x10043a2c2  cmp     eax, 0C0000005h
0x10043a2c7  jz      short loc_10043A2F9
0x10043a2c9  add     eax, 1FFFFFFFh
0x10043a2ce  cmp     eax, 1
0x10043a2d1  ja      short loc_10043A2E9
0x10043a2d3  mov     rax, [rbp+48h]
0x10043a2d7  cmp     dword ptr [rax+18h], 1
0x10043a2db  jnz     short loc_10043A2E9
0x10043a2dd  mov     rax, [rbp+48h]
0x10043a2e1  mov     ecx, [rax+20h]
0x10043a2e4  mov     [rbp+40h], ecx
0x10043a2e7  jmp     short loc_10043A2F0
0x10043a2e9  mov     dword ptr [rbp+40h], 8000FFFFh
0x10043a2f0  mov     dword ptr [rbp+44h], 1
0x10043a2f7  jmp     short loc_10043A300
0x10043a2f9  mov     dword ptr [rbp+44h], 0
0x10043a300  mov     eax, [rbp+44h]
0x10043a303  add     rsp, 40h
0x10043a307  pop     rbp
0x10043a308  retn
```
