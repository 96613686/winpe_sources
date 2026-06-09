# RedirectedSCardLocateCardsA(unsigned __int64,char const *,SCARD_READERSTATEA *,ulong)

- ea: `0x18002cc68`
- end: `0x18002cf5e`
- name: `?RedirectedSCardLocateCardsA@@YAJ_KPEBDPEAUSCARD_READERSTATEA@@K@Z`
- size: `758`
- prototype: `int(unsigned __int64, const char *, struct SCARD_READERSTATEA *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180026640`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x1800127cc`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002cc68`
- `0x18002e1e4`
- `0x18002e29c`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002ce2c`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002ce2c`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002cd81`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002cd81`
- `RPCRT4!NdrMesTypeFree3` at `0x18002ce81`
- `RPCRT4!NdrMesTypeFree3` at `0x18002ce81`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002ccef`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002ccef`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002cde9`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002cde9`

## pseudocode

```c
__int64 __fastcall RedirectedSCardLocateCardsA(
        __int64 a1,
        const char *a2,
        struct SCARD_READERSTATEW *a3,
        unsigned int a4)
{
  unsigned int SCardError; // ebx
  int v10; // eax
  handle_t pHandle; // [rsp+40h] [rbp-98h] BYREF
  int v12; // [rsp+48h] [rbp-90h]
  char *pBuffer; // [rsp+50h] [rbp-88h] BYREF
  struct _ReaderStateW *v14; // [rsp+58h] [rbp-80h] BYREF
  struct _BUFFER_LIST_STRUCT *v15; // [rsp+60h] [rbp-78h] BYREF
  struct _ReaderState_Return *v16[2]; // [rsp+68h] [rbp-70h] BYREF
  __int128 pObject; // [rsp+78h] [rbp-60h] BYREF
  __int128 v18; // [rsp+88h] [rbp-50h]
  __int128 v19; // [rsp+98h] [rbp-40h]
  unsigned int pEncodedSize; // [rsp+E0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  pObject = 0;
  v18 = 0;
  v19 = 0;
  *(_OWORD *)v16 = 0;
  v14 = 0;
  v15 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !a2 )
    return 2148532241LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    LODWORD(v18) = _CalculateNumBytesInMultiStringA(a2);
    *((_QWORD *)&v18 + 1) = a2;
    LODWORD(v19) = a4;
    if ( (unsigned int)_AllocAndCopyReaderStateWStructsForCall(a4, &v14, a3) )
    {
      SCardError = -2146435066;
      goto LABEL_16;
    }
    *((_QWORD *)&v19 + 1) = v14;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0xCu, &pObject);
    v10 = _SendSCardIOCTL(0x90098u, pBuffer, pEncodedSize, &v15, *(LPCRITICAL_SECTION *)a1, 0xFFFFFFFF, 0x800u);
    if ( v10 )
    {
      SCardError = _MakeSCardError(v10);
      goto LABEL_16;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v15 + 2), *((_DWORD *)v15 + 7), &pHandle) )
    {
      *(_OWORD *)v16 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x10u, v16);
      SCardError = (unsigned int)v16[0];
      v12 = (int)v16[0];
      if ( LODWORD(v16[0]) )
      {
LABEL_15:
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x10u, v16);
        goto LABEL_16;
      }
      if ( a4 == HIDWORD(v16[0]) )
      {
        _CopyReaderStateWStructsForReturn(a4, a3, v16[1]);
        goto LABEL_15;
      }
    }
  }
  SCardError = -2146435041;
LABEL_16:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  MIDL_user_free(v14);
  if ( v15 )
    *((_DWORD *)v15 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002cc68  mov     rax, rsp
0x18002cc6b  push    rbx
0x18002cc6c  push    rsi
0x18002cc6d  push    rdi
0x18002cc6e  push    r14
0x18002cc70  sub     rsp, 0B8h
0x18002cc77  mov     edi, r9d
0x18002cc7a  mov     r14, r8
0x18002cc7d  mov     rbx, rdx
0x18002cc80  mov     rsi, rcx
0x18002cc83  mov     [rsp+0D8h+pBuffer], 0
0x18002cc8c  mov     dword ptr [rax+8], 0
0x18002cc93  mov     [rsp+0D8h+pHandle], 0
0x18002cc9c  xorps   xmm0, xmm0
0x18002cc9f  movups  xmmword ptr [rax-60h], xmm0
0x18002cca3  movups  xmmword ptr [rax-50h], xmm0
0x18002cca7  movups  xmmword ptr [rax-40h], xmm0
0x18002ccab  movups  xmmword ptr [rax-70h], xmm0
0x18002ccaf  mov     qword ptr [rax-80h], 0
0x18002ccb7  mov     qword ptr [rax-78h], 0
0x18002ccbf  test    rcx, rcx
0x18002ccc2  jnz     short loc_18002CCCE
0x18002ccc4  mov     eax, 80100004h
0x18002ccc9  jmp     loc_18002CF51
0x18002ccce  test    rbx, rbx
0x18002ccd1  jnz     short loc_18002CCDD
0x18002ccd3  mov     eax, 80100011h
0x18002ccd8  jmp     loc_18002CF51
0x18002ccdd  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x18002cce2  lea     rdx, [rsp+0D8h+pEncodedSize]; pEncodedSize
0x18002ccea  lea     rcx, [rsp+0D8h+pBuffer]; pBuffer
0x18002ccef  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002ccf5  test    eax, eax
0x18002ccf7  jz      short loc_18002CD03
0x18002ccf9  mov     ebx, 8010001Fh
0x18002ccfe  jmp     loc_18002CF20
0x18002cd03  movups  xmm0, xmmword ptr [rsi+8]
0x18002cd07  movdqu  [rsp+0D8h+var_60], xmm0
0x18002cd0d  mov     rcx, rbx; char *
0x18002cd10  call    ?_CalculateNumBytesInMultiStringA@@YAKPEBD@Z; _CalculateNumBytesInMultiStringA(char const *)
0x18002cd15  mov     [rsp+0D8h+var_50], eax
0x18002cd1c  mov     [rsp+0D8h+var_48], rbx
0x18002cd24  mov     [rsp+0D8h+var_40], edi
0x18002cd2b  mov     r8, r14; struct SCARD_READERSTATEW *
0x18002cd2e  lea     rdx, [rsp+0D8h+var_80]; struct _ReaderStateW **
0x18002cd33  mov     ecx, edi; unsigned int
0x18002cd35  call    ?_AllocAndCopyReaderStateWStructsForCall@@YAJKPEAPEAU_ReaderStateW@@PEAUSCARD_READERSTATEW@@@Z; _AllocAndCopyReaderStateWStructsForCall(ulong,_ReaderStateW * *,SCARD_READERSTATEW *)
0x18002cd3a  test    eax, eax
0x18002cd3c  jz      short loc_18002CD48
0x18002cd3e  mov     ebx, 80100006h
0x18002cd43  jmp     loc_18002CF20
0x18002cd48  mov     rax, [rsp+0D8h+var_80]
0x18002cd4d  mov     [rsp+0D8h+var_38], rax
0x18002cd55  lea     rax, [rsp+0D8h+var_60]
0x18002cd5a  mov     [rsp+0D8h+pObject], rax; pObject
0x18002cd5f  mov     [rsp+0D8h+nTypeIndex], 0Ch; nTypeIndex
0x18002cd67  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002cd6e  lea     r8, pProxyInfo; pProxyInfo
0x18002cd75  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002cd7c  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002cd81  call    cs:__imp_NdrMesTypeEncode3
0x18002cd87  nop
0x18002cd88  mov     [rsp+0D8h+var_A8], 800h; unsigned int
0x18002cd90  mov     dword ptr [rsp+0D8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002cd98  mov     rax, [rsi]
0x18002cd9b  mov     qword ptr [rsp+0D8h+nTypeIndex], rax; lpCriticalSection
0x18002cda0  lea     r9, [rsp+0D8h+var_78]; struct _BUFFER_LIST_STRUCT **
0x18002cda5  mov     r8d, [rsp+0D8h+pEncodedSize]; InputBufferLength
0x18002cdad  mov     rdx, [rsp+0D8h+pBuffer]; InputBuffer
0x18002cdb2  mov     ecx, 90098h; IoControlCode
0x18002cdb7  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002cdbc  test    eax, eax
0x18002cdbe  jz      short loc_18002CDCE
0x18002cdc0  mov     ecx, eax; int
0x18002cdc2  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002cdc7  mov     ebx, eax
0x18002cdc9  jmp     loc_18002CF20
0x18002cdce  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002cdd3  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002cdd8  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x18002cddd  mov     rcx, [rsp+0D8h+var_78]
0x18002cde2  mov     edx, [rcx+1Ch]; BufferSize
0x18002cde5  mov     rcx, [rcx+10h]; Buffer
0x18002cde9  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002cdef  test    eax, eax
0x18002cdf1  jnz     loc_18002CCF9
0x18002cdf7  xorps   xmm0, xmm0
0x18002cdfa  movups  xmmword ptr [rsp+0D8h+var_70], xmm0
0x18002cdff  lea     rax, [rsp+0D8h+var_70]
0x18002ce04  mov     [rsp+0D8h+pObject], rax; pObject
0x18002ce09  mov     esi, 10h
0x18002ce0e  mov     [rsp+0D8h+nTypeIndex], esi; nTypeIndex
0x18002ce12  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002ce19  lea     r8, pProxyInfo; pProxyInfo
0x18002ce20  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002ce27  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002ce2c  call    cs:__imp_NdrMesTypeDecode3
0x18002ce32  nop
0x18002ce33  mov     ebx, dword ptr [rsp+0D8h+var_70]
0x18002ce37  mov     [rsp+0D8h+var_90], ebx
0x18002ce3b  test    ebx, ebx
0x18002ce3d  jnz     short loc_18002CE59
0x18002ce3f  cmp     edi, dword ptr [rsp+0D8h+var_70+4]
0x18002ce43  jnz     loc_18002CCF9
0x18002ce49  mov     r8, [rsp+0D8h+var_70+8]; struct _ReaderState_Return *
0x18002ce4e  mov     rdx, r14; struct SCARD_READERSTATEW *
0x18002ce51  mov     ecx, edi; unsigned int
0x18002ce53  call    ?_CopyReaderStateWStructsForReturn@@YAXKPEAUSCARD_READERSTATEW@@PEAU_ReaderState_Return@@@Z; _CopyReaderStateWStructsForReturn(ulong,SCARD_READERSTATEW *,_ReaderState_Return *)
0x18002ce58  nop
0x18002ce59  lea     rax, [rsp+0D8h+var_70]
0x18002ce5e  mov     [rsp+0D8h+pObject], rax; pObject
0x18002ce63  mov     [rsp+0D8h+nTypeIndex], esi; nTypeIndex
0x18002ce67  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002ce6e  lea     r8, pProxyInfo; pProxyInfo
0x18002ce75  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002ce7c  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002ce81  call    cs:__imp_NdrMesTypeFree3
0x18002ce87  jmp     loc_18002CF20
0x18002ce8c  mov     ebx, [rsp+0D8h+var_90]
0x18002ce90  jmp     loc_18002CF20
0x18002ce95  mov     ebx, eax
0x18002ce97  mov     edx, 2
0x18002ce9c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cea1  lea     rax, WPP_GLOBAL_Control
0x18002cea8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ceaf  cmp     rcx, rax
0x18002ceb2  jz      short loc_18002CED9
0x18002ceb4  test    byte ptr [rcx+1Ch], 8
0x18002ceb8  jz      short loc_18002CED9
0x18002ceba  cmp     byte ptr [rcx+19h], 2
0x18002cebe  jb      short loc_18002CED9
0x18002cec0  mov     edx, 31h ; '1'
0x18002cec5  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002cec9  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002ced0  mov     rcx, [rcx+10h]
0x18002ced4  call    WPP_SF_sd
0x18002ced9  jmp     short loc_18002CF20
0x18002cedb  mov     ebx, eax
0x18002cedd  mov     edx, 2
0x18002cee2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cee7  lea     rax, WPP_GLOBAL_Control
0x18002ceee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cef5  cmp     rcx, rax
0x18002cef8  jz      short loc_18002CF20
0x18002cefa  test    byte ptr [rcx+1Ch], 8
0x18002cefe  jz      short loc_18002CF20
0x18002cf00  cmp     byte ptr [rcx+19h], 2
0x18002cf04  jb      short loc_18002CF20
0x18002cf06  mov     edx, 30h ; '0'
0x18002cf0b  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002cf0f  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002cf16  mov     rcx, [rcx+10h]
0x18002cf1a  call    WPP_SF_sd
0x18002cf1f  nop
0x18002cf20  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002cf25  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002cf2a  mov     rcx, [rsp+0D8h+pBuffer]; void *
0x18002cf2f  call    MIDL_user_free
0x18002cf34  mov     rcx, [rsp+0D8h+var_80]; void *
0x18002cf39  call    MIDL_user_free
0x18002cf3e  mov     rax, [rsp+0D8h+var_78]
0x18002cf43  test    rax, rax
0x18002cf46  jz      short loc_18002CF4F
0x18002cf48  mov     dword ptr [rax+8], 0
0x18002cf4f  mov     eax, ebx
0x18002cf51  add     rsp, 0B8h
0x18002cf58  pop     r14
0x18002cf5a  pop     rdi
0x18002cf5b  pop     rsi
0x18002cf5c  pop     rbx
0x18002cf5d  retn
```
