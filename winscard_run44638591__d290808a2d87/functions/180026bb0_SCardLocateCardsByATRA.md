# SCardLocateCardsByATRA

- ea: `0x180026bb0`
- end: `0x180026d42`
- name: `SCardLocateCardsByATRA`
- size: `402`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPSCARD_ATRMASK rgAtrMasks, DWORD cAtrs, LPSCARD_READERSTATEA rgReaderStates, DWORD cReaders)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026640`

## callees

- `0x180004ca0`
- `0x18000e3d0`
- `0x1800126f0`
- `0x180024634`
- `0x180026bb0`
- `0x18002cf64`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026bff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026bff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LONG __stdcall SCardLocateCardsByATRA(
        SCARDCONTEXT hContext,
        LPSCARD_ATRMASK rgAtrMasks,
        DWORD cAtrs,
        LPSCARD_READERSTATEA rgReaderStates,
        DWORD cReaders)
{
  LONG CardsByATRA; // edi
  CHandleList *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v13; // r15
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rax
  int v16; // ecx
  DWORD i; // ebx
  const unsigned __int16 *v18; // rdx
  ulong pExceptionObject; // [rsp+38h] [rbp-70h] BYREF
  ulong v21; // [rsp+3Ch] [rbp-6Ch] BYREF
  ulong v22; // [rsp+40h] [rbp-68h] BYREF
  const int *v23; // [rsp+48h] [rbp-60h] BYREF
  const unsigned __int16 *v24; // [rsp+50h] [rbp-58h]
  int v25; // [rsp+58h] [rbp-50h]
  int v26; // [rsp+5Ch] [rbp-4Ch]
  LONG v27; // [rsp+60h] [rbp-48h] BYREF
  char *v28; // [rsp+68h] [rbp-40h]

  CardsByATRA = 0;
  try
  {
    if ( !rgReaderStates )
    {
      pExceptionObject = -2146435068;
      throw &pExceptionObject;
    }
    v10 = g_phlContexts;
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v28 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v10, hContext);
    if ( !HandlePtr )
    {
      v21 = 6;
      throw &v21;
    }
    v13 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v11);
    if ( *(_DWORD *)(v13 + 16) )
    {
      v22 = -2146435042;
      throw &v22;
    }
    v14 = *(_QWORD *)(v13 + 128);
    if ( v14 )
    {
      CardsByATRA = RedirectedSCardLocateCardsByATRA(
                      v14,
                      rgAtrMasks,
                      cAtrs,
                      (struct SCARD_READERSTATEW *)rgReaderStates,
                      cReaders);
    }
    else
    {
      v23 = &CBuffer::`vftable';
      v15 = 0;
      v24 = 0;
      v25 = 0;
      v16 = 0;
      v26 = 0;
      for ( i = 0; i < cReaders; ++i )
      {
        MStrAdd((struct CBuffer *)&v23, rgReaderStates[(unsigned __int64)i].szReader);
        v16 = v26;
        v15 = v24;
      }
      v18 = &WideCharStr;
      if ( v16 )
        v18 = v15;
      CSCardUserContext::LocateCards(
        (CSCardUserContext *)v13,
        v18,
        rgAtrMasks,
        cAtrs,
        (struct SCARD_READERSTATEW *)rgReaderStates,
        cReaders);
      v23 = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)&v23);
    }
  }
  catch ( ulong v27 )
  {
    return v27;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return CardsByATRA;
}

