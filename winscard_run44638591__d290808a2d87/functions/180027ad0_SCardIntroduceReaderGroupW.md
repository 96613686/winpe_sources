# SCardIntroduceReaderGroupW

- ea: `0x180027ad0`
- end: `0x180027c42`
- name: `SCardIntroduceReaderGroupW`
- size: `370`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR szGroupName)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800093e4`
- `0x18000e090`
- `0x18000e680`
- `0x180010898`
- `0x1800126f0`
- `0x180012d80`
- `0x180027ad0`
- `0x18002b270`
- `0x18002b490`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b78`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LONG __stdcall SCardIntroduceReaderGroupW(SCARDCONTEXT hContext, LPCWSTR szGroupName)
{
  LONG v4; // edi
  __int64 v5; // rbx
  CHandleList *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v9; // rbx
  const unsigned __int16 *v10; // rax
  unsigned int v11; // ecx
  ulong pExceptionObject; // [rsp+24h] [rbp-74h] BYREF
  ulong v17; // [rsp+28h] [rbp-70h] BYREF
  ulong v18; // [rsp+2Ch] [rbp-6Ch] BYREF
  LONG v19; // [rsp+30h] [rbp-68h] BYREF
  void **v20; // [rsp+40h] [rbp-58h] BYREF
  int v21; // [rsp+48h] [rbp-50h]
  const int *v22; // [rsp+50h] [rbp-48h]
  __int64 v23; // [rsp+58h] [rbp-40h]
  int v24; // [rsp+60h] [rbp-38h]
  int v25; // [rsp+64h] [rbp-34h]
  const int *v26; // [rsp+68h] [rbp-30h]
  __int64 v27; // [rsp+70h] [rbp-28h]
  int v28; // [rsp+78h] [rbp-20h]
  int v29; // [rsp+7Ch] [rbp-1Ch]

  v4 = 0;
  try
  {
    v20 = &CTextString::`vftable';
    v22 = &CBuffer::`vftable';
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = &CBuffer::`vftable';
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v21 = 3;
    v5 = 0;
    if ( hContext )
    {
      v6 = g_phlContexts;
      v7 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
      HandlePtr = CHandleList::GetHandlePtr(v6, hContext);
      if ( !HandlePtr )
      {
        pExceptionObject = 6;
        throw &pExceptionObject;
      }
      v9 = *(_QWORD *)HandlePtr;
      LeaveCriticalSection(v7);
      if ( *(_DWORD *)(v9 + 16) )
      {
        v17 = -2146435042;
        throw &v17;
      }
      v5 = *(_QWORD *)(v9 + 128);
      if ( v5 )
        goto LABEL_27;
    }
    if ( !RedirectionContextIsLocal(0) )
    {
LABEL_27:
      if ( RedirectDisabled() )
      {
        v18 = -2146435043;
        throw &v18;
      }
      v4 = I_ContextAndStringCallWithLongReturn(v5, (const unsigned __int8 *)szGroupName, 1, 0x90054u);
    }
    else
    {
      CTextString::operator=(&v20, szGroupName);
      v10 = CTextString::Unicode((CTextString *)&v20);
      IntroduceReaderGroup(v11, v10);
    }
    CTextString::~CTextString((CTextString *)&v20);
  }
  catch ( ulong v19 )
  {
    return v19;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v4;
}

```

## disassembly

```asm
0x180027ad0  mov     r11, rsp
0x180027ad3  mov     [r11+8], rbx
0x180027ad7  mov     [r11+10h], rsi
0x180027adb  push    rdi
0x180027adc  push    r14
0x180027ade  push    r15
0x180027ae0  sub     rsp, 80h
0x180027ae7  mov     r15, rdx
0x180027aea  mov     rsi, rcx
0x180027aed  xor     edi, edi
0x180027aef  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180027af6  mov     [r11-58h], rax
0x180027afa  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180027b01  mov     [r11-48h], rax
0x180027b05  mov     [r11-40h], rdi
0x180027b09  mov     [rsp+98h+var_38], edi
0x180027b0d  mov     [rsp+98h+var_34], edi
0x180027b11  mov     [r11-30h], rax
0x180027b15  mov     [r11-28h], rdi
0x180027b19  mov     [rsp+98h+var_20], edi
0x180027b1d  mov     [rsp+98h+var_1C], edi
0x180027b21  mov     [rsp+98h+var_50], 3
0x180027b29  xor     ebx, ebx
0x180027b2b  test    rcx, rcx
0x180027b2e  jz      short loc_180027BA9
0x180027b30  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180027b37  lea     r14, [rbx+20h]
0x180027b3b  mov     [r11+18h], r14
0x180027b3f  mov     rcx, r14; lpCriticalSection
0x180027b42  call    cs:__imp_EnterCriticalSection
0x180027b48  nop
0x180027b49  mov     rdx, rsi; unsigned __int64
0x180027b4c  mov     rcx, rbx; this
0x180027b4f  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180027b54  test    rax, rax
0x180027b57  jnz     short loc_180027B72
0x180027b59  mov     [rsp+98h+pExceptionObject], 6
0x180027b61  lea     rdx, _TI1K; pThrowInfo
0x180027b68  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180027b6d  call    _CxxThrowException_0
0x180027b72  mov     rbx, [rax]
0x180027b75  mov     rcx, r14; lpCriticalSection
0x180027b78  call    cs:__imp_LeaveCriticalSection
0x180027b7e  cmp     dword ptr [rbx+10h], 0
0x180027b82  jz      short loc_180027B9D
0x180027b84  mov     [rsp+98h+var_70], 8010001Eh
0x180027b8c  lea     rdx, _TI1K; pThrowInfo
0x180027b93  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180027b98  call    _CxxThrowException_0
0x180027b9d  mov     rbx, [rbx+80h]
0x180027ba4  test    rbx, rbx
0x180027ba7  jnz     short loc_180027BD5
0x180027ba9  xor     ecx, ecx; lpCriticalSection
0x180027bab  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180027bb0  test    al, al
0x180027bb2  jz      short loc_180027BD5
0x180027bb4  mov     rdx, r15
0x180027bb7  lea     rcx, [rsp+98h+var_58]
0x180027bbc  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x180027bc1  lea     rcx, [rsp+98h+var_58]; this
0x180027bc6  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180027bcb  mov     rdx, rax; unsigned __int16 *
0x180027bce  call    ?IntroduceReaderGroup@@YAXKPEBG@Z; IntroduceReaderGroup(ulong,ushort const *)
0x180027bd3  jmp     short loc_180027C14
0x180027bd5  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180027bda  test    al, al
0x180027bdc  jz      short loc_180027BF7
0x180027bde  mov     [rsp+98h+var_6C], 8010001Dh
0x180027be6  lea     rdx, _TI1K; pThrowInfo
0x180027bed  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x180027bf2  call    _CxxThrowException_0
0x180027bf7  mov     r9d, 90054h; unsigned int
0x180027bfd  mov     r8d, 1; int
0x180027c03  mov     rdx, r15; unsigned __int8 *
0x180027c06  mov     rcx, rbx; unsigned __int64
0x180027c09  call    ?I_ContextAndStringCallWithLongReturn@@YAJ_KPEBEHK@Z; I_ContextAndStringCallWithLongReturn(unsigned __int64,uchar const *,int,ulong)
0x180027c0e  mov     edi, eax
0x180027c10  mov     [rsp+98h+var_78], eax
0x180027c14  lea     rcx, [rsp+98h+var_58]; this
0x180027c19  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180027c1e  nop
0x180027c1f  jmp     short loc_180027C27
0x180027c21  jmp     short $+2
0x180027c23  mov     edi, [rsp+98h+var_78]
0x180027c27  mov     eax, edi
0x180027c29  lea     r11, [rsp+98h+var_18]
0x180027c31  mov     rbx, [r11+20h]
0x180027c35  mov     rsi, [r11+28h]
0x180027c39  mov     rsp, r11
0x180027c3c  pop     r15
0x180027c3e  pop     r14
0x180027c40  pop     rdi
0x180027c41  retn
```
