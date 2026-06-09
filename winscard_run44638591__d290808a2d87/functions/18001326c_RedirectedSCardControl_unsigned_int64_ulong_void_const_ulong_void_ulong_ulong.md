# RedirectedSCardControl(unsigned __int64,ulong,void const *,ulong,void *,ulong,ulong *)

- ea: `0x18001326c`
- end: `0x180013588`
- name: `?RedirectedSCardControl@@YAJ_KKPEBXKPEAXKPEAK@Z`
- size: `796`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, const void *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012f80`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x18001326c`
- `0x180016ef0`
- `0x18001991c`
- `0x180019a14`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x180013437`
- `RPCRT4!NdrMesTypeDecode3` at `0x180013437`
- `RPCRT4!NdrMesTypeEncode3` at `0x180013378`
- `RPCRT4!NdrMesTypeEncode3` at `0x180013378`
- `RPCRT4!NdrMesTypeFree3` at `0x1800134a6`
- `RPCRT4!NdrMesTypeFree3` at `0x1800134a6`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800132e7`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800132e7`
- `RPCRT4!MesHandleFree` at `0x1800133d2`
- `RPCRT4!MesHandleFree` at `0x18001354f`
- `RPCRT4!MesHandleFree` at `0x1800133d2`
- `RPCRT4!MesHandleFree` at `0x18001354f`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800133f2`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800133f2`

## pseudocode

```c
__int64 __fastcall RedirectedSCardControl(
        __int64 a1,
        unsigned int a2,
        const void *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned int SCardError; // ebx
  unsigned __int8 *v13; // rsi
  int v14; // eax
  unsigned int v15; // r8d
  unsigned int *v16; // rax
  handle_t pHandle; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v18; // [rsp+48h] [rbp-90h]
  char *pBuffer; // [rsp+50h] [rbp-88h] BYREF
  struct _BUFFER_LIST_STRUCT *v20; // [rsp+58h] [rbp-80h] BYREF
  unsigned __int8 *v21[2]; // [rsp+60h] [rbp-78h] BYREF
  __int128 pObject; // [rsp+70h] [rbp-68h] BYREF
  __int128 v23; // [rsp+80h] [rbp-58h]
  __int128 v24; // [rsp+90h] [rbp-48h]
  __int64 v25; // [rsp+A0h] [rbp-38h]
  unsigned int pEncodedSize; // [rsp+E0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v20 = 0;
  pObject = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  *(_OWORD *)v21 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    v23 = *(_OWORD *)(a1 + 24);
    *(_QWORD *)&v24 = __PAIR64__(a4, a2);
    *((_QWORD *)&v24 + 1) = a3;
    v13 = a5;
    LODWORD(v25) = a5 == 0;
    HIDWORD(v25) = a6;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x22u, &pObject);
    v14 = _SendSCardIOCTL(0x900D4u, pBuffer, pEncodedSize, &v20, **(LPCRITICAL_SECTION **)a1, 0xFFFFFFFF, 0x800u);
    if ( v14 )
    {
      SCardError = _MakeSCardError(v14);
      goto LABEL_13;
    }
    if ( pHandle )
    {
      MesHandleFree(pHandle);
      pHandle = 0;
    }
    if ( !MesDecodeBufferHandleCreate(*((char **)v20 + 2), *((_DWORD *)v20 + 7), &pHandle) )
    {
      *(_OWORD *)v21 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x23u, v21);
      SCardError = (unsigned int)v21[0];
      v18 = (unsigned int)v21[0];
      if ( !LODWORD(v21[0]) )
      {
        v15 = HIDWORD(v21[0]);
        v16 = a7;
        *a7 = HIDWORD(v21[0]);
        SCardError = _CopyReturnToCallerBuffer(*(struct _REDIR_LOCAL_SCARDCONTEXT **)a1, v21[1], v15, v13, v16, 1u);
        v18 = SCardError;
      }
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x23u, v21);
      goto LABEL_13;
    }
  }
  SCardError = -2146435041;
