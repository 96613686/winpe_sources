# I_SCardStatus(unsigned __int64,uchar *,ulong *,ulong *,ulong *,uchar *,ulong *,int)

- ea: `0x180018b48`
- end: `0x180018f47`
- name: `?I_SCardStatus@@YAJ_KPEAEPEAK2212H@Z`
- size: `1023`
- prototype: `int(unsigned __int64, unsigned __int8 *, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000fb40`
- `0x180018960`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x180016ef0`
- `0x180018b48`
- `0x18001991c`
- `0x180019a14`
- `0x18001be10`
- `0x18001c7a8`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x180018d6f`
- `RPCRT4!NdrMesTypeDecode3` at `0x180018d6f`
- `RPCRT4!NdrMesTypeEncode3` at `0x180018ca3`
- `RPCRT4!NdrMesTypeEncode3` at `0x180018ca3`
- `RPCRT4!NdrMesTypeFree3` at `0x180018e5e`
- `RPCRT4!NdrMesTypeFree3` at `0x180018e5e`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180018c07`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180018c07`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180018d1e`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180018d1e`

## pseudocode

```c
__int64 __fastcall I_SCardStatus(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        int a8)
{
  unsigned int SCardError; // ebx
  int v14; // eax
  unsigned int v15; // r8d
  handle_t pHandle; // [rsp+48h] [rbp-F0h] BYREF
  unsigned int pEncodedSize; // [rsp+50h] [rbp-E8h] BYREF
  char *pBuffer; // [rsp+58h] [rbp-E0h] BYREF
  struct _BUFFER_LIST_STRUCT *v19; // [rsp+60h] [rbp-D8h] BYREF
  unsigned __int8 *v20; // [rsp+68h] [rbp-D0h]
  unsigned __int8 *v21; // [rsp+70h] [rbp-C8h]
  __int128 pObject; // [rsp+78h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+88h] [rbp-B0h]
  __int128 v24; // [rsp+98h] [rbp-A0h]
  _DWORD v25[2]; // [rsp+B0h] [rbp-88h] BYREF
  unsigned __int8 *v26; // [rsp+B8h] [rbp-80h]
  unsigned int v27; // [rsp+C0h] [rbp-78h]
  unsigned int v28; // [rsp+C4h] [rbp-74h]
  unsigned __int8 v29[32]; // [rsp+C8h] [rbp-70h] BYREF
  unsigned int v30; // [rsp+E8h] [rbp-50h]

  v20 = a2;
  v21 = a6;
  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v19 = 0;
  pObject = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v25, 0, 0x40u);
  if ( !a1 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    v23 = *(_OWORD *)(a1 + 24);
    LODWORD(v24) = a2 == 0;
    if ( a3 )
      DWORD1(v24) = *a3;
    else
      DWORD1(v24) = 0;
    if ( a7 )
      DWORD2(v24) = *a7;
    else
      DWORD2(v24) = 0;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Cu, &pObject);
    v14 = _SendSCardIOCTL(
            a8 != 0 ? 590028 : 590024,
            pBuffer,
            pEncodedSize,
            &v19,
            **(LPCRITICAL_SECTION **)a1,
            0xFFFFFFFF,
            0x800u);
    if ( v14 )
    {
      SCardError = _MakeSCardError(v14);
      goto LABEL_26;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v19 + 2), *((_DWORD *)v19 + 7), &pHandle) )
    {
      memset_0(v25, 0, 0x40u);
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Du, v25);
      v15 = v30;
      if ( v30 <= 0x20 )
      {
        SCardError = v25[0];
        if ( !v25[0] )
        {
          if ( a3 )
          {
            SCardError = _CopyReturnToCallerBuffer(
                           *(struct _REDIR_LOCAL_SCARDCONTEXT **)a1,
                           v26,
                           v25[1],
                           v20,
                           a3,
                           (a8 != 0) + 2);
            v15 = v30;
          }
          if ( !SCardError )
          {
            if ( a4 )
              *a4 = v27;
            if ( a5 )
              *a5 = v28;
            if ( a7 )
              SCardError = _CopyReturnToCallerBuffer(*(struct _REDIR_LOCAL_SCARDCONTEXT **)a1, v29, v15, v21, a7, 1u);
          }
        }
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x1Du, v25);
        goto LABEL_26;
      }
    }
  }
  SCardError = -2146435041;
LABEL_26:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v19 )
    *((_DWORD *)v19 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x180018b48  push    rbx
0x180018b4a  push    rsi
0x180018b4b  push    rdi
0x180018b4c  push    r12
0x180018b4e  push    r13
0x180018b50  push    r14
0x180018b52  push    r15
0x180018b54  sub     rsp, 100h
0x180018b5b  mov     rax, cs:__security_cookie
0x180018b62  xor     rax, rsp
0x180018b65  mov     [rsp+138h+var_48], rax
0x180018b6d  mov     r12, r9
0x180018b70  mov     rsi, r8
0x180018b73  mov     rbx, rdx
0x180018b76  mov     [rsp+138h+var_D0], rdx
0x180018b7b  mov     r14, rcx
0x180018b7e  mov     r13, [rsp+138h+arg_20]
0x180018b86  mov     rax, [rsp+138h+arg_28]
0x180018b8e  mov     [rsp+138h+var_C8], rax
0x180018b93  mov     rdi, [rsp+138h+arg_30]
0x180018b9b  mov     [rsp+138h+pBuffer], 0
0x180018ba4  mov     [rsp+138h+pEncodedSize], 0
0x180018bac  mov     [rsp+138h+pHandle], 0
0x180018bb5  mov     [rsp+138h+var_D8], 0
0x180018bbe  xorps   xmm0, xmm0
0x180018bc1  movups  [rsp+138h+var_C0], xmm0
0x180018bc6  movups  [rsp+138h+var_B0], xmm0
0x180018bce  movups  [rsp+138h+var_A0], xmm0
0x180018bd6  xor     edx, edx; Val
0x180018bd8  lea     r8d, [rdx+40h]; Size
0x180018bdc  lea     rcx, [rsp+138h+var_88]; void *
0x180018be4  call    memset_0
0x180018be9  test    r14, r14
0x180018bec  jnz     short loc_180018BF8
0x180018bee  mov     eax, 80100004h
0x180018bf3  jmp     loc_180018F24
0x180018bf8  lea     r8, [rsp+138h+pHandle]; pHandle
0x180018bfd  lea     rdx, [rsp+138h+pEncodedSize]; pEncodedSize
0x180018c02  lea     rcx, [rsp+138h+pBuffer]; pBuffer
0x180018c07  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180018c0d  test    eax, eax
0x180018c0f  jz      short loc_180018C1B
0x180018c11  mov     ebx, 8010001Fh
0x180018c16  jmp     loc_180018EFD
0x180018c1b  movups  xmm0, xmmword ptr [r14+8]
0x180018c20  movups  [rsp+138h+var_C0], xmm0
0x180018c25  movups  xmm1, xmmword ptr [r14+18h]
0x180018c2a  movups  [rsp+138h+var_B0], xmm1
0x180018c32  xor     eax, eax
0x180018c34  test    rbx, rbx
0x180018c37  setz    al
0x180018c3a  mov     dword ptr [rsp+138h+var_A0], eax
0x180018c41  test    rsi, rsi
0x180018c44  jz      short loc_180018C51
0x180018c46  mov     eax, [rsi]
0x180018c48  mov     dword ptr [rsp+138h+var_A0+4], eax
0x180018c4f  jmp     short loc_180018C5C
0x180018c51  mov     dword ptr [rsp+138h+var_A0+4], 0
0x180018c5c  test    rdi, rdi
0x180018c5f  jz      short loc_180018C6C
0x180018c61  mov     eax, [rdi]
0x180018c63  mov     dword ptr [rsp+138h+var_A0+8], eax
0x180018c6a  jmp     short loc_180018C77
0x180018c6c  mov     dword ptr [rsp+138h+var_A0+8], 0
0x180018c77  lea     rax, [rsp+138h+var_C0]
0x180018c7c  mov     [rsp+138h+pObject], rax; pObject
0x180018c81  mov     [rsp+138h+nTypeIndex], 1Ch; nTypeIndex
0x180018c89  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180018c90  lea     r8, pProxyInfo; pProxyInfo
0x180018c97  lea     rdx, pPicklingInfo; pPicklingInfo
0x180018c9e  mov     rcx, [rsp+138h+pHandle]; Handle
0x180018ca3  call    cs:__imp_NdrMesTypeEncode3
0x180018ca9  nop
0x180018caa  mov     rdx, [r14]
0x180018cad  mov     r15d, [rsp+138h+arg_38]
0x180018cb5  mov     eax, r15d
0x180018cb8  neg     eax
0x180018cba  sbb     ecx, ecx
0x180018cbc  and     ecx, 4
0x180018cbf  add     ecx, 900C8h; IoControlCode
0x180018cc5  mov     [rsp+138h+var_108], 800h; unsigned int
0x180018ccd  mov     dword ptr [rsp+138h+pObject], 0FFFFFFFFh; dwMilliseconds
0x180018cd5  mov     rax, [rdx]
0x180018cd8  mov     qword ptr [rsp+138h+nTypeIndex], rax; lpCriticalSection
0x180018cdd  lea     r9, [rsp+138h+var_D8]; struct _BUFFER_LIST_STRUCT **
0x180018ce2  mov     r8d, [rsp+138h+pEncodedSize]; InputBufferLength
0x180018ce7  mov     rdx, [rsp+138h+pBuffer]; InputBuffer
0x180018cec  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x180018cf1  test    eax, eax
0x180018cf3  jz      short loc_180018D03
0x180018cf5  mov     ecx, eax; int
0x180018cf7  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x180018cfc  mov     ebx, eax
0x180018cfe  jmp     loc_180018EFD
0x180018d03  lea     rcx, [rsp+138h+pHandle]; void **
0x180018d08  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x180018d0d  lea     r8, [rsp+138h+pHandle]; pHandle
0x180018d12  mov     rcx, [rsp+138h+var_D8]
0x180018d17  mov     edx, [rcx+1Ch]; BufferSize
0x180018d1a  mov     rcx, [rcx+10h]; Buffer
0x180018d1e  call    cs:__imp_MesDecodeBufferHandleCreate
0x180018d24  test    eax, eax
0x180018d26  jnz     loc_180018C11
0x180018d2c  xor     edx, edx; Val
0x180018d2e  lea     r8d, [rax+40h]; Size
0x180018d32  lea     rcx, [rsp+138h+var_88]; void *
0x180018d3a  call    memset_0
0x180018d3f  nop
0x180018d40  lea     rax, [rsp+138h+var_88]
0x180018d48  mov     [rsp+138h+pObject], rax; pObject
0x180018d4d  mov     [rsp+138h+nTypeIndex], 1Dh; nTypeIndex
0x180018d55  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180018d5c  lea     r8, pProxyInfo; pProxyInfo
0x180018d63  lea     rdx, pPicklingInfo; pPicklingInfo
0x180018d6a  mov     rcx, [rsp+138h+pHandle]; Handle
0x180018d6f  call    cs:__imp_NdrMesTypeDecode3
0x180018d75  nop
0x180018d76  mov     r8d, [rsp+138h+var_50]
0x180018d7e  cmp     r8d, 20h ; ' '
0x180018d82  ja      loc_180018C11
0x180018d88  mov     ebx, [rsp+138h+var_88]
0x180018d8f  mov     [rsp+138h+var_F8], ebx
0x180018d93  test    ebx, ebx
0x180018d95  jnz     loc_180018E2F
0x180018d9b  test    rsi, rsi
0x180018d9e  jz      short loc_180018DDE
0x180018da0  neg     r15d
0x180018da3  sbb     eax, eax
0x180018da5  neg     eax
0x180018da7  add     eax, 2
0x180018daa  mov     dword ptr [rsp+138h+pObject], eax; unsigned int
0x180018dae  mov     qword ptr [rsp+138h+nTypeIndex], rsi; unsigned int *
0x180018db3  mov     r9, [rsp+138h+var_D0]; unsigned __int8 *
0x180018db8  mov     r8d, [rsp+138h+var_84]; unsigned int
0x180018dc0  mov     rdx, [rsp+138h+var_80]; unsigned __int8 *
0x180018dc8  mov     rcx, [r14]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x180018dcb  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x180018dd0  mov     ebx, eax
0x180018dd2  mov     [rsp+138h+var_F8], eax
0x180018dd6  mov     r8d, [rsp+138h+var_50]; unsigned int
0x180018dde  test    ebx, ebx
0x180018de0  jnz     short loc_180018E2F
0x180018de2  test    r12, r12
0x180018de5  jz      short loc_180018DF2
0x180018de7  mov     eax, [rsp+138h+var_78]
0x180018dee  mov     [r12], eax
0x180018df2  test    r13, r13
0x180018df5  jz      short loc_180018E02
0x180018df7  mov     eax, [rsp+138h+var_74]
0x180018dfe  mov     [r13+0], eax
0x180018e02  test    rdi, rdi
0x180018e05  jz      short loc_180018E2F
0x180018e07  mov     dword ptr [rsp+138h+pObject], 1; unsigned int
0x180018e0f  mov     qword ptr [rsp+138h+nTypeIndex], rdi; unsigned int *
0x180018e14  mov     r9, [rsp+138h+var_C8]; unsigned __int8 *
0x180018e19  lea     rdx, [rsp+138h+var_70]; unsigned __int8 *
0x180018e21  mov     rcx, [r14]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x180018e24  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x180018e29  mov     ebx, eax
0x180018e2b  mov     [rsp+138h+var_F8], eax
0x180018e2f  lea     rax, [rsp+138h+var_88]
0x180018e37  mov     [rsp+138h+pObject], rax; pObject
0x180018e3c  mov     [rsp+138h+nTypeIndex], 1Dh; nTypeIndex
0x180018e44  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180018e4b  lea     r8, pProxyInfo; pProxyInfo
0x180018e52  lea     rdx, pPicklingInfo; pPicklingInfo
0x180018e59  mov     rcx, [rsp+138h+pHandle]; Handle
0x180018e5e  call    cs:__imp_NdrMesTypeFree3
0x180018e64  jmp     loc_180018EFD
0x180018e69  mov     ebx, [rsp+138h+var_F8]
0x180018e6d  jmp     loc_180018EFD
0x180018e72  mov     ebx, eax
0x180018e74  mov     edx, 2
0x180018e79  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180018e7e  lea     rax, WPP_GLOBAL_Control
0x180018e85  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e8c  cmp     rcx, rax
0x180018e8f  jz      short loc_180018EB6
0x180018e91  test    byte ptr [rcx+1Ch], 8
0x180018e95  jz      short loc_180018EB6
0x180018e97  cmp     byte ptr [rcx+19h], 2
0x180018e9b  jb      short loc_180018EB6
0x180018e9d  mov     edx, 47h ; 'G'
0x180018ea2  mov     [rsp+138h+nTypeIndex], ebx
0x180018ea6  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180018ead  mov     rcx, [rcx+10h]
0x180018eb1  call    WPP_SF_sd
0x180018eb6  jmp     short loc_180018EFD
0x180018eb8  mov     ebx, eax
0x180018eba  mov     edx, 2
0x180018ebf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180018ec4  lea     rax, WPP_GLOBAL_Control
0x180018ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ed2  cmp     rcx, rax
0x180018ed5  jz      short loc_180018EFD
0x180018ed7  test    byte ptr [rcx+1Ch], 8
0x180018edb  jz      short loc_180018EFD
0x180018edd  cmp     byte ptr [rcx+19h], 2
0x180018ee1  jb      short loc_180018EFD
0x180018ee3  mov     edx, 46h ; 'F'
0x180018ee8  mov     [rsp+138h+nTypeIndex], ebx
0x180018eec  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180018ef3  mov     rcx, [rcx+10h]
0x180018ef7  call    WPP_SF_sd
0x180018efc  nop
0x180018efd  lea     rcx, [rsp+138h+pHandle]; void **
0x180018f02  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x180018f07  mov     rcx, [rsp+138h+pBuffer]; void *
0x180018f0c  call    MIDL_user_free
0x180018f11  mov     rax, [rsp+138h+var_D8]
0x180018f16  test    rax, rax
0x180018f19  jz      short loc_180018F22
0x180018f1b  mov     dword ptr [rax+8], 0
0x180018f22  mov     eax, ebx
0x180018f24  mov     rcx, [rsp+138h+var_48]
0x180018f2c  xor     rcx, rsp; StackCookie
0x180018f2f  call    __security_check_cookie
0x180018f34  add     rsp, 100h
0x180018f3b  pop     r15
0x180018f3d  pop     r14
0x180018f3f  pop     r13
0x180018f41  pop     r12
0x180018f43  pop     rdi
0x180018f44  pop     rsi
0x180018f45  pop     rbx
0x180018f46  retn
```
