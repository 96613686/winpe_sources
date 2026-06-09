# CTextNormalizerTransJPN::WordBreakerBackup(ushort const *,long,long,ushort * *,ulong *,ulong *,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0002 * *,ulong *,ulong *)

- ea: `0x1800daef0`
- end: `0x1800db08f`
- name: `?WordBreakerBackup@CTextNormalizerTransJPN@@MEAAJPEBGJJPEAPEAGPEAK2PEAPEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0002@@22@Z`
- size: `415`
- prototype: `__int64 __fastcall(CTextNormalizerTransJPN *this, const unsigned __int16 *, int, __int64, unsigned __int16 **, unsigned int *, unsigned int *, struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0002 **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180004312`
- `0x18004c4d8`
- `0x1800daef0`
- `0x1800db098`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db073`

## pseudocode

```c
__int64 __fastcall CTextNormalizerTransJPN::WordBreakerBackup(
        CTextNormalizerTransJPN *this,
        const unsigned __int16 *a2,
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
  v10 = CTextNormalizerTransJPN::WordBreakerBackupHelp(
          (__int64)this,
          a2,
          a3,
          a4,
          (struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)&v21);
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
0x1800daef0  mov     rax, rsp
0x1800daef3  mov     [rax+20h], r9d
0x1800daef7  push    rbx
0x1800daef8  push    rbp
0x1800daef9  push    rsi
0x1800daefa  push    rdi
0x1800daefb  push    r12
0x1800daefd  push    r13
0x1800daeff  push    r14
0x1800daf01  push    r15
0x1800daf03  sub     rsp, 88h
0x1800daf0a  xorps   xmm0, xmm0
0x1800daf0d  movups  xmmword ptr [rax-80h], xmm0
0x1800daf11  movups  xmmword ptr [rax-70h], xmm0
0x1800daf15  movups  xmmword ptr [rax-60h], xmm0
0x1800daf19  lea     rax, [rax-80h]
0x1800daf1d  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800daf22  call    ?WordBreakerBackupHelp@CTextNormalizerTransJPN@@AEAAJPEBGJW4SRWORDBREAKERFLAGS@@PEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003@@@Z; CTextNormalizerTransJPN::WordBreakerBackupHelp(ushort const *,long,SRWORDBREAKERFLAGS,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)
0x1800daf27  xor     r9d, r9d
0x1800daf2a  mov     edi, eax
0x1800daf2c  test    eax, eax
0x1800daf2e  js      loc_1800DB069
0x1800daf34  mov     esi, [rsp+0C8h+var_80]
0x1800daf38  test    esi, esi
0x1800daf3a  jz      loc_1800DB069
0x1800daf40  mov     r15, [rsp+0C8h+arg_28]
0x1800daf48  mov     ebx, r9d
0x1800daf4b  mov     r14, [rsp+0C8h+arg_40]
0x1800daf53  mov     ecx, r9d
0x1800daf56  mov     r8, qword ptr [rsp+0C8h+var_70]
0x1800daf5b  mov     r12d, [r15]
0x1800daf5e  mov     r13d, [r14]
0x1800daf61  mov     [rsp+0C8h+var_88], r12d
0x1800daf66  cmp     ecx, esi
0x1800daf68  jnb     short loc_1800DAF86
0x1800daf6a  mov     eax, ecx
0x1800daf6c  mov     rdx, [r8+rax*8]
0x1800daf70  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800daf74  inc     rax
0x1800daf77  cmp     [rdx+rax*2], r9w
0x1800daf7c  jnz     short loc_1800DAF74
0x1800daf7e  inc     ebx
0x1800daf80  add     ebx, eax
0x1800daf82  inc     ecx
0x1800daf84  jmp     short loc_1800DAF66
0x1800daf86  mov     rbp, [rsp+0C8h+arg_38]
0x1800daf8e  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x1800daf95  mov     r9, [rsp+0C8h+arg_48]; unsigned int *
0x1800daf9d  lea     r8d, [rsi+r13]; unsigned int
0x1800dafa1  mov     [rsp+0C8h+var_A0], rax; struct CHeap *
0x1800dafa6  mov     rcx, rbp; void **
0x1800dafa9  mov     edx, 0Ch; unsigned __int64
0x1800dafae  mov     [rsp+0C8h+var_A8], 1; unsigned int
0x1800dafb6  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x1800dafbb  mov     edi, eax
0x1800dafbd  test    eax, eax
0x1800dafbf  js      loc_1800DB079
0x1800dafc5  mov     r9, [rsp+0C8h+arg_30]; unsigned int *
0x1800dafcd  lea     r8d, [r12+rbx]; unsigned int
0x1800dafd1  mov     r12, [rsp+0C8h+arg_20]
0x1800dafd9  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x1800dafe0  mov     [rsp+0C8h+var_A0], rax; struct CHeap *
0x1800dafe5  mov     rcx, r12; void **
0x1800dafe8  mov     edx, 2; unsigned __int64
0x1800dafed  mov     [rsp+0C8h+var_A8], 0Ah; unsigned int
0x1800daff5  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x1800daffa  mov     edi, eax
0x1800daffc  test    eax, eax
0x1800daffe  js      short loc_1800DB079
0x1800db000  add     [r15], ebx
0x1800db003  mov     rax, [r12]
0x1800db007  mov     ecx, [rsp+0C8h+var_88]
0x1800db00b  mov     rdx, [rsp+0C8h+Src]; Src
0x1800db010  mov     r8d, ebx
0x1800db013  add     r8, r8; Size
0x1800db016  lea     rcx, [rax+rcx*2]; void *
0x1800db01a  call    memcpy_0
0x1800db01f  add     [r14], esi
0x1800db022  lea     rbx, ds:0[r13*2]
0x1800db02a  mov     rax, [rbp+0]
0x1800db02e  lea     r8, [rsi+rsi*2]
0x1800db032  mov     rdx, [rsp+0C8h+var_60]; Src
0x1800db037  add     rbx, r13
0x1800db03a  shl     r8, 2; Size
0x1800db03e  lea     rcx, [rax+rbx*4]; void *
0x1800db042  call    memcpy_0
0x1800db047  mov     rax, [rbp+0]
0x1800db04b  xor     edx, edx
0x1800db04d  mov     r9d, [rsp+0C8h+arg_18]
0x1800db055  lea     r8, [rax+rbx*4]
0x1800db059  cmp     edx, esi
0x1800db05b  jnb     short loc_1800DB069
0x1800db05d  lea     rcx, [rdx+rdx*2]
0x1800db061  add     [r8+rcx*4], r9d
0x1800db065  inc     edx
0x1800db067  jmp     short loc_1800DB059
0x1800db069  mov     rcx, [rsp+0C8h+pv]; pv
0x1800db06e  test    rcx, rcx
0x1800db071  jz      short loc_1800DB079
0x1800db073  call    cs:__imp_CoTaskMemFree
0x1800db079  mov     eax, edi
0x1800db07b  add     rsp, 88h
0x1800db082  pop     r15
0x1800db084  pop     r14
0x1800db086  pop     r13
0x1800db088  pop     r12
0x1800db08a  pop     rdi
0x1800db08b  pop     rsi
0x1800db08c  pop     rbp
0x1800db08d  pop     rbx
0x1800db08e  retn
```
