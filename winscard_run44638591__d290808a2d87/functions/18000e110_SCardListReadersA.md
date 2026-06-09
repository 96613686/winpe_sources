# SCardListReadersA

- ea: `0x18000e110`
- end: `0x18000e3c2`
- name: `SCardListReadersA`
- size: `690`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR mszGroups, LPSTR mszReaders, LPDWORD pcchReaders)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x1800093e4`
- `0x180009480`
- `0x18000e110`
- `0x18000e3d0`
- `0x18000e400`
- `0x18000e470`
- `0x18000e680`
- `0x180010898`
- `0x180012650`
- `0x180019b80`
- `0x18001b9b8`
- `0x18002ef20`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e2aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e2aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e332`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e332`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
LONG __stdcall SCardListReadersA(SCARDCONTEXT hContext, LPCSTR mszGroups, LPSTR mszReaders, LPDWORD pcchReaders)
{
  LONG v7; // r12d
  void *v8; // rdi
  __int64 v9; // rbx
  unsigned int v10; // r14d
  struct _REDIR_LOCAL_SCARDCONTEXT *v11; // rsi
  const unsigned __int16 *v12; // rax
  CHandleList *v14; // rsi
  struct _RTL_CRITICAL_SECTION *v15; // r14
  SCARDCONTEXT v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  ulong v19; // [rsp+34h] [rbp-A4h] BYREF
  ulong pExceptionObject; // [rsp+38h] [rbp-A0h] BYREF
  ulong v21; // [rsp+3Ch] [rbp-9Ch] BYREF
  const int *v22; // [rsp+40h] [rbp-98h] BYREF
  void *v23; // [rsp+48h] [rbp-90h]
  int v24; // [rsp+50h] [rbp-88h]
  int v25; // [rsp+54h] [rbp-84h]
  void **v26; // [rsp+60h] [rbp-78h] BYREF
  int v27; // [rsp+68h] [rbp-70h]
  _QWORD v28[2]; // [rsp+70h] [rbp-68h] BYREF
  int v29; // [rsp+80h] [rbp-58h]
  int v30; // [rsp+84h] [rbp-54h]
  _QWORD v31[2]; // [rsp+88h] [rbp-50h] BYREF
  int v32; // [rsp+98h] [rbp-40h]
  int v33; // [rsp+9Ch] [rbp-3Ch]
  LONG v34; // [rsp+A0h] [rbp-38h] BYREF
  char *v35; // [rsp+A8h] [rbp-30h]

  v7 = 0;
  try
  {
    v22 = &CBuffer::`vftable';
    v8 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v28[0] = &CBuffer::`vftable';
    v28[1] = 0;
    v29 = 0;
    v30 = 0;
    v31[0] = &CBuffer::`vftable';
    v31[1] = 0;
    v32 = 0;
    v33 = 0;
    v27 = 3;
    v26 = &CTextMultistring::`vftable';
    if ( hContext )
    {
      v14 = g_phlContexts;
      v15 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
      v35 = (char *)g_phlContexts + 32;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
      if ( HIBYTE(hContext) != *((_BYTE *)v14 + 8)
        || *((_DWORD *)v14 + 4) <= (hContext & 0x7FFFFFFF)
        || (v16 = 16 * (hContext & 0x7FFFFFFF),
            v17 = *((_QWORD *)v14 + 3),
            ((*(_DWORD *)(v16 + v17 + 8) ^ HIDWORD(hContext)) & 0xFFFFFF) != 0) )
      {
        pExceptionObject = 6;
        throw &pExceptionObject;
      }
      v9 = *(_QWORD *)(v16 + v17);
      LeaveCriticalSection(v15);
      if ( *(_DWORD *)(v9 + 16) )
      {
        v19 = -2146435042;
        throw &v19;
      }
      v10 = *(_DWORD *)(v9 + 28);
      v11 = *(struct _REDIR_LOCAL_SCARDCONTEXT **)(v9 + 128);
      if ( v11 )
        goto LABEL_21;
    }
    else
    {
      v9 = 0;
      v10 = 2;
      v11 = 0;
    }
    if ( RedirectionContextIsLocal(0) )
    {
      if ( mszGroups )
      {
        v18 = ((__int64 (__fastcall *)(void ***, LPCSTR))v26[2])(&v26, mszGroups);
        CBuffer::Set((CBuffer *)v31, (const unsigned __int8 *const)mszGroups, v18 + 1);
      }
      else
      {
        v32 = 0;
      }
      v27 = 1;
      v12 = CTextString::Unicode((CTextString *)&v26);
      ListReaders(v10, v12, (struct CBuffer *)&v22);
      if ( v9 )
        CSCardUserContext::StripInactiveReaders((CSCardUserContext *)v9, (struct CBuffer *)&v22);
      PlaceMultiResult((struct CSCardUserContext *)v9, (struct CBuffer *)&v22, mszReaders, pcchReaders);
      v8 = v23;
LABEL_10:
      v26 = &CTextString::`vftable';
      v31[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v31);
      v28[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v28);
      v22 = &CBuffer::`vftable';
      if ( v8 )
        operator delete(v8);
      v23 = 0;
      v24 = 0;
      v25 = 0;
      return v7;
    }
LABEL_21:
    if ( RedirectDisabled() )
    {
      v21 = -2146435043;
      throw &v21;
    }
    v7 = I_SCardListReaders(v11, (const unsigned __int16 *)mszGroups, (unsigned __int8 *)mszReaders, pcchReaders, 0);
    goto LABEL_10;
  }
  catch ( ulong v34 )
  {
    return v34;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v7;
}

```

