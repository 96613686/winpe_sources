# CEngineLocaleHandlerJPN::CheckWord(ushort const *,tagMSASRCheckWord *,ushort * *)

- ea: `0x1800db250`
- end: `0x1800db520`
- name: `?CheckWord@CEngineLocaleHandlerJPN@@UEAAJPEBGPEAW4tagMSASRCheckWord@@PEAPEAG@Z`
- size: `720`
- prototype: `__int64 __fastcall(CEngineLocaleHandlerJPN *__hidden this, const unsigned __int16 *, enum tagMSASRCheckWord *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004312`
- `0x180006b20`
- `0x1800c91c4`
- `0x1800db250`
- `0x1800dbfb4`
- `0x1800dc380`
- `0x1800dc5c8`
- `0x1800e06a0`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800db3a4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800db3a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800db4d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800db4e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800db4d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800db4e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db4b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db4b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEngineLocaleHandlerJPN::CheckWord(
        CEngineLocaleHandlerJPN *this,
        const unsigned __int16 *a2,
        enum tagMSASRCheckWord *a3,
        unsigned __int16 **a4)
{
  int v6; // ebx
  OLECHAR *v7; // r14
  __int64 v8; // rcx
  int v9; // esi
  int ReverseConverter; // edi
  int v11; // r12d
  int v12; // ebx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  BSTR v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rbx
  unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // r9
  int v22; // r8d
  LPVOID pv; // [rsp+38h] [rbp-39h] BYREF
  struct CReverseConverter *v25[2]; // [rsp+40h] [rbp-31h] BYREF
  __int128 v26; // [rsp+50h] [rbp-21h] BYREF
  __int64 v27; // [rsp+60h] [rbp-11h]
  char v28[96]; // [rsp+68h] [rbp-9h] BYREF

  v6 = 0;
  v7 = 0;
  if ( (unsigned int)IsPureEnglish(a2) )
  {
    ReverseConverter = 0;
    goto LABEL_31;
  }
  v26 = 0;
  v27 = 0;
  v8 = *((_QWORD *)this + 6);
  v9 = 1;
  if ( v8 )
  {
    ReverseConverter = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, __int64, __int128 *))(*(_QWORD *)v8 + 24LL))(
                         v8,
                         a2,
                         *((unsigned __int16 *)this + 20),
                         1,
                         &v26);
    if ( ReverseConverter >= 0 )
    {
      v11 = 0;
      goto LABEL_26;
    }
  }
  v11 = 1;
  v12 = CWordParserJPN::Extract(v25, a2, v28);
  v25[0] = 0;
  ReverseConverter = CEngineLocaleHandlerJPN::GetReverseConverter(this, v25);
  if ( v12 != 3 && ReverseConverter >= 0 )
  {
    pv = 0;
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    if ( (int)v13 == v13 )
    {
      ReverseConverter = (*(__int64 (__fastcall **)(struct CReverseConverter *, const unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)v25[0] + 40LL))(
                           v25[0],
                           a2,
                           (unsigned int)v13,
                           &pv);
      if ( !ReverseConverter )
      {
        v11 = 0;
        if ( *((_DWORD *)pv + 16) == 1
          && (v14 = *((_QWORD *)pv + 7), (unsigned __int16)(*(_WORD *)(v14 + 12) - 106) <= 0xDu) )
        {
          v15 = *(unsigned __int16 *)(v14 + 4);
          v16 = (unsigned int)(v13 + 2 * v15 + 5);
          if ( v16 != v13 + 2 * v15 + 5 )
            goto LABEL_23;
          v17 = SysAllocStringLen(0, v16);
          v7 = v17;
          if ( !v17 )
            goto LABEL_23;
          *v17 = 47;
          memcpy_0(v17 + 1, a2, 2 * v13 + 2);
          v7[v13 + 1] = 47;
          memcpy_0(
            &v7[v13 + 2],
            (const void *)(*(_QWORD *)((char *)pv + 4) + 2LL * **((unsigned __int16 **)pv + 7)),
            *(unsigned __int16 *)(*((_QWORD *)pv + 7) + 4LL));
          v18 = v13 + *(unsigned __int16 *)(*((_QWORD *)pv + 7) + 4LL);
          v7[v18 + 2] = 59;
          v19 = v18 + 3;
          v7[v18 + 3] = 0;
          ReverseConverter = CEngineLocaleHandler::EnsureLookupLexicon(this);
          if ( ReverseConverter < 0
            || (ReverseConverter = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, __int64, __int128 *))(**((_QWORD **)this + 9) + 24LL))(
                                     *((_QWORD *)this + 9),
                                     v7,
                                     *((unsigned __int16 *)this + 20),
                                     4096,
                                     &v26),
                ReverseConverter < 0) )
          {
            v7[v19 - 1] = 47;
            v20 = (unsigned __int16 *)*((_QWORD *)pv + 7);
            v21 = (unsigned __int16 *)(*(_QWORD *)((char *)pv + 4) + 2LL * *v20);
            if ( v20[2] )
            {
              do
                v7[v19++] = CEngineLocaleHandlerJPN::KatakanaFromHiragana(*v21);
              while ( v22 != 1 );
            }
            *(_DWORD *)&v7[v19] = 59;
            v11 = 1;
            goto LABEL_23;
          }
          v6 = 0;
        }
        else
        {
          v6 = 0;
        }
