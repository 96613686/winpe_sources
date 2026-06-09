# SAXWriter::Init(void)

- ea: `0x10041da70`
- end: `0x10041db08`
- name: `?Init@SAXWriter@@MEAAJXZ`
- size: `152`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x10041d090`
- `0x10041d8a0`
- `0x10041da70`
- `0x100423e80`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::Init(SAXWriter *this)
{
  unsigned int v2; // edi
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  v2 = 0;
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 13);
  if ( v3 )
  {
    (**v3)(v3, 1);
    *((_QWORD *)this + 13) = 0;
  }
  if ( !*((_QWORD *)this + 12) )
    SAXWriter::setStream(this, 0);
  if ( !**((_WORD **)this + 20) )
    SAXWriter::setEncoding(this, 0, *((_BYTE *)this + 226));
  (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 24LL))(this);
  if ( !*((_QWORD *)this + 13) )
    return (unsigned int)-2147024882;
  return v2;
}

```

## disassembly

```asm
0x10041da70  mov     [rsp+arg_0], rbx
0x10041da75  push    rdi
0x10041da76  sub     rsp, 50h
0x10041da7a  mov     rbx, rcx
0x10041da7d  xor     edi, edi
0x10041da7f  mov     [rsp+58h+var_30], edi
0x10041da83  mov     rcx, [rcx+68h]
0x10041da87  test    rcx, rcx
0x10041da8a  jz      short loc_10041DA9F
0x10041da8c  mov     rax, [rcx]
0x10041da8f  lea     edx, [rdi+1]
0x10041da92  mov     rax, [rax]
0x10041da95  call    cs:__guard_dispatch_icall_fptr
0x10041da9b  mov     [rbx+68h], rdi
0x10041da9f  cmp     qword ptr [rbx+60h], 0
0x10041daa4  jnz     short loc_10041DAB0
0x10041daa6  xor     edx, edx; struct IStream *
0x10041daa8  mov     rcx, rbx; this
0x10041daab  call    ?setStream@SAXWriter@@QEAAXPEAUIStream@@@Z; SAXWriter::setStream(IStream *)
0x10041dab0  mov     rax, [rbx+0A0h]
0x10041dab7  cmp     word ptr [rax], 0
0x10041dabb  jnz     short loc_10041DACF
0x10041dabd  movzx   r8d, byte ptr [rbx+0E2h]; bool
0x10041dac5  xor     edx, edx; wchar_t *
0x10041dac7  mov     rcx, rbx; this
0x10041daca  call    ?setEncoding@SAXWriter@@QEAAXPEB_W_N@Z; SAXWriter::setEncoding(wchar_t const *,bool)
0x10041dacf  mov     rax, [rbx]
0x10041dad2  mov     rcx, rbx
0x10041dad5  mov     rax, [rax+18h]
0x10041dad9  call    cs:__guard_dispatch_icall_fptr
0x10041dadf  cmp     qword ptr [rbx+68h], 0
0x10041dae4  jnz     short loc_10041DAF1
0x10041dae6  mov     edi, 8007000Eh
0x10041daeb  mov     [rsp+58h+var_30], edi
0x10041daef  jmp     short loc_10041DAFB
0x10041daf1  jmp     short loc_10041DAFB
0x10041daf3  mov     edi, [rsp+58h+var_38]
0x10041daf7  mov     [rsp+58h+var_30], edi
0x10041dafb  mov     eax, edi
0x10041dafd  mov     rbx, [rsp+58h+arg_0]
0x10041db02  add     rsp, 50h
0x10041db06  pop     rdi
0x10041db07  retn
0x10043a070  push    rbp
0x10043a072  sub     rsp, 20h
0x10043a076  mov     rbp, rdx
0x10043a079  mov     [rbp+40h], rcx
0x10043a07d  mov     [rbp+38h], rcx
0x10043a081  mov     rax, [rbp+38h]
0x10043a085  mov     rcx, [rax]
0x10043a088  mov     [rbp+30h], rcx
0x10043a08c  mov     rax, [rbp+30h]
0x10043a090  mov     eax, [rax]
0x10043a092  cmp     eax, 0C0000005h
0x10043a097  jz      short loc_10043A0C9
0x10043a099  add     eax, 1FFFFFFFh
0x10043a09e  cmp     eax, 1
0x10043a0a1  ja      short loc_10043A0B9
0x10043a0a3  mov     rax, [rbp+30h]
0x10043a0a7  cmp     dword ptr [rax+18h], 1
0x10043a0ab  jnz     short loc_10043A0B9
0x10043a0ad  mov     rax, [rbp+30h]
0x10043a0b1  mov     ecx, [rax+20h]
0x10043a0b4  mov     [rbp+20h], ecx
0x10043a0b7  jmp     short loc_10043A0C0
0x10043a0b9  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a0c0  mov     dword ptr [rbp+24h], 1
0x10043a0c7  jmp     short loc_10043A0D0
0x10043a0c9  mov     dword ptr [rbp+24h], 0
0x10043a0d0  mov     eax, [rbp+24h]
0x10043a0d3  add     rsp, 20h
0x10043a0d7  pop     rbp
0x10043a0d8  retn
```
