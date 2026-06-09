# EventFieldElementEnd(_XMRW_OPEN_CONTEXT *)

- ea: `0x140033bac`
- end: `0x140033ebc`
- name: `?EventFieldElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14003290c`

## callees

- `0x140033bac`
- `0x140035b7c`
- `0x14003673c`
- `0x14003694c`
- `0x1400400d6`
- `0x140040130`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventFieldElementEnd(struct _XMRW_OPEN_CONTEXT *a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbx
  __int64 v4; // rdi
  _OWORD *v5; // r15
  struct RPT_STRING *v6; // rdx
  unsigned int TdhEventInfo; // r14d
  __int64 v8; // rcx
  unsigned int v9; // edx
  __int64 result; // rax
  __int64 v11; // rcx
  char v12; // cl
  int v13; // r8d
  char v14; // cl
  int v15; // r8d
  unsigned int v16; // [rsp+20h] [rbp-79h] BYREF
  _EVENT_PROPERTY_INFO v17; // [rsp+28h] [rbp-71h] BYREF
  struct _EVENT_RECORD v18; // [rsp+40h] [rbp-59h] BYREF

  v1 = *((_QWORD *)a1 + 10);
  memset_0(&v18, 0, sizeof(v18));
  v16 = 0;
  memset(&v17, 0, sizeof(v17));
  if ( !v1 )
    return 0;
  v3 = *((_QWORD *)a1 + 12);
  if ( !v3 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  if ( *(char *)(v1 + 680) < 0 )
    *(_WORD *)(v3 + 236) = *(_WORD *)(v1 + 210);
  v5 = (_OWORD *)(v3 + 216);
  v6 = 0;
  if ( (*(_BYTE *)(v3 + 353) & 1) == 0 )
    v6 = (struct RPT_STRING *)(v3 + 176);
  TdhEventInfo = GetTdhEventInfo((struct _TRACERPT_EVENT_FIELD_SOURCE *)(v3 + 216), v6, &v17, &v18);
  if ( TdhEventInfo )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v16);
    if ( TdhEventInfo == -1073222110 )
      PrintMessage(0x46Du, v16);
    else
      PrintMessage(0x46Eu, v16);
    return 0;
  }
  v8 = 0;
  v9 = (*(unsigned __int8 *)(v1 + 681) >> 4) & 3;
  if ( !v9 )
  {
LABEL_17:
    if ( (_DWORD)v8 != v9 )
      goto LABEL_23;
    if ( (*(_BYTE *)(v3 + 370) & 2) != 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v16);
      PrintMessage(0x46Fu, v16);
    }
    else
    {
      if ( (*(_BYTE *)(v1 + 681) & 0x30u) < 0x20 )
      {
        v11 = 3 * v8;
        *(_OWORD *)(v1 + 8 * v11 + 632) = *v5;
        *(_QWORD *)(v1 + 8 * v11 + 648) = *(_QWORD *)(v3 + 232);
        *(_BYTE *)(v1 + 681) ^= (*(_BYTE *)(v1 + 681) ^ (*(_BYTE *)(v1 + 681) + 16)) & 0x30;
        goto LABEL_23;
      }
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v16);
      PrintMessage(0x470u, v16);
    }
    return 3221745200LL;
  }
  while ( *(_QWORD *)(v1 + 24 * v8 + 632) != *(_QWORD *)v5
       || *(_QWORD *)(v1 + 24 * v8 + 640) != *(_QWORD *)(v3 + 224)
       || *(_WORD *)(v1 + 24 * v8 + 648) != *(_WORD *)(v3 + 232) )
  {
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= v9 )
      goto LABEL_17;
  }
