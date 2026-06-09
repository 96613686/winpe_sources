# BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate const &,UserBuffer &,BinXmlWriter &)

- ea: `0x180024428`
- end: `0x180024659`
- name: `?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEBVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z`
- size: `561`
- prototype: `void __fastcall(BinXmlReader *this, const struct BinXmlTemplate *, struct UserBuffer *, struct BinXmlWriter *)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800240ac`
- `0x180024428`
- `0x18002fdb4`

## callees

- `0x180004e70`
- `0x1800058f4`
- `0x18000a4b4`
- `0x1800130b0`
- `0x180013650`
- `0x1800243e4`
- `0x180024428`
- `0x180024a50`
- `0x18002e4dc`
- `0x18002f2ec`
- `0x18002f384`
- `0x18002f4b0`
- `0x18002fdb4`

## pseudocode

```c
void __fastcall BinXmlReader::CopyTemplateInstanceInto(
        BinXmlReader *this,
        const struct BinXmlTemplate *a2,
        struct UserBuffer *a3,
        struct BinXmlWriter *a4)
{
  unsigned int *v8; // r14
  unsigned int v9; // r12d
  BinXmlTmplInstWriter *started; // rdi
  int v11; // ebx
  unsigned int v12; // ecx
  BinXmlReader *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // [rsp+20h] [rbp-B9h] BYREF
  __int64 v20; // [rsp+28h] [rbp-B1h] BYREF
  int v21; // [rsp+30h] [rbp-A9h]
  unsigned int v22; // [rsp+34h] [rbp-A5h]
  __int64 v23; // [rsp+38h] [rbp-A1h] BYREF
  int v24; // [rsp+40h] [rbp-99h]
  int v25; // [rsp+44h] [rbp-95h]
  _QWORD v26[6]; // [rsp+50h] [rbp-89h] BYREF
  __m128i si128; // [rsp+80h] [rbp-59h] BYREF
  __int64 v28; // [rsp+90h] [rbp-49h]
  __int128 v29; // [rsp+98h] [rbp-41h]
  __int64 v30; // [rsp+A8h] [rbp-31h]
  int v31; // [rsp+B0h] [rbp-29h]
  int v32; // [rsp+B4h] [rbp-25h]
  char v33; // [rsp+B8h] [rbp-21h]
  char v34; // [rsp+B9h] [rbp-20h]
  char v35; // [rsp+BAh] [rbp-1Fh]
  __int128 v36; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v37; // [rsp+D0h] [rbp-9h]
  __int64 v38; // [rsp+E0h] [rbp+7h]
  __int64 v39; // [rsp+E8h] [rbp+Fh]

  v19 = 0;
  UserBuffer::Read4(a3, &v19);
  v8 = (unsigned int *)(*(_QWORD *)a3 + *((unsigned int *)a3 + 2));
  v9 = v19;
  UserBuffer::Advance(a3, 4 * v19);
  v26[0] = *(_QWORD *)a4;
  v26[1] = *((_QWORD *)a4 + 1);
  v26[2] = *((_QWORD *)a4 + 2);
  v26[3] = v26[0];
  v26[4] = 0;
  v26[5] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v28 = -1;
  v29 = 0;
  v30 = *((_QWORD *)a4 + 11);
  v31 = *((_DWORD *)a4 + 24);
  v32 = 0;
  v33 = 0;
  v34 = *((_BYTE *)a4 + 105);
  v35 = 0;
  started = BinXmlWriter::StartTemplateInstance((BinXmlWriter *)v26, v9, a2);
  v11 = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      v12 = *v8++;
      v20 = 0;
      v21 = -1;
      v22 = HIWORD(v12);
      if ( HIWORD(v12) - 32 <= 1u )
        break;
      BinXmlReader::NextValueData(this, this, (struct BinXmlVariant *)&v20, (unsigned __int16)v12);
      BinXmlTmplInstWriter::Value(started, (struct BinXmlVariant *)&v20);
LABEL_11:
      if ( ++v11 >= v9 )
        goto LABEL_12;
    }
    BinXmlTmplInstWriter::StartOpenContent(started);
    v13 = this;
    if ( v22 == 32 )
    {
      BinXmlReader::NextReaderData(this);
      v14 = *((unsigned int *)this + 9);
      v15 = *((_QWORD *)this + 3);
      v16 = *(__int64 **)(v15 + 40 * v14);
      if ( v16 )
      {
        v23 = *(_QWORD *)(v15 + 40 * v14 + 24);
        v24 = 0;
        v25 = *(_DWORD *)(v15 + 40 * v14 + 32);
        v36 = 0;
        v37 = 0;
        v38 = *((_QWORD *)this + 11);
        v39 = *((_QWORD *)a4 + 1);
        v17 = *v16;
        v18 = v16[1];
        v37 = *((_OWORD *)v16 + 1);
        *(_QWORD *)&v36 = v17;
        *((_QWORD *)&v36 + 1) = v18;
        BinXmlReader::CopyTemplateInstanceInto(this, (const struct BinXmlTemplate *)&v36, (struct UserBuffer *)&v23, a4);
        BinXmlWriter::EndOfFile(a4);
LABEL_10:
        BinXmlTmplInstWriter::AdjustValueSpec(started, 0x21u);
        goto LABEL_11;
      }
      v13 = this;
    }
    else
    {
      *((_QWORD *)this + 2) = this;
    }
    BinXmlReader::InternalCopyInto(v13, (struct BinXmlWriter *)v26);
    goto LABEL_10;
  }
LABEL_12:
  utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(&si128);
}

```

