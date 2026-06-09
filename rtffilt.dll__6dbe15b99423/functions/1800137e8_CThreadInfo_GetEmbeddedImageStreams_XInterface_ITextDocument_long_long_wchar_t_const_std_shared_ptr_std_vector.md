# CThreadInfo::GetEmbeddedImageStreams(XInterface<ITextDocument> &,long,long,wchar_t const *,std::shared_ptr<std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>>)

- ea: `0x1800137e8`
- end: `0x180013a16`
- name: `?GetEmbeddedImageStreams@CThreadInfo@@AEAAJAEAV?$XInterface@UITextDocument@@@@JJPEB_WV?$shared_ptr@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int, int, _WORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011994`

## callees

- `0x18000e22c`
- `0x1800137e8`
- `0x180018f38`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CThreadInfo::GetEmbeddedImageStreams(__int64 a1, _QWORD *a2, int a3, int a4, _WORD *a5, _QWORD *a6)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  _WORD *v10; // r14
  int v11; // esi
  int i; // r15d
  __int64 v13; // rbx
  _QWORD *v14; // rdx
  __int64 v15; // rcx
  volatile signed __int32 *v16; // rdi
  volatile signed __int32 *v18; // rdi
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h] BYREF
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF
  _QWORD *v22; // [rsp+88h] [rbp+48h]

  v22 = a2;
  v21 = a1;
  v8 = a2;
  v9 = a6;
  v10 = a5;
  if ( a5 && *a6 )
  {
    v11 = 0;
    for ( i = 0; i < a4; ++v10 )
    {
      if ( *v10 == 0xFFFC )
      {
        a5 = 0;
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD **))(*(_QWORD *)*v8 + 192LL))(
                *v8,
                (unsigned int)(i + a3),
                (unsigned int)(i + a3 + 1),
                &a5);
        if ( v11 >= 0 )
        {
          v19 = 0;
          v11 = (*(__int64 (__fastcall **)(_WORD *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a5 + 456LL))(
                  a5,
                  &v19);
          if ( v11 >= 0 )
          {
            v20 = 0;
            v11 = (**v19)(v19, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v20);
            if ( v11 >= 0 )
            {
              if ( v20 )
              {
                v21 = 0;
                v11 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v20 + 24LL))(
                        v20,
                        &GUID_NULL,
                        &GUID_0000000c_0000_0000_c000_000000000046,
                        &v21);
                if ( v11 >= 0 && v21 )
                {
                  v13 = *v9;
                  v14 = *(_QWORD **)(*v9 + 8LL);
                  if ( v14 == *(_QWORD **)(*v9 + 16LL) )
                  {
                    std::vector<winrt::com_ptr<IStream>>::_Emplace_reallocate<winrt::com_ptr<IStream> const &>(
                      *v9,
                      v14,
                      &v21);
                  }
                  else
                  {
                    *v14 = v21;
                    if ( v21 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
                    *(_QWORD *)(v13 + 8) += 8LL;
                  }
                }
                if ( v21 )
                  winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v21);
              }
            }
          }
        }
        v15 = (__int64)a5;
        a5 = 0;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v8 = v22;
      }
      ++i;
    }
    v16 = (volatile signed __int32 *)v9[1];
    if ( v16 && _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    return (unsigned int)v11;
  }
  else
  {
    v18 = (volatile signed __int32 *)a6[1];
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    return 2147751683LL;
  }
}

