# I_SCardListReaderGroups(unsigned __int64,uchar *,ulong *,int)

- ea: `0x18002ba08`
- end: `0x18002bd58`
- name: `?I_SCardListReaderGroups@@YAJ_KPEAEPEAKH@Z`
- size: `848`
- prototype: `__int64 __fastcall(struct _REDIR_LOCAL_SCARDCONTEXT *, unsigned __int8 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180026190`
- `0x180028000`

## callees

- `0x18000605c`
- `0x180006c80`
- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x180016ef0`
- `0x18001991c`
- `0x180019a14`
- `0x18002ba08`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002bbe5`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002bbe5`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002bb38`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002bb38`
- `RPCRT4!NdrMesTypeFree3` at `0x18002bc4e`
- `RPCRT4!NdrMesTypeFree3` at `0x18002bc4e`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002ba87`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002ba87`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002bba3`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002bba3`

## pseudocode

```c
__int64 __fastcall I_SCardListReaderGroups(
        struct _REDIR_LOCAL_SCARDCONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        int a4)
{
  unsigned int SCardError; // ebx
  int v10; // eax
  handle_t pHandle; // [rsp+48h] [rbp-60h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-58h] BYREF
  char *pBuffer; // [rsp+58h] [rbp-50h] BYREF
  struct _BUFFER_LIST_STRUCT *v14; // [rsp+60h] [rbp-48h] BYREF
  unsigned __int8 *v15[2]; // [rsp+68h] [rbp-40h] BYREF
  __int128 pObject; // [rsp+78h] [rbp-30h] BYREF
  __int64 v17; // [rsp+88h] [rbp-20h]
  unsigned int pEncodedSize; // [rsp+C0h] [rbp+18h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v14 = 0;
  pObject = 0;
  v17 = 0;
  *(_OWORD *)v15 = 0;
  lpCriticalSection = 0;
  if ( !a3 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    if ( a1 )
    {
      pObject = *(_OWORD *)((char *)a1 + 8);
      lpCriticalSection = *(LPCRITICAL_SECTION *)a1;
    }
    else
    {
      *((_QWORD *)&pObject + 1) = 0;
      LODWORD(pObject) = 0;
      v10 = RedirectionContextLookup(&lpCriticalSection);
      if ( v10 )
        goto LABEL_8;
    }
    LODWORD(v17) = a2 == 0;
    HIDWORD(v17) = *a3;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0xAu, &pObject);
    v10 = _SendSCardIOCTL(a4 != 0 ? 589860 : 589856, pBuffer, pEncodedSize, &v14, lpCriticalSection, 0xFFFFFFFF, 0x800u);
    if ( !v10 )
    {
      SafeMesHandleFree(&pHandle);
      if ( !MesDecodeBufferHandleCreate(*((char **)v14 + 2), *((_DWORD *)v14 + 7), &pHandle) )
      {
        *(_OWORD *)v15 = 0;
        NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, v15);
        SCardError = (unsigned int)v15[0];
        if ( !LODWORD(v15[0]) )
          SCardError = _CopyReturnToCallerBuffer(a1, v15[1], HIDWORD(v15[0]), a2, a3, (a4 != 0) + 2);
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, v15);
        goto LABEL_14;
      }
      goto LABEL_4;
    }
LABEL_8:
    SCardError = _MakeSCardError(v10);
    goto LABEL_14;
  }
LABEL_4:
  SCardError = -2146435041;
LABEL_14:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v14 )
    *((_DWORD *)v14 + 2) = 0;
  if ( !a1 )
  {
    if ( lpCriticalSection )
      RedirectionContextRelease((struct _REDIRECTION_CONTEXT *)lpCriticalSection);
  }
  return SCardError;
}

