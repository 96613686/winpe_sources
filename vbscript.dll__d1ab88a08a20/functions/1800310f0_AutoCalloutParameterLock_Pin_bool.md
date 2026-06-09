# AutoCalloutParameterLock::Pin(bool)

- ea: `0x1800310f0`
- end: `0x180031353`
- name: `?Pin@AutoCalloutParameterLock@@AEAAJ_N@Z`
- size: `611`
- prototype: `__int64 __fastcall(AutoCalloutParameterLock *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180013e74`
- `0x18001cb70`

## callees

- `0x180005dd8`
- `0x1800310f0`
- `0x180069fd4`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800311a0`
- `OLE32!CoTaskMemAlloc` at `0x1800311a0`
- `OLE32!CoTaskMemFree` at `0x180031332`
- `OLE32!CoTaskMemFree` at `0x180031332`

## pseudocode

```c
__int64 __fastcall AutoCalloutParameterLock::Pin(AutoCalloutParameterLock *this, char a2)
{
  unsigned int v2; // r15d
  unsigned int v3; // ebx
  __int128 v6; // xmm6
  AutoVariantRef *v7; // rdi
  __int16 *v8; // rax
  __int16 v9; // cx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rdx
  char *v14; // rax
  _QWORD *v15; // rsi
  int v17; // r14d
  int v18; // r9d
  int v19; // r9d
  bool v20; // al
  __int64 *v21; // rcx
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int128 v24; // [rsp+20h] [rbp-58h]
  __int128 v25; // [rsp+30h] [rbp-48h]

  v2 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 6) )
  {
    while ( 1 )
    {
      v6 = 0;
      v7 = (AutoVariantRef *)(*((_QWORD *)this + 2) + 32LL * v3);
      DWORD1(v24) = 0;
      v25 = 0;
      if ( *(_WORD *)v7 != 16396 )
        break;
      v8 = (__int16 *)*((_QWORD *)v7 + 1);
      v9 = *v8;
      if ( *v8 == 8 )
      {
        v10 = *((_QWORD *)v8 + 1);
        if ( !v10 )
          goto LABEL_9;
        v11 = 0;
        v12 = 0;
      }
      else
      {
        if ( v9 != 9 && v9 != 13 )
        {
          if ( v9 == 24588 )
          {
            v21 = (__int64 *)*((_QWORD *)v8 + 1);
            if ( !v21 )
              goto LABEL_9;
            v10 = *v21;
            if ( !v10 )
              goto LABEL_9;
          }
          else
          {
            if ( (v9 & 0x6000) != 0x2000 )
              goto LABEL_9;
            v10 = *((_QWORD *)v8 + 1);
            if ( !v10 )
              goto LABEL_9;
          }
          goto LABEL_34;
        }
        v10 = *((_QWORD *)v8 + 1);
        if ( !v10 )
          goto LABEL_9;
        v11 = 2;
        v12 = 0;
      }
LABEL_6:
      v13 = *((_QWORD *)v7 + 3);
      *((_QWORD *)&v24 + 1) = v10;
      LODWORD(v24) = v11;
      if ( !v13 || (v18 = *(_DWORD *)(v13 + 8), v18 != v11) )
      {
LABEL_7:
        v14 = (char *)CoTaskMemAlloc(0x28u);
        v15 = v14;
        if ( v14 )
        {
          *(_OWORD *)(v14 + 8) = v24;
          *(_OWORD *)(v14 + 24) = v6;
          v17 = AutoVariantRef::PinnableData::Pin((AutoVariantRef::PinnableData *)(v14 + 8));
          if ( v17 < 0 )
          {
            CoTaskMemFree(v15);
            if ( a2 )
              AutoVariantRef::ClearCurrentPinnableData(v7);
            v2 = v17;
          }
          else
          {
            *v15 = *((_QWORD *)v7 + 3);
            *((_QWORD *)v7 + 3) = v15;
          }
        }
        else
        {
          v2 = -2147024882;
        }
        goto LABEL_9;
      }
      if ( !v18 )
        goto LABEL_17;
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
          goto LABEL_7;
LABEL_17:
        v20 = *(_QWORD *)(v13 + 16) == v10;
        goto LABEL_18;
      }
      v23 = *(_QWORD *)(v13 + 16);
      v20 = v23 == v10 && (!v23 || *(_QWORD *)(v13 + 24) == v12);
LABEL_18:
      if ( !v20 )
        goto LABEL_7;
LABEL_9:
      if ( ++v3 >= *((_DWORD *)this + 6) )
        return v2;
    }
    if ( *(_WORD *)v7 != 24588 )
      goto LABEL_9;
    v22 = (__int64 *)*((_QWORD *)v7 + 1);
    if ( !v22 )
      goto LABEL_9;
    v10 = *v22;
    if ( !v10 )
      goto LABEL_9;
