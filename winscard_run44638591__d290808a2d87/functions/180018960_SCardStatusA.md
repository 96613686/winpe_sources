# SCardStatusA

- ea: `0x180018960`
- end: `0x180018b41`
- name: `SCardStatusA`
- size: `481`
- prototype: `LONG __stdcall(SCARDHANDLE hCard, LPSTR mszReaderNames, LPDWORD pcchReaderLen, LPDWORD pdwState, LPDWORD pdwProtocol, LPBYTE pbAtr, LPDWORD pcbAtrLen)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003de0`
- `0x18000e3d0`
- `0x18000e470`
- `0x18000fd94`
- `0x1800126f0`
- `0x180018960`
- `0x180018b48`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018994`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018994`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LONG __stdcall SCardStatusA(
        SCARDHANDLE hCard,
        LPSTR mszReaderNames,
        LPDWORD pcchReaderLen,
        LPDWORD pdwState,
        LPDWORD pdwProtocol,
        LPBYTE pbAtr,
        LPDWORD pcbAtrLen)
{
  LONG v11; // edi
  CHandleList *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned int v21; // [rsp+44h] [rbp-84h] BYREF
  unsigned int v22[2]; // [rsp+48h] [rbp-80h] BYREF
  ulong pExceptionObject; // [rsp+50h] [rbp-78h] BYREF
  ulong v24; // [rsp+54h] [rbp-74h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-70h] BYREF
  int v26; // [rsp+68h] [rbp-60h]
  int v27; // [rsp+6Ch] [rbp-5Ch]
  _QWORD v28[2]; // [rsp+70h] [rbp-58h] BYREF
  int v29; // [rsp+80h] [rbp-48h]
  int v30; // [rsp+84h] [rbp-44h]
  LONG v31; // [rsp+88h] [rbp-40h] BYREF

  v11 = 0;
  try
  {
    v12 = g_phlReaders;
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlReaders + 32);
    *(_QWORD *)v22 = (char *)g_phlReaders + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlReaders + 32));
    HandlePtr = CHandleList::GetHandlePtr(v12, hCard);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v15 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v13);
    if ( *(_DWORD *)(v15 + 16) )
    {
      v24 = -2146435042;
      throw &v24;
    }
    v16 = *(_QWORD *)(v15 + 40);
    if ( v16 )
    {
      v11 = I_SCardStatus(
              v16,
              (unsigned __int8 *)mszReaderNames,
              pcchReaderLen,
              pdwState,
              pdwProtocol,
              pbAtr,
              pcbAtrLen,
              0);
    }
    else
    {
      v28[0] = &CBuffer::`vftable';
      v28[1] = 0;
      v29 = 0;
      v30 = 0;
      v25[0] = &CBuffer::`vftable';
      v25[1] = 0;
      v26 = 0;
      v27 = 0;
      v21 = 0;
      v22[0] = 0;
      CReaderContext::Status((CReaderContext *)v15, &v21, v22, (struct CBuffer *)v28, (struct CBuffer *)v25);
      if ( pdwState )
        *pdwState = v21;
      if ( pdwProtocol )
        *pdwProtocol = v22[0];
      if ( pcchReaderLen )
        PlaceMultiResult(
          *(struct CSCardUserContext **)(*(_QWORD *)(v15 + 24) + 40LL),
          (struct CBuffer *)v25,
          mszReaderNames,
          pcchReaderLen);
      if ( pcbAtrLen )
        PlaceResult(
          *(struct CSCardUserContext **)(*(_QWORD *)(v15 + 24) + 40LL),
          (struct CBuffer *)v28,
          pbAtr,
          pcbAtrLen);
      v25[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v25);
      v28[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v28);
    }
  }
  catch ( ulong v31 )
  {
    return v31;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v11;
}

