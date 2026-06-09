# SCardState

- ea: `0x180023820`
- end: `0x1800239b2`
- name: `SCardState`
- size: `402`
- prototype: `LONG __stdcall(SCARDHANDLE hCard, LPDWORD pdwState, LPDWORD pdwProtocol, LPBYTE pbAtr, LPDWORD pcbAtrLen)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180003de0`
- `0x18000e3d0`
- `0x18000fd94`
- `0x1800126f0`
- `0x180023820`
- `0x18002dd0c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023854`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002388d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002388d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LONG __stdcall SCardState(SCARDHANDLE hCard, LPDWORD pdwState, LPDWORD pdwProtocol, LPBYTE pbAtr, LPDWORD pcbAtrLen)
{
  LONG v9; // edi
  CHandleList *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // r15
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  unsigned int v19; // [rsp+34h] [rbp-84h] BYREF
  unsigned int v20[2]; // [rsp+38h] [rbp-80h] BYREF
  ulong pExceptionObject; // [rsp+40h] [rbp-78h] BYREF
  ulong v22; // [rsp+44h] [rbp-74h] BYREF
  _QWORD v23[2]; // [rsp+48h] [rbp-70h] BYREF
  int v24; // [rsp+58h] [rbp-60h]
  int v25; // [rsp+5Ch] [rbp-5Ch]
  _QWORD v26[2]; // [rsp+60h] [rbp-58h] BYREF
  int v27; // [rsp+70h] [rbp-48h]
  int v28; // [rsp+74h] [rbp-44h]
  LONG v29; // [rsp+78h] [rbp-40h] BYREF

  v9 = 0;
  try
  {
    v10 = g_phlReaders;
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlReaders + 32);
    *(_QWORD *)v20 = (char *)g_phlReaders + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlReaders + 32));
    HandlePtr = CHandleList::GetHandlePtr(v10, hCard);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v13 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v11);
    if ( *(_DWORD *)(v13 + 16) )
    {
      v22 = -2146435042;
      throw &v22;
    }
    v14 = *(_QWORD *)(v13 + 40);
    if ( v14 )
    {
      v9 = RedirectedSCardState(v14, pdwState, pdwProtocol, pbAtr, pcbAtrLen);
    }
    else
    {
      v23[0] = &CBuffer::`vftable';
      v23[1] = 0;
      v24 = 0;
      v25 = 0;
      v26[0] = &CBuffer::`vftable';
      v26[1] = 0;
      v27 = 0;
      v28 = 0;
      v19 = 0;
      v20[0] = 0;
      CReaderContext::Status((CReaderContext *)v13, &v19, v20, (struct CBuffer *)v23, (struct CBuffer *)v26);
      if ( pdwState )
        *pdwState = v19;
      if ( pdwProtocol )
        *pdwProtocol = v20[0];
      if ( pcbAtrLen )
        PlaceResult(
          *(struct CSCardUserContext **)(*(_QWORD *)(v13 + 24) + 40LL),
          (struct CBuffer *)v23,
          pbAtr,
          pcbAtrLen);
      v26[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v26);
      v23[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v23);
    }
  }
  catch ( ulong v29 )
  {
    return v29;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v9;
}

