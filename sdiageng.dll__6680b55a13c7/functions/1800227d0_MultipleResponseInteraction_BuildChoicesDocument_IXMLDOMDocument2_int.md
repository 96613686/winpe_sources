# MultipleResponseInteraction::BuildChoicesDocument(IXMLDOMDocument2 * *,int)

- ea: `0x1800227d0`
- end: `0x180022a24`
- name: `?BuildChoicesDocument@MultipleResponseInteraction@@MEAAJPEAPEAUIXMLDOMDocument2@@H@Z`
- size: `596`
- prototype: `__int64 __fastcall(MultipleResponseInteraction *this, struct IXMLDOMDocument2 **, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800227d0`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x180022830`: `<?xml version="1.0" encoding="utf-8"?><Choices/>`

## pseudocode

```c
__int64 __fastcall MultipleResponseInteraction::BuildChoicesDocument(
        MultipleResponseInteraction *this,
        struct IXMLDOMDocument2 **a2,
        unsigned int a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  struct IXMLDOMDocument2 *v8; // rsi
  int v9; // r8d
  __int64 v10; // r15
  __int64 v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int64 v14; // rax
  __int64 v15; // r15
  __int64 v16; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int64 v19; // rax
  __int128 v21; // [rsp+30h] [rbp-30h] BYREF
  __int128 v22; // [rsp+40h] [rbp-20h]
  __int128 v23; // [rsp+50h] [rbp-10h]
  struct IXMLDOMDocument2 *v24; // [rsp+98h] [rbp+38h] BYREF
  struct IXMLDOMDocument2 *v25; // [rsp+A8h] [rbp+48h] BYREF

  v25 = 0;
  v24 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    SdpDebugTrace(1u, L"MultipleResponseInteraction::BuildChoicesDocument", 327, -2147024809);
    goto LABEL_22;
  }
  v7 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Choices/>", &v25);
  v8 = v25;
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = 332;
LABEL_5:
    SdpDebugTrace(1u, L"MultipleResponseInteraction::BuildChoicesDocument", v9, v7);
    goto LABEL_20;
  }
  if ( !a3 )
  {
    v10 = 0;
    if ( *((_DWORD *)this + 32) )
    {
      while ( 1 )
      {
        if ( v24 )
        {
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v24->lpVtbl->Release)(v24);
          v24 = 0;
        }
        v11 = *((_QWORD *)this + 15);
        v12 = *(_OWORD *)(v11 + 48 * v10 + 16);
        v21 = *(_OWORD *)(v11 + 48 * v10);
        v13 = *(_OWORD *)(v11 + 48 * v10 + 32);
        v14 = *(_QWORD *)this;
        v22 = v12;
        v23 = v13;
        v7 = (*(__int64 (__fastcall **)(MultipleResponseInteraction *, __int128 *, struct IXMLDOMDocument2 **, _QWORD))(v14 + 104))(
               this,
               &v21,
               &v24,
               0);
        v6 = v7;
        if ( v7 < 0 )
          break;
        v7 = SdpXmlAppend(v8, 0, v24);
        v6 = v7;
        if ( v7 < 0 )
        {
          v9 = 348;
          goto LABEL_5;
        }
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= *((_DWORD *)this + 32) )
          goto LABEL_13;
      }
      v9 = 345;
      goto LABEL_5;
    }
  }
