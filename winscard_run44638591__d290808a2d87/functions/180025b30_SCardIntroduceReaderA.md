# SCardIntroduceReaderA

- ea: `0x180025b30`
- end: `0x180025d21`
- name: `SCardIntroduceReaderA`
- size: `497`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR szReaderName, LPCSTR szDeviceName)`
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
- `0x180025b30`
- `0x18002b0ec`
- `0x18002b734`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c0e`

## pseudocode

```c
LONG __stdcall SCardIntroduceReaderA(SCARDCONTEXT hContext, LPCSTR szReaderName, LPCSTR szDeviceName)
{
  LONG v6; // edi
  CHandleList *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v10; // rbx
  __int64 v11; // rsi
  int v12; // r14d
  const unsigned __int16 *v13; // rbx
  const unsigned __int16 *v14; // rax
  ulong pExceptionObject; // [rsp+34h] [rbp-C4h] BYREF
  ulong v17; // [rsp+38h] [rbp-C0h] BYREF
  ulong v18; // [rsp+3Ch] [rbp-BCh] BYREF
  void **v19; // [rsp+50h] [rbp-A8h] BYREF
  int v20; // [rsp+58h] [rbp-A0h]
  const int *v21; // [rsp+60h] [rbp-98h]
  __int64 v22; // [rsp+68h] [rbp-90h]
  int v23; // [rsp+70h] [rbp-88h]
  int v24; // [rsp+74h] [rbp-84h]
  const int *v25; // [rsp+78h] [rbp-80h]
  __int64 v26; // [rsp+80h] [rbp-78h]
  int v27; // [rsp+88h] [rbp-70h]
  int v28; // [rsp+8Ch] [rbp-6Ch]
  void **v29; // [rsp+90h] [rbp-68h] BYREF
  int v30; // [rsp+98h] [rbp-60h]
  const int *v31; // [rsp+A0h] [rbp-58h]
  __int64 v32; // [rsp+A8h] [rbp-50h]
  int v33; // [rsp+B0h] [rbp-48h]
  int v34; // [rsp+B4h] [rbp-44h]
  const int *v35; // [rsp+B8h] [rbp-40h]
  __int64 v36; // [rsp+C0h] [rbp-38h]
  int v37; // [rsp+C8h] [rbp-30h]
  int v38; // [rsp+CCh] [rbp-2Ch]

  v6 = 0;
  v29 = &CTextString::`vftable';
  v31 = &CBuffer::`vftable';
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = &CBuffer::`vftable';
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v30 = 3;
  v19 = &CTextString::`vftable';
  v21 = &CBuffer::`vftable';
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = &CBuffer::`vftable';
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v20 = 3;
  if ( hContext )
  {
    v7 = g_phlContexts;
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v7, hContext);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v10 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v8);
    if ( *(_DWORD *)(v10 + 16) )
    {
      v17 = -2146435042;
      throw &v17;
    }
    v11 = *(_QWORD *)(v10 + 128);
    if ( v11 )
      goto LABEL_11;
    v12 = *(_DWORD *)(v10 + 28);
  }
  else
  {
    v12 = 2;
    v11 = 0;
  }
  if ( RedirectionContextIsLocal(0) )
  {
    CTextString::operator=(&v29, szReaderName);
    CTextString::operator=(&v19, szDeviceName);
    v13 = CTextString::Unicode((CTextString *)&v19);
    v14 = CTextString::Unicode((CTextString *)&v29);
    IntroduceReader(v12, v14, v13);
    goto LABEL_14;
  }
LABEL_11:
  if ( RedirectDisabled() )
  {
    v18 = -2146435043;
    throw &v18;
  }
  v6 = I_ContextAndTwoStringCallWithLongReturn(
         v11,
         (const unsigned __int8 *)szReaderName,
         (const unsigned __int8 *)szDeviceName,
         0,
         0x90060u);
LABEL_14:
  CTextString::~CTextString((CTextString *)&v19);
  CTextString::~CTextString((CTextString *)&v29);
  return v6;
}

```

## disassembly

