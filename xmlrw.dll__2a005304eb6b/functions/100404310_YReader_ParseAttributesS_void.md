# YReader::ParseAttributesS(void)

- ea: `0x100404310`
- end: `0x10040465f`
- name: `?ParseAttributesS@YReader@@AEAAXXZ`
- size: `847`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x100401780`
- `0x1004019c0`
- `0x100404310`
- `0x100404670`
- `0x10040b880`
- `0x10040c7b0`
- `0x100415950`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseAttributesS(YReader *this)
{
  unsigned int v2; // edx
  __int64 v3; // rdi
  __int64 v4; // rax
  const void *v5; // rcx
  bool v6; // zf
  int v7; // eax
  __int64 v8; // rdx
  struct StringPtr *v9; // rdx
  int v10; // eax
  unsigned int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  int i; // eax
  int v16; // ecx
  void (__fastcall *v17)(YReader *__hidden); // rax
  __int128 v18; // [rsp+20h] [rbp-18h] BYREF

  *((_DWORD *)this + 710) = 0;
  *((_DWORD *)this + 1326) = 0;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  while ( *((_DWORD *)this + 28) != 5 )
  {
    switch ( *((_DWORD *)this + 28) )
    {
      case 6:
        *((_DWORD *)this + 444) = 1;
        if ( *((_DWORD *)this + 710) )
          (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 72LL))(
            *((_QWORD *)this + 13),
            (char *)this + 1800);
        v17 = YReader::ParseEETagEndS;
        goto LABEL_37;
      case 0xC:
        v2 = *((_DWORD *)this + 710);
        if ( *((_DWORD *)this + 711) == v2 )
        {
          _stack<Attribute,16>::grow((char *)this + 2816);
          v2 = *((_DWORD *)this + 710);
        }
        v3 = *((_QWORD *)this + 354) + 152LL * v2;
        *((_DWORD *)this + 710) = v2 + 1;
        YReader::GetTokenQName(this, (struct StringPtr *)v3, (struct StringPtr *)(v3 + 16));
        *(_DWORD *)(v3 + 96) = 0;
        *(_DWORD *)(v3 + 144) = 0;
        *(_OWORD *)(v3 + 64) = CodeStringPtr::CDATA;
        if ( *(_DWORD *)(v3 + 24) )
        {
          v4 = *(unsigned int *)(v3 + 24);
          if ( (_DWORD)v4 != dword_100450B48 )
            goto LABEL_15;
          v5 = *(const void **)(v3 + 16);
        }
        else
        {
          v4 = *(unsigned int *)(v3 + 8);
          if ( (_DWORD)v4 != dword_100450B48 )
            goto LABEL_15;
          v5 = *(const void **)v3;
        }
        v6 = memcmp(v5, CodeStringPtr::xmlns, 2 * v4) == 0;
        v7 = 1;
        if ( !v6 )
LABEL_15:
          v7 = 0;
        *(_DWORD *)(v3 + 100) = v7;
        if ( v7 )
        {
          YReader::ParseAttributeValue(this, 0);
          YReader::NormalizeAttributeValue(this, (struct StringPtr *)(v3 + 80));
          v8 = *(unsigned int *)(v3 + 24);
          *(_QWORD *)(v3 + 104) = 0;
          if ( (_DWORD)v8 )
          {
            v10 = *(_DWORD *)(v3 + 8) - v8;
            *(_QWORD *)&v18 = *(_QWORD *)v3 + 2 * (v8 + 1);
            v9 = (struct StringPtr *)&v18;
            DWORD2(v18) = v10 - 1;
          }
          else
          {
            v9 = (struct StringPtr *)&CodeStringPtr::empty;
          }
          NamespaceSupport::PushPrefix((YReader *)((char *)this + 512), v9, (struct StringPtr *)(v3 + 80));
          *(_OWORD *)(v3 + 32) = *(_OWORD *)&CodeStringPtr::xmlnsUri;
          *(_OWORD *)(v3 + 48) = CodeStringPtr::empty;
          v11 = *((_DWORD *)this + 1326);
          if ( *((_DWORD *)this + 1327) == v11 )
          {
            _stack<Attribute,16>::grow((char *)this + 5280);
            v11 = *((_DWORD *)this + 1326);
          }
          *((_DWORD *)this + 1326) = v11 + 1;
          v12 = 152LL * v11;
          v13 = *((_QWORD *)this + 662);
          *(_OWORD *)(v12 + v13) = *(_OWORD *)v3;
          *(_OWORD *)(v12 + v13 + 16) = *(_OWORD *)(v3 + 16);
          *(_OWORD *)(v12 + v13 + 32) = *(_OWORD *)(v3 + 32);
          *(_OWORD *)(v12 + v13 + 48) = *(_OWORD *)(v3 + 48);
          *(_OWORD *)(v12 + v13 + 64) = *(_OWORD *)(v3 + 64);
          *(_OWORD *)(v12 + v13 + 80) = *(_OWORD *)(v3 + 80);
          *(_OWORD *)(v12 + v13 + 96) = *(_OWORD *)(v3 + 96);
          *(_OWORD *)(v12 + v13 + 112) = *(_OWORD *)(v3 + 112);
          *(_OWORD *)(v12 + v13 + 128) = *(_OWORD *)(v3 + 128);
          *(_QWORD *)(v12 + v13 + 144) = *(_QWORD *)(v3 + 144);
          --*((_DWORD *)this + 710);
        }
        else
        {
          v14 = 0x7FFFFFFF;
          if ( *((int *)this + 458) > 0 )
            v14 = *((_DWORD *)this + 458);
          *((_DWORD *)this + 77) = v14;
          (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
          *(_OWORD *)(v3 + 104) = *((_OWORD *)this + 17);
          *(_OWORD *)(v3 + 120) = *((_OWORD *)this + 18);
          *(_WORD *)(v3 + 136) = *((_WORD *)this + 152);
          for ( i = *((_DWORD *)this + 28); i >= 7; i = *((_DWORD *)this + 28) )
          {
            if ( (unsigned int)i > 0xB )
              break;
            v16 = 0x7FFFFFFF;
            if ( *((int *)this + 458) > 0 )
              v16 = *((_DWORD *)this + 458);
            *((_DWORD *)this + 77) = v16;
            (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
          }
        }
        break;
      case 0x3B:
        MXRRaiseException(-1072894463);
        JUMPOUT(0x10040465ELL);
    }
  }
  *((_DWORD *)this + 444) = 2;
  if ( *((_DWORD *)this + 710) )
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 72LL))(
      *((_QWORD *)this + 13),
      (char *)this + 1800);
  v17 = YReader::ParseTagEndS;
LABEL_37:
  *(_QWORD *)&v18 = v17;
  DWORD2(v18) = 0;
  *((_OWORD *)this + 94) = v18;
}

```