LABEL_24:
        CoTaskMemFree(pv);
        goto LABEL_26;
      }
    }
    else
    {
      ReverseConverter = -2147024882;
    }
LABEL_23:
    v6 = 1;
    goto LABEL_24;
  }
  v6 = 1;
LABEL_26:
  CWordPronunciationList::~CWordPronunciationList((CWordPronunciationList *)&v26);
  if ( ReverseConverter < 0 )
  {
    SysFreeString(v7);
    v7 = 0;
    goto LABEL_32;
  }
  if ( v11 )
  {
LABEL_31:
    v9 = 0;
    goto LABEL_32;
  }
  SysFreeString(v7);
  v7 = 0;
  v9 = v6 + 1;
LABEL_32:
  *(_DWORD *)a3 = v9;
  *a4 = v7;
  return (unsigned int)ReverseConverter;
}

```

## disassembly

```asm
0x1800db250  mov     rax, rsp
0x1800db253  mov     [rax+8], rbx
0x1800db257  mov     [rax+20h], r9
0x1800db25b  mov     [rax+18h], r8
0x1800db25f  push    rbp
0x1800db260  push    rsi
0x1800db261  push    rdi
0x1800db262  push    r12
0x1800db264  push    r13
0x1800db266  push    r14
0x1800db268  push    r15
0x1800db26a  lea     rbp, [rax-5Fh]
0x1800db26e  sub     rsp, 90h
0x1800db275  mov     r15, rdx
0x1800db278  mov     r13, rcx
0x1800db27b  xor     ebx, ebx
0x1800db27d  mov     r14d, ebx
0x1800db280  mov     rcx, rdx; unsigned __int16 *
0x1800db283  call    ?IsPureEnglish@@YAHPEBG@Z; IsPureEnglish(ushort const *)
0x1800db288  test    eax, eax
0x1800db28a  jnz     loc_1800DB4F2
0x1800db290  xorps   xmm0, xmm0
0x1800db293  xor     eax, eax
0x1800db295  movups  [rbp+57h+var_78], xmm0
0x1800db299  mov     [rbp+57h+var_68], rax
0x1800db29d  mov     rcx, [r13+30h]
0x1800db2a1  lea     esi, [rbx+1]
0x1800db2a4  test    rcx, rcx
0x1800db2a7  jz      short loc_1800DB2D7
0x1800db2a9  mov     rax, [rcx]
0x1800db2ac  lea     rdx, [rbp+57h+var_78]
0x1800db2b0  mov     [rsp+20h], rdx
0x1800db2b5  mov     r9d, esi
0x1800db2b8  movzx   r8d, word ptr [r13+28h]
0x1800db2bd  mov     rdx, r15
0x1800db2c0  mov     rax, [rax+18h]
0x1800db2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db2c9  mov     edi, eax
0x1800db2cb  test    eax, eax
0x1800db2cd  js      short loc_1800DB2D7
0x1800db2cf  mov     r12d, ebx
0x1800db2d2  jmp     loc_1800DB4BA
0x1800db2d7  mov     r12d, esi
0x1800db2da  lea     r8, [rbp+57h+var_60]
0x1800db2de  mov     rdx, r15
0x1800db2e1  lea     rcx, [rbp+57h+var_88]
0x1800db2e5  call    ?Extract@CWordParserJPN@@UEAA?AW4tagWordFormat@@PEBGPEAUWordFeatures_t@@@Z; CWordParserJPN::Extract(ushort const *,WordFeatures_t *)
0x1800db2ea  mov     ebx, eax
0x1800db2ec  mov     [rbp+57h+var_88], 0
0x1800db2f4  lea     rdx, [rbp+57h+var_88]; struct CReverseConverter **
0x1800db2f8  mov     rcx, r13; this
0x1800db2fb  call    ?GetReverseConverter@CEngineLocaleHandlerJPN@@QEAAJPEAPEAVCReverseConverter@@@Z; CEngineLocaleHandlerJPN::GetReverseConverter(CReverseConverter * *)
0x1800db300  mov     edi, eax
0x1800db302  cmp     ebx, 3
0x1800db305  jz      loc_1800DB4B8
0x1800db30b  xor     eax, eax
0x1800db30d  test    edi, edi
0x1800db30f  js      loc_1800DB4B8
0x1800db315  mov     [rbp+57h+pv], rax
0x1800db319  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800db31d  inc     rbx
0x1800db320  cmp     [r15+rbx*2], ax
0x1800db325  jnz     short loc_1800DB31D
0x1800db327  movsxd  rax, ebx
0x1800db32a  cmp     rax, rbx
0x1800db32d  jz      short loc_1800DB339
0x1800db32f  mov     edi, 8007000Eh
0x1800db334  jmp     loc_1800DB4AA
0x1800db339  mov     rcx, [rbp+57h+var_88]
0x1800db33d  mov     rax, [rcx]
0x1800db340  lea     r9, [rbp+57h+pv]
0x1800db344  mov     r8d, ebx
0x1800db347  mov     rdx, r15
0x1800db34a  mov     rax, [rax+28h]
0x1800db34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db353  mov     edi, eax
0x1800db355  xor     edx, edx
0x1800db357  test    eax, eax
0x1800db359  jnz     loc_1800DB4AA
0x1800db35f  mov     r12d, edx
0x1800db362  mov     rax, [rbp+57h+pv]
0x1800db366  cmp     [rax+40h], esi
0x1800db369  jz      short loc_1800DB372
0x1800db36b  mov     ebx, edx
0x1800db36d  jmp     loc_1800DB4AC
0x1800db372  mov     rax, [rbp+57h+pv]
0x1800db376  mov     rcx, [rax+38h]
0x1800db37a  movzx   eax, word ptr [rcx+0Ch]
0x1800db37e  sub     ax, 6Ah ; 'j'
0x1800db382  cmp     ax, 0Dh
0x1800db386  ja      short loc_1800DB36B
0x1800db388  movzx   eax, word ptr [rcx+4]
0x1800db38c  lea     rcx, ds:5[rax*2]
0x1800db394  add     rcx, rbx
0x1800db397  mov     edx, ecx; ui
0x1800db399  cmp     rdx, rcx
0x1800db39c  jnz     loc_1800DB4AA
0x1800db3a2  xor     ecx, ecx; strIn
0x1800db3a4  call    cs:__imp_SysAllocStringLen
0x1800db3aa  mov     r14, rax
0x1800db3ad  test    rax, rax
0x1800db3b0  jz      loc_1800DB4AA
0x1800db3b6  mov     edi, 2Fh ; '/'
0x1800db3bb  mov     [rax], di
0x1800db3be  lea     r8, ds:2[rbx*2]; Size
0x1800db3c6  lea     rcx, [rax+2]; void *
0x1800db3ca  mov     rdx, r15; Src
0x1800db3cd  call    memcpy_0
0x1800db3d2  mov     [r14+rbx*2+2], di
0x1800db3d8  mov     rdx, [rbp+57h+pv]
0x1800db3dc  mov     rax, [rdx+38h]
0x1800db3e0  movzx   r8d, word ptr [rax+4]; Size
0x1800db3e5  movzx   ecx, word ptr [rax]
0x1800db3e8  mov     rax, [rdx+4]
0x1800db3ec  lea     rdx, [rax+rcx*2]; Src
0x1800db3f0  lea     rcx, [r14+4]
0x1800db3f4  lea     rcx, [rcx+rbx*2]; void *
0x1800db3f8  call    memcpy_0
0x1800db3fd  mov     rax, [rbp+57h+pv]
0x1800db401  mov     rcx, [rax+38h]
0x1800db405  movzx   ecx, word ptr [rcx+4]
0x1800db409  add     rcx, rbx
0x1800db40c  mov     word ptr [r14+rcx*2+4], 3Bh ; ';'
0x1800db414  lea     rbx, [rcx+3]
0x1800db418  xor     r15d, r15d
0x1800db41b  mov     [r14+rbx*2], r15w
0x1800db420  mov     rcx, r13; this
0x1800db423  call    ?EnsureLookupLexicon@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureLookupLexicon(void)
0x1800db428  mov     edi, eax
0x1800db42a  test    eax, eax
0x1800db42c  js      short loc_1800DB460
0x1800db42e  mov     rcx, [r13+48h]
0x1800db432  mov     rax, [rcx]
0x1800db435  lea     rdx, [rbp+57h+var_78]
0x1800db439  mov     [rsp+20h], rdx
0x1800db43e  mov     r9d, 1000h
0x1800db444  movzx   r8d, word ptr [r13+28h]
0x1800db449  mov     rdx, r14
0x1800db44c  mov     rax, [rax+18h]
0x1800db450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db455  mov     edi, eax
0x1800db457  test    eax, eax
0x1800db459  js      short loc_1800DB460
0x1800db45b  mov     ebx, r15d
0x1800db45e  jmp     short loc_1800DB4AC
0x1800db460  mov     word ptr [r14+rbx*2-2], 2Fh ; '/'
0x1800db468  mov     rax, [rbp+57h+pv]
0x1800db46c  mov     rdx, [rax+38h]
0x1800db470  movzx   ecx, word ptr [rdx]
0x1800db473  mov     rax, [rax+4]
0x1800db477  lea     r9, [rax+rcx*2]
0x1800db47b  movzx   r8d, word ptr [rdx+4]
0x1800db480  test    r8d, r8d
0x1800db483  jz      short loc_1800DB49F
0x1800db485  movzx   ecx, word ptr [r9]; unsigned __int16
0x1800db489  lea     r9, [r9+2]
0x1800db48d  call    ?KatakanaFromHiragana@CEngineLocaleHandlerJPN@@SAGG@Z; CEngineLocaleHandlerJPN::KatakanaFromHiragana(ushort)
0x1800db492  mov     [r14+rbx*2], ax
0x1800db497  add     rbx, rsi
0x1800db49a  sub     r8d, esi
0x1800db49d  jnz     short loc_1800DB485
0x1800db49f  mov     dword ptr [r14+rbx*2], 3Bh ; ';'
0x1800db4a7  mov     r12d, esi
0x1800db4aa  mov     ebx, esi
0x1800db4ac  mov     rcx, [rbp+57h+pv]; pv
0x1800db4b0  call    cs:__imp_CoTaskMemFree
0x1800db4b6  jmp     short loc_1800DB4BA
0x1800db4b8  mov     ebx, esi
0x1800db4ba  lea     rcx, [rbp+57h+var_78]; this
0x1800db4be  call    ??1CWordPronunciationList@@QEAA@XZ; CWordPronunciationList::~CWordPronunciationList(void)
0x1800db4c3  xor     r15d, r15d
0x1800db4c6  test    edi, edi
0x1800db4c8  js      short loc_1800DB4E4
0x1800db4ca  test    r12d, r12d
0x1800db4cd  jz      short loc_1800DB4D3
0x1800db4cf  xor     ebx, ebx
0x1800db4d1  jmp     short loc_1800DB4F4
0x1800db4d3  mov     rcx, r14; bstrString
0x1800db4d6  call    cs:__imp_SysFreeString
0x1800db4dc  mov     r14, r15
0x1800db4df  lea     esi, [rbx+1]
0x1800db4e2  jmp     short loc_1800DB4F6
0x1800db4e4  mov     rcx, r14; bstrString
0x1800db4e7  call    cs:__imp_SysFreeString
0x1800db4ed  mov     r14, r15
0x1800db4f0  jmp     short loc_1800DB4F6
0x1800db4f2  mov     edi, ebx
0x1800db4f4  mov     esi, ebx
0x1800db4f6  mov     rax, [rbp+57h+arg_10]
0x1800db4fa  mov     [rax], esi
0x1800db4fc  mov     rax, [rbp+57h+arg_18]
0x1800db500  mov     [rax], r14
0x1800db503  mov     eax, edi
0x1800db505  mov     rbx, [rsp+0C0h+arg_0]
0x1800db50d  add     rsp, 90h
0x1800db514  pop     r15
0x1800db516  pop     r14
0x1800db518  pop     r13
0x1800db51a  pop     r12
0x1800db51c  pop     rdi
0x1800db51d  pop     rsi
0x1800db51e  pop     rbp
0x1800db51f  retn
```
