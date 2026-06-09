# RedirectedSCardGetDeviceTypeId(unsigned __int64,ushort const *,ulong *)

- ea: `0x18002c704`
- end: `0x18002c9a5`
- name: `?RedirectedSCardGetDeviceTypeId@@YAJ_KPEBGPEAK@Z`
- size: `673`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180016560`
- `0x180025490`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002c704`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002c881`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002c881`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002c7dc`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002c7dc`
- `RPCRT4!NdrMesTypeFree3` at `0x18002c8c1`
- `RPCRT4!NdrMesTypeFree3` at `0x18002c8c1`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002c78a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002c78a`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002c841`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002c841`

## pseudocode

```c
__int64 __fastcall RedirectedSCardGetDeviceTypeId(__int64 a1, const unsigned __int16 *a2, unsigned int *a3)
{
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  unsigned int SCardError; // ebx
  int v9; // eax
  handle_t pHandle; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+48h] [rbp-50h] BYREF
  char *pBuffer; // [rsp+50h] [rbp-48h] BYREF
  struct _BUFFER_LIST_STRUCT *v13; // [rsp+58h] [rbp-40h] BYREF
  __int128 pObject; // [rsp+60h] [rbp-38h] BYREF
  const unsigned __int16 *v15; // [rsp+70h] [rbp-28h]
  unsigned int pEncodedSize; // [rsp+A0h] [rbp+8h] BYREF
  int v17; // [rsp+B8h] [rbp+20h]

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v13 = 0;
  result = 0;
  pObject = 0;
  v15 = 0;
  v11 = 0;
  if ( !a1 || !a3 )
    return 2148532228LL;
  v7 = *(struct _RTL_CRITICAL_SECTION **)a1;
  if ( *(_DWORD *)(*(_QWORD *)a1 + 68LL) < 3u )
  {
    *a3 = 32;
    return result;
  }
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    v15 = a2;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Eu, &pObject);
    v9 = _SendSCardIOCTL(0x90108u, pBuffer, pEncodedSize, &v13, v7, 0xFFFFFFFF, 0x800u);
    if ( v9 )
    {
      SCardError = _MakeSCardError(v9);
      goto LABEL_13;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v13 + 2), *((_DWORD *)v13 + 7), &pHandle) )
    {
      v11 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Fu, &v11);
      SCardError = v11;
      v17 = v11;
      if ( !(_DWORD)v11 )
        *a3 = HIDWORD(v11);
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Fu, &v11);
      goto LABEL_13;
    }
  }
  SCardError = -2146435041;