LABEL_23:
  if ( (*(_BYTE *)(v3 + 352) & 3) != 0 )
  {
    if ( (*(_BYTE *)(v3 + 368) & 0x10) != 0 )
      goto LABEL_35;
    v12 = *(_BYTE *)(v3 + 353);
    if ( (v12 & 1) != 0 )
    {
      if ( (v12 & 2) != 0 )
        goto LABEL_43;
LABEL_35:
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v16);
      PrintMessage(0x471u, v16);
      return 3221745193LL;
    }
    if ( (v17.nonStructType.InType > 0x15u || (v13 = 3219448, !_bittest(&v13, v17.nonStructType.InType)))
      && v17.nonStructType.InType != 308
      || v17.nonStructType.MapNameOffset )
    {
      *(_BYTE *)(v3 + 353) = v12 & 0xFD;
      goto LABEL_35;
    }
    goto LABEL_33;
  }
  v12 = *(_BYTE *)(v3 + 353);
  if ( (v12 & 1) == 0 )
  {
    if ( (v17.nonStructType.InType > 0x15u || (v15 = 3219448, !_bittest(&v15, v17.nonStructType.InType)))
      && v17.nonStructType.InType != 308
      || v17.nonStructType.MapNameOffset )
    {
      v14 = v12 & 0xFD;
      goto LABEL_42;
    }
LABEL_33:
    v14 = v12 | 2;
LABEL_42:
    *(_BYTE *)(v3 + 353) = v14;
  }
LABEL_43:
  result = InsertMofInfo(&v18);
  if ( (_DWORD)result )
    return result;
  *(struct _EVENT_RECORD *)(v3 + 240) = v18;
  return 0;
}

