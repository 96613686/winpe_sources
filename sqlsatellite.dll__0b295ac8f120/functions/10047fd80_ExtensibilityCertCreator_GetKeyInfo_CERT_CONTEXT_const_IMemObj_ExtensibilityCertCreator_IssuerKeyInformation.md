# ExtensibilityCertCreator::GetKeyInfo(_CERT_CONTEXT const *,IMemObj *,ExtensibilityCertCreator::IssuerKeyInformation *)

- ea: `0x10047fd80`
- end: `0x10048027f`
- name: `?GetKeyInfo@ExtensibilityCertCreator@@YAJPEBU_CERT_CONTEXT@@PEAVIMemObj@@PEAUIssuerKeyInformation@1@@Z`
- size: `1279`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, const struct _CERT_CONTEXT *, struct IMemObj *, struct ExtensibilityCertCreator::IssuerKeyInformation *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x100480290`

## callees

- `0x100455f90`
- `0x100478330`
- `0x10047fb40`
- `0x10047fd80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10047fe32`
- `KERNEL32!GetCurrentThreadId` at `0x10047ff41`
- `KERNEL32!GetCurrentThreadId` at `0x10048000e`
- `KERNEL32!GetCurrentThreadId` at `0x100480100`
- `KERNEL32!GetCurrentThreadId` at `0x1004801a3`
- `KERNEL32!GetCurrentThreadId` at `0x10047fe32`
- `KERNEL32!GetCurrentThreadId` at `0x10047ff41`
- `KERNEL32!GetCurrentThreadId` at `0x10048000e`
- `KERNEL32!GetCurrentThreadId` at `0x100480100`
- `KERNEL32!GetCurrentThreadId` at `0x1004801a3`
- `KERNEL32!GetLastError` at `0x10047fe0f`
- `KERNEL32!GetLastError` at `0x10047ff22`
- `KERNEL32!GetLastError` at `0x10047ffeb`
- `KERNEL32!GetLastError` at `0x1004800dd`
- `KERNEL32!GetLastError` at `0x10047fe0f`
- `KERNEL32!GetLastError` at `0x10047ff22`
- `KERNEL32!GetLastError` at `0x10047ffeb`
- `KERNEL32!GetLastError` at `0x1004800dd`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047fea6`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047ffba`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10048008a`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10048017c`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100480218`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047fea6`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047ffba`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10048008a`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10048017c`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100480218`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047fde3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047fef7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100480243`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100480256`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047fde3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047fef7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100480243`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100480256`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047fede`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047fede`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10047fdfa`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10047ff14`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10047fdfa`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10047ff14`
- `CRYPT32!CertFindExtension` at `0x1004800b6`
- `CRYPT32!CertFindExtension` at `0x1004800b6`
- `ADVAPI32!CryptAcquireContextW` at `0x10047ffdd`
- `ADVAPI32!CryptAcquireContextW` at `0x10047ffdd`
- `ADVAPI32!CryptReleaseContext` at `0x10047fdd4`
- `ADVAPI32!CryptReleaseContext` at `0x100480234`
- `ADVAPI32!CryptReleaseContext` at `0x10047fdd4`
- `ADVAPI32!CryptReleaseContext` at `0x100480234`

## string_xrefs

- `0x10047fece`: `Sql\Ntdbms\extensibility\common\src\ExtensibilityCertCreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ExtensibilityCertCreator::GetKeyInfo(
        PCCERT_CONTEXT pCertContext,
        struct _CERT_CONTEXT *a2,
        struct IMemObj *a3,
        struct ExtensibilityCertCreator::IssuerKeyInformation *a4)
{
  LPCWSTR *v7; // rbx
  signed int KeyIdentifierBlobWithExtension; // edi
  signed int LastError; // eax
  __int64 v10; // r14
  signed int v11; // eax
  DWORD v12; // eax
  __int64 v13; // r14
  signed int v14; // eax
  DWORD v15; // eax
  __int64 v16; // r14
  PCERT_EXTENSION Extension; // rax
  signed int v18; // eax
  DWORD v19; // eax
  __int64 v20; // r14
  DWORD v21; // eax
  __int64 v22; // r14
  __m256i v24; // [rsp+38h] [rbp-D0h] BYREF
  signed int v25; // [rsp+58h] [rbp-B0h]
  DWORD CurrentThreadId; // [rsp+5Ch] [rbp-ACh]
  const char *v27; // [rsp+60h] [rbp-A8h]
  __m256i v28; // [rsp+68h] [rbp-A0h] BYREF
  signed int v29; // [rsp+88h] [rbp-80h]
  DWORD v30; // [rsp+8Ch] [rbp-7Ch]
  const char *v31; // [rsp+90h] [rbp-78h]
  int v32; // [rsp+98h] [rbp-70h]
  __int128 v33; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-58h]
  signed int v35; // [rsp+B8h] [rbp-50h]
  DWORD v36; // [rsp+BCh] [rbp-4Ch]
  const char *v37; // [rsp+C0h] [rbp-48h]
  int v38; // [rsp+C8h] [rbp-40h]
  __int128 v39; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-28h]
  signed int v41; // [rsp+E8h] [rbp-20h]
  DWORD v42; // [rsp+ECh] [rbp-1Ch]
  const char *v43; // [rsp+F0h] [rbp-18h]
  int v44; // [rsp+F8h] [rbp-10h]
  __int128 v45; // [rsp+100h] [rbp-8h] BYREF
  __int64 v46; // [rsp+110h] [rbp+8h]
  int v47; // [rsp+118h] [rbp+10h]
  DWORD v48; // [rsp+11Ch] [rbp+14h]
  const char *v49; // [rsp+120h] [rbp+18h]
  int v50; // [rsp+128h] [rbp+20h]
  __int64 v51; // [rsp+130h] [rbp+28h]
  _BYTE v52[216]; // [rsp+138h] [rbp+30h] BYREF
  int v53; // [rsp+210h] [rbp+108h]
  __int64 v54; // [rsp+218h] [rbp+110h]
  _BYTE v55[216]; // [rsp+228h] [rbp+120h] BYREF
  int v56; // [rsp+300h] [rbp+1F8h]
  __int64 v57; // [rsp+308h] [rbp+200h]
  _BYTE v58[216]; // [rsp+318h] [rbp+210h] BYREF
  int v59; // [rsp+3F0h] [rbp+2E8h]
  __int64 v60; // [rsp+3F8h] [rbp+2F0h]
  _BYTE v61[216]; // [rsp+408h] [rbp+300h] BYREF
  int v62; // [rsp+4E0h] [rbp+3D8h]
  __int64 v63; // [rsp+4E8h] [rbp+3E0h]
  _BYTE v64[216]; // [rsp+4F8h] [rbp+3F0h] BYREF
  int v65; // [rsp+5D0h] [rbp+4C8h]
  __int64 v66; // [rsp+5D8h] [rbp+4D0h]
  DWORD pcbData; // [rsp+630h] [rbp+528h] BYREF

  v51 = -2;
  v7 = 0;
  v24.m256i_i64[0] = 0;
  KeyIdentifierBlobWithExtension = 0;
  if ( a3 )
  {
    if ( *(_QWORD *)a3 )
      CryptReleaseContext(*(_QWORD *)a3, 0);
    operator delete(*((void **)a3 + 2), 0x10u);
  }
  if ( !CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData) )
  {
    LastError = GetLastError();
    KeyIdentifierBlobWithExtension = LastError;
    if ( LastError > 0 )
      KeyIdentifierBlobWithExtension = (unsigned __int16)LastError | 0x80070000;
    if ( g_extensibilityErrorRingBuffer )
    {
      memset(&v24.m256i_u64[1], 0, 24);
      v25 = KeyIdentifierBlobWithExtension;
      CurrentThreadId = GetCurrentThreadId();
      v27 = "ExtensibilityCertCreator::GetKeyInfo";
      v28.m256i_i32[0] = 392;
      v10 = g_extensibilityErrorRingBuffer;
      v53 = 0;
      v54 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v52, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v24.m256i_u64[1], v52);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v10, &v24.m256i_u64[1], v52);
    }
    if ( KeyIdentifierBlobWithExtension < 0 )
      goto LABEL_54;
  }
  v7 = (LPCWSTR *)operator new[](
                    pcbData,
                    (struct IMemObj *)a2,
                    1,
                    "Sql\\Ntdbms\\extensibility\\common\\src\\ExtensibilityCertCreator.cpp",
                    400,
                    6u);
  if ( !v7 )
  {
    v24.m256i_i64[0] = 0;
    KeyIdentifierBlobWithExtension = -2147024882;
    if ( g_extensibilityErrorRingBuffer )
    {
      v21 = GetCurrentThreadId();
      v45 = 0;
      v46 = 0;
      v47 = -2147024882;
      v48 = v21;
      v49 = "ExtensibilityCertCreator::GetKeyInfo";
      v50 = 405;
      v22 = g_extensibilityErrorRingBuffer;
      v65 = 0;
      v66 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v64, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v45, v64);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v22, &v45, v64);
    }
    goto LABEL_54;
  }
  operator delete(0, 0x30u);
  v24.m256i_i64[0] = (__int64)v7;
  if ( !CertGetCertificateContextProperty(pCertContext, 2u, v7, &pcbData) )
  {
    v11 = GetLastError();
    KeyIdentifierBlobWithExtension = v11;
    if ( v11 > 0 )
      KeyIdentifierBlobWithExtension = (unsigned __int16)v11 | 0x80070000;
    if ( g_extensibilityErrorRingBuffer )
    {
      v12 = GetCurrentThreadId();
      memset(&v28.m256i_u64[1], 0, 24);
      v29 = KeyIdentifierBlobWithExtension;
      v30 = v12;
      v31 = "ExtensibilityCertCreator::GetKeyInfo";
      v32 = 420;
      v13 = g_extensibilityErrorRingBuffer;
      v56 = 0;
      v57 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v55, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v28.m256i_u64[1], v55);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v13, &v28.m256i_u64[1], v55);
    }
  }
  if ( KeyIdentifierBlobWithExtension < 0 )
    goto LABEL_54;
  if ( !CryptAcquireContextW((HCRYPTPROV *)a3, *v7, v7[1], *((_DWORD *)v7 + 4), *((_DWORD *)v7 + 5)) )
  {
    v14 = GetLastError();
    KeyIdentifierBlobWithExtension = v14;
    if ( v14 > 0 )
      KeyIdentifierBlobWithExtension = (unsigned __int16)v14 | 0x80070000;
    if ( g_extensibilityErrorRingBuffer )
    {
      v15 = GetCurrentThreadId();
      v33 = 0;
      v34 = 0;
      v35 = KeyIdentifierBlobWithExtension;
      v36 = v15;
      v37 = "ExtensibilityCertCreator::GetKeyInfo";
      v38 = 436;
      v16 = g_extensibilityErrorRingBuffer;
      v59 = 0;
      v60 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v58, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v33, v58);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v16, &v33, v58);
    }
    if ( KeyIdentifierBlobWithExtension < 0 )
      goto LABEL_54;
  }
  *((_DWORD *)a3 + 2) = *((_DWORD *)v7 + 10);
  Extension = CertFindExtension("2.5.29.14", pCertContext->pCertInfo->cExtension, pCertContext->pCertInfo->rgExtension);
  if ( Extension )
  {
    KeyIdentifierBlobWithExtension = GetKeyIdentifierBlobWithExtension(Extension, a2, a3, &pcbData);
  }
  else
  {
    v18 = GetLastError();
    KeyIdentifierBlobWithExtension = v18;
    if ( v18 > 0 )
      KeyIdentifierBlobWithExtension = (unsigned __int16)v18 | 0x80070000;
    if ( g_extensibilityErrorRingBuffer )
    {
      v19 = GetCurrentThreadId();
      v39 = 0;
      v40 = 0;
      v41 = KeyIdentifierBlobWithExtension;
      v42 = v19;
      v43 = "ExtensibilityCertCreator::GetKeyInfo";
      v44 = 466;
      v20 = g_extensibilityErrorRingBuffer;
      v62 = 0;
      v63 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v61, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v39, v61);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v20, &v39, v61);
    }
  }
  if ( KeyIdentifierBlobWithExtension < 0 )
  {
LABEL_54:
    if ( a3 )
    {
      _mm_lfence();
      if ( *(_QWORD *)a3 )
      {
        _mm_lfence();
        CryptReleaseContext(*(_QWORD *)a3, 0);
      }
      operator delete(*((void **)a3 + 2), 0x10u);
      v7 = (LPCWSTR *)v24.m256i_i64[0];
    }
  }
  operator delete(v7, 0x30u);
  return (unsigned int)KeyIdentifierBlobWithExtension;
}

