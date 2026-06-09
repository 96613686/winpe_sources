# CRecoExt::GetPronunciationsInternal(ushort const *,ushort const *,ushort const *,ushort,ulong,int,SPWORDPRONUNCIATIONLIST *)

- ea: `0x18000500c`
- end: `0x180005270`
- name: `?GetPronunciationsInternal@CRecoExt@@AEAAJPEBG00GKHPEAUSPWORDPRONUNCIATIONLIST@@@Z`
- size: `612`
- prototype: `int(CRecoExt *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, unsigned int, int, struct SPWORDPRONUNCIATIONLIST *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004f90`
- `0x180004fd0`

## callees

- `0x180001c50`
- `0x1800031c8`
- `0x180003774`
- `0x180004da0`
- `0x18000500c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005239`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecoExt::GetPronunciationsInternal(
        CRecoExt *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 a5,
        unsigned int a6,
        int a7,
        struct SPWORDPRONUNCIATIONLIST *a8)
{
  struct SPWORDPRONUNCIATIONLIST *v10; // rdi
  unsigned __int64 v11; // rbx
  unsigned int v12; // r15d
  SIZE_T v13; // r8
  __int64 v14; // r12
  int v15; // ebx
  char *v16; // rax
  void *v17; // r14
  CRecoExt *v18; // rcx
  SPWORDPRONUNCIATION *v19; // r8
  enum SPLEXICONTYPE v20; // eax
  __int64 v21; // r8
  CRecoExt *v22; // r9
  CRecoExt *v23; // rcx
  enum SPLEXICONTYPE v24; // eax
  __int64 v25; // r8
  __int64 v26; // rcx
  int v27; // eax
  unsigned __int16 *v28; // rax
  char *v29; // rsi
  int v30; // r8d
  int v31; // edx
  BYTE *pvBuffer; // rcx
  int v34; // [rsp+20h] [rbp-40h]
  CRecoExt *v35; // [rsp+40h] [rbp-20h] BYREF
  __int64 v36; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-10h] BYREF
  int v38; // [rsp+A8h] [rbp+48h] BYREF
  const unsigned __int16 *v39; // [rsp+B0h] [rbp+50h]
  const unsigned __int16 *v40; // [rsp+B8h] [rbp+58h]

  v40 = a4;
  v39 = a3;
  v35 = 0;
  v36 = 0;
  v10 = a8;
  if ( !a2 )
    goto LABEL_35;
  if ( !*a2 )
    goto LABEL_35;
  if ( !a8 )
    goto LABEL_35;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( v11 > 0x80 || (v12 = a6) == 0 )
  {
LABEL_35:
    v15 = -2147024809;
    goto LABEL_36;
  }
  v13 = 2 * v11 + 270;
  v38 = 0;
  v14 = (unsigned int)(2 * v11 + 270);
  if ( v14 != v13 || !g_heap || (v16 = (char *)HeapAlloc(g_heap, 0, v13), (v17 = v16) == 0) )
  {
    v15 = -2147024882;
LABEL_37:
    pvBuffer = v10->pvBuffer;
    if ( pvBuffer )
      CoTaskMemFree(pvBuffer);
    v10->ulSize = 0;
    v10->pvBuffer = 0;
    v10->pFirstWordPronunciation = 0;
    goto LABEL_40;
  }
  if ( *((_QWORD *)this + 15)
    && (*(_DWORD *)v16 = 49,
        *((_WORD *)v16 + 2) = a5,
        *((_DWORD *)v16 + 2) = v12,
        memcpy_0(v16 + 12, a2, 2 * v11 + 2),
        v15 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, CRecoExt **, int *))(**((_QWORD **)this + 15) + 32LL))(
                *((_QWORD *)this + 15),
                v17,
                (unsigned int)v14,
                &v35,
                &v38),
        v15 >= 0) )
  {
    v18 = v35;
    v10->ulSize = *(_DWORD *)v35;
    v10->pvBuffer = (BYTE *)v18;
    v19 = (SPWORDPRONUNCIATION *)((char *)v18 + *((_QWORD *)v18 + 2));
    v10->pFirstWordPronunciation = v19;
    v20 = CRecoExt::ConvertLexiconTypeForOutput(v18, v19->eLexiconType);
    *(_DWORD *)(v21 + 8) = v20;
    if ( v21 )
    {
      do
      {
        if ( *(_QWORD *)v21 )
        {
          v23 = (CRecoExt *)((char *)v35 + *(_QWORD *)v21);
          *(_QWORD *)v21 = v23;
        }
        else
        {
          v23 = v22;
        }
        v24 = CRecoExt::ConvertLexiconTypeForOutput(v23, *(enum SPLEXICONTYPE *)(v21 + 8));
        *(_DWORD *)(v25 + 8) = v24;
        v21 = v26;
      }
      while ( v26 );
    }
  }
  else if ( a7 )
  {
    v15 = -2147200931;
  }
  else
  {
    *(_OWORD *)pv = 0;
    LOWORD(v34) = a5;
    v27 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, LPVOID *))(*((_QWORD *)this + 3) + 24LL))(
            (char *)this + 24,
            a2,
            v39,
            v40,
            v34,
            pv);
    if ( v27 < 0 )
    {
      if ( v27 == -2147220436 )
        v27 = -2147200931;
      v15 = v27;
    }
    else
    {
      if ( LODWORD(pv[0]) != 1 )
        goto LABEL_28;
      v28 = *(unsigned __int16 **)pv[1];
      v29 = (char *)a2 - *(_QWORD *)pv[1];
      do
      {
        v30 = *(unsigned __int16 *)&v29[(_QWORD)v28];
        v31 = *v28 - v30;
        if ( v31 )
          break;
        ++v28;
      }
      while ( v30 );
      v15 = -2147200931;
      if ( v31 )
LABEL_28:
        v15 = -2147200899;
      CoTaskMemFree(pv[1]);
    }
  }
  CWinHeap::Free((CWinHeap *)&g_heap, v17);
  if ( v15 )
  {
LABEL_36:
    if ( !v10 )
      goto LABEL_40;
    goto LABEL_37;
  }
