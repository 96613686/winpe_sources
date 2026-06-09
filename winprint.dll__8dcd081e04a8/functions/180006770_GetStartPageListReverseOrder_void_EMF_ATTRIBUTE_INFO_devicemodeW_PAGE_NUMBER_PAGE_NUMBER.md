# GetStartPageListReverseOrder(void *,_EMF_ATTRIBUTE_INFO *,_devicemodeW *,_PAGE_NUMBER * *,_PAGE_NUMBER * *)

- ea: `0x180006770`
- end: `0x180006994`
- name: `?GetStartPageListReverseOrder@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@PEAU_devicemodeW@@PEAPEAU_PAGE_NUMBER@@3@Z`
- size: `548`
- prototype: `__int64 __fastcall(void *, struct _EMF_ATTRIBUTE_INFO *, struct _devicemodeW *, struct _PAGE_NUMBER **, struct _PAGE_NUMBER **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002400`

## callees

- `0x180003860`
- `0x180006514`
- `0x180006770`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000686f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000686f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006967`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006967`

## pseudocode

```c
__int64 __fastcall GetStartPageListReverseOrder(
        _DWORD *a1,
        struct _EMF_ATTRIBUTE_INFO *a2,
        struct _devicemodeW *a3,
        HLOCAL *a4,
        struct _PAGE_NUMBER **a5)
{
  int v5; // r11d
  unsigned int v6; // ebx
  struct _PAGE_NUMBER **v10; // rsi
  unsigned int v11; // r8d
  __int64 v12; // r13
  unsigned int v13; // edx
  int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // r11d
  __int64 v17; // rcx
  unsigned int v18; // r15d
  struct _PAGE_NUMBER *v19; // rax
  __int64 dmOrientation; // r8
  unsigned int v21; // r12d
  unsigned int v22; // ebp
  __int64 PlaybackPageOrderForDriverNup; // rax
  _QWORD *v24; // r10
  unsigned __int64 v25; // r11
  unsigned int v26; // r9d
  unsigned int i; // r8d
  unsigned int v28; // ecx
  _QWORD *v29; // rcx
  _QWORD **v30; // rax
  _QWORD *v31; // r8
  _QWORD *v32; // r9
  __int64 v33; // rdx
  unsigned int uBytes; // [rsp+20h] [rbp-48h] BYREF
  unsigned int uBytes_4; // [rsp+24h] [rbp-44h]
  unsigned int v37; // [rsp+28h] [rbp-40h]
  _DWORD *v38; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v39; // [rsp+78h] [rbp+10h] BYREF

  v38 = a1;
  v5 = *((_DWORD *)a2 + 7);
  v6 = 1;
  v39 = 0;
  LODWORD(v38) = 1;
  uBytes = 0;
  if ( (unsigned int)(v5 - 1) > 0xFFFFFFFD )
    return 0;
  if ( !a4 )
    return 0;
  v10 = a5;
  if ( !a5 )
    return 0;
  v11 = *((_DWORD *)a2 + 9);
  v12 = v11;
  v13 = *((_DWORD *)a2 + 8);
  v14 = *((_DWORD *)a2 + 13);
  v15 = *((_DWORD *)a2 + 15);
  if ( v11 <= 1 )
    v12 = v13;
  *a4 = 0;
  v37 = v11;
  uBytes_4 = v15;
  *v10 = 0;
  if ( (int)ULongLongToULong(v12 * ((v14 != 0) + 1LL), (unsigned int *)&v38) < 0 )
    goto LABEL_38;
  v17 = v16 / (unsigned int)v38 + 1;
  if ( (_DWORD)v38 * (v16 / (unsigned int)v38) == v16 )
    v17 = v16 / (unsigned int)v38;
  if ( (int)ULongLongToULong((unsigned int)v38 * v17, &v39) >= 0
    && (v18 = v39, (int)ULongLongToULong(24LL * v39, &uBytes) >= 0)
    && (v19 = (struct _PAGE_NUMBER *)LocalAlloc(0x40u, uBytes)) != 0 )
  {
    *a4 = v19;
    dmOrientation = (unsigned int)a3->dmOrientation;
    v21 = uBytes_4;
    v22 = 1;
    PlaybackPageOrderForDriverNup = GetPlaybackPageOrderForDriverNup((unsigned int)v12, uBytes_4, dmOrientation);
    v26 = v37;
    v38 = (_DWORD *)PlaybackPageOrderForDriverNup;
    while ( v22 <= v18 && v25 >= (unsigned __int64)*a4 )
    {
      for ( i = 1; i <= (unsigned int)v12; ++i )
      {
        if ( v22 > v18 )
          goto LABEL_26;
        if ( i == 1 )
        {
          *(_QWORD *)v25 = v24;
          v24 = (_QWORD *)v25;
        }
        else
        {
          *(_QWORD *)(v25 + 32) = v25;
        }
        if ( v26 > 1 && v21 )
          v28 = v22 + v38[i - 1] - (v22 - 1) % (unsigned int)v12 - 1;
        else
          v28 = v22;
        *(_DWORD *)(v25 + 16) = v28;
        v25 -= 24LL;
        ++v22;
      }
    }
LABEL_26:
    if ( *((_DWORD *)a2 + 13) && !*((_DWORD *)a2 + 20) && v24 )
    {
      v29 = v24;
      if ( *v24 )
        v24 = (_QWORD *)*v24;
      do
      {
        v30 = (_QWORD **)*v29;
        if ( !*v29 )
          break;
        v31 = v29;
        v32 = v29;
        v29 = *v30;
        v33 = *v30 ? *v29 : 0LL;
        *v31 = v33;
        *v30 = v32;
      }
      while ( v29 );
    }
  }
  else
  {
LABEL_38:
    v6 = 0;
    if ( *a4 )
      LocalFree(*a4);
    *a4 = 0;
    v24 = 0;
  }
  *v10 = (struct _PAGE_NUMBER *)v24;
  return v6;
}

```

