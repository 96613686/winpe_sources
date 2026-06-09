# CTextNormalizerTransCHX::WordBreakerBackup(ushort const *,long,long,ushort * *,ulong *,ulong *,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0002 * *,ulong *,ulong *)

- ea: `0x18001c1f0`
- end: `0x18001c38f`
- name: `?WordBreakerBackup@CTextNormalizerTransCHX@@MEAAJPEBGJJPEAPEAGPEAK2PEAPEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0002@@22@Z`
- size: `415`
- prototype: `__int64 __fastcall(CTextNormalizerTransCHX *__hidden this, const unsigned __int16 *, int, int, unsigned __int16 **, unsigned int *, unsigned int *, struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0002 **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180004312`
- `0x18001c1f0`
- `0x18001c398`
- `0x18004c4d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c373`

## pseudocode

```c
__int64 __fastcall CTextNormalizerTransCHX::WordBreakerBackup(
        CTextNormalizerTransCHX *this,
        unsigned __int16 *a2,
        int a3,
        __int64 a4,
        unsigned __int16 **a5,
        unsigned int *a6,
        unsigned int *a7,
        struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0002 **a8,
        unsigned int *a9,
        unsigned int *a10)
{
  int v10; // edi
  __int64 v11; // rsi
  unsigned int v12; // ebx
  unsigned int v13; // ecx
  int v14; // r12d
  __int64 v15; // r13
  __int64 v16; // rax
  __int64 v17; // rdx
  char *v18; // r8
  int v20; // [rsp+40h] [rbp-88h]
  __int128 v21; // [rsp+48h] [rbp-80h] BYREF
  __int128 v22; // [rsp+58h] [rbp-70h]
  __int128 v23; // [rsp+68h] [rbp-60h]
  int v24; // [rsp+E8h] [rbp+20h]

  v24 = a4;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v10 = CTextNormalizerTransCHX::WordBreakerBackupHelp((__int64)this, a2, a3, a4, (__int64)&v21);
  if ( v10 >= 0 )
  {
    v11 = (unsigned int)v21;
    if ( (_DWORD)v21 )
    {
      v12 = 0;
      v13 = 0;
      v14 = *a6;
      v15 = *a9;
      v20 = *a6;
      while ( v13 < (unsigned int)v21 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(*(_QWORD *)(v22 + 8LL * v13) + 2 * v16) );
        v12 += v16 + 1;
        ++v13;
      }
      v10 = EnsureArrayVoid((void **)a8, 0xCu, (int)v21 + (int)v15, a10, 1u, (struct CHeap *)&g_heap);
      if ( v10 < 0 )
        return (unsigned int)v10;
      v10 = EnsureArrayVoid((void **)a5, 2u, v14 + v12, a7, 0xAu, (struct CHeap *)&g_heap);
      if ( v10 < 0 )
        return (unsigned int)v10;
      *a6 += v12;
      memcpy_0(&(*a5)[v20], *((const void **)&v21 + 1), 2LL * v12);
      *a9 += v11;
      memcpy_0((char *)*a8 + 12 * v15, (const void *)v23, 12 * v11);
      v17 = 0;
      v18 = (char *)*a8 + 12 * v15;
      while ( (unsigned int)v17 < (unsigned int)v11 )
      {
        *(_DWORD *)&v18[12 * v17] += v24;
        v17 = (unsigned int)(v17 + 1);
      }
    }
  }
  if ( *((_QWORD *)&v23 + 1) )
    CoTaskMemFree(*((LPVOID *)&v23 + 1));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c1f0  mov     rax, rsp
0x18001c1f3  mov     [rax+20h], r9d
0x18001c1f7  push    rbx
0x18001c1f8  push    rbp
0x18001c1f9  push    rsi
0x18001c1fa  push    rdi
0x18001c1fb  push    r12
0x18001c1fd  push    r13
0x18001c1ff  push    r14
0x18001c201  push    r15
0x18001c203  sub     rsp, 88h
0x18001c20a  xorps   xmm0, xmm0
0x18001c20d  movups  xmmword ptr [rax-80h], xmm0
0x18001c211  movups  xmmword ptr [rax-70h], xmm0
0x18001c215  movups  xmmword ptr [rax-60h], xmm0
0x18001c219  lea     rax, [rax-80h]
0x18001c21d  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18001c222  call    ?WordBreakerBackupHelp@CTextNormalizerTransCHX@@AEAAJPEBGJW4SRWORDBREAKERFLAGS@@PEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003@@@Z; CTextNormalizerTransCHX::WordBreakerBackupHelp(ushort const *,long,SRWORDBREAKERFLAGS,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)
0x18001c227  xor     r9d, r9d
0x18001c22a  mov     edi, eax
0x18001c22c  test    eax, eax
0x18001c22e  js      loc_18001C369
0x18001c234  mov     esi, [rsp+0C8h+var_80]
0x18001c238  test    esi, esi
0x18001c23a  jz      loc_18001C369
0x18001c240  mov     r15, [rsp+0C8h+arg_28]
0x18001c248  mov     ebx, r9d
0x18001c24b  mov     r14, [rsp+0C8h+arg_40]
0x18001c253  mov     ecx, r9d
0x18001c256  mov     r8, qword ptr [rsp+0C8h+var_70]
0x18001c25b  mov     r12d, [r15]
0x18001c25e  mov     r13d, [r14]
0x18001c261  mov     [rsp+0C8h+var_88], r12d
0x18001c266  cmp     ecx, esi
0x18001c268  jnb     short loc_18001C286
0x18001c26a  mov     eax, ecx
0x18001c26c  mov     rdx, [r8+rax*8]
0x18001c270  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c274  inc     rax
0x18001c277  cmp     [rdx+rax*2], r9w
0x18001c27c  jnz     short loc_18001C274
0x18001c27e  inc     ebx
0x18001c280  add     ebx, eax
0x18001c282  inc     ecx
0x18001c284  jmp     short loc_18001C266
0x18001c286  mov     rbp, [rsp+0C8h+arg_38]
0x18001c28e  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x18001c295  mov     r9, [rsp+0C8h+arg_48]; unsigned int *
0x18001c29d  lea     r8d, [rsi+r13]; unsigned int
0x18001c2a1  mov     [rsp+0C8h+var_A0], rax; struct CHeap *
0x18001c2a6  mov     rcx, rbp; void **
0x18001c2a9  mov     edx, 0Ch; unsigned __int64
0x18001c2ae  mov     [rsp+0C8h+var_A8], 1; unsigned int
0x18001c2b6  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x18001c2bb  mov     edi, eax
0x18001c2bd  test    eax, eax
0x18001c2bf  js      loc_18001C379
0x18001c2c5  mov     r9, [rsp+0C8h+arg_30]; unsigned int *
0x18001c2cd  lea     r8d, [r12+rbx]; unsigned int
0x18001c2d1  mov     r12, [rsp+0C8h+arg_20]
0x18001c2d9  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x18001c2e0  mov     [rsp+0C8h+var_A0], rax; struct CHeap *
0x18001c2e5  mov     rcx, r12; void **
0x18001c2e8  mov     edx, 2; unsigned __int64
0x18001c2ed  mov     [rsp+0C8h+var_A8], 0Ah; unsigned int
0x18001c2f5  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x18001c2fa  mov     edi, eax
0x18001c2fc  test    eax, eax
0x18001c2fe  js      short loc_18001C379
0x18001c300  add     [r15], ebx
0x18001c303  mov     rax, [r12]
0x18001c307  mov     ecx, [rsp+0C8h+var_88]
0x18001c30b  mov     rdx, [rsp+0C8h+Src]; Src
0x18001c310  mov     r8d, ebx
0x18001c313  add     r8, r8; Size
0x18001c316  lea     rcx, [rax+rcx*2]; void *
0x18001c31a  call    memcpy_0
0x18001c31f  add     [r14], esi
0x18001c322  lea     rbx, ds:0[r13*2]
0x18001c32a  mov     rax, [rbp+0]
0x18001c32e  lea     r8, [rsi+rsi*2]
0x18001c332  mov     rdx, [rsp+0C8h+var_60]; Src
0x18001c337  add     rbx, r13
0x18001c33a  shl     r8, 2; Size
0x18001c33e  lea     rcx, [rax+rbx*4]; void *
0x18001c342  call    memcpy_0
0x18001c347  mov     rax, [rbp+0]
0x18001c34b  xor     edx, edx
0x18001c34d  mov     r9d, [rsp+0C8h+arg_18]
0x18001c355  lea     r8, [rax+rbx*4]
0x18001c359  cmp     edx, esi
0x18001c35b  jnb     short loc_18001C369
0x18001c35d  lea     rcx, [rdx+rdx*2]
0x18001c361  add     [r8+rcx*4], r9d
0x18001c365  inc     edx
0x18001c367  jmp     short loc_18001C359
0x18001c369  mov     rcx, [rsp+0C8h+pv]; pv
0x18001c36e  test    rcx, rcx
0x18001c371  jz      short loc_18001C379
0x18001c373  call    cs:__imp_CoTaskMemFree
0x18001c379  mov     eax, edi
0x18001c37b  add     rsp, 88h
0x18001c382  pop     r15
0x18001c384  pop     r14
0x18001c386  pop     r13
0x18001c388  pop     r12
0x18001c38a  pop     rdi
0x18001c38b  pop     rsi
0x18001c38c  pop     rbp
0x18001c38d  pop     rbx
0x18001c38e  retn
```