## disassembly

```asm
0x18000e110  mov     r11, rsp
0x18000e113  mov     [r11+8], rbx
0x18000e117  mov     [r11+10h], rsi
0x18000e11b  mov     [r11+18h], r8
0x18000e11f  push    rdi
0x18000e120  push    r12
0x18000e122  push    r13
0x18000e124  push    r14
0x18000e126  push    r15
0x18000e128  sub     rsp, 0B0h
0x18000e12f  mov     r13, r9
0x18000e132  mov     r15, rdx
0x18000e135  mov     rbx, rcx
0x18000e138  xor     ecx, ecx
0x18000e13a  mov     r12d, ecx
0x18000e13d  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000e144  mov     [rsp+0D8h+var_98], rax
0x18000e149  mov     edi, ecx
0x18000e14b  mov     [rsp+0D8h+var_90], rcx
0x18000e150  mov     [rsp+0D8h+var_88], ecx
0x18000e154  mov     [rsp+0D8h+var_84], ecx
0x18000e158  lea     rdx, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18000e15f  mov     [r11-78h], rdx
0x18000e163  mov     [r11-68h], rax
0x18000e167  mov     [r11-60h], rcx
0x18000e16b  mov     [r11-58h], ecx
0x18000e16f  mov     [r11-54h], ecx
0x18000e173  mov     [r11-50h], rax
0x18000e177  mov     [r11-48h], rcx
0x18000e17b  mov     [r11-40h], ecx
0x18000e17f  mov     [r11-3Ch], ecx
0x18000e183  mov     [rsp+0D8h+var_70], 3
0x18000e18b  lea     rax, ??_7CTextMultistring@@6B@; const CTextMultistring::`vftable'
0x18000e192  mov     [r11-78h], rax
0x18000e196  test    rbx, rbx
0x18000e199  jnz     loc_18000E294
0x18000e19f  mov     ebx, ecx
0x18000e1a1  mov     r14d, 2
0x18000e1a7  mov     esi, ecx
0x18000e1a9  xor     ecx, ecx; lpCriticalSection
0x18000e1ab  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x18000e1b0  test    al, al
0x18000e1b2  jz      loc_18000E352
0x18000e1b8  test    r15, r15
0x18000e1bb  jnz     loc_18000E2FC
0x18000e1c1  mov     [rsp+0D8h+var_40], r15d
0x18000e1c9  mov     [rsp+0D8h+var_70], 1
0x18000e1d1  lea     rcx, [rsp+0D8h+var_78]; this
0x18000e1d6  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18000e1db  lea     r8, [rsp+0D8h+var_98]; struct CBuffer *
0x18000e1e0  mov     rdx, rax; unsigned __int16 *
0x18000e1e3  mov     ecx, r14d; unsigned int
0x18000e1e6  call    ?ListReaders@@YAXKPEBGAEAVCBuffer@@@Z; ListReaders(ulong,ushort const *,CBuffer &)
0x18000e1eb  test    rbx, rbx
0x18000e1ee  jz      short loc_18000E1FD
0x18000e1f0  lea     rdx, [rsp+0D8h+var_98]; struct CBuffer *
0x18000e1f5  mov     rcx, rbx; this
0x18000e1f8  call    ?StripInactiveReaders@CSCardUserContext@@QEAAXAEAVCBuffer@@@Z; CSCardUserContext::StripInactiveReaders(CBuffer &)
0x18000e1fd  mov     r9, r13; unsigned int *
0x18000e200  mov     r8, [rsp+0D8h+arg_10]; char *
0x18000e208  lea     rdx, [rsp+0D8h+var_98]; struct CBuffer *
0x18000e20d  mov     rcx, rbx; this
0x18000e210  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEADPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,char *,ulong *)
0x18000e215  mov     rdi, [rsp+0D8h+var_90]
0x18000e21a  xor     ebx, ebx
0x18000e21c  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18000e223  mov     [rsp+0D8h+var_78], rax
0x18000e228  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000e22f  mov     [rsp+0D8h+var_50], rsi
0x18000e237  lea     rcx, [rsp+0D8h+var_50]; this
0x18000e23f  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18000e244  nop
0x18000e245  mov     [rsp+0D8h+var_68], rsi
0x18000e24a  lea     rcx, [rsp+0D8h+var_68]; this
0x18000e24f  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18000e254  nop
0x18000e255  mov     [rsp+0D8h+var_98], rsi
0x18000e25a  test    rdi, rdi
0x18000e25d  jz      short loc_18000E267
0x18000e25f  mov     rcx, rdi; void *
0x18000e262  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e267  mov     [rsp+0D8h+var_90], rbx
0x18000e26c  mov     [rsp+0D8h+var_88], ebx
0x18000e270  mov     [rsp+0D8h+var_84], ebx
0x18000e274  mov     eax, r12d
0x18000e277  lea     r11, [rsp+0D8h+var_28]
0x18000e27f  mov     rbx, [r11+30h]
0x18000e283  mov     rsi, [r11+38h]
0x18000e287  mov     rsp, r11
0x18000e28a  pop     r15
0x18000e28c  pop     r14
0x18000e28e  pop     r13
0x18000e290  pop     r12
0x18000e292  pop     rdi
0x18000e293  retn
0x18000e294  mov     rsi, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18000e29b  lea     r14, [rsi+20h]
0x18000e29f  mov     [rsp+0D8h+var_30], r14
0x18000e2a7  mov     rcx, r14; lpCriticalSection
0x18000e2aa  call    cs:__imp_EnterCriticalSection
0x18000e2b0  nop
0x18000e2b1  mov     rax, rbx
0x18000e2b4  shr     rax, 38h
0x18000e2b8  cmp     al, [rsi+8]
0x18000e2bb  jnz     short loc_18000E2E2
0x18000e2bd  mov     eax, ebx
0x18000e2bf  btr     eax, 1Fh
0x18000e2c3  cmp     [rsi+10h], eax
0x18000e2c6  jbe     short loc_18000E2E2
0x18000e2c8  mov     edx, eax
0x18000e2ca  shl     rdx, 4
0x18000e2ce  mov     rax, [rsi+18h]
0x18000e2d2  shr     rbx, 20h
0x18000e2d6  xor     ebx, [rdx+rax+8]
0x18000e2da  test    ebx, 0FFFFFFh
0x18000e2e0  jz      short loc_18000E32B
0x18000e2e2  mov     [rsp+0D8h+pExceptionObject], 6
0x18000e2ea  lea     rdx, _TI1K; pThrowInfo
0x18000e2f1  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000e2f6  call    _CxxThrowException_0
0x18000e2fc  mov     rax, [rsp+0D8h+var_78]
0x18000e301  mov     rdx, r15
0x18000e304  lea     rcx, [rsp+0D8h+var_78]
0x18000e309  mov     rax, [rax+10h]
0x18000e30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e312  lea     r8d, [rax+1]; unsigned int
0x18000e316  mov     rdx, r15; unsigned __int8 *
0x18000e319  lea     rcx, [rsp+0D8h+var_50]; this
0x18000e321  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18000e326  jmp     loc_18000E1C9
0x18000e32b  mov     rbx, [rdx+rax]
0x18000e32f  mov     rcx, r14; lpCriticalSection
0x18000e332  call    cs:__imp_LeaveCriticalSection
0x18000e338  cmp     dword ptr [rbx+10h], 0
0x18000e33c  jnz     short loc_18000E383
0x18000e33e  mov     r14d, [rbx+1Ch]
0x18000e342  mov     rsi, [rbx+80h]
0x18000e349  test    rsi, rsi
0x18000e34c  jz      loc_18000E1A9
0x18000e352  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x18000e357  test    al, al
0x18000e359  jnz     short loc_18000E39C
0x18000e35b  xor     ebx, ebx
0x18000e35d  mov     [rsp+0D8h+var_B8], ebx; int
0x18000e361  mov     r9, r13; unsigned int *
0x18000e364  mov     r8, [rsp+0D8h+arg_10]; unsigned __int8 *
0x18000e36c  mov     rdx, r15; unsigned __int8 *
0x18000e36f  mov     rcx, rsi; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18000e372  call    ?I_SCardListReaders@@YAJ_KPEBEPEAEPEAKH@Z; I_SCardListReaders(unsigned __int64,uchar const *,uchar *,ulong *,int)
0x18000e377  mov     r12d, eax
0x18000e37a  mov     [rsp+0D8h+var_A8], eax
0x18000e37e  jmp     loc_18000E21C
0x18000e383  mov     [rsp+0D8h+var_A4], 8010001Eh
0x18000e38b  lea     rdx, _TI1K; pThrowInfo
0x18000e392  lea     rcx, [rsp+0D8h+var_A4]; pExceptionObject
0x18000e397  call    _CxxThrowException_0
0x18000e39c  mov     [rsp+0D8h+var_9C], 8010001Dh
0x18000e3a4  lea     rdx, _TI1K; pThrowInfo
0x18000e3ab  lea     rcx, [rsp+0D8h+var_9C]; pExceptionObject
0x18000e3b0  call    _CxxThrowException_0
0x18000e3b6  jmp     short $+2
0x18000e3b8  mov     r12d, [rsp+0D8h+var_A8]
0x18000e3bd  jmp     loc_18000E274
```