```

## disassembly

```asm
0x18002ba08  mov     r11, rsp
0x18002ba0b  mov     [r11+10h], rbx
0x18002ba0f  mov     [r11+20h], rsi
0x18002ba13  mov     [r11+8], rcx
0x18002ba17  push    rdi
0x18002ba18  push    r14
0x18002ba1a  push    r15
0x18002ba1c  sub     rsp, 90h
0x18002ba23  mov     r15d, r9d
0x18002ba26  mov     rsi, r8
0x18002ba29  mov     r14, rdx
0x18002ba2c  mov     rdi, rcx
0x18002ba2f  mov     qword ptr [r11-50h], 0
0x18002ba37  mov     dword ptr [r11+18h], 0
0x18002ba3f  mov     qword ptr [r11-60h], 0
0x18002ba47  mov     qword ptr [r11-48h], 0
0x18002ba4f  xorps   xmm0, xmm0
0x18002ba52  xor     eax, eax
0x18002ba54  movups  [rsp+0A8h+var_30], xmm0
0x18002ba59  mov     [r11-20h], rax
0x18002ba5d  movups  xmmword ptr [rsp+0A8h+var_40], xmm0
0x18002ba62  mov     [r11-58h], rax
0x18002ba66  test    r8, r8
0x18002ba69  jnz     short loc_18002BA75
0x18002ba6b  mov     eax, 80100004h
0x18002ba70  jmp     loc_18002BD3F
0x18002ba75  lea     r8, [rsp+0A8h+pHandle]; pHandle
0x18002ba7a  lea     rdx, [rsp+0A8h+pEncodedSize]; pEncodedSize
0x18002ba82  lea     rcx, [rsp+0A8h+pBuffer]; pBuffer
0x18002ba87  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002ba8d  test    eax, eax
0x18002ba8f  jz      short loc_18002BA9B
0x18002ba91  mov     ebx, 8010001Fh
0x18002ba96  jmp     loc_18002BD04
0x18002ba9b  test    rdi, rdi
0x18002ba9e  jz      short loc_18002BAC4
0x18002baa0  mov     eax, [rdi+8]
0x18002baa3  mov     dword ptr [rsp+0A8h+var_30], eax
0x18002baa7  mov     eax, [rdi+0Ch]
0x18002baaa  mov     dword ptr [rsp+0A8h+var_30+4], eax
0x18002baae  mov     rax, [rdi+10h]
0x18002bab2  mov     qword ptr [rsp+0A8h+var_30+8], rax
0x18002baba  mov     rax, [rdi]
0x18002babd  mov     [rsp+0A8h+lpCriticalSection], rax
0x18002bac2  jmp     short loc_18002BAF4
0x18002bac4  mov     qword ptr [rsp+0A8h+var_30+8], 0
0x18002bad0  mov     dword ptr [rsp+0A8h+var_30], 0
0x18002bad8  lea     rcx, [rsp+0A8h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x18002badd  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x18002bae2  test    eax, eax
0x18002bae4  jz      short loc_18002BAF4
0x18002bae6  mov     ecx, eax; int
0x18002bae8  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002baed  mov     ebx, eax
0x18002baef  jmp     loc_18002BD04
0x18002baf4  xor     eax, eax
0x18002baf6  test    r14, r14
0x18002baf9  setz    al
0x18002bafc  mov     [rsp+0A8h+var_20], eax
0x18002bb03  mov     eax, [rsi]
0x18002bb05  mov     [rsp+0A8h+var_1C], eax
0x18002bb0c  lea     rax, [rsp+0A8h+var_30]
0x18002bb11  mov     [rsp+0A8h+pObject], rax; pObject
0x18002bb16  mov     [rsp+0A8h+nTypeIndex], 0Ah; nTypeIndex
0x18002bb1e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002bb25  lea     r8, pProxyInfo; pProxyInfo
0x18002bb2c  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002bb33  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x18002bb38  call    cs:__imp_NdrMesTypeEncode3
0x18002bb3e  nop
0x18002bb3f  mov     eax, r15d
0x18002bb42  neg     eax
0x18002bb44  sbb     ecx, ecx
0x18002bb46  and     ecx, 4
0x18002bb49  add     ecx, 90020h; IoControlCode
0x18002bb4f  mov     [rsp+0A8h+var_78], 800h; unsigned int
0x18002bb57  mov     dword ptr [rsp+0A8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002bb5f  mov     rax, [rsp+0A8h+lpCriticalSection]
0x18002bb64  mov     qword ptr [rsp+0A8h+nTypeIndex], rax; lpCriticalSection
0x18002bb69  lea     r9, [rsp+0A8h+var_48]; struct _BUFFER_LIST_STRUCT **
0x18002bb6e  mov     r8d, [rsp+0A8h+pEncodedSize]; InputBufferLength
0x18002bb76  mov     rdx, [rsp+0A8h+pBuffer]; InputBuffer
0x18002bb7b  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002bb80  test    eax, eax
0x18002bb82  jnz     loc_18002BAE6
0x18002bb88  lea     rcx, [rsp+0A8h+pHandle]; void **
0x18002bb8d  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002bb92  lea     r8, [rsp+0A8h+pHandle]; pHandle
0x18002bb97  mov     rcx, [rsp+0A8h+var_48]
0x18002bb9c  mov     edx, [rcx+1Ch]; BufferSize
0x18002bb9f  mov     rcx, [rcx+10h]; Buffer
0x18002bba3  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002bba9  test    eax, eax
0x18002bbab  jnz     loc_18002BA91
0x18002bbb1  xorps   xmm0, xmm0
0x18002bbb4  movups  xmmword ptr [rsp+0A8h+var_40], xmm0
0x18002bbb9  lea     rax, [rsp+0A8h+var_40]
0x18002bbbe  mov     [rsp+0A8h+pObject], rax; pObject
0x18002bbc3  mov     [rsp+0A8h+nTypeIndex], 1; nTypeIndex
0x18002bbcb  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002bbd2  lea     r8, pProxyInfo; pProxyInfo
0x18002bbd9  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002bbe0  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x18002bbe5  call    cs:__imp_NdrMesTypeDecode3
0x18002bbeb  nop
0x18002bbec  mov     ebx, dword ptr [rsp+0A8h+var_40]
0x18002bbf0  test    ebx, ebx
0x18002bbf2  jnz     short loc_18002BC1E
0x18002bbf4  neg     r15d
0x18002bbf7  sbb     eax, eax
0x18002bbf9  neg     eax
0x18002bbfb  add     eax, 2
0x18002bbfe  mov     dword ptr [rsp+0A8h+pObject], eax; unsigned int
0x18002bc02  mov     qword ptr [rsp+0A8h+nTypeIndex], rsi; unsigned int *
0x18002bc07  mov     r9, r14; unsigned __int8 *
0x18002bc0a  mov     r8d, dword ptr [rsp+0A8h+var_40+4]; unsigned int
0x18002bc0f  mov     rdx, [rsp+0A8h+var_40+8]; unsigned __int8 *
0x18002bc14  mov     rcx, rdi; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18002bc17  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x18002bc1c  mov     ebx, eax
0x18002bc1e  mov     [rsp+0A8h+var_68], ebx
0x18002bc22  lea     rax, [rsp+0A8h+var_40]
0x18002bc27  mov     [rsp+0A8h+pObject], rax; pObject
0x18002bc2c  mov     [rsp+0A8h+nTypeIndex], 1; nTypeIndex
0x18002bc34  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002bc3b  lea     r8, pProxyInfo; pProxyInfo
0x18002bc42  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002bc49  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x18002bc4e  call    cs:__imp_NdrMesTypeFree3
0x18002bc54  jmp     loc_18002BD04
0x18002bc59  mov     rdi, [rsp+0A8h+arg_0]
0x18002bc61  mov     ebx, [rsp+0A8h+var_68]
0x18002bc65  jmp     loc_18002BD04
0x18002bc6a  mov     ebx, eax
0x18002bc6c  mov     edx, 2
0x18002bc71  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002bc76  lea     rax, WPP_GLOBAL_Control
0x18002bc7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc84  cmp     rcx, rax
0x18002bc87  jz      short loc_18002BCAE
0x18002bc89  test    byte ptr [rcx+1Ch], 8
0x18002bc8d  jz      short loc_18002BCAE
0x18002bc8f  cmp     byte ptr [rcx+19h], 2
0x18002bc93  jb      short loc_18002BCAE
0x18002bc95  mov     edx, 29h ; ')'
0x18002bc9a  mov     [rsp+0A8h+nTypeIndex], ebx
0x18002bc9e  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002bca5  mov     rcx, [rcx+10h]
0x18002bca9  call    WPP_SF_sd
0x18002bcae  mov     rdi, [rsp+0A8h+arg_0]
0x18002bcb6  jmp     short loc_18002BD04
0x18002bcb8  mov     ebx, eax
0x18002bcba  mov     edx, 2
0x18002bcbf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002bcc4  lea     rax, WPP_GLOBAL_Control
0x18002bccb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcd2  cmp     rcx, rax
0x18002bcd5  jz      short loc_18002BCFC
0x18002bcd7  test    byte ptr [rcx+1Ch], 8
0x18002bcdb  jz      short loc_18002BCFC
0x18002bcdd  cmp     byte ptr [rcx+19h], 2
0x18002bce1  jb      short loc_18002BCFC
0x18002bce3  mov     edx, 28h ; '('
0x18002bce8  mov     [rsp+0A8h+nTypeIndex], ebx
0x18002bcec  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002bcf3  mov     rcx, [rcx+10h]
0x18002bcf7  call    WPP_SF_sd
0x18002bcfc  mov     rdi, [rsp+0A8h+arg_0]
0x18002bd04  lea     rcx, [rsp+0A8h+pHandle]; void **
0x18002bd09  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002bd0e  mov     rcx, [rsp+0A8h+pBuffer]; void *
0x18002bd13  call    MIDL_user_free
0x18002bd18  mov     rax, [rsp+0A8h+var_48]
0x18002bd1d  test    rax, rax
0x18002bd20  jz      short loc_18002BD29
0x18002bd22  mov     dword ptr [rax+8], 0
0x18002bd29  test    rdi, rdi
0x18002bd2c  jnz     short loc_18002BD3D
0x18002bd2e  mov     rcx, [rsp+0A8h+lpCriticalSection]; struct _REDIRECTION_CONTEXT *
0x18002bd33  test    rcx, rcx
0x18002bd36  jz      short loc_18002BD3D
0x18002bd38  call    ?RedirectionContextRelease@@YAKPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextRelease(_REDIRECTION_CONTEXT *)
0x18002bd3d  mov     eax, ebx
0x18002bd3f  lea     r11, [rsp+0A8h+var_18]
0x18002bd47  mov     rbx, [r11+28h]
0x18002bd4b  mov     rsi, [r11+38h]
0x18002bd4f  mov     rsp, r11
0x18002bd52  pop     r15
0x18002bd54  pop     r14
0x18002bd56  pop     rdi
0x18002bd57  retn
```
