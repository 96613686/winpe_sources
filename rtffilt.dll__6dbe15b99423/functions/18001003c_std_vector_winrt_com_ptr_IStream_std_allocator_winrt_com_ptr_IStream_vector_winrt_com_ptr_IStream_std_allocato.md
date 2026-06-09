# std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>::~vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>(void)

- ea: `0x18001003c`
- end: `0x1800100e2`
- name: `??1?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@QEAA@XZ`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014030`
- `0x180015120`
- `0x18001a757`

## callees

- `0x1800022a4`
- `0x18001003c`
- `0x180018f38`

## pseudocode

```c
void __fastcall std::vector<winrt::com_ptr<IStream>>::~vector<winrt::com_ptr<IStream>>(__int64 a1)
{
  __int64 *v1; // rbx
  __int64 *v3; // rsi
  __int64 *v4; // rcx
  __int64 *v5; // rax

  v1 = *(__int64 **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(__int64 **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v1);
      ++v1;
    }
    v4 = *(__int64 **)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v5 = *(__int64 **)a1;
    }
    else
    {
      v5 = (__int64 *)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001003c  mov     [rsp+arg_0], rbx
0x180010041  mov     [rsp+arg_8], rsi
0x180010046  push    rdi
0x180010047  sub     rsp, 20h
0x18001004b  mov     rbx, [rcx]
0x18001004e  mov     rdi, rcx
0x180010051  test    rbx, rbx
0x180010054  jz      short loc_1800100D2
0x180010056  mov     rsi, [rcx+8]
0x18001005a  jmp     short loc_18001006E
0x18001005c  cmp     qword ptr [rbx], 0
0x180010060  jz      short loc_18001006A
0x180010062  mov     rcx, rbx
0x180010065  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18001006a  add     rbx, 8
0x18001006e  cmp     rbx, rsi
0x180010071  jnz     short loc_18001005C
0x180010073  mov     rcx, [rdi]
0x180010076  mov     rax, [rdi+10h]
0x18001007a  sub     rax, rcx
0x18001007d  sar     rax, 3
0x180010081  lea     rdx, ds:0[rax*8]
0x180010089  cmp     rdx, 1000h
0x180010090  jb      short loc_1800100B0
0x180010092  mov     rax, [rcx-8]
0x180010096  sub     rcx, rax
0x180010099  sub     rcx, 8
0x18001009d  cmp     rcx, 1Fh
0x1800100a1  ja      short loc_1800100A9
0x1800100a3  add     rdx, 27h ; '''
0x1800100a7  jmp     short loc_1800100B3
0x1800100a9  mov     ecx, 5
0x1800100ae  int     29h; Win8: RtlFailFast(ecx)
0x1800100b0  mov     rax, rcx
0x1800100b3  mov     rcx, rax; Block
0x1800100b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800100bb  mov     qword ptr [rdi], 0
0x1800100c2  mov     qword ptr [rdi+8], 0
0x1800100ca  mov     qword ptr [rdi+10h], 0
0x1800100d2  mov     rbx, [rsp+28h+arg_0]
0x1800100d7  mov     rsi, [rsp+28h+arg_8]
0x1800100dc  add     rsp, 20h
0x1800100e0  pop     rdi
0x1800100e1  retn
```