LABEL_13:
  v15 = 0;
  if ( *((_DWORD *)this + 28) )
  {
    while ( 1 )
    {
      if ( v24 )
      {
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v24->lpVtbl->Release)(v24);
        v24 = 0;
      }
      v16 = *((_QWORD *)this + 13);
      v17 = *(_OWORD *)(v16 + 48 * v15 + 16);
      v21 = *(_OWORD *)(v16 + 48 * v15);
      v18 = *(_OWORD *)(v16 + 48 * v15 + 32);
      v19 = *(_QWORD *)this;
      v22 = v17;
      v23 = v18;
      v7 = (*(__int64 (__fastcall **)(MultipleResponseInteraction *, __int128 *, struct IXMLDOMDocument2 **, _QWORD))(v19 + 104))(
             this,
             &v21,
             &v24,
             a3);
      v6 = v7;
      if ( v7 < 0 )
        break;
      v7 = SdpXmlAppend(v8, 0, v24);
      v6 = v7;
      if ( v7 < 0 )
      {
        v9 = 359;
        goto LABEL_5;
      }
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= *((_DWORD *)this + 28) )
        goto LABEL_19;
    }
    v9 = 356;
    goto LABEL_5;
  }
LABEL_19:
  *a2 = v8;
  ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->AddRef)(v8);
LABEL_20:
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
LABEL_22:
  if ( v24 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v24->lpVtbl->Release)(v24);
  return v6;
}