```

## disassembly

```asm
0x180026bb0  push    rbx
0x180026bb2  push    rsi
0x180026bb3  push    rdi
0x180026bb4  push    r12
0x180026bb6  push    r13
0x180026bb8  push    r14
0x180026bba  push    r15
0x180026bbc  sub     rsp, 70h
0x180026bc0  mov     rsi, r9
0x180026bc3  mov     r12d, r8d
0x180026bc6  mov     r13, rdx
0x180026bc9  mov     r15, rcx
0x180026bcc  xor     edi, edi
0x180026bce  test    r9, r9
0x180026bd1  jnz     short loc_180026BEC
0x180026bd3  mov     [rsp+0A8h+pExceptionObject], 80100004h
0x180026bdb  lea     rdx, _TI1K; pThrowInfo
0x180026be2  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180026be7  call    _CxxThrowException_0
0x180026bec  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180026bf3  lea     r14, [rbx+20h]
0x180026bf7  mov     [rsp+0A8h+var_40], r14
0x180026bfc  mov     rcx, r14; lpCriticalSection
0x180026bff  call    cs:__imp_EnterCriticalSection
0x180026c05  nop
0x180026c06  mov     rdx, r15; unsigned __int64
0x180026c09  mov     rcx, rbx; this
0x180026c0c  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180026c11  test    rax, rax
0x180026c14  jnz     short loc_180026C2F
0x180026c16  mov     [rsp+0A8h+var_6C], 6
0x180026c1e  lea     rdx, _TI1K; pThrowInfo
0x180026c25  lea     rcx, [rsp+0A8h+var_6C]; pExceptionObject
0x180026c2a  call    _CxxThrowException_0
0x180026c2f  mov     r15, [rax]
0x180026c32  mov     rcx, r14; lpCriticalSection
0x180026c35  call    cs:__imp_LeaveCriticalSection
0x180026c3b  xor     r8d, r8d
0x180026c3e  cmp     [r15+10h], r8d
0x180026c42  jz      short loc_180026C5D
0x180026c44  mov     [rsp+0A8h+var_68], 8010001Eh
0x180026c4c  lea     rdx, _TI1K; pThrowInfo
0x180026c53  lea     rcx, [rsp+0A8h+var_68]; pExceptionObject
0x180026c58  call    _CxxThrowException_0
0x180026c5d  mov     rcx, [r15+80h]; unsigned __int64
0x180026c64  test    rcx, rcx
0x180026c67  jz      short loc_180026C8D
0x180026c69  mov     eax, [rsp+0A8h+cReaders]
0x180026c70  mov     dword ptr [rsp+0A8h+var_88], eax; unsigned int
0x180026c74  mov     r9, rsi; struct SCARD_READERSTATEA *
0x180026c77  mov     r8d, r12d; unsigned int
0x180026c7a  mov     rdx, r13; struct _SCARD_ATRMASK *
0x180026c7d  call    ?RedirectedSCardLocateCardsByATRA@@YAJ_KPEAU_SCARD_ATRMASK@@KPEAUSCARD_READERSTATEA@@K@Z; RedirectedSCardLocateCardsByATRA(unsigned __int64,_SCARD_ATRMASK *,ulong,SCARD_READERSTATEA *,ulong)
0x180026c82  mov     edi, eax
0x180026c84  mov     [rsp+0A8h+var_78], eax
0x180026c88  jmp     loc_180026D28
0x180026c8d  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180026c94  mov     [rsp+0A8h+var_60], rax
0x180026c99  mov     rax, r8
0x180026c9c  mov     [rsp+0A8h+var_58], rax
0x180026ca1  mov     [rsp+0A8h+var_50], r8d
0x180026ca6  mov     ecx, r8d
0x180026ca9  mov     [rsp+0A8h+var_4C], ecx
0x180026cad  mov     [rsp+0A8h+var_74], r8d
0x180026cb2  mov     ebx, r8d
0x180026cb5  mov     [rsp+0A8h+var_74], ebx
0x180026cb9  mov     r14d, [rsp+0A8h+cReaders]
0x180026cc1  cmp     ebx, r14d
0x180026cc4  jnb     short loc_180026CEB
0x180026cc6  mov     edx, ebx
0x180026cc8  shl     rdx, 6
0x180026ccc  mov     rdx, [rdx+rsi]; char *
0x180026cd0  lea     rcx, [rsp+0A8h+var_60]; struct CBuffer *
0x180026cd5  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBD@Z; MStrAdd(CBuffer &,char const *)
0x180026cda  inc     ebx
0x180026cdc  mov     [rsp+0A8h+var_74], ebx
0x180026ce0  mov     ecx, [rsp+0A8h+var_4C]
0x180026ce4  mov     rax, [rsp+0A8h+var_58]
0x180026ce9  jmp     short loc_180026CC1
0x180026ceb  lea     rdx, WideCharStr
0x180026cf2  test    ecx, ecx
0x180026cf4  cmovnz  rdx, rax; unsigned __int16 *
0x180026cf8  mov     [rsp+0A8h+var_80], r14d; unsigned int
0x180026cfd  mov     [rsp+0A8h+var_88], rsi; struct SCARD_READERSTATEW *
0x180026d02  mov     r9d, r12d; unsigned int
0x180026d05  mov     r8, r13; struct _SCARD_ATRMASK *
0x180026d08  mov     rcx, r15; this
0x180026d0b  call    ?LocateCards@CSCardUserContext@@QEAAXPEBGPEAU_SCARD_ATRMASK@@KPEAUSCARD_READERSTATEW@@K@Z; CSCardUserContext::LocateCards(ushort const *,_SCARD_ATRMASK *,ulong,SCARD_READERSTATEW *,ulong)
0x180026d10  nop
0x180026d11  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180026d18  mov     [rsp+0A8h+var_60], rax
0x180026d1d  lea     rcx, [rsp+0A8h+var_60]; this
0x180026d22  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180026d27  nop
0x180026d28  jmp     short loc_180026D30
0x180026d2a  jmp     short $+2
0x180026d2c  mov     edi, [rsp+0A8h+var_78]
0x180026d30  mov     eax, edi
0x180026d32  add     rsp, 70h
0x180026d36  pop     r15
0x180026d38  pop     r14
0x180026d3a  pop     r13
0x180026d3c  pop     r12
0x180026d3e  pop     rdi
0x180026d3f  pop     rsi
0x180026d40  pop     rbx
0x180026d41  retn
```
