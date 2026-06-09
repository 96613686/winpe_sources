# SCardGetReaderDeviceInstanceIdA

- ea: `0x1800257b0`
- end: `0x180025975`
- name: `SCardGetReaderDeviceInstanceIdA`
- size: `453`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800093e4`
- `0x18000e090`
- `0x18000e3d0`
- `0x18000e680`
- `0x180010898`
- `0x180011b0c`
- `0x1800126f0`
- `0x18001a538`
- `0x18001b65c`
- `0x1800257b0`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025840`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025840`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025879`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SCardGetReaderDeviceInstanceIdA(unsigned __int64 a1, __int64 a2, char *a3, unsigned int *a4)
{
  unsigned int v8; // edi
  CHandleList *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v12; // rbx
  const unsigned __int16 *v13; // rax
  ulong pExceptionObject; // [rsp+28h] [rbp-B0h] BYREF
  ulong v19; // [rsp+2Ch] [rbp-ACh] BYREF
  ulong v20; // [rsp+30h] [rbp-A8h] BYREF
  ulong v21; // [rsp+34h] [rbp-A4h] BYREF
  ulong v22; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-98h] BYREF
  int v24; // [rsp+50h] [rbp-88h]
  int v25; // [rsp+54h] [rbp-84h]
  ulong v26; // [rsp+58h] [rbp-80h] BYREF
  void **v27; // [rsp+60h] [rbp-78h] BYREF
  int v28; // [rsp+68h] [rbp-70h]
  const int *v29; // [rsp+70h] [rbp-68h]
  __int64 v30; // [rsp+78h] [rbp-60h]
  int v31; // [rsp+80h] [rbp-58h]
  int v32; // [rsp+84h] [rbp-54h]
  const int *v33; // [rsp+88h] [rbp-50h]
  __int64 v34; // [rsp+90h] [rbp-48h]
  int v35; // [rsp+98h] [rbp-40h]
  int v36; // [rsp+9Ch] [rbp-3Ch]

  v8 = 0;
  try
  {
    v27 = &CTextString::`vftable';
    v29 = &CBuffer::`vftable';
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = &CBuffer::`vftable';
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v28 = 3;
    if ( !a4 )
    {
      pExceptionObject = -2146435068;
      throw &pExceptionObject;
    }
    v9 = g_phlContexts;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v9, a1);
    if ( !HandlePtr )
    {
      v19 = 6;
      throw &v19;
    }
    v12 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v10);
    if ( *(_DWORD *)(v12 + 16) )
    {
      v20 = -2146435042;
      throw &v20;
    }
    if ( *(_QWORD *)(v12 + 128) || !RedirectionContextIsLocal(0) )
    {
      if ( RedirectDisabled() )
      {
        v21 = -2146435043;
        throw &v21;
      }
      v22 = -2146435049;
      throw &v22;
    }
    v23[0] = &CBuffer::`vftable';
    v23[1] = 0;
    v24 = 0;
    v25 = 0;
    CTextString::operator=(&v27, a2);
    v13 = CTextString::Unicode((CTextString *)&v27);
    CSCardUserContext::GetReaderDeviceInstanceId((CSCardUserContext *)v12, v13, (struct CBuffer *)v23);
    PlaceResult((struct CSCardUserContext *)v12, (struct CBuffer *)v23, a3, a4);
    v23[0] = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)v23);
    CTextString::~CTextString((CTextString *)&v27);
  }
  catch ( ulong v26 )
  {
    return v26;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v8;
}