```

## disassembly

```asm
0x140033bac  push    rbp
0x140033bae  push    rbx
0x140033baf  push    rsi
0x140033bb0  push    rdi
0x140033bb1  push    r14
0x140033bb3  push    r15
0x140033bb5  lea     rbp, [rsp-2Fh]
0x140033bba  sub     rsp, 0C8h
0x140033bc1  mov     rax, cs:__security_cookie
0x140033bc8  xor     rax, rsp
0x140033bcb  mov     [rbp+57h+var_40], rax
0x140033bcf  mov     rsi, [rcx+50h]
0x140033bd3  xor     edx, edx; Val
0x140033bd5  mov     rdi, rcx
0x140033bd8  lea     rcx, [rbp+57h+var_B0]; void *
0x140033bdc  lea     r8d, [rdx+70h]; Size
0x140033be0  call    memset_0
0x140033be5  xor     eax, eax
0x140033be7  xorps   xmm0, xmm0
0x140033bea  mov     qword ptr [rbp+57h+var_C8.10h], rax
0x140033bee  mov     [rbp+57h+var_D0], eax
0x140033bf1  movups  xmmword ptr [rbp+57h+var_C8.Flags], xmm0
0x140033bf5  test    rsi, rsi
0x140033bf8  jz      loc_140033E9E
0x140033bfe  mov     rbx, [rdi+60h]
0x140033c02  test    rbx, rbx
0x140033c05  jz      loc_140033E9E
0x140033c0b  mov     rdi, [rdi+18h]
0x140033c0f  cmp     [rsi+2A8h], al
0x140033c15  jge     short loc_140033C25
0x140033c17  movzx   eax, word ptr [rsi+0D2h]
0x140033c1e  mov     [rbx+0ECh], ax
0x140033c25  test    byte ptr [rbx+161h], 1
0x140033c2c  lea     rax, [rbx+0B0h]
0x140033c33  lea     r15, [rbx+0D8h]
0x140033c3a  mov     edx, 0
0x140033c3f  cmovz   rdx, rax; struct RPT_STRING *
0x140033c43  lea     r9, [rbp+57h+var_B0]; struct _EVENT_RECORD *
0x140033c47  lea     r8, [rbp+57h+var_C8]; struct _EVENT_PROPERTY_INFO *
0x140033c4b  mov     rcx, r15; struct _TRACERPT_EVENT_FIELD_SOURCE *
0x140033c4e  call    ?GetTdhEventInfo@@YAKPEAU_TRACERPT_EVENT_FIELD_SOURCE@@PEAVRPT_STRING@@PEAU_EVENT_PROPERTY_INFO@@PEAU_EVENT_RECORD@@@Z; GetTdhEventInfo(_TRACERPT_EVENT_FIELD_SOURCE *,RPT_STRING *,_EVENT_PROPERTY_INFO *,_EVENT_RECORD *)
0x140033c53  mov     r14d, eax
0x140033c56  test    eax, eax
0x140033c58  jz      short loc_140033C92
0x140033c5a  mov     rcx, [rdi]
0x140033c5d  lea     rdx, [rbp+57h+var_D0]
0x140033c61  mov     rax, [rcx+0A8h]
0x140033c68  mov     rcx, rdi
0x140033c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033c70  mov     edx, [rbp+57h+var_D0]
0x140033c73  cmp     r14d, 0C007EE22h
0x140033c7a  jnz     short loc_140033C8B
0x140033c7c  mov     ecx, 46Dh; unsigned int
0x140033c81  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033c86  jmp     loc_140033E9E
0x140033c8b  mov     ecx, 46Eh
0x140033c90  jmp     short loc_140033C81
0x140033c92  movzx   r8d, byte ptr [rsi+2A9h]
0x140033c9a  xor     ecx, ecx
0x140033c9c  mov     edx, r8d
0x140033c9f  mov     r10b, 2
0x140033ca2  shr     edx, 4
0x140033ca5  and     edx, 3
0x140033ca8  jbe     short loc_140033CE1
0x140033caa  lea     r9, [rcx+rcx*2]
0x140033cae  mov     rax, [rsi+r9*8+278h]
0x140033cb6  cmp     rax, [r15]
0x140033cb9  jnz     short loc_140033CDB
0x140033cbb  mov     rax, [rsi+r9*8+280h]
0x140033cc3  cmp     rax, [r15+8]
0x140033cc7  jnz     short loc_140033CDB
0x140033cc9  movzx   eax, word ptr [rbx+0E8h]
0x140033cd0  cmp     [rsi+r9*8+288h], ax
0x140033cd9  jz      short loc_140033D5A
0x140033cdb  inc     ecx
0x140033cdd  cmp     ecx, edx
0x140033cdf  jb      short loc_140033CAA
0x140033ce1  cmp     ecx, edx
0x140033ce3  jnz     short loc_140033D5A
0x140033ce5  test    [rbx+172h], r10b
0x140033cec  jz      short loc_140033D1B
0x140033cee  mov     rax, [rdi]
0x140033cf1  lea     rdx, [rbp+57h+var_D0]
0x140033cf5  mov     rcx, rdi
0x140033cf8  mov     rax, [rax+0A8h]
0x140033cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033d04  mov     ecx, 46Fh; unsigned int
0x140033d09  mov     edx, [rbp+57h+var_D0]
0x140033d0c  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033d11  mov     eax, 0C007EE30h
0x140033d16  jmp     loc_140033EA0
0x140033d1b  and     r8b, 30h
0x140033d1f  cmp     r8b, 20h ; ' '
0x140033d23  jnb     short loc_140033D85
0x140033d25  movups  xmm0, xmmword ptr [r15]
0x140033d29  lea     rcx, [rcx+rcx*2]
0x140033d2d  movups  xmmword ptr [rsi+rcx*8+278h], xmm0
0x140033d35  movsd   xmm1, qword ptr [r15+10h]
0x140033d3b  movsd   qword ptr [rsi+rcx*8+288h], xmm1
0x140033d44  mov     al, [rsi+2A9h]
0x140033d4a  lea     ecx, [rax+10h]
0x140033d4d  xor     cl, al
0x140033d4f  and     cl, 30h
0x140033d52  xor     cl, al
0x140033d54  mov     [rsi+2A9h], cl
0x140033d5a  test    byte ptr [rbx+160h], 3
0x140033d61  jz      loc_140033E05
0x140033d67  test    byte ptr [rbx+170h], 10h
0x140033d6e  jnz     short loc_140033DD8
0x140033d70  mov     cl, [rbx+161h]
0x140033d76  test    cl, 1
0x140033d79  jz      short loc_140033DA5
0x140033d7b  test    r10b, cl
0x140033d7e  jz      short loc_140033DD8
0x140033d80  jmp     loc_140033E3E
0x140033d85  mov     rax, [rdi]
0x140033d88  lea     rdx, [rbp+57h+var_D0]
0x140033d8c  mov     rcx, rdi
0x140033d8f  mov     rax, [rax+0A8h]
0x140033d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033d9b  mov     ecx, 470h
0x140033da0  jmp     loc_140033D09
0x140033da5  movzx   edx, word ptr [rbp+57h+var_C8.8]
0x140033da9  cmp     edx, 15h
0x140033dac  ja      short loc_140033DBA
0x140033dae  mov     r8d, 311FF8h
0x140033db4  bt      r8d, edx
0x140033db8  jb      short loc_140033DC4
0x140033dba  mov     eax, 134h
0x140033dbf  cmp     dx, ax
0x140033dc2  jnz     short loc_140033DCF
0x140033dc4  cmp     dword ptr [rbp+57h+var_C8.8+4], 0
0x140033dc8  jnz     short loc_140033DCF
0x140033dca  or      cl, r10b
0x140033dcd  jmp     short loc_140033E38
0x140033dcf  and     cl, 0FDh
0x140033dd2  mov     [rbx+161h], cl
0x140033dd8  mov     rax, [rdi]
0x140033ddb  lea     rdx, [rbp+57h+var_D0]
0x140033ddf  mov     rcx, rdi
0x140033de2  mov     rax, [rax+0A8h]
0x140033de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033dee  mov     edx, [rbp+57h+var_D0]
0x140033df1  mov     ecx, 471h; unsigned int
0x140033df6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033dfb  mov     eax, 0C007EE29h
0x140033e00  jmp     loc_140033EA0
0x140033e05  mov     cl, [rbx+161h]
0x140033e0b  test    cl, 1
0x140033e0e  jnz     short loc_140033E3E
0x140033e10  movzx   edx, word ptr [rbp+57h+var_C8.8]
0x140033e14  cmp     edx, 15h
0x140033e17  ja      short loc_140033E25
0x140033e19  mov     r8d, 311FF8h
0x140033e1f  bt      r8d, edx
0x140033e23  jb      short loc_140033E2F
0x140033e25  mov     eax, 134h
0x140033e2a  cmp     dx, ax
0x140033e2d  jnz     short loc_140033E35
0x140033e2f  cmp     dword ptr [rbp+57h+var_C8.8+4], 0
0x140033e33  jz      short loc_140033DCA
0x140033e35  and     cl, 0FDh
0x140033e38  mov     [rbx+161h], cl
0x140033e3e  mov     dl, [rsi+0D0h]
0x140033e44  lea     rcx, [rbp+57h+var_B0]; struct _EVENT_RECORD *
0x140033e48  call    InsertMofInfo
0x140033e4d  test    eax, eax
0x140033e4f  jnz     short loc_140033EA0
0x140033e51  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.EventHeader.Size]
0x140033e55  movups  xmmword ptr [rbx+0F0h], xmm0
0x140033e5c  movaps  xmm1, xmmword ptr [rbp+57h+var_B0.EventHeader.TimeStamp]
0x140033e60  movups  xmmword ptr [rbx+100h], xmm1
0x140033e67  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.EventHeader.ProviderId.Data4]
0x140033e6b  movups  xmmword ptr [rbx+110h], xmm0
0x140033e72  movaps  xmm1, xmmword ptr [rbp+57h+var_B0.EventHeader.EventDescriptor.Keyword]
0x140033e76  movups  xmmword ptr [rbx+120h], xmm1
0x140033e7d  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.EventHeader.ActivityId.Data1]
0x140033e81  movups  xmmword ptr [rbx+130h], xmm0
0x140033e88  movaps  xmm1, xmmword ptr [rbp+57h+var_B0.BufferContext]
0x140033e8c  movups  xmmword ptr [rbx+140h], xmm1
0x140033e93  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.UserData]
0x140033e97  movups  xmmword ptr [rbx+150h], xmm0
0x140033e9e  xor     eax, eax
0x140033ea0  mov     rcx, [rbp+57h+var_40]
0x140033ea4  xor     rcx, rsp; StackCookie
0x140033ea7  call    __security_check_cookie
0x140033eac  add     rsp, 0C8h
0x140033eb3  pop     r15
0x140033eb5  pop     r14
0x140033eb7  pop     rdi
0x140033eb8  pop     rsi
0x140033eb9  pop     rbx
0x140033eba  pop     rbp
0x140033ebb  retn
```
