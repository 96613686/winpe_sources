# p9fs::Handler::WriteWOpenReply(p9fs::WOpenStatus,ushort,p9fs::Fid &,unsigned __int64,p9fs::Handler::MessageResponse &)

- ea: `0x18001bd28`
- end: `0x18001c096`
- name: `?WriteWOpenReply@Handler@p9fs@@AEAAJW4WOpenStatus@2@GAEAVFid@2@_KAEAVMessageResponse@12@@Z`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180014b78`

## callees

- `0x180004120`
- `0x180010020`
- `0x1800167e0`
- `0x180017f1c`
- `0x180018ffc`
- `0x18001bd28`
- `0x18001c93c`
- `0x180034010`

## string_xrefs

- `0x18001bd90`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::WriteWOpenReply(
        __int64 a1,
        char a2,
        __int16 a3,
        __int64 *a4,
        __int64 a5,
        p9fs::SpanWriter *a6)
{
  unsigned int v9; // ebx
  __int64 result; // rax
  char v11; // di
  gsl::details *v12; // rcx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  const struct p9fs::StatResult *v16; // r8
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD v29[2]; // [rsp+30h] [rbp-99h] BYREF
  char *v30; // [rsp+40h] [rbp-89h] BYREF
  int v31; // [rsp+48h] [rbp-81h]
  char v32; // [rsp+4Ch] [rbp-7Dh]
  __int16 v33; // [rsp+4Dh] [rbp-7Ch]
  char v34; // [rsp+4Fh] [rbp-7Ah]
  char v35[8]; // [rsp+50h] [rbp-79h] BYREF
  char *v36[14]; // [rsp+58h] [rbp-71h] BYREF
  int v37; // [rsp+C8h] [rbp-1h]
  char v38; // [rsp+CCh] [rbp+3h]
  __int16 v39; // [rsp+CDh] [rbp+4h]
  char v40; // [rsp+CFh] [rbp+6h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  (*(void (__fastcall **)(__int64 *, char *, __int64))(*a4 + 16))(a4, v35, a5);
  if ( !v35[0] )
  {
    v9 = (unsigned int)v36[0];
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x43A,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
      (const char *)LODWORD(v36[0]),
      (int)"%hs",
      "stat");
    return v9;
  }
  v31 = v37;
  v33 = v39;
  v34 = v40;
  v32 = v38;
  v11 = v38 & 2;
  v30 = v36[13];
  p9fs::Handler::MessageResponse::EnsureSize((__int64)a6, 133);
  v13 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 <= v13 )
    goto LABEL_34;
  v12 = (gsl::details *)*((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v13 + 1;
  *((_BYTE *)v12 + v13) = a2;
  v14 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < v14 || *(_QWORD *)a6 - v14 < 2 )
    goto LABEL_34;
  v15 = *((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v14 + 2;
  *(_WORD *)(v14 + v15) = a3;
  p9fs::SpanWriter::Qid(a6, (const struct p9fs::Qid *)&v30);
  v17 = *((_QWORD *)a6 + 2);
  v12 = *(gsl::details **)a6;
  if ( !v11 )
  {
    if ( (unsigned __int64)v12 >= v17 )
    {
      v12 = (gsl::details *)((char *)v12 - v17);
      if ( (unsigned __int64)v12 >= 2 )
        goto LABEL_22;
    }
LABEL_34:
    gsl::details::terminate(v12);
  }
  if ( (unsigned __int64)v12 < v17 )
    goto LABEL_35;
  v12 = (gsl::details *)((char *)v12 - v17);
  if ( (unsigned __int64)v12 - 2 > 0xFFFFFFFFFFFFFFFCuLL )
    goto LABEL_35;
  v12 = (gsl::details *)((char *)v12 - 2);
  if ( v12 == (gsl::details *)-1LL )
    goto LABEL_35;
  v18 = v17 + *((_QWORD *)a6 + 1) + 2LL;
  if ( !v18 )
  {
    if ( v12 )
      goto LABEL_35;
  }
  v19 = *a4;
  v29[0] = v12;
  v29[1] = v18;
  (*(void (__fastcall **)(__int64 *, char **, _QWORD *))(v19 + 136))(a4, &v30, v29);
  v17 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < v17 )
LABEL_35:
    gsl::details::terminate(v12);
  v20 = *(_QWORD *)a6 - v17;
  if ( !(_BYTE)v30 )
  {
    if ( v20 < 2 )
      goto LABEL_35;
LABEL_22:
    v12 = (gsl::details *)*((_QWORD *)a6 + 1);
    *((_QWORD *)a6 + 2) = v17 + 2;
    *(_WORD *)((char *)v12 + v17) = 0;
    goto LABEL_23;
  }
  if ( v20 < 2 )
    goto LABEL_35;
  v21 = *((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v17 + 2;
  *(_WORD *)(v17 + v21) = WORD2(v30);
  v12 = (gsl::details *)*((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < (unsigned __int64)v12 || *(_QWORD *)a6 - (_QWORD)v12 < (unsigned __int64)HIDWORD(v30) )
    goto LABEL_35;
  *((_QWORD *)a6 + 2) = (char *)v12 + HIDWORD(v30);
LABEL_23:
  v22 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < v22 )
    goto LABEL_34;
  if ( *(_QWORD *)a6 - v22 < 4 )
    goto LABEL_34;
  v23 = *((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v22 + 4;
  *(_DWORD *)(v22 + v23) = 0;
  p9fs::util::SpanWriteStatResult(a6, (struct p9fs::SpanWriter *)v36, v16);
  v24 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < v24 )
    goto LABEL_34;
  if ( *(_QWORD *)a6 - v24 < 8 )
    goto LABEL_34;
  v12 = (gsl::details *)*((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v24 + 8;
  *(_QWORD *)((char *)v12 + v24) = 0;
  v25 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < v25 )
    goto LABEL_34;
  if ( *(_QWORD *)a6 - v25 < 8 )
    goto LABEL_34;
  v12 = (gsl::details *)*((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v25 + 8;
  *(_QWORD *)((char *)v12 + v25) = 0;
  v26 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < v26 )
    goto LABEL_34;
  if ( *(_QWORD *)a6 - v26 < 8 )
    goto LABEL_34;
  v12 = (gsl::details *)*((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v26 + 8;
  *(_QWORD *)((char *)v12 + v26) = 0;
  v27 = *((_QWORD *)a6 + 2);
  if ( *(_QWORD *)a6 < v27 || *(_QWORD *)a6 - v27 < 8 )
    goto LABEL_34;
  v28 = *((_QWORD *)a6 + 1);
  *((_QWORD *)a6 + 2) = v27 + 8;
  result = 0;
  *(_QWORD *)(v27 + v28) = 0;
  return result;
}

```

