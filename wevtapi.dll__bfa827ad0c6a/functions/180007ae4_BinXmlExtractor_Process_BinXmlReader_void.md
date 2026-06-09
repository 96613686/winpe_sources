# BinXmlExtractor::Process(BinXmlReader &,void *)

- ea: `0x180007ae4`
- end: `0x180007fb2`
- name: `?Process@BinXmlExtractor@@QEAAXAEAVBinXmlReader@@PEAX@Z`
- size: `1230`
- prototype: `void __fastcall(BinXmlExtractor *this, struct BinXmlReader *, void *)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001840`
- `0x180001f34`
- `0x1800071b0`
- `0x180017864`

## callees

- `0x180003aa0`
- `0x180004070`
- `0x180007ae4`
- `0x18000ab80`
- `0x18000b6a0`
- `0x1800131e8`
- `0x180013398`
- `0x180013750`
- `0x180013bb0`
- `0x1800181a0`
- `0x180019700`
- `0x180023548`
- `0x180038fa4`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007df5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007df5`

## pseudocode

```c
void __fastcall BinXmlExtractor::Process(BinXmlExtractor *this, struct BinXmlReader *a2, void *a3)
{
  __int64 v3; // rbx
  BinXmlExtractor *v5; // r15
  char *v6; // rsi
  char *v7; // r14
  unsigned int v8; // r12d
  int v9; // edi
  char *v10; // rbx
  __int64 *v11; // rsi
  unsigned int v12; // r8d
  const WCHAR *v13; // rcx
  __int64 v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rdi
  int v17; // edi
  __int64 v18; // rdx
  int v19; // esi
  unsigned int v20; // esi
  unsigned int v21; // r14d
  int v22; // [rsp+38h] [rbp-59h]
  int v23; // [rsp+38h] [rbp-59h]
  LPCWCH lpString2; // [rsp+40h] [rbp-51h] BYREF
  int cchCount2; // [rsp+48h] [rbp-49h]
  __int64 v26; // [rsp+4Ch] [rbp-45h]
  char v27; // [rsp+54h] [rbp-3Dh]
  LPCWCH v28; // [rsp+58h] [rbp-39h]
  const WCHAR *v29; // [rsp+60h] [rbp-31h] BYREF
  int v30; // [rsp+68h] [rbp-29h]
  int v31; // [rsp+6Ch] [rbp-25h]
  __int128 pExceptionObject; // [rsp+70h] [rbp-21h] BYREF
  __int64 v33; // [rsp+80h] [rbp-11h]
  int v34; // [rsp+88h] [rbp-9h]
  int v35; // [rsp+8Ch] [rbp-5h]
  int v36; // [rsp+90h] [rbp-1h]
  __int64 v37; // [rsp+98h] [rbp+7h] BYREF
  int v38; // [rsp+A0h] [rbp+Fh]
  int v39; // [rsp+A4h] [rbp+13h]
  __int64 v40; // [rsp+A8h] [rbp+17h] BYREF
  int v41; // [rsp+B0h] [rbp+1Fh]
  int v42; // [rsp+B4h] [rbp+23h]
  bool v45; // [rsp+110h] [rbp+7Fh] BYREF

  v3 = (__int64)a3;
  v5 = this;
  lpString2 = 0;
  cchCount2 = -1;
  v26 = 0;
  v27 = 0;
  v45 = 0;
  v6 = (char *)this + 72;
  v7 = (char *)this + 72;
  v8 = *((_DWORD *)this + 30);
  v9 = *((_DWORD *)this + 32);
  v22 = v9;
  while ( 1 )
  {
    while ( 1 )
    {
      BinXmlReader::NextToken(a2, (struct BinXmlToken *)&lpString2, 1);
      if ( HIDWORD(v26) != 1 )
        break;
      v10 = *(char **)v7;
      if ( !*(_QWORD *)v7 )
        goto LABEL_2;
      do
      {
        if ( v10[60] )
          break;
        if ( BinXmlString::Equals((BinXmlString *)lpString2, *((const wchar_t **)v10 + 4), *((_QWORD *)v10 + 5)) )
          break;
        v10 = (char *)*((_QWORD *)v10 + 3);
      }
      while ( v10 );
      if ( !v10 )
      {
LABEL_2:
        BinXmlReader::SeekToEndOfCurrentElement(a2);
        goto LABEL_3;
      }
      if ( (v10[52] & 1) != 0 )
      {
        v17 = 1;
        v23 = 1;
        if ( BinXmlReader::IsCurrentElementRootOfTemplate(a2) )
          goto LABEL_55;
        BinXmlReader::SeekToEndOfCurrentElementStartTag(a2, &v45);
        if ( v45 )
        {
          v17 = 0;
        }
        else
        {
          BinXmlReader::NextToken(a2, (struct BinXmlToken *)&lpString2, 1);
          if ( HIDWORD(v26) == 1 )
          {
            v17 = 2;
            v23 = 2;
          }
          else
          {
            v17 = HIDWORD(v26) != 4;
            v23 = v17;
            if ( HIDWORD(v26) == 4 )
              goto LABEL_49;
          }
LABEL_55:
          if ( BinXmlReader::IsCurrentElementRootOfTemplate(a2) )
          {
            v20 = BinXmlReader::NumTemplateInstanceValues(a2);
            v21 = 0;
            if ( v20 )
            {
              do
              {
                v37 = 0;
                v38 = -1;
                v39 = 0;
                BinXmlReader::GetTemplateInstanceValue(a2, v21, (struct BinXmlVariant *)&v37);
                (*((void (__fastcall **)(void *, _QWORD, __int64 *))v5 + 17))(a3, *((unsigned int *)v10 + 12), &v37);
                ++v21;
              }
              while ( v21 < v20 );
              v17 = v23;
            }
LABEL_50:
            v19 = 0;
            if ( v17 )
            {
              do
              {
                BinXmlReader::SeekToEndOfCurrentElement(a2);
                ++v19;
              }
              while ( v19 < v17 );
            }
            v7 = (char *)*((_QWORD *)v10 + 2);
            v8 = *((_DWORD *)v7 + 12);
            v9 = *((_DWORD *)v7 + 14);
            v22 = v9;
LABEL_44:
            v6 = (char *)v5 + 72;
            goto LABEL_3;
          }
        }
LABEL_49:
        v40 = 0;
        v41 = -1;
        v42 = 0;
        v18 = *((unsigned int *)v10 + 12);
        LODWORD(v18) = v18 | 0x80000000;
        (*((void (__fastcall **)(void *, __int64, __int64 *))v5 + 17))(a3, v18, &v40);
        goto LABEL_50;
      }
      v7 = v10;
      v8 = *((_DWORD *)v10 + 12);
      v9 = *((_DWORD *)v10 + 14);
      v22 = v9;
      if ( !*((_QWORD *)v10 + 1) )
      {
        BinXmlReader::SeekToEndOfCurrentElementStartTag(a2, &v45);
        if ( !v45 )
          goto LABEL_3;
        v7 = (char *)*((_QWORD *)v10 + 2);
        v8 = *((_DWORD *)v7 + 12);
        v9 = *((_DWORD *)v7 + 14);
        goto LABEL_22;
      }
LABEL_4:
      v3 = (__int64)a3;
    }
    if ( HIDWORD(v26) == 3 || HIDWORD(v26) == 4 )
    {
      if ( v7 == v6 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 13);
        }
        pExceptionObject = 0;
        v33 = 0;
        v34 = 13;
        v35 = -1;
        v36 = 583;
        throw (EvtException *)&pExceptionObject;
      }
      v7 = (char *)*((_QWORD *)v7 + 2);
      v8 = *((_DWORD *)v7 + 12);
      v9 = *((_DWORD *)v7 + 14);
LABEL_22:
      v22 = v9;
      goto LABEL_3;
    }
    if ( HIDWORD(v26) != 5 )
      break;
    if ( v8 != -1 )
    {
      BinXmlExtractor::InvokeCallback((__int64)v5, v3, v8, v9, (__int64)&lpString2);
      goto LABEL_3;
    }
  }
  if ( HIDWORD(v26) == 6 )
  {
    v11 = (__int64 *)*((_QWORD *)v7 + 1);
    if ( v11 )
    {
      do
      {
        if ( BinXmlString::Equals((BinXmlString *)lpString2, (const wchar_t *)v11[4], v11[5]) )
          break;
        v11 = (__int64 *)*v11;
      }
      while ( v11 );
      v3 = (__int64)a3;
    }
    do
    {
      BinXmlReader::NextToken(a2, (struct BinXmlToken *)&lpString2, 1);
      if ( HIDWORD(v26) != 5 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 13);
        }
        pExceptionObject = 0;
        v33 = 0;
        v34 = 13;
        v35 = -1;
        v36 = 613;
        throw (EvtException *)&pExceptionObject;
      }
      if ( v11 )
      {
        v12 = *((_DWORD *)v11 + 12);
        if ( v12 != -1 )
          BinXmlExtractor::InvokeCallback((__int64)v5, v3, v12, *((_DWORD *)v11 + 13), (__int64)&lpString2);
        if ( v11[1] != v11[2] )
        {
          v8 = -1;
          if ( (_DWORD)v26 )
          {
            v29 = 0;
            v30 = -1;
            v31 = 0;
            if ( (_DWORD)v26 == 1 )
            {
              v13 = lpString2;
              v28 = lpString2;
              LODWORD(v14) = cchCount2;
            }
            else
            {
              BinXmlVariantHolder::InitToString((BinXmlVariantHolder *)&v29, (const struct BinXmlVariant *)&lpString2);
              v13 = v29;
              v28 = v29;
              v14 = -1;
              do
                ++v14;
              while ( v29[v14] );
            }
            v15 = v11[1];
            v16 = v11[2];
            while ( 1 )
            {
              if ( v15 == v16 )
              {
                v9 = v22;
                goto LABEL_42;
              }
              if ( (unsigned int)v14 == *(_QWORD *)(v15 + 8)
                && CompareStringOrdinal(*(LPCWCH *)v15, *(_DWORD *)(v15 + 8), v13, v14, 1) == 2 )
              {
                break;
              }
              v15 += 24;
              v13 = v28;
            }
            v8 = *(_DWORD *)(v15 + 16);
            v9 = *(_DWORD *)(v15 + 20);
            v22 = v9;
LABEL_42:
            BinXmlVariantHolder::Clear((BinXmlVariantHolder *)&v29);
            v5 = this;
          }
        }
      }
      v3 = (__int64)a3;
    }
    while ( v27 );
    goto LABEL_44;
  }
