# SCardForgetReaderA

- ea: `0x180025170`
- end: `0x1800252eb`
- name: `SCardForgetReaderA`
- size: `379`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR szReaderName)`
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
- `0x180025170`
- `0x18002acb0`
- `0x18002b490`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800251e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800251e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025216`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025216`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LONG __stdcall SCardForgetReaderA(SCARDCONTEXT hContext, LPCSTR szReaderName)
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
  LONG v16; // [rsp+30h] [rbp-68h] BYREF
  void **v17; // [rsp+40h] [rbp-58h] BYREF
  int v18; // [rsp+48h] [rbp-50h]
  const int *v19; // [rsp+50h] [rbp-48h]
  __int64 v20; // [rsp+58h] [rbp-40h]
  int v21; // [rsp+60h] [rbp-38h]
  int v22; // [rsp+64h] [rbp-34h]
  const int *v23; // [rsp+68h] [rbp-30h]
  __int64 v24; // [rsp+70h] [rbp-28h]
  int v25; // [rsp+78h] [rbp-20h]
  int v26; // [rsp+7Ch] [rbp-1Ch]

  v4 = 0;
  try
  {
    v17 = &CTextString::`vftable';
    v19 = &CBuffer::`vftable';
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = &CBuffer::`vftable';
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v18 = 3;
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
        goto LABEL_12;
      v10 = *(_DWORD *)(v8 + 28);
    }
    else
    {
      v10 = 2;
      v9 = 0;
    }
    if ( RedirectionContextIsLocal(0) )
    {
      CTextString::operator=(&v17, szReaderName);
      v11 = CTextString::Unicode((CTextString *)&v17);
      ForgetReader(v10, v11);
LABEL_15:
      CTextString::~CTextString((CTextString *)&v17);
      return v4;
    }
LABEL_12:
    if ( RedirectDisabled() )
    {
      v15 = -2146435043;
      throw &v15;
    }
    v4 = I_ContextAndStringCallWithLongReturn(v9, (const unsigned __int8 *)szReaderName, 0, 0x90068u);
    goto LABEL_15;
  }
  catch ( ulong v16 )
  {
    return v16;
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
0x180025170  mov     r11, rsp
0x180025173  mov     [r11+8], rbx
0x180025177  mov     [r11+10h], rsi
0x18002517b  push    rdi
0x18002517c  push    r14
0x18002517e  push    r15
0x180025180  sub     rsp, 80h
0x180025187  mov     r15, rdx
0x18002518a  mov     rsi, rcx
0x18002518d  xor     edi, edi
0x18002518f  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180025196  mov     [r11-58h], rax
0x18002519a  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800251a1  mov     [r11-48h], rax
0x1800251a5  mov     [r11-40h], rdi
0x1800251a9  mov     [rsp+98h+var_38], edi
0x1800251ad  mov     [rsp+98h+var_34], edi
0x1800251b1  mov     [r11-30h], rax
0x1800251b5  mov     [r11-28h], rdi
0x1800251b9  mov     [rsp+98h+var_20], edi
0x1800251bd  mov     [rsp+98h+var_1C], edi
0x1800251c1  mov     [rsp+98h+var_50], 3
0x1800251c9  test    rcx, rcx
0x1800251cc  jz      short loc_18002524C
0x1800251ce  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x1800251d5  lea     r14, [rbx+20h]
0x1800251d9  mov     [r11+18h], r14
0x1800251dd  mov     rcx, r14; lpCriticalSection
0x1800251e0  call    cs:__imp_EnterCriticalSection
0x1800251e6  nop
0x1800251e7  mov     rdx, rsi; unsigned __int64
0x1800251ea  mov     rcx, rbx; this
0x1800251ed  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800251f2  test    rax, rax
0x1800251f5  jnz     short loc_180025210
0x1800251f7  mov     [rsp+98h+pExceptionObject], 6
0x1800251ff  lea     rdx, _TI1K; pThrowInfo
0x180025206  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002520b  call    _CxxThrowException_0
0x180025210  mov     rbx, [rax]
0x180025213  mov     rcx, r14; lpCriticalSection
0x180025216  call    cs:__imp_LeaveCriticalSection
0x18002521c  cmp     dword ptr [rbx+10h], 0
0x180025220  jz      short loc_18002523B
0x180025222  mov     [rsp+98h+var_70], 8010001Eh
0x18002522a  lea     rdx, _TI1K; pThrowInfo
0x180025231  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180025236  call    _CxxThrowException_0
0x18002523b  mov     rsi, [rbx+80h]
0x180025242  test    rsi, rsi
0x180025245  jnz     short loc_180025281
0x180025247  mov     ebx, [rbx+1Ch]
0x18002524a  jmp     short loc_180025253
0x18002524c  mov     ebx, 2
0x180025251  xor     esi, esi
0x180025253  xor     ecx, ecx; lpCriticalSection
0x180025255  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x18002525a  test    al, al
0x18002525c  jz      short loc_180025281
0x18002525e  mov     rdx, r15
0x180025261  lea     rcx, [rsp+98h+var_58]
0x180025266  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x18002526b  lea     rcx, [rsp+98h+var_58]; this
0x180025270  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180025275  mov     rdx, rax; unsigned __int16 *
0x180025278  mov     ecx, ebx; unsigned int
0x18002527a  call    ?ForgetReader@@YAXKPEBG@Z; ForgetReader(ulong,ushort const *)
0x18002527f  jmp     short loc_1800252BD
0x180025281  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180025286  test    al, al
0x180025288  jz      short loc_1800252A3
0x18002528a  mov     [rsp+98h+var_6C], 8010001Dh
0x180025292  lea     rdx, _TI1K; pThrowInfo
0x180025299  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x18002529e  call    _CxxThrowException_0
0x1800252a3  mov     r9d, 90068h; unsigned int
0x1800252a9  xor     r8d, r8d; int
0x1800252ac  mov     rdx, r15; unsigned __int8 *
0x1800252af  mov     rcx, rsi; unsigned __int64
0x1800252b2  call    ?I_ContextAndStringCallWithLongReturn@@YAJ_KPEBEHK@Z; I_ContextAndStringCallWithLongReturn(unsigned __int64,uchar const *,int,ulong)
0x1800252b7  mov     edi, eax
0x1800252b9  mov     [rsp+98h+var_78], eax
0x1800252bd  lea     rcx, [rsp+98h+var_58]; this
0x1800252c2  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x1800252c7  nop
0x1800252c8  jmp     short loc_1800252D0
0x1800252ca  jmp     short $+2
0x1800252cc  mov     edi, [rsp+98h+var_78]
0x1800252d0  mov     eax, edi
0x1800252d2  lea     r11, [rsp+98h+var_18]
0x1800252da  mov     rbx, [r11+20h]
0x1800252de  mov     rsi, [r11+28h]
0x1800252e2  mov     rsp, r11
0x1800252e5  pop     r15
0x1800252e7  pop     r14
0x1800252e9  pop     rdi
0x1800252ea  retn
```
