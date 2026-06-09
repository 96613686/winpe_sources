# RedirectedSCardState(unsigned __int64,ulong *,ulong *,uchar *,ulong *)

- ea: `0x18002dd0c`
- end: `0x18002e009`
- name: `?RedirectedSCardState@@YAJ_KPEAK1PEAE1@Z`
- size: `765`
- prototype: `int(unsigned __int64, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023820`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x180016ef0`
- `0x18001991c`
- `0x180019a14`
- `0x18002dd0c`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002deb4`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002deb4`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002de00`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002de00`
- `RPCRT4!NdrMesTypeFree3` at `0x18002df32`
- `RPCRT4!NdrMesTypeFree3` at `0x18002df32`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002dd8a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002dd8a`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002de6b`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002de6b`

## pseudocode

```c
__int64 __fastcall RedirectedSCardState(
        __int64 a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  unsigned int SCardError; // ebx
  unsigned int *v11; // r15
  int v12; // eax
  handle_t pHandle; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v14; // [rsp+48h] [rbp-90h]
  char *pBuffer; // [rsp+50h] [rbp-88h] BYREF
  struct _BUFFER_LIST_STRUCT *v16; // [rsp+58h] [rbp-80h] BYREF
  unsigned int v17[4]; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int8 *v18; // [rsp+70h] [rbp-68h]
  __int128 pObject; // [rsp+78h] [rbp-60h] BYREF
  __int128 v20; // [rsp+88h] [rbp-50h]
  __int64 v21; // [rsp+98h] [rbp-40h]
  unsigned int pEncodedSize; // [rsp+E0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v16 = 0;
  pObject = 0;
  v20 = 0;
  v21 = 0;
  *(_OWORD *)v17 = 0;
  v18 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    v20 = *(_OWORD *)(a1 + 24);
    LODWORD(v21) = a4 == 0;
    v11 = a5;
    HIDWORD(v21) = *a5;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Au, &pObject);
    v12 = _SendSCardIOCTL(0x900C4u, pBuffer, pEncodedSize, &v16, **(LPCRITICAL_SECTION **)a1, 0xFFFFFFFF, 0x800u);
    if ( v12 )
    {
      SCardError = _MakeSCardError(v12);
      goto LABEL_15;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v16 + 2), *((_DWORD *)v16 + 7), &pHandle) )
    {
      *(_OWORD *)v17 = 0;
      v18 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Bu, v17);
      SCardError = v17[0];
      v14 = v17[0];
      if ( !v17[0] )
      {
        if ( a2 )
          *a2 = v17[1];
        if ( a3 )
          *a3 = v17[2];
        SCardError = _CopyReturnToCallerBuffer(*(struct _REDIR_LOCAL_SCARDCONTEXT **)a1, v18, v17[3], a4, v11, 1u);
        v14 = SCardError;
      }
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Bu, v17);
      goto LABEL_15;
    }
  }
  SCardError = -2146435041;
LABEL_15:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v16 )
    *((_DWORD *)v16 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002dd0c  mov     r11, rsp
0x18002dd0f  push    rbx
0x18002dd10  push    rsi
0x18002dd11  push    rdi
0x18002dd12  push    r12
0x18002dd14  push    r14
0x18002dd16  push    r15
0x18002dd18  sub     rsp, 0A8h
0x18002dd1f  mov     r12, r9
0x18002dd22  mov     r14, r8
0x18002dd25  mov     rsi, rdx
0x18002dd28  mov     rdi, rcx
0x18002dd2b  mov     [rsp+0D8h+pBuffer], 0
0x18002dd34  mov     dword ptr [r11+8], 0
0x18002dd3c  mov     [rsp+0D8h+pHandle], 0
0x18002dd45  mov     qword ptr [r11-80h], 0
0x18002dd4d  xorps   xmm0, xmm0
0x18002dd50  xor     eax, eax
0x18002dd52  movups  [rsp+0D8h+var_60], xmm0
0x18002dd57  movups  xmmword ptr [r11-50h], xmm0
0x18002dd5c  mov     [r11-40h], rax
0x18002dd60  movups  xmmword ptr [rsp+0D8h+var_78], xmm0
0x18002dd65  mov     [r11-68h], rax
0x18002dd69  test    rcx, rcx
0x18002dd6c  jnz     short loc_18002DD78
0x18002dd6e  mov     eax, 80100004h
0x18002dd73  jmp     loc_18002DFF8
0x18002dd78  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x18002dd7d  lea     rdx, [rsp+0D8h+pEncodedSize]; pEncodedSize
0x18002dd85  lea     rcx, [rsp+0D8h+pBuffer]; pBuffer
0x18002dd8a  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002dd90  test    eax, eax
0x18002dd92  jz      short loc_18002DD9E
0x18002dd94  mov     ebx, 8010001Fh
0x18002dd99  jmp     loc_18002DFD1
0x18002dd9e  movups  xmm0, xmmword ptr [rdi+8]
0x18002dda2  movups  [rsp+0D8h+var_60], xmm0
0x18002dda7  movups  xmm1, xmmword ptr [rdi+18h]
0x18002ddab  movups  [rsp+0D8h+var_50], xmm1
0x18002ddb3  xor     eax, eax
0x18002ddb5  test    r12, r12
0x18002ddb8  setz    al
0x18002ddbb  mov     [rsp+0D8h+var_40], eax
0x18002ddc2  mov     r15, [rsp+0D8h+arg_20]
0x18002ddca  mov     eax, [r15]
0x18002ddcd  mov     [rsp+0D8h+var_3C], eax
0x18002ddd4  lea     rax, [rsp+0D8h+var_60]
0x18002ddd9  mov     [rsp+0D8h+pObject], rax; pObject
0x18002ddde  mov     [rsp+0D8h+nTypeIndex], 1Ah; nTypeIndex
0x18002dde6  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002dded  lea     r8, pProxyInfo; pProxyInfo
0x18002ddf4  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002ddfb  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002de00  call    cs:__imp_NdrMesTypeEncode3
0x18002de06  nop
0x18002de07  mov     rax, [rdi]
0x18002de0a  mov     [rsp+0D8h+var_A8], 800h; unsigned int
0x18002de12  mov     dword ptr [rsp+0D8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002de1a  mov     rax, [rax]
0x18002de1d  mov     qword ptr [rsp+0D8h+nTypeIndex], rax; lpCriticalSection
0x18002de22  lea     r9, [rsp+0D8h+var_80]; struct _BUFFER_LIST_STRUCT **
0x18002de27  mov     r8d, [rsp+0D8h+pEncodedSize]; InputBufferLength
0x18002de2f  mov     rdx, [rsp+0D8h+pBuffer]; InputBuffer
0x18002de34  mov     ecx, 900C4h; IoControlCode
0x18002de39  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002de3e  test    eax, eax
0x18002de40  jz      short loc_18002DE50
0x18002de42  mov     ecx, eax; int
0x18002de44  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002de49  mov     ebx, eax
0x18002de4b  jmp     loc_18002DFD1
0x18002de50  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002de55  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002de5a  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x18002de5f  mov     rcx, [rsp+0D8h+var_80]
0x18002de64  mov     edx, [rcx+1Ch]; BufferSize
0x18002de67  mov     rcx, [rcx+10h]; Buffer
0x18002de6b  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002de71  test    eax, eax
0x18002de73  jnz     loc_18002DD94
0x18002de79  xorps   xmm0, xmm0
0x18002de7c  xor     eax, eax
0x18002de7e  movups  xmmword ptr [rsp+0D8h+var_78], xmm0
0x18002de83  mov     [rsp+0D8h+var_68], rax
0x18002de88  lea     rax, [rsp+0D8h+var_78]
0x18002de8d  mov     [rsp+0D8h+pObject], rax; pObject
0x18002de92  mov     [rsp+0D8h+nTypeIndex], 1Bh; nTypeIndex
0x18002de9a  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002dea1  lea     r8, pProxyInfo; pProxyInfo
0x18002dea8  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002deaf  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002deb4  call    cs:__imp_NdrMesTypeDecode3
0x18002deba  nop
0x18002debb  mov     ebx, [rsp+0D8h+var_78]
0x18002debf  mov     [rsp+0D8h+var_90], ebx
0x18002dec3  test    ebx, ebx
0x18002dec5  jnz     short loc_18002DF06
0x18002dec7  test    rsi, rsi
0x18002deca  jz      short loc_18002DED2
0x18002decc  mov     eax, [rsp+0D8h+var_78+4]
0x18002ded0  mov     [rsi], eax
0x18002ded2  test    r14, r14
0x18002ded5  jz      short loc_18002DEDE
0x18002ded7  mov     eax, [rsp+0D8h+var_78+8]
0x18002dedb  mov     [r14], eax
0x18002dede  mov     dword ptr [rsp+0D8h+pObject], 1; unsigned int
0x18002dee6  mov     qword ptr [rsp+0D8h+nTypeIndex], r15; unsigned int *
0x18002deeb  mov     r9, r12; unsigned __int8 *
0x18002deee  mov     r8d, [rsp+0D8h+var_78+0Ch]; unsigned int
0x18002def3  mov     rdx, [rsp+0D8h+var_68]; unsigned __int8 *
0x18002def8  mov     rcx, [rdi]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18002defb  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x18002df00  mov     ebx, eax
0x18002df02  mov     [rsp+0D8h+var_90], eax
0x18002df06  lea     rax, [rsp+0D8h+var_78]
0x18002df0b  mov     [rsp+0D8h+pObject], rax; pObject
0x18002df10  mov     [rsp+0D8h+nTypeIndex], 1Bh; nTypeIndex
0x18002df18  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002df1f  lea     r8, pProxyInfo; pProxyInfo
0x18002df26  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002df2d  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002df32  call    cs:__imp_NdrMesTypeFree3
0x18002df38  jmp     loc_18002DFD1
0x18002df3d  mov     ebx, [rsp+0D8h+var_90]
0x18002df41  jmp     loc_18002DFD1
0x18002df46  mov     ebx, eax
0x18002df48  mov     edx, 2
0x18002df4d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002df52  lea     rax, WPP_GLOBAL_Control
0x18002df59  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df60  cmp     rcx, rax
0x18002df63  jz      short loc_18002DF8A
0x18002df65  test    byte ptr [rcx+1Ch], 8
0x18002df69  jz      short loc_18002DF8A
0x18002df6b  cmp     byte ptr [rcx+19h], 2
0x18002df6f  jb      short loc_18002DF8A
0x18002df71  mov     edx, 45h ; 'E'
0x18002df76  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002df7a  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002df81  mov     rcx, [rcx+10h]
0x18002df85  call    WPP_SF_sd
0x18002df8a  jmp     short loc_18002DFD1
0x18002df8c  mov     ebx, eax
0x18002df8e  mov     edx, 2
0x18002df93  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002df98  lea     rax, WPP_GLOBAL_Control
0x18002df9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfa6  cmp     rcx, rax
0x18002dfa9  jz      short loc_18002DFD1
0x18002dfab  test    byte ptr [rcx+1Ch], 8
0x18002dfaf  jz      short loc_18002DFD1
0x18002dfb1  cmp     byte ptr [rcx+19h], 2
0x18002dfb5  jb      short loc_18002DFD1
0x18002dfb7  mov     edx, 44h ; 'D'
0x18002dfbc  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002dfc0  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002dfc7  mov     rcx, [rcx+10h]
0x18002dfcb  call    WPP_SF_sd
0x18002dfd0  nop
0x18002dfd1  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002dfd6  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002dfdb  mov     rcx, [rsp+0D8h+pBuffer]; void *
0x18002dfe0  call    MIDL_user_free
0x18002dfe5  mov     rax, [rsp+0D8h+var_80]
0x18002dfea  test    rax, rax
0x18002dfed  jz      short loc_18002DFF6
0x18002dfef  mov     dword ptr [rax+8], 0
0x18002dff6  mov     eax, ebx
0x18002dff8  add     rsp, 0A8h
0x18002dfff  pop     r15
0x18002e001  pop     r14
0x18002e003  pop     r12
0x18002e005  pop     rdi
0x18002e006  pop     rsi
0x18002e007  pop     rbx
0x18002e008  retn
```
