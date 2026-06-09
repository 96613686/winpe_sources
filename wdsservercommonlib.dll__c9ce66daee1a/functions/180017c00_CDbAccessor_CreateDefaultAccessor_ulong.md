# CDbAccessor::CreateDefaultAccessor(ulong)

- ea: `0x180017c00`
- end: `0x180017e48`
- name: `?CreateDefaultAccessor@CDbAccessor@@QEAAJK@Z`
- size: `584`
- prototype: `__int64 __fastcall(CDbAccessor *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x18000179c`
- `0x180017970`
- `0x180017c00`
- `0x18002e468`
- `0x18002f3ba`
- `0x180030010`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x180017e12`
- `OLE32!CoTaskMemFree` at `0x180017e2c`
- `OLE32!CoTaskMemFree` at `0x180017e12`
- `OLE32!CoTaskMemFree` at `0x180017e2c`

## pseudocode

```c
__int64 __fastcall CDbAccessor::CreateDefaultAccessor(CDbAccessor *this, unsigned int a2)
{
  int Accessor; // edi
  void *v5; // rcx
  void *v6; // rcx
  unsigned __int64 v7; // rax
  void *v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r10
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 i; // r8
  __int64 v14; // rax
  __int64 v15; // rdx
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int64 v18; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v19; // [rsp+68h] [rbp+38h] BYREF

  v18 = 0;
  pv = 0;
  v19 = 0;
  Accessor = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *, LPVOID *, LPVOID *))(**((_QWORD **)this + 1) + 24LL))(
               *((_QWORD *)this + 1),
               &v18,
               &pv,
               &v19);
  if ( Accessor >= 0 )
  {
    if ( v18 )
    {
      v5 = (void *)*((_QWORD *)this + 2);
      if ( v5 )
      {
        operator delete(v5);
        *((_QWORD *)this + 2) = 0;
      }
      *((_DWORD *)this + 6) = 0;
      v6 = (void *)*((_QWORD *)this + 4);
      if ( v6 )
      {
        operator delete(v6);
        *((_QWORD *)this + 4) = 0;
      }
      *((_DWORD *)this + 10) = 0;
      v7 = 88 * v18;
      if ( !is_mul_ok(v18, 0x58u) )
        v7 = -1;
      v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 2) = v8;
      if ( v8 )
      {
        memset_0(v8, 0, 88 * v18);
        v9 = v18;
        v10 = 0;
        if ( v18 )
        {
          v11 = 0;
          do
          {
            v12 = *(_QWORD *)((char *)pv + v11 + 16);
            if ( v12 )
            {
              *(_QWORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2)) = v12;
              *(_WORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2) + 84) = *(_WORD *)((char *)pv + v11 + 40);
              for ( i = 0; i < 2; ++i )
                *(_BYTE *)(*((_QWORD *)this + 2) + 88LL * *((unsigned int *)this + 6) + i + 86) = *((_BYTE *)pv
                                                                                                  + v11
                                                                                                  + i
                                                                                                  + 42);
              *(_QWORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2) + 72) = *(_QWORD *)((char *)pv + v11 + 32);
              *(_DWORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2) + 60) = 0;
              *(_DWORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2) + 64) = 0;
              *(_DWORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2) + 56) = 7;
              *(_QWORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2) + 16) = *((unsigned int *)this + 10);
              *((_DWORD *)this + 10) += 8;
              *(_QWORD *)(88LL * *((unsigned int *)this + 6) + *((_QWORD *)this + 2) + 24) = *((unsigned int *)this + 10);
              v14 = *((unsigned int *)this + 6);
              *((_DWORD *)this + 10) += 4;
              *(_QWORD *)(88 * v14 + *((_QWORD *)this + 2) + 8) = *((unsigned int *)this + 10);
              v15 = *((unsigned int *)this + 6);
              *((_DWORD *)this + 10) += *(_DWORD *)(88 * v15 + *((_QWORD *)this + 2) + 72);
              v9 = v18;
              *((_DWORD *)this + 6) = v15 + 1;
            }
            ++v10;
            v11 += 80;
          }
          while ( v10 < v9 );
        }
        Accessor = CDbAccessor::CreateAccessor(this, a2);
      }
      else
      {
        Accessor = -2147024882;
      }
    }
    else
    {
      Accessor = -2147024637;
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v19 )
    CoTaskMemFree(v19);
  return (unsigned int)Accessor;
}

