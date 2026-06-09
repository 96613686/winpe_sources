# PHN_DICT::SRIdToSAPIId_BSTR(ushort * const,ushort * *)

- ea: `0x1800ae7e4`
- end: `0x1800aeac9`
- name: `?SRIdToSAPIId_BSTR@PHN_DICT@@QEBAJQEAGPEAPEAG@Z`
- size: `741`
- prototype: `int(PHN_DICT *__hidden this, unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800c8360`

## callees

- `0x180002470`
- `0x180002e00`
- `0x1800041d0`
- `0x1800060c0`
- `0x1800ae260`
- `0x1800ae7e4`
- `0x1800ba6b4`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aea08`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aea2e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aea44`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aea08`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aea2e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aea44`
- `OLEAUT32!__imp_SysStringLen` at `0x1800ae809`
- `OLEAUT32!__imp_SysStringLen` at `0x1800ae809`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aea8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aea8b`

## pseudocode

```c
__int64 __fastcall PHN_DICT::SRIdToSAPIId_BSTR(PHN_DICT *this, unsigned __int16 *const a2, unsigned __int16 **a3)
{
  UINT v5; // eax
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rbx
  SIZE_T v9; // rax
  struct ITextNormMultiResult *v10; // r15
  OLECHAR *v11; // r14
  unsigned __int16 *v12; // rdi
  int v13; // ebx
  __int64 v14; // rax
  int InputTape; // eax
  PHN_DICT *v16; // rcx
  struct InputTape *v17; // r12
  wchar_t *v18; // rax
  unsigned __int64 v19; // rdx
  UINT v20; // esi
  wchar_t *v21; // r13
  char v22; // r9
  unsigned __int64 v23; // rcx
  wchar_t *v24; // r8
  SIZE_T v25; // rax
  UINT v26; // edi
  __int64 v27; // rax
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rax
  struct InputTape *v30; // [rsp+30h] [rbp-20h] BYREF
  struct ITextNormMultiResult *v31; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v32; // [rsp+40h] [rbp-10h]
  wchar_t *Buffer; // [rsp+A8h] [rbp+58h] BYREF

  v5 = SysStringLen(a2);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
    return 2147942487LL;
  v31 = 0;
  Buffer = 0;
  v9 = 2 * (4LL * v5 + 1);
  v10 = 0;
  v11 = 0;
  if ( !is_mul_ok(4 * v7 + 1, 2u) )
    v9 = -1;
  v32 = (unsigned __int16 *)CWinHeap::Alloc(&g_heap, v9, 0);
  v12 = v32;
  v30 = 0;
  if ( v32 )
  {
    if ( v7 )
    {
      do
      {
        StringCchPrintfW(v12, 5u, L"%d ", a2[v6]);
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
        ++v6;
        v12 += v14;
      }
      while ( v6 < v7 );
    }
    v12 = v32;
    InputTape = ITransducer::GetInputTape(*((_QWORD *)this + 21), (__int64)v32, 1u, &v30, 0);
    v17 = v30;
    v13 = InputTape;
    if ( InputTape < 0 )
    {
LABEL_39:
      if ( v17 )
        (**(void (__fastcall ***)(struct InputTape *, __int64))v17)(v17, 1);
      if ( v10 )
        (*(void (__fastcall **)(struct ITextNormMultiResult *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_43;
    }
    v13 = PHN_DICT::ReceiveString(v16, v30, *((struct ITransducer **)this + 21), &v31);
    if ( v13 < 0 )
    {
      v29 = SysAllocStringLen(&word_18010FB50, 0);
      v10 = v31;
    }
    else
    {
      v10 = v31;
      v13 = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, wchar_t **))(*(_QWORD *)v31 + 24LL))(v31, &Buffer);
      if ( v13 < 0 )
        goto LABEL_39;
      v18 = Buffer;
      v19 = -1;
      do
        ++v19;
      while ( Buffer[v19] );
      if ( v19 )
      {
        v20 = 1;
        v21 = Buffer;
        v22 = 0;
        v23 = 0;
        while ( 1 )
        {
          v24 = &v18[v23++];
          if ( *v24 != 32 )
            break;
          if ( v23 >= v19 )
          {
LABEL_21:
            v25 = 2LL * (v20 + 1);
            if ( !is_mul_ok(v20 + 1, 2u) )
              v25 = -1;
            v11 = (OLECHAR *)CWinHeap::Alloc(&g_heap, v25, 0);
            if ( v11 )
            {
              v26 = 0;
              if ( v20 )
              {
                do
                {
                  swscanf_s(v21, L"%04x", &v11[v26]);
                  v27 = -1;
                  do
                    ++v27;
                  while ( v21[v27] );
                  ++v26;
                  v21 += v27 + 1;
                }
                while ( v26 < v20 );
                v17 = v30;
              }
              v11[v20] = 0;
              v28 = SysAllocStringLen(v11, v20);
              v12 = v32;
              *a3 = v28;
              if ( !v28 )
                v13 = -2147024882;
            }
            else
            {
              v13 = -2147024882;
            }
            goto LABEL_39;
          }
          if ( v24[1] == 32 || !v22 )
          {
LABEL_20:
            if ( v23 >= v19 )
              goto LABEL_21;
          }
          else
          {
            *v24 = 0;
            ++v20;
            v18 = Buffer;
          }
        }
        v22 = 1;
        goto LABEL_20;
      }
      v29 = SysAllocStringLen(&word_18010FB50, 0);
      v13 = -2147196928;
    }
    *a3 = v29;
    goto LABEL_39;
  }
  v13 = -2147024882;
LABEL_43:
  if ( Buffer )
  {
    CoTaskMemFree(Buffer);
    Buffer = 0;
  }
  if ( v12 )
    operator delete(v12);
  if ( v11 )
    operator delete(v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800ae7e4  mov     [rsp-38h+arg_0], rbx
0x1800ae7e9  mov     [rsp-38h+arg_10], r8
0x1800ae7ee  push    rbp
0x1800ae7ef  push    rsi
0x1800ae7f0  push    rdi
0x1800ae7f1  push    r12
0x1800ae7f3  push    r13
0x1800ae7f5  push    r14
0x1800ae7f7  push    r15
0x1800ae7f9  mov     rbp, rsp
0x1800ae7fc  sub     rsp, 50h
0x1800ae800  mov     r13, rcx
0x1800ae803  mov     r12, rdx
0x1800ae806  mov     rcx, rdx; pbstr
0x1800ae809  call    cs:__imp_SysStringLen
0x1800ae80f  xor     esi, esi
0x1800ae811  mov     ebx, eax
0x1800ae813  test    eax, eax
0x1800ae815  jnz     short loc_1800AE821
0x1800ae817  mov     eax, 80070057h
0x1800ae81c  jmp     loc_1800AEAB1
0x1800ae821  lea     rcx, ds:1[rbx*4]
0x1800ae829  mov     [rbp+var_18], rsi
0x1800ae82d  mov     eax, 2
0x1800ae832  mov     [rbp+Buffer], rsi
0x1800ae836  mul     rcx
0x1800ae839  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ae840  mov     r15, rsi
0x1800ae843  mov     r14, rsi
0x1800ae846  cmovb   rax, rcx
0x1800ae84a  xor     r8d, r8d; bool
0x1800ae84d  mov     rdx, rax; unsigned __int64
0x1800ae850  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800ae857  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800ae85c  mov     [rbp+var_10], rax
0x1800ae860  mov     rdi, rax
0x1800ae863  mov     [rbp+var_20], rsi
0x1800ae867  test    rax, rax
0x1800ae86a  jnz     short loc_1800AE876
0x1800ae86c  mov     ebx, 8007000Eh
0x1800ae871  jmp     loc_1800AEA82
0x1800ae876  test    rbx, rbx
0x1800ae879  jz      short loc_1800AE8AF
0x1800ae87b  movzx   r9d, word ptr [r12+rsi*2]
0x1800ae880  lea     r8, aD_2; "%d "
0x1800ae887  mov     edx, 5; unsigned __int64
0x1800ae88c  mov     rcx, rdi; unsigned __int16 *
0x1800ae88f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ae894  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ae898  xor     ecx, ecx
0x1800ae89a  inc     rax
0x1800ae89d  cmp     [rdi+rax*2], cx
0x1800ae8a1  jnz     short loc_1800AE89A
0x1800ae8a3  inc     rsi
0x1800ae8a6  lea     rdi, [rdi+rax*2]
0x1800ae8aa  cmp     rsi, rbx
0x1800ae8ad  jb      short loc_1800AE87B
0x1800ae8af  mov     rdi, [rbp+var_10]
0x1800ae8b3  lea     r9, [rbp+var_20]
0x1800ae8b7  mov     rcx, [r13+0A8h]
0x1800ae8be  xor     esi, esi
0x1800ae8c0  mov     rdx, rdi
0x1800ae8c3  mov     [rsp+50h+var_30], rsi
0x1800ae8c8  lea     r8d, [rsi+1]
0x1800ae8cc  call    ?GetInputTape@ITransducer@@QEBAJPEBGW4INPUT_TYPE@InputTape@@PEAPEAV3@PEAUIAttributeLexicon@@W4TN_BOUNDARY@@@Z; ITransducer::GetInputTape(ushort const *,InputTape::INPUT_TYPE,InputTape * *,IAttributeLexicon *,TN_BOUNDARY)
0x1800ae8d1  mov     r12, [rbp+var_20]
0x1800ae8d5  mov     ebx, eax
0x1800ae8d7  test    eax, eax
0x1800ae8d9  js      loc_1800AEA55
0x1800ae8df  mov     r8, [r13+0A8h]; struct ITransducer *
0x1800ae8e6  lea     r9, [rbp+var_18]; struct ITextNormMultiResult **
0x1800ae8ea  mov     rdx, r12; struct InputTape *
0x1800ae8ed  call    ?ReceiveString@PHN_DICT@@IEBAJPEBVInputTape@@PEAVITransducer@@PEAPEAUITextNormMultiResult@@@Z; PHN_DICT::ReceiveString(InputTape const *,ITransducer *,ITextNormMultiResult * *)
0x1800ae8f2  mov     ebx, eax
0x1800ae8f4  test    eax, eax
0x1800ae8f6  js      loc_1800AEA3B
0x1800ae8fc  mov     r15, [rbp+var_18]
0x1800ae900  lea     rdx, [rbp+Buffer]
0x1800ae904  mov     rcx, r15
0x1800ae907  mov     rax, [r15]
0x1800ae90a  mov     rax, [rax+18h]
0x1800ae90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae913  mov     ebx, eax
0x1800ae915  test    eax, eax
0x1800ae917  js      loc_1800AEA55
0x1800ae91d  mov     rax, [rbp+Buffer]
0x1800ae921  or      r11, 0FFFFFFFFFFFFFFFFh
0x1800ae925  mov     rdx, r11
0x1800ae928  inc     rdx; ui
0x1800ae92b  cmp     [rax+rdx*2], si
0x1800ae92f  jnz     short loc_1800AE928
0x1800ae931  test    rdx, rdx
0x1800ae934  jz      loc_1800AEA27
0x1800ae93a  xor     r10d, r10d
0x1800ae93d  mov     esi, 1
0x1800ae942  mov     r13, rax
0x1800ae945  mov     r9b, r10b
0x1800ae948  mov     ecx, r10d
0x1800ae94b  test    rdx, rdx
0x1800ae94e  jz      short loc_1800AE966
0x1800ae950  lea     r8, [rax+rcx*2]
0x1800ae954  inc     rcx
0x1800ae957  cmp     word ptr [r8], 20h ; ' '
0x1800ae95c  jz      short loc_1800AE99D
0x1800ae95e  mov     r9b, 1
0x1800ae961  cmp     rcx, rdx
0x1800ae964  jb      short loc_1800AE950
0x1800ae966  lea     edx, [rsi+1]
0x1800ae969  mov     eax, 2
0x1800ae96e  mul     rdx
0x1800ae971  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800ae978  cmovb   rax, r11
0x1800ae97c  xor     r8d, r8d; bool
0x1800ae97f  mov     rdx, rax; unsigned __int64
0x1800ae982  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800ae987  mov     r14, rax
0x1800ae98a  xor     eax, eax
0x1800ae98c  test    r14, r14
0x1800ae98f  jnz     short loc_1800AE9BB
0x1800ae991  mov     ebx, 8007000Eh
0x1800ae996  xor     esi, esi
0x1800ae998  jmp     loc_1800AEA55
0x1800ae99d  cmp     rcx, rdx
0x1800ae9a0  jnb     short loc_1800AE966
0x1800ae9a2  cmp     word ptr [r8+2], 20h ; ' '
0x1800ae9a8  jz      short loc_1800AE961
0x1800ae9aa  test    r9b, r9b
0x1800ae9ad  jz      short loc_1800AE961
0x1800ae9af  mov     [r8], r10w
0x1800ae9b3  inc     esi
0x1800ae9b5  mov     rax, [rbp+Buffer]
0x1800ae9b9  jmp     short loc_1800AE950
0x1800ae9bb  mov     edi, eax
0x1800ae9bd  test    esi, esi
0x1800ae9bf  jz      short loc_1800AE9FC
0x1800ae9c1  mov     eax, edi
0x1800ae9c3  lea     rdx, a04x_0; "%04x"
0x1800ae9ca  mov     rcx, r13; Buffer
0x1800ae9cd  lea     r8, [r14+rax*2]
0x1800ae9d1  call    swscanf_s
0x1800ae9d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ae9da  xor     ecx, ecx
0x1800ae9dc  inc     rax
0x1800ae9df  cmp     [r13+rax*2+0], cx
0x1800ae9e5  jnz     short loc_1800AE9DC
0x1800ae9e7  lea     r13, [r13+rax*2+0]
0x1800ae9ec  inc     edi
0x1800ae9ee  add     r13, 2
0x1800ae9f2  cmp     edi, esi
0x1800ae9f4  jb      short loc_1800AE9C1
0x1800ae9f6  mov     r12, [rbp+var_20]
0x1800ae9fa  xor     eax, eax
0x1800ae9fc  mov     ecx, esi
0x1800ae9fe  mov     edx, esi; ui
0x1800aea00  mov     [r14+rcx*2], ax
0x1800aea05  mov     rcx, r14; strIn
0x1800aea08  call    cs:__imp_SysAllocStringLen
0x1800aea0e  mov     rcx, [rbp+arg_10]
0x1800aea12  xor     esi, esi
0x1800aea14  mov     rdi, [rbp+var_10]
0x1800aea18  mov     [rcx], rax
0x1800aea1b  test    rax, rax
0x1800aea1e  jnz     short loc_1800AEA55
0x1800aea20  mov     ebx, 8007000Eh
0x1800aea25  jmp     short loc_1800AEA55
0x1800aea27  lea     rcx, word_18010FB50; strIn
0x1800aea2e  call    cs:__imp_SysAllocStringLen
0x1800aea34  mov     ebx, 80046000h
0x1800aea39  jmp     short loc_1800AEA4E
0x1800aea3b  xor     edx, edx; ui
0x1800aea3d  lea     rcx, word_18010FB50; strIn
0x1800aea44  call    cs:__imp_SysAllocStringLen
0x1800aea4a  mov     r15, [rbp+var_18]
0x1800aea4e  mov     rcx, [rbp+arg_10]
0x1800aea52  mov     [rcx], rax
0x1800aea55  test    r12, r12
0x1800aea58  jz      short loc_1800AEA6E
0x1800aea5a  mov     rax, [r12]
0x1800aea5e  mov     edx, 1
0x1800aea63  mov     rcx, r12
0x1800aea66  mov     rax, [rax]
0x1800aea69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea6e  test    r15, r15
0x1800aea71  jz      short loc_1800AEA82
0x1800aea73  mov     rax, [r15]
0x1800aea76  mov     rcx, r15
0x1800aea79  mov     rax, [rax+10h]
0x1800aea7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea82  mov     rcx, [rbp+Buffer]; pv
0x1800aea86  test    rcx, rcx
0x1800aea89  jz      short loc_1800AEA95
0x1800aea8b  call    cs:__imp_CoTaskMemFree
0x1800aea91  mov     [rbp+Buffer], rsi
0x1800aea95  test    rdi, rdi
0x1800aea98  jz      short loc_1800AEAA2
0x1800aea9a  mov     rcx, rdi; void *
0x1800aea9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aeaa2  test    r14, r14
0x1800aeaa5  jz      short loc_1800AEAAF
0x1800aeaa7  mov     rcx, r14; void *
0x1800aeaaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aeaaf  mov     eax, ebx
0x1800aeab1  mov     rbx, [rsp+50h+arg_0]
0x1800aeab9  add     rsp, 50h
0x1800aeabd  pop     r15
0x1800aeabf  pop     r14
0x1800aeac1  pop     r13
0x1800aeac3  pop     r12
0x1800aeac5  pop     rdi
0x1800aeac6  pop     rsi
0x1800aeac7  pop     rbp
0x1800aeac8  retn
```
