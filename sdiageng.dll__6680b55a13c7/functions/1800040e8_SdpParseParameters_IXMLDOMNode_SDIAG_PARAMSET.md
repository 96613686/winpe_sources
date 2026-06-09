# SdpParseParameters(IXMLDOMNode *,_SDIAG_PARAMSET *)

- ea: `0x1800040e8`
- end: `0x180004377`
- name: `?SdpParseParameters@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMSET@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct _SDIAG_PARAMSET *)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180003b2c`
- `0x18001a530`
- `0x18001dc28`
- `0x1800208f4`
- `0x180026790`

## callees

- `0x1800012b0`
- `0x1800025c8`
- `0x180003e50`
- `0x1800040e8`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x180029882`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800042ea`
- `msvcrt!_wcsicmp` at `0x1800042ea`

## pseudocode

```c
__int64 __fastcall SdpParseParameters(struct IXMLDOMNode *a1, struct _SDIAG_PARAMSET *a2)
{
  struct IXMLDOMNode *v2; // r14
  struct IXMLDOMNodeList *v3; // r15
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  int ChildNodes; // eax
  __int64 v8; // rsi
  const wchar_t **v9; // rax
  const wchar_t **v10; // r13
  __int64 v11; // r12
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  unsigned int v17; // r12d
  __int64 v18; // rcx
  struct _SDIAG_PARAMSET *v19; // rax
  __int128 v21; // [rsp+20h] [rbp-18h] BYREF
  __int64 v22; // [rsp+80h] [rbp+48h] BYREF
  struct _SDIAG_PARAMSET *v23; // [rsp+88h] [rbp+50h]
  struct IXMLDOMNode *v24; // [rsp+90h] [rbp+58h] BYREF
  struct IXMLDOMNodeList *v25; // [rsp+98h] [rbp+60h] BYREF

  v23 = a2;
  v2 = 0;
  v3 = 0;
  v25 = 0;
  v24 = 0;
  LODWORD(v22) = 0;
  v21 = 0;
  if ( !a1 )
  {
    v4 = 347;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpParseParameters", v4, v5);
    goto LABEL_35;
  }
  if ( !a2 )
  {
    v4 = 348;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a1, &v25, (unsigned int *)&v22);
  v6 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    SdpDebugTrace(1u, L"SdpParseParameters", 354, ChildNodes);
    v3 = v25;
    goto LABEL_35;
  }
  v8 = (unsigned int)v22;
  v3 = v25;
  if ( !(_DWORD)v22 )
  {
    LODWORD(v8) = DWORD2(v21);
    v10 = (const wchar_t **)v21;
LABEL_28:
    v15 = 0;
    if ( (_DWORD)v8 )
    {
      while ( 2 )
      {
        v16 = v15++;
        v17 = v15;
        if ( v15 < (unsigned int)v8 )
        {
          v18 = 24 * v16;
          v22 = 24 * v16;
          do
          {
            if ( !_wcsicmp(*(const wchar_t **)((char *)v10 + v18), v10[3 * v17]) )
            {
              v5 = -2147024809;
              v4 = 385;
              v6 = -2147024809;
              goto LABEL_4;
            }
            v18 = v22;
            ++v17;
          }
          while ( v17 < (unsigned int)v8 );
          if ( v15 < (unsigned int)v8 )
            continue;
        }
        break;
      }
    }
    v19 = v23;
    *(_QWORD *)&v21 = 0;
    DWORD2(v21) = 0;
    *(_QWORD *)v23 = v10;
    *((_DWORD *)v19 + 2) = v8;
    v6 = 0;
    goto LABEL_35;
  }
  v9 = (const wchar_t **)operator new[](saturated_mul((unsigned int)v22, 0x18u));
  *(_QWORD *)&v21 = v9;
  v10 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v4 = 359;
    v5 = -2147024882;
    goto LABEL_4;
  }
  memset_0(v9, 0, 24 * v8);
  v11 = 0;
  DWORD2(v21) = v8;
  if ( !(_DWORD)v8 )
    goto LABEL_28;
  while ( 1 )
  {
    if ( v2 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
      v24 = 0;
    }
    v12 = SdpXmlNextNode(v3, &v24);
    v6 = v12;
    if ( v12 < 0 )
      break;
    v2 = v24;
    v13 = SdpXmlCheckNode(v24, L"Parameter");
    v6 = v13;
    if ( v13 < 0 )
    {
      v5 = v13;
      goto LABEL_25;
    }
    if ( v13 == 1 || !v2 )
    {
      v6 = -2147467259;
      v5 = -2147467259;
LABEL_25:
      v4 = 370;
      goto LABEL_4;
    }
    v14 = SdpParseParameter(v2, (struct _SDIAG_PARAMETER *)&v10[3 * v11]);
    v6 = v14;
    if ( v14 < 0 )
    {
      v5 = v14;
      v4 = 373;
      goto LABEL_4;
    }
    v11 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v11 >= (unsigned int)v8 )
      goto LABEL_28;
  }
  SdpDebugTrace(1u, L"SdpParseParameters", 369, v12);
  v2 = v24;
LABEL_35:
  SdpFreeParamSet((struct _SDIAG_PARAMSET *)&v21);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v3->lpVtbl->Release)(v3);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  return v6;
}

```