## disassembly

```asm
0x180006770  mov     rax, rsp
0x180006773  mov     [rax+18h], rbx
0x180006777  mov     [rax+8], rcx
0x18000677b  push    rbp
0x18000677c  push    rsi
0x18000677d  push    rdi
0x18000677e  push    r12
0x180006780  push    r13
0x180006782  push    r14
0x180006784  push    r15
0x180006786  sub     rsp, 30h
0x18000678a  mov     r11d, [rdx+1Ch]
0x18000678e  xor     ebp, ebp
0x180006790  mov     ebx, 1
0x180006795  mov     [rax+10h], ebp
0x180006798  mov     [rax+8], ebx
0x18000679b  mov     rdi, r9
0x18000679e  mov     [rax-48h], ebp
0x1800067a1  mov     r12, r8
0x1800067a4  lea     eax, [r11-1]
0x1800067a8  mov     r14, rdx
0x1800067ab  cmp     eax, 0FFFFFFFDh
0x1800067ae  ja      loc_18000697A
0x1800067b4  test    r9, r9
0x1800067b7  jz      loc_18000697A
0x1800067bd  mov     rsi, [rsp+68h+arg_20]
0x1800067c5  test    rsi, rsi
0x1800067c8  jz      loc_18000697A
0x1800067ce  mov     r8d, [r14+24h]
0x1800067d2  mov     r13d, r8d
0x1800067d5  mov     edx, [rdx+20h]
0x1800067d8  cmp     r8d, ebx
0x1800067db  mov     ecx, [r14+34h]
0x1800067df  mov     eax, [r14+3Ch]
0x1800067e3  cmovbe  r13d, edx
0x1800067e7  neg     ecx
0x1800067e9  mov     [r9], rbp
0x1800067ec  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x1800067f1  mov     [rsp+68h+var_40], r8d
0x1800067f6  sbb     rcx, rcx
0x1800067f9  mov     dword ptr [rsp+68h+uBytes+4], eax
0x1800067fd  neg     rcx
0x180006800  mov     [rsi], rbp
0x180006803  add     rcx, rbx
0x180006806  imul    rcx, r13; unsigned __int64
0x18000680a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000680f  test    eax, eax
0x180006811  js      loc_18000695D
0x180006817  mov     r8d, dword ptr [rsp+68h+arg_0]
0x18000681c  xor     edx, edx
0x18000681e  mov     eax, r11d
0x180006821  div     r8d
0x180006824  mov     edx, eax
0x180006826  imul    edx, r8d
0x18000682a  lea     ecx, [rax+1]
0x18000682d  cmp     edx, r11d
0x180006830  lea     rdx, [rsp+68h+arg_8]; unsigned int *
0x180006835  cmovz   ecx, eax
0x180006838  imul    rcx, r8; unsigned __int64
0x18000683c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180006841  test    eax, eax
0x180006843  js      loc_18000695D
0x180006849  mov     r15d, [rsp+68h+arg_8]
0x18000684e  lea     rdx, [rsp+68h+uBytes]; unsigned int *
0x180006853  lea     rcx, [r15+r15*2]
0x180006857  shl     rcx, 3; unsigned __int64
0x18000685b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180006860  test    eax, eax
0x180006862  js      loc_18000695D
0x180006868  mov     edx, dword ptr [rsp+68h+uBytes]; uBytes
0x18000686c  lea     ecx, [rbx+3Fh]; uFlags
0x18000686f  call    cs:__imp_LocalAlloc
0x180006875  test    rax, rax
0x180006878  jz      loc_18000695D
0x18000687e  mov     [rdi], rax
0x180006881  lea     ecx, [r15-1]
0x180006885  movsx   r8d, word ptr [r12+4Ch]
0x18000688b  lea     rcx, [rcx+rcx*2]
0x18000688f  mov     r12d, dword ptr [rsp+68h+uBytes+4]
0x180006894  lea     r11, [rax+rcx*8]
0x180006898  mov     ecx, r13d
0x18000689b  xor     r10d, r10d
0x18000689e  mov     edx, r12d
0x1800068a1  mov     ebp, ebx
0x1800068a3  call    ?GetPlaybackPageOrderForDriverNup@@YAPEAKKW4_ENupDirection@@H@Z; GetPlaybackPageOrderForDriverNup(ulong,_ENupDirection,int)
0x1800068a8  mov     r9d, [rsp+68h+var_40]
0x1800068ad  mov     [rsp+68h+arg_0], rax
0x1800068b2  cmp     ebp, r15d
0x1800068b5  ja      short loc_180006911
0x1800068b7  cmp     r11, [rdi]
0x1800068ba  jb      short loc_180006911
0x1800068bc  mov     r8d, ebx
0x1800068bf  cmp     r8d, r13d
0x1800068c2  ja      short loc_1800068B2
0x1800068c4  cmp     ebp, r15d
0x1800068c7  ja      short loc_180006911
0x1800068c9  cmp     r8d, ebx
0x1800068cc  jnz     short loc_1800068D6
0x1800068ce  mov     [r11], r10
0x1800068d1  mov     r10, r11
0x1800068d4  jmp     short loc_1800068DA
0x1800068d6  mov     [r11+20h], r11
0x1800068da  cmp     r9d, ebx
0x1800068dd  jbe     short loc_180006900
0x1800068df  test    r12d, r12d
0x1800068e2  jz      short loc_180006900
0x1800068e4  lea     eax, [rbp-1]
0x1800068e7  xor     edx, edx
0x1800068e9  div     r13d
0x1800068ec  mov     rax, [rsp+68h+arg_0]
0x1800068f1  lea     ecx, [r8-1]
0x1800068f5  mov     ecx, [rax+rcx*4]
0x1800068f8  sub     ecx, edx
0x1800068fa  dec     ecx
0x1800068fc  add     ecx, ebp
0x1800068fe  jmp     short loc_180006902
0x180006900  mov     ecx, ebp
0x180006902  mov     [r11+10h], ecx
0x180006906  add     r8d, ebx
0x180006909  sub     r11, 18h
0x18000690d  add     ebp, ebx
0x18000690f  jmp     short loc_1800068BF
0x180006911  cmp     dword ptr [r14+34h], 0
0x180006916  jz      short loc_180006973
0x180006918  cmp     dword ptr [r14+50h], 0
0x18000691d  jnz     short loc_180006973
0x18000691f  test    r10, r10
0x180006922  jz      short loc_18000695B
0x180006924  mov     rax, [r10]
0x180006927  mov     rcx, r10
0x18000692a  test    rax, rax
0x18000692d  cmovnz  r10, rax
0x180006931  mov     rax, [rcx]
0x180006934  test    rax, rax
0x180006937  jz      short loc_180006973
0x180006939  mov     r8, rcx
0x18000693c  mov     r9, rcx
0x18000693f  mov     rcx, [rax]
0x180006942  test    rcx, rcx
0x180006945  jnz     short loc_18000694B
0x180006947  xor     edx, edx
0x180006949  jmp     short loc_18000694E
0x18000694b  mov     rdx, [rcx]
0x18000694e  mov     [r8], rdx
0x180006951  mov     [rax], r9
0x180006954  test    rcx, rcx
0x180006957  jnz     short loc_180006931
0x180006959  jmp     short loc_180006973
0x18000695b  jmp     short loc_180006973
0x18000695d  mov     rcx, [rdi]; hMem
0x180006960  mov     ebx, ebp
0x180006962  test    rcx, rcx
0x180006965  jz      short loc_18000696D
0x180006967  call    cs:__imp_LocalFree
0x18000696d  mov     [rdi], rbp
0x180006970  mov     r10, rbp
0x180006973  mov     [rsi], r10
0x180006976  mov     eax, ebx
0x180006978  jmp     short loc_18000697C
0x18000697a  xor     eax, eax
0x18000697c  mov     rbx, [rsp+68h+arg_10]
0x180006984  add     rsp, 30h
0x180006988  pop     r15
0x18000698a  pop     r14
0x18000698c  pop     r13
0x18000698e  pop     r12
0x180006990  pop     rdi
0x180006991  pop     rsi
0x180006992  pop     rbp
0x180006993  retn
```
