# CSREngine::GetDisplayAlternates(SPSERIALIZEDDISPLAYPHRASE const *,ulong,ushort const *,void * *,ulong *)

- ea: `0x18000af64`
- end: `0x18000b3eb`
- name: `?GetDisplayAlternates@CSREngine@@AEAAJPEBUSPSERIALIZEDDISPLAYPHRASE@@KPEBGPEAPEAXPEAK@Z`
- size: `1159`
- prototype: `int(CSREngine *__hidden this, const struct SPSERIALIZEDDISPLAYPHRASE *, unsigned int, const unsigned __int16 *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ef20`

## callees

- `0x180002470`
- `0x180002e00`
- `0x1800040b8`
- `0x180004312`
- `0x18000af64`
- `0x18000e304`
- `0x18001441c`
- `0x180095a38`
- `0x180095c08`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b2e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b2e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b364`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b364`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000afd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000afd0`

## pseudocode

```c
__int64 __fastcall CSREngine::GetDisplayAlternates(
        CSREngine *this,
        const struct SPSERIALIZEDDISPLAYPHRASE *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        void **a5,
        unsigned int *a6)
{
  __int64 v6; // rax
  __int64 v9; // rsi
  struct SPSERIALIZEDDISPLAYPHRASE **v10; // r15
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  struct SPPHRASEELEMENT *v12; // r14
  unsigned int v13; // r13d
  int v14; // eax
  struct SPDISPLAYPHRASE *v15; // r12
  int v16; // edi
  __int64 v17; // r9
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  struct SPSERIALIZEDDISPLAYPHRASE **v20; // rax
  unsigned int v21; // r13d
  __int64 v22; // rbx
  unsigned int v23; // r14d
  ULONG ulNumTokens; // eax
  struct SPPHRASEREPLACEMENT *v25; // rdx
  struct SPSERIALIZEDDISPLAYPHRASE *v26; // rax
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // r14
  __int64 v29; // r12
  char *v30; // r14
  struct SPSERIALIZEDDISPLAYPHRASE *v31; // rax
  __int64 i; // rbx
  char v34; // [rsp+98h] [rbp-59h] BYREF
  char v35; // [rsp+99h] [rbp-58h] BYREF
  char v36[2]; // [rsp+9Ah] [rbp-57h] BYREF
  unsigned int v37; // [rsp+9Ch] [rbp-55h] BYREF
  struct SPPHRASEELEMENT *v38; // [rsp+A0h] [rbp-51h] BYREF
  int v39; // [rsp+A8h] [rbp-49h] BYREF
  unsigned int v40; // [rsp+ACh] [rbp-45h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-41h] BYREF
  unsigned int v42; // [rsp+B8h] [rbp-39h] BYREF
  unsigned int *v43; // [rsp+C0h] [rbp-31h] BYREF
  unsigned __int16 *v44; // [rsp+C8h] [rbp-29h] BYREF
  SPDISPLAYPHRASE v45; // [rsp+D0h] [rbp-21h] BYREF
  int v46; // [rsp+E0h] [rbp-11h] BYREF
  struct SPDISPLAYTOKEN *v47; // [rsp+E8h] [rbp-9h]
  __int64 v48; // [rsp+F0h] [rbp-1h]
  __int64 v49[8]; // [rsp+F8h] [rbp+7h] BYREF

  v6 = *((_QWORD *)this + 17);
  pv = 0;
  v47 = 0;
  LODWORD(v9) = 0;
  v44 = 0;
  v10 = 0;
  v11 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v6 + 64) + 600LL);
  *(_QWORD *)&v45.ulNumTokens = 0;
  v12 = 0;
  v38 = 0;
  v43 = 0;
  v13 = 0;
  v37 = 0;
  EnterCriticalSection(v11);
  v48 = *(_QWORD *)(*((_QWORD *)this + 17) + 456LL);
  v49[0] = 0;
  v42 = 0;
  v40 = 0;
  v46 = 0;
  v35 = 0;
  v34 = 0;
  v14 = DeserializeDisplayPhrase(a2, (struct SPDISPLAYPHRASE **)&pv);
  v15 = (struct SPDISPLAYPHRASE *)pv;
  v16 = v14;
  if ( v14 >= 0 )
  {
    v16 = PackTextFormattIng((struct SPDISPLAYPHRASE *)pv, &v44, (unsigned __int16 **)&v45, &v38, &v43, &v37);
    if ( v16 < 0 )
    {
LABEL_41:
      v13 = v37;
      v12 = v38;
      goto LABEL_42;
    }
    if ( v44 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v44[v17] );
    }
    else
    {
      v17 = 0;
    }
    v13 = v37;
    v12 = v38;
    v39 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64, _DWORD, int, struct SPPHRASEELEMENT *, unsigned int, unsigned int, __int64 *, unsigned int *, unsigned int *, int *, char *, char *, int *, const unsigned __int16 *))(*(_QWORD *)v48 + 120LL))(
            v48,
            v44,
            *(_QWORD *)&v45.ulNumTokens,
            v17,
            0,
            3,
            v38,
            v37,
            a3,
            v49,
            &v42,
            &v40,
            &v46,
            &v35,
            &v34,
            &v39,
            a4);
    if ( v16 >= 0 )
    {
      v9 = v42;
      if ( !v39 || !v42 )
        v9 = v42 + 1;
      if ( (unsigned int)v9 > a3 )
        v9 = a3;
      v18 = 24LL * v15->ulNumTokens;
      if ( !is_mul_ok(v15->ulNumTokens, 0x18u) )
        v18 = -1;
      v47 = (struct SPDISPLAYTOKEN *)CWinHeap::Alloc((CWinHeap *)&g_heap, v18, 0);
      if ( !v47 )
        goto LABEL_17;
      memset_0(v47, 0, 24LL * v15->ulNumTokens);
      v19 = 8LL * (unsigned int)v9;
      if ( !is_mul_ok((unsigned int)v9, 8u) )
        v19 = -1;
      v20 = (struct SPSERIALIZEDDISPLAYPHRASE **)CWinHeap::Alloc((CWinHeap *)&g_heap, v19, 0);
      v10 = v20;
      if ( !v20 )
      {
LABEL_17:
        v16 = -2147024882;
        goto LABEL_42;
      }
      v21 = 4;
      memset_0(v20, 0, 8 * v9);
      v22 = 0;
      v36[0] = 0;
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v48 + 200LL))(v48, v36);
      v23 = 0;
      while ( v23 < (unsigned int)v9 )
      {
        ulNumTokens = v15->ulNumTokens;
        v45.pTokens = v47;
        *(&v45.ulNumTokens + 1) = 0;
        v45.ulNumTokens = ulNumTokens;
        if ( v23 != 1 || v39 )
        {
          if ( v49[0] )
            v25 = *(struct SPPHRASEREPLACEMENT **)(v49[0] + 8 * v22);
          else
            v25 = 0;
          v16 = UnpackTextFormatting(v15, v38, v43, v37, v25, v40, v35, v34, v47, 0, SPAF_ONE_TRAILING_SPACE);
          if ( v16 < 0 )
            goto LABEL_41;
        }
        else
        {
          v16 = UnpackTextFormatting(
                  v15,
                  v38,
                  v43,
                  v37,
                  0,
                  v40,
                  v35,
                  v34,
                  v47,
                  1,
                  (enum SPDISPLYATTRIBUTES)(unsigned __int8)v36[0]);
          if ( v16 < 0 )
            goto LABEL_41;
          LODWORD(v22) = v22 - 1;
        }
        v16 = SerializeDisplayPhrase(&v45, &v10[v23]);
        if ( v16 < 0 )
          goto LABEL_40;
        v26 = v10[v23++];
        v15 = (struct SPDISPLAYPHRASE *)pv;
        v21 += (*(_DWORD *)v26 + 7) & 0xFFFFFFF8;
        v22 = (unsigned int)(v22 + 1);
      }
      v27 = (unsigned __int16 *)CoTaskMemAlloc(v21);
      v44 = v27;
      v28 = v27;
      if ( !v27 )
      {
        v16 = -2147024882;
        goto LABEL_41;
      }
      v29 = 0;
      *(_DWORD *)v27 = v9;
      if ( (_DWORD)v9 )
      {
        v30 = (char *)(v27 + 2);
        do
        {
          memcpy_0(v30, v10[v29], *(unsigned int *)v10[v29]);
          v31 = v10[v29];
          v29 = (unsigned int)(v29 + 1);
          v30 += (*(unsigned int *)v31 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
        }
        while ( (unsigned int)v29 < (unsigned int)v9 );
        v28 = v44;
      }
      *a5 = v28;
      *a6 = v21;
LABEL_40:
      v15 = (struct SPDISPLAYPHRASE *)pv;
      goto LABEL_41;
    }
  }