## disassembly

```asm
0x1800040e8  mov     [rsp-40h+arg_8], rdx
0x1800040ed  push    rbp
0x1800040ee  push    rbx
0x1800040ef  push    rsi
0x1800040f0  push    rdi
0x1800040f1  push    r12
0x1800040f3  push    r13
0x1800040f5  push    r14
0x1800040f7  push    r15
0x1800040f9  mov     rbp, rsp
0x1800040fc  sub     rsp, 38h
0x180004100  xor     r14d, r14d
0x180004103  xor     r15d, r15d
0x180004106  mov     [rbp+arg_18], r15
0x18000410a  xorps   xmm0, xmm0
0x18000410d  mov     [rbp+arg_10], r14
0x180004111  mov     rax, rdx
0x180004114  mov     dword ptr [rbp+arg_0], r14d
0x180004118  movups  [rbp+var_18], xmm0
0x18000411c  test    rcx, rcx
0x18000411f  jnz     short loc_180004146
0x180004121  mov     r8d, 15Bh; int
0x180004127  mov     r9d, 80070057h; int
0x18000412d  mov     ecx, 1; Level
0x180004132  mov     ebx, r9d
0x180004135  lea     rdx, aSdpparseparame; "SdpParseParameters"
0x18000413c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004141  jmp     loc_18000431F
0x180004146  test    rax, rax
0x180004149  jnz     short loc_180004153
0x18000414b  mov     r8d, 15Ch
0x180004151  jmp     short loc_180004127
0x180004153  mov     rdx, rcx; struct IXMLDOMNode *
0x180004156  lea     r9, [rbp+arg_0]; unsigned int *
0x18000415a  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18000415c  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180004160  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180004165  mov     ebx, eax
0x180004167  test    eax, eax
0x180004169  jns     short loc_18000418E
0x18000416b  mov     r9d, eax; int
0x18000416e  lea     rdx, aSdpparseparame; "SdpParseParameters"
0x180004175  mov     r8d, 162h; int
0x18000417b  mov     ecx, 1; Level
0x180004180  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004185  mov     r15, [rbp+arg_18]
0x180004189  jmp     loc_18000431F
0x18000418e  mov     esi, dword ptr [rbp+arg_0]
0x180004191  mov     edi, 1
0x180004196  mov     r15, [rbp+arg_18]
0x18000419a  test    esi, esi
0x18000419c  jz      loc_1800042B6
0x1800041a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800041a9  lea     eax, [rdi+17h]
0x1800041ac  mul     rsi
0x1800041af  cmovb   rax, rcx
0x1800041b3  mov     rcx, rax; unsigned __int64
0x1800041b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800041bb  mov     qword ptr [rbp+var_18], rax
0x1800041bf  mov     r13, rax
0x1800041c2  test    rax, rax
0x1800041c5  jnz     short loc_1800041DC
0x1800041c7  mov     ebx, 8007000Eh
0x1800041cc  mov     r8d, 167h
0x1800041d2  mov     r9d, ebx
0x1800041d5  mov     ecx, edi
0x1800041d7  jmp     loc_180004135
0x1800041dc  lea     r8, [rsi+rsi*2]
0x1800041e0  xor     edx, edx; Val
0x1800041e2  shl     r8, 3; Size
0x1800041e6  mov     rcx, r13; void *
0x1800041e9  call    memset_0
0x1800041ee  xor     r12d, r12d
0x1800041f1  mov     dword ptr [rbp+var_18+8], esi
0x1800041f4  test    esi, esi
0x1800041f6  jz      loc_1800042BD
0x1800041fc  test    r14, r14
0x1800041ff  jz      short loc_180004218
0x180004201  mov     rax, [r14]
0x180004204  mov     rcx, r14
0x180004207  mov     rax, [rax+10h]
0x18000420b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004210  mov     [rbp+arg_10], 0
0x180004218  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18000421c  mov     rcx, r15; struct IXMLDOMNodeList *
0x18000421f  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180004224  mov     ebx, eax
0x180004226  test    eax, eax
0x180004228  js      short loc_180004299
0x18000422a  mov     r14, [rbp+arg_10]
0x18000422e  lea     rdx, aParameter; "Parameter"
0x180004235  mov     rcx, r14; struct IXMLDOMNode *
0x180004238  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18000423d  mov     ebx, eax
0x18000423f  test    eax, eax
0x180004241  js      short loc_18000428B
0x180004243  cmp     eax, edi
0x180004245  jz      short loc_180004281
0x180004247  test    r14, r14
0x18000424a  jz      short loc_180004281
0x18000424c  lea     rcx, [r12+r12*2]
0x180004250  lea     rdx, ds:0[rcx*8]
0x180004258  mov     rcx, r14; struct IXMLDOMNode *
0x18000425b  add     rdx, r13; struct _SDIAG_PARAMETER *
0x18000425e  call    ?SdpParseParameter@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMETER@@@Z; SdpParseParameter(IXMLDOMNode *,_SDIAG_PARAMETER *)
0x180004263  mov     ebx, eax
0x180004265  test    eax, eax
0x180004267  js      short loc_180004273
0x180004269  add     r12d, edi
0x18000426c  cmp     r12d, esi
0x18000426f  jb      short loc_1800041FC
0x180004271  jmp     short loc_1800042BD
0x180004273  mov     r9d, eax
0x180004276  mov     r8d, 175h
0x18000427c  jmp     loc_1800041D5
0x180004281  mov     ebx, 80004005h
0x180004286  mov     r9d, ebx
0x180004289  jmp     short loc_18000428E
0x18000428b  mov     r9d, eax
0x18000428e  mov     r8d, 172h
0x180004294  jmp     loc_1800041D5
0x180004299  mov     r9d, eax; int
0x18000429c  lea     rdx, aSdpparseparame; "SdpParseParameters"
0x1800042a3  mov     r8d, 171h; int
0x1800042a9  mov     ecx, edi; Level
0x1800042ab  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800042b0  mov     r14, [rbp+arg_10]
0x1800042b4  jmp     short loc_18000431F
0x1800042b6  mov     esi, dword ptr [rbp+var_18+8]
0x1800042b9  mov     r13, qword ptr [rbp+var_18]
0x1800042bd  xor     ebx, ebx
0x1800042bf  test    esi, esi
0x1800042c1  jz      short loc_180004304
0x1800042c3  mov     eax, ebx
0x1800042c5  inc     ebx
0x1800042c7  mov     r12d, ebx
0x1800042ca  cmp     ebx, esi
0x1800042cc  jnb     short loc_180004304
0x1800042ce  lea     rcx, [rax+rax*2]
0x1800042d2  shl     rcx, 3
0x1800042d6  mov     [rbp+arg_0], rcx
0x1800042da  mov     rcx, [rcx+r13]; String1
0x1800042de  mov     eax, r12d
0x1800042e1  lea     rdx, [rax+rax*2]
0x1800042e5  mov     rdx, [r13+rdx*8+0]; String2
0x1800042ea  call    cs:__imp__wcsicmp
0x1800042f0  test    eax, eax
0x1800042f2  jz      short loc_180004363
0x1800042f4  mov     rcx, [rbp+arg_0]
0x1800042f8  add     r12d, edi
0x1800042fb  cmp     r12d, esi
0x1800042fe  jb      short loc_1800042DA
0x180004300  cmp     ebx, esi
0x180004302  jb      short loc_1800042C3
0x180004304  mov     rax, [rbp+arg_8]
0x180004308  mov     qword ptr [rbp+var_18], 0
0x180004310  mov     dword ptr [rbp+var_18+8], 0
0x180004317  mov     [rax], r13
0x18000431a  mov     [rax+8], esi
0x18000431d  xor     ebx, ebx
0x18000431f  lea     rcx, [rbp+var_18]; struct _SDIAG_PARAMSET *
0x180004323  call    ?SdpFreeParamSet@@YAJPEAU_SDIAG_PARAMSET@@@Z; SdpFreeParamSet(_SDIAG_PARAMSET *)
0x180004328  test    r15, r15
0x18000432b  jz      short loc_18000433C
0x18000432d  mov     rax, [r15]
0x180004330  mov     rcx, r15
0x180004333  mov     rax, [rax+10h]
0x180004337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000433c  test    r14, r14
0x18000433f  jz      short loc_180004350
0x180004341  mov     rax, [r14]
0x180004344  mov     rcx, r14
0x180004347  mov     rax, [rax+10h]
0x18000434b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004350  mov     eax, ebx
0x180004352  add     rsp, 38h
0x180004356  pop     r15
0x180004358  pop     r14
0x18000435a  pop     r13
0x18000435c  pop     r12
0x18000435e  pop     rdi
0x18000435f  pop     rsi
0x180004360  pop     rbx
0x180004361  pop     rbp
0x180004362  retn
0x180004363  mov     r9d, 80070057h
0x180004369  mov     r8d, 181h
0x18000436f  mov     ebx, r9d
0x180004372  jmp     loc_1800041D5
```
