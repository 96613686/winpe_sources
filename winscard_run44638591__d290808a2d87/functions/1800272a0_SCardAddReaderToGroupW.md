# SCardAddReaderToGroupW

- ea: `0x1800272a0`
- end: `0x180027494`
- name: `SCardAddReaderToGroupW`
- size: `500`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR szReaderName, LPCWSTR szGroupName)`
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
- `0x1800272a0`
- `0x18002aaf8`
- `0x18002b734`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027348`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027348`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002737e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002737e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LONG __stdcall SCardAddReaderToGroupW(SCARDCONTEXT hContext, LPCWSTR szReaderName, LPCWSTR szGroupName)
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
  LONG v19; // [rsp+40h] [rbp-B8h] BYREF
  void **v20; // [rsp+50h] [rbp-A8h] BYREF
  int v21; // [rsp+58h] [rbp-A0h]
  const int *v22; // [rsp+60h] [rbp-98h]
  __int64 v23; // [rsp+68h] [rbp-90h]
  int v24; // [rsp+70h] [rbp-88h]
  int v25; // [rsp+74h] [rbp-84h]
  const int *v26; // [rsp+78h] [rbp-80h]
  __int64 v27; // [rsp+80h] [rbp-78h]
  int v28; // [rsp+88h] [rbp-70h]
  int v29; // [rsp+8Ch] [rbp-6Ch]
  void **v30; // [rsp+90h] [rbp-68h] BYREF
  int v31; // [rsp+98h] [rbp-60h]
  const int *v32; // [rsp+A0h] [rbp-58h]
  __int64 v33; // [rsp+A8h] [rbp-50h]
  int v34; // [rsp+B0h] [rbp-48h]
  int v35; // [rsp+B4h] [rbp-44h]
  const int *v36; // [rsp+B8h] [rbp-40h]
  __int64 v37; // [rsp+C0h] [rbp-38h]
  int v38; // [rsp+C8h] [rbp-30h]
  int v39; // [rsp+CCh] [rbp-2Ch]

  v6 = 0;
  try
  {
    v30 = &CTextString::`vftable';
    v32 = &CBuffer::`vftable';
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = &CBuffer::`vftable';
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v31 = 3;
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
        goto LABEL_12;
      v12 = *(_DWORD *)(v10 + 28);
    }
    else
    {
      v12 = 2;
      v11 = 0;
    }
    if ( RedirectionContextIsLocal(0) )
    {
      CTextString::operator=(&v30, szReaderName);
      CTextString::operator=(&v20, szGroupName);
      v13 = CTextString::Unicode((CTextString *)&v20);
      v14 = CTextString::Unicode((CTextString *)&v30);
      AddReaderToGroup(v12, v14, v13);
LABEL_15:
      CTextString::~CTextString((CTextString *)&v20);
      CTextString::~CTextString((CTextString *)&v30);
      return v6;
    }
LABEL_12:
    if ( RedirectDisabled() )
    {
      v18 = -2146435043;
      throw &v18;
    }
    v6 = I_ContextAndTwoStringCallWithLongReturn(
           v11,
           (const unsigned __int8 *)szReaderName,
           (const unsigned __int8 *)szGroupName,
           1,
           0x90074u);
    goto LABEL_15;
  }
  catch ( ulong v19 )
  {
    return v19;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v6;
}

