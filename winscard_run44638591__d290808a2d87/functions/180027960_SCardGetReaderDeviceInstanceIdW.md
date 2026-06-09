# SCardGetReaderDeviceInstanceIdW

- ea: `0x180027960`
- end: `0x180027abf`
- name: `SCardGetReaderDeviceInstanceIdW`
- size: `351`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000227c`
- `0x1800093e4`
- `0x18000e3d0`
- `0x180010898`
- `0x1800126f0`
- `0x18001a538`
- `0x180027960`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800279af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800279af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800279e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800279e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SCardGetReaderDeviceInstanceIdW(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v8; // edi
  CHandleList *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v12; // rbx
  ulong pExceptionObject; // [rsp+28h] [rbp-70h] BYREF
  ulong v18; // [rsp+2Ch] [rbp-6Ch] BYREF
  ulong v19; // [rsp+30h] [rbp-68h] BYREF
  ulong v20; // [rsp+34h] [rbp-64h] BYREF
  ulong v21; // [rsp+38h] [rbp-60h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-58h] BYREF
  int v23; // [rsp+50h] [rbp-48h]
  int v24; // [rsp+54h] [rbp-44h]
  ulong v25; // [rsp+58h] [rbp-40h] BYREF

  v8 = 0;
  try
  {
    if ( !a4 )
    {
      pExceptionObject = -2146435068;
      throw &pExceptionObject;
    }
    v9 = g_phlContexts;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v9, a1);
    if ( !HandlePtr )
    {
      v18 = 6;
      throw &v18;
    }
    v12 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v10);
    if ( *(_DWORD *)(v12 + 16) )
    {
      v19 = -2146435042;
      throw &v19;
    }
    if ( *(_QWORD *)(v12 + 128) || !RedirectionContextIsLocal(0) )
    {
      if ( RedirectDisabled() )
      {
        v20 = -2146435043;
        throw &v20;
      }
      v21 = -2146435049;
      throw &v21;
    }
    v22[0] = &CBuffer::`vftable';
    v22[1] = 0;
    v23 = 0;
    v24 = 0;
    CSCardUserContext::GetReaderDeviceInstanceId((CSCardUserContext *)v12, a2, (struct CBuffer *)v22);
    PlaceResult((struct CSCardUserContext *)v12, (struct CBuffer *)v22, a3, a4);
    v22[0] = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)v22);
  }
  catch ( ulong v25 )
  {
    return v25;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v8;
}

```

## disassembly

```asm
0x180027960  push    rbx
0x180027962  push    rsi
0x180027963  push    rdi
0x180027964  push    r12
0x180027966  push    r13
0x180027968  push    r14
0x18002796a  push    r15
0x18002796c  sub     rsp, 60h
0x180027970  mov     r14, r9
0x180027973  mov     r12, r8
0x180027976  mov     r13, rdx
0x180027979  mov     r15, rcx
0x18002797c  xor     edi, edi
0x18002797e  test    r9, r9
0x180027981  jnz     short loc_18002799C
0x180027983  mov     [rsp+98h+pExceptionObject], 80100004h
0x18002798b  lea     rdx, _TI1K; pThrowInfo
0x180027992  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180027997  call    _CxxThrowException_0
0x18002799c  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x1800279a3  lea     rsi, [rbx+20h]
0x1800279a7  mov     [rsp+98h+var_78], rsi
0x1800279ac  mov     rcx, rsi; lpCriticalSection
0x1800279af  call    cs:__imp_EnterCriticalSection
0x1800279b5  nop
0x1800279b6  mov     rdx, r15; unsigned __int64
0x1800279b9  mov     rcx, rbx; this
0x1800279bc  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800279c1  xor     r15d, r15d
0x1800279c4  test    rax, rax
0x1800279c7  jnz     short loc_1800279E2
0x1800279c9  mov     [rsp+98h+var_6C], 6
0x1800279d1  lea     rdx, _TI1K; pThrowInfo
0x1800279d8  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x1800279dd  call    _CxxThrowException_0
0x1800279e2  mov     rbx, [rax]
0x1800279e5  mov     rcx, rsi; lpCriticalSection
0x1800279e8  call    cs:__imp_LeaveCriticalSection
0x1800279ee  cmp     [rbx+10h], r15d
0x1800279f2  jz      short loc_180027A0D
0x1800279f4  mov     [rsp+98h+var_68], 8010001Eh
0x1800279fc  lea     rdx, _TI1K; pThrowInfo
0x180027a03  lea     rcx, [rsp+98h+var_68]; pExceptionObject
0x180027a08  call    _CxxThrowException_0
0x180027a0d  cmp     [rbx+80h], r15
0x180027a14  jnz     short loc_180027A72
0x180027a16  xor     ecx, ecx; lpCriticalSection
0x180027a18  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180027a1d  test    al, al
0x180027a1f  jz      short loc_180027A72
0x180027a21  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180027a28  mov     [rsp+98h+var_58], rsi
0x180027a2d  mov     [rsp+98h+var_50], r15
0x180027a32  mov     [rsp+98h+var_48], r15d
0x180027a37  mov     [rsp+98h+var_44], r15d
0x180027a3c  lea     r8, [rsp+98h+var_58]; struct CBuffer *
0x180027a41  mov     rdx, r13; unsigned __int16 *
0x180027a44  mov     rcx, rbx; this
0x180027a47  call    ?GetReaderDeviceInstanceId@CSCardUserContext@@QEAAJPEBGAEAVCBuffer@@@Z; CSCardUserContext::GetReaderDeviceInstanceId(ushort const *,CBuffer &)
0x180027a4c  mov     r9, r14; unsigned int *
0x180027a4f  mov     r8, r12; unsigned __int16 *
0x180027a52  lea     rdx, [rsp+98h+var_58]; struct CBuffer *
0x180027a57  mov     rcx, rbx; struct CSCardUserContext *
0x180027a5a  call    ?PlaceResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAGPEAK@Z; PlaceResult(CSCardUserContext *,CBuffer &,ushort *,ulong *)
0x180027a5f  nop
0x180027a60  mov     [rsp+98h+var_58], rsi
0x180027a65  lea     rcx, [rsp+98h+var_58]; this
0x180027a6a  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180027a6f  nop
0x180027a70  jmp     short loc_180027AAD
0x180027a72  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180027a77  lea     rdx, _TI1K; pThrowInfo
0x180027a7e  test    al, al
0x180027a80  jz      short loc_180027A94
0x180027a82  mov     [rsp+98h+var_64], 8010001Dh
0x180027a8a  lea     rcx, [rsp+98h+var_64]; pExceptionObject
0x180027a8f  call    _CxxThrowException_0
0x180027a94  mov     [rsp+98h+var_60], 80100017h
0x180027a9c  lea     rcx, [rsp+98h+var_60]; pExceptionObject
0x180027aa1  call    _CxxThrowException_0
0x180027aa7  jmp     short $+2
0x180027aa9  mov     edi, dword ptr [rsp+98h+var_78]
0x180027aad  mov     eax, edi
0x180027aaf  add     rsp, 60h
0x180027ab3  pop     r15
0x180027ab5  pop     r14
0x180027ab7  pop     r13
0x180027ab9  pop     r12
0x180027abb  pop     rdi
0x180027abc  pop     rsi
0x180027abd  pop     rbx
0x180027abe  retn
```