LABEL_42:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 600LL));
  if ( v10 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
      CoTaskMemFree(v10[i]);
    operator delete(v10);
  }
  CoTaskMemFree(v15);
  operator delete(v12);
  operator delete(v43);
  operator delete(v47);
  (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 128LL))(v48, v49[0], v13, a3);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000af64  mov     rax, rsp
0x18000af67  mov     [rax+10h], rbx
0x18000af6b  mov     [rax+20h], r9
0x18000af6f  mov     [rax+18h], r8d
0x18000af73  mov     [rax+8], rcx
0x18000af77  push    rbp
0x18000af78  push    rsi
0x18000af79  push    rdi
0x18000af7a  push    r12
0x18000af7c  push    r13
0x18000af7e  push    r14
0x18000af80  push    r15
0x18000af82  lea     rbp, [rax-4Fh]
0x18000af86  sub     rsp, 100h
0x18000af8d  mov     rax, [rcx+88h]
0x18000af94  xor     r12d, r12d
0x18000af97  mov     rdi, rcx
0x18000af9a  mov     [rbp+47h+pv], r12
0x18000af9e  mov     rbx, rdx
0x18000afa1  mov     [rbp+47h+var_50], r12
0x18000afa5  mov     esi, r12d
0x18000afa8  mov     [rbp+47h+var_70], r12
0x18000afac  mov     rcx, [rax+40h]
0x18000afb0  mov     r15d, r12d
0x18000afb3  add     rcx, 258h; lpCriticalSection
0x18000afba  mov     qword ptr [rbp+47h+var_68.ulNumTokens], r12
0x18000afbe  mov     r14d, r12d
0x18000afc1  mov     [rbp+47h+var_98], r12
0x18000afc5  mov     [rbp+47h+var_78], r12
0x18000afc9  mov     r13d, r12d
0x18000afcc  mov     [rbp+47h+var_9C], r12d
0x18000afd0  call    cs:__imp_EnterCriticalSection
0x18000afd6  mov     rax, [rdi+88h]
0x18000afdd  lea     rdx, [rbp+47h+pv]; struct SPDISPLAYPHRASE **
0x18000afe1  mov     rcx, rbx; struct SPSERIALIZEDDISPLAYPHRASE *
0x18000afe4  mov     rax, [rax+1C8h]
0x18000afeb  mov     [rbp+47h+var_48], rax
0x18000afef  mov     [rbp+47h+var_40], r12
0x18000aff3  mov     [rbp+47h+var_80], r12d
0x18000aff7  mov     [rbp+47h+var_8C], r12d
0x18000affb  mov     [rbp+47h+var_58], r12d
0x18000afff  mov     [rbp+47h+var_9F], r12b
0x18000b003  mov     [rbp+47h+var_A0], r12b
0x18000b007  call    ?DeserializeDisplayPhrase@@YAJPEBUSPSERIALIZEDDISPLAYPHRASE@@PEAPEAUSPDISPLAYPHRASE@@@Z; DeserializeDisplayPhrase(SPSERIALIZEDDISPLAYPHRASE const *,SPDISPLAYPHRASE * *)
0x18000b00c  mov     r12, [rbp+47h+pv]
0x18000b010  mov     edi, eax
0x18000b012  test    eax, eax
0x18000b014  js      loc_18000B34E
0x18000b01a  lea     rax, [rbp+47h+var_9C]
0x18000b01e  mov     rcx, r12; struct SPDISPLAYPHRASE *
0x18000b021  mov     [rsp+130h+var_108], rax; unsigned int *
0x18000b026  lea     r9, [rbp+47h+var_98]; struct SPPHRASEELEMENT **
0x18000b02a  lea     rax, [rbp+47h+var_78]
0x18000b02e  lea     r8, [rbp+47h+var_68]; unsigned __int16 **
0x18000b032  mov     [rsp+130h+var_110], rax; unsigned int **
0x18000b037  lea     rdx, [rbp+47h+var_70]; unsigned __int16 **
0x18000b03b  call    ?PackTextFormattIng@@YAJPEAUSPDISPLAYPHRASE@@PEAPEAG1PEAPEAUSPPHRASEELEMENT@@PEAPEAKPEAK@Z; PackTextFormattIng(SPDISPLAYPHRASE *,ushort * *,ushort * *,SPPHRASEELEMENT * *,ulong * *,ulong *)
0x18000b040  xor     r8d, r8d
0x18000b043  mov     edi, eax
0x18000b045  test    eax, eax
0x18000b047  js      loc_18000B346
0x18000b04d  mov     rdx, [rbp+47h+var_70]
0x18000b051  test    rdx, rdx
0x18000b054  jz      short loc_18000B066
0x18000b056  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000b05a  inc     r9
0x18000b05d  cmp     [rdx+r9*2], r8w
0x18000b062  jnz     short loc_18000B05A
0x18000b064  jmp     short loc_18000B069
0x18000b066  mov     r9d, r8d
0x18000b069  mov     r10, [rbp+47h+var_48]
0x18000b06d  mov     rcx, [rbp+47h+arg_18]
0x18000b071  mov     ebx, [rbp+47h+arg_10]
0x18000b074  mov     r13d, [rbp+47h+var_9C]
0x18000b078  mov     r14, [rbp+47h+var_98]
0x18000b07c  mov     [rsp+80h], rcx
0x18000b084  lea     rcx, [rbp+47h+var_90]
0x18000b088  mov     [rsp+130h+var_B8], rcx
0x18000b08d  lea     rcx, [rbp+47h+var_A0]
0x18000b091  mov     [rsp+130h+var_C0], rcx
0x18000b096  lea     rcx, [rbp+47h+var_9F]
0x18000b09a  mov     [rsp+130h+var_C8], rcx
0x18000b09f  lea     rcx, [rbp+47h+var_58]
0x18000b0a3  mov     [rsp+130h+var_D0], rcx
0x18000b0a8  lea     rcx, [rbp+47h+var_8C]
0x18000b0ac  mov     [rsp+130h+var_D8], rcx
0x18000b0b1  lea     rcx, [rbp+47h+var_80]
0x18000b0b5  mov     qword ptr [rsp+130h+var_E0], rcx
0x18000b0ba  lea     rcx, [rbp+47h+var_40]
0x18000b0be  mov     qword ptr [rsp+130h+var_E8], rcx
0x18000b0c3  mov     rcx, r10
0x18000b0c6  mov     dword ptr [rsp+130h+var_F0], ebx
0x18000b0ca  mov     [rbp+47h+var_90], r8d
0x18000b0ce  mov     rax, [r10]
0x18000b0d1  mov     dword ptr [rsp+130h+var_F8], r13d
0x18000b0d6  mov     qword ptr [rsp+130h+var_100], r14
0x18000b0db  mov     dword ptr [rsp+130h+var_108], 3
0x18000b0e3  mov     rax, [rax+78h]
0x18000b0e7  mov     dword ptr [rsp+130h+var_110], r8d
0x18000b0ec  mov     r8, qword ptr [rbp+47h+var_68.ulNumTokens]
0x18000b0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0f5  mov     edi, eax
0x18000b0f7  test    eax, eax
0x18000b0f9  js      loc_18000B34E
0x18000b0ff  mov     esi, [rbp+47h+var_80]
0x18000b102  cmp     [rbp+47h+var_90], r15d
0x18000b106  jz      short loc_18000B10C
0x18000b108  test    esi, esi
0x18000b10a  jnz     short loc_18000B10E
0x18000b10c  inc     esi
0x18000b10e  mov     ecx, [r12]
0x18000b112  cmp     esi, ebx
0x18000b114  mov     eax, 18h
0x18000b119  cmova   esi, ebx
0x18000b11c  mul     rcx
0x18000b11f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b126  cmovb   rax, rcx
0x18000b12a  xor     r8d, r8d; bool
0x18000b12d  mov     rdx, rax; unsigned __int64
0x18000b130  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000b137  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18000b13c  mov     [rbp+47h+var_50], rax
0x18000b140  mov     rcx, rax; void *
0x18000b143  test    rax, rax
0x18000b146  jnz     short loc_18000B152
0x18000b148  mov     edi, 8007000Eh
0x18000b14d  jmp     loc_18000B34E
0x18000b152  mov     eax, [r12]
0x18000b156  xor     edx, edx; Val
0x18000b158  lea     r8, [rax+rax*2]
0x18000b15c  shl     r8, 3; Size
0x18000b160  call    memset_0
0x18000b165  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b16c  mov     ebx, esi
0x18000b16e  mov     eax, 8
0x18000b173  mul     rbx
0x18000b176  cmovb   rax, rcx
0x18000b17a  xor     r8d, r8d; bool
0x18000b17d  mov     rdx, rax; unsigned __int64
0x18000b180  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000b187  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18000b18c  mov     r15, rax
0x18000b18f  test    rax, rax
0x18000b192  jz      short loc_18000B148
0x18000b194  lea     r8, ds:0[rsi*8]; Size
0x18000b19c  xor     edx, edx; Val
0x18000b19e  mov     rcx, rax; void *
0x18000b1a1  mov     r13d, 4
0x18000b1a7  call    memset_0
0x18000b1ac  mov     rcx, [rbp+47h+var_48]
0x18000b1b0  lea     rdx, [rbp+47h+var_9E]
0x18000b1b4  xor     ebx, ebx
0x18000b1b6  mov     [rbp+47h+var_9E], bl
0x18000b1b9  mov     rax, [rcx]
0x18000b1bc  mov     rax, [rax+0C8h]
0x18000b1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c8  xor     r10d, r10d
0x18000b1cb  mov     r14d, r10d
0x18000b1ce  cmp     r14d, esi
0x18000b1d1  jnb     loc_18000B2DF
0x18000b1d7  mov     r9, [rbp+47h+var_50]
0x18000b1db  mov     eax, [r12]
0x18000b1df  mov     [rbp+47h+var_68.pTokens], r9
0x18000b1e3  mov     dword ptr [rbp+47h+var_68+4], r10d
0x18000b1e7  mov     [rbp+47h+var_68.ulNumTokens], eax
0x18000b1ea  cmp     r14d, 1
0x18000b1ee  jnz     short loc_18000B244
0x18000b1f0  cmp     [rbp+47h+var_90], r10d
0x18000b1f4  jnz     short loc_18000B244
0x18000b1f6  movzx   eax, [rbp+47h+var_9E]
0x18000b1fa  mov     rcx, r12; struct SPDISPLAYPHRASE *
0x18000b1fd  mov     r8, [rbp+47h+var_78]; unsigned int *
0x18000b201  mov     rdx, [rbp+47h+var_98]; struct SPPHRASEELEMENT *
0x18000b205  mov     [rsp+130h+var_E0], eax; enum SPDISPLYATTRIBUTES
0x18000b209  mov     al, [rbp+47h+var_A0]
0x18000b20c  mov     [rsp+130h+var_E8], r14d; int
0x18000b211  mov     [rsp+130h+var_F0], r9; struct SPDISPLAYTOKEN *
0x18000b216  mov     r9d, [rbp+47h+var_9C]; unsigned int
0x18000b21a  mov     [rsp+130h+var_F8], al; char
0x18000b21e  mov     al, [rbp+47h+var_9F]
0x18000b221  mov     [rsp+130h+var_100], al; char
0x18000b225  mov     eax, [rbp+47h+var_8C]
0x18000b228  mov     dword ptr [rsp+130h+var_108], eax; unsigned int
0x18000b22c  mov     [rsp+130h+var_110], r10; struct SPPHRASEREPLACEMENT *
0x18000b231  call    ?UnpackTextFormatting@@YAJPEBUSPDISPLAYPHRASE@@PEBUSPPHRASEELEMENT@@PEBKKPEAUSPPHRASEREPLACEMENT@@KEEPEAUSPDISPLAYTOKEN@@HW4SPDISPLYATTRIBUTES@@@Z; UnpackTextFormatting(SPDISPLAYPHRASE const *,SPPHRASEELEMENT const *,ulong const *,ulong,SPPHRASEREPLACEMENT *,ulong,uchar,uchar,SPDISPLAYTOKEN *,int,SPDISPLYATTRIBUTES)
0x18000b236  mov     edi, eax
0x18000b238  test    eax, eax
0x18000b23a  js      loc_18000B346
0x18000b240  dec     ebx
0x18000b242  jmp     short loc_18000B2A2
0x18000b244  mov     rcx, [rbp+47h+var_40]
0x18000b248  mov     r8d, [rbp+47h+var_8C]
0x18000b24c  test    rcx, rcx
0x18000b24f  jz      short loc_18000B257
0x18000b251  mov     rdx, [rcx+rbx*8]
0x18000b255  jmp     short loc_18000B25A
0x18000b257  mov     rdx, r10
0x18000b25a  mov     al, [rbp+47h+var_A0]
0x18000b25d  mov     rcx, r12; struct SPDISPLAYPHRASE *
0x18000b260  mov     [rsp+130h+var_E0], 2; enum SPDISPLYATTRIBUTES
0x18000b268  mov     [rsp+130h+var_E8], r10d; int
0x18000b26d  mov     [rsp+130h+var_F0], r9; struct SPDISPLAYTOKEN *
0x18000b272  mov     r9d, [rbp+47h+var_9C]; unsigned int
0x18000b276  mov     [rsp+130h+var_F8], al; char
0x18000b27a  mov     al, [rbp+47h+var_9F]
0x18000b27d  mov     [rsp+130h+var_100], al; char
0x18000b281  mov     dword ptr [rsp+130h+var_108], r8d; unsigned int
0x18000b286  mov     r8, [rbp+47h+var_78]; unsigned int *
0x18000b28a  mov     [rsp+130h+var_110], rdx; struct SPPHRASEREPLACEMENT *
0x18000b28f  mov     rdx, [rbp+47h+var_98]; struct SPPHRASEELEMENT *
0x18000b293  call    ?UnpackTextFormatting@@YAJPEBUSPDISPLAYPHRASE@@PEBUSPPHRASEELEMENT@@PEBKKPEAUSPPHRASEREPLACEMENT@@KEEPEAUSPDISPLAYTOKEN@@HW4SPDISPLYATTRIBUTES@@@Z; UnpackTextFormatting(SPDISPLAYPHRASE const *,SPPHRASEELEMENT const *,ulong const *,ulong,SPPHRASEREPLACEMENT *,ulong,uchar,uchar,SPDISPLAYTOKEN *,int,SPDISPLYATTRIBUTES)
0x18000b298  mov     edi, eax
0x18000b29a  test    eax, eax
0x18000b29c  js      loc_18000B346
0x18000b2a2  mov     eax, r14d
0x18000b2a5  lea     rcx, [rbp+47h+var_68]; struct SPDISPLAYPHRASE *
0x18000b2a9  lea     r12, [r15+rax*8]
0x18000b2ad  mov     rdx, r12; struct SPSERIALIZEDDISPLAYPHRASE **
0x18000b2b0  call    ?SerializeDisplayPhrase@@YAJPEBUSPDISPLAYPHRASE@@PEAPEAUSPSERIALIZEDDISPLAYPHRASE@@@Z; SerializeDisplayPhrase(SPDISPLAYPHRASE const *,SPSERIALIZEDDISPLAYPHRASE * *)
0x18000b2b5  xor     r10d, r10d
0x18000b2b8  mov     edi, eax
0x18000b2ba  test    eax, eax
0x18000b2bc  js      loc_18000B342
0x18000b2c2  mov     rax, [r12]
0x18000b2c6  inc     r14d
0x18000b2c9  mov     r12, [rbp+47h+pv]
0x18000b2cd  mov     ecx, [rax]
0x18000b2cf  add     ecx, 7
0x18000b2d2  and     ecx, 0FFFFFFF8h
0x18000b2d5  add     r13d, ecx
0x18000b2d8  inc     ebx
0x18000b2da  jmp     loc_18000B1CE
0x18000b2df  mov     ecx, r13d; cb
0x18000b2e2  call    cs:__imp_CoTaskMemAlloc
0x18000b2e8  mov     [rbp+47h+var_70], rax
0x18000b2ec  mov     r14, rax
0x18000b2ef  test    rax, rax
0x18000b2f2  jnz     short loc_18000B2FB
0x18000b2f4  mov     edi, 8007000Eh
0x18000b2f9  jmp     short loc_18000B346
0x18000b2fb  xor     r12d, r12d
0x18000b2fe  mov     [rax], esi
0x18000b300  test    esi, esi
0x18000b302  jz      short loc_18000B334
0x18000b304  lea     r14, [rax+4]
0x18000b308  mov     rdx, [r15+r12*8]; Src
0x18000b30c  mov     rcx, r14; void *
0x18000b30f  mov     r8d, [rdx]; Size
0x18000b312  call    memcpy_0
0x18000b317  mov     rax, [r15+r12*8]
0x18000b31b  inc     r12d
0x18000b31e  mov     ecx, [rax]
0x18000b320  add     rcx, 7
0x18000b324  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000b328  add     r14, rcx
0x18000b32b  cmp     r12d, esi
0x18000b32e  jb      short loc_18000B308
0x18000b330  mov     r14, [rbp+47h+var_70]
0x18000b334  mov     rax, [rbp+47h+arg_20]
0x18000b338  mov     [rax], r14
0x18000b33b  mov     rax, [rbp+47h+arg_28]
0x18000b33f  mov     [rax], r13d
0x18000b342  mov     r12, [rbp+47h+pv]
0x18000b346  mov     r13d, [rbp+47h+var_9C]
0x18000b34a  mov     r14, [rbp+47h+var_98]
0x18000b34e  mov     rax, [rbp+47h+arg_0]
0x18000b352  mov     rax, [rax+88h]
0x18000b359  mov     rcx, [rax+40h]
0x18000b35d  add     rcx, 258h; lpCriticalSection
0x18000b364  call    cs:__imp_LeaveCriticalSection
0x18000b36a  test    r15, r15
0x18000b36d  jz      short loc_18000B38D
0x18000b36f  xor     ebx, ebx
0x18000b371  test    esi, esi
0x18000b373  jz      short loc_18000B385
0x18000b375  mov     rcx, [r15+rbx*8]; pv
0x18000b379  call    cs:__imp_CoTaskMemFree
0x18000b37f  inc     ebx
0x18000b381  cmp     ebx, esi
0x18000b383  jb      short loc_18000B375
0x18000b385  mov     rcx, r15; void *
0x18000b388  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b38d  mov     rcx, r12; pv
0x18000b390  call    cs:__imp_CoTaskMemFree
0x18000b396  mov     rcx, r14; void *
0x18000b399  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b39e  mov     rcx, [rbp+47h+var_78]; void *
0x18000b3a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3a7  mov     rcx, [rbp+47h+var_50]; void *
0x18000b3ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3b0  mov     rcx, [rbp+47h+var_48]
0x18000b3b4  mov     r8d, r13d
0x18000b3b7  mov     r9d, [rbp+47h+arg_10]
0x18000b3bb  mov     rdx, [rbp+47h+var_40]
0x18000b3bf  mov     rax, [rcx]
0x18000b3c2  mov     rax, [rax+80h]
0x18000b3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ce  mov     rbx, [rsp+130h+arg_8]
0x18000b3d6  mov     eax, edi
0x18000b3d8  add     rsp, 100h
  ... truncated ...
```
