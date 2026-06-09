# SCardConnectW

- ea: `0x180011b70`
- end: `0x180011fec`
- name: `SCardConnectW`
- size: `1148`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR szReader, DWORD dwShareMode, DWORD dwPreferredProtocols, LPSCARDHANDLE phCard, LPDWORD pdwActiveProtocol)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028ed8`

## callees

- `0x180005a90`
- `0x180008f70`
- `0x18000d640`
- `0x18000dab0`
- `0x18000e090`
- `0x18000e680`
- `0x180011b70`
- `0x180012480`
- `0x180012650`
- `0x1800153a0`
- `0x1800170f8`
- `0x18001b9b8`
- `0x18001b9c4`
- `0x18002ef20`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011bc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011bc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LONG __stdcall SCardConnectW(
        SCARDCONTEXT hContext,
        LPCWSTR szReader,
        DWORD dwShareMode,
        DWORD dwPreferredProtocols,
        LPSCARDHANDLE phCard,
        LPDWORD pdwActiveProtocol)
{
  LONG v8; // esi
  CHandleList *v9; // rdi
  struct _RTL_CRITICAL_SECTION *v10; // r14
  SCARDCONTEXT v11; // rdi
  __int64 v12; // rdi
  int v13; // eax
  char *v14; // rbx
  __int64 v15; // r14
  __int64 v16; // r13
  unsigned __int64 v17; // rdi
  struct CSCardSubcontext *v18; // rdi
  const unsigned __int16 *v19; // rdx
  struct CBuffer *v20; // r8
  const WCHAR *v21; // r9
  void *v22; // r14
  ulong v23; // eax
  int v25; // [rsp+30h] [rbp-D8h]
  int v26; // [rsp+38h] [rbp-D0h]
  int v27; // [rsp+40h] [rbp-C8h]
  int pExceptionObject; // [rsp+50h] [rbp-B8h] BYREF
  ulong v29; // [rsp+54h] [rbp-B4h] BYREF
  ulong v30; // [rsp+58h] [rbp-B0h] BYREF
  ulong v31; // [rsp+5Ch] [rbp-ACh] BYREF
  ulong v32; // [rsp+60h] [rbp-A8h] BYREF
  ulong v33; // [rsp+64h] [rbp-A4h] BYREF
  ulong v34; // [rsp+68h] [rbp-A0h] BYREF
  void (__fastcall ***v35)(_QWORD, __int64); // [rsp+70h] [rbp-98h]
  const int *v36; // [rsp+78h] [rbp-90h] BYREF
  void *v37; // [rsp+80h] [rbp-88h]
  int v38; // [rsp+88h] [rbp-80h]
  int v39; // [rsp+8Ch] [rbp-7Ch]
  void **v40; // [rsp+90h] [rbp-78h] BYREF
  int v41; // [rsp+98h] [rbp-70h]
  _QWORD v42[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v43; // [rsp+B0h] [rbp-58h]
  int v44; // [rsp+B4h] [rbp-54h]
  const int *v45; // [rsp+B8h] [rbp-50h]
  __int64 v46; // [rsp+C0h] [rbp-48h]
  int v47; // [rsp+C8h] [rbp-40h]
  int v48; // [rsp+CCh] [rbp-3Ch]
  LONG v49; // [rsp+D0h] [rbp-38h] BYREF
  char *v50; // [rsp+D8h] [rbp-30h]

  v8 = 0;
  v35 = 0;
  try
  {
    *phCard = 0;
    v9 = g_phlContexts;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v50 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    if ( HIBYTE(hContext) != *((_BYTE *)v9 + 8)
      || *((_DWORD *)v9 + 4) <= (hContext & 0x7FFFFFFF)
      || (v11 = 16 * (hContext & 0x7FFFFFFF) + *((_QWORD *)v9 + 3),
          ((*(_DWORD *)(v11 + 8) ^ HIDWORD(hContext)) & 0xFFFFFF) != 0)
      || !v11 )
    {
      v34 = 6;
      throw &v34;
    }
    v12 = *(_QWORD *)v11;
    LeaveCriticalSection(v10);
    v40 = &CTextString::`vftable';
    v42[0] = &CBuffer::`vftable';
    v42[1] = 0;
    v43 = 0;
    v44 = 0;
    v45 = &CBuffer::`vftable';
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v41 = 3;
    if ( *(_DWORD *)(v12 + 16) )
    {
      pExceptionObject = -2146435042;
      throw (ulong *)&pExceptionObject;
    }
    if ( szReader )
    {
      v13 = ((__int64 (__fastcall *)(void ***, LPCWSTR))v40[1])(&v40, szReader);
      CBuffer::Set((CBuffer *)v42, (const unsigned __int8 *const)szReader, 2 * v13 + 2);
    }
    else
    {
      v43 = 0;
    }
    v41 = 2;
    v14 = (char *)operator new(0x30u);
    v50 = v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = &CHandle::`vftable';
      *((_DWORD *)v14 + 2) = 0;
      *((_DWORD *)v14 + 3) = 0x7FFFFFFF;
      *((_DWORD *)v14 + 4) = 0;
      *(_QWORD *)v14 = &CReaderContext::`vftable';
      *((_DWORD *)v14 + 9) = 0;
      *((_QWORD *)v14 + 3) = 0;
      *((_DWORD *)v14 + 8) = -1;
      *((_QWORD *)v14 + 5) = 0;
    }
    else
    {
      v14 = 0;
    }
    v35 = (void (__fastcall ***)(_QWORD, __int64))v14;
    if ( !v14 )
    {
      v29 = -2146435066;
      throw &v29;
    }
    v15 = *(_QWORD *)(v12 + 128);
    v16 = *(_QWORD *)(v12 + 136);
    if ( v15 )
    {
      v17 = CHandleList::Add(g_phlReaders, (struct CHandle *)v14, *(_DWORD *)(v16 + 72));
      v8 = I_SCardConnect(
             v15,
             (const unsigned __int8 *)szReader,
             dwShareMode,
             dwPreferredProtocols,
             phCard,
             pdwActiveProtocol,
             1);
      if ( v8 )
      {
        CHandleList::Close(g_phlReaders, v17);
        (**(void (__fastcall ***)(void *, __int64))v14)(v14, 1);
      }
      else
      {
        *((_QWORD *)v14 + 5) = *phCard;
        *phCard = v17;
      }
    }
    else
    {
      v18 = CSCardUserContext::AcquireSubcontext((CSCardUserContext *)v12, 1);
      if ( !v18 )
      {
        v30 = -2146435066;
        throw &v30;
      }
      v19 = CTextString::Unicode((CTextString *)&v40);
      v36 = &CBuffer::`vftable';
      v37 = 0;
      v38 = 0;
      v39 = 0;
      if ( !*v19 )
      {
        v31 = -2146435063;
        throw &v31;
      }
      if ( !(unsigned int)GetReaderInfo(*(_DWORD *)(*((_QWORD *)v18 + 5) + 28LL), v19, v20, (const void **)&v36) )
      {
        v32 = -2146435063;
        throw &v32;
      }
      v21 = &WideCharStr;
      v22 = v37;
      if ( v39 )
        LODWORD(v21) = (_DWORD)v37;
      v23 = CalRpcConnect(
              *((_QWORD *)v18 + 14),
              dwPreferredProtocols,
              dwShareMode,
              (int)v21,
              (__int64)(v14 + 32),
              (__int64)(v14 + 36),
              v25,
              v26,
              v27,
              (int)v18,
              pExceptionObject);
      if ( v23 )
      {
        v33 = v23;
        throw &v33;
      }
      *((_QWORD *)v14 + 3) = v18;
      v36 = &CBuffer::`vftable';
      if ( v22 )
        operator delete(v22);
      v37 = 0;
      v38 = 0;
      v39 = 0;
      CSCardSubcontext::ReleaseSubcontext(*((CSCardSubcontext **)v14 + 3));
      if ( pdwActiveProtocol )
        *pdwActiveProtocol = *((_DWORD *)v14 + 9);
      *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL) = CHandleList::Add(
                                                  g_phlReaders,
                                                  (struct CHandle *)v14,
                                                  *(_DWORD *)(v16 + 72));
      *phCard = *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL);
    }
    CTextString::~CTextString((CTextString *)&v40);
  }
  catch ( ulong v49 )
  {
    if ( v35 )
      (**v35)(v35, 1);
    return v49;
  }
  catch ( ... )
  {
    if ( v35 )
      (**v35)(v35, 1);
    return -2146435068;
  }
  return v8;
}