```

## disassembly

```asm
0x180017c00  mov     [rsp-18h+arg_8], rbx
0x180017c05  push    rbp
0x180017c06  push    rsi
0x180017c07  push    rdi
0x180017c08  mov     rbp, rsp
0x180017c0b  sub     rsp, 30h
0x180017c0f  and     [rbp+arg_10], 0
0x180017c14  lea     r9, [rbp+arg_18]
0x180017c18  and     [rbp+pv], 0
0x180017c1d  lea     r8, [rbp+pv]
0x180017c21  and     [rbp+arg_18], 0
0x180017c26  mov     rbx, rcx
0x180017c29  mov     rcx, [rcx+8]
0x180017c2d  mov     esi, edx
0x180017c2f  lea     rdx, [rbp+arg_10]
0x180017c33  mov     rax, [rcx]
0x180017c36  mov     rax, [rax+18h]
0x180017c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c3f  mov     edi, eax
0x180017c41  test    eax, eax
0x180017c43  js      loc_180017E09
0x180017c49  cmp     [rbp+arg_10], 0
0x180017c4e  jnz     short loc_180017C5A
0x180017c50  mov     edi, 80070103h
0x180017c55  jmp     loc_180017E09
0x180017c5a  mov     rcx, [rbx+10h]; lpMem
0x180017c5e  test    rcx, rcx
0x180017c61  jz      short loc_180017C6D
0x180017c63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017c68  and     qword ptr [rbx+10h], 0
0x180017c6d  and     dword ptr [rbx+18h], 0
0x180017c71  mov     rcx, [rbx+20h]; lpMem
0x180017c75  test    rcx, rcx
0x180017c78  jz      short loc_180017C84
0x180017c7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017c7f  and     qword ptr [rbx+20h], 0
0x180017c84  and     dword ptr [rbx+28h], 0
0x180017c88  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017c8f  mov     eax, 58h ; 'X'
0x180017c94  mul     [rbp+arg_10]
0x180017c98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017c9f  cmovo   rax, rcx
0x180017ca3  mov     rcx, rax; unsigned __int64
0x180017ca6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017cab  mov     [rbx+10h], rax
0x180017caf  test    rax, rax
0x180017cb2  jnz     short loc_180017CBE
0x180017cb4  mov     edi, 8007000Eh
0x180017cb9  jmp     loc_180017E09
0x180017cbe  imul    r8, [rbp+arg_10], 58h ; 'X'; Size
0x180017cc3  xor     edx, edx; Val
0x180017cc5  mov     rcx, rax; void *
0x180017cc8  call    memset_0
0x180017ccd  mov     rcx, [rbp+arg_10]
0x180017cd1  xor     r10d, r10d
0x180017cd4  test    rcx, rcx
0x180017cd7  jz      loc_180017DFD
0x180017cdd  xor     r9d, r9d
0x180017ce0  mov     rax, [rbp+pv]
0x180017ce4  mov     rdx, [r9+rax+10h]
0x180017ce9  test    rdx, rdx
0x180017cec  jz      loc_180017DED
0x180017cf2  mov     eax, [rbx+18h]
0x180017cf5  imul    rcx, rax, 58h ; 'X'
0x180017cf9  mov     rax, [rbx+10h]
0x180017cfd  mov     [rcx+rax], rdx
0x180017d01  mov     eax, [rbx+18h]
0x180017d04  mov     rdx, [rbx+10h]
0x180017d08  imul    r8, rax, 58h ; 'X'
0x180017d0c  mov     rax, [rbp+pv]
0x180017d10  movzx   ecx, word ptr [r9+rax+28h]
0x180017d16  mov     [r8+rdx+54h], cx
0x180017d1c  xor     r8d, r8d
0x180017d1f  mov     eax, [rbx+18h]
0x180017d22  lea     rcx, [r9+r8]
0x180017d26  imul    rdx, rax, 58h ; 'X'
0x180017d2a  mov     rax, [rbp+pv]
0x180017d2e  add     rdx, [rbx+10h]
0x180017d32  mov     cl, [rcx+rax+2Ah]
0x180017d36  mov     [rdx+r8+56h], cl
0x180017d3b  inc     r8
0x180017d3e  cmp     r8, 2
0x180017d42  jl      short loc_180017D1F
0x180017d44  mov     eax, [rbx+18h]
0x180017d47  mov     rdx, [rbx+10h]
0x180017d4b  imul    r8, rax, 58h ; 'X'
0x180017d4f  mov     rax, [rbp+pv]
0x180017d53  mov     rcx, [r9+rax+20h]
0x180017d58  mov     [r8+rdx+48h], rcx
0x180017d5d  mov     eax, [rbx+18h]
0x180017d60  imul    rcx, rax, 58h ; 'X'
0x180017d64  mov     rax, [rbx+10h]
0x180017d68  and     dword ptr [rcx+rax+3Ch], 0
0x180017d6d  mov     eax, [rbx+18h]
0x180017d70  imul    rcx, rax, 58h ; 'X'
0x180017d74  mov     rax, [rbx+10h]
0x180017d78  and     dword ptr [rcx+rax+40h], 0
0x180017d7d  mov     eax, [rbx+18h]
0x180017d80  imul    rcx, rax, 58h ; 'X'
0x180017d84  mov     rax, [rbx+10h]
0x180017d88  mov     dword ptr [rcx+rax+38h], 7
0x180017d90  mov     edx, [rbx+28h]
0x180017d93  mov     eax, [rbx+18h]
0x180017d96  imul    rcx, rax, 58h ; 'X'
0x180017d9a  mov     rax, [rbx+10h]
0x180017d9e  mov     [rcx+rax+10h], rdx
0x180017da3  add     dword ptr [rbx+28h], 8
0x180017da7  mov     eax, [rbx+18h]
0x180017daa  mov     edx, [rbx+28h]
0x180017dad  imul    rcx, rax, 58h ; 'X'
0x180017db1  mov     rax, [rbx+10h]
0x180017db5  mov     [rcx+rax+18h], rdx
0x180017dba  mov     eax, [rbx+18h]
0x180017dbd  add     dword ptr [rbx+28h], 4
0x180017dc1  mov     edx, [rbx+28h]
0x180017dc4  imul    rcx, rax, 58h ; 'X'
0x180017dc8  mov     rax, [rbx+10h]
0x180017dcc  mov     [rcx+rax+8], rdx
0x180017dd1  mov     edx, [rbx+18h]
0x180017dd4  mov     rax, [rbx+10h]
0x180017dd8  imul    rcx, rdx, 58h ; 'X'
0x180017ddc  mov     ecx, [rcx+rax+48h]
0x180017de0  lea     eax, [rdx+1]
0x180017de3  add     [rbx+28h], ecx
0x180017de6  mov     rcx, [rbp+arg_10]
0x180017dea  mov     [rbx+18h], eax
0x180017ded  inc     r10
0x180017df0  add     r9, 50h ; 'P'
0x180017df4  cmp     r10, rcx
0x180017df7  jb      loc_180017CE0
0x180017dfd  mov     edx, esi; unsigned int
0x180017dff  mov     rcx, rbx; this
0x180017e02  call    ?CreateAccessor@CDbAccessor@@QEAAJK@Z; CDbAccessor::CreateAccessor(ulong)
0x180017e07  mov     edi, eax
0x180017e09  mov     rcx, [rbp+pv]; pv
0x180017e0d  test    rcx, rcx
0x180017e10  jz      short loc_180017E23
0x180017e12  call    cs:__imp_CoTaskMemFree
0x180017e19  nop     dword ptr [rax+rax+00h]
0x180017e1e  and     [rbp+pv], 0
0x180017e23  mov     rcx, [rbp+arg_18]; pv
0x180017e27  test    rcx, rcx
0x180017e2a  jz      short loc_180017E38
0x180017e2c  call    cs:__imp_CoTaskMemFree
0x180017e33  nop     dword ptr [rax+rax+00h]
0x180017e38  mov     rbx, [rsp+30h+arg_8]
0x180017e3d  mov     eax, edi
0x180017e3f  add     rsp, 30h
0x180017e43  pop     rdi
0x180017e44  pop     rsi
0x180017e45  pop     rbp
0x180017e46  retn
```