```

## disassembly

```asm
0x1800137e8  mov     [rsp-38h+arg_10], rbx
0x1800137ed  mov     [rsp-38h+arg_8], rdx
0x1800137f2  mov     [rsp-38h+arg_0], rcx
0x1800137f7  push    rbp
0x1800137f8  push    rsi
0x1800137f9  push    rdi
0x1800137fa  push    r12
0x1800137fc  push    r13
0x1800137fe  push    r14
0x180013800  push    r15
0x180013802  mov     rbp, rsp
0x180013805  sub     rsp, 40h
0x180013809  mov     r12d, r9d
0x18001380c  mov     r13d, r8d
0x18001380f  mov     rax, rdx
0x180013812  mov     rdi, [rbp+arg_28]
0x180013816  mov     r14, [rbp+arg_20]
0x18001381a  xor     ebx, ebx
0x18001381c  test    r14, r14
0x18001381f  jz      loc_1800139BA
0x180013825  cmp     [rdi], rbx
0x180013828  jz      loc_1800139BA
0x18001382e  mov     esi, ebx
0x180013830  mov     r15d, ebx
0x180013833  test    r9d, r9d
0x180013836  jle     loc_180013977
0x18001383c  mov     ecx, 0FFFCh
0x180013841  cmp     [r14], cx
0x180013845  jnz     loc_180013967
0x18001384b  mov     [rbp+arg_20], rbx
0x18001384f  mov     rcx, [rax]
0x180013852  lea     edx, [r15+r13]
0x180013856  mov     rax, [rcx]
0x180013859  lea     r8d, [rdx+1]
0x18001385d  lea     r9, [rbp+arg_20]
0x180013861  mov     rax, [rax+0C0h]
0x180013868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001386d  mov     esi, eax
0x18001386f  test    eax, eax
0x180013871  js      loc_180013949
0x180013877  mov     [rbp+var_10], rbx
0x18001387b  mov     rcx, [rbp+arg_20]
0x18001387f  mov     rax, [rcx]
0x180013882  lea     rdx, [rbp+var_10]
0x180013886  mov     rax, [rax+1C8h]
0x18001388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013892  mov     esi, eax
0x180013894  test    eax, eax
0x180013896  js      loc_180013949
0x18001389c  mov     [rbp+var_8], rbx
0x1800138a0  mov     rcx, [rbp+var_10]
0x1800138a4  mov     rax, [rcx]
0x1800138a7  lea     r8, [rbp+var_8]
0x1800138ab  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1800138b2  mov     rax, [rax]
0x1800138b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ba  mov     esi, eax
0x1800138bc  test    eax, eax
0x1800138be  js      loc_180013949
0x1800138c4  mov     rcx, [rbp+var_8]
0x1800138c8  test    rcx, rcx
0x1800138cb  jz      short loc_180013949
0x1800138cd  mov     [rbp+arg_0], rbx
0x1800138d1  mov     rax, [rcx]
0x1800138d4  lea     r9, [rbp+arg_0]
0x1800138d8  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x1800138df  lea     rdx, GUID_NULL
0x1800138e6  mov     rax, [rax+18h]
0x1800138ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ef  mov     esi, eax
0x1800138f1  test    eax, eax
0x1800138f3  js      short loc_180013939
0x1800138f5  mov     rax, [rbp+arg_0]
0x1800138f9  test    rax, rax
0x1800138fc  jz      short loc_180013939
0x1800138fe  mov     rbx, [rdi]
0x180013901  mov     rdx, [rbx+8]
0x180013905  cmp     rdx, [rbx+10h]
0x180013909  jz      short loc_18001392B
0x18001390b  mov     [rdx], rax
0x18001390e  mov     rcx, [rbp+arg_0]
0x180013912  test    rcx, rcx
0x180013915  jz      short loc_180013924
0x180013917  mov     rax, [rcx]
0x18001391a  mov     rax, [rax+8]
0x18001391e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013923  nop
0x180013924  add     qword ptr [rbx+8], 8
0x180013929  jmp     short loc_180013937
0x18001392b  lea     r8, [rbp+arg_0]
0x18001392f  mov     rcx, rbx
0x180013932  call    ??$_Emplace_reallocate@AEBU?$com_ptr@UIStream@@@winrt@@@?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@AEAAPEAU?$com_ptr@UIStream@@@winrt@@QEAU23@AEBU23@@Z; std::vector<winrt::com_ptr<IStream>>::_Emplace_reallocate<winrt::com_ptr<IStream> const &>(winrt::com_ptr<IStream> * const,winrt::com_ptr<IStream> const &)
0x180013937  xor     ebx, ebx
0x180013939  cmp     [rbp+arg_0], rbx
0x18001393d  jz      short loc_180013949
0x18001393f  lea     rcx, [rbp+arg_0]
0x180013943  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180013948  nop
0x180013949  mov     rcx, [rbp+arg_20]
0x18001394d  mov     [rbp+arg_20], rbx
0x180013951  test    rcx, rcx
0x180013954  jz      short loc_180013963
0x180013956  mov     rax, [rcx]
0x180013959  mov     rax, [rax+10h]
0x18001395d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013962  nop
0x180013963  mov     rax, [rbp+arg_8]
0x180013967  inc     r15d
0x18001396a  add     r14, 2
0x18001396e  cmp     r15d, r12d
0x180013971  jl      loc_18001383C
0x180013977  mov     rdi, [rdi+8]
0x18001397b  test    rdi, rdi
0x18001397e  jz      short loc_1800139B6
0x180013980  or      ebx, 0FFFFFFFFh
0x180013983  mov     eax, ebx
0x180013985  lock xadd [rdi+8], eax
0x18001398a  add     eax, ebx
0x18001398c  jnz     short loc_1800139B6
0x18001398e  mov     rax, [rdi]
0x180013991  mov     rcx, rdi
0x180013994  mov     rax, [rax]
0x180013997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001399c  mov     eax, ebx
0x18001399e  lock xadd [rdi+0Ch], eax
0x1800139a3  add     eax, ebx
0x1800139a5  jnz     short loc_1800139B6
0x1800139a7  mov     rax, [rdi]
0x1800139aa  mov     rcx, rdi
0x1800139ad  mov     rax, [rax+8]
0x1800139b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139b6  mov     eax, esi
0x1800139b8  jmp     short loc_1800139FE
0x1800139ba  mov     rdi, [rdi+8]
0x1800139be  test    rdi, rdi
0x1800139c1  jz      short loc_1800139F9
0x1800139c3  or      ebx, 0FFFFFFFFh
0x1800139c6  mov     eax, ebx
0x1800139c8  lock xadd [rdi+8], eax
0x1800139cd  add     eax, ebx
0x1800139cf  jnz     short loc_1800139F9
0x1800139d1  mov     rax, [rdi]
0x1800139d4  mov     rcx, rdi
0x1800139d7  mov     rax, [rax]
0x1800139da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139df  mov     eax, ebx
0x1800139e1  lock xadd [rdi+0Ch], eax
0x1800139e6  add     eax, ebx
0x1800139e8  jnz     short loc_1800139F9
0x1800139ea  mov     rax, [rdi]
0x1800139ed  mov     rcx, rdi
0x1800139f0  mov     rax, [rax+8]
0x1800139f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139f9  mov     eax, 80041703h
0x1800139fe  mov     rbx, [rsp+40h+arg_10]
0x180013a06  add     rsp, 40h
0x180013a0a  pop     r15
0x180013a0c  pop     r14
0x180013a0e  pop     r13
0x180013a10  pop     r12
0x180013a12  pop     rdi
0x180013a13  pop     rsi
0x180013a14  pop     rbp
0x180013a15  retn
```