```

## disassembly

```asm
0x10047fd80  mov     rax, rsp
0x10047fd83  push    rbp
0x10047fd84  push    r12
0x10047fd86  push    r13
0x10047fd88  push    r14
0x10047fd8a  push    r15
0x10047fd8c  lea     rbp, [rax-508h]
0x10047fd93  sub     rsp, 5E0h
0x10047fd9a  mov     [rbp+500h+var_4D8], 0FFFFFFFFFFFFFFFEh
0x10047fda2  mov     [rax+8], rbx
0x10047fda6  mov     [rax+10h], rsi
0x10047fdaa  mov     [rax+18h], rdi
0x10047fdae  mov     rsi, r8
0x10047fdb1  mov     r12, rdx
0x10047fdb4  mov     r15, rcx
0x10047fdb7  xor     r13d, r13d
0x10047fdba  mov     ebx, r13d
0x10047fdbd  mov     qword ptr [rsp+600h+var_5D0], rbx
0x10047fdc2  mov     edi, r13d
0x10047fdc5  test    r8, r8
0x10047fdc8  jz      short loc_10047FDE9
0x10047fdca  mov     rcx, [r8]; hProv
0x10047fdcd  test    rcx, rcx
0x10047fdd0  jz      short loc_10047FDDA
0x10047fdd2  xor     edx, edx; dwFlags
0x10047fdd4  call    cs:__imp_CryptReleaseContext
0x10047fdda  mov     edx, 10h
0x10047fddf  mov     rcx, [rsi+10h]
0x10047fde3  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10047fde9  lea     r9, [rbp+500h+pcbData]; pcbData
0x10047fdf0  xor     r8d, r8d; pvData
0x10047fdf3  lea     edx, [r8+2]; dwPropId
0x10047fdf7  mov     rcx, r15; pCertContext
0x10047fdfa  call    cs:__imp_CertGetCertificateContextProperty
0x10047fe00  lea     r14, aExtensibilityc_1; "ExtensibilityCertCreator::GetKeyInfo"
0x10047fe07  test    eax, eax
0x10047fe09  jnz     loc_10047FEBB
0x10047fe0f  call    cs:__imp_GetLastError
0x10047fe15  mov     edi, eax
0x10047fe17  test    eax, eax
0x10047fe19  jle     short loc_10047FE24
0x10047fe1b  movzx   edi, ax
0x10047fe1e  or      edi, 80070000h
0x10047fe24  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047fe2c  jz      loc_10047FEB3
0x10047fe32  call    cs:__imp_GetCurrentThreadId
0x10047fe38  xorps   xmm0, xmm0
0x10047fe3b  xor     ecx, ecx
0x10047fe3d  movups  xmmword ptr [rsp+600h+var_5D0+8], xmm0
0x10047fe42  mov     [rsp+600h+var_5B8], rcx
0x10047fe47  mov     dword ptr [rsp+600h+var_5B0], edi
0x10047fe4b  mov     dword ptr [rsp+600h+var_5B0+4], eax
0x10047fe4f  mov     [rsp+600h+var_5A8], r14
0x10047fe54  mov     dword ptr [rsp+600h+var_5A0], 188h
0x10047fe5c  mov     r14, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047fe63  mov     [rbp+500h+var_3F8], r13d
0x10047fe6a  mov     [rbp+500h+var_3F0], r13
0x10047fe71  cmp     [r14+40h], rcx
0x10047fe75  jz      short loc_10047FE83
0x10047fe77  lea     edx, [rcx+1]
0x10047fe7a  lea     rcx, [rbp+500h+var_4D0]
0x10047fe7e  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10047fe83  test    byte ptr cs:dword_1005113AC, 10h
0x10047fe8a  jz      short loc_10047FE9A
0x10047fe8c  lea     rdx, [rbp+500h+var_4D0]
0x10047fe90  lea     rcx, [rsp+600h+var_5D0+8]
0x10047fe95  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10047fe9a  lea     r8, [rbp+500h+var_4D0]
0x10047fe9e  lea     rdx, [rsp+600h+var_5D0+8]
0x10047fea3  mov     rcx, r14
0x10047fea6  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10047feac  lea     r14, aExtensibilityc_1; "ExtensibilityCertCreator::GetKeyInfo"
0x10047feb3  test    edi, edi
0x10047feb5  js      loc_10048021E
0x10047febb  mov     ecx, [rbp+500h+pcbData]
0x10047fec1  mov     byte ptr [rsp+600h+var_5D8], 6
0x10047fec6  mov     [rsp+600h+dwFlags], 190h
0x10047fece  lea     r9, aSqlNtdbmsExten_6; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047fed5  mov     r8d, 1
0x10047fedb  mov     rdx, r12
0x10047fede  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047fee4  mov     rbx, rax
0x10047fee7  test    rax, rax
0x10047feea  jz      loc_10048018F
0x10047fef0  mov     edx, 30h ; '0'
0x10047fef5  xor     ecx, ecx
0x10047fef7  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10047fefd  mov     qword ptr [rsp+600h+var_5D0], rbx
0x10047ff02  lea     r9, [rbp+500h+pcbData]; pcbData
0x10047ff09  mov     r8, rbx; pvData
0x10047ff0c  mov     edx, 2; dwPropId
0x10047ff11  mov     rcx, r15; pCertContext
0x10047ff14  call    cs:__imp_CertGetCertificateContextProperty
0x10047ff1a  test    eax, eax
0x10047ff1c  jnz     loc_10047FFC0
0x10047ff22  call    cs:__imp_GetLastError
0x10047ff28  mov     edi, eax
0x10047ff2a  test    eax, eax
0x10047ff2c  jle     short loc_10047FF37
0x10047ff2e  movzx   edi, ax
0x10047ff31  or      edi, 80070000h
0x10047ff37  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047ff3f  jz      short loc_10047FFC0
0x10047ff41  call    cs:__imp_GetCurrentThreadId
0x10047ff47  xorps   xmm0, xmm0
0x10047ff4a  xor     ecx, ecx
0x10047ff4c  movups  xmmword ptr [rsp+600h+var_5A0+8], xmm0
0x10047ff51  mov     [rsp+600h+var_588], rcx
0x10047ff56  mov     [rbp+500h+var_580], edi
0x10047ff59  mov     [rbp+500h+var_57C], eax
0x10047ff5c  mov     [rbp+500h+var_578], r14
0x10047ff60  mov     [rbp+500h+var_570], 1A4h
0x10047ff67  mov     r14, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047ff6e  mov     [rbp+500h+var_308], r13d
0x10047ff75  mov     [rbp+500h+var_300], r13
0x10047ff7c  cmp     [r14+40h], rcx
0x10047ff80  jz      short loc_10047FF91
0x10047ff82  lea     edx, [rcx+1]
0x10047ff85  lea     rcx, [rbp+500h+var_3E0]
0x10047ff8c  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10047ff91  test    byte ptr cs:dword_1005113AC, 10h
0x10047ff98  jz      short loc_10047FFAB
0x10047ff9a  lea     rdx, [rbp+500h+var_3E0]
0x10047ffa1  lea     rcx, [rsp+600h+var_5A0+8]
0x10047ffa6  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10047ffab  lea     r8, [rbp+500h+var_3E0]
0x10047ffb2  lea     rdx, [rsp+600h+var_5A0+8]
0x10047ffb7  mov     rcx, r14
0x10047ffba  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10047ffc0  test    edi, edi
0x10047ffc2  js      loc_10048021E
0x10047ffc8  mov     eax, [rbx+14h]
0x10047ffcb  mov     [rsp+600h+dwFlags], eax; dwFlags
0x10047ffcf  mov     r9d, [rbx+10h]; dwProvType
0x10047ffd3  mov     r8, [rbx+8]; szProvider
0x10047ffd7  mov     rdx, [rbx]; szContainer
0x10047ffda  mov     rcx, rsi; phProv
0x10047ffdd  call    cs:__imp_CryptAcquireContextW
0x10047ffe3  test    eax, eax
0x10047ffe5  jnz     loc_100480098
0x10047ffeb  call    cs:__imp_GetLastError
0x10047fff1  mov     edi, eax
0x10047fff3  test    eax, eax
0x10047fff5  jle     short loc_100480000
0x10047fff7  movzx   edi, ax
0x10047fffa  or      edi, 80070000h
0x100480000  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480008  jz      loc_100480090
0x10048000e  call    cs:__imp_GetCurrentThreadId
0x100480014  xorps   xmm0, xmm0
0x100480017  xor     ecx, ecx
0x100480019  movups  [rbp+500h+var_568], xmm0
0x10048001d  mov     [rbp+500h+var_558], rcx
0x100480021  mov     [rbp+500h+var_550], edi
0x100480024  mov     [rbp+500h+var_54C], eax
0x100480027  lea     rax, aExtensibilityc_1; "ExtensibilityCertCreator::GetKeyInfo"
0x10048002e  mov     [rbp+500h+var_548], rax
0x100480032  mov     [rbp+500h+var_540], 1B4h
0x100480039  mov     r14, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480040  mov     [rbp+500h+var_218], r13d
0x100480047  mov     [rbp+500h+var_210], r13
0x10048004e  cmp     [r14+40h], rcx
0x100480052  jz      short loc_100480063
0x100480054  lea     edx, [rcx+1]
0x100480057  lea     rcx, [rbp+500h+var_2F0]
0x10048005e  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x100480063  test    byte ptr cs:dword_1005113AC, 10h
0x10048006a  jz      short loc_10048007C
0x10048006c  lea     rdx, [rbp+500h+var_2F0]
0x100480073  lea     rcx, [rbp+500h+var_568]
0x100480077  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10048007c  lea     r8, [rbp+500h+var_2F0]
0x100480083  lea     rdx, [rbp+500h+var_568]
0x100480087  mov     rcx, r14
0x10048008a  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x100480090  test    edi, edi
0x100480092  js      loc_10048021E
0x100480098  mov     eax, [rbx+28h]
0x10048009b  mov     [rsi+8], eax
0x10048009e  mov     rax, [r15+18h]
0x1004800a2  mov     r8, [rax+0C8h]; rgExtensions
0x1004800a9  mov     edx, [rax+0C0h]; cExtensions
0x1004800af  lea     rcx, pszObjId; "2.5.29.14"
0x1004800b6  call    cs:__imp_CertFindExtension
0x1004800bc  test    rax, rax
0x1004800bf  jz      short loc_1004800DD
0x1004800c1  lea     r9, [rbp+500h+pcbData]
0x1004800c8  mov     r8, rsi
0x1004800cb  mov     rdx, r12
0x1004800ce  mov     rcx, rax
0x1004800d1  call    GetKeyIdentifierBlobWithExtension
0x1004800d6  mov     edi, eax
0x1004800d8  jmp     loc_100480182
0x1004800dd  call    cs:__imp_GetLastError
0x1004800e3  mov     edi, eax
0x1004800e5  test    eax, eax
0x1004800e7  jle     short loc_1004800F2
0x1004800e9  movzx   edi, ax
0x1004800ec  or      edi, 80070000h
0x1004800f2  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x1004800fa  jz      loc_100480182
0x100480100  call    cs:__imp_GetCurrentThreadId
0x100480106  xorps   xmm0, xmm0
0x100480109  xor     ecx, ecx
0x10048010b  movups  [rbp+500h+var_538], xmm0
0x10048010f  mov     [rbp+500h+var_528], rcx
0x100480113  mov     [rbp+500h+var_520], edi
0x100480116  mov     [rbp+500h+var_51C], eax
0x100480119  lea     rax, aExtensibilityc_1; "ExtensibilityCertCreator::GetKeyInfo"
0x100480120  mov     [rbp+500h+var_518], rax
0x100480124  mov     [rbp+500h+var_510], 1D2h
0x10048012b  mov     r14, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480132  mov     [rbp+500h+var_128], r13d
0x100480139  mov     [rbp+500h+var_120], r13
0x100480140  cmp     [r14+40h], rcx
0x100480144  jz      short loc_100480155
0x100480146  lea     edx, [rcx+1]
0x100480149  lea     rcx, [rbp+500h+var_200]
0x100480150  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x100480155  test    byte ptr cs:dword_1005113AC, 10h
0x10048015c  jz      short loc_10048016E
0x10048015e  lea     rdx, [rbp+500h+var_200]
0x100480165  lea     rcx, [rbp+500h+var_538]
0x100480169  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10048016e  lea     r8, [rbp+500h+var_200]
0x100480175  lea     rdx, [rbp+500h+var_538]
0x100480179  mov     rcx, r14
0x10048017c  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x100480182  test    edi, edi
0x100480184  jns     loc_10048024E
0x10048018a  jmp     loc_10048021E
0x10048018f  mov     qword ptr [rsp+600h+var_5D0], rbx
0x100480194  mov     edi, 8007000Eh
0x100480199  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x1004801a1  jz      short loc_10048021E
0x1004801a3  call    cs:__imp_GetCurrentThreadId
0x1004801a9  xorps   xmm0, xmm0
0x1004801ac  xor     ecx, ecx
0x1004801ae  movups  [rbp+500h+var_508], xmm0
0x1004801b2  mov     [rbp+500h+var_4F8], rcx
0x1004801b6  mov     [rbp+500h+var_4F0], edi
0x1004801b9  mov     [rbp+500h+var_4EC], eax
0x1004801bc  mov     [rbp+500h+var_4E8], r14
0x1004801c0  mov     [rbp+500h+var_4E0], 195h
0x1004801c7  mov     r14, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x1004801ce  mov     [rbp+500h+var_38], r13d
0x1004801d5  mov     [rbp+500h+var_30], r13
0x1004801dc  cmp     [r14+40h], rcx
0x1004801e0  jz      short loc_1004801F1
0x1004801e2  lea     edx, [rcx+1]
0x1004801e5  lea     rcx, [rbp+500h+var_110]
0x1004801ec  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004801f1  test    byte ptr cs:dword_1005113AC, 10h
0x1004801f8  jz      short loc_10048020A
0x1004801fa  lea     rdx, [rbp+500h+var_110]
0x100480201  lea     rcx, [rbp+500h+var_508]
0x100480205  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10048020a  lea     r8, [rbp+500h+var_110]
0x100480211  lea     rdx, [rbp+500h+var_508]
0x100480215  mov     rcx, r14
0x100480218  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10048021e  test    rsi, rsi
0x100480221  jz      short loc_10048024E
0x100480223  lfence
0x100480226  cmp     qword ptr [rsi], 0
0x10048022a  jz      short loc_10048023A
0x10048022c  lfence
0x10048022f  xor     edx, edx; dwFlags
0x100480231  mov     rcx, [rsi]; hProv
0x100480234  call    cs:__imp_CryptReleaseContext
0x10048023a  mov     edx, 10h
0x10048023f  mov     rcx, [rsi+10h]
0x100480243  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100480249  mov     rbx, qword ptr [rsp+600h+var_5D0]
0x10048024e  mov     edx, 30h ; '0'
0x100480253  mov     rcx, rbx
0x100480256  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10048025c  mov     eax, edi
0x10048025e  lea     r11, [rsp+600h+var_20]
0x100480266  mov     rbx, [r11+30h]
0x10048026a  mov     rsi, [r11+38h]
0x10048026e  mov     rdi, [r11+40h]
0x100480272  mov     rsp, r11
0x100480275  pop     r15
0x100480277  pop     r14
0x100480279  pop     r13
0x10048027b  pop     r12
0x10048027d  pop     rbp
0x10048027e  retn
```