## disassembly

```asm
0x100404310  mov     [rsp+arg_10], rbx
0x100404315  mov     [rsp+arg_18], rbp
0x10040431a  push    r14
0x10040431c  sub     rsp, 30h
0x100404320  mov     rbx, rcx
0x100404323  xor     r14d, r14d
0x100404326  mov     [rcx+0B18h], r14d
0x10040432d  mov     [rcx+14B8h], r14d
0x100404334  add     rcx, 28h ; '('
0x100404338  mov     rax, [rbx+0D8h]
0x10040433f  call    cs:__guard_dispatch_icall_fptr
0x100404345  mov     [rsp+38h+arg_0], rsi
0x10040434a  mov     [rsp+38h+arg_8], rdi
0x10040434f  nop
0x100404350  mov     ecx, [rbx+70h]
0x100404353  sub     ecx, 5
0x100404356  jz      loc_1004045F1
0x10040435c  sub     ecx, 1
0x10040435f  jz      loc_1004045BD
0x100404365  sub     ecx, 6
0x100404368  jz      short loc_100404375
0x10040436a  cmp     ecx, 2Fh ; '/'
0x10040436d  jz      loc_100404654
0x100404373  jmp     short loc_100404350
0x100404375  lea     rsi, [rbx+0B00h]
0x10040437c  mov     edx, [rsi+18h]
0x10040437f  cmp     [rsi+1Ch], edx
0x100404382  jnz     short loc_100404391
0x100404384  xor     edx, edx
0x100404386  mov     rcx, rsi
0x100404389  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x10040438e  mov     edx, [rsi+18h]
0x100404391  mov     eax, edx
0x100404393  mov     rcx, rbx; this
0x100404396  imul    rdi, rax, 98h
0x10040439d  lea     eax, [rdx+1]
0x1004043a0  add     rdi, [rsi+10h]
0x1004043a4  mov     rdx, rdi; struct StringPtr *
0x1004043a7  mov     [rsi+18h], eax
0x1004043aa  lea     r8, [rdi+10h]; struct StringPtr *
0x1004043ae  call    ?GetTokenQName@YReader@@AEAAXPEAUStringPtr@@0@Z; YReader::GetTokenQName(StringPtr *,StringPtr *)
0x1004043b3  movups  xmm0, xmmword ptr cs:?CDATA@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::CDATA
0x1004043ba  mov     [rdi+60h], r14d
0x1004043be  mov     [rdi+90h], r14d
0x1004043c5  movups  xmmword ptr [rdi+40h], xmm0
0x1004043c9  cmp     [rdi+18h], r14d
0x1004043cd  jz      short loc_1004043E0
0x1004043cf  mov     eax, [rdi+18h]
0x1004043d2  cmp     eax, cs:dword_100450B48
0x1004043d8  jnz     short loc_100404409
0x1004043da  mov     rcx, [rdi+10h]
0x1004043de  jmp     short loc_1004043EE
0x1004043e0  mov     eax, [rdi+8]
0x1004043e3  cmp     eax, cs:dword_100450B48
0x1004043e9  jnz     short loc_100404409
0x1004043eb  mov     rcx, [rdi]; Buf1
0x1004043ee  mov     rdx, cs:?xmlns@CodeStringPtr@@2UStringPtr@@A; Buf2
0x1004043f5  mov     r8, rax
0x1004043f8  add     r8, r8; Size
0x1004043fb  call    memcmp
0x100404400  test    eax, eax
0x100404402  mov     eax, 1
0x100404407  jz      short loc_10040440C
0x100404409  mov     eax, r14d
0x10040440c  mov     [rdi+64h], eax
0x10040440f  test    eax, eax
0x100404411  jz      loc_100404527
0x100404417  xor     edx, edx; bool
0x100404419  mov     rcx, rbx; this
0x10040441c  call    ?ParseAttributeValue@YReader@@AEAAX_N@Z; YReader::ParseAttributeValue(bool)
0x100404421  lea     rdx, [rdi+50h]; struct StringPtr *
0x100404425  mov     rcx, rbx; this
0x100404428  call    ?NormalizeAttributeValue@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::NormalizeAttributeValue(StringPtr *)
0x10040442d  mov     edx, [rdi+18h]
0x100404430  lea     r8, [rdi+50h]; struct StringPtr *
0x100404434  mov     [rdi+68h], r14
0x100404438  test    edx, edx
0x10040443a  jnz     short loc_100404445
0x10040443c  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100404443  jmp     short loc_100404465
0x100404445  mov     rax, [rdi]
0x100404448  lea     rcx, [rdx+1]
0x10040444c  lea     rcx, [rax+rcx*2]
0x100404450  mov     eax, [rdi+8]
0x100404453  sub     eax, edx
0x100404455  mov     qword ptr [rsp+38h+var_18], rcx
0x10040445a  dec     eax
0x10040445c  lea     rdx, [rsp+38h+var_18]; struct StringPtr *
0x100404461  mov     dword ptr [rsp+38h+var_18+8], eax
0x100404465  lea     rcx, [rbx+200h]; this
0x10040446c  call    ?PushPrefix@NamespaceSupport@@QEAAXPEAUStringPtr@@0@Z; NamespaceSupport::PushPrefix(StringPtr *,StringPtr *)
0x100404471  movups  xmm0, xmmword ptr cs:?xmlnsUri@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlnsUri
0x100404478  lea     rsi, [rbx+14A0h]
0x10040447f  movups  xmmword ptr [rdi+20h], xmm0
0x100404483  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040448a  movups  xmmword ptr [rdi+30h], xmm1
0x10040448e  mov     ecx, [rsi+18h]
0x100404491  cmp     [rsi+1Ch], ecx
0x100404494  jnz     short loc_1004044A3
0x100404496  xor     edx, edx
0x100404498  mov     rcx, rsi
0x10040449b  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x1004044a0  mov     ecx, [rsi+18h]
0x1004044a3  lea     eax, [rcx+1]
0x1004044a6  mov     [rsi+18h], eax
0x1004044a9  movups  xmm0, xmmword ptr [rdi]
0x1004044ac  mov     eax, ecx
0x1004044ae  imul    rcx, rax, 98h
0x1004044b5  mov     rax, [rsi+10h]
0x1004044b9  movups  xmmword ptr [rcx+rax], xmm0
0x1004044bd  movups  xmm1, xmmword ptr [rdi+10h]
0x1004044c1  movups  xmmword ptr [rcx+rax+10h], xmm1
0x1004044c6  movups  xmm0, xmmword ptr [rdi+20h]
0x1004044ca  movups  xmmword ptr [rcx+rax+20h], xmm0
0x1004044cf  movups  xmm1, xmmword ptr [rdi+30h]
0x1004044d3  movups  xmmword ptr [rcx+rax+30h], xmm1
0x1004044d8  movups  xmm0, xmmword ptr [rdi+40h]
0x1004044dc  movups  xmmword ptr [rcx+rax+40h], xmm0
0x1004044e1  movups  xmm1, xmmword ptr [rdi+50h]
0x1004044e5  movups  xmmword ptr [rcx+rax+50h], xmm1
0x1004044ea  movups  xmm0, xmmword ptr [rdi+60h]
0x1004044ee  movups  xmmword ptr [rcx+rax+60h], xmm0
0x1004044f3  movups  xmm1, xmmword ptr [rdi+70h]
0x1004044f7  movups  xmmword ptr [rcx+rax+70h], xmm1
0x1004044fc  movups  xmm0, xmmword ptr [rdi+80h]
0x100404503  movups  xmmword ptr [rcx+rax+80h], xmm0
0x10040450b  movsd   xmm1, qword ptr [rdi+90h]
0x100404513  movsd   qword ptr [rcx+rax+90h], xmm1
0x10040451c  dec     dword ptr [rbx+0B18h]
0x100404522  jmp     loc_100404350
0x100404527  mov     ecx, [rbx+728h]
0x10040452d  mov     eax, 7FFFFFFFh
0x100404532  test    ecx, ecx
0x100404534  cmovg   eax, ecx
0x100404537  lea     rcx, [rbx+28h]
0x10040453b  mov     [rbx+134h], eax
0x100404541  mov     rax, [rbx+0D8h]
0x100404548  call    cs:__guard_dispatch_icall_fptr
0x10040454e  movups  xmm0, xmmword ptr [rbx+110h]
0x100404555  movups  xmmword ptr [rdi+68h], xmm0
0x100404559  movups  xmm1, xmmword ptr [rbx+120h]
0x100404560  movups  xmmword ptr [rdi+78h], xmm1
0x100404564  movzx   eax, word ptr [rbx+130h]
0x10040456b  mov     [rdi+88h], ax
0x100404572  mov     eax, [rbx+70h]
0x100404575  cmp     eax, 7
0x100404578  jl      loc_100404350
0x10040457e  xchg    ax, ax
0x100404580  cmp     eax, 0Bh
0x100404583  ja      loc_100404350
0x100404589  mov     eax, [rbx+728h]
0x10040458f  mov     ecx, 7FFFFFFFh
0x100404594  test    eax, eax
0x100404596  cmovg   ecx, eax
0x100404599  mov     [rbx+134h], ecx
0x10040459f  lea     rcx, [rbx+28h]
0x1004045a3  mov     rax, [rbx+0D8h]
0x1004045aa  call    cs:__guard_dispatch_icall_fptr
0x1004045b0  mov     eax, [rbx+70h]
0x1004045b3  cmp     eax, 7
0x1004045b6  jge     short loc_100404580
0x1004045b8  jmp     loc_100404350
0x1004045bd  mov     dword ptr [rbx+6F0h], 1
0x1004045c7  cmp     [rbx+0B18h], r14d
0x1004045ce  jbe     short loc_1004045E8
0x1004045d0  mov     rcx, [rbx+68h]
0x1004045d4  lea     rdx, [rbx+708h]
0x1004045db  mov     rax, [rcx]
0x1004045de  mov     rax, [rax+48h]
0x1004045e2  call    cs:__guard_dispatch_icall_fptr
0x1004045e8  lea     rax, ?ParseEETagEndS@YReader@@AEAAXXZ; YReader::ParseEETagEndS(void)
0x1004045ef  jmp     short loc_100404623
0x1004045f1  mov     dword ptr [rbx+6F0h], 2
0x1004045fb  cmp     [rbx+0B18h], r14d
0x100404602  jbe     short loc_10040461C
0x100404604  mov     rcx, [rbx+68h]
0x100404608  lea     rdx, [rbx+708h]
0x10040460f  mov     rax, [rcx]
0x100404612  mov     rax, [rax+48h]
0x100404616  call    cs:__guard_dispatch_icall_fptr
0x10040461c  lea     rax, ?ParseTagEndS@YReader@@AEAAXXZ; YReader::ParseTagEndS(void)
0x100404623  mov     rdi, [rsp+38h+arg_8]
0x100404628  mov     rsi, [rsp+38h+arg_0]
0x10040462d  mov     rbp, [rsp+38h+arg_18]
0x100404632  mov     qword ptr [rsp+38h+var_18], rax
0x100404637  mov     dword ptr [rsp+38h+var_18+8], r14d
0x10040463c  movups  xmm0, [rsp+38h+var_18]
0x100404641  movups  xmmword ptr [rbx+5E0h], xmm0
0x100404648  mov     rbx, [rsp+38h+arg_10]
0x10040464d  add     rsp, 30h
0x100404651  pop     r14
0x100404653  retn
0x100404654  mov     ecx, 0C00CEE01h; int
0x100404659  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
