# SCardIntroduceReaderGroupA

- ea: `0x180025d30`
- end: `0x180025e9f`
- name: `SCardIntroduceReaderGroupA`
- size: `367`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR szGroupName)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800093e4`
- `0x18000e090`
- `0x18000e680`
- `0x180010898`
- `0x180011b0c`
- `0x1800126f0`
- `0x180025d30`
- `0x18002b270`
- `0x18002b490`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025da2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025da2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025dd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025dd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LONG __stdcall SCardIntroduceReaderGroupA(SCARDCONTEXT hContext, LPCSTR szGroupName)
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
      v4 = I_ContextAndStringCallWithLongReturn(v5, (const unsigned __int8 *)szGroupName, 0, 0x90050u);
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
0x180025d30  mov     r11, rsp
0x180025d33  mov     [r11+8], rbx
0x180025d37  mov     [r11+10h], rsi
0x180025d3b  push    rdi
0x180025d3c  push    r14
0x180025d3e  push    r15
0x180025d40  sub     rsp, 80h
0x180025d47  mov     r15, rdx
0x180025d4a  mov     rsi, rcx
0x180025d4d  xor     edi, edi
0x180025d4f  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180025d56  mov     [r11-58h], rax
0x180025d5a  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180025d61  mov     [r11-48h], rax
0x180025d65  mov     [r11-40h], rdi
0x180025d69  mov     [rsp+98h+var_38], edi
0x180025d6d  mov     [rsp+98h+var_34], edi
0x180025d71  mov     [r11-30h], rax
0x180025d75  mov     [r11-28h], rdi
0x180025d79  mov     [rsp+98h+var_20], edi
0x180025d7d  mov     [rsp+98h+var_1C], edi
0x180025d81  mov     [rsp+98h+var_50], 3
0x180025d89  xor     ebx, ebx
0x180025d8b  test    rcx, rcx
0x180025d8e  jz      short loc_180025E09
0x180025d90  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180025d97  lea     r14, [rbx+20h]
0x180025d9b  mov     [r11+18h], r14
0x180025d9f  mov     rcx, r14; lpCriticalSection
0x180025da2  call    cs:__imp_EnterCriticalSection
0x180025da8  nop
0x180025da9  mov     rdx, rsi; unsigned __int64
0x180025dac  mov     rcx, rbx; this
0x180025daf  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180025db4  test    rax, rax
0x180025db7  jnz     short loc_180025DD2
0x180025db9  mov     [rsp+98h+pExceptionObject], 6
0x180025dc1  lea     rdx, _TI1K; pThrowInfo
0x180025dc8  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180025dcd  call    _CxxThrowException_0
0x180025dd2  mov     rbx, [rax]
0x180025dd5  mov     rcx, r14; lpCriticalSection
0x180025dd8  call    cs:__imp_LeaveCriticalSection
0x180025dde  cmp     dword ptr [rbx+10h], 0
0x180025de2  jz      short loc_180025DFD
0x180025de4  mov     [rsp+98h+var_70], 8010001Eh
0x180025dec  lea     rdx, _TI1K; pThrowInfo
0x180025df3  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180025df8  call    _CxxThrowException_0
0x180025dfd  mov     rbx, [rbx+80h]
0x180025e04  test    rbx, rbx
0x180025e07  jnz     short loc_180025E35
0x180025e09  xor     ecx, ecx; lpCriticalSection
0x180025e0b  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180025e10  test    al, al
0x180025e12  jz      short loc_180025E35
0x180025e14  mov     rdx, r15
0x180025e17  lea     rcx, [rsp+98h+var_58]
0x180025e1c  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x180025e21  lea     rcx, [rsp+98h+var_58]; this
0x180025e26  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180025e2b  mov     rdx, rax; unsigned __int16 *
0x180025e2e  call    ?IntroduceReaderGroup@@YAXKPEBG@Z; IntroduceReaderGroup(ulong,ushort const *)
0x180025e33  jmp     short loc_180025E71
0x180025e35  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180025e3a  test    al, al
0x180025e3c  jz      short loc_180025E57
0x180025e3e  mov     [rsp+98h+var_6C], 8010001Dh
0x180025e46  lea     rdx, _TI1K; pThrowInfo
0x180025e4d  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x180025e52  call    _CxxThrowException_0
0x180025e57  mov     r9d, 90050h; unsigned int
0x180025e5d  xor     r8d, r8d; int
0x180025e60  mov     rdx, r15; unsigned __int8 *
0x180025e63  mov     rcx, rbx; unsigned __int64
0x180025e66  call    ?I_ContextAndStringCallWithLongReturn@@YAJ_KPEBEHK@Z; I_ContextAndStringCallWithLongReturn(unsigned __int64,uchar const *,int,ulong)
0x180025e6b  mov     edi, eax
0x180025e6d  mov     [rsp+98h+var_78], eax
0x180025e71  lea     rcx, [rsp+98h+var_58]; this
0x180025e76  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180025e7b  nop
0x180025e7c  jmp     short loc_180025E84
0x180025e7e  jmp     short $+2
0x180025e80  mov     edi, [rsp+98h+var_78]
0x180025e84  mov     eax, edi
0x180025e86  lea     r11, [rsp+98h+var_18]
0x180025e8e  mov     rbx, [r11+20h]
0x180025e92  mov     rsi, [r11+28h]
0x180025e96  mov     rsp, r11
0x180025e99  pop     r15
0x180025e9b  pop     r14
0x180025e9d  pop     rdi
0x180025e9e  retn
```
