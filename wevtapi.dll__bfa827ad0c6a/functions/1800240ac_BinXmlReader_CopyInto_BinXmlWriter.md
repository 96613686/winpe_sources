# BinXmlReader::CopyInto(BinXmlWriter &)

- ea: `0x1800240ac`
- end: `0x180024391`
- name: `?CopyInto@BinXmlReader@@QEAAXAEAVBinXmlWriter@@@Z`
- size: `741`
- prototype: `void __fastcall(BinXmlReader *this, WriteBuffer **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180030454`
- `0x1800355c8`

## callees

- `0x180003780`
- `0x180008b20`
- `0x1800240ac`
- `0x180024398`
- `0x1800243e4`
- `0x180024428`
- `0x180024a50`
- `0x18002fdb4`

## pseudocode

```c
void __fastcall BinXmlReader::CopyInto(BinXmlReader *this, WriteBuffer **a2)
{
  WriteBuffer *v2; // rdi
  int v4; // eax
  unsigned int v6; // r14d
  WriteBuffer *v7; // rax
  __int64 **v8; // rax
  __int64 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned int v13; // r15d
  int v14; // r12d
  __int64 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  unsigned int v24; // ebx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 *v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  _BYTE v33[4]; // [rsp+20h] [rbp-50h] BYREF
  int v34; // [rsp+24h] [rbp-4Ch] BYREF
  __int64 v35; // [rsp+28h] [rbp-48h] BYREF
  int v36; // [rsp+30h] [rbp-40h]
  int v37; // [rsp+34h] [rbp-3Ch]
  __int128 v38; // [rsp+38h] [rbp-38h] BYREF
  __int128 v39; // [rsp+48h] [rbp-28h]
  __int64 v40; // [rsp+58h] [rbp-18h]
  WriteBuffer *v41; // [rsp+60h] [rbp-10h]

  v2 = *a2;
  v4 = *((_DWORD *)this + 46);
  v6 = *((_DWORD *)*a2 + 4);
  if ( v4 )
  {
    WriteBuffer::SetCurrentIndex(v2, v4 + v6);
    WriteBuffer::SetCurrentIndex(v2, v6);
  }
  if ( *((_BYTE *)this + 189) )
  {
    v40 = *((_QWORD *)this + 11);
    v7 = a2[1];
    v38 = 0;
    v41 = v7;
    v8 = (__int64 **)*((_QWORD *)this + 3);
    v39 = 0;
    v33[0] = 0;
    v9 = *v8;
    v10 = **v8;
    v11 = (*v8)[1];
    *(_QWORD *)&v39 = (*v8)[2];
    v12 = v9[3];
    *(_QWORD *)&v38 = v10;
    *((_QWORD *)&v39 + 1) = v12;
    *((_QWORD *)&v38 + 1) = v11;
    BinXmlWriter::CopyTemplate((BinXmlWriter *)a2, (const struct BinXmlTemplate *)&v38);
    WriteBuffer::Write(
      v2,
      *(const void **)(*((_QWORD *)this + 3) + 24LL),
      *(_DWORD *)(*((_QWORD *)this + 3) + 32LL) - 4);
    v13 = *((_DWORD *)v2 + 4);
    WriteBuffer::SetCurrentIndex(v2, v13 + 4);
    WriteBuffer::Write(v2, *(const void **)(*((_QWORD *)this + 3) + 8LL), *(_DWORD *)(*((_QWORD *)this + 3) + 16LL));
    v14 = *((_DWORD *)v2 + 4);
    v15 = *(__int64 **)(*((_QWORD *)this + 3) + 40LL);
    v16 = *v15;
    v17 = v15[1];
    *(_QWORD *)&v39 = v15[2];
    v18 = v15[3];
    *(_QWORD *)&v38 = v16;
    *((_QWORD *)&v39 + 1) = v18;
    *((_QWORD *)&v38 + 1) = v17;
    BinXmlWriter::CopyTemplate((BinXmlWriter *)a2, (const struct BinXmlTemplate *)&v38);
    WriteBuffer::Write(v2, *(const void **)(*((_QWORD *)this + 3) + 64LL), *(_DWORD *)(*((_QWORD *)this + 3) + 72LL));
    v19 = *((_QWORD *)this + 3);
    if ( *(_QWORD *)(v19 + 56) )
      WriteBuffer::Write(v2, *(const void **)(v19 + 48), *(_DWORD *)(v19 + 56));
    if ( *((_DWORD *)this + 8) == 3 )
    {
      v20 = *(__int64 **)(*((_QWORD *)this + 3) + 80LL);
      v21 = *v20;
      v22 = v20[1];
      v39 = *((_OWORD *)v20 + 1);
      *(_QWORD *)&v38 = v21;
      *((_QWORD *)&v38 + 1) = v22;
      BinXmlWriter::CopyTemplate((BinXmlWriter *)a2, (const struct BinXmlTemplate *)&v38);
      WriteBuffer::Write(
        v2,
        *(const void **)(*((_QWORD *)this + 3) + 104LL),
        *(_DWORD *)(*((_QWORD *)this + 3) + 112LL));
      v23 = *((_QWORD *)this + 3);
      if ( *(_QWORD *)(v23 + 96) )
        WriteBuffer::Write(v2, *(const void **)(v23 + 88), *(_DWORD *)(v23 + 96));
    }
    WriteBuffer::Write(v2, v33, 1u);
    v24 = *((_DWORD *)v2 + 4);
    v34 = (v24 - v14) | 0x210000;
    WriteBuffer::SetCurrentIndex(v2, v13);
    WriteBuffer::Write(v2, &v34, 4u);
    WriteBuffer::SetCurrentIndex(v2, v24);
    WriteBuffer::Write(v2, v33, 1u);
  }
  else
  {
    v25 = *((unsigned int *)this + 9);
    v26 = *((_QWORD *)this + 3);
    v27 = 5 * v25;
    v28 = *(__int64 **)(v26 + 40 * v25);
    if ( v28 && *(_QWORD *)(v26 + 40 * v25 + 16) )
    {
      v29 = *(_QWORD *)(v26 + 40 * v25 + 24);
      v38 = 0;
      v35 = v29;
      LODWORD(v29) = *(_DWORD *)(v26 + 8 * v27 + 32);
      v39 = 0;
      v37 = v29;
      v40 = *((_QWORD *)this + 11);
      v41 = a2[1];
      v30 = *v28;
      v31 = v28[1];
      *(_QWORD *)&v39 = v28[2];
      v32 = v28[3];
      *(_QWORD *)&v38 = v30;
      *((_QWORD *)&v38 + 1) = v31;
      v36 = 0;
      *((_QWORD *)&v39 + 1) = v32;
      BinXmlReader::CopyTemplateInstanceInto(
        this,
        (const struct BinXmlTemplate *)&v38,
        (struct UserBuffer *)&v35,
        (struct BinXmlWriter *)a2);
      BinXmlWriter::EndOfFile((BinXmlWriter *)a2);
    }
    else
    {
      BinXmlReader::InternalCopyInto(this, (struct BinXmlWriter *)a2);
    }
  }
  *((_DWORD *)this + 46) = *((_DWORD *)v2 + 4) - v6;
}

```

