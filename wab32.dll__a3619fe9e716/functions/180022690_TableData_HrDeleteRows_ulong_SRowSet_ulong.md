# TableData::HrDeleteRows(ulong,_SRowSet *,ulong *)

- ea: `0x180022690`
- end: `0x180022973`
- name: `?HrDeleteRows@TableData@@UEAAJKPEAU_SRowSet@@PEAK@Z`
- size: `739`
- prototype: `__int64 __fastcall(TableData *__hidden this, unsigned int, struct _SRowSet *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180021850`
- `0x180022690`
- `0x1800230c4`
- `0x18006b768`
- `0x18006b988`
- `0x180093010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800226c7`
- `KERNEL32!EnterCriticalSection` at `0x1800226c7`
- `KERNEL32!LeaveCriticalSection` at `0x180022953`
- `KERNEL32!LeaveCriticalSection` at `0x180022953`
- `KERNEL32!RtlMoveMemory` at `0x18002287a`
- `KERNEL32!RtlMoveMemory` at `0x18002287a`

## pseudocode

```c
__int64 __fastcall TableData::HrDeleteRows(TableData *this, char a2, struct _SRowSet *a3, unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  int v6; // edi
  __int64 v10; // rbx
  ULONG cRows; // edx
  _QWORD *v12; // r13
  struct _SRow ***v13; // r14
  SRow *v14; // r15
  SRow *aRow; // r12
  ULONG cValues; // eax
  _DWORD *p_ulPropTag; // rdx
  struct _SRow ***v18; // r8
  struct _SRow **v19; // rdx
  unsigned int v20; // ecx
  struct _SRow *v21; // r15
  __int64 v22; // rdx
  int v23; // r11d
  _QWORD *v24; // rdx
  _QWORD *v25; // r9
  __int64 v26; // rax
  void *v27; // rdx
  void **v28; // rbx
  MAPIUnknown *v29; // r14
  struct _SRow **v31; // [rsp+40h] [rbp-10h] BYREF
  void *v32; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v33; // [rsp+98h] [rbp+48h] BYREF
  unsigned int *v34; // [rsp+A8h] [rbp+58h]

  v34 = a4;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 352);
  v6 = 0;
  v32 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 352));
  if ( (a2 & 1) != 0 )
  {
    LODWORD(v10) = *((_DWORD *)this + 22);
    if ( !(_DWORD)v10
      || (v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 78) + 80LL))((char *)this - 624), v6 >= 0) )
    {
      if ( a4 )
        *a4 = v10;
    }
  }
  else
  {
    cRows = a3->cRows;
    LODWORD(v10) = 0;
    if ( a3->cRows )
    {
      v12 = (_QWORD *)((char *)this - 624);
      if ( *((_DWORD *)this + 16) == 2 || !*((_QWORD *)this + 7) )
      {
        if ( cRows <= 0x1FFFFFFF )
        {
          v6 = MAPIUnknown::Allocate((TableData *)((char *)this - 624), 8 * cRows, &v32);
          if ( v6 >= 0 )
          {
            v13 = (struct _SRow ***)v32;
            v14 = &a3->aRow[a3->cRows];
            aRow = a3->aRow;
LABEL_14:
            if ( v14 <= aRow )
            {
              v18 = (struct _SRow ***)v32;
              v6 = 0;
              v10 = ((char *)v13 - (_BYTE *)v32) >> 3;
              while ( v13 > v18 )
              {
                v19 = (struct _SRow **)*((_QWORD *)this + 12);
                --v13;
                v20 = *((_DWORD *)this + 22);
                v33 = 0;
                v21 = **v13;
                if ( (int)PlprowByLprow(v20, v19, v21, &v33) >= 0 )
                {
                  *((_DWORD *)this + 22) = v23 - 1;
                  if ( v33 != v23 - 1 )
                    RtlMoveMemory(
                      (PVOID)(v22 + 8LL * v33),
                      (const void *)(v22 + 8LL * v33 + 8),
                      8 * (v23 - 1) - 8 * v33);
                }
                **v13 = 0;
                *v13 = (struct _SRow **)v21;
                v18 = (struct _SRow ***)v32;
              }
              v24 = (_QWORD *)*((_QWORD *)this + 14);
              v25 = v24;
              if ( v24 < &v24[*((unsigned int *)this + 26)] )
              {
                do
                {
                  if ( *v24 )
                    *v25++ = *v24;
                  ++v24;
                }
                while ( (unsigned __int64)v24 < *((_QWORD *)this + 14)
                                              + 8 * (unsigned __int64)*((unsigned int *)this + 26) );
                v18 = (struct _SRow ***)v32;
              }
              v26 = *v12;
              *((_DWORD *)this + 26) = ((__int64)v25 - v12[92]) >> 3;
              (*(void (__fastcall **)(char *, _QWORD, struct _SRow ***, _QWORD, _QWORD, _QWORD))(v26 + 56))(
                (char *)this - 624,
                (unsigned int)v10,
                v18,
                0,
                0,
                0);
              if ( v34 )
                *v34 = v10;
            }
            else
            {
              --v14;
              v31 = 0;
              if ( !(unsigned int)FBadRow(v14) )
              {
                cValues = v14->cValues;
                if ( cValues )
                {
                  p_ulPropTag = &v14->lpProps->ulPropTag;
                  if ( p_ulPropTag )
                  {
                    while ( cValues )
                    {
                      if ( *p_ulPropTag == *((_DWORD *)this + 17)
                        || !*((_WORD *)this + 34) && ((*((_DWORD *)this + 17) ^ *p_ulPropTag) & 0xFFFF0000) == 0 )
                      {
                        if ( !p_ulPropTag )
                          break;
                        v6 = (*(__int64 (__fastcall **)(char *, _DWORD *, struct _SRow ***))(*v12 + 32LL))(
                               (char *)this - 624,
                               p_ulPropTag,
                               &v31);
                        if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147221233 )
                        {
                          *v13++ = v31;
                          goto LABEL_14;
                        }
                        goto LABEL_41;
                      }
                      --cValues;
                      p_ulPropTag += 6;
                    }
                  }
                }
              }
              v6 = -2147024809;
            }
LABEL_41:
            v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 352);
          }
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
        v6 = -2147467259;
      }
    }
  }
  v27 = v32;
  if ( v32 )
  {
    v28 = (void **)((char *)v32 + 8 * (unsigned int)v10);
    if ( v32 >= v28 )
    {
      v29 = (TableData *)((char *)this - 624);
    }
    else
    {
      do
      {
        v29 = (TableData *)((char *)this - 624);
        MAPIUnknown::Free((TableData *)((char *)this - 624), *v28);
        v27 = v32;
        --v28;
      }
      while ( v32 < v28 );
    }
    MAPIUnknown::Free(v29, v27);
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022690  mov     [rsp-38h+arg_10], rbx
0x180022695  mov     [rsp-38h+arg_18], r9
0x18002269a  push    rbp
0x18002269b  push    rsi
0x18002269c  push    rdi
0x18002269d  push    r12
0x18002269f  push    r13
0x1800226a1  push    r14
0x1800226a3  push    r15
0x1800226a5  mov     rbp, rsp
0x1800226a8  sub     rsp, 50h
0x1800226ac  lea     r15, [rcx-160h]
0x1800226b3  mov     rsi, rcx
0x1800226b6  xor     edi, edi
0x1800226b8  mov     rcx, r15; lpCriticalSection
0x1800226bb  mov     r14, r9
0x1800226be  mov     [rbp+arg_0], rdi
0x1800226c2  mov     r12, r8
0x1800226c5  mov     ebx, edx
0x1800226c7  call    cs:__imp_EnterCriticalSection
0x1800226cd  test    bl, 1
0x1800226d0  jz      short loc_18002270A
0x1800226d2  lea     rcx, [rsi-270h]
0x1800226d9  mov     ebx, [rcx+2C8h]
0x1800226df  test    ebx, ebx
0x1800226e1  jz      short loc_1800226F9
0x1800226e3  mov     rax, [rcx]
0x1800226e6  mov     rax, [rax+50h]
0x1800226ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226ef  mov     edi, eax
0x1800226f1  test    eax, eax
0x1800226f3  js      loc_18002290C
0x1800226f9  test    r14, r14
0x1800226fc  jz      loc_18002290C
0x180022702  mov     [r14], ebx
0x180022705  jmp     loc_18002290C
0x18002270a  mov     edx, [r12]
0x18002270e  xor     ebx, ebx
0x180022710  test    edx, edx
0x180022712  jz      loc_18002290C
0x180022718  lea     r13, [rsi-270h]
0x18002271f  cmp     dword ptr [r13+2B0h], 2
0x180022727  jz      short loc_180022739
0x180022729  cmp     [rsi+38h], rbx
0x18002272d  jz      short loc_180022739
0x18002272f  mov     edi, 80004005h
0x180022734  jmp     loc_18002290C
0x180022739  cmp     edx, 1FFFFFFFh
0x18002273f  jbe     short loc_18002274B
0x180022741  mov     edi, 8007000Eh
0x180022746  jmp     loc_18002290C
0x18002274b  shl     edx, 3; unsigned int
0x18002274e  lea     r8, [rbp+arg_0]; void **
0x180022752  mov     rcx, r13; this
0x180022755  call    ?Allocate@MAPIUnknown@@QEAAJKPEAPEAX@Z; MAPIUnknown::Allocate(ulong,void * *)
0x18002275a  mov     edi, eax
0x18002275c  test    eax, eax
0x18002275e  js      loc_18002290C
0x180022764  mov     r15d, [r12]
0x180022768  mov     r14, [rbp+arg_0]
0x18002276c  shl     r15, 4
0x180022770  add     r15, 8
0x180022774  add     r15, r12
0x180022777  add     r12, 8
0x18002277b  cmp     r15, r12
0x18002277e  jbe     loc_18002281D
0x180022784  sub     r15, 10h
0x180022788  mov     [rbp+var_10], rbx
0x18002278c  mov     rcx, r15
0x18002278f  call    FBadRow
0x180022794  test    eax, eax
0x180022796  jnz     short loc_180022813
0x180022798  mov     eax, [r15+4]
0x18002279c  test    eax, eax
0x18002279e  jz      short loc_180022813
0x1800227a0  mov     rdx, [r15+8]
0x1800227a4  movzx   r8d, word ptr [rsi+44h]
0x1800227a9  test    rdx, rdx
0x1800227ac  jz      short loc_180022813
0x1800227ae  test    eax, eax
0x1800227b0  jz      short loc_180022813
0x1800227b2  mov     ecx, [rdx]
0x1800227b4  cmp     ecx, [rsi+44h]
0x1800227b7  jz      short loc_1800227D1
0x1800227b9  test    r8d, r8d
0x1800227bc  jnz     short loc_1800227C9
0x1800227be  xor     ecx, [rsi+44h]
0x1800227c1  test    ecx, 0FFFF0000h
0x1800227c7  jz      short loc_1800227D1
0x1800227c9  dec     eax
0x1800227cb  add     rdx, 18h
0x1800227cf  jmp     short loc_1800227AE
0x1800227d1  test    rdx, rdx
0x1800227d4  jz      short loc_180022813
0x1800227d6  mov     rax, [r13+0]
0x1800227da  lea     r8, [rbp+var_10]
0x1800227de  mov     rcx, r13
0x1800227e1  mov     rax, [rax+20h]
0x1800227e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ea  mov     ecx, 80000000h
0x1800227ef  mov     edi, eax
0x1800227f1  add     eax, ecx
0x1800227f3  test    ecx, eax
0x1800227f5  jnz     short loc_180022803
0x1800227f7  cmp     edi, 8004010Fh
0x1800227fd  jnz     loc_180022905
0x180022803  mov     rax, [rbp+var_10]
0x180022807  mov     [r14], rax
0x18002280a  add     r14, 8
0x18002280e  jmp     loc_18002277B
0x180022813  mov     edi, 80070057h
0x180022818  jmp     loc_180022905
0x18002281d  mov     r8, [rbp+arg_0]
0x180022821  mov     rbx, r14
0x180022824  sub     rbx, r8
0x180022827  xor     edi, edi
0x180022829  sar     rbx, 3
0x18002282d  jmp     short loc_18002288D
0x18002282f  mov     r11d, [rsi+58h]
0x180022833  lea     r9, [rbp+arg_8]; unsigned int *
0x180022837  mov     rdx, [rsi+60h]; struct _SRow **
0x18002283b  sub     r14, 8
0x18002283f  mov     ecx, r11d; unsigned int
0x180022842  mov     [rbp+arg_8], edi
0x180022845  mov     rax, [r14]
0x180022848  mov     r15, [rax]
0x18002284b  mov     r8, r15; struct _SRow *
0x18002284e  call    ?PlprowByLprow@@YAJKPEAPEAU_SRow@@PEAU1@PEAK@Z; PlprowByLprow(ulong,_SRow * *,_SRow *,ulong *)
0x180022853  test    eax, eax
0x180022855  js      short loc_180022880
0x180022857  lea     r8d, [r11-1]
0x18002285b  mov     [rsi+58h], r8d
0x18002285f  cmp     [rbp+arg_8], r8d
0x180022863  jz      short loc_180022880
0x180022865  mov     eax, [rbp+arg_8]
0x180022868  shl     r8d, 3
0x18002286c  lea     rcx, [rdx+rax*8]; Destination
0x180022870  sub     r8d, ecx
0x180022873  add     r8d, edx; Length
0x180022876  lea     rdx, [rcx+8]; Source
0x18002287a  call    cs:__imp_RtlMoveMemory
0x180022880  mov     rax, [r14]
0x180022883  mov     [rax], rdi
0x180022886  mov     [r14], r15
0x180022889  mov     r8, [rbp+arg_0]
0x18002288d  cmp     r14, r8
0x180022890  ja      short loc_18002282F
0x180022892  mov     rdx, [rsi+70h]
0x180022896  mov     eax, [rsi+68h]
0x180022899  mov     r9, rdx
0x18002289c  lea     rcx, [rdx+rax*8]
0x1800228a0  cmp     rdx, rcx
0x1800228a3  jnb     short loc_1800228CC
0x1800228a5  mov     rax, [rdx]
0x1800228a8  test    rax, rax
0x1800228ab  jz      short loc_1800228B4
0x1800228ad  mov     [r9], rax
0x1800228b0  add     r9, 8
0x1800228b4  mov     ecx, [rsi+68h]
0x1800228b7  add     rdx, 8
0x1800228bb  mov     rax, [rsi+70h]
0x1800228bf  lea     rcx, [rax+rcx*8]
0x1800228c3  cmp     rdx, rcx
0x1800228c6  jb      short loc_1800228A5
0x1800228c8  mov     r8, [rbp+arg_0]
0x1800228cc  sub     r9, [r13+2E0h]
0x1800228d3  mov     edx, ebx
0x1800228d5  mov     rax, [r13+0]
0x1800228d9  mov     rcx, r13
0x1800228dc  sar     r9, 3
0x1800228e0  mov     [rsi+68h], r9d
0x1800228e4  xor     r9d, r9d
0x1800228e7  mov     [rsp+50h+var_28], rdi
0x1800228ec  mov     rax, [rax+38h]
0x1800228f0  mov     [rsp+50h+var_30], rdi
0x1800228f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228fa  mov     rax, [rbp+arg_18]
0x1800228fe  test    rax, rax
0x180022901  jz      short loc_180022905
0x180022903  mov     [rax], ebx
0x180022905  lea     r15, [rsi-160h]
0x18002290c  mov     rdx, [rbp+arg_0]; void *
0x180022910  test    rdx, rdx
0x180022913  jz      short loc_180022950
0x180022915  mov     eax, ebx
0x180022917  lea     rbx, [rdx+rax*8]
0x18002291b  cmp     rdx, rbx
0x18002291e  jnb     short loc_180022941
0x180022920  mov     rdx, [rbx]; void *
0x180022923  lea     r14, [rsi-270h]
0x18002292a  mov     rcx, r14; this
0x18002292d  call    ?Free@MAPIUnknown@@QEAAXPEAX@Z; MAPIUnknown::Free(void *)
0x180022932  mov     rdx, [rbp+arg_0]
0x180022936  sub     rbx, 8
0x18002293a  cmp     rdx, rbx
0x18002293d  jb      short loc_180022920
0x18002293f  jmp     short loc_180022948
0x180022941  lea     r14, [rsi-270h]
0x180022948  mov     rcx, r14; this
0x18002294b  call    ?Free@MAPIUnknown@@QEAAXPEAX@Z; MAPIUnknown::Free(void *)
0x180022950  mov     rcx, r15; lpCriticalSection
0x180022953  call    cs:__imp_LeaveCriticalSection
0x180022959  mov     rbx, [rsp+50h+arg_10]
0x180022961  mov     eax, edi
0x180022963  add     rsp, 50h
0x180022967  pop     r15
0x180022969  pop     r14
0x18002296b  pop     r13
0x18002296d  pop     r12
0x18002296f  pop     rdi
0x180022970  pop     rsi
0x180022971  pop     rbp
0x180022972  retn
```
