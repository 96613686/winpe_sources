# CDbAccessor::CreateDefaultAccessor(ulong)

- ea: `0x1800189c0`
- end: `0x180018c16`
- name: `?CreateDefaultAccessor@CDbAccessor@@QEAAJK@Z`
- size: `598`
- prototype: `__int64 __fastcall(CDbAccessor *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x18000214c`
- `0x180018720`
- `0x1800189c0`
- `0x180030362`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018a23`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018a41`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018a23`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018a41`
- `OLE32!CoTaskMemFree` at `0x180018be0`
- `OLE32!CoTaskMemFree` at `0x180018bfa`
- `OLE32!CoTaskMemFree` at `0x180018be0`
- `OLE32!CoTaskMemFree` at `0x180018bfa`

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
0x1800189c0  mov     [rsp-18h+arg_8], rbx
0x1800189c5  push    rbp
0x1800189c6  push    rsi
0x1800189c7  push    rdi
0x1800189c8  mov     rbp, rsp
0x1800189cb  sub     rsp, 30h
0x1800189cf  and     [rbp+arg_10], 0
0x1800189d4  lea     r9, [rbp+arg_18]
0x1800189d8  and     [rbp+pv], 0
0x1800189dd  lea     r8, [rbp+pv]
0x1800189e1  and     [rbp+arg_18], 0
0x1800189e6  mov     rbx, rcx
0x1800189e9  mov     rcx, [rcx+8]
0x1800189ed  mov     esi, edx
0x1800189ef  lea     rdx, [rbp+arg_10]
0x1800189f3  mov     rax, [rcx]
0x1800189f6  mov     rax, [rax+18h]
0x1800189fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189ff  mov     edi, eax
0x180018a01  test    eax, eax
0x180018a03  js      loc_180018BD7
0x180018a09  cmp     [rbp+arg_10], 0
0x180018a0e  jnz     short loc_180018A1A
0x180018a10  mov     edi, 80070103h
0x180018a15  jmp     loc_180018BD7
0x180018a1a  mov     rcx, [rbx+10h]
0x180018a1e  test    rcx, rcx
0x180018a21  jz      short loc_180018A34
0x180018a23  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018a2a  nop     dword ptr [rax+rax+00h]
0x180018a2f  and     qword ptr [rbx+10h], 0
0x180018a34  and     dword ptr [rbx+18h], 0
0x180018a38  mov     rcx, [rbx+20h]
0x180018a3c  test    rcx, rcx
0x180018a3f  jz      short loc_180018A52
0x180018a41  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018a48  nop     dword ptr [rax+rax+00h]
0x180018a4d  and     qword ptr [rbx+20h], 0
0x180018a52  and     dword ptr [rbx+28h], 0
0x180018a56  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018a5d  mov     eax, 58h ; 'X'
0x180018a62  mul     [rbp+arg_10]
0x180018a66  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018a6d  cmovo   rax, rcx
0x180018a71  mov     rcx, rax; unsigned __int64
0x180018a74  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018a79  mov     [rbx+10h], rax
0x180018a7d  test    rax, rax
0x180018a80  jnz     short loc_180018A8C
0x180018a82  mov     edi, 8007000Eh
0x180018a87  jmp     loc_180018BD7
0x180018a8c  imul    r8, [rbp+arg_10], 58h ; 'X'; Size
0x180018a91  xor     edx, edx; Val
0x180018a93  mov     rcx, rax; void *
0x180018a96  call    memset_0
0x180018a9b  mov     rcx, [rbp+arg_10]
0x180018a9f  xor     r10d, r10d
0x180018aa2  test    rcx, rcx
0x180018aa5  jz      loc_180018BCB
0x180018aab  xor     r9d, r9d
0x180018aae  mov     rax, [rbp+pv]
0x180018ab2  mov     rdx, [r9+rax+10h]
0x180018ab7  test    rdx, rdx
0x180018aba  jz      loc_180018BBB
0x180018ac0  mov     eax, [rbx+18h]
0x180018ac3  imul    rcx, rax, 58h ; 'X'
0x180018ac7  mov     rax, [rbx+10h]
0x180018acb  mov     [rcx+rax], rdx
0x180018acf  mov     eax, [rbx+18h]
0x180018ad2  mov     rdx, [rbx+10h]
0x180018ad6  imul    r8, rax, 58h ; 'X'
0x180018ada  mov     rax, [rbp+pv]
0x180018ade  movzx   ecx, word ptr [r9+rax+28h]
0x180018ae4  mov     [r8+rdx+54h], cx
0x180018aea  xor     r8d, r8d
0x180018aed  mov     eax, [rbx+18h]
0x180018af0  lea     rcx, [r9+r8]
0x180018af4  imul    rdx, rax, 58h ; 'X'
0x180018af8  mov     rax, [rbp+pv]
0x180018afc  add     rdx, [rbx+10h]
0x180018b00  mov     cl, [rcx+rax+2Ah]
0x180018b04  mov     [rdx+r8+56h], cl
0x180018b09  inc     r8
0x180018b0c  cmp     r8, 2
0x180018b10  jl      short loc_180018AED
0x180018b12  mov     eax, [rbx+18h]
0x180018b15  mov     rdx, [rbx+10h]
0x180018b19  imul    r8, rax, 58h ; 'X'
0x180018b1d  mov     rax, [rbp+pv]
0x180018b21  mov     rcx, [r9+rax+20h]
0x180018b26  mov     [r8+rdx+48h], rcx
0x180018b2b  mov     eax, [rbx+18h]
0x180018b2e  imul    rcx, rax, 58h ; 'X'
0x180018b32  mov     rax, [rbx+10h]
0x180018b36  and     dword ptr [rcx+rax+3Ch], 0
0x180018b3b  mov     eax, [rbx+18h]
0x180018b3e  imul    rcx, rax, 58h ; 'X'
0x180018b42  mov     rax, [rbx+10h]
0x180018b46  and     dword ptr [rcx+rax+40h], 0
0x180018b4b  mov     eax, [rbx+18h]
0x180018b4e  imul    rcx, rax, 58h ; 'X'
0x180018b52  mov     rax, [rbx+10h]
0x180018b56  mov     dword ptr [rcx+rax+38h], 7
0x180018b5e  mov     edx, [rbx+28h]
0x180018b61  mov     eax, [rbx+18h]
0x180018b64  imul    rcx, rax, 58h ; 'X'
0x180018b68  mov     rax, [rbx+10h]
0x180018b6c  mov     [rcx+rax+10h], rdx
0x180018b71  add     dword ptr [rbx+28h], 8
0x180018b75  mov     eax, [rbx+18h]
0x180018b78  mov     edx, [rbx+28h]
0x180018b7b  imul    rcx, rax, 58h ; 'X'
0x180018b7f  mov     rax, [rbx+10h]
0x180018b83  mov     [rcx+rax+18h], rdx
0x180018b88  mov     eax, [rbx+18h]
0x180018b8b  add     dword ptr [rbx+28h], 4
0x180018b8f  mov     edx, [rbx+28h]
0x180018b92  imul    rcx, rax, 58h ; 'X'
0x180018b96  mov     rax, [rbx+10h]
0x180018b9a  mov     [rcx+rax+8], rdx
0x180018b9f  mov     edx, [rbx+18h]
0x180018ba2  mov     rax, [rbx+10h]
0x180018ba6  imul    rcx, rdx, 58h ; 'X'
0x180018baa  mov     ecx, [rcx+rax+48h]
0x180018bae  lea     eax, [rdx+1]
0x180018bb1  add     [rbx+28h], ecx
0x180018bb4  mov     rcx, [rbp+arg_10]
0x180018bb8  mov     [rbx+18h], eax
0x180018bbb  inc     r10
0x180018bbe  add     r9, 50h ; 'P'
0x180018bc2  cmp     r10, rcx
0x180018bc5  jb      loc_180018AAE
0x180018bcb  mov     edx, esi; unsigned int
0x180018bcd  mov     rcx, rbx; this
0x180018bd0  call    ?CreateAccessor@CDbAccessor@@QEAAJK@Z; CDbAccessor::CreateAccessor(ulong)
0x180018bd5  mov     edi, eax
0x180018bd7  mov     rcx, [rbp+pv]; pv
0x180018bdb  test    rcx, rcx
0x180018bde  jz      short loc_180018BF1
0x180018be0  call    cs:__imp_CoTaskMemFree
0x180018be7  nop     dword ptr [rax+rax+00h]
0x180018bec  and     [rbp+pv], 0
0x180018bf1  mov     rcx, [rbp+arg_18]; pv
0x180018bf5  test    rcx, rcx
0x180018bf8  jz      short loc_180018C06
0x180018bfa  call    cs:__imp_CoTaskMemFree
0x180018c01  nop     dword ptr [rax+rax+00h]
0x180018c06  mov     rbx, [rsp+30h+arg_8]
0x180018c0b  mov     eax, edi
0x180018c0d  add     rsp, 30h
0x180018c11  pop     rdi
0x180018c12  pop     rsi
0x180018c13  pop     rbp
0x180018c14  retn
```