## disassembly

```asm
0x1800240ac  mov     [rsp-28h+arg_10], rbx
0x1800240b1  mov     [rsp-28h+arg_18], rsi
0x1800240b6  push    rbp
0x1800240b7  push    rdi
0x1800240b8  push    r12
0x1800240ba  push    r14
0x1800240bc  push    r15
0x1800240be  mov     rbp, rsp
0x1800240c1  sub     rsp, 70h
0x1800240c5  mov     rax, cs:__security_cookie
0x1800240cc  xor     rax, rsp
0x1800240cf  mov     [rbp+var_8], rax
0x1800240d3  mov     rdi, [rdx]
0x1800240d6  mov     rbx, rdx
0x1800240d9  mov     eax, [rcx+0B8h]
0x1800240df  mov     rsi, rcx
0x1800240e2  mov     r14d, [rdi+10h]
0x1800240e6  test    eax, eax
0x1800240e8  jz      short loc_180024101
0x1800240ea  lea     edx, [rax+r14]; unsigned int
0x1800240ee  mov     rcx, rdi; this
0x1800240f1  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x1800240f6  mov     edx, r14d; unsigned int
0x1800240f9  mov     rcx, rdi; this
0x1800240fc  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180024101  cmp     byte ptr [rsi+0BDh], 0
0x180024108  jz      loc_1800242CA
0x18002410e  mov     rax, [rsi+58h]
0x180024112  xorps   xmm0, xmm0
0x180024115  mov     [rbp+var_18], rax
0x180024119  mov     rax, [rbx+8]
0x18002411d  movdqu  [rbp+var_38], xmm0
0x180024122  mov     [rbp+var_10], rax
0x180024126  mov     rax, [rsi+18h]
0x18002412a  movups  [rbp+var_28], xmm0
0x18002412e  mov     [rbp+var_50], 0
0x180024132  mov     rcx, [rax]
0x180024135  mov     rax, [rcx+10h]
0x180024139  mov     rdx, [rcx]
0x18002413c  mov     r8, [rcx+8]
0x180024140  mov     qword ptr [rbp+var_28], rax
0x180024144  mov     rax, [rcx+18h]
0x180024148  mov     rcx, rbx; this
0x18002414b  mov     qword ptr [rbp+var_38], rdx
0x18002414f  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x180024153  mov     qword ptr [rbp+var_28+8], rax
0x180024157  mov     qword ptr [rbp+var_38+8], r8
0x18002415b  call    ?CopyTemplate@BinXmlWriter@@QEAAXAEBVBinXmlTemplate@@@Z; BinXmlWriter::CopyTemplate(BinXmlTemplate const &)
0x180024160  mov     rdx, [rsi+18h]
0x180024164  mov     rcx, rdi; this
0x180024167  mov     r8d, [rdx+20h]
0x18002416b  mov     rdx, [rdx+18h]; void *
0x18002416f  sub     r8d, 4; unsigned int
0x180024173  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180024178  mov     r15d, [rdi+10h]
0x18002417c  mov     rcx, rdi; this
0x18002417f  lea     edx, [r15+4]; unsigned int
0x180024183  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180024188  mov     rdx, [rsi+18h]
0x18002418c  mov     rcx, rdi; this
0x18002418f  mov     r8d, [rdx+10h]; unsigned int
0x180024193  mov     rdx, [rdx+8]; void *
0x180024197  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002419c  mov     rax, [rsi+18h]
0x1800241a0  mov     r12d, [rdi+10h]
0x1800241a4  mov     rcx, [rax+28h]
0x1800241a8  mov     rax, [rcx+10h]
0x1800241ac  mov     rdx, [rcx]
0x1800241af  mov     r8, [rcx+8]
0x1800241b3  mov     qword ptr [rbp+var_28], rax
0x1800241b7  mov     rax, [rcx+18h]
0x1800241bb  mov     rcx, rbx; this
0x1800241be  mov     qword ptr [rbp+var_38], rdx
0x1800241c2  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x1800241c6  mov     qword ptr [rbp+var_28+8], rax
0x1800241ca  mov     qword ptr [rbp+var_38+8], r8
0x1800241ce  call    ?CopyTemplate@BinXmlWriter@@QEAAXAEBVBinXmlTemplate@@@Z; BinXmlWriter::CopyTemplate(BinXmlTemplate const &)
0x1800241d3  mov     rdx, [rsi+18h]
0x1800241d7  mov     rcx, rdi; this
0x1800241da  mov     r8d, [rdx+48h]; unsigned int
0x1800241de  mov     rdx, [rdx+40h]; void *
0x1800241e2  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800241e7  mov     rdx, [rsi+18h]
0x1800241eb  cmp     qword ptr [rdx+38h], 0
0x1800241f0  jz      short loc_180024202
0x1800241f2  mov     r8d, [rdx+38h]; unsigned int
0x1800241f6  mov     rcx, rdi; this
0x1800241f9  mov     rdx, [rdx+30h]; void *
0x1800241fd  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180024202  cmp     dword ptr [rsi+20h], 3
0x180024206  jnz     short loc_18002426A
0x180024208  mov     rax, [rsi+18h]
0x18002420c  mov     rcx, rbx; this
0x18002420f  mov     rdx, [rax+50h]
0x180024213  mov     rax, [rdx+10h]
0x180024217  mov     r8, [rdx]
0x18002421a  mov     r9, [rdx+8]
0x18002421e  mov     qword ptr [rbp+var_28], rax
0x180024222  mov     rax, [rdx+18h]
0x180024226  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x18002422a  mov     qword ptr [rbp+var_28+8], rax
0x18002422e  mov     qword ptr [rbp+var_38], r8
0x180024232  mov     qword ptr [rbp+var_38+8], r9
0x180024236  call    ?CopyTemplate@BinXmlWriter@@QEAAXAEBVBinXmlTemplate@@@Z; BinXmlWriter::CopyTemplate(BinXmlTemplate const &)
0x18002423b  mov     rdx, [rsi+18h]
0x18002423f  mov     rcx, rdi; this
0x180024242  mov     r8d, [rdx+70h]; unsigned int
0x180024246  mov     rdx, [rdx+68h]; void *
0x18002424a  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002424f  mov     rdx, [rsi+18h]
0x180024253  cmp     qword ptr [rdx+60h], 0
0x180024258  jz      short loc_18002426A
0x18002425a  mov     r8d, [rdx+60h]; unsigned int
0x18002425e  mov     rcx, rdi; this
0x180024261  mov     rdx, [rdx+58h]; void *
0x180024265  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002426a  mov     r8d, 1; unsigned int
0x180024270  lea     rdx, [rbp+var_50]; void *
0x180024274  mov     rcx, rdi; this
0x180024277  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002427c  mov     ebx, [rdi+10h]
0x18002427f  mov     edx, r15d; unsigned int
0x180024282  mov     eax, ebx
0x180024284  mov     rcx, rdi; this
0x180024287  sub     eax, r12d
0x18002428a  or      eax, 210000h
0x18002428f  mov     [rbp+var_4C], eax
0x180024292  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180024297  mov     r8d, 4; unsigned int
0x18002429d  lea     rdx, [rbp+var_4C]; void *
0x1800242a1  mov     rcx, rdi; this
0x1800242a4  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800242a9  mov     edx, ebx; unsigned int
0x1800242ab  mov     rcx, rdi; this
0x1800242ae  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x1800242b3  mov     r8d, 1; unsigned int
0x1800242b9  lea     rdx, [rbp+var_50]; void *
0x1800242bd  mov     rcx, rdi; this
0x1800242c0  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800242c5  jmp     loc_180024360
0x1800242ca  mov     eax, [rsi+24h]
0x1800242cd  mov     rdx, [rsi+18h]
0x1800242d1  lea     rcx, [rax+rax*4]
0x1800242d5  mov     r8, [rdx+rcx*8]
0x1800242d9  test    r8, r8
0x1800242dc  jz      short loc_180024355
0x1800242de  cmp     qword ptr [rdx+rcx*8+10h], 0
0x1800242e4  jz      short loc_180024355
0x1800242e6  mov     rax, [rdx+rcx*8+18h]
0x1800242eb  xorps   xmm0, xmm0
0x1800242ee  movdqu  [rbp+var_38], xmm0
0x1800242f3  mov     [rbp+var_48], rax
0x1800242f7  mov     r9, rbx; struct BinXmlWriter *
0x1800242fa  mov     eax, [rdx+rcx*8+20h]
0x1800242fe  movups  [rbp+var_28], xmm0
0x180024302  mov     [rbp+var_3C], eax
0x180024305  mov     rax, [rsi+58h]
0x180024309  mov     [rbp+var_18], rax
0x18002430d  mov     rax, [rbx+8]
0x180024311  mov     [rbp+var_10], rax
0x180024315  mov     rax, [r8+10h]
0x180024319  mov     rcx, [r8]
0x18002431c  mov     rdx, [r8+8]
0x180024320  mov     qword ptr [rbp+var_28], rax
0x180024324  mov     rax, [r8+18h]
0x180024328  lea     r8, [rbp+var_48]; struct UserBuffer *
0x18002432c  mov     qword ptr [rbp+var_38], rcx
0x180024330  mov     rcx, rsi; this
0x180024333  mov     qword ptr [rbp+var_38+8], rdx
0x180024337  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x18002433b  mov     [rbp+var_40], 0
0x180024342  mov     qword ptr [rbp+var_28+8], rax
0x180024346  call    ?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEBVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z; BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate const &,UserBuffer &,BinXmlWriter &)
0x18002434b  mov     rcx, rbx; this
0x18002434e  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x180024353  jmp     short loc_180024360
0x180024355  mov     rdx, rbx; struct BinXmlWriter *
0x180024358  mov     rcx, rsi; this
0x18002435b  call    ?InternalCopyInto@BinXmlReader@@AEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::InternalCopyInto(BinXmlWriter &)
0x180024360  mov     eax, [rdi+10h]
0x180024363  sub     eax, r14d
0x180024366  mov     [rsi+0B8h], eax
0x18002436c  mov     rcx, [rbp+var_8]
0x180024370  xor     rcx, rsp; StackCookie
0x180024373  call    __security_check_cookie
0x180024378  lea     r11, [rsp+70h+var_s0]
0x18002437d  mov     rbx, [r11+40h]
0x180024381  mov     rsi, [r11+48h]
0x180024385  mov     rsp, r11
0x180024388  pop     r15
0x18002438a  pop     r14
0x18002438c  pop     r12
0x18002438e  pop     rdi
0x18002438f  pop     rbp
0x180024390  retn
```
