# SCardAddReaderToGroupA

- ea: `0x180024f70`
- end: `0x180025161`
- name: `SCardAddReaderToGroupA`
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
- `0x180024f70`
- `0x18002aaf8`
- `0x18002b734`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025018`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025018`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002504e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002504e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LONG __stdcall SCardAddReaderToGroupA(SCARDCONTEXT hContext, LPCSTR szReaderName, LPCSTR szGroupName)
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
           0,
           0x90070u);
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
0x180024f70  mov     r11, rsp
0x180024f73  mov     [r11+8], rbx
0x180024f77  mov     [r11+10h], rsi
0x180024f7b  push    rdi
0x180024f7c  push    r12
0x180024f7e  push    r13
0x180024f80  push    r14
0x180024f82  push    r15
0x180024f84  sub     rsp, 0D0h
0x180024f8b  mov     r15, r8
0x180024f8e  mov     r12, rdx
0x180024f91  mov     r14, rcx
0x180024f94  xor     r13d, r13d
0x180024f97  mov     edi, r13d
0x180024f9a  lea     rcx, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180024fa1  mov     [r11-68h], rcx
0x180024fa5  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180024fac  mov     [r11-58h], rax
0x180024fb0  mov     [r11-50h], r13
0x180024fb4  mov     [r11-48h], r13d
0x180024fb8  mov     [r11-44h], r13d
0x180024fbc  mov     [r11-40h], rax
0x180024fc0  mov     [r11-38h], r13
0x180024fc4  mov     [r11-30h], r13d
0x180024fc8  mov     [r11-2Ch], r13d
0x180024fcc  lea     edx, [r13+3]
0x180024fd0  mov     [r11-60h], edx
0x180024fd4  mov     [rsp+0F8h+var_A8], rcx
0x180024fd9  mov     [rsp+0F8h+var_98], rax
0x180024fde  mov     [rsp+0F8h+var_90], r13
0x180024fe3  mov     [rsp+0F8h+var_88], r13d
0x180024fe8  mov     [rsp+0F8h+var_84], r13d
0x180024fed  mov     [r11-80h], rax
0x180024ff1  mov     [r11-78h], r13
0x180024ff5  mov     [r11-70h], r13d
0x180024ff9  mov     [r11-6Ch], r13d
0x180024ffd  mov     [rsp+0F8h+var_A0], edx
0x180025001  test    r14, r14
0x180025004  jz      short loc_180025085
0x180025006  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18002500d  lea     rsi, [rbx+20h]
0x180025011  mov     [r11+20h], rsi
0x180025015  mov     rcx, rsi; lpCriticalSection
0x180025018  call    cs:__imp_EnterCriticalSection
0x18002501e  nop
0x18002501f  mov     rdx, r14; unsigned __int64
0x180025022  mov     rcx, rbx; this
0x180025025  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x18002502a  test    rax, rax
0x18002502d  jnz     short loc_180025048
0x18002502f  mov     [rsp+0F8h+pExceptionObject], 6
0x180025037  lea     rdx, _TI1K; pThrowInfo
0x18002503e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180025043  call    _CxxThrowException_0
0x180025048  mov     rbx, [rax]
0x18002504b  mov     rcx, rsi; lpCriticalSection
0x18002504e  call    cs:__imp_LeaveCriticalSection
0x180025054  cmp     [rbx+10h], r13d
0x180025058  jz      short loc_180025073
0x18002505a  mov     [rsp+0F8h+var_C0], 8010001Eh
0x180025062  lea     rdx, _TI1K; pThrowInfo
0x180025069  lea     rcx, [rsp+0F8h+var_C0]; pExceptionObject
0x18002506e  call    _CxxThrowException_0
0x180025073  mov     rsi, [rbx+80h]
0x18002507a  test    rsi, rsi
0x18002507d  jnz     short loc_1800250E0
0x18002507f  mov     r14d, [rbx+1Ch]
0x180025083  jmp     short loc_18002508E
0x180025085  mov     r14d, 2
0x18002508b  mov     rsi, r13
0x18002508e  xor     ecx, ecx; lpCriticalSection
0x180025090  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180025095  test    al, al
0x180025097  jz      short loc_1800250E0
0x180025099  mov     rdx, r12
0x18002509c  lea     rcx, [rsp+0F8h+var_68]
0x1800250a4  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x1800250a9  mov     rdx, r15
0x1800250ac  lea     rcx, [rsp+0F8h+var_A8]
0x1800250b1  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x1800250b6  lea     rcx, [rsp+0F8h+var_A8]; this
0x1800250bb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800250c0  mov     rbx, rax
0x1800250c3  lea     rcx, [rsp+0F8h+var_68]; this
0x1800250cb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800250d0  mov     r8, rbx; unsigned __int16 *
0x1800250d3  mov     rdx, rax; unsigned __int16 *
0x1800250d6  mov     ecx, r14d; unsigned int
0x1800250d9  call    ?AddReaderToGroup@@YAXKPEBG0@Z; AddReaderToGroup(ulong,ushort const *,ushort const *)
0x1800250de  jmp     short loc_180025121
0x1800250e0  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x1800250e5  test    al, al
0x1800250e7  jz      short loc_180025102
0x1800250e9  mov     [rsp+0F8h+var_BC], 8010001Dh
0x1800250f1  lea     rdx, _TI1K; pThrowInfo
0x1800250f8  lea     rcx, [rsp+0F8h+var_BC]; pExceptionObject
0x1800250fd  call    _CxxThrowException_0
0x180025102  mov     [rsp+0F8h+IoControlCode], 90070h; IoControlCode
0x18002510a  xor     r9d, r9d; int
0x18002510d  mov     r8, r15; unsigned __int8 *
0x180025110  mov     rdx, r12; unsigned __int8 *
0x180025113  mov     rcx, rsi; unsigned __int64
0x180025116  call    ?I_ContextAndTwoStringCallWithLongReturn@@YAJ_KPEBE1HK@Z; I_ContextAndTwoStringCallWithLongReturn(unsigned __int64,uchar const *,uchar const *,int,ulong)
0x18002511b  mov     edi, eax
0x18002511d  mov     [rsp+0F8h+var_C8], eax
0x180025121  lea     rcx, [rsp+0F8h+var_A8]; this
0x180025126  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18002512b  nop
0x18002512c  lea     rcx, [rsp+0F8h+var_68]; this
0x180025134  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180025139  nop
0x18002513a  jmp     short loc_180025142
0x18002513c  jmp     short $+2
0x18002513e  mov     edi, [rsp+0F8h+var_C8]
0x180025142  mov     eax, edi
0x180025144  lea     r11, [rsp+0F8h+var_28]
0x18002514c  mov     rbx, [r11+30h]
0x180025150  mov     rsi, [r11+38h]
0x180025154  mov     rsp, r11
0x180025157  pop     r15
0x180025159  pop     r14
0x18002515b  pop     r13
0x18002515d  pop     r12
0x18002515f  pop     rdi
0x180025160  retn
```