LABEL_13:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  MIDL_user_free(pBuffer);
  if ( v20 )
    *((_DWORD *)v20 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18001326c  mov     r11, rsp
0x18001326f  push    rbx
0x180013270  push    rsi
0x180013271  push    rdi
0x180013272  push    r14
0x180013274  sub     rsp, 0B8h
0x18001327b  mov     ebx, r9d
0x18001327e  mov     rsi, r8
0x180013281  mov     r14d, edx
0x180013284  mov     rdi, rcx
0x180013287  mov     [rsp+0D8h+pBuffer], 0
0x180013290  mov     dword ptr [r11+8], 0
0x180013298  mov     [rsp+0D8h+pHandle], 0
0x1800132a1  mov     qword ptr [r11-80h], 0
0x1800132a9  xorps   xmm0, xmm0
0x1800132ac  xor     eax, eax
0x1800132ae  movups  [rsp+0D8h+var_68], xmm0
0x1800132b3  movups  xmmword ptr [r11-58h], xmm0
0x1800132b8  movups  xmmword ptr [r11-48h], xmm0
0x1800132bd  mov     [r11-38h], rax
0x1800132c1  movups  xmmword ptr [rsp+0D8h+var_78], xmm0
0x1800132c6  test    rcx, rcx
0x1800132c9  jnz     short loc_1800132D5
0x1800132cb  mov     eax, 80100004h
0x1800132d0  jmp     loc_18001357B
0x1800132d5  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x1800132da  lea     rdx, [rsp+0D8h+pEncodedSize]; pEncodedSize
0x1800132e2  lea     rcx, [rsp+0D8h+pBuffer]; pBuffer
0x1800132e7  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x1800132ed  test    eax, eax
0x1800132ef  jz      short loc_1800132FB
0x1800132f1  mov     ebx, 8010001Fh
0x1800132f6  jmp     loc_180013545
0x1800132fb  movups  xmm0, xmmword ptr [rdi+8]
0x1800132ff  movups  [rsp+0D8h+var_68], xmm0
0x180013304  movups  xmm1, xmmword ptr [rdi+18h]
0x180013308  movups  [rsp+0D8h+var_58], xmm1
0x180013310  mov     [rsp+0D8h+var_48], r14d
0x180013318  mov     [rsp+0D8h+var_44], ebx
0x18001331f  mov     [rsp+0D8h+var_40], rsi
0x180013327  xor     eax, eax
0x180013329  mov     rsi, [rsp+0D8h+arg_20]
0x180013331  test    rsi, rsi
0x180013334  setz    al
0x180013337  mov     [rsp+0D8h+var_38], eax
0x18001333e  mov     eax, [rsp+0D8h+arg_28]
0x180013345  mov     [rsp+0D8h+var_34], eax
0x18001334c  lea     rax, [rsp+0D8h+var_68]
0x180013351  mov     [rsp+0D8h+pObject], rax; pObject
0x180013356  mov     [rsp+0D8h+nTypeIndex], 22h ; '"'; nTypeIndex
0x18001335e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180013365  lea     r8, pProxyInfo; pProxyInfo
0x18001336c  lea     rdx, pPicklingInfo; pPicklingInfo
0x180013373  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x180013378  call    cs:__imp_NdrMesTypeEncode3
0x18001337e  nop
0x18001337f  mov     rax, [rdi]
0x180013382  mov     [rsp+0D8h+var_A8], 800h; unsigned int
0x18001338a  mov     dword ptr [rsp+0D8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x180013392  mov     rax, [rax]
0x180013395  mov     qword ptr [rsp+0D8h+nTypeIndex], rax; lpCriticalSection
0x18001339a  lea     r9, [rsp+0D8h+var_80]; struct _BUFFER_LIST_STRUCT **
0x18001339f  mov     r8d, [rsp+0D8h+pEncodedSize]; InputBufferLength
0x1800133a7  mov     rdx, [rsp+0D8h+pBuffer]; InputBuffer
0x1800133ac  mov     ecx, 900D4h; IoControlCode
0x1800133b1  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x1800133b6  test    eax, eax
0x1800133b8  jz      short loc_1800133C8
0x1800133ba  mov     ecx, eax; int
0x1800133bc  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x1800133c1  mov     ebx, eax
0x1800133c3  jmp     loc_180013545
0x1800133c8  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x1800133cd  test    rcx, rcx
0x1800133d0  jz      short loc_1800133E1
0x1800133d2  call    cs:__imp_MesHandleFree
0x1800133d8  mov     [rsp+0D8h+pHandle], 0
0x1800133e1  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x1800133e6  mov     rcx, [rsp+0D8h+var_80]
0x1800133eb  mov     edx, [rcx+1Ch]; BufferSize
0x1800133ee  mov     rcx, [rcx+10h]; Buffer
0x1800133f2  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800133f8  test    eax, eax
0x1800133fa  jnz     loc_1800132F1
0x180013400  xorps   xmm0, xmm0
0x180013403  movups  xmmword ptr [rsp+0D8h+var_78], xmm0
0x180013408  lea     rax, [rsp+0D8h+var_78]
0x18001340d  mov     [rsp+0D8h+pObject], rax; pObject
0x180013412  mov     r14d, 23h ; '#'
0x180013418  mov     [rsp+0D8h+nTypeIndex], r14d; nTypeIndex
0x18001341d  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180013424  lea     r8, pProxyInfo; pProxyInfo
0x18001342b  lea     rdx, pPicklingInfo; pPicklingInfo
0x180013432  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x180013437  call    cs:__imp_NdrMesTypeDecode3
0x18001343d  nop
0x18001343e  mov     ebx, dword ptr [rsp+0D8h+var_78]
0x180013442  mov     [rsp+0D8h+var_90], ebx
0x180013446  test    ebx, ebx
0x180013448  jnz     short loc_18001347D
0x18001344a  mov     r8d, dword ptr [rsp+0D8h+var_78+4]; unsigned int
0x18001344f  mov     rax, [rsp+0D8h+arg_30]
0x180013457  mov     [rax], r8d
0x18001345a  mov     dword ptr [rsp+0D8h+pObject], 1; unsigned int
0x180013462  mov     qword ptr [rsp+0D8h+nTypeIndex], rax; unsigned int *
0x180013467  mov     r9, rsi; unsigned __int8 *
0x18001346a  mov     rdx, [rsp+0D8h+var_78+8]; unsigned __int8 *
0x18001346f  mov     rcx, [rdi]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x180013472  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x180013477  mov     ebx, eax
0x180013479  mov     [rsp+0D8h+var_90], eax
0x18001347d  lea     rax, [rsp+0D8h+var_78]
0x180013482  mov     [rsp+0D8h+pObject], rax; pObject
0x180013487  mov     [rsp+0D8h+nTypeIndex], r14d; nTypeIndex
0x18001348c  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180013493  lea     r8, pProxyInfo; pProxyInfo
0x18001349a  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800134a1  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x1800134a6  call    cs:__imp_NdrMesTypeFree3
0x1800134ac  jmp     loc_180013545
0x1800134b1  mov     ebx, [rsp+0D8h+var_90]
0x1800134b5  jmp     loc_180013545
0x1800134ba  mov     ebx, eax
0x1800134bc  mov     edx, 2
0x1800134c1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800134c6  lea     rax, WPP_GLOBAL_Control
0x1800134cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134d4  cmp     rcx, rax
0x1800134d7  jz      short loc_1800134FE
0x1800134d9  test    byte ptr [rcx+1Ch], 8
0x1800134dd  jz      short loc_1800134FE
0x1800134df  cmp     byte ptr [rcx+19h], 2
0x1800134e3  jb      short loc_1800134FE
0x1800134e5  mov     edx, 4Dh ; 'M'
0x1800134ea  mov     [rsp+0D8h+nTypeIndex], ebx
0x1800134ee  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x1800134f5  mov     rcx, [rcx+10h]
0x1800134f9  call    WPP_SF_sd
0x1800134fe  jmp     short loc_180013545
0x180013500  mov     ebx, eax
0x180013502  mov     edx, 2
0x180013507  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001350c  lea     rax, WPP_GLOBAL_Control
0x180013513  mov     rcx, cs:WPP_GLOBAL_Control
0x18001351a  cmp     rcx, rax
0x18001351d  jz      short loc_180013545
0x18001351f  test    byte ptr [rcx+1Ch], 8
0x180013523  jz      short loc_180013545
0x180013525  cmp     byte ptr [rcx+19h], 2
0x180013529  jb      short loc_180013545
0x18001352b  mov     edx, 4Ch ; 'L'
0x180013530  mov     [rsp+0D8h+nTypeIndex], ebx
0x180013534  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001353b  mov     rcx, [rcx+10h]
0x18001353f  call    WPP_SF_sd
0x180013544  nop
0x180013545  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18001354a  test    rcx, rcx
0x18001354d  jz      short loc_18001355E
0x18001354f  call    cs:__imp_MesHandleFree
0x180013555  mov     [rsp+0D8h+pHandle], 0
0x18001355e  mov     rcx, [rsp+0D8h+pBuffer]; void *
0x180013563  call    MIDL_user_free
0x180013568  mov     rax, [rsp+0D8h+var_80]
0x18001356d  test    rax, rax
0x180013570  jz      short loc_180013579
0x180013572  mov     dword ptr [rax+8], 0
0x180013579  mov     eax, ebx
0x18001357b  add     rsp, 0B8h
0x180013582  pop     r14
0x180013584  pop     rdi
0x180013585  pop     rsi
0x180013586  pop     rbx
0x180013587  retn
```