```

## disassembly

```asm
0x180023820  push    rbx
0x180023822  push    rsi
0x180023823  push    rdi
0x180023824  push    r12
0x180023826  push    r13
0x180023828  push    r14
0x18002382a  push    r15
0x18002382c  sub     rsp, 80h
0x180023833  mov     r13, r9
0x180023836  mov     rsi, r8
0x180023839  mov     r14, rdx
0x18002383c  mov     r12, rcx
0x18002383f  xor     edi, edi
0x180023841  mov     rbx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; CHandleList * g_phlReaders
0x180023848  lea     r15, [rbx+20h]
0x18002384c  mov     qword ptr [rsp+0B8h+var_80], r15
0x180023851  mov     rcx, r15; lpCriticalSection
0x180023854  call    cs:__imp_EnterCriticalSection
0x18002385a  nop
0x18002385b  mov     rdx, r12; unsigned __int64
0x18002385e  mov     rcx, rbx; this
0x180023861  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180023866  xor     r12d, r12d
0x180023869  test    rax, rax
0x18002386c  jnz     short loc_180023887
0x18002386e  mov     [rsp+0B8h+pExceptionObject], 6
0x180023876  lea     rdx, _TI1K; pThrowInfo
0x18002387d  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180023882  call    _CxxThrowException_0
0x180023887  mov     rbx, [rax]
0x18002388a  mov     rcx, r15; lpCriticalSection
0x18002388d  call    cs:__imp_LeaveCriticalSection
0x180023893  cmp     [rbx+10h], r12d
0x180023897  jz      short loc_1800238B2
0x180023899  mov     [rsp+0B8h+var_74], 8010001Eh
0x1800238a1  lea     rdx, _TI1K; pThrowInfo
0x1800238a8  lea     rcx, [rsp+0B8h+var_74]; pExceptionObject
0x1800238ad  call    _CxxThrowException_0
0x1800238b2  mov     rcx, [rbx+28h]; unsigned __int64
0x1800238b6  test    rcx, rcx
0x1800238b9  jz      short loc_1800238E1
0x1800238bb  mov     rax, [rsp+0B8h+pcbAtrLen]
0x1800238c3  mov     [rsp+0B8h+var_98], rax; unsigned int *
0x1800238c8  mov     r9, r13; unsigned __int8 *
0x1800238cb  mov     r8, rsi; unsigned int *
0x1800238ce  mov     rdx, r14; unsigned int *
0x1800238d1  call    ?RedirectedSCardState@@YAJ_KPEAK1PEAE1@Z; RedirectedSCardState(unsigned __int64,ulong *,ulong *,uchar *,ulong *)
0x1800238d6  mov     edi, eax
0x1800238d8  mov     [rsp+0B8h+var_88], eax
0x1800238dc  jmp     loc_180023995
0x1800238e1  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800238e8  mov     [rsp+0B8h+var_70], r15
0x1800238ed  mov     [rsp+0B8h+var_68], r12
0x1800238f2  mov     [rsp+0B8h+var_60], r12d
0x1800238f7  mov     [rsp+0B8h+var_5C], r12d
0x1800238fc  mov     [rsp+0B8h+var_58], r15
0x180023901  mov     [rsp+0B8h+var_50], r12
0x180023906  mov     [rsp+0B8h+var_48], r12d
0x18002390b  mov     [rsp+0B8h+var_44], r12d
0x180023910  mov     [rsp+0B8h+var_84], r12d
0x180023915  mov     [rsp+0B8h+var_80], r12d
0x18002391a  lea     rax, [rsp+0B8h+var_58]
0x18002391f  mov     [rsp+0B8h+var_98], rax; struct CBuffer *
0x180023924  lea     r9, [rsp+0B8h+var_70]; struct CBuffer *
0x180023929  lea     r8, [rsp+0B8h+var_80]; unsigned int *
0x18002392e  lea     rdx, [rsp+0B8h+var_84]; unsigned int *
0x180023933  mov     rcx, rbx; this
0x180023936  call    ?Status@CReaderContext@@QEAAXPEAK0AEAVCBuffer@@1@Z; CReaderContext::Status(ulong *,ulong *,CBuffer &,CBuffer &)
0x18002393b  test    r14, r14
0x18002393e  jz      short loc_180023947
0x180023940  mov     eax, [rsp+0B8h+var_84]
0x180023944  mov     [r14], eax
0x180023947  test    rsi, rsi
0x18002394a  jz      short loc_180023952
0x18002394c  mov     eax, [rsp+0B8h+var_80]
0x180023950  mov     [rsi], eax
0x180023952  mov     r9, [rsp+0B8h+pcbAtrLen]; unsigned int *
0x18002395a  test    r9, r9
0x18002395d  jz      short loc_180023975
0x18002395f  mov     rcx, [rbx+18h]
0x180023963  mov     r8, r13; unsigned __int8 *
0x180023966  lea     rdx, [rsp+0B8h+var_70]; struct CBuffer *
0x18002396b  mov     rcx, [rcx+28h]; struct CSCardUserContext *
0x18002396f  call    ?PlaceResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAEPEAK@Z; PlaceResult(CSCardUserContext *,CBuffer &,uchar *,ulong *)
0x180023974  nop
0x180023975  mov     [rsp+0B8h+var_58], r15
0x18002397a  lea     rcx, [rsp+0B8h+var_58]; this
0x18002397f  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180023984  nop
0x180023985  mov     [rsp+0B8h+var_70], r15
0x18002398a  lea     rcx, [rsp+0B8h+var_70]; this
0x18002398f  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180023994  nop
0x180023995  jmp     short loc_18002399D
0x180023997  jmp     short $+2
0x180023999  mov     edi, [rsp+0B8h+var_88]
0x18002399d  mov     eax, edi
0x18002399f  add     rsp, 80h
0x1800239a6  pop     r15
0x1800239a8  pop     r14
0x1800239aa  pop     r13
0x1800239ac  pop     r12
0x1800239ae  pop     rdi
0x1800239af  pop     rsi
0x1800239b0  pop     rbx
0x1800239b1  retn
```