```

## disassembly

```asm
0x1800257b0  mov     r11, rsp
0x1800257b3  push    rbx
0x1800257b4  push    rsi
0x1800257b5  push    rdi
0x1800257b6  push    r12
0x1800257b8  push    r13
0x1800257ba  push    r14
0x1800257bc  push    r15
0x1800257be  sub     rsp, 0A0h
0x1800257c5  mov     r14, r9
0x1800257c8  mov     r12, r8
0x1800257cb  mov     r13, rdx
0x1800257ce  mov     r15, rcx
0x1800257d1  xor     ecx, ecx
0x1800257d3  mov     edi, ecx
0x1800257d5  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x1800257dc  mov     [r11-78h], rax
0x1800257e0  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800257e7  mov     [r11-68h], rax
0x1800257eb  mov     [r11-60h], rcx
0x1800257ef  mov     [r11-58h], ecx
0x1800257f3  mov     [r11-54h], ecx
0x1800257f7  mov     [r11-50h], rax
0x1800257fb  mov     [r11-48h], rcx
0x1800257ff  mov     [r11-40h], ecx
0x180025803  mov     [r11-3Ch], ecx
0x180025807  mov     [rsp+0D8h+var_70], 3
0x18002580f  test    r9, r9
0x180025812  jnz     short loc_18002582D
0x180025814  mov     [rsp+0D8h+pExceptionObject], 80100004h
0x18002581c  lea     rdx, _TI1K; pThrowInfo
0x180025823  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180025828  call    _CxxThrowException_0
0x18002582d  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180025834  lea     rsi, [rbx+20h]
0x180025838  mov     [rsp+0D8h+var_B8], rsi
0x18002583d  mov     rcx, rsi; lpCriticalSection
0x180025840  call    cs:__imp_EnterCriticalSection
0x180025846  nop
0x180025847  mov     rdx, r15; unsigned __int64
0x18002584a  mov     rcx, rbx; this
0x18002584d  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180025852  xor     r15d, r15d
0x180025855  test    rax, rax
0x180025858  jnz     short loc_180025873
0x18002585a  mov     [rsp+0D8h+var_AC], 6
0x180025862  lea     rdx, _TI1K; pThrowInfo
0x180025869  lea     rcx, [rsp+0D8h+var_AC]; pExceptionObject
0x18002586e  call    _CxxThrowException_0
0x180025873  mov     rbx, [rax]
0x180025876  mov     rcx, rsi; lpCriticalSection
0x180025879  call    cs:__imp_LeaveCriticalSection
0x18002587f  cmp     [rbx+10h], r15d
0x180025883  jz      short loc_18002589E
0x180025885  mov     [rsp+0D8h+var_A8], 8010001Eh
0x18002588d  lea     rdx, _TI1K; pThrowInfo
0x180025894  lea     rcx, [rsp+0D8h+var_A8]; pExceptionObject
0x180025899  call    _CxxThrowException_0
0x18002589e  cmp     [rbx+80h], r15
0x1800258a5  jnz     short loc_180025925
0x1800258a7  xor     ecx, ecx; lpCriticalSection
0x1800258a9  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x1800258ae  test    al, al
0x1800258b0  jz      short loc_180025925
0x1800258b2  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800258b9  mov     [rsp+0D8h+var_98], rsi
0x1800258be  mov     [rsp+0D8h+var_90], r15
0x1800258c3  mov     [rsp+0D8h+var_88], r15d
0x1800258c8  mov     [rsp+0D8h+var_84], r15d
0x1800258cd  mov     rdx, r13
0x1800258d0  lea     rcx, [rsp+0D8h+var_78]
0x1800258d5  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x1800258da  lea     rcx, [rsp+0D8h+var_78]; this
0x1800258df  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800258e4  lea     r8, [rsp+0D8h+var_98]; struct CBuffer *
0x1800258e9  mov     rdx, rax; unsigned __int16 *
0x1800258ec  mov     rcx, rbx; this
0x1800258ef  call    ?GetReaderDeviceInstanceId@CSCardUserContext@@QEAAJPEBGAEAVCBuffer@@@Z; CSCardUserContext::GetReaderDeviceInstanceId(ushort const *,CBuffer &)
0x1800258f4  mov     r9, r14; unsigned int *
0x1800258f7  mov     r8, r12; char *
0x1800258fa  lea     rdx, [rsp+0D8h+var_98]; struct CBuffer *
0x1800258ff  mov     rcx, rbx; this
0x180025902  call    ?PlaceResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEADPEAK@Z; PlaceResult(CSCardUserContext *,CBuffer &,char *,ulong *)
0x180025907  nop
0x180025908  mov     [rsp+0D8h+var_98], rsi
0x18002590d  lea     rcx, [rsp+0D8h+var_98]; this
0x180025912  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180025917  nop
0x180025918  lea     rcx, [rsp+0D8h+var_78]; this
0x18002591d  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180025922  nop
0x180025923  jmp     short loc_180025960
0x180025925  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x18002592a  lea     rdx, _TI1K; pThrowInfo
0x180025931  test    al, al
0x180025933  jz      short loc_180025947
0x180025935  mov     [rsp+0D8h+var_A4], 8010001Dh
0x18002593d  lea     rcx, [rsp+0D8h+var_A4]; pExceptionObject
0x180025942  call    _CxxThrowException_0
0x180025947  mov     [rsp+0D8h+var_A0], 80100017h
0x18002594f  lea     rcx, [rsp+0D8h+var_A0]; pExceptionObject
0x180025954  call    _CxxThrowException_0
0x18002595a  jmp     short $+2
0x18002595c  mov     edi, dword ptr [rsp+0D8h+var_B8]
0x180025960  mov     eax, edi
0x180025962  add     rsp, 0A0h
0x180025969  pop     r15
0x18002596b  pop     r14
0x18002596d  pop     r13
0x18002596f  pop     r12
0x180025971  pop     rdi
0x180025972  pop     rsi
0x180025973  pop     rbx
0x180025974  retn
```
