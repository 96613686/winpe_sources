# std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180010464`
- end: `0x1800104f0`
- name: `??1_Reallocation_guard@?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@QEAA@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e22c`

## callees

- `0x1800022a4`
- `0x180010464`
- `0x180018f38`

## pseudocode

```c
void __fastcall std::vector<winrt::com_ptr<IStream>>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  __int64 *v2; // rsi
  __int64 *i; // rbx
  __int64 v4; // rcx
  void *v5; // rax

  if ( a1[1] )
  {
    v2 = (__int64 *)a1[4];
    for ( i = (__int64 *)a1[3]; i != v2; ++i )
    {
      if ( *i )
        winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(i);
    }
    v4 = a1[1];
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v5 = (void *)a1[1];
    }
    else
    {
      v5 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
}

```

## disassembly

```asm
0x180010464  mov     [rsp+arg_0], rbx
0x180010469  mov     [rsp+arg_8], rsi
0x18001046e  push    rdi
0x18001046f  sub     rsp, 20h
0x180010473  cmp     qword ptr [rcx+8], 0
0x180010478  mov     rdi, rcx
0x18001047b  jz      short loc_1800104E0
0x18001047d  mov     rsi, [rcx+20h]
0x180010481  mov     rbx, [rcx+18h]
0x180010485  jmp     short loc_180010499
0x180010487  cmp     qword ptr [rbx], 0
0x18001048b  jz      short loc_180010495
0x18001048d  mov     rcx, rbx
0x180010490  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180010495  add     rbx, 8
0x180010499  cmp     rbx, rsi
0x18001049c  jnz     short loc_180010487
0x18001049e  mov     rax, [rdi+10h]
0x1800104a2  mov     rcx, [rdi+8]
0x1800104a6  lea     rdx, ds:0[rax*8]
0x1800104ae  cmp     rdx, 1000h
0x1800104b5  jb      short loc_1800104D5
0x1800104b7  mov     rax, [rcx-8]
0x1800104bb  sub     rcx, rax
0x1800104be  sub     rcx, 8
0x1800104c2  cmp     rcx, 1Fh
0x1800104c6  ja      short loc_1800104CE
0x1800104c8  add     rdx, 27h ; '''
0x1800104cc  jmp     short loc_1800104D8
0x1800104ce  mov     ecx, 5
0x1800104d3  int     29h; Win8: RtlFailFast(ecx)
0x1800104d5  mov     rax, rcx
0x1800104d8  mov     rcx, rax; Block
0x1800104db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104e0  mov     rbx, [rsp+28h+arg_0]
0x1800104e5  mov     rsi, [rsp+28h+arg_8]
0x1800104ea  add     rsp, 20h
0x1800104ee  pop     rdi
0x1800104ef  retn
```
