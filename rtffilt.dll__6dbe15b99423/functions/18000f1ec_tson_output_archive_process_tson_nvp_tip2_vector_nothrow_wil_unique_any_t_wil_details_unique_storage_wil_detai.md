# tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x18000f1ec`
- end: `0x18000f4da`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `750`
- prototype: `__int64 __fastcall(tson *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800189d8`

## callees

- `0x18000f1ec`
- `0x180016768`
- `0x180017c40`
- `0x180017d40`
- `0x180018360`
- `0x180018f64`
- `0x180019178`

## pseudocode

```c
void __fastcall tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  char v4; // r10
  __int64 *v5; // r15
  __int64 v8; // rsi
  _BYTE *v9; // rbx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdx
  char *v12; // rcx
  void **v13; // r14
  __int64 v14; // r12
  _BYTE *v15; // r15
  unsigned __int64 v16; // rbp
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // r14
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  char *v22; // rcx
  struct tson::output_archive *v23; // rsi
  __int64 v24; // rbp
  struct wil::StoredFailureInfo *v25; // r8
  unsigned __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // r14
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rdx
  char *v31; // rcx
  struct tson::output_archive *v32; // rsi
  __int64 v33; // rbp
  struct tip2::test_flag *v34; // r8
  unsigned __int64 v35; // rax

  v4 = *(_BYTE *)(a2 + 8);
  v5 = a4;
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_BYTE *)this + 8) = v4;
  v8 = *(_QWORD *)(a2 + 16);
  tson::output_archive::write_name(this, 0);
  v9 = (char *)this + 24;
  v10 = *((_QWORD *)this + 16);
  if ( v10 >= 0x19 )
  {
    *v9 = 1;
  }
  else
  {
    *(_DWORD *)&v9[4 * v10 + 4] = 0;
    v10 = ++*((_QWORD *)this + 16);
  }
  v11 = *(_QWORD *)(v8 + 16);
  if ( v10 )
  {
    v12 = (char *)this + 4 * v10 + 20;
  }
  else
  {
    *v9 = 1;
    v12 = (char *)this + 24;
  }
  *((_DWORD *)v12 + 1) = 2;
  if ( v11 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v11;
  v13 = *(void ***)v8;
  v14 = *(_QWORD *)v8 + 8LL * *(_QWORD *)(v8 + 16);
  if ( *(_QWORD *)v8 != v14 )
  {
    do
    {
      v15 = *v13;
      if ( *v13 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
      }
      else
      {
        v16 = 0;
      }
      if ( tson::output_archive::write_name(this, v15 == 0) )
      {
        v17 = *((_QWORD *)this + 18);
        if ( *(_QWORD *)(v17 + 2072) < *(_QWORD *)(v17 + 2080)
          || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
        {
          *(_BYTE *)(*(_QWORD *)(v17 + 2072))++ = 23;
        }
        tson::output_archive::write_string_bytes(this, v16, v15, v16);
      }
      ++v13;
    }
    while ( v13 != (void **)v14 );
    v5 = a4;
  }
  tson::output_archive::finishNode(this);
  v18 = *a3;
  *((_BYTE *)this + 8) = *((_BYTE *)a3 + 8);
  *(_QWORD *)this = v18;
  v19 = a3[2];
  tson::output_archive::write_name(this, 0);
  v20 = *((_QWORD *)this + 16);
  if ( v20 >= 0x19 )
  {
    *v9 = 1;
  }
  else
  {
    *(_DWORD *)&v9[4 * v20 + 4] = 0;
    v20 = ++*((_QWORD *)this + 16);
  }
  v21 = *(_QWORD *)(v19 + 16);
  if ( v20 )
  {
    v22 = (char *)this + 4 * v20 + 20;
  }
  else
  {
    *v9 = 1;
    v22 = (char *)this + 24;
  }
  *((_DWORD *)v22 + 1) = 2;
  if ( v21 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v21;
  v23 = *(struct tson::output_archive **)v19;
  v24 = *(_QWORD *)v19 + 168LL * *(_QWORD *)(v19 + 16);
  while ( v23 != (struct tson::output_archive *)v24 )
  {
    tson::output_archive::write_name(this, 0);
    v26 = *((_QWORD *)this + 16);
    if ( v26 >= 0x19 )
    {
      *v9 = 1;
    }
    else
    {
      *(_DWORD *)&v9[4 * v26 + 4] = 0;
      ++*((_QWORD *)this + 16);
    }
    tson::save_nothrow(this, v23, v25);
    tson::output_archive::finishNode(this);
    v23 = (struct tson::output_archive *)((char *)v23 + 168);
  }
  tson::output_archive::finishNode(this);
  v27 = *v5;
  *((_BYTE *)this + 8) = *((_BYTE *)v5 + 8);
  *(_QWORD *)this = v27;
  v28 = v5[2];
  tson::output_archive::write_name(this, 0);
  v29 = *((_QWORD *)this + 16);
  if ( v29 >= 0x19 )
  {
    *v9 = 1;
  }
  else
  {
    *(_DWORD *)&v9[4 * v29 + 4] = 0;
    v29 = ++*((_QWORD *)this + 16);
  }
  v30 = *(_QWORD *)(v28 + 16);
  if ( v29 )
  {
    v31 = (char *)this + 4 * v29 + 20;
  }
  else
  {
    *v9 = 1;
    v31 = (char *)this + 24;
  }
  *((_DWORD *)v31 + 1) = 2;
  if ( v30 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v30;
  v32 = *(struct tson::output_archive **)v28;
  v33 = *(_QWORD *)v28 + 104LL * *(_QWORD *)(v28 + 16);
  while ( v32 != (struct tson::output_archive *)v33 )
  {
    tson::output_archive::write_name(this, 0);
    v35 = *((_QWORD *)this + 16);
    if ( v35 >= 0x19 )
    {
      *v9 = 1;
    }
    else
    {
      *(_DWORD *)&v9[4 * v35 + 4] = 0;
      ++*((_QWORD *)this + 16);
    }
    tson::save_nothrow(this, v32, v34);
    tson::output_archive::finishNode(this);
    v32 = (struct tson::output_archive *)((char *)v32 + 104);
  }
  tson::output_archive::finishNode(this);
}

```