```

## disassembly

```asm
0x180018960  push    rbx
0x180018962  push    rsi
0x180018963  push    rdi
0x180018964  push    r12
0x180018966  push    r13
0x180018968  push    r14
0x18001896a  push    r15
0x18001896c  sub     rsp, 90h
0x180018973  mov     r14, r9
0x180018976  mov     r15, r8
0x180018979  mov     r13, rdx
0x18001897c  mov     r12, rcx
0x18001897f  xor     edi, edi
0x180018981  mov     rbx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; CHandleList * g_phlReaders
0x180018988  lea     rsi, [rbx+20h]
0x18001898c  mov     qword ptr [rsp+0C8h+var_80], rsi
0x180018991  mov     rcx, rsi; lpCriticalSection
0x180018994  call    cs:__imp_EnterCriticalSection
0x18001899a  nop
0x18001899b  mov     rdx, r12; unsigned __int64
0x18001899e  mov     rcx, rbx; this
0x1800189a1  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800189a6  xor     r12d, r12d
0x1800189a9  test    rax, rax
0x1800189ac  jnz     short loc_1800189C7
0x1800189ae  mov     [rsp+0C8h+pExceptionObject], 6
0x1800189b6  lea     rdx, _TI1K; pThrowInfo
0x1800189bd  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800189c2  call    _CxxThrowException_0
0x1800189c7  mov     rbx, [rax]
0x1800189ca  mov     rcx, rsi; lpCriticalSection
0x1800189cd  call    cs:__imp_LeaveCriticalSection
0x1800189d3  cmp     [rbx+10h], r12d
0x1800189d7  jz      short loc_1800189F2
0x1800189d9  mov     [rsp+0C8h+var_74], 8010001Eh
0x1800189e1  lea     rdx, _TI1K; pThrowInfo
0x1800189e8  lea     rcx, [rsp+0C8h+var_74]; pExceptionObject
0x1800189ed  call    _CxxThrowException_0
0x1800189f2  mov     rcx, [rbx+28h]; unsigned __int64
0x1800189f6  test    rcx, rcx
0x1800189f9  jz      short loc_180018A40
0x1800189fb  mov     [rsp+0C8h+var_90], r12d; int
0x180018a00  mov     rax, [rsp+0C8h+pcbAtrLen]
0x180018a08  mov     [rsp+0C8h+var_98], rax; unsigned int *
0x180018a0d  mov     rax, [rsp+0C8h+pbAtr]
0x180018a15  mov     [rsp+0C8h+var_A0], rax; unsigned __int8 *
0x180018a1a  mov     rax, [rsp+0C8h+pdwProtocol]
0x180018a22  mov     [rsp+0C8h+var_A8], rax; unsigned int *
0x180018a27  mov     r9, r14; unsigned int *
0x180018a2a  mov     r8, r15; unsigned int *
0x180018a2d  mov     rdx, r13; unsigned __int8 *
0x180018a30  call    ?I_SCardStatus@@YAJ_KPEAEPEAK2212H@Z; I_SCardStatus(unsigned __int64,uchar *,ulong *,ulong *,ulong *,uchar *,ulong *,int)
0x180018a35  mov     edi, eax
0x180018a37  mov     [rsp+0C8h+var_88], eax
0x180018a3b  jmp     loc_180018B24
0x180018a40  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180018a47  mov     [rsp+0C8h+var_58], rsi
0x180018a4c  mov     [rsp+0C8h+var_50], r12
0x180018a51  mov     [rsp+0C8h+var_48], r12d
0x180018a59  mov     [rsp+0C8h+var_44], r12d
0x180018a61  mov     [rsp+0C8h+var_70], rsi
0x180018a66  mov     [rsp+0C8h+var_68], r12
0x180018a6b  mov     [rsp+0C8h+var_60], r12d
0x180018a70  mov     [rsp+0C8h+var_5C], r12d
0x180018a75  mov     [rsp+0C8h+var_84], r12d
0x180018a7a  mov     [rsp+0C8h+var_80], r12d
0x180018a7f  lea     rax, [rsp+0C8h+var_70]
0x180018a84  mov     [rsp+0C8h+var_A8], rax; struct CBuffer *
0x180018a89  lea     r9, [rsp+0C8h+var_58]; struct CBuffer *
0x180018a8e  lea     r8, [rsp+0C8h+var_80]; unsigned int *
0x180018a93  lea     rdx, [rsp+0C8h+var_84]; unsigned int *
0x180018a98  mov     rcx, rbx; this
0x180018a9b  call    ?Status@CReaderContext@@QEAAXPEAK0AEAVCBuffer@@1@Z; CReaderContext::Status(ulong *,ulong *,CBuffer &,CBuffer &)
0x180018aa0  test    r14, r14
0x180018aa3  jz      short loc_180018AAC
0x180018aa5  mov     eax, [rsp+0C8h+var_84]
0x180018aa9  mov     [r14], eax
0x180018aac  mov     rcx, [rsp+0C8h+pdwProtocol]
0x180018ab4  test    rcx, rcx
0x180018ab7  jz      short loc_180018ABF
0x180018ab9  mov     eax, [rsp+0C8h+var_80]
0x180018abd  mov     [rcx], eax
0x180018abf  test    r15, r15
0x180018ac2  jz      short loc_180018ADC
0x180018ac4  mov     rcx, [rbx+18h]
0x180018ac8  mov     r9, r15; unsigned int *
0x180018acb  mov     r8, r13; char *
0x180018ace  lea     rdx, [rsp+0C8h+var_70]; struct CBuffer *
0x180018ad3  mov     rcx, [rcx+28h]; this
0x180018ad7  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEADPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,char *,ulong *)
0x180018adc  mov     r9, [rsp+0C8h+pcbAtrLen]; unsigned int *
0x180018ae4  test    r9, r9
0x180018ae7  jz      short loc_180018B04
0x180018ae9  mov     rcx, [rbx+18h]
0x180018aed  mov     r8, [rsp+0C8h+pbAtr]; unsigned __int8 *
0x180018af5  lea     rdx, [rsp+0C8h+var_58]; struct CBuffer *
0x180018afa  mov     rcx, [rcx+28h]; struct CSCardUserContext *
0x180018afe  call    ?PlaceResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAEPEAK@Z; PlaceResult(CSCardUserContext *,CBuffer &,uchar *,ulong *)
0x180018b03  nop
0x180018b04  mov     [rsp+0C8h+var_70], rsi
0x180018b09  lea     rcx, [rsp+0C8h+var_70]; this
0x180018b0e  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180018b13  nop
0x180018b14  mov     [rsp+0C8h+var_58], rsi
0x180018b19  lea     rcx, [rsp+0C8h+var_58]; this
0x180018b1e  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180018b23  nop
0x180018b24  jmp     short loc_180018B2C
0x180018b26  jmp     short $+2
0x180018b28  mov     edi, [rsp+0C8h+var_88]
0x180018b2c  mov     eax, edi
0x180018b2e  add     rsp, 90h
0x180018b35  pop     r15
0x180018b37  pop     r14
0x180018b39  pop     r13
0x180018b3b  pop     r12
0x180018b3d  pop     rdi
0x180018b3e  pop     rsi
0x180018b3f  pop     rbx
0x180018b40  retn
```