```

## disassembly

```asm
0x1800272a0  mov     r11, rsp
0x1800272a3  mov     [r11+8], rbx
0x1800272a7  mov     [r11+10h], rsi
0x1800272ab  push    rdi
0x1800272ac  push    r12
0x1800272ae  push    r13
0x1800272b0  push    r14
0x1800272b2  push    r15
0x1800272b4  sub     rsp, 0D0h
0x1800272bb  mov     r15, r8
0x1800272be  mov     r12, rdx
0x1800272c1  mov     r14, rcx
0x1800272c4  xor     r13d, r13d
0x1800272c7  mov     edi, r13d
0x1800272ca  lea     rcx, ??_7CTextString@@6B@; const CTextString::`vftable'
0x1800272d1  mov     [r11-68h], rcx
0x1800272d5  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800272dc  mov     [r11-58h], rax
0x1800272e0  mov     [r11-50h], r13
0x1800272e4  mov     [r11-48h], r13d
0x1800272e8  mov     [r11-44h], r13d
0x1800272ec  mov     [r11-40h], rax
0x1800272f0  mov     [r11-38h], r13
0x1800272f4  mov     [r11-30h], r13d
0x1800272f8  mov     [r11-2Ch], r13d
0x1800272fc  lea     edx, [r13+3]
0x180027300  mov     [r11-60h], edx
0x180027304  mov     [rsp+0F8h+var_A8], rcx
0x180027309  mov     [rsp+0F8h+var_98], rax
0x18002730e  mov     [rsp+0F8h+var_90], r13
0x180027313  mov     [rsp+0F8h+var_88], r13d
0x180027318  mov     [rsp+0F8h+var_84], r13d
0x18002731d  mov     [r11-80h], rax
0x180027321  mov     [r11-78h], r13
0x180027325  mov     [r11-70h], r13d
0x180027329  mov     [r11-6Ch], r13d
0x18002732d  mov     [rsp+0F8h+var_A0], edx
0x180027331  test    r14, r14
0x180027334  jz      short loc_1800273B5
0x180027336  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18002733d  lea     rsi, [rbx+20h]
0x180027341  mov     [r11+20h], rsi
0x180027345  mov     rcx, rsi; lpCriticalSection
0x180027348  call    cs:__imp_EnterCriticalSection
0x18002734e  nop
0x18002734f  mov     rdx, r14; unsigned __int64
0x180027352  mov     rcx, rbx; this
0x180027355  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x18002735a  test    rax, rax
0x18002735d  jnz     short loc_180027378
0x18002735f  mov     [rsp+0F8h+pExceptionObject], 6
0x180027367  lea     rdx, _TI1K; pThrowInfo
0x18002736e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180027373  call    _CxxThrowException_0
0x180027378  mov     rbx, [rax]
0x18002737b  mov     rcx, rsi; lpCriticalSection
0x18002737e  call    cs:__imp_LeaveCriticalSection
0x180027384  cmp     [rbx+10h], r13d
0x180027388  jz      short loc_1800273A3
0x18002738a  mov     [rsp+0F8h+var_C0], 8010001Eh
0x180027392  lea     rdx, _TI1K; pThrowInfo
0x180027399  lea     rcx, [rsp+0F8h+var_C0]; pExceptionObject
0x18002739e  call    _CxxThrowException_0
0x1800273a3  mov     rsi, [rbx+80h]
0x1800273aa  test    rsi, rsi
0x1800273ad  jnz     short loc_180027410
0x1800273af  mov     r14d, [rbx+1Ch]
0x1800273b3  jmp     short loc_1800273BE
0x1800273b5  mov     r14d, 2
0x1800273bb  mov     rsi, r13
0x1800273be  xor     ecx, ecx; lpCriticalSection
0x1800273c0  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x1800273c5  test    al, al
0x1800273c7  jz      short loc_180027410
0x1800273c9  mov     rdx, r12
0x1800273cc  lea     rcx, [rsp+0F8h+var_68]
0x1800273d4  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x1800273d9  mov     rdx, r15
0x1800273dc  lea     rcx, [rsp+0F8h+var_A8]
0x1800273e1  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x1800273e6  lea     rcx, [rsp+0F8h+var_A8]; this
0x1800273eb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800273f0  mov     rbx, rax
0x1800273f3  lea     rcx, [rsp+0F8h+var_68]; this
0x1800273fb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180027400  mov     r8, rbx; unsigned __int16 *
0x180027403  mov     rdx, rax; unsigned __int16 *
0x180027406  mov     ecx, r14d; unsigned int
0x180027409  call    ?AddReaderToGroup@@YAXKPEBG0@Z; AddReaderToGroup(ulong,ushort const *,ushort const *)
0x18002740e  jmp     short loc_180027454
0x180027410  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180027415  test    al, al
0x180027417  jz      short loc_180027432
0x180027419  mov     [rsp+0F8h+var_BC], 8010001Dh
0x180027421  lea     rdx, _TI1K; pThrowInfo
0x180027428  lea     rcx, [rsp+0F8h+var_BC]; pExceptionObject
0x18002742d  call    _CxxThrowException_0
0x180027432  mov     [rsp+0F8h+IoControlCode], 90074h; IoControlCode
0x18002743a  mov     r9d, 1; int
0x180027440  mov     r8, r15; unsigned __int8 *
0x180027443  mov     rdx, r12; unsigned __int8 *
0x180027446  mov     rcx, rsi; unsigned __int64
0x180027449  call    ?I_ContextAndTwoStringCallWithLongReturn@@YAJ_KPEBE1HK@Z; I_ContextAndTwoStringCallWithLongReturn(unsigned __int64,uchar const *,uchar const *,int,ulong)
0x18002744e  mov     edi, eax
0x180027450  mov     [rsp+0F8h+var_C8], eax
0x180027454  lea     rcx, [rsp+0F8h+var_A8]; this
0x180027459  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18002745e  nop
0x18002745f  lea     rcx, [rsp+0F8h+var_68]; this
0x180027467  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18002746c  nop
0x18002746d  jmp     short loc_180027475
0x18002746f  jmp     short $+2
0x180027471  mov     edi, [rsp+0F8h+var_C8]
0x180027475  mov     eax, edi
0x180027477  lea     r11, [rsp+0F8h+var_28]
0x18002747f  mov     rbx, [r11+30h]
0x180027483  mov     rsi, [r11+38h]
0x180027487  mov     rsp, r11
0x18002748a  pop     r15
0x18002748c  pop     r14
0x18002748e  pop     r13
0x180027490  pop     r12
0x180027492  pop     rdi
0x180027493  retn
```
