# MultipleResponseInteraction::InitializeChoices(IXMLDOMNode *)

- ea: `0x180023020`
- end: `0x180023256`
- name: `?InitializeChoices@MultipleResponseInteraction@@MEAAJPEAUIXMLDOMNode@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(MultipleResponseInteraction *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800012b0`
- `0x180023020`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x180029882`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall MultipleResponseInteraction::InitializeChoices(
        MultipleResponseInteraction *this,
        struct IXMLDOMNode *a2)
{
  struct IXMLDOMNodeList *v2; // r15
  struct IXMLDOMNode *v3; // rdi
  __int64 v4; // r14
  void *v5; // r12
  unsigned int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  MultipleResponseInteraction *v9; // rcx
  int ChildNodes; // eax
  void *v11; // rax
  __int64 v12; // r13
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned int v18; // [rsp+78h] [rbp+50h] BYREF
  struct IXMLDOMNode *v19; // [rsp+80h] [rbp+58h] BYREF
  struct IXMLDOMNodeList *v20; // [rsp+88h] [rbp+60h] BYREF

  v2 = 0;
  v3 = 0;
  LODWORD(v4) = 0;
  v20 = 0;
  v5 = 0;
  v19 = 0;
  v18 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 150;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v20, &v18);
  v6 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    SdpDebugTrace(1u, L"MultipleResponseInteraction::InitializeChoices", 156, ChildNodes);
    v2 = v20;
    LODWORD(v4) = v18;
LABEL_5:
    v9 = this;
    goto LABEL_21;
  }
  v4 = v18;
  v2 = v20;
  if ( v18 )
  {
    v11 = operator new[](saturated_mul(v18, 0x30u));
    v5 = v11;
    if ( !v11 )
    {
      v6 = -2147467261;
      v7 = 163;
LABEL_3:
      v8 = v6;
LABEL_4:
      SdpDebugTrace(1u, L"MultipleResponseInteraction::InitializeChoices", v7, v8);
      goto LABEL_5;
    }
    memset_0(v11, 0, 48 * v4);
    v12 = 0;
    if ( (_DWORD)v4 )
    {
      while ( 1 )
      {
        if ( v3 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
          v19 = 0;
        }
        v13 = SdpXmlNextNode(v2, &v19);
        v6 = v13;
        if ( v13 < 0 )
          break;
        v3 = v19;
        v14 = SdpXmlCheckNode(v19, L"Choice");
        v6 = v14;
        if ( v14 < 0 )
        {
          v8 = v14;
          goto LABEL_29;
        }
        if ( v14 == 1 || !v3 )
        {
          v6 = -2147467259;
          v8 = -2147467259;
LABEL_29:
          v7 = 172;
          goto LABEL_4;
        }
        v15 = (*(__int64 (__fastcall **)(MultipleResponseInteraction *, struct IXMLDOMNode *, __int64))(*(_QWORD *)this + 88LL))(
                this,
                v3,
                (__int64)v5 + 48 * v12);
        v6 = v15;
        if ( v15 < 0 )
        {
          v8 = v15;
          v7 = 175;
          goto LABEL_4;
        }
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= (unsigned int)v4 )
          goto LABEL_20;
      }
      SdpDebugTrace(1u, L"MultipleResponseInteraction::InitializeChoices", 171, v13);
      v3 = v19;
      goto LABEL_5;
    }
  }
LABEL_20:
  v9 = this;
  *((_QWORD *)this + 13) = v5;
  v5 = 0;
  *((_DWORD *)this + 28) = v4;
  LODWORD(v4) = 0;
LABEL_21:
  (*(void (__fastcall **)(MultipleResponseInteraction *, void *, _QWORD))(*(_QWORD *)v9 + 120LL))(
    v9,
    v5,
    (unsigned int)v4);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v2->lpVtbl->Release)(v2);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  return v6;
}

```

## disassembly

