# SCardForgetReaderW

- ea: `0x180027630`
- end: `0x1800277ae`
- name: `SCardForgetReaderW`
- size: `382`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR szReaderName)`
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
- `0x180027630`
- `0x18002acb0`
- `0x18002b490`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800276a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800276a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276d6`

## pseudocode

```c
LONG __stdcall SCardForgetReaderW(SCARDCONTEXT hContext, LPCWSTR szReaderName)
{
  LONG v4; // edi
  CHandleList *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v8; // rbx
  __int64 v9; // rsi
  int v10; // ebx
  const unsigned __int16 *v11; // rax
  ulong pExceptionObject; // [rsp+24h] [rbp-74h] BYREF
  ulong v14; // [rsp+28h] [rbp-70h] BYREF
  ulong v15; // [rsp+2Ch] [rbp-6Ch] BYREF
  void **v16; // [rsp+40h] [rbp-58h] BYREF
  int v17; // [rsp+48h] [rbp-50h]
  const int *v18; // [rsp+50h] [rbp-48h]
  __int64 v19; // [rsp+58h] [rbp-40h]
  int v20; // [rsp+60h] [rbp-38h]
  int v21; // [rsp+64h] [rbp-34h]
  const int *v22; // [rsp+68h] [rbp-30h]
  __int64 v23; // [rsp+70h] [rbp-28h]
  int v24; // [rsp+78h] [rbp-20h]
  int v25; // [rsp+7Ch] [rbp-1Ch]

  v4 = 0;
  v16 = &CTextString::`vftable';
  v18 = &CBuffer::`vftable';
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = &CBuffer::`vftable';
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v17 = 3;
  if ( hContext )
  {
    v5 = g_phlContexts;
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v5, hContext);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v8 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v6);
    if ( *(_DWORD *)(v8 + 16) )
    {
      v14 = -2146435042;
      throw &v14;
    }
    v9 = *(_QWORD *)(v8 + 128);
    if ( v9 )
      goto LABEL_11;
    v10 = *(_DWORD *)(v8 + 28);
  }
  else
  {
    v10 = 2;
    v9 = 0;
  }
  if ( RedirectionContextIsLocal(0) )
  {
    CTextString::operator=(&v16, szReaderName);
    v11 = CTextString::Unicode((CTextString *)&v16);
    ForgetReader(v10, v11);
    goto LABEL_14;
  }
LABEL_11:
  if ( RedirectDisabled() )
  {
    v15 = -2146435043;
    throw &v15;
  }
  v4 = I_ContextAndStringCallWithLongReturn(v9, (const unsigned __int8 *)szReaderName, 1, 0x9006Cu);
LABEL_14:
  CTextString::~CTextString((CTextString *)&v16);
  return v4;
}

```

## disassembly

```asm
0x180027630  mov     r11, rsp
0x180027633  mov     [r11+8], rbx
0x180027637  mov     [r11+10h], rsi
0x18002763b  push    rdi
0x18002763c  push    r14
0x18002763e  push    r15
0x180027640  sub     rsp, 80h
0x180027647  mov     r15, rdx
0x18002764a  mov     rsi, rcx
0x18002764d  xor     edi, edi
0x18002764f  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180027656  mov     [r11-58h], rax
0x18002765a  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180027661  mov     [r11-48h], rax
0x180027665  mov     [r11-40h], rdi
0x180027669  mov     [rsp+98h+var_38], edi
0x18002766d  mov     [rsp+98h+var_34], edi
0x180027671  mov     [r11-30h], rax
0x180027675  mov     [r11-28h], rdi
0x180027679  mov     [rsp+98h+var_20], edi
0x18002767d  mov     [rsp+98h+var_1C], edi
0x180027681  mov     [rsp+98h+var_50], 3
0x180027689  test    rcx, rcx
0x18002768c  jz      short loc_18002770C
0x18002768e  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180027695  lea     r14, [rbx+20h]
0x180027699  mov     [r11+18h], r14
0x18002769d  mov     rcx, r14; lpCriticalSection
0x1800276a0  call    cs:__imp_EnterCriticalSection
0x1800276a6  nop
0x1800276a7  mov     rdx, rsi; unsigned __int64
0x1800276aa  mov     rcx, rbx; this
0x1800276ad  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800276b2  test    rax, rax
0x1800276b5  jnz     short loc_1800276D0
0x1800276b7  mov     [rsp+98h+pExceptionObject], 6
0x1800276bf  lea     rdx, _TI1K; pThrowInfo
0x1800276c6  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800276cb  call    _CxxThrowException_0
0x1800276d0  mov     rbx, [rax]
0x1800276d3  mov     rcx, r14; lpCriticalSection
0x1800276d6  call    cs:__imp_LeaveCriticalSection
0x1800276dc  cmp     dword ptr [rbx+10h], 0
0x1800276e0  jz      short loc_1800276FB
0x1800276e2  mov     [rsp+98h+var_70], 8010001Eh
0x1800276ea  lea     rdx, _TI1K; pThrowInfo
0x1800276f1  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x1800276f6  call    _CxxThrowException_0
0x1800276fb  mov     rsi, [rbx+80h]
0x180027702  test    rsi, rsi
0x180027705  jnz     short loc_180027741
0x180027707  mov     ebx, [rbx+1Ch]
0x18002770a  jmp     short loc_180027713
0x18002770c  mov     ebx, 2
0x180027711  xor     esi, esi
0x180027713  xor     ecx, ecx; lpCriticalSection
0x180027715  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x18002771a  test    al, al
0x18002771c  jz      short loc_180027741
0x18002771e  mov     rdx, r15
0x180027721  lea     rcx, [rsp+98h+var_58]
0x180027726  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18002772b  lea     rcx, [rsp+98h+var_58]; this
0x180027730  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180027735  mov     rdx, rax; unsigned __int16 *
0x180027738  mov     ecx, ebx; unsigned int
0x18002773a  call    ?ForgetReader@@YAXKPEBG@Z; ForgetReader(ulong,ushort const *)
0x18002773f  jmp     short loc_180027780
0x180027741  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180027746  test    al, al
0x180027748  jz      short loc_180027763
0x18002774a  mov     [rsp+98h+var_6C], 8010001Dh
0x180027752  lea     rdx, _TI1K; pThrowInfo
0x180027759  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x18002775e  call    _CxxThrowException_0
0x180027763  mov     r9d, 9006Ch; unsigned int
0x180027769  mov     r8d, 1; int
0x18002776f  mov     rdx, r15; unsigned __int8 *
0x180027772  mov     rcx, rsi; unsigned __int64
0x180027775  call    ?I_ContextAndStringCallWithLongReturn@@YAJ_KPEBEHK@Z; I_ContextAndStringCallWithLongReturn(unsigned __int64,uchar const *,int,ulong)
0x18002777a  mov     edi, eax
0x18002777c  mov     [rsp+98h+var_78], eax
0x180027780  lea     rcx, [rsp+98h+var_58]; this
0x180027785  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18002778a  nop
0x18002778b  jmp     short loc_180027793
0x18002778d  jmp     short $+2
0x18002778f  mov     edi, [rsp+98h+var_78]
0x180027793  mov     eax, edi
0x180027795  lea     r11, [rsp+98h+var_18]
0x18002779d  mov     rbx, [r11+20h]
0x1800277a1  mov     rsi, [r11+28h]
0x1800277a5  mov     rsp, r11
0x1800277a8  pop     r15
0x1800277aa  pop     r14
0x1800277ac  pop     rdi
0x1800277ad  retn
```