## disassembly

```asm
0x18001bd28  mov     [rsp-8+arg_0], rbx
0x18001bd2d  mov     [rsp-8+arg_8], rsi
0x18001bd32  push    rbp
0x18001bd33  push    rdi
0x18001bd34  push    r12
0x18001bd36  push    r14
0x18001bd38  push    r15
0x18001bd3a  lea     rbp, [rsp-27h]
0x18001bd3f  sub     rsp, 0F0h
0x18001bd46  mov     rax, cs:__security_cookie
0x18001bd4d  xor     rax, rsp
0x18001bd50  mov     [rbp+47h+var_30], rax
0x18001bd54  mov     rax, [r9]
0x18001bd57  movzx   r12d, r8w
0x18001bd5b  mov     r8, [rbp+47h+arg_20]
0x18001bd5f  mov     r14b, dl
0x18001bd62  mov     rbx, [rbp+47h+arg_28]
0x18001bd66  lea     rdx, [rbp+47h+var_C0]
0x18001bd6a  mov     r15, rcx
0x18001bd6d  mov     rsi, r9
0x18001bd70  mov     rax, [rax+10h]
0x18001bd74  mov     rcx, r9
0x18001bd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd7c  cmp     [rbp+47h+var_C0], 0
0x18001bd80  jnz     short loc_18001BDDF
0x18001bd82  mov     ebx, dword ptr [rbp+47h+var_B8]
0x18001bd85  lea     rax, aStat; "stat"
0x18001bd8c  mov     rcx, [rbp+4Fh]; this
0x18001bd90  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18001bd97  mov     [rsp+110h+var_E8], rax; char *
0x18001bd9c  mov     r9d, ebx; char *
0x18001bd9f  lea     rax, aHs_0; "%hs"
0x18001bda6  mov     edx, 43Ah; void *
0x18001bdab  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18001bdb0  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001bdb5  mov     eax, ebx
0x18001bdb7  mov     rcx, [rbp+47h+var_30]
0x18001bdbb  xor     rcx, rsp; StackCookie
0x18001bdbe  call    __security_check_cookie
0x18001bdc3  lea     r11, [rsp+110h+var_20]
0x18001bdcb  mov     rbx, [r11+30h]
0x18001bdcf  mov     rsi, [r11+38h]
0x18001bdd3  mov     rsp, r11
0x18001bdd6  pop     r15
0x18001bdd8  pop     r14
0x18001bdda  pop     r12
0x18001bddc  pop     rdi
0x18001bddd  pop     rbp
0x18001bdde  retn
0x18001bddf  mov     eax, [rbp+47h+var_48]
0x18001bde2  mov     dl, 85h
0x18001bde4  mov     dil, [rbp+47h+var_44]
0x18001bde8  mov     rcx, rbx
0x18001bdeb  movsd   xmm0, [rbp+47h+var_50]
0x18001bdf0  mov     [rsp+110h+var_C8], eax
0x18001bdf4  movzx   eax, [rbp+47h+var_43]
0x18001bdf8  mov     [rbp+47h+var_C3], ax
0x18001bdfc  mov     al, [rbp+47h+var_41]
0x18001bdff  mov     [rbp+47h+var_C1], al
0x18001be02  mov     [rbp+47h+var_C4], dil
0x18001be06  and     dil, 2
0x18001be0a  mov     al, dil
0x18001be0d  movsd   [rsp+110h+var_D0], xmm0
0x18001be13  mov     r9d, [r15+70h]
0x18001be17  neg     al
0x18001be19  sbb     r8d, r8d
0x18001be1c  and     r8d, 1000h
0x18001be23  call    ?EnsureSize@MessageResponse@Handler@p9fs@@QEAAXW4MessageType@3@II@Z; p9fs::Handler::MessageResponse::EnsureSize(p9fs::MessageType,uint,uint)
0x18001be28  mov     rdx, [rbx+10h]
0x18001be2c  mov     rax, [rbx]
0x18001be2f  cmp     rax, rdx
0x18001be32  jb      loc_18001C08A
0x18001be38  sub     rax, rdx
0x18001be3b  cmp     rax, 1
0x18001be3f  jb      loc_18001C08A
0x18001be45  mov     rcx, [rbx+8]
0x18001be49  lea     rax, [rdx+1]
0x18001be4d  mov     [rbx+10h], rax
0x18001be51  mov     [rdx+rcx], r14b
0x18001be55  mov     rdx, [rbx+10h]
0x18001be59  mov     rax, [rbx]
0x18001be5c  cmp     rax, rdx
0x18001be5f  jb      loc_18001C08A
0x18001be65  sub     rax, rdx
0x18001be68  cmp     rax, 2
0x18001be6c  jb      loc_18001C08A
0x18001be72  mov     rcx, [rbx+8]
0x18001be76  lea     rax, [rdx+2]
0x18001be7a  mov     [rbx+10h], rax
0x18001be7e  mov     [rdx+rcx], r12w
0x18001be83  lea     rdx, [rsp+110h+var_D0]; struct p9fs::Qid *
0x18001be88  mov     rcx, rbx; this
0x18001be8b  call    ?Qid@SpanWriter@p9fs@@QEAAXAEBU02@@Z; p9fs::SpanWriter::Qid(p9fs::Qid const &)
0x18001be90  mov     rdx, [rbx+10h]
0x18001be94  mov     rcx, [rbx]; this
0x18001be97  test    dil, dil
0x18001be9a  jz      loc_18001BF73
0x18001bea0  cmp     rcx, rdx
0x18001bea3  jb      loc_18001C090
0x18001bea9  sub     rcx, rdx
0x18001beac  lea     rax, [rcx-2]
0x18001beb0  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x18001beb4  ja      loc_18001C090
0x18001beba  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18001bebe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bec2  jz      loc_18001C090
0x18001bec8  mov     r8, [rbx+8]
0x18001becc  add     r8, 2
0x18001bed0  add     r8, rdx
0x18001bed3  jnz     short loc_18001BEDE
0x18001bed5  test    rcx, rcx
0x18001bed8  jnz     loc_18001C090
0x18001bede  mov     rax, [rsi]
0x18001bee1  lea     rdx, [rsp+110h+var_D0]
0x18001bee6  mov     [rsp+110h+var_E0], rcx
0x18001beeb  mov     rcx, rsi
0x18001beee  mov     [rsp+110h+var_D8], r8
0x18001bef3  lea     r8, [rsp+110h+var_E0]
0x18001bef8  mov     rax, [rax+88h]
0x18001beff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf04  mov     rdx, [rbx+10h]
0x18001bf08  mov     rax, [rbx]
0x18001bf0b  cmp     rax, rdx
0x18001bf0e  jb      loc_18001C090
0x18001bf14  sub     rax, rdx
0x18001bf17  cmp     byte ptr [rsp+110h+var_D0], 0
0x18001bf1c  jz      short loc_18001BF67
0x18001bf1e  cmp     rax, 2
0x18001bf22  jb      loc_18001C090
0x18001bf28  mov     rcx, [rbx+8]
0x18001bf2c  lea     rax, [rdx+2]
0x18001bf30  mov     [rbx+10h], rax
0x18001bf34  movzx   eax, word ptr [rsp+110h+var_D0+4]
0x18001bf39  mov     [rdx+rcx], ax
0x18001bf3d  mov     rcx, [rbx+10h]
0x18001bf41  mov     rax, [rbx]
0x18001bf44  cmp     rax, rcx
0x18001bf47  jb      loc_18001C090
0x18001bf4d  mov     edx, dword ptr [rsp+110h+var_D0+4]
0x18001bf51  sub     rax, rcx
0x18001bf54  cmp     rax, rdx
0x18001bf57  jb      loc_18001C090
0x18001bf5d  lea     rax, [rdx+rcx]
0x18001bf61  mov     [rbx+10h], rax
0x18001bf65  jmp     short loc_18001BF9B
0x18001bf67  cmp     rax, 2
0x18001bf6b  jb      loc_18001C090
0x18001bf71  jmp     short loc_18001BF89
0x18001bf73  cmp     rcx, rdx
0x18001bf76  jb      loc_18001C08A
0x18001bf7c  sub     rcx, rdx
0x18001bf7f  cmp     rcx, 2
0x18001bf83  jb      loc_18001C08A
0x18001bf89  mov     rcx, [rbx+8]
0x18001bf8d  lea     rax, [rdx+2]
0x18001bf91  mov     [rbx+10h], rax
0x18001bf95  xor     eax, eax
0x18001bf97  mov     [rdx+rcx], ax
0x18001bf9b  mov     rdx, [rbx+10h]
0x18001bf9f  mov     rax, [rbx]
0x18001bfa2  cmp     rax, rdx
0x18001bfa5  jb      loc_18001C08A
0x18001bfab  sub     rax, rdx
0x18001bfae  cmp     rax, 4
0x18001bfb2  jb      loc_18001C08A
0x18001bfb8  mov     rcx, [rbx+8]
0x18001bfbc  lea     rax, [rdx+4]
0x18001bfc0  mov     [rbx+10h], rax
0x18001bfc4  mov     dword ptr [rdx+rcx], 0
0x18001bfcb  lea     rdx, [rbp+47h+var_B8]; struct p9fs::SpanWriter *
0x18001bfcf  mov     rcx, rbx; this
0x18001bfd2  call    ?SpanWriteStatResult@util@p9fs@@YAXAEAVSpanWriter@2@AEBUStatResult@2@@Z; p9fs::util::SpanWriteStatResult(p9fs::SpanWriter &,p9fs::StatResult const &)
0x18001bfd7  mov     rdx, [rbx+10h]
0x18001bfdb  mov     rax, [rbx]
0x18001bfde  cmp     rax, rdx
0x18001bfe1  jb      loc_18001C08A
0x18001bfe7  sub     rax, rdx
0x18001bfea  cmp     rax, 8
0x18001bfee  jb      loc_18001C08A
0x18001bff4  mov     rcx, [rbx+8]
0x18001bff8  lea     rax, [rdx+8]
0x18001bffc  mov     [rbx+10h], rax
0x18001c000  mov     qword ptr [rdx+rcx], 0
0x18001c008  mov     rdx, [rbx+10h]
0x18001c00c  mov     rax, [rbx]
0x18001c00f  cmp     rax, rdx
0x18001c012  jb      short loc_18001C08A
0x18001c014  sub     rax, rdx
0x18001c017  cmp     rax, 8
0x18001c01b  jb      short loc_18001C08A
0x18001c01d  mov     rcx, [rbx+8]
0x18001c021  lea     rax, [rdx+8]
0x18001c025  mov     [rbx+10h], rax
0x18001c029  mov     qword ptr [rdx+rcx], 0
0x18001c031  mov     rdx, [rbx+10h]
0x18001c035  mov     rax, [rbx]
0x18001c038  cmp     rax, rdx
0x18001c03b  jb      short loc_18001C08A
0x18001c03d  sub     rax, rdx
0x18001c040  cmp     rax, 8
0x18001c044  jb      short loc_18001C08A
0x18001c046  mov     rcx, [rbx+8]
0x18001c04a  lea     rax, [rdx+8]
0x18001c04e  mov     [rbx+10h], rax
0x18001c052  mov     qword ptr [rdx+rcx], 0
0x18001c05a  mov     rdx, [rbx+10h]
0x18001c05e  mov     rax, [rbx]
0x18001c061  cmp     rax, rdx
0x18001c064  jb      short loc_18001C08A
0x18001c066  sub     rax, rdx
0x18001c069  cmp     rax, 8
0x18001c06d  jb      short loc_18001C08A
0x18001c06f  mov     rcx, [rbx+8]
0x18001c073  lea     rax, [rdx+8]
0x18001c077  mov     [rbx+10h], rax
0x18001c07b  xor     eax, eax
0x18001c07d  mov     qword ptr [rdx+rcx], 0
0x18001c085  jmp     loc_18001BDB7
0x18001c08a  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18001c090  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
