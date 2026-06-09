# RedirectedSCardTransmit(unsigned __int64,_SCARD_IO_REQUEST const *,uchar const *,ulong,_SCARD_IO_REQUEST *,uchar *,ulong *)

- ea: `0x18000396c`
- end: `0x180003dd8`
- name: `?RedirectedSCardTransmit@@YAJ_KPEBU_SCARD_IO_REQUEST@@PEBEKPEAU1@PEAEPEAK@Z`
- size: `1132`
- prototype: `__int64 __fastcall(unsigned __int64, const struct _SCARD_IO_REQUEST *, const unsigned __int8 *, unsigned int, struct _SCARD_IO_REQUEST *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003790`

## callees

- `0x18000396c`
- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x18001991c`
- `0x180019a14`
- `0x18001c7a8`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c97`
- `RPCRT4!NdrMesTypeDecode3` at `0x180003bf3`
- `RPCRT4!NdrMesTypeDecode3` at `0x180003bf3`
- `RPCRT4!NdrMesTypeEncode3` at `0x180003b2e`
- `RPCRT4!NdrMesTypeEncode3` at `0x180003b2e`
- `RPCRT4!NdrMesTypeFree3` at `0x180003cf1`
- `RPCRT4!NdrMesTypeFree3` at `0x180003cf1`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800039f6`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800039f6`
- `RPCRT4!MesHandleFree` at `0x180003b89`
- `RPCRT4!MesHandleFree` at `0x180003d9a`
- `RPCRT4!MesHandleFree` at `0x180003b89`
- `RPCRT4!MesHandleFree` at `0x180003d9a`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180003ba9`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180003ba9`

## pseudocode

