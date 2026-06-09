# SCardRemoveReaderFromGroupA

- ea: `0x180026d80`
- end: `0x180026f71`
- name: `SCardRemoveReaderFromGroupA`
- size: `497`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR szReaderName, LPCSTR szGroupName)`
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
- `0x180026d80`
- `0x18002b2d8`
- `0x18002b734`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e5e`

## pseudocode

```c
LONG __stdcall SCardRemoveReaderFromGroupA(SCARDCONTEXT hContext, LPCSTR szReaderName, LPCSTR szGroupName)
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
    CTextString::operator=(&v19, szGroupName);
    v13 = CTextString::Unicode((CTextString *)&v19);
    v14 = CTextString::Unicode((CTextString *)&v29);
    RemoveReaderFromGroup(v12, v14, v13);
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
         (const unsigned __int8 *)szGroupName,
         0,
         0x90078u);
LABEL_14:
  CTextString::~CTextString((CTextString *)&v19);
  CTextString::~CTextString((CTextString *)&v29);
  return v6;
}

```

## disassembly

```asm
0x180026d80  mov     r11, rsp
0x180026d83  mov     [r11+8], rbx
0x180026d87  mov     [r11+10h], rsi
0x180026d8b  push    rdi
0x180026d8c  push    r12
0x180026d8e  push    r13
0x180026d90  push    r14
0x180026d92  push    r15
0x180026d94  sub     rsp, 0D0h
0x180026d9b  mov     r15, r8
0x180026d9e  mov     r12, rdx
0x180026da1  mov     r14, rcx
0x180026da4  xor     r13d, r13d
0x180026da7  mov     edi, r13d
0x180026daa  lea     rcx, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180026db1  mov     [r11-68h], rcx
0x180026db5  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180026dbc  mov     [r11-58h], rax
0x180026dc0  mov     [r11-50h], r13
0x180026dc4  mov     [r11-48h], r13d
0x180026dc8  mov     [r11-44h], r13d
0x180026dcc  mov     [r11-40h], rax
0x180026dd0  mov     [r11-38h], r13
0x180026dd4  mov     [r11-30h], r13d
0x180026dd8  mov     [r11-2Ch], r13d
0x180026ddc  lea     edx, [r13+3]
0x180026de0  mov     [r11-60h], edx
0x180026de4  mov     [rsp+0F8h+var_A8], rcx
0x180026de9  mov     [rsp+0F8h+var_98], rax
0x180026dee  mov     [rsp+0F8h+var_90], r13
0x180026df3  mov     [rsp+0F8h+var_88], r13d
0x180026df8  mov     [rsp+0F8h+var_84], r13d
0x180026dfd  mov     [r11-80h], rax
0x180026e01  mov     [r11-78h], r13
0x180026e05  mov     [r11-70h], r13d
0x180026e09  mov     [r11-6Ch], r13d
0x180026e0d  mov     [rsp+0F8h+var_A0], edx
0x180026e11  test    r14, r14
0x180026e14  jz      short loc_180026E95
0x180026e16  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180026e1d  lea     rsi, [rbx+20h]
0x180026e21  mov     [r11+20h], rsi
0x180026e25  mov     rcx, rsi; lpCriticalSection
0x180026e28  call    cs:__imp_EnterCriticalSection
0x180026e2e  nop
0x180026e2f  mov     rdx, r14; unsigned __int64
0x180026e32  mov     rcx, rbx; this
0x180026e35  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180026e3a  test    rax, rax
0x180026e3d  jnz     short loc_180026E58
0x180026e3f  mov     [rsp+0F8h+pExceptionObject], 6
0x180026e47  lea     rdx, _TI1K; pThrowInfo
0x180026e4e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180026e53  call    _CxxThrowException_0
0x180026e58  mov     rbx, [rax]
0x180026e5b  mov     rcx, rsi; lpCriticalSection
0x180026e5e  call    cs:__imp_LeaveCriticalSection
0x180026e64  cmp     [rbx+10h], r13d
0x180026e68  jz      short loc_180026E83
0x180026e6a  mov     [rsp+0F8h+var_C0], 8010001Eh
0x180026e72  lea     rdx, _TI1K; pThrowInfo
0x180026e79  lea     rcx, [rsp+0F8h+var_C0]; pExceptionObject
0x180026e7e  call    _CxxThrowException_0
0x180026e83  mov     rsi, [rbx+80h]
0x180026e8a  test    rsi, rsi
0x180026e8d  jnz     short loc_180026EF0
0x180026e8f  mov     r14d, [rbx+1Ch]
0x180026e93  jmp     short loc_180026E9E
0x180026e95  mov     r14d, 2
0x180026e9b  mov     rsi, r13
0x180026e9e  xor     ecx, ecx; lpCriticalSection
0x180026ea0  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180026ea5  test    al, al
0x180026ea7  jz      short loc_180026EF0
0x180026ea9  mov     rdx, r12
0x180026eac  lea     rcx, [rsp+0F8h+var_68]
0x180026eb4  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x180026eb9  mov     rdx, r15
0x180026ebc  lea     rcx, [rsp+0F8h+var_A8]
0x180026ec1  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x180026ec6  lea     rcx, [rsp+0F8h+var_A8]; this
0x180026ecb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180026ed0  mov     rbx, rax
0x180026ed3  lea     rcx, [rsp+0F8h+var_68]; this
0x180026edb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180026ee0  mov     r8, rbx; unsigned __int16 *
0x180026ee3  mov     rdx, rax; unsigned __int16 *
0x180026ee6  mov     ecx, r14d; unsigned int
0x180026ee9  call    ?RemoveReaderFromGroup@@YAXKPEBG0@Z; RemoveReaderFromGroup(ulong,ushort const *,ushort const *)
0x180026eee  jmp     short loc_180026F31
0x180026ef0  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180026ef5  test    al, al
0x180026ef7  jz      short loc_180026F12
0x180026ef9  mov     [rsp+0F8h+var_BC], 8010001Dh
0x180026f01  lea     rdx, _TI1K; pThrowInfo
0x180026f08  lea     rcx, [rsp+0F8h+var_BC]; pExceptionObject
0x180026f0d  call    _CxxThrowException_0
0x180026f12  mov     [rsp+0F8h+IoControlCode], 90078h; IoControlCode
0x180026f1a  xor     r9d, r9d; int
0x180026f1d  mov     r8, r15; unsigned __int8 *
0x180026f20  mov     rdx, r12; unsigned __int8 *
0x180026f23  mov     rcx, rsi; unsigned __int64
0x180026f26  call    ?I_ContextAndTwoStringCallWithLongReturn@@YAJ_KPEBE1HK@Z; I_ContextAndTwoStringCallWithLongReturn(unsigned __int64,uchar const *,uchar const *,int,ulong)
0x180026f2b  mov     edi, eax
0x180026f2d  mov     [rsp+0F8h+var_C8], eax
0x180026f31  lea     rcx, [rsp+0F8h+var_A8]; this
0x180026f36  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180026f3b  nop
0x180026f3c  lea     rcx, [rsp+0F8h+var_68]; this
0x180026f44  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180026f49  nop
0x180026f4a  jmp     short loc_180026F52
0x180026f4c  jmp     short $+2
0x180026f4e  mov     edi, [rsp+0F8h+var_C8]
0x180026f52  mov     eax, edi
0x180026f54  lea     r11, [rsp+0F8h+var_28]
0x180026f5c  mov     rbx, [r11+30h]
0x180026f60  mov     rsi, [r11+38h]
0x180026f64  mov     rsp, r11
0x180026f67  pop     r15
0x180026f69  pop     r14
0x180026f6b  pop     r13
0x180026f6d  pop     r12
0x180026f6f  pop     rdi
0x180026f70  retn
```
