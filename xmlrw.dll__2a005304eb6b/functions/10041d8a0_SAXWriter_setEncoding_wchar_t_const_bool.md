# SAXWriter::setEncoding(wchar_t const *,bool)

- ea: `0x10041d8a0`
- end: `0x10041d94e`
- name: `?setEncoding@SAXWriter@@QEAAXPEB_W_N@Z`
- size: `174`
- prototype: `void __fastcall(SAXWriter *__hidden this, const wchar_t *, bool)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10041cdf0`
- `0x10041d270`
- `0x10041d460`
- `0x10041da70`

## callees

- `0x100401780`
- `0x10041d8a0`
- `0x100420450`
- `0x100439df0`

## pseudocode

```c
void __fastcall SAXWriter::setEncoding(SAXWriter *this, const wchar_t *a2, unsigned __int8 a3)
{
  const wchar_t *v3; // rdi
  const wchar_t *v6; // rax
  __int64 v7; // r9
  int v8; // ecx
  int v9; // edx
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = a2;
  if ( !a2 )
    v3 = CodeStringPtr::utf16;
  v6 = v3;
  v7 = *((_QWORD *)this + 20) - (_QWORD)v3;
  do
  {
    v8 = *(const wchar_t *)((char *)v6 + v7);
    v9 = *v6 - v8;
    if ( v9 )
      break;
    ++v6;
  }
  while ( v8 );
  if ( v9 )
  {
    if ( (unsigned int)CharEncoder::getCharsetInfo(v3, (unsigned int *)this + 22, &v10) == -2 )
    {
      MXRRaiseException(-2147024809);
      JUMPOUT(0x10041D94DLL);
    }
    if ( *((_QWORD *)this + 13) )
    {
      (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 184LL))(this);
      (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)this + 216LL))(this, v3, a3);
    }
  }
}

```

## disassembly

```asm
0x10041d8a0  mov     [rsp+arg_8], rbx
0x10041d8a5  mov     [rsp+arg_10], rsi
0x10041d8aa  push    rdi
0x10041d8ab  sub     rsp, 20h
0x10041d8af  mov     r9, [rcx+0A0h]
0x10041d8b6  test    rdx, rdx
0x10041d8b9  mov     rdi, rdx
0x10041d8bc  movzx   esi, r8b
0x10041d8c0  cmovz   rdi, cs:?utf16@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::utf16
0x10041d8c8  mov     rbx, rcx
0x10041d8cb  mov     rax, rdi
0x10041d8ce  sub     r9, rdi
0x10041d8d1  movzx   edx, word ptr [rax]
0x10041d8d4  movzx   ecx, word ptr [rax+r9]
0x10041d8d9  sub     edx, ecx
0x10041d8db  jnz     short loc_10041D8E5
0x10041d8dd  add     rax, 2
0x10041d8e1  test    ecx, ecx
0x10041d8e3  jnz     short loc_10041D8D1
0x10041d8e5  test    edx, edx
0x10041d8e7  jz      short loc_10041D933
0x10041d8e9  lea     rdx, [rbx+58h]; unsigned int *
0x10041d8ed  mov     rcx, rdi; wchar_t *
0x10041d8f0  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x10041d8f5  call    ?getCharsetInfo@CharEncoder@@SAHPEB_WPEAI1@Z; CharEncoder::getCharsetInfo(wchar_t const *,uint *,uint *)
0x10041d8fa  cmp     eax, 0FFFFFFFEh
0x10041d8fd  jz      short loc_10041D943
0x10041d8ff  cmp     qword ptr [rbx+68h], 0
0x10041d904  jz      short loc_10041D933
0x10041d906  mov     rax, [rbx]
0x10041d909  mov     rcx, rbx
0x10041d90c  mov     rax, [rax+0B8h]
0x10041d913  call    cs:__guard_dispatch_icall_fptr
0x10041d919  mov     rax, [rbx]
0x10041d91c  movzx   r8d, sil
0x10041d920  mov     rdx, rdi
0x10041d923  mov     rcx, rbx
0x10041d926  mov     rax, [rax+0D8h]
0x10041d92d  call    cs:__guard_dispatch_icall_fptr
0x10041d933  mov     rbx, [rsp+28h+arg_8]
0x10041d938  mov     rsi, [rsp+28h+arg_10]
0x10041d93d  add     rsp, 20h
0x10041d941  pop     rdi
0x10041d942  retn
0x10041d943  mov     ecx, 80070057h; int
0x10041d948  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