```

## disassembly

```asm
0x180011b70  mov     rax, rsp
0x180011b73  mov     [rax+8], rbx
0x180011b77  mov     [rax+10h], rsi
0x180011b7b  mov     [rax+20h], r9d
0x180011b7f  mov     [rax+18h], r8d
0x180011b83  push    rdi
0x180011b84  push    r12
0x180011b86  push    r13
0x180011b88  push    r14
0x180011b8a  push    r15
0x180011b8c  sub     rsp, 0E0h
0x180011b93  mov     r12, rdx
0x180011b96  mov     rbx, rcx
0x180011b99  xor     r13d, r13d
0x180011b9c  mov     esi, r13d
0x180011b9f  mov     [rsp+108h+var_98], r13
0x180011ba4  mov     qword ptr [rsp+108h+var_C0], r13
0x180011ba9  mov     r15, [rsp+108h+phCard]
0x180011bb1  mov     [r15], r13
0x180011bb4  mov     rdi, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180011bbb  lea     r14, [rdi+20h]
0x180011bbf  mov     [rax-30h], r14
0x180011bc3  mov     rcx, r14; lpCriticalSection
0x180011bc6  call    cs:__imp_EnterCriticalSection
0x180011bcc  nop
0x180011bcd  mov     rax, rbx
0x180011bd0  shr     rax, 38h
0x180011bd4  cmp     al, [rdi+8]
0x180011bd7  jnz     loc_180011FAD
0x180011bdd  mov     eax, ebx
0x180011bdf  btr     eax, 1Fh
0x180011be3  cmp     [rdi+10h], eax
0x180011be6  jbe     loc_180011FAD
0x180011bec  mov     edx, eax
0x180011bee  shl     rdx, 4
0x180011bf2  mov     rdi, [rdi+18h]
0x180011bf6  add     rdi, rdx
0x180011bf9  shr     rbx, 20h
0x180011bfd  xor     ebx, [rdi+8]
0x180011c00  test    ebx, 0FFFFFFh
0x180011c06  jnz     loc_180011FAD
0x180011c0c  test    rdi, rdi
0x180011c0f  jz      loc_180011FAD
0x180011c15  mov     rdi, [rdi]
0x180011c18  mov     rcx, r14; lpCriticalSection
0x180011c1b  call    cs:__imp_LeaveCriticalSection
0x180011c21  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180011c28  mov     [rsp+108h+var_78], rax
0x180011c30  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180011c37  mov     [rsp+108h+var_68], rax
0x180011c3f  mov     [rsp+108h+var_60], r13
0x180011c47  mov     [rsp+108h+var_58], r13d
0x180011c4f  mov     [rsp+108h+var_54], r13d
0x180011c57  mov     [rsp+108h+var_50], rax
0x180011c5f  mov     [rsp+108h+var_48], r13
0x180011c67  mov     [rsp+108h+var_40], r13d
0x180011c6f  mov     [rsp+108h+var_3C], r13d
0x180011c77  mov     [rsp+108h+var_70], 3
0x180011c82  cmp     [rdi+10h], r13d
0x180011c86  jz      short loc_180011CA1
0x180011c88  mov     [rsp+108h+pExceptionObject], 8010001Eh
0x180011c90  lea     rdx, _TI1K; pThrowInfo
0x180011c97  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180011c9c  call    _CxxThrowException_0
0x180011ca1  test    r12, r12
0x180011ca4  jz      short loc_180011CDC
0x180011ca6  mov     rax, [rsp+108h+var_78]
0x180011cae  mov     rdx, r12
0x180011cb1  lea     rcx, [rsp+108h+var_78]
0x180011cb9  mov     rax, [rax+8]
0x180011cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc2  lea     r8d, ds:2[rax*2]; unsigned int
0x180011cca  mov     rdx, r12; unsigned __int8 *
0x180011ccd  lea     rcx, [rsp+108h+var_68]; this
0x180011cd5  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x180011cda  jmp     short loc_180011CE4
0x180011cdc  mov     [rsp+108h+var_58], r13d
0x180011ce4  mov     [rsp+108h+var_70], 2
0x180011cef  mov     ecx, 30h ; '0'; Size
0x180011cf4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011cf9  mov     rbx, rax
0x180011cfc  mov     [rsp+108h+var_30], rax
0x180011d04  test    rax, rax
0x180011d07  jz      short loc_180011D41
0x180011d09  lea     rax, ??_7CHandle@@6B@; const CHandle::`vftable'
0x180011d10  mov     [rbx], rax
0x180011d13  mov     [rbx+8], r13d
0x180011d17  mov     dword ptr [rbx+0Ch], 7FFFFFFFh
0x180011d1e  mov     [rbx+10h], r13d
0x180011d22  lea     rax, ??_7CReaderContext@@6B@; const CReaderContext::`vftable'
0x180011d29  mov     [rbx], rax
0x180011d2c  mov     [rbx+24h], r13d
0x180011d30  mov     [rbx+18h], r13
0x180011d34  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x180011d3b  mov     [rbx+28h], r13
0x180011d3f  jmp     short loc_180011D44
0x180011d41  mov     rbx, r13
0x180011d44  mov     [rsp+108h+var_98], rbx
0x180011d49  test    rbx, rbx
0x180011d4c  jnz     short loc_180011D67
0x180011d4e  mov     [rsp+108h+var_B4], 80100006h
0x180011d56  lea     rdx, _TI1K; pThrowInfo
0x180011d5d  lea     rcx, [rsp+108h+var_B4]; pExceptionObject
0x180011d62  call    _CxxThrowException_0
0x180011d67  mov     r14, [rdi+80h]
0x180011d6e  mov     r13, [rdi+88h]
0x180011d75  test    r14, r14
0x180011d78  jz      loc_180011E09
0x180011d7e  mov     r8d, [r13+48h]; unsigned int
0x180011d82  mov     rdx, rbx; struct CHandle *
0x180011d85  mov     rcx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; this
0x180011d8c  call    ?Add@CHandleList@@QEAA_KPEAVCHandle@@K@Z; CHandleList::Add(CHandle *,ulong)
0x180011d91  mov     rdi, rax
0x180011d94  mov     [rsp+108h+var_D8], 1; int
0x180011d9c  mov     rax, [rsp+108h+pdwActiveProtocol]
0x180011da4  mov     [rsp+108h+var_E0], rax; unsigned int *
0x180011da9  mov     [rsp+108h+var_E8], r15; unsigned __int64 *
0x180011dae  mov     r9d, [rsp+108h+arg_18]; unsigned int
0x180011db6  mov     r8d, [rsp+108h+arg_10]; unsigned int
0x180011dbe  mov     rdx, r12; unsigned __int8 *
0x180011dc1  mov     rcx, r14; unsigned __int64
0x180011dc4  call    ?I_SCardConnect@@YAJ_KPEBEKKPEA_KPEAKH@Z; I_SCardConnect(unsigned __int64,uchar const *,ulong,ulong,unsigned __int64 *,ulong *,int)
0x180011dc9  mov     esi, eax
0x180011dcb  mov     [rsp+108h+var_C8], eax
0x180011dcf  test    eax, eax
0x180011dd1  jnz     short loc_180011DE2
0x180011dd3  mov     rax, [r15]
0x180011dd6  mov     [rbx+28h], rax
0x180011dda  mov     [r15], rdi
0x180011ddd  jmp     loc_180011F9D
0x180011de2  mov     rdx, rdi; unsigned __int64
0x180011de5  mov     rcx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; this
0x180011dec  call    ?Close@CHandleList@@QEAAPEAVCHandle@@_K@Z; CHandleList::Close(unsigned __int64)
0x180011df1  mov     rax, [rbx]
0x180011df4  mov     edx, 1
0x180011df9  mov     rcx, rbx
0x180011dfc  mov     rax, [rax]
0x180011dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e04  jmp     loc_180011F9D
0x180011e09  mov     edx, 1; int
0x180011e0e  mov     rcx, rdi; this
0x180011e11  call    ?AcquireSubcontext@CSCardUserContext@@QEAAPEAVCSCardSubcontext@@H@Z; CSCardUserContext::AcquireSubcontext(int)
0x180011e16  mov     rdi, rax
0x180011e19  mov     qword ptr [rsp+108h+var_C0], rax; int
0x180011e1e  xor     r12d, r12d
0x180011e21  test    rax, rax
0x180011e24  jnz     short loc_180011E3F
0x180011e26  mov     [rsp+108h+var_B0], 80100006h
0x180011e2e  lea     rdx, _TI1K; pThrowInfo
0x180011e35  lea     rcx, [rsp+108h+var_B0]; pExceptionObject
0x180011e3a  call    _CxxThrowException_0
0x180011e3f  lea     rcx, [rsp+108h+var_78]; this
0x180011e47  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180011e4c  mov     rdx, rax; unsigned __int16 *
0x180011e4f  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180011e56  mov     [rsp+108h+var_90], rax
0x180011e5b  mov     [rsp+108h+var_88], r12
0x180011e63  mov     [rsp+108h+var_80], r12d
0x180011e6b  mov     [rsp+108h+var_7C], r12d
0x180011e73  cmp     r12w, [rdx]
0x180011e77  jnz     short loc_180011E92
0x180011e79  mov     [rsp+108h+var_AC], 80100009h
0x180011e81  lea     rdx, _TI1K; pThrowInfo
0x180011e88  lea     rcx, [rsp+108h+var_AC]; pExceptionObject
0x180011e8d  call    _CxxThrowException_0
0x180011e92  mov     rcx, [rdi+28h]
0x180011e96  lea     r9, [rsp+108h+var_90]; struct CBuffer *
0x180011e9b  mov     ecx, [rcx+1Ch]; unsigned int
0x180011e9e  call    ?GetReaderInfo@@YAHKPEBGPEAVCBuffer@@1@Z; GetReaderInfo(ulong,ushort const *,CBuffer *,CBuffer *)
0x180011ea3  test    eax, eax
0x180011ea5  jnz     short loc_180011EC0
0x180011ea7  mov     [rsp+108h+var_A8], 80100009h
0x180011eaf  lea     rdx, _TI1K; pThrowInfo
0x180011eb6  lea     rcx, [rsp+108h+var_A8]; pExceptionObject
0x180011ebb  call    _CxxThrowException_0
0x180011ec0  lea     r9, WideCharStr
0x180011ec7  mov     r14, [rsp+108h+var_88]
0x180011ecf  cmp     [rsp+108h+var_7C], r12d
0x180011ed7  cmova   r9, r14; int
0x180011edb  lea     r12, [rbx+24h]
0x180011edf  lea     rax, [rbx+20h]
0x180011ee3  mov     [rsp+108h+var_E0], r12; __int64
0x180011ee8  mov     [rsp+108h+var_E8], rax; __int64
0x180011eed  mov     r8d, [rsp+108h+arg_10]; int
0x180011ef5  mov     edx, [rsp+108h+arg_18]; int
0x180011efc  mov     rcx, [rdi+70h]; int
0x180011f00  call    CalRpcConnect
0x180011f05  test    eax, eax
0x180011f07  jz      short loc_180011F1E
0x180011f09  mov     [rsp+108h+var_A4], eax
0x180011f0d  lea     rdx, _TI1K; pThrowInfo
0x180011f14  lea     rcx, [rsp+108h+var_A4]; pExceptionObject
0x180011f19  call    _CxxThrowException_0
0x180011f1e  mov     [rbx+18h], rdi
0x180011f22  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180011f29  mov     [rsp+108h+var_90], rax
0x180011f2e  xor     edi, edi
0x180011f30  test    r14, r14
0x180011f33  jz      short loc_180011F3D
0x180011f35  mov     rcx, r14; void *
0x180011f38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011f3d  mov     [rsp+108h+var_88], rdi
0x180011f45  mov     [rsp+108h+var_80], edi
0x180011f4c  mov     [rsp+108h+var_7C], edi
0x180011f53  mov     qword ptr [rsp+108h+var_C0], rdi
0x180011f58  mov     rcx, [rbx+18h]; this
0x180011f5c  call    ?ReleaseSubcontext@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::ReleaseSubcontext(void)
0x180011f61  mov     rcx, [rsp+108h+pdwActiveProtocol]
0x180011f69  test    rcx, rcx
0x180011f6c  jz      short loc_180011F74
0x180011f6e  mov     eax, [r12]
0x180011f72  mov     [rcx], eax
0x180011f74  mov     r8d, [r13+48h]; unsigned int
0x180011f78  mov     rdx, rbx; struct CHandle *
0x180011f7b  mov     rcx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; this
0x180011f82  call    ?Add@CHandleList@@QEAA_KPEAVCHandle@@K@Z; CHandleList::Add(CHandle *,ulong)
0x180011f87  mov     rcx, rax
0x180011f8a  mov     rax, [rbx+18h]
0x180011f8e  mov     [rax+8], rcx
0x180011f92  mov     rax, [rbx+18h]
0x180011f96  mov     rcx, [rax+8]
0x180011f9a  mov     [r15], rcx
0x180011f9d  lea     rcx, [rsp+108h+var_78]; this
0x180011fa5  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180011faa  nop
0x180011fab  jmp     short loc_180011FCD
0x180011fad  mov     [rsp+108h+var_A0], 6
0x180011fb5  lea     rdx, _TI1K; pThrowInfo
0x180011fbc  lea     rcx, [rsp+108h+var_A0]; pExceptionObject
0x180011fc1  call    _CxxThrowException_0
0x180011fc7  jmp     short $+2
0x180011fc9  mov     esi, [rsp+108h+var_C8]
0x180011fcd  mov     eax, esi
0x180011fcf  lea     r11, [rsp+108h+var_28]
0x180011fd7  mov     rbx, [r11+30h]
0x180011fdb  mov     rsi, [r11+38h]
0x180011fdf  mov     rsp, r11
0x180011fe2  pop     r15
0x180011fe4  pop     r14
0x180011fe6  pop     r13
0x180011fe8  pop     r12
0x180011fea  pop     rdi
0x180011feb  retn
```
