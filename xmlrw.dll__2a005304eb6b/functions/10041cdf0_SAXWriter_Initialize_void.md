# SAXWriter::Initialize(void)

- ea: `0x10041cdf0`
- end: `0x10041ce93`
- name: `?Initialize@SAXWriter@@IEAAXXZ`
- size: `163`
- prototype: `void __fastcall(SAXWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10041cae0`

## callees

- `0x10041cdf0`
- `0x10041d8a0`
- `0x100439df0`

## pseudocode

```c
void __fastcall SAXWriter::Initialize(SAXWriter *this)
{
  __int64 v2; // rdi
  __int64 v3; // rsi

  v2 = *((_QWORD *)this + 12);
  if ( *((_QWORD *)this + 13) )
    (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 184LL))(this);
  v3 = *((_QWORD *)this + 12);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  *((_QWORD *)this + 12) = v2;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *((_QWORD *)this + 13) )
    (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)this + 208LL))(this, *((_QWORD *)this + 12));
  SAXWriter::setEncoding(this, *((const wchar_t **)this + 20), *((_BYTE *)this + 226));
}

```

## disassembly

```asm
0x10041cdf0  mov     [rsp+arg_0], rbx
0x10041cdf5  mov     [rsp+arg_8], rsi
0x10041cdfa  push    rdi
0x10041cdfb  sub     rsp, 20h
0x10041cdff  cmp     qword ptr [rcx+68h], 0
0x10041ce04  mov     rbx, rcx
0x10041ce07  mov     rdi, [rcx+60h]
0x10041ce0b  jz      short loc_10041CE1D
0x10041ce0d  mov     rax, [rcx]
0x10041ce10  mov     rax, [rax+0B8h]
0x10041ce17  call    cs:__guard_dispatch_icall_fptr
0x10041ce1d  mov     rsi, [rbx+60h]
0x10041ce21  test    rdi, rdi
0x10041ce24  jz      short loc_10041CE36
0x10041ce26  mov     rax, [rdi]
0x10041ce29  mov     rcx, rdi
0x10041ce2c  mov     rax, [rax+8]
0x10041ce30  call    cs:__guard_dispatch_icall_fptr
0x10041ce36  mov     [rbx+60h], rdi
0x10041ce3a  test    rsi, rsi
0x10041ce3d  jz      short loc_10041CE4F
0x10041ce3f  mov     rax, [rsi]
0x10041ce42  mov     rcx, rsi
0x10041ce45  mov     rax, [rax+10h]
0x10041ce49  call    cs:__guard_dispatch_icall_fptr
0x10041ce4f  cmp     qword ptr [rbx+68h], 0
0x10041ce54  jz      short loc_10041CE6D
0x10041ce56  mov     rax, [rbx]
0x10041ce59  mov     rcx, rbx
0x10041ce5c  mov     rdx, [rbx+60h]
0x10041ce60  mov     rax, [rax+0D0h]
0x10041ce67  call    cs:__guard_dispatch_icall_fptr
0x10041ce6d  movzx   r8d, byte ptr [rbx+0E2h]; bool
0x10041ce75  mov     rcx, rbx; this
0x10041ce78  mov     rdx, [rbx+0A0h]; wchar_t *
0x10041ce7f  mov     rbx, [rsp+28h+arg_0]
0x10041ce84  mov     rsi, [rsp+28h+arg_8]
0x10041ce89  add     rsp, 20h
0x10041ce8d  pop     rdi
0x10041ce8e  jmp     ?setEncoding@SAXWriter@@QEAAXPEB_W_N@Z; SAXWriter::setEncoding(wchar_t const *,bool)
```