```asm
0x180023020  mov     [rsp-40h+arg_0], rcx
0x180023025  push    rbp
0x180023026  push    rbx
0x180023027  push    rsi
0x180023028  push    rdi
0x180023029  push    r12
0x18002302b  push    r13
0x18002302d  push    r14
0x18002302f  push    r15
0x180023031  mov     rbp, rsp
0x180023034  sub     rsp, 28h
0x180023038  xor     r15d, r15d
0x18002303b  xor     edi, edi
0x18002303d  xor     r14d, r14d
0x180023040  mov     [rbp+arg_18], r15
0x180023044  xor     r12d, r12d
0x180023047  mov     [rbp+arg_10], rdi
0x18002304b  mov     [rbp+arg_8], r14d
0x18002304f  test    rdx, rdx
0x180023052  jnz     short loc_18002307C
0x180023054  mov     ebx, 80070057h
0x180023059  mov     r8d, 96h; int
0x18002305f  mov     r9d, ebx; int
0x180023062  mov     ecx, 1; Level
0x180023067  lea     rdx, aMultiplerespon_4; "MultipleResponseInteraction::Initialize"...
0x18002306e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180023073  mov     rcx, [rbp+arg_0]
0x180023077  jmp     loc_1800231C4
0x18002307c  lea     r9, [rbp+arg_8]; unsigned int *
0x180023080  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180023082  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180023086  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18002308b  mov     ebx, eax
0x18002308d  test    eax, eax
0x18002308f  jns     short loc_1800230B5
0x180023091  mov     r9d, eax; int
0x180023094  lea     rdx, aMultiplerespon_4; "MultipleResponseInteraction::Initialize"...
0x18002309b  mov     r8d, 9Ch; int
0x1800230a1  mov     ecx, 1; Level
0x1800230a6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800230ab  mov     r15, [rbp+arg_18]
0x1800230af  mov     r14d, [rbp+arg_8]
0x1800230b3  jmp     short loc_180023073
0x1800230b5  mov     r14d, [rbp+arg_8]
0x1800230b9  mov     r15, [rbp+arg_18]
0x1800230bd  test    r14d, r14d
0x1800230c0  jz      loc_1800231B2
0x1800230c6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800230cd  mov     eax, 30h ; '0'
0x1800230d2  mul     r14
0x1800230d5  cmovb   rax, rcx
0x1800230d9  mov     rcx, rax; unsigned __int64
0x1800230dc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800230e1  mov     r12, rax
0x1800230e4  test    rax, rax
0x1800230e7  jnz     short loc_1800230F9
0x1800230e9  mov     ebx, 80004003h
0x1800230ee  mov     r8d, 0A3h
0x1800230f4  jmp     loc_18002305F
0x1800230f9  lea     r8, [r14+r14*2]
0x1800230fd  xor     edx, edx; Val
0x1800230ff  shl     r8, 4; Size
0x180023103  mov     rcx, r12; void *
0x180023106  call    memset_0
0x18002310b  xor     r13d, r13d
0x18002310e  test    r14d, r14d
0x180023111  jz      loc_1800231B2
0x180023117  lea     esi, [r13+1]
0x18002311b  test    rdi, rdi
0x18002311e  jz      short loc_180023137
0x180023120  mov     rax, [rdi]
0x180023123  mov     rcx, rdi
0x180023126  mov     rax, [rax+10h]
0x18002312a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002312f  mov     [rbp+arg_10], 0
0x180023137  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18002313b  mov     rcx, r15; struct IXMLDOMNodeList *
0x18002313e  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180023143  mov     ebx, eax
0x180023145  test    eax, eax
0x180023147  js      loc_180023236
0x18002314d  mov     rdi, [rbp+arg_10]
0x180023151  lea     rdx, aChoice; "Choice"
0x180023158  mov     rcx, rdi; struct IXMLDOMNode *
0x18002315b  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180023160  mov     ebx, eax
0x180023162  test    eax, eax
0x180023164  js      loc_180023226
0x18002316a  cmp     eax, esi
0x18002316c  jz      loc_18002321C
0x180023172  test    rdi, rdi
0x180023175  jz      loc_18002321C
0x18002317b  mov     rcx, [rbp+arg_0]
0x18002317f  lea     r8, ds:0[r13*2]
0x180023187  add     r8, r13
0x18002318a  mov     rdx, rdi
0x18002318d  shl     r8, 4
0x180023191  add     r8, r12
0x180023194  mov     r9, [rcx]
0x180023197  mov     rax, [r9+58h]
0x18002319b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231a0  mov     ebx, eax
0x1800231a2  test    eax, eax
0x1800231a4  js      short loc_180023211
0x1800231a6  add     r13d, esi
0x1800231a9  cmp     r13d, r14d
0x1800231ac  jb      loc_18002311B
0x1800231b2  mov     rcx, [rbp+arg_0]
0x1800231b6  mov     [rcx+68h], r12
0x1800231ba  xor     r12d, r12d
0x1800231bd  mov     [rcx+70h], r14d
0x1800231c1  xor     r14d, r14d
0x1800231c4  mov     rax, [rcx]
0x1800231c7  mov     r8d, r14d
0x1800231ca  mov     rdx, r12
0x1800231cd  mov     rax, [rax+78h]
0x1800231d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231d6  test    r15, r15
0x1800231d9  jz      short loc_1800231EA
0x1800231db  mov     rax, [r15]
0x1800231de  mov     rcx, r15
0x1800231e1  mov     rax, [rax+10h]
0x1800231e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231ea  test    rdi, rdi
0x1800231ed  jz      short loc_1800231FE
0x1800231ef  mov     rax, [rdi]
0x1800231f2  mov     rcx, rdi
0x1800231f5  mov     rax, [rax+10h]
0x1800231f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231fe  mov     eax, ebx
0x180023200  add     rsp, 28h
0x180023204  pop     r15
0x180023206  pop     r14
0x180023208  pop     r13
0x18002320a  pop     r12
0x18002320c  pop     rdi
0x18002320d  pop     rsi
0x18002320e  pop     rbx
0x18002320f  pop     rbp
0x180023210  retn
0x180023211  mov     r9d, eax
0x180023214  mov     r8d, 0AFh
0x18002321a  jmp     short loc_18002322F
0x18002321c  mov     ebx, 80004005h
0x180023221  mov     r9d, ebx
0x180023224  jmp     short loc_180023229
0x180023226  mov     r9d, eax
0x180023229  mov     r8d, 0ACh
0x18002322f  mov     ecx, esi
0x180023231  jmp     loc_180023067
0x180023236  mov     r9d, eax; int
0x180023239  lea     rdx, aMultiplerespon_4; "MultipleResponseInteraction::Initialize"...
0x180023240  mov     r8d, 0ABh; int
0x180023246  mov     ecx, esi; Level
0x180023248  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002324d  mov     rdi, [rbp+arg_10]
0x180023251  jmp     loc_180023073
```