LABEL_13:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v13 )
    *((_DWORD *)v13 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002c704  mov     r11, rsp
0x18002c707  mov     [r11+10h], rbx
0x18002c70b  push    rsi
0x18002c70c  push    rdi
0x18002c70d  push    r14
0x18002c70f  sub     rsp, 80h
0x18002c716  mov     rdi, r8
0x18002c719  mov     r14, rdx
0x18002c71c  mov     rbx, rcx
0x18002c71f  mov     qword ptr [r11-48h], 0
0x18002c727  mov     dword ptr [r11+8], 0
0x18002c72f  mov     qword ptr [r11-58h], 0
0x18002c737  mov     qword ptr [r11-40h], 0
0x18002c73f  xorps   xmm0, xmm0
0x18002c742  xor     eax, eax
0x18002c744  movups  [rsp+98h+var_38], xmm0
0x18002c749  mov     [r11-28h], rax
0x18002c74d  mov     [r11-50h], rax
0x18002c751  test    rcx, rcx
0x18002c754  jz      loc_18002C98C
0x18002c75a  test    r8, r8
0x18002c75d  jz      loc_18002C98C
0x18002c763  mov     rsi, [rcx]
0x18002c766  cmp     dword ptr [rsi+44h], 3
0x18002c76a  jnb     short loc_18002C778
0x18002c76c  mov     dword ptr [r8], 20h ; ' '
0x18002c773  jmp     loc_18002C991
0x18002c778  lea     r8, [rsp+98h+pHandle]; pHandle
0x18002c77d  lea     rdx, [rsp+98h+pEncodedSize]; pEncodedSize
0x18002c785  lea     rcx, [rsp+98h+pBuffer]; pBuffer
0x18002c78a  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002c790  test    eax, eax
0x18002c792  jz      short loc_18002C79E
0x18002c794  mov     ebx, 8010001Fh
0x18002c799  jmp     loc_18002C963
0x18002c79e  movups  xmm0, xmmword ptr [rbx+8]
0x18002c7a2  movdqu  [rsp+98h+var_38], xmm0
0x18002c7a8  mov     [rsp+98h+var_28], r14
0x18002c7ad  lea     rax, [rsp+98h+var_38]
0x18002c7b2  mov     [rsp+98h+pObject], rax; pObject
0x18002c7b7  mov     [rsp+98h+nTypeIndex], 2Eh ; '.'; nTypeIndex
0x18002c7bf  lea     r14, ArrTypeOffset
0x18002c7c6  mov     r9, r14; ArrTypeOffset
0x18002c7c9  lea     r8, pProxyInfo; pProxyInfo
0x18002c7d0  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c7d7  mov     rcx, [rsp+98h+pHandle]; Handle
0x18002c7dc  call    cs:__imp_NdrMesTypeEncode3
0x18002c7e2  nop
0x18002c7e3  mov     [rsp+98h+var_68], 800h; unsigned int
0x18002c7eb  mov     dword ptr [rsp+98h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002c7f3  mov     qword ptr [rsp+98h+nTypeIndex], rsi; lpCriticalSection
0x18002c7f8  lea     r9, [rsp+98h+var_40]; struct _BUFFER_LIST_STRUCT **
0x18002c7fd  mov     r8d, [rsp+98h+pEncodedSize]; InputBufferLength
0x18002c805  mov     rdx, [rsp+98h+pBuffer]; InputBuffer
0x18002c80a  mov     ecx, 90108h; IoControlCode
0x18002c80f  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002c814  test    eax, eax
0x18002c816  jz      short loc_18002C826
0x18002c818  mov     ecx, eax; int
0x18002c81a  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002c81f  mov     ebx, eax
0x18002c821  jmp     loc_18002C963
0x18002c826  lea     rcx, [rsp+98h+pHandle]; void **
0x18002c82b  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002c830  lea     r8, [rsp+98h+pHandle]; pHandle
0x18002c835  mov     rcx, [rsp+98h+var_40]
0x18002c83a  mov     edx, [rcx+1Ch]; BufferSize
0x18002c83d  mov     rcx, [rcx+10h]; Buffer
0x18002c841  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002c847  test    eax, eax
0x18002c849  jnz     loc_18002C794
0x18002c84f  mov     [rsp+98h+var_50], 0
0x18002c858  lea     rax, [rsp+98h+var_50]
0x18002c85d  mov     [rsp+98h+pObject], rax; pObject
0x18002c862  mov     esi, 2Fh ; '/'
0x18002c867  mov     [rsp+98h+nTypeIndex], esi; nTypeIndex
0x18002c86b  mov     r9, r14; ArrTypeOffset
0x18002c86e  lea     r8, pProxyInfo; pProxyInfo
0x18002c875  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c87c  mov     rcx, [rsp+98h+pHandle]; Handle
0x18002c881  call    cs:__imp_NdrMesTypeDecode3
0x18002c887  nop
0x18002c888  mov     ebx, dword ptr [rsp+98h+var_50]
0x18002c88c  mov     [rsp+98h+arg_18], ebx
0x18002c893  test    ebx, ebx
0x18002c895  jnz     short loc_18002C89D
0x18002c897  mov     eax, dword ptr [rsp+98h+var_50+4]
0x18002c89b  mov     [rdi], eax
0x18002c89d  lea     rax, [rsp+98h+var_50]
0x18002c8a2  mov     [rsp+98h+pObject], rax; pObject
0x18002c8a7  mov     [rsp+98h+nTypeIndex], esi; nTypeIndex
0x18002c8ab  mov     r9, r14; ArrTypeOffset
0x18002c8ae  lea     r8, pProxyInfo; pProxyInfo
0x18002c8b5  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c8bc  mov     rcx, [rsp+98h+pHandle]; Handle
0x18002c8c1  call    cs:__imp_NdrMesTypeFree3
0x18002c8c7  jmp     loc_18002C963
0x18002c8cc  mov     ebx, [rsp+98h+arg_18]
0x18002c8d3  jmp     loc_18002C963
0x18002c8d8  mov     ebx, eax
0x18002c8da  mov     edx, 2
0x18002c8df  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c8e4  lea     rax, WPP_GLOBAL_Control
0x18002c8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8f2  cmp     rcx, rax
0x18002c8f5  jz      short loc_18002C91C
0x18002c8f7  test    byte ptr [rcx+1Ch], 8
0x18002c8fb  jz      short loc_18002C91C
0x18002c8fd  cmp     byte ptr [rcx+19h], 2
0x18002c901  jb      short loc_18002C91C
0x18002c903  mov     edx, 59h ; 'Y'
0x18002c908  mov     [rsp+98h+nTypeIndex], ebx
0x18002c90c  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c913  mov     rcx, [rcx+10h]
0x18002c917  call    WPP_SF_sd
0x18002c91c  jmp     short loc_18002C963
0x18002c91e  mov     ebx, eax
0x18002c920  mov     edx, 2
0x18002c925  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c92a  lea     rax, WPP_GLOBAL_Control
0x18002c931  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c938  cmp     rcx, rax
0x18002c93b  jz      short loc_18002C963
0x18002c93d  test    byte ptr [rcx+1Ch], 8
0x18002c941  jz      short loc_18002C963
0x18002c943  cmp     byte ptr [rcx+19h], 2
0x18002c947  jb      short loc_18002C963
0x18002c949  mov     edx, 58h ; 'X'
0x18002c94e  mov     [rsp+98h+nTypeIndex], ebx
0x18002c952  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c959  mov     rcx, [rcx+10h]
0x18002c95d  call    WPP_SF_sd
0x18002c962  nop
0x18002c963  lea     rcx, [rsp+98h+pHandle]; void **
0x18002c968  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002c96d  mov     rcx, [rsp+98h+pBuffer]; void *
0x18002c972  call    MIDL_user_free
0x18002c977  mov     rax, [rsp+98h+var_40]
0x18002c97c  test    rax, rax
0x18002c97f  jz      short loc_18002C988
0x18002c981  mov     dword ptr [rax+8], 0
0x18002c988  mov     eax, ebx
0x18002c98a  jmp     short loc_18002C991
0x18002c98c  mov     eax, 80100004h
0x18002c991  mov     rbx, [rsp+98h+arg_8]
0x18002c999  add     rsp, 80h
0x18002c9a0  pop     r14
0x18002c9a2  pop     rdi
0x18002c9a3  pop     rsi
0x18002c9a4  retn
```