```

## disassembly

```asm
0x1800227d0  mov     [rsp-28h+arg_0], rbx
0x1800227d5  mov     [rsp-28h+arg_10], rsi
0x1800227da  push    rbp
0x1800227db  push    r12
0x1800227dd  push    r13
0x1800227df  push    r14
0x1800227e1  push    r15
0x1800227e3  mov     rbp, rsp
0x1800227e6  sub     rsp, 60h
0x1800227ea  mov     [rbp+arg_18], 0
0x1800227f2  mov     r13d, r8d
0x1800227f5  mov     [rbp+arg_8], 0
0x1800227fd  mov     r12, rdx
0x180022800  mov     r14, rcx
0x180022803  test    rdx, rdx
0x180022806  jnz     short loc_18002282C
0x180022808  mov     ebx, 80070057h
0x18002280d  lea     rdx, aMultiplerespon_12; "MultipleResponseInteraction::BuildChoic"...
0x180022814  mov     r9d, ebx; int
0x180022817  lea     ecx, [r12+1]; Level
0x18002281c  mov     r8d, 147h; int
0x180022822  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022827  jmp     loc_1800229C7
0x18002282c  lea     rdx, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x180022830  lea     rcx, aXmlVersion10En_25; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180022837  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18002283c  mov     rsi, [rbp+arg_18]
0x180022840  mov     ebx, eax
0x180022842  test    eax, eax
0x180022844  jns     short loc_180022865
0x180022846  mov     r8d, 14Ch; int
0x18002284c  mov     r9d, eax; int
0x18002284f  lea     rdx, aMultiplerespon_12; "MultipleResponseInteraction::BuildChoic"...
0x180022856  mov     ecx, 1; Level
0x18002285b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022860  jmp     loc_1800229B3
0x180022865  test    r13d, r13d
0x180022868  jnz     loc_18002290C
0x18002286e  xor     r15d, r15d
0x180022871  cmp     [r14+80h], r15d
0x180022878  jbe     loc_18002290C
0x18002287e  mov     rcx, [rbp+arg_8]
0x180022882  test    rcx, rcx
0x180022885  jz      short loc_18002289B
0x180022887  mov     rax, [rcx]
0x18002288a  mov     rax, [rax+10h]
0x18002288e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022893  mov     [rbp+arg_8], 0
0x18002289b  mov     rax, [r14+78h]
0x18002289f  lea     rcx, [r15+r15*2]
0x1800228a3  add     rcx, rcx
0x1800228a6  lea     r8, [rbp+arg_8]
0x1800228aa  xor     r9d, r9d
0x1800228ad  lea     rdx, [rbp+var_30]
0x1800228b1  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800228b5  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x1800228ba  movaps  [rbp+var_30], xmm0
0x1800228be  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x1800228c3  mov     rax, [r14]
0x1800228c6  mov     rcx, r14
0x1800228c9  movaps  [rbp+var_20], xmm1
0x1800228cd  movaps  [rbp+var_10], xmm0
0x1800228d1  mov     rax, [rax+68h]
0x1800228d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228da  mov     ebx, eax
0x1800228dc  test    eax, eax
0x1800228de  js      loc_180022A03
0x1800228e4  mov     r8, [rbp+arg_8]; struct IXMLDOMDocument2 *
0x1800228e8  xor     edx, edx; struct IXMLDOMElement *
0x1800228ea  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1800228ed  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x1800228f2  mov     ebx, eax
0x1800228f4  test    eax, eax
0x1800228f6  js      loc_1800229F8
0x1800228fc  inc     r15d
0x1800228ff  cmp     r15d, [r14+80h]
0x180022906  jb      loc_18002287E
0x18002290c  xor     r15d, r15d
0x18002290f  cmp     [r14+70h], r15d
0x180022913  jbe     loc_1800229A0
0x180022919  mov     rcx, [rbp+arg_8]
0x18002291d  test    rcx, rcx
0x180022920  jz      short loc_180022936
0x180022922  mov     rax, [rcx]
0x180022925  mov     rax, [rax+10h]
0x180022929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002292e  mov     [rbp+arg_8], 0
0x180022936  mov     rax, [r14+68h]
0x18002293a  lea     rcx, [r15+r15*2]
0x18002293e  add     rcx, rcx
0x180022941  lea     r8, [rbp+arg_8]
0x180022945  mov     r9d, r13d
0x180022948  lea     rdx, [rbp+var_30]
0x18002294c  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180022950  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x180022955  movaps  [rbp+var_30], xmm0
0x180022959  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x18002295e  mov     rax, [r14]
0x180022961  mov     rcx, r14
0x180022964  movaps  [rbp+var_20], xmm1
0x180022968  movaps  [rbp+var_10], xmm0
0x18002296c  mov     rax, [rax+68h]
0x180022970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022975  mov     ebx, eax
0x180022977  test    eax, eax
0x180022979  js      loc_180022A19
0x18002297f  mov     r8, [rbp+arg_8]; struct IXMLDOMDocument2 *
0x180022983  xor     edx, edx; struct IXMLDOMElement *
0x180022985  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180022988  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18002298d  mov     ebx, eax
0x18002298f  test    eax, eax
0x180022991  js      short loc_180022A0E
0x180022993  inc     r15d
0x180022996  cmp     r15d, [r14+70h]
0x18002299a  jb      loc_180022919
0x1800229a0  mov     [r12], rsi
0x1800229a4  mov     rcx, rsi
0x1800229a7  mov     rax, [rsi]
0x1800229aa  mov     rax, [rax+8]
0x1800229ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229b3  test    rsi, rsi
0x1800229b6  jz      short loc_1800229C7
0x1800229b8  mov     rax, [rsi]
0x1800229bb  mov     rcx, rsi
0x1800229be  mov     rax, [rax+10h]
0x1800229c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229c7  mov     rcx, [rbp+arg_8]
0x1800229cb  test    rcx, rcx
0x1800229ce  jz      short loc_1800229DC
0x1800229d0  mov     rax, [rcx]
0x1800229d3  mov     rax, [rax+10h]
0x1800229d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229dc  lea     r11, [rsp+60h+var_s0]
0x1800229e1  mov     eax, ebx
0x1800229e3  mov     rbx, [r11+30h]
0x1800229e7  mov     rsi, [r11+40h]
0x1800229eb  mov     rsp, r11
0x1800229ee  pop     r15
0x1800229f0  pop     r14
0x1800229f2  pop     r13
0x1800229f4  pop     r12
0x1800229f6  pop     rbp
0x1800229f7  retn
0x1800229f8  mov     r8d, 15Ch
0x1800229fe  jmp     loc_18002284C
0x180022a03  mov     r8d, 159h
0x180022a09  jmp     loc_18002284C
0x180022a0e  mov     r8d, 167h
0x180022a14  jmp     loc_18002284C
0x180022a19  mov     r8d, 164h
0x180022a1f  jmp     loc_18002284C
```