LABEL_3:
  if ( HIDWORD(v26) )
    goto LABEL_4;
}

```

## disassembly

```asm
0x180007ae4  mov     rax, rsp
0x180007ae7  mov     [rax+10h], rbx
0x180007aeb  mov     [rax+18h], r8
0x180007aef  mov     [rax+8], rcx
0x180007af3  push    rbp
0x180007af4  push    rsi
0x180007af5  push    rdi
0x180007af6  push    r12
0x180007af8  push    r13
0x180007afa  push    r14
0x180007afc  push    r15
0x180007afe  lea     rbp, [rax-5Fh]
0x180007b02  sub     rsp, 0B0h
0x180007b09  mov     rbx, r8
0x180007b0c  mov     r13, rdx
0x180007b0f  mov     r15, rcx
0x180007b12  xor     eax, eax
0x180007b14  mov     [rbp+57h+lpString2], rax
0x180007b18  mov     [rbp+57h+cchCount2], 0FFFFFFFFh
0x180007b1f  mov     [rbp+57h+var_9C], rax
0x180007b23  mov     [rbp+57h+var_94], al
0x180007b26  mov     [rbp+57h+arg_18], al
0x180007b29  lea     rsi, [rcx+48h]
0x180007b2d  mov     r14, rsi
0x180007b30  mov     r12d, [rsi+30h]
0x180007b34  mov     edi, [rsi+38h]
0x180007b37  mov     [rbp+57h+var_B0], edi
0x180007b3a  jmp     short loc_180007B52
0x180007b3c  mov     rcx, r13; this
0x180007b3f  call    ?SeekToEndOfCurrentElement@BinXmlReader@@QEAAXXZ; BinXmlReader::SeekToEndOfCurrentElement(void)
0x180007b44  cmp     dword ptr [rbp+57h+var_9C+4], 0
0x180007b48  jz      loc_180007C35
0x180007b4e  mov     rbx, [rbp+57h+arg_10]
0x180007b52  mov     r8b, 1; bool
0x180007b55  lea     rdx, [rbp+57h+lpString2]; struct BinXmlToken *
0x180007b59  mov     rcx, r13; this
0x180007b5c  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x180007b61  mov     ecx, dword ptr [rbp+57h+var_9C+4]
0x180007b64  sub     ecx, 1
0x180007b67  jnz     short loc_180007BDE
0x180007b69  mov     rbx, [r14]
0x180007b6c  xor     ecx, ecx
0x180007b6e  test    rbx, rbx
0x180007b71  jz      short loc_180007B3C
0x180007b73  cmp     [rbx+3Ch], cl
0x180007b76  jnz     short loc_180007B98
0x180007b78  mov     r8, [rbx+28h]; unsigned __int64
0x180007b7c  mov     rdx, [rbx+20h]; wchar_t *
0x180007b80  mov     rcx, [rbp+57h+lpString2]; this
0x180007b84  call    ?Equals@BinXmlString@@QEBA_NPEB_W_K@Z; BinXmlString::Equals(wchar_t const *,unsigned __int64)
0x180007b89  xor     ecx, ecx
0x180007b8b  test    al, al
0x180007b8d  jnz     short loc_180007B98
0x180007b8f  mov     rbx, [rbx+18h]
0x180007b93  test    rbx, rbx
0x180007b96  jnz     short loc_180007B73
0x180007b98  test    rbx, rbx
0x180007b9b  jz      short loc_180007B3C
0x180007b9d  test    byte ptr [rbx+34h], 1
0x180007ba1  jnz     loc_180007D32
0x180007ba7  mov     r14, rbx
0x180007baa  mov     r12d, [rbx+30h]
0x180007bae  mov     edi, [rbx+38h]
0x180007bb1  mov     [rbp+57h+var_B0], edi
0x180007bb4  cmp     [rbx+8], rcx
0x180007bb8  jnz     short loc_180007B4E
0x180007bba  lea     rdx, [rbp+57h+arg_18]; bool *
0x180007bbe  mov     rcx, r13; this
0x180007bc1  call    ?SeekToEndOfCurrentElementStartTag@BinXmlReader@@QEAAXAEA_N@Z; BinXmlReader::SeekToEndOfCurrentElementStartTag(bool &)
0x180007bc6  cmp     [rbp+57h+arg_18], 0
0x180007bca  jz      loc_180007B44
0x180007bd0  mov     r14, [rbx+10h]
0x180007bd4  mov     r12d, [r14+30h]
0x180007bd8  mov     edi, [r14+38h]
0x180007bdc  jmp     short loc_180007C2D
0x180007bde  sub     ecx, 2
0x180007be1  jz      short loc_180007C16
0x180007be3  sub     ecx, 1
0x180007be6  jz      short loc_180007C16
0x180007be8  sub     ecx, 1
0x180007beb  jnz     short loc_180007C50
0x180007bed  cmp     r12d, 0FFFFFFFFh
0x180007bf1  jz      loc_180007B52
0x180007bf7  lea     rax, [rbp+57h+lpString2]
0x180007bfb  mov     [rsp+20h], rax
0x180007c00  mov     r9d, edi
0x180007c03  mov     r8d, r12d
0x180007c06  mov     rdx, rbx
0x180007c09  mov     rcx, r15
0x180007c0c  call    ?InvokeCallback@BinXmlExtractor@@AEAAXPEAXKW4BinXmlVarType@@AEAUBinXmlVariant@@@Z; BinXmlExtractor::InvokeCallback(void *,ulong,BinXmlVarType,BinXmlVariant &)
0x180007c11  jmp     loc_180007B44
0x180007c16  cmp     r14, rsi
0x180007c19  jz      loc_180007F48
0x180007c1f  mov     rax, [r14+10h]
0x180007c23  mov     r14, rax
0x180007c26  mov     r12d, [rax+30h]
0x180007c2a  mov     edi, [rax+38h]
0x180007c2d  mov     [rbp+57h+var_B0], edi
0x180007c30  jmp     loc_180007B44
0x180007c35  mov     rbx, [rsp+0E0h+arg_8]
0x180007c3d  add     rsp, 0B0h
0x180007c44  pop     r15
0x180007c46  pop     r14
0x180007c48  pop     r13
0x180007c4a  pop     r12
0x180007c4c  pop     rdi
0x180007c4d  pop     rsi
0x180007c4e  pop     rbp
0x180007c4f  retn
0x180007c50  cmp     ecx, 1
0x180007c53  jnz     loc_180007B44
0x180007c59  mov     rsi, [r14+8]
0x180007c5d  test    rsi, rsi
0x180007c60  jz      short loc_180007C83
0x180007c62  mov     r8, [rsi+28h]; unsigned __int64
0x180007c66  mov     rdx, [rsi+20h]; wchar_t *
0x180007c6a  mov     rcx, [rbp+57h+lpString2]; this
0x180007c6e  call    ?Equals@BinXmlString@@QEBA_NPEB_W_K@Z; BinXmlString::Equals(wchar_t const *,unsigned __int64)
0x180007c73  test    al, al
0x180007c75  jnz     short loc_180007C7F
0x180007c77  mov     rsi, [rsi]
0x180007c7a  test    rsi, rsi
0x180007c7d  jnz     short loc_180007C62
0x180007c7f  mov     rbx, [rbp+57h+arg_10]
0x180007c83  mov     r8b, 1; bool
0x180007c86  lea     rdx, [rbp+57h+lpString2]; struct BinXmlToken *
0x180007c8a  mov     rcx, r13; this
0x180007c8d  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x180007c92  cmp     dword ptr [rbp+57h+var_9C+4], 5
0x180007c96  jnz     loc_180007EDE
0x180007c9c  xor     ecx, ecx
0x180007c9e  test    rsi, rsi
0x180007ca1  jz      short loc_180007D1B
0x180007ca3  mov     r8d, [rsi+30h]
0x180007ca7  cmp     r8d, 0FFFFFFFFh
0x180007cab  jnz     loc_180007EAA
0x180007cb1  mov     rax, [rsi+10h]
0x180007cb5  cmp     [rsi+8], rax
0x180007cb9  jz      short loc_180007D1B
0x180007cbb  or      edx, 0FFFFFFFFh
0x180007cbe  mov     r12d, edx
0x180007cc1  mov     eax, dword ptr [rbp+57h+var_9C]
0x180007cc4  test    eax, eax
0x180007cc6  jz      short loc_180007D1B
0x180007cc8  mov     [rbp+57h+var_88], rcx
0x180007ccc  mov     [rbp+57h+var_80], edx
0x180007ccf  mov     [rbp+57h+var_7C], ecx
0x180007cd2  cmp     eax, 1
0x180007cd5  jnz     loc_180007E80
0x180007cdb  mov     rcx, [rbp+57h+lpString2]
0x180007cdf  mov     [rbp+57h+var_90], rcx
0x180007ce3  mov     r15d, [rbp+57h+cchCount2]
0x180007ce7  mov     rbx, [rsi+8]
0x180007ceb  mov     rdi, [rsi+10h]
0x180007cef  cmp     rbx, rdi
0x180007cf2  jz      short loc_180007D0B
0x180007cf4  mov     eax, r15d
0x180007cf7  cmp     rax, [rbx+8]
0x180007cfb  jz      loc_180007DE1
0x180007d01  add     rbx, 18h
0x180007d05  mov     rcx, [rbp+57h+var_90]
0x180007d09  jmp     short loc_180007CEF
0x180007d0b  mov     edi, [rbp+57h+var_B0]
0x180007d0e  lea     rcx, [rbp+57h+var_88]; this
0x180007d12  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x180007d17  mov     r15, [rbp+57h+arg_0]
0x180007d1b  cmp     [rbp+57h+var_94], 0
0x180007d1f  mov     rbx, [rbp+57h+arg_10]
0x180007d23  jnz     loc_180007C83
0x180007d29  lea     rsi, [r15+48h]
0x180007d2d  jmp     loc_180007B44
0x180007d32  mov     edi, 1
0x180007d37  mov     [rbp+57h+var_B0], edi
0x180007d3a  mov     rcx, r13; this
0x180007d3d  call    ?IsCurrentElementRootOfTemplate@BinXmlReader@@QEAA_NXZ; BinXmlReader::IsCurrentElementRootOfTemplate(void)
0x180007d42  xor     r12d, r12d
0x180007d45  test    al, al
0x180007d47  jnz     loc_180007E13
0x180007d4d  lea     rdx, [rbp+57h+arg_18]; bool *
0x180007d51  mov     rcx, r13; this
0x180007d54  call    ?SeekToEndOfCurrentElementStartTag@BinXmlReader@@QEAAXAEA_N@Z; BinXmlReader::SeekToEndOfCurrentElementStartTag(bool &)
0x180007d59  cmp     [rbp+57h+arg_18], r12b
0x180007d5d  jnz     loc_180007ED6
0x180007d63  mov     r8b, dil; bool
0x180007d66  lea     rdx, [rbp+57h+lpString2]; struct BinXmlToken *
0x180007d6a  mov     rcx, r13; this
0x180007d6d  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x180007d72  cmp     dword ptr [rbp+57h+var_9C+4], edi
0x180007d75  jz      loc_180007EC9
0x180007d7b  cmp     dword ptr [rbp+57h+var_9C+4], 4
0x180007d7f  cmovz   edi, r12d
0x180007d83  mov     [rbp+57h+var_B0], edi
0x180007d86  test    edi, edi
0x180007d88  jnz     loc_180007E13
0x180007d8e  mov     [rbp+57h+var_40], r12
0x180007d92  mov     [rbp+57h+var_38], 0FFFFFFFFh
0x180007d99  mov     [rbp+57h+var_34], r12d
0x180007d9d  mov     edx, [rbx+30h]
0x180007da0  bts     edx, 1Fh
0x180007da4  lea     r8, [rbp+57h+var_40]
0x180007da8  mov     rcx, [rbp+57h+arg_10]
0x180007dac  mov     rax, [r15+88h]
0x180007db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007db8  mov     esi, r12d
0x180007dbb  test    edi, edi
0x180007dbd  jz      short loc_180007DCD
0x180007dbf  mov     rcx, r13; this
0x180007dc2  call    ?SeekToEndOfCurrentElement@BinXmlReader@@QEAAXXZ; BinXmlReader::SeekToEndOfCurrentElement(void)
0x180007dc7  inc     esi
0x180007dc9  cmp     esi, edi
0x180007dcb  jl      short loc_180007DBF
0x180007dcd  mov     r14, [rbx+10h]
0x180007dd1  mov     r12d, [r14+30h]
0x180007dd5  mov     edi, [r14+38h]
0x180007dd9  mov     [rbp+57h+var_B0], edi
0x180007ddc  jmp     loc_180007D29
0x180007de1  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x180007de9  mov     r9d, r15d; cchCount2
0x180007dec  mov     r8, rcx; lpString2
0x180007def  mov     edx, [rbx+8]; cchCount1
0x180007df2  mov     rcx, [rbx]; lpString1
0x180007df5  call    cs:__imp_CompareStringOrdinal
0x180007dfb  cmp     eax, 2
0x180007dfe  jnz     loc_180007D01
0x180007e04  mov     r12d, [rbx+10h]
0x180007e08  mov     edi, [rbx+14h]
0x180007e0b  mov     [rbp+57h+var_B0], edi
0x180007e0e  jmp     loc_180007D0E
0x180007e13  mov     rcx, r13; this
0x180007e16  call    ?IsCurrentElementRootOfTemplate@BinXmlReader@@QEAA_NXZ; BinXmlReader::IsCurrentElementRootOfTemplate(void)
0x180007e1b  test    al, al
0x180007e1d  jz      loc_180007D8E
0x180007e23  mov     rcx, r13; this
0x180007e26  call    ?NumTemplateInstanceValues@BinXmlReader@@QEAAKXZ; BinXmlReader::NumTemplateInstanceValues(void)
0x180007e2b  mov     esi, eax
0x180007e2d  mov     r14d, r12d
0x180007e30  test    eax, eax
0x180007e32  jz      short loc_180007DB8
0x180007e34  mov     r12, [rbp+57h+arg_10]
0x180007e38  xor     edi, edi
0x180007e3a  mov     [rbp+57h+var_50], rdi
0x180007e3e  mov     [rbp+57h+var_48], 0FFFFFFFFh
0x180007e45  mov     [rbp+57h+var_44], edi
0x180007e48  lea     r8, [rbp+57h+var_50]; struct BinXmlVariant *
0x180007e4c  mov     edx, r14d; unsigned int
0x180007e4f  mov     rcx, r13; this
0x180007e52  call    ?GetTemplateInstanceValue@BinXmlReader@@QEAAXKAEAUBinXmlVariant@@@Z; BinXmlReader::GetTemplateInstanceValue(ulong,BinXmlVariant &)
0x180007e57  lea     r8, [rbp+57h+var_50]
0x180007e5b  mov     edx, [rbx+30h]
0x180007e5e  mov     rcx, r12
0x180007e61  mov     rax, [r15+88h]
0x180007e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6d  inc     r14d
0x180007e70  cmp     r14d, esi
0x180007e73  jb      short loc_180007E3A
0x180007e75  mov     edi, [rbp+57h+var_B0]
0x180007e78  xor     r12d, r12d
0x180007e7b  jmp     loc_180007DB8
0x180007e80  lea     rdx, [rbp+57h+lpString2]; struct BinXmlVariant *
0x180007e84  lea     rcx, [rbp+57h+var_88]; this
0x180007e88  call    ?InitToString@BinXmlVariantHolder@@QEAA_NAEBUBinXmlVariant@@@Z; BinXmlVariantHolder::InitToString(BinXmlVariant const &)
0x180007e8d  mov     rcx, [rbp+57h+var_88]
0x180007e91  mov     [rbp+57h+var_90], rcx
0x180007e95  or      r15, 0FFFFFFFFFFFFFFFFh
0x180007e99  xor     eax, eax
0x180007e9b  inc     r15
0x180007e9e  cmp     [rcx+r15*2], ax
0x180007ea3  jnz     short loc_180007E9B
0x180007ea5  jmp     loc_180007CE7
0x180007eaa  lea     rax, [rbp+57h+lpString2]
0x180007eae  mov     [rsp+20h], rax
0x180007eb3  mov     r9d, [rsi+34h]
0x180007eb7  mov     rdx, rbx
0x180007eba  mov     rcx, r15
0x180007ebd  call    ?InvokeCallback@BinXmlExtractor@@AEAAXPEAXKW4BinXmlVarType@@AEAUBinXmlVariant@@@Z; BinXmlExtractor::InvokeCallback(void *,ulong,BinXmlVarType,BinXmlVariant &)
0x180007ec2  xor     ecx, ecx
0x180007ec4  jmp     loc_180007CB1
0x180007ec9  mov     edi, 2
0x180007ece  mov     [rbp+57h+var_B0], edi
0x180007ed1  jmp     loc_180007E13
0x180007ed6  mov     edi, r12d
0x180007ed9  jmp     loc_180007D8E
0x180007ede  lea     rax, WPP_GLOBAL_Control
0x180007ee5  mov     ebx, 0Dh
0x180007eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ef1  cmp     rcx, rax
0x180007ef4  jz      short loc_180007F18
0x180007ef6  test    byte ptr [rcx+1Ch], 2
0x180007efa  jz      short loc_180007F18
0x180007efc  cmp     byte ptr [rcx+19h], 2
0x180007f00  jb      short loc_180007F18
0x180007f02  lea     edx, [rbx+15h]
0x180007f05  mov     r9d, ebx
0x180007f08  lea     r8, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids
0x180007f0f  mov     rcx, [rcx+10h]
0x180007f13  call    WPP_SF_D
0x180007f18  xorps   xmm0, xmm0
0x180007f1b  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180007f20  xor     eax, eax
0x180007f22  mov     [rbp+57h+var_68], rax
  ... truncated ...
```
