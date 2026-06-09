# SCardListReaderGroupsA

- ea: `0x180026190`
- end: `0x1800262e3`
- name: `SCardListReaderGroupsA`
- size: `339`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPSTR mszGroups, LPDWORD pcchGroups)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800093e4`
- `0x18000e3d0`
- `0x18000e470`
- `0x180010898`
- `0x1800126f0`
- `0x180026190`
- `0x18002a8ec`
- `0x18002ba08`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800261d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800261d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002620f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002620f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LONG __stdcall SCardListReaderGroupsA(SCARDCONTEXT hContext, LPSTR mszGroups, LPDWORD pcchGroups)
{
  LONG v6; // edi
  CHandleList *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v10; // rbx
  struct _REDIR_LOCAL_SCARDCONTEXT *v11; // rsi
  unsigned int v12; // r14d
  ulong pExceptionObject; // [rsp+24h] [rbp-64h] BYREF
  ulong v15; // [rsp+28h] [rbp-60h] BYREF
  ulong v16; // [rsp+2Ch] [rbp-5Ch] BYREF
  LONG v17; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-50h] BYREF
  int v19; // [rsp+48h] [rbp-40h]
  int v20; // [rsp+4Ch] [rbp-3Ch]

  v6 = 0;
  try
  {
    v18[0] = &CBuffer::`vftable';
    v18[1] = 0;
    v19 = 0;
    v20 = 0;
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
        v15 = -2146435042;
        throw &v15;
      }
      v11 = *(struct _REDIR_LOCAL_SCARDCONTEXT **)(v10 + 128);
      if ( v11 )
        goto LABEL_12;
      v12 = *(_DWORD *)(v10 + 28);
    }
    else
    {
      v10 = 0;
      v11 = 0;
      v12 = 2;
    }
    if ( RedirectionContextIsLocal(0) )
    {
      ListReaderGroups(v12, (struct CBuffer *)v18);
      PlaceMultiResult((struct CSCardUserContext *)v10, (struct CBuffer *)v18, mszGroups, pcchGroups);
LABEL_15:
      v18[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v18);
      return v6;
    }
LABEL_12:
    if ( RedirectDisabled() )
    {
      v16 = -2146435043;
      throw &v16;
    }
    v6 = I_SCardListReaderGroups(v11, (unsigned __int8 *)mszGroups, pcchGroups, 0);
    goto LABEL_15;
  }
  catch ( ulong v17 )
  {
    return v17;
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
0x180026190  mov     r11, rsp
0x180026193  push    rbx
0x180026194  push    rsi
0x180026195  push    rdi
0x180026196  push    r12
0x180026198  push    r14
0x18002619a  push    r15
0x18002619c  sub     rsp, 58h
0x1800261a0  mov     r15, r8
0x1800261a3  mov     r12, rdx
0x1800261a6  mov     rsi, rcx
0x1800261a9  xor     edi, edi
0x1800261ab  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800261b2  mov     [r11-50h], rax
0x1800261b6  mov     [r11-48h], rdi
0x1800261ba  mov     [rsp+88h+var_40], edi
0x1800261be  mov     [rsp+88h+var_3C], edi
0x1800261c2  test    rcx, rcx
0x1800261c5  jz      short loc_180026246
0x1800261c7  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x1800261ce  lea     r14, [rbx+20h]
0x1800261d2  mov     [r11+20h], r14
0x1800261d6  mov     rcx, r14; lpCriticalSection
0x1800261d9  call    cs:__imp_EnterCriticalSection
0x1800261df  nop
0x1800261e0  mov     rdx, rsi; unsigned __int64
0x1800261e3  mov     rcx, rbx; this
0x1800261e6  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800261eb  test    rax, rax
0x1800261ee  jnz     short loc_180026209
0x1800261f0  mov     [rsp+88h+pExceptionObject], 6
0x1800261f8  lea     rdx, _TI1K; pThrowInfo
0x1800261ff  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180026204  call    _CxxThrowException_0
0x180026209  mov     rbx, [rax]
0x18002620c  mov     rcx, r14; lpCriticalSection
0x18002620f  call    cs:__imp_LeaveCriticalSection
0x180026215  cmp     dword ptr [rbx+10h], 0
0x180026219  jz      short loc_180026234
0x18002621b  mov     [rsp+88h+var_60], 8010001Eh
0x180026223  lea     rdx, _TI1K; pThrowInfo
0x18002622a  lea     rcx, [rsp+88h+var_60]; pExceptionObject
0x18002622f  call    _CxxThrowException_0
0x180026234  mov     rsi, [rbx+80h]
0x18002623b  test    rsi, rsi
0x18002623e  jnz     short loc_18002627B
0x180026240  mov     r14d, [rbx+1Ch]
0x180026244  jmp     short loc_18002624E
0x180026246  xor     ebx, ebx
0x180026248  xor     esi, esi
0x18002624a  lea     r14d, [rbx+2]
0x18002624e  xor     ecx, ecx; lpCriticalSection
0x180026250  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180026255  test    al, al
0x180026257  jz      short loc_18002627B
0x180026259  lea     rdx, [rsp+88h+var_50]; struct CBuffer *
0x18002625e  mov     ecx, r14d; unsigned int
0x180026261  call    ?ListReaderGroups@@YAXKAEAVCBuffer@@@Z; ListReaderGroups(ulong,CBuffer &)
0x180026266  mov     r9, r15; unsigned int *
0x180026269  mov     r8, r12; char *
0x18002626c  lea     rdx, [rsp+88h+var_50]; struct CBuffer *
0x180026271  mov     rcx, rbx; this
0x180026274  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEADPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,char *,ulong *)
0x180026279  jmp     short loc_1800262B4
0x18002627b  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180026280  test    al, al
0x180026282  jz      short loc_18002629D
0x180026284  mov     [rsp+88h+var_5C], 8010001Dh
0x18002628c  lea     rdx, _TI1K; pThrowInfo
0x180026293  lea     rcx, [rsp+88h+var_5C]; pExceptionObject
0x180026298  call    _CxxThrowException_0
0x18002629d  xor     r9d, r9d; int
0x1800262a0  mov     r8, r15; unsigned int *
0x1800262a3  mov     rdx, r12; unsigned __int8 *
0x1800262a6  mov     rcx, rsi; struct _REDIR_LOCAL_SCARDCONTEXT *
0x1800262a9  call    ?I_SCardListReaderGroups@@YAJ_KPEAEPEAKH@Z; I_SCardListReaderGroups(unsigned __int64,uchar *,ulong *,int)
0x1800262ae  mov     edi, eax
0x1800262b0  mov     [rsp+88h+var_68], eax
0x1800262b4  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800262bb  mov     [rsp+88h+var_50], rax
0x1800262c0  lea     rcx, [rsp+88h+var_50]; this
0x1800262c5  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800262ca  nop
0x1800262cb  jmp     short loc_1800262D3
0x1800262cd  jmp     short $+2
0x1800262cf  mov     edi, [rsp+88h+var_68]
0x1800262d3  mov     eax, edi
0x1800262d5  add     rsp, 58h
0x1800262d9  pop     r15
0x1800262db  pop     r14
0x1800262dd  pop     r12
0x1800262df  pop     rdi
0x1800262e0  pop     rsi
0x1800262e1  pop     rbx
0x1800262e2  retn
```