## disassembly

```asm
0x18000f1ec  mov     [rsp+arg_18], r9
0x18000f1f1  push    rbx
0x18000f1f2  push    rbp
0x18000f1f3  push    rsi
0x18000f1f4  push    rdi
0x18000f1f5  push    r12
0x18000f1f7  push    r13
0x18000f1f9  push    r14
0x18000f1fb  push    r15
0x18000f1fd  sub     rsp, 48h
0x18000f201  mov     r10b, [rdx+8]
0x18000f205  mov     r15, r9
0x18000f208  mov     rax, [rdx]
0x18000f20b  mov     r13, r8
0x18000f20e  mov     [rcx], rax
0x18000f211  mov     rdi, rcx
0x18000f214  mov     [rcx+8], r10b
0x18000f218  mov     rsi, [rdx+10h]
0x18000f21c  xor     edx, edx; bool
0x18000f21e  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000f223  lea     rbx, [rdi+18h]
0x18000f227  mov     rax, [rbx+68h]
0x18000f22b  cmp     rax, 19h
0x18000f22f  jnb     short loc_18000F243
0x18000f231  mov     dword ptr [rbx+rax*4+4], 0
0x18000f239  inc     qword ptr [rbx+68h]
0x18000f23d  mov     rax, [rbx+68h]
0x18000f241  jmp     short loc_18000F246
0x18000f243  mov     byte ptr [rbx], 1
0x18000f246  mov     rdx, [rsi+10h]
0x18000f24a  test    rax, rax
0x18000f24d  jz      short loc_18000F259
0x18000f24f  lea     rcx, [rbx-4]
0x18000f253  lea     rcx, [rcx+rax*4]
0x18000f257  jmp     short loc_18000F25F
0x18000f259  mov     byte ptr [rbx], 1
0x18000f25c  mov     rcx, rbx
0x18000f25f  mov     dword ptr [rcx+4], 2
0x18000f266  cmp     rdx, 0FFFFh
0x18000f26d  jbe     short loc_18000F282
0x18000f26f  cmp     dword ptr [rdi+88h], 0
0x18000f276  jl      short loc_18000F282
0x18000f278  mov     dword ptr [rdi+88h], 8000000Bh
0x18000f282  mov     [rdi+0Ah], dx
0x18000f286  mov     r14, [rsi]
0x18000f289  mov     rax, [rsi+10h]
0x18000f28d  lea     r12, [r14+rax*8]
0x18000f291  cmp     r14, r12
0x18000f294  jz      loc_18000F321
0x18000f29a  mov     r15, [r14]
0x18000f29d  test    r15, r15
0x18000f2a0  jz      short loc_18000F2B2
0x18000f2a2  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000f2a6  inc     rbp
0x18000f2a9  cmp     byte ptr [r15+rbp], 0
0x18000f2ae  jnz     short loc_18000F2A6
0x18000f2b0  jmp     short loc_18000F2B4
0x18000f2b2  xor     ebp, ebp
0x18000f2b4  test    r15, r15
0x18000f2b7  mov     rcx, rdi; this
0x18000f2ba  setz    dl; bool
0x18000f2bd  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000f2c2  test    al, al
0x18000f2c4  jz      short loc_18000F310
0x18000f2c6  mov     rsi, [rdi+90h]
0x18000f2cd  mov     rax, [rsi+820h]
0x18000f2d4  cmp     [rsi+818h], rax
0x18000f2db  jb      short loc_18000F2EE
0x18000f2dd  mov     edx, 1; unsigned __int64
0x18000f2e2  mov     rcx, rsi; this
0x18000f2e5  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000f2ea  test    al, al
0x18000f2ec  jz      short loc_18000F2FF
0x18000f2ee  mov     rax, [rsi+818h]
0x18000f2f5  mov     byte ptr [rax], 17h
0x18000f2f8  inc     qword ptr [rsi+818h]
0x18000f2ff  mov     r9, rbp; unsigned __int64
0x18000f302  mov     r8, r15; void *
0x18000f305  mov     rdx, rbp; unsigned __int64
0x18000f308  mov     rcx, rdi; this
0x18000f30b  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18000f310  add     r14, 8
0x18000f314  cmp     r14, r12
0x18000f317  jnz     short loc_18000F29A
0x18000f319  mov     r15, [rsp+88h+arg_18]
0x18000f321  mov     rcx, rdi; this
0x18000f324  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000f329  mov     cl, [r13+8]
0x18000f32d  xor     edx, edx; bool
0x18000f32f  mov     rax, [r13+0]
0x18000f333  mov     [rdi+8], cl
0x18000f336  mov     rcx, rdi; this
0x18000f339  mov     [rdi], rax
0x18000f33c  mov     r14, [r13+10h]
0x18000f340  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000f345  mov     rax, [rbx+68h]
0x18000f349  cmp     rax, 19h
0x18000f34d  jnb     short loc_18000F361
0x18000f34f  mov     dword ptr [rbx+rax*4+4], 0
0x18000f357  inc     qword ptr [rbx+68h]
0x18000f35b  mov     rax, [rbx+68h]
0x18000f35f  jmp     short loc_18000F364
0x18000f361  mov     byte ptr [rbx], 1
0x18000f364  mov     rdx, [r14+10h]
0x18000f368  test    rax, rax
0x18000f36b  jz      short loc_18000F377
0x18000f36d  lea     rcx, [rbx-4]
0x18000f371  lea     rcx, [rcx+rax*4]
0x18000f375  jmp     short loc_18000F37D
0x18000f377  mov     byte ptr [rbx], 1
0x18000f37a  mov     rcx, rbx
0x18000f37d  mov     dword ptr [rcx+4], 2
0x18000f384  cmp     rdx, 0FFFFh
0x18000f38b  jbe     short loc_18000F3A0
0x18000f38d  cmp     dword ptr [rdi+88h], 0
0x18000f394  jl      short loc_18000F3A0
0x18000f396  mov     dword ptr [rdi+88h], 8000000Bh
0x18000f3a0  mov     [rdi+0Ah], dx
0x18000f3a4  imul    rbp, [r14+10h], 0A8h
0x18000f3ac  mov     rsi, [r14]
0x18000f3af  add     rbp, rsi
0x18000f3b2  jmp     short loc_18000F3F0
0x18000f3b4  xor     edx, edx; bool
0x18000f3b6  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000f3bb  mov     rax, [rbx+68h]
0x18000f3bf  cmp     rax, 19h
0x18000f3c3  jnb     short loc_18000F3D3
0x18000f3c5  mov     dword ptr [rbx+rax*4+4], 0
0x18000f3cd  inc     qword ptr [rbx+68h]
0x18000f3d1  jmp     short loc_18000F3D6
0x18000f3d3  mov     byte ptr [rbx], 1
0x18000f3d6  mov     rdx, rsi; struct tson::output_archive *
0x18000f3d9  mov     rcx, rdi; this
0x18000f3dc  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::save_nothrow(tson::output_archive &,wil::StoredFailureInfo &)
0x18000f3e1  mov     rcx, rdi; this
0x18000f3e4  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000f3e9  add     rsi, 0A8h
0x18000f3f0  mov     rcx, rdi; this
0x18000f3f3  cmp     rsi, rbp
0x18000f3f6  jnz     short loc_18000F3B4
0x18000f3f8  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000f3fd  mov     cl, [r15+8]
0x18000f401  xor     edx, edx; bool
0x18000f403  mov     rax, [r15]
0x18000f406  mov     [rdi+8], cl
0x18000f409  mov     rcx, rdi; this
0x18000f40c  mov     [rdi], rax
0x18000f40f  mov     r14, [r15+10h]
0x18000f413  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000f418  mov     rax, [rbx+68h]
0x18000f41c  cmp     rax, 19h
0x18000f420  jnb     short loc_18000F434
0x18000f422  mov     dword ptr [rbx+rax*4+4], 0
0x18000f42a  inc     qword ptr [rbx+68h]
0x18000f42e  mov     rax, [rbx+68h]
0x18000f432  jmp     short loc_18000F437
0x18000f434  mov     byte ptr [rbx], 1
0x18000f437  mov     rdx, [r14+10h]
0x18000f43b  test    rax, rax
0x18000f43e  jz      short loc_18000F44A
0x18000f440  lea     rcx, [rbx-4]
0x18000f444  lea     rcx, [rcx+rax*4]
0x18000f448  jmp     short loc_18000F450
0x18000f44a  mov     byte ptr [rbx], 1
0x18000f44d  mov     rcx, rbx
0x18000f450  mov     dword ptr [rcx+4], 2
0x18000f457  cmp     rdx, 0FFFFh
0x18000f45e  jbe     short loc_18000F473
0x18000f460  cmp     dword ptr [rdi+88h], 0
0x18000f467  jl      short loc_18000F473
0x18000f469  mov     dword ptr [rdi+88h], 8000000Bh
0x18000f473  mov     [rdi+0Ah], dx
0x18000f477  imul    rbp, [r14+10h], 68h ; 'h'
0x18000f47c  mov     rsi, [r14]
0x18000f47f  add     rbp, rsi
0x18000f482  jmp     short loc_18000F4BD
0x18000f484  xor     edx, edx; bool
0x18000f486  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000f48b  mov     rax, [rbx+68h]
0x18000f48f  cmp     rax, 19h
0x18000f493  jnb     short loc_18000F4A3
0x18000f495  mov     dword ptr [rbx+rax*4+4], 0
0x18000f49d  inc     qword ptr [rbx+68h]
0x18000f4a1  jmp     short loc_18000F4A6
0x18000f4a3  mov     byte ptr [rbx], 1
0x18000f4a6  mov     rdx, rsi; struct tson::output_archive *
0x18000f4a9  mov     rcx, rdi; this
0x18000f4ac  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAUtest_flag@tip2@@@Z; tson::save_nothrow(tson::output_archive &,tip2::test_flag &)
0x18000f4b1  mov     rcx, rdi; this
0x18000f4b4  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000f4b9  add     rsi, 68h ; 'h'
0x18000f4bd  mov     rcx, rdi; this
0x18000f4c0  cmp     rsi, rbp
0x18000f4c3  jnz     short loc_18000F484
0x18000f4c5  add     rsp, 48h
0x18000f4c9  pop     r15
0x18000f4cb  pop     r14
0x18000f4cd  pop     r13
0x18000f4cf  pop     r12
0x18000f4d1  pop     rdi
0x18000f4d2  pop     rsi
0x18000f4d3  pop     rbp
0x18000f4d4  pop     rbx
0x18000f4d5  jmp     ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
```