LABEL_40:
  ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(&v36);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000500c  mov     [rsp-38h+arg_0], rbx
0x180005011  mov     [rsp-38h+arg_18], r9
0x180005016  mov     [rsp-38h+arg_10], r8
0x18000501b  push    rbp
0x18000501c  push    rsi
0x18000501d  push    rdi
0x18000501e  push    r12
0x180005020  push    r13
0x180005022  push    r14
0x180005024  push    r15
0x180005026  mov     rbp, rsp
0x180005029  sub     rsp, 60h
0x18000502d  mov     rsi, rdx
0x180005030  mov     r13, rcx
0x180005033  xor     r9d, r9d
0x180005036  mov     [rbp+var_20], r9
0x18000503a  mov     [rbp+var_18], r9
0x18000503e  mov     rdi, [rbp+arg_38]
0x180005042  test    rdx, rdx
0x180005045  jz      loc_180005226
0x18000504b  cmp     [rdx], r9w
0x18000504f  jz      loc_180005226
0x180005055  test    rdi, rdi
0x180005058  jz      loc_180005226
0x18000505e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005062  inc     rbx
0x180005065  cmp     [rdx+rbx*2], r9w
0x18000506a  jnz     short loc_180005062
0x18000506c  cmp     rbx, 80h
0x180005073  ja      loc_180005226
0x180005079  mov     r15d, [rbp+arg_28]
0x18000507d  test    r15d, r15d
0x180005080  jz      loc_180005226
0x180005086  lea     r8, ds:10Eh[rbx*2]; dwBytes
0x18000508e  mov     [rbp+arg_8], r9d
0x180005092  mov     r12d, r8d
0x180005095  cmp     r12, r8
0x180005098  jz      short loc_1800050A4
0x18000509a  mov     ebx, 8007000Eh
0x18000509f  jmp     loc_180005230
0x1800050a4  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x1800050ab  test    rcx, rcx
0x1800050ae  jz      short loc_18000509A
0x1800050b0  xor     edx, edx; dwFlags
0x1800050b2  call    cs:__imp_HeapAlloc
0x1800050b8  mov     r14, rax
0x1800050bb  xor     r9d, r9d
0x1800050be  test    rax, rax
0x1800050c1  jz      short loc_18000509A
0x1800050c3  cmp     [r13+78h], r9
0x1800050c7  jz      loc_18000517B
0x1800050cd  mov     dword ptr [rax], 31h ; '1'
0x1800050d3  movzx   eax, [rbp+arg_20]
0x1800050d7  mov     [r14+4], ax
0x1800050dc  mov     [r14+8], r15d
0x1800050e0  lea     r8, ds:2[rbx*2]; Size
0x1800050e8  lea     rcx, [r14+0Ch]; void *
0x1800050ec  mov     rdx, rsi; Src
0x1800050ef  call    memcpy_0
0x1800050f4  mov     rcx, [r13+78h]
0x1800050f8  mov     rax, [rcx]
0x1800050fb  lea     rdx, [rbp+arg_8]
0x1800050ff  mov     [rsp+60h+var_40], rdx
0x180005104  lea     r9, [rbp+var_20]
0x180005108  mov     r8d, r12d
0x18000510b  mov     rdx, r14
0x18000510e  mov     rax, [rax+20h]
0x180005112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005117  mov     ebx, eax
0x180005119  xor     r9d, r9d
0x18000511c  test    eax, eax
0x18000511e  js      short loc_18000517B
0x180005120  mov     rcx, [rbp+var_20]; this
0x180005124  mov     eax, [rcx]
0x180005126  mov     [rdi], eax
0x180005128  mov     [rdi+8], rcx
0x18000512c  mov     r8, [rcx+10h]
0x180005130  add     r8, rcx
0x180005133  mov     [rdi+10h], r8
0x180005137  mov     edx, [r8+8]; enum SPLEXICONTYPE
0x18000513b  call    ?ConvertLexiconTypeForOutput@CRecoExt@@AEAA?AW4SPLEXICONTYPE@@W42@@Z; CRecoExt::ConvertLexiconTypeForOutput(SPLEXICONTYPE)
0x180005140  mov     [r8+8], eax
0x180005144  test    r8, r8
0x180005147  jz      loc_18000520E
0x18000514d  mov     rcx, [r8]
0x180005150  test    rcx, rcx
0x180005153  jz      short loc_18000515E
0x180005155  add     rcx, [rbp+var_20]
0x180005159  mov     [r8], rcx
0x18000515c  jmp     short loc_180005161
0x18000515e  mov     rcx, r9; this
0x180005161  mov     edx, [r8+8]; enum SPLEXICONTYPE
0x180005165  call    ?ConvertLexiconTypeForOutput@CRecoExt@@AEAA?AW4SPLEXICONTYPE@@W42@@Z; CRecoExt::ConvertLexiconTypeForOutput(SPLEXICONTYPE)
0x18000516a  mov     [r8+8], eax
0x18000516e  mov     r8, rcx
0x180005171  test    rcx, rcx
0x180005174  jnz     short loc_18000514D
0x180005176  jmp     loc_18000520E
0x18000517b  cmp     [rbp+arg_30], r9d
0x18000517f  jz      short loc_18000518B
0x180005181  mov     ebx, 8004505Dh
0x180005186  jmp     loc_18000520E
0x18000518b  xorps   xmm0, xmm0
0x18000518e  movups  xmmword ptr [rbp+pv], xmm0
0x180005192  lea     rcx, [r13+18h]
0x180005196  mov     rax, [rcx]
0x180005199  lea     rdx, [rbp+pv]
0x18000519d  mov     [rsp+60h+var_38], rdx
0x1800051a2  movzx   edx, [rbp+arg_20]
0x1800051a6  mov     word ptr [rsp+60h+var_40], dx
0x1800051ab  mov     r9, [rbp+arg_18]
0x1800051af  mov     r8, [rbp+arg_10]
0x1800051b3  mov     rdx, rsi
0x1800051b6  mov     rax, [rax+18h]
0x1800051ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051bf  test    eax, eax
0x1800051c1  js      short loc_1800051FF
0x1800051c3  mov     rcx, [rbp+pv+8]; pv
0x1800051c7  cmp     dword ptr [rbp+pv], 1
0x1800051cb  jnz     short loc_1800051F2
0x1800051cd  mov     rax, [rcx]
0x1800051d0  sub     rsi, rax
0x1800051d3  movzx   edx, word ptr [rax]
0x1800051d6  movzx   r8d, word ptr [rax+rsi]
0x1800051db  sub     edx, r8d
0x1800051de  jnz     short loc_1800051E9
0x1800051e0  add     rax, 2
0x1800051e4  test    r8d, r8d
0x1800051e7  jnz     short loc_1800051D3
0x1800051e9  test    edx, edx
0x1800051eb  mov     ebx, 8004505Dh
0x1800051f0  jz      short loc_1800051F7
0x1800051f2  mov     ebx, 8004507Dh
0x1800051f7  call    cs:__imp_CoTaskMemFree
0x1800051fd  jmp     short loc_18000520E
0x1800051ff  mov     ebx, 8004505Dh
0x180005204  cmp     eax, 8004042Ch
0x180005209  cmovz   eax, ebx
0x18000520c  mov     ebx, eax
0x18000520e  mov     rdx, r14; void *
0x180005211  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180005218  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18000521d  xor     r9d, r9d
0x180005220  test    ebx, ebx
0x180005222  jz      short loc_18000524D
0x180005224  jmp     short loc_18000522B
0x180005226  mov     ebx, 80070057h
0x18000522b  test    rdi, rdi
0x18000522e  jz      short loc_18000524D
0x180005230  mov     rcx, [rdi+8]; pv
0x180005234  test    rcx, rcx
0x180005237  jz      short loc_180005242
0x180005239  call    cs:__imp_CoTaskMemFree
0x18000523f  xor     r9d, r9d
0x180005242  mov     [rdi], r9d
0x180005245  mov     [rdi+8], r9
0x180005249  mov     [rdi+10h], r9
0x18000524d  lea     rcx, [rbp+var_18]
0x180005251  call    ??1?$CComPtrBase@UISpPhraseBuilder@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(void)
0x180005256  mov     eax, ebx
0x180005258  mov     rbx, [rsp+60h+arg_0]
0x180005260  add     rsp, 60h
0x180005264  pop     r15
0x180005266  pop     r14
0x180005268  pop     r13
0x18000526a  pop     r12
0x18000526c  pop     rdi
0x18000526d  pop     rsi
0x18000526e  pop     rbp
0x18000526f  retn
```