LABEL_34:
    v12 = *(_QWORD *)(v10 + 16);
    v11 = 1;
    *(_QWORD *)&v25 = v12;
    v6 = v25;
    goto LABEL_6;
  }
  return v2;
}

```

## disassembly

```asm
0x1800310f0  mov     rax, rsp
0x1800310f3  push    rbx
0x1800310f4  push    rbp
0x1800310f5  push    r12
0x1800310f7  push    r15
0x1800310f9  sub     rsp, 58h
0x1800310fd  xor     r15d, r15d
0x180031100  xor     ebx, ebx
0x180031102  movzx   r12d, dl
0x180031106  mov     rbp, rcx
0x180031109  cmp     [rcx+18h], ebx
0x18003110c  jbe     loc_1800311F8
0x180031112  mov     [rax+10h], rdi
0x180031116  mov     edx, 600Ch
0x18003111b  mov     [rax+18h], r13
0x18003111f  mov     r8d, 6000h
0x180031125  movaps  xmmword ptr [rax-38h], xmm6
0x180031129  mov     r13d, 400Ch
0x18003112f  mov     [rax+8], rsi
0x180031133  mov     r9d, 2000h
0x180031139  mov     [rax-28h], r14
0x18003113d  nop     dword ptr [rax]
0x180031140  xorps   xmm6, xmm6
0x180031143  mov     edi, ebx
0x180031145  shl     rdi, 5
0x180031149  add     rdi, [rbp+10h]
0x18003114d  movups  [rsp+78h+var_58], xmm6
0x180031152  movups  [rsp+78h+var_48], xmm6
0x180031157  movzx   eax, word ptr [rdi]
0x18003115a  cmp     ax, r13w
0x18003115e  jnz     loc_1800312D3
0x180031164  mov     rax, [rdi+8]
0x180031168  movzx   ecx, word ptr [rax]
0x18003116b  cmp     cx, 8
0x18003116f  jnz     loc_18003126E
0x180031175  mov     rcx, [rax+8]
0x180031179  test    rcx, rcx
0x18003117c  jz      short loc_1800311CB
0x18003117e  xor     eax, eax
0x180031180  movq    r8, xmm6
0x180031185  mov     rdx, [rdi+18h]
0x180031189  mov     qword ptr [rsp+78h+var_58+8], rcx
0x18003118e  mov     dword ptr [rsp+78h+var_58], eax
0x180031192  test    rdx, rdx
0x180031195  jnz     loc_180031234
0x18003119b  mov     ecx, 28h ; '('; cb
0x1800311a0  call    cs:__imp_CoTaskMemAlloc
0x1800311a7  nop     dword ptr [rax+rax+00h]
0x1800311ac  mov     rsi, rax
0x1800311af  test    rax, rax
0x1800311b2  jnz     short loc_180031207
0x1800311b4  mov     r15d, 8007000Eh
0x1800311ba  mov     edx, 600Ch
0x1800311bf  mov     r8d, 6000h
0x1800311c5  mov     r9d, 2000h
0x1800311cb  inc     ebx
0x1800311cd  cmp     ebx, [rbp+18h]
0x1800311d0  jb      loc_180031140
0x1800311d6  movaps  xmm6, [rsp+78h+var_38]
0x1800311db  mov     r14, [rsp+78h+var_28]
0x1800311e0  mov     r13, [rsp+78h+arg_10]
0x1800311e8  mov     rdi, [rsp+78h+arg_8]
0x1800311f0  mov     rsi, [rsp+78h+arg_0]
0x1800311f8  mov     eax, r15d
0x1800311fb  add     rsp, 58h
0x1800311ff  pop     r15
0x180031201  pop     r12
0x180031203  pop     rbp
0x180031204  pop     rbx
0x180031205  retn
0x180031207  movups  xmm0, [rsp+78h+var_58]
0x18003120c  lea     rcx, [rax+8]; this
0x180031210  movups  xmmword ptr [rcx], xmm0
0x180031213  movups  xmmword ptr [rcx+10h], xmm6
0x180031217  call    ?Pin@PinnableData@AutoVariantRef@@QEAAJXZ; AutoVariantRef::PinnableData::Pin(void)
0x18003121c  mov     r14d, eax
0x18003121f  test    eax, eax
0x180031221  js      loc_18003132F
0x180031227  mov     rax, [rdi+18h]
0x18003122b  mov     [rsi], rax
0x18003122e  mov     [rdi+18h], rsi
0x180031232  jmp     short loc_1800311BA
0x180031234  mov     r9d, [rdx+8]
0x180031238  cmp     r9d, eax
0x18003123b  jnz     loc_18003119B
0x180031241  test    r9d, r9d
0x180031244  jz      short loc_18003125A
0x180031246  sub     r9d, 1
0x18003124a  jz      loc_18003130D
0x180031250  cmp     r9d, 1
0x180031254  jnz     loc_18003119B
0x18003125a  cmp     [rdx+10h], rcx
0x18003125e  setz    al
0x180031261  test    al, al
0x180031263  jz      loc_18003119B
0x180031269  jmp     loc_1800311BA
0x18003126e  cmp     cx, 9
0x180031272  jz      short loc_1800312B7
0x180031274  cmp     cx, 0Dh
0x180031278  jz      short loc_1800312B7
0x18003127a  cmp     cx, dx
0x18003127d  jnz     short loc_18003129A
0x18003127f  mov     rcx, [rax+8]
0x180031283  test    rcx, rcx
0x180031286  jz      loc_1800311CB
0x18003128c  mov     rcx, [rcx]
0x18003128f  test    rcx, rcx
0x180031292  jz      loc_1800311CB
0x180031298  jmp     short loc_1800312F5
0x18003129a  and     cx, r8w
0x18003129e  cmp     cx, r9w
0x1800312a2  jnz     loc_1800311CB
0x1800312a8  mov     rcx, [rax+8]
0x1800312ac  test    rcx, rcx
0x1800312af  jz      loc_1800311CB
0x1800312b5  jmp     short loc_1800312F5
0x1800312b7  mov     rcx, [rax+8]
0x1800312bb  test    rcx, rcx
0x1800312be  jz      loc_1800311CB
0x1800312c4  mov     eax, 2
0x1800312c9  movq    r8, xmm6
0x1800312ce  jmp     loc_180031185
0x1800312d3  cmp     ax, dx
0x1800312d6  jnz     loc_1800311CB
0x1800312dc  mov     rcx, [rdi+8]
0x1800312e0  test    rcx, rcx
0x1800312e3  jz      loc_1800311CB
0x1800312e9  mov     rcx, [rcx]
0x1800312ec  test    rcx, rcx
0x1800312ef  jz      loc_1800311CB
0x1800312f5  mov     r8, [rcx+10h]
0x1800312f9  mov     eax, 1
0x1800312fe  mov     qword ptr [rsp+78h+var_48], r8
0x180031303  movups  xmm6, [rsp+78h+var_48]
0x180031308  jmp     loc_180031185
0x18003130d  mov     rax, [rdx+10h]
0x180031311  cmp     rax, rcx
0x180031314  jnz     short loc_180031328
0x180031316  test    rax, rax
0x180031319  jz      short loc_180031321
0x18003131b  cmp     [rdx+18h], r8
0x18003131f  jnz     short loc_180031328
0x180031321  mov     al, 1
0x180031323  jmp     loc_180031261
0x180031328  xor     al, al
0x18003132a  jmp     loc_180031261
0x18003132f  mov     rcx, rsi; pv
0x180031332  call    cs:__imp_CoTaskMemFree
0x180031339  nop     dword ptr [rax+rax+00h]
0x18003133e  test    r12b, r12b
0x180031341  jz      short loc_18003134B
0x180031343  mov     rcx, rdi; this
0x180031346  call    ?ClearCurrentPinnableData@AutoVariantRef@@AEAAXXZ; AutoVariantRef::ClearCurrentPinnableData(void)
0x18003134b  mov     r15d, r14d
0x18003134e  jmp     loc_1800311BA
```