## disassembly

```asm
0x180024428  push    rbp
0x18002442a  push    rbx
0x18002442b  push    rsi
0x18002442c  push    rdi
0x18002442d  push    r12
0x18002442f  push    r14
0x180024431  push    r15
0x180024433  lea     rbp, [rsp-27h]
0x180024438  sub     rsp, 100h
0x18002443f  mov     rax, cs:__security_cookie
0x180024446  xor     rax, rsp
0x180024449  mov     [rbp+57h+var_40], rax
0x18002444d  mov     r15, r9
0x180024450  mov     rbx, r8
0x180024453  mov     rdi, rdx
0x180024456  mov     rsi, rcx
0x180024459  mov     [rsp+130h+var_110], 0
0x180024461  lea     rdx, [rsp+130h+var_110]; void *
0x180024466  mov     rcx, r8; this
0x180024469  call    ?Read4@UserBuffer@@QEAAXPEAX@Z; UserBuffer::Read4(void *)
0x18002446e  mov     r14d, [rbx+8]
0x180024472  add     r14, [rbx]
0x180024475  mov     r12d, [rsp+130h+var_110]
0x18002447a  lea     edx, ds:0[r12*4]; unsigned int
0x180024482  mov     rcx, rbx; this
0x180024485  call    ?Advance@UserBuffer@@QEAAXK@Z; UserBuffer::Advance(ulong)
0x18002448a  mov     rcx, [r15]
0x18002448d  mov     [rsp+130h+var_E0], rcx
0x180024492  mov     rax, [r15+8]
0x180024496  mov     [rsp+130h+var_D8], rax
0x18002449b  mov     rax, [r15+10h]
0x18002449f  mov     [rbp+57h+var_D0], rax
0x1800244a3  mov     [rbp+57h+var_C8], rcx
0x1800244a7  mov     [rbp+57h+var_C0], 0
0x1800244af  mov     [rbp+57h+var_B8], 0
0x1800244b7  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800244bf  movdqa  [rbp+57h+var_B0], xmm0
0x1800244c4  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x1800244cc  xorps   xmm0, xmm0
0x1800244cf  movups  [rbp+57h+var_98], xmm0
0x1800244d3  mov     rax, [r15+58h]
0x1800244d7  mov     [rbp+57h+var_88], rax
0x1800244db  mov     eax, [r15+60h]
0x1800244df  mov     [rbp+57h+var_80], eax
0x1800244e2  mov     [rbp+57h+var_7C], 0
0x1800244e9  mov     [rbp+57h+var_78], 0
0x1800244ed  mov     al, [r15+69h]
0x1800244f1  mov     [rbp+57h+var_77], al
0x1800244f4  mov     [rbp+57h+var_76], 0
0x1800244f8  mov     r8, rdi; struct BinXmlTemplate *
0x1800244fb  mov     edx, r12d; unsigned int
0x1800244fe  lea     rcx, [rsp+130h+var_E0]; this
0x180024503  call    ?StartTemplateInstance@BinXmlWriter@@QEAAPEAVBinXmlTmplInstWriter@@KAEBVBinXmlTemplate@@@Z; BinXmlWriter::StartTemplateInstance(ulong,BinXmlTemplate const &)
0x180024508  mov     rdi, rax
0x18002450b  xor     ebx, ebx
0x18002450d  test    r12d, r12d
0x180024510  jz      loc_180024632
0x180024516  mov     ecx, [r14]
0x180024519  lea     r14, [r14+4]
0x18002451d  mov     [rsp+130h+var_108], 0
0x180024526  mov     [rsp+130h+var_100], 0FFFFFFFFh
0x18002452e  mov     eax, ecx
0x180024530  shr     eax, 10h
0x180024533  mov     [rsp+130h+var_FC], eax
0x180024537  add     eax, 0FFFFFFE0h
0x18002453a  cmp     eax, 1
0x18002453d  jbe     short loc_180024565
0x18002453f  movzx   r9d, cx; unsigned int
0x180024543  lea     r8, [rsp+130h+var_108]; struct BinXmlVariant *
0x180024548  mov     rdx, rsi; struct UserBuffer *
0x18002454b  mov     rcx, rsi; this
0x18002454e  call    ?NextValueData@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@K@Z; BinXmlReader::NextValueData(UserBuffer &,BinXmlVariant &,ulong)
0x180024553  lea     rdx, [rsp+130h+var_108]; struct BinXmlVariant *
0x180024558  mov     rcx, rdi; this
0x18002455b  call    ?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z; BinXmlTmplInstWriter::Value(BinXmlVariant &)
0x180024560  jmp     loc_180024627
0x180024565  mov     rcx, rdi; this
0x180024568  call    ?StartOpenContent@BinXmlTmplInstWriter@@QEAAXXZ; BinXmlTmplInstWriter::StartOpenContent(void)
0x18002456d  mov     rcx, rsi; this
0x180024570  cmp     [rsp+130h+var_FC], 20h ; ' '
0x180024575  jnz     loc_18002460C
0x18002457b  call    ?NextReaderData@BinXmlReader@@AEAAXXZ; BinXmlReader::NextReaderData(void)
0x180024580  mov     eax, [rsi+24h]
0x180024583  lea     rcx, [rax+rax*4]
0x180024587  mov     rdx, [rsi+18h]
0x18002458b  mov     r8, [rdx+rcx*8]
0x18002458f  test    r8, r8
0x180024592  jz      short loc_180024607
0x180024594  mov     rax, [rdx+rcx*8+18h]
0x180024599  mov     [rsp+130h+var_F8], rax
0x18002459e  mov     [rsp+130h+var_F0], 0
0x1800245a6  mov     eax, [rdx+rcx*8+20h]
0x1800245aa  mov     [rsp+130h+var_EC], eax
0x1800245ae  xorps   xmm0, xmm0
0x1800245b1  movdqu  [rbp+57h+var_70], xmm0
0x1800245b6  movups  [rbp+57h+var_60], xmm0
0x1800245ba  mov     rax, [rsi+58h]
0x1800245be  mov     [rbp+57h+var_50], rax
0x1800245c2  mov     rax, [r15+8]
0x1800245c6  mov     [rbp+57h+var_48], rax
0x1800245ca  mov     rcx, [r8]
0x1800245cd  mov     rdx, [r8+8]
0x1800245d1  mov     rax, [r8+10h]
0x1800245d5  mov     qword ptr [rbp+57h+var_60], rax
0x1800245d9  mov     rax, [r8+18h]
0x1800245dd  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800245e1  mov     qword ptr [rbp+57h+var_70], rcx
0x1800245e5  mov     qword ptr [rbp+57h+var_70+8], rdx
0x1800245e9  mov     r9, r15; struct BinXmlWriter *
0x1800245ec  lea     r8, [rsp+130h+var_F8]; struct UserBuffer *
0x1800245f1  lea     rdx, [rbp+57h+var_70]; struct BinXmlTemplate *
0x1800245f5  mov     rcx, rsi; this
0x1800245f8  call    ?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEBVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z; BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate const &,UserBuffer &,BinXmlWriter &)
0x1800245fd  mov     rcx, r15; this
0x180024600  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x180024605  jmp     short loc_18002461A
0x180024607  mov     rcx, rsi
0x18002460a  jmp     short loc_180024610
0x18002460c  mov     [rsi+10h], rsi
0x180024610  lea     rdx, [rsp+130h+var_E0]; struct BinXmlWriter *
0x180024615  call    ?InternalCopyInto@BinXmlReader@@AEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::InternalCopyInto(BinXmlWriter &)
0x18002461a  mov     edx, 21h ; '!'; unsigned int
0x18002461f  mov     rcx, rdi; this
0x180024622  call    ?AdjustValueSpec@BinXmlTmplInstWriter@@AEAAXK@Z; BinXmlTmplInstWriter::AdjustValueSpec(ulong)
0x180024627  inc     ebx
0x180024629  cmp     ebx, r12d
0x18002462c  jb      loc_180024516
0x180024632  lea     rcx, [rbp+57h+var_B0]
0x180024636  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002463b  mov     rcx, [rbp+57h+var_40]
0x18002463f  xor     rcx, rsp; StackCookie
0x180024642  call    __security_check_cookie
0x180024647  add     rsp, 100h
0x18002464e  pop     r15
0x180024650  pop     r14
0x180024652  pop     r12
0x180024654  pop     rdi
0x180024655  pop     rsi
0x180024656  pop     rbx
0x180024657  pop     rbp
0x180024658  retn
```