```c
__int64 __fastcall RedirectedSCardTransmit(
        __int64 a1,
        const struct _SCARD_IO_REQUEST *a2,
        const unsigned __int8 *a3,
        int a4,
        struct _SCARD_IO_REQUEST *a5,
        unsigned __int8 *a6,
        unsigned int *a7)
{
  unsigned int SCardError; // edi
  DWORD cbPciLength; // eax
  struct _SCARD_IO_REQUEST *v14; // rsi
  DWORD v15; // eax
  unsigned __int8 *v16; // r15
  unsigned int *v17; // r13
  int v18; // eax
  __int64 v19; // rdx
  size_t v20; // r8
  SIZE_T v21; // rdi
  const void *v22; // rsi
  LPCRITICAL_SECTION *v23; // rcx
  unsigned int v24; // eax
  LPCRITICAL_SECTION ProcessHeap; // rax
  unsigned __int8 *v26; // rax
  unsigned __int8 *v27; // rcx
  handle_t pHandle; // [rsp+40h] [rbp-D8h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-D0h]
  char *pBuffer; // [rsp+50h] [rbp-C8h] BYREF
  struct _BUFFER_LIST_STRUCT *v31; // [rsp+58h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+60h] [rbp-B8h] BYREF
  __int128 v33; // [rsp+70h] [rbp-A8h] BYREF
  SIZE_T dwBytes[2]; // [rsp+80h] [rbp-98h]
  _OWORD pObject[2]; // [rsp+90h] [rbp-88h] BYREF
  DWORD dwProtocol; // [rsp+B0h] [rbp-68h]
  DWORD v37; // [rsp+B4h] [rbp-64h]
  const struct _SCARD_IO_REQUEST *v38; // [rsp+B8h] [rbp-60h]
  int v39; // [rsp+C0h] [rbp-58h]
  const unsigned __int8 *v40; // [rsp+C8h] [rbp-50h]
  __int128 *v41; // [rsp+D0h] [rbp-48h]
  BOOL v42; // [rsp+D8h] [rbp-40h]
  unsigned int v43; // [rsp+DCh] [rbp-3Ch]
  unsigned int pEncodedSize; // [rsp+120h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v31 = 0;
  memset_0(pObject, 0, 0x50u);
  v33 = 0;
  *(_OWORD *)dwBytes = 0;
  v32 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject[0] = *(_OWORD *)(a1 + 8);
    pObject[1] = *(_OWORD *)(a1 + 24);
    dwProtocol = a2->dwProtocol;
    cbPciLength = a2->cbPciLength;
    if ( cbPciLength < 8 )
    {
      SCardError = -2146435068;
      goto LABEL_45;
    }
    v37 = cbPciLength - 8;
    v38 = cbPciLength == 8 ? 0LL : &a2[1];
    v39 = a4;
    v40 = a3;
    v14 = a5;
    if ( a5 )
    {
      v41 = &v32;
      LODWORD(v32) = a5->dwProtocol;
      v15 = a5->cbPciLength;
      if ( v15 < 8 )
      {
        SCardError = -2146435047;
        goto LABEL_45;
      }
      DWORD1(v32) = v15 - 8;
      *((_QWORD *)&v32 + 1) = v15 == 8 ? 0LL : &a5[1];
    }
    else
    {
      v41 = 0;
    }
    v16 = a6;
    v42 = a6 == 0;
    v17 = a7;
    v43 = *a7;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Eu, pObject);
    v18 = _SendSCardIOCTL(0x900D0u, pBuffer, pEncodedSize, &v31, **(LPCRITICAL_SECTION **)a1, 0xFFFFFFFF, 0x800u);
    if ( v18 )
    {
      SCardError = _MakeSCardError(v18);
      goto LABEL_45;
    }
    if ( pHandle )
    {
      MesHandleFree(pHandle);
      pHandle = 0;
    }
    if ( !MesDecodeBufferHandleCreate(*((char **)v31 + 2), *((_DWORD *)v31 + 7), &pHandle) )
    {
      v33 = 0;
      *(_OWORD *)dwBytes = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Fu, &v33);
      SCardError = v33;
      v29 = v33;
      if ( (_DWORD)v33 )
      {
LABEL_44:
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Fu, &v33);
        goto LABEL_45;
      }
      if ( v14 )
      {
        v19 = *((_QWORD *)&v33 + 1);
        if ( *((_QWORD *)&v33 + 1) )
        {
          v14->dwProtocol = **((_DWORD **)&v33 + 1);
          if ( *(_DWORD *)(v19 + 4) )
          {
            v20 = *(unsigned int *)(v19 + 4);
            if ( v20 <= (unsigned __int64)a2->cbPciLength - 8 )
              memcpy_0(&v14[1], *(const void **)(v19 + 8), v20);
          }
        }
      }
      v21 = LODWORD(dwBytes[0]);
      v22 = (const void *)dwBytes[1];
      v23 = *(LPCRITICAL_SECTION **)a1;
      v24 = *v17;
      *v17 = dwBytes[0];
      if ( v22 && v16 )
      {
        if ( v24 == -1 )
        {
          if ( v23 )
            ProcessHeap = v23[3];
          else
            ProcessHeap = (LPCRITICAL_SECTION)GetProcessHeap();
          v26 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, v21);
          *(_QWORD *)v16 = v26;
          if ( !v26 )
          {
            SCardError = -2146435066;
            goto LABEL_43;
          }
          v27 = v26;
        }
        else
        {
          if ( v24 < (unsigned int)v21 )
          {
            SCardError = -2146435064;
LABEL_43:
            v29 = SCardError;
            goto LABEL_44;
          }
          v27 = v16;
        }
        memcpy_0(v27, v22, v21);
      }
      SCardError = 0;
      goto LABEL_43;
    }
  }
  SCardError = -2146435041;
LABEL_45:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  MIDL_user_free(pBuffer);
  if ( v31 )
    *((_DWORD *)v31 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18000396c  mov     rax, rsp
0x18000396f  push    rsi
0x180003970  push    rdi
0x180003971  push    r12
0x180003973  push    r13
0x180003975  push    r14
0x180003977  push    r15
0x180003979  sub     rsp, 0E8h
0x180003980  mov     edi, r9d
0x180003983  mov     rsi, r8
0x180003986  mov     r14, rdx
0x180003989  mov     r12, rcx
0x18000398c  mov     [rsp+118h+pBuffer], 0
0x180003995  mov     dword ptr [rax+8], 0
0x18000399c  mov     [rsp+118h+pHandle], 0
0x1800039a5  mov     [rsp+118h+var_C0], 0
0x1800039ae  xor     edx, edx; Val
0x1800039b0  lea     r8d, [rdx+50h]; Size
0x1800039b4  lea     rcx, [rax-88h]; void *
0x1800039bb  call    memset_0
0x1800039c0  xorps   xmm0, xmm0
0x1800039c3  movups  [rsp+118h+var_A8], xmm0
0x1800039c8  movups  xmmword ptr [rsp+118h+dwBytes], xmm0
0x1800039d0  movups  [rsp+118h+var_B8], xmm0
0x1800039d5  test    r12, r12
0x1800039d8  jnz     short loc_1800039E4
0x1800039da  mov     eax, 80100004h
0x1800039df  jmp     loc_180003DC6
0x1800039e4  lea     r8, [rsp+118h+pHandle]; pHandle
0x1800039e9  lea     rdx, [rsp+118h+pEncodedSize]; pEncodedSize
0x1800039f1  lea     rcx, [rsp+118h+pBuffer]; pBuffer
0x1800039f6  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x1800039fc  test    eax, eax
0x1800039fe  jz      short loc_180003A0A
0x180003a00  mov     edi, 8010001Fh
0x180003a05  jmp     loc_180003D90
0x180003a0a  movups  xmm0, xmmword ptr [r12+8]
0x180003a10  movaps  [rsp+118h+var_88], xmm0
0x180003a18  movups  xmm1, xmmword ptr [r12+18h]
0x180003a1e  movaps  [rsp+118h+var_78], xmm1
0x180003a26  mov     eax, [r14]
0x180003a29  mov     [rsp+118h+var_68], eax
0x180003a30  mov     eax, [r14+4]
0x180003a34  cmp     eax, 8
0x180003a37  jnb     short loc_180003A43
0x180003a39  mov     edi, 80100004h
0x180003a3e  jmp     loc_180003D90
0x180003a43  add     eax, 0FFFFFFF8h
0x180003a46  mov     [rsp+118h+var_64], eax
0x180003a4d  jz      short loc_180003A5D
0x180003a4f  lea     rax, [r14+8]
0x180003a53  mov     [rsp+118h+var_60], rax
0x180003a5b  jmp     short loc_180003A69
0x180003a5d  mov     [rsp+118h+var_60], 0
0x180003a69  mov     [rsp+118h+var_58], edi
0x180003a70  mov     [rsp+118h+var_50], rsi
0x180003a78  mov     rsi, [rsp+118h+arg_20]
0x180003a80  test    rsi, rsi
0x180003a83  jz      short loc_180003AC9
0x180003a85  lea     rax, [rsp+118h+var_B8]
0x180003a8a  mov     [rsp+118h+var_48], rax
0x180003a92  mov     eax, [rsi]
0x180003a94  mov     dword ptr [rsp+118h+var_B8], eax
0x180003a98  mov     eax, [rsi+4]
0x180003a9b  cmp     eax, 8
0x180003a9e  jnb     short loc_180003AAA
0x180003aa0  mov     edi, 80100019h
0x180003aa5  jmp     loc_180003D90
0x180003aaa  add     eax, 0FFFFFFF8h
0x180003aad  mov     dword ptr [rsp+118h+var_B8+4], eax
0x180003ab1  jz      short loc_180003ABE
0x180003ab3  lea     rax, [rsi+8]
0x180003ab7  mov     qword ptr [rsp+118h+var_B8+8], rax
0x180003abc  jmp     short loc_180003AD5
0x180003abe  mov     qword ptr [rsp+118h+var_B8+8], 0
0x180003ac7  jmp     short loc_180003AD5
0x180003ac9  mov     [rsp+118h+var_48], 0
0x180003ad5  xor     eax, eax
0x180003ad7  mov     r15, [rsp+118h+arg_28]
0x180003adf  test    r15, r15
0x180003ae2  setz    al
0x180003ae5  mov     [rsp+118h+var_40], eax
0x180003aec  mov     r13, [rsp+118h+arg_30]
0x180003af4  mov     eax, [r13+0]
0x180003af8  mov     [rsp+118h+var_3C], eax
0x180003aff  lea     rax, [rsp+118h+var_88]
0x180003b07  mov     [rsp+118h+pObject], rax; pObject
0x180003b0c  mov     [rsp+118h+nTypeIndex], 1Eh; nTypeIndex
0x180003b14  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180003b1b  lea     r8, pProxyInfo; pProxyInfo
0x180003b22  lea     rdx, pPicklingInfo; pPicklingInfo
0x180003b29  mov     rcx, [rsp+118h+pHandle]; Handle
0x180003b2e  call    cs:__imp_NdrMesTypeEncode3
0x180003b34  nop
0x180003b35  mov     rax, [r12]
0x180003b39  mov     [rsp+118h+var_E8], 800h; unsigned int
0x180003b41  mov     dword ptr [rsp+118h+pObject], 0FFFFFFFFh; dwMilliseconds
0x180003b49  mov     rax, [rax]
0x180003b4c  mov     qword ptr [rsp+118h+nTypeIndex], rax; lpCriticalSection
0x180003b51  lea     r9, [rsp+118h+var_C0]; struct _BUFFER_LIST_STRUCT **
0x180003b56  mov     r8d, [rsp+118h+pEncodedSize]; InputBufferLength
0x180003b5e  mov     rdx, [rsp+118h+pBuffer]; InputBuffer
0x180003b63  mov     ecx, 900D0h; IoControlCode
0x180003b68  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x180003b6d  test    eax, eax
0x180003b6f  jz      short loc_180003B7F
0x180003b71  mov     ecx, eax; int
0x180003b73  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x180003b78  mov     edi, eax
0x180003b7a  jmp     loc_180003D90
0x180003b7f  mov     rcx, [rsp+118h+pHandle]; Handle
0x180003b84  test    rcx, rcx
0x180003b87  jz      short loc_180003B98
0x180003b89  call    cs:__imp_MesHandleFree
0x180003b8f  mov     [rsp+118h+pHandle], 0
0x180003b98  lea     r8, [rsp+118h+pHandle]; pHandle
0x180003b9d  mov     rcx, [rsp+118h+var_C0]
0x180003ba2  mov     edx, [rcx+1Ch]; BufferSize
0x180003ba5  mov     rcx, [rcx+10h]; Buffer
0x180003ba9  call    cs:__imp_MesDecodeBufferHandleCreate
0x180003baf  test    eax, eax
0x180003bb1  jnz     loc_180003A00
0x180003bb7  xorps   xmm0, xmm0
0x180003bba  movups  [rsp+118h+var_A8], xmm0
0x180003bbf  movups  xmmword ptr [rsp+118h+dwBytes], xmm0
0x180003bc7  lea     rax, [rsp+118h+var_A8]
0x180003bcc  mov     [rsp+118h+pObject], rax; pObject
0x180003bd1  mov     [rsp+118h+nTypeIndex], 1Fh; nTypeIndex
0x180003bd9  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180003be0  lea     r8, pProxyInfo; pProxyInfo
0x180003be7  lea     rdx, pPicklingInfo; pPicklingInfo
0x180003bee  mov     rcx, [rsp+118h+pHandle]; Handle
0x180003bf3  call    cs:__imp_NdrMesTypeDecode3
0x180003bf9  nop
0x180003bfa  mov     edi, dword ptr [rsp+118h+var_A8]
0x180003bfe  mov     [rsp+118h+var_D0], edi
0x180003c02  test    edi, edi
0x180003c04  jnz     loc_180003CC5
0x180003c0a  test    rsi, rsi
0x180003c0d  jz      short loc_180003C40
0x180003c0f  mov     rdx, qword ptr [rsp+118h+var_A8+8]
0x180003c14  test    rdx, rdx
0x180003c17  jz      short loc_180003C40
0x180003c19  mov     eax, [rdx]
0x180003c1b  mov     [rsi], eax
0x180003c1d  cmp     [rdx+4], edi
0x180003c20  jz      short loc_180003C40
0x180003c22  mov     r8d, [rdx+4]; Size
0x180003c26  mov     eax, [r14+4]
0x180003c2a  sub     rax, 8
0x180003c2e  cmp     r8, rax
0x180003c31  ja      short loc_180003C40
0x180003c33  lea     rcx, [rsi+8]; void *
0x180003c37  mov     rdx, [rdx+8]; Src
0x180003c3b  call    memcpy_0
0x180003c40  mov     edi, dword ptr [rsp+118h+dwBytes]
0x180003c47  mov     rsi, [rsp+118h+dwBytes+8]
0x180003c4f  mov     rcx, [r12]
0x180003c53  mov     eax, [r13+0]
0x180003c57  mov     [r13+0], edi
0x180003c5b  test    rsi, rsi
0x180003c5e  jz      short loc_180003CBF
0x180003c60  test    r15, r15
0x180003c63  jz      short loc_180003CBF
0x180003c65  or      edx, 0FFFFFFFFh
0x180003c68  cmp     eax, edx
0x180003c6a  jz      short loc_180003C7B
0x180003c6c  cmp     eax, edi
0x180003c6e  jnb     short loc_180003C77
0x180003c70  mov     edi, 80100008h
0x180003c75  jmp     short loc_180003CC1
0x180003c77  cmp     eax, edx
0x180003c79  jnz     short loc_180003CB1
0x180003c7b  test    rcx, rcx
0x180003c7e  jz      short loc_180003C86
0x180003c80  mov     rax, [rcx+18h]
0x180003c84  jmp     short loc_180003C8C
0x180003c86  call    cs:__imp_GetProcessHeap
0x180003c8c  mov     r8, rdi; dwBytes
0x180003c8f  mov     edx, 8; dwFlags
0x180003c94  mov     rcx, rax; hHeap
0x180003c97  call    cs:__imp_HeapAlloc
0x180003c9d  mov     [r15], rax
0x180003ca0  test    rax, rax
0x180003ca3  jz      short loc_180003CAA
0x180003ca5  mov     rcx, rax
0x180003ca8  jmp     short loc_180003CB4
0x180003caa  mov     edi, 80100006h
0x180003caf  jmp     short loc_180003CC1
0x180003cb1  mov     rcx, r15; void *
0x180003cb4  mov     r8, rdi; Size
0x180003cb7  mov     rdx, rsi; Src
0x180003cba  call    memcpy_0
0x180003cbf  xor     edi, edi
0x180003cc1  mov     [rsp+118h+var_D0], edi
0x180003cc5  lea     rax, [rsp+118h+var_A8]
0x180003cca  mov     [rsp+118h+pObject], rax; pObject
0x180003ccf  mov     [rsp+118h+nTypeIndex], 1Fh; nTypeIndex
0x180003cd7  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180003cde  lea     r8, pProxyInfo; pProxyInfo
0x180003ce5  lea     rdx, pPicklingInfo; pPicklingInfo
0x180003cec  mov     rcx, [rsp+118h+pHandle]; Handle
0x180003cf1  call    cs:__imp_NdrMesTypeFree3
0x180003cf7  jmp     loc_180003D90
0x180003cfc  mov     edi, [rsp+118h+var_D0]
0x180003d00  jmp     loc_180003D90
0x180003d05  mov     edi, eax
0x180003d07  mov     edx, 2
0x180003d0c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180003d11  lea     rax, WPP_GLOBAL_Control
0x180003d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d1f  cmp     rcx, rax
0x180003d22  jz      short loc_180003D49
0x180003d24  test    byte ptr [rcx+1Ch], 8
0x180003d28  jz      short loc_180003D49
0x180003d2a  cmp     byte ptr [rcx+19h], 2
0x180003d2e  jb      short loc_180003D49
0x180003d30  mov     edx, 49h ; 'I'
0x180003d35  mov     [rsp+118h+nTypeIndex], edi
0x180003d39  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180003d40  mov     rcx, [rcx+10h]
0x180003d44  call    WPP_SF_sd
0x180003d49  jmp     short loc_180003D90
0x180003d4b  mov     edi, eax
0x180003d4d  mov     edx, 2
0x180003d52  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180003d57  lea     rax, WPP_GLOBAL_Control
0x180003d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d65  cmp     rcx, rax
0x180003d68  jz      short loc_180003D90
0x180003d6a  test    byte ptr [rcx+1Ch], 8
0x180003d6e  jz      short loc_180003D90
0x180003d70  cmp     byte ptr [rcx+19h], 2
0x180003d74  jb      short loc_180003D90
0x180003d76  mov     edx, 48h ; 'H'
0x180003d7b  mov     [rsp+118h+nTypeIndex], edi
0x180003d7f  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180003d86  mov     rcx, [rcx+10h]
0x180003d8a  call    WPP_SF_sd
0x180003d8f  nop
0x180003d90  mov     rcx, [rsp+118h+pHandle]; Handle
0x180003d95  test    rcx, rcx
0x180003d98  jz      short loc_180003DA9
0x180003d9a  call    cs:__imp_MesHandleFree
0x180003da0  mov     [rsp+118h+pHandle], 0
0x180003da9  mov     rcx, [rsp+118h+pBuffer]; void *
0x180003dae  call    MIDL_user_free
0x180003db3  mov     rax, [rsp+118h+var_C0]
0x180003db8  test    rax, rax
0x180003dbb  jz      short loc_180003DC4
0x180003dbd  mov     dword ptr [rax+8], 0
0x180003dc4  mov     eax, edi
0x180003dc6  add     rsp, 0E8h
0x180003dcd  pop     r15
0x180003dcf  pop     r14
0x180003dd1  pop     r13
0x180003dd3  pop     r12
0x180003dd5  pop     rdi
0x180003dd6  pop     rsi
0x180003dd7  retn
```