```asm
0x180025b30  mov     r11, rsp
0x180025b33  mov     [r11+8], rbx
0x180025b37  mov     [r11+10h], rsi
0x180025b3b  push    rdi
0x180025b3c  push    r12
0x180025b3e  push    r13
0x180025b40  push    r14
0x180025b42  push    r15
0x180025b44  sub     rsp, 0D0h
0x180025b4b  mov     r15, r8
0x180025b4e  mov     r12, rdx
0x180025b51  mov     r14, rcx
0x180025b54  xor     r13d, r13d
0x180025b57  mov     edi, r13d
0x180025b5a  lea     rcx, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180025b61  mov     [r11-68h], rcx
0x180025b65  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180025b6c  mov     [r11-58h], rax
0x180025b70  mov     [r11-50h], r13
0x180025b74  mov     [r11-48h], r13d
0x180025b78  mov     [r11-44h], r13d
0x180025b7c  mov     [r11-40h], rax
0x180025b80  mov     [r11-38h], r13
0x180025b84  mov     [r11-30h], r13d
0x180025b88  mov     [r11-2Ch], r13d
0x180025b8c  lea     edx, [r13+3]
0x180025b90  mov     [r11-60h], edx
0x180025b94  mov     [rsp+0F8h+var_A8], rcx
0x180025b99  mov     [rsp+0F8h+var_98], rax
0x180025b9e  mov     [rsp+0F8h+var_90], r13
0x180025ba3  mov     [rsp+0F8h+var_88], r13d
0x180025ba8  mov     [rsp+0F8h+var_84], r13d
0x180025bad  mov     [r11-80h], rax
0x180025bb1  mov     [r11-78h], r13
0x180025bb5  mov     [r11-70h], r13d
0x180025bb9  mov     [r11-6Ch], r13d
0x180025bbd  mov     [rsp+0F8h+var_A0], edx
0x180025bc1  test    r14, r14
0x180025bc4  jz      short loc_180025C45
0x180025bc6  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180025bcd  lea     rsi, [rbx+20h]
0x180025bd1  mov     [r11+20h], rsi
0x180025bd5  mov     rcx, rsi; lpCriticalSection
0x180025bd8  call    cs:__imp_EnterCriticalSection
0x180025bde  nop
0x180025bdf  mov     rdx, r14; unsigned __int64
0x180025be2  mov     rcx, rbx; this
0x180025be5  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180025bea  test    rax, rax
0x180025bed  jnz     short loc_180025C08
0x180025bef  mov     [rsp+0F8h+pExceptionObject], 6
0x180025bf7  lea     rdx, _TI1K; pThrowInfo
0x180025bfe  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180025c03  call    _CxxThrowException_0
0x180025c08  mov     rbx, [rax]
0x180025c0b  mov     rcx, rsi; lpCriticalSection
0x180025c0e  call    cs:__imp_LeaveCriticalSection
0x180025c14  cmp     [rbx+10h], r13d
0x180025c18  jz      short loc_180025C33
0x180025c1a  mov     [rsp+0F8h+var_C0], 8010001Eh
0x180025c22  lea     rdx, _TI1K; pThrowInfo
0x180025c29  lea     rcx, [rsp+0F8h+var_C0]; pExceptionObject
0x180025c2e  call    _CxxThrowException_0
0x180025c33  mov     rsi, [rbx+80h]
0x180025c3a  test    rsi, rsi
0x180025c3d  jnz     short loc_180025CA0
0x180025c3f  mov     r14d, [rbx+1Ch]
0x180025c43  jmp     short loc_180025C4E
0x180025c45  mov     r14d, 2
0x180025c4b  mov     rsi, r13
0x180025c4e  xor     ecx, ecx; lpCriticalSection
0x180025c50  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180025c55  test    al, al
0x180025c57  jz      short loc_180025CA0
0x180025c59  mov     rdx, r12
0x180025c5c  lea     rcx, [rsp+0F8h+var_68]
0x180025c64  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x180025c69  mov     rdx, r15
0x180025c6c  lea     rcx, [rsp+0F8h+var_A8]
0x180025c71  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x180025c76  lea     rcx, [rsp+0F8h+var_A8]; this
0x180025c7b  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180025c80  mov     rbx, rax
0x180025c83  lea     rcx, [rsp+0F8h+var_68]; this
0x180025c8b  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180025c90  mov     r8, rbx; unsigned __int16 *
0x180025c93  mov     rdx, rax; unsigned __int16 *
0x180025c96  mov     ecx, r14d; unsigned int
0x180025c99  call    ?IntroduceReader@@YAXKPEBG0@Z; IntroduceReader(ulong,ushort const *,ushort const *)
0x180025c9e  jmp     short loc_180025CE1
0x180025ca0  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180025ca5  test    al, al
0x180025ca7  jz      short loc_180025CC2
0x180025ca9  mov     [rsp+0F8h+var_BC], 8010001Dh
0x180025cb1  lea     rdx, _TI1K; pThrowInfo
0x180025cb8  lea     rcx, [rsp+0F8h+var_BC]; pExceptionObject
0x180025cbd  call    _CxxThrowException_0
0x180025cc2  mov     [rsp+0F8h+IoControlCode], 90060h; IoControlCode
0x180025cca  xor     r9d, r9d; int
0x180025ccd  mov     r8, r15; unsigned __int8 *
0x180025cd0  mov     rdx, r12; unsigned __int8 *
0x180025cd3  mov     rcx, rsi; unsigned __int64
0x180025cd6  call    ?I_ContextAndTwoStringCallWithLongReturn@@YAJ_KPEBE1HK@Z; I_ContextAndTwoStringCallWithLongReturn(unsigned __int64,uchar const *,uchar const *,int,ulong)
0x180025cdb  mov     edi, eax
0x180025cdd  mov     [rsp+0F8h+var_C8], eax
0x180025ce1  lea     rcx, [rsp+0F8h+var_A8]; this
0x180025ce6  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180025ceb  nop
0x180025cec  lea     rcx, [rsp+0F8h+var_68]; this
0x180025cf4  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180025cf9  nop
0x180025cfa  jmp     short loc_180025D02
0x180025cfc  jmp     short $+2
0x180025cfe  mov     edi, [rsp+0F8h+var_C8]
0x180025d02  mov     eax, edi
0x180025d04  lea     r11, [rsp+0F8h+var_28]
0x180025d0c  mov     rbx, [r11+30h]
0x180025d10  mov     rsi, [r11+38h]
0x180025d14  mov     rsp, r11
0x180025d17  pop     r15
0x180025d19  pop     r14
0x180025d1b  pop     r13
0x180025d1d  pop     r12
0x180025d1f  pop     rdi
0x180025d20  retn
```
