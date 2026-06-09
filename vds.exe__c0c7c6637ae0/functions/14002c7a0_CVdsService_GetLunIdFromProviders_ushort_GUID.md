# CVdsService::GetLunIdFromProviders(ushort *,_GUID *)

- ea: `0x14002c7a0`
- end: `0x14002cad5`
- name: `?GetLunIdFromProviders@CVdsService@@CAJPEAGPEAU_GUID@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x140037320`

## callees

- `0x140013298`
- `0x140025e20`
- `0x14002c7a0`
- `0x14002cadc`
- `0x14002e123`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsTrace` at `0x14002c85a`
- `vdsutil!VdsTrace` at `0x14002c8f8`
- `vdsutil!VdsTrace` at `0x14002c968`
- `vdsutil!VdsTrace` at `0x14002c85a`
- `vdsutil!VdsTrace` at `0x14002c8f8`
- `vdsutil!VdsTrace` at `0x14002c968`
- `vdsutil!VdsTraceEx` at `0x14002ca91`
- `vdsutil!VdsTraceEx` at `0x14002ca91`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c870`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c870`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c890`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c890`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14002c8bd`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14002c8bd`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14002ca03`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14002ca03`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002c80b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002c80b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002caa5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002caa5`
- `vdsutil!VdsTraceW` at `0x14002c993`
- `vdsutil!VdsTraceW` at `0x14002c9b6`
- `vdsutil!VdsTraceW` at `0x14002c993`
- `vdsutil!VdsTraceW` at `0x14002c9b6`

## string_xrefs

- `0x14002c7fd`: `CVdsService::GetLunIdFromProviders()`
- `0x14002c851`: `CVdsService::GetLunIdFromProviders, 1, path=%ws, hr=%lX`
- `0x14002c8ef`: `CVdsService::GetLunIdFromProviders, 2, path=%ws`
- `0x14002c95c`: `CVdsService::GetLunIdFromProviders, 3 [%ws] to LUN-disk map, hr=%lX`
- `0x14002c987`: `CVdsService::GetLunIdFromProviders, 4, Type=%ld, CodeSet=%ld, size=%lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::GetLunIdFromProviders(LPCWSTR lpFileName, struct _GUID *a2)
{
  struct _GUID *v2; // rsi
  int LunInformationForDisk; // eax
  unsigned int v5; // r15d
  const wchar_t *v6; // r8
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  signed int v8; // ebx
  const wchar_t *v9; // r8
  unsigned int v10; // eax
  unsigned int v11; // r13d
  const wchar_t *v12; // r8
  VDS_STORAGE_IDENTIFIER *m_rgIdentifiers; // rbx
  ULONG v14; // edi
  unsigned __int8 *m_rgbIdentifier; // rsi
  ULONG i; // r15d
  int v17; // eax
  int v18; // ecx
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  int v22; // r10d
  int v23; // r11d
  int v24; // ebx
  int Data3; // edi
  int Data2; // esi
  unsigned int v28[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v31; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID *v32; // [rsp+90h] [rbp-70h]
  __int128 Buf1; // [rsp+98h] [rbp-68h] BYREF
  __int128 Buf2; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v35[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[16]; // [rsp+D0h] [rbp-30h] BYREF
  struct _VDS_LUN_INFORMATION v37; // [rsp+E0h] [rbp-20h] BYREF

  v2 = a2;
  v32 = a2;
  Buf1 = 0;
  memset_0(&v37, 0, sizeof(v37));
  v31 = 0;
  v30 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v35, 0x5Eu, "CVdsService::GetLunIdFromProviders()");
  memset_0(&v37, 0, sizeof(v37));
  *v2 = 0;
  LunInformationForDisk = CVdsService::GetLunInformationForDisk(lpFileName, &v37, &v31);
  v5 = LunInformationForDisk;
  if ( LunInformationForDisk >= 0 )
  {
    for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstHardwareProviders, &Buf2);
          ;
          CRtlListIter::Next((CRtlListIter *)&Buf1) )
    {
      Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstHardwareProviders, v36);
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        break;
      EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
      v8 = (**EntryPointer)(EntryPointer, &IID_IVdsHwProviderPrivate, &v30);
      if ( !v8 )
        goto LABEL_12;
      v9 = lpFileName;
      if ( !lpFileName )
        v9 = L"UNKNOWN";
      VdsTrace(0, "CVdsService::GetLunIdFromProviders, 2, path=%ws", v9);
      if ( v8 < 0 )
      {
        VdsLogError(0xC2000009, 0, 0, v8, 0x2000035u, 0);
      }
      else
      {
LABEL_12:
        v10 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, struct _VDS_LUN_INFORMATION *, struct _GUID *))(*(_QWORD *)v30 + 24LL))(
                v30,
                lpFileName,
                &v37,
                v2);
        v11 = v10;
        if ( v10 )
        {
          v12 = lpFileName;
          if ( !lpFileName )
            v12 = L"UNKNOWN";
          VdsTrace(2, "CVdsService::GetLunIdFromProviders, 3 [%ws] to LUN-disk map, hr=%lX", v12, v10);
          m_rgIdentifiers = v37.m_deviceIdDescriptor.m_rgIdentifiers;
          v14 = 0;
          if ( v37.m_deviceIdDescriptor.m_cIdentifiers )
          {
            do
            {
              v28[0] = m_rgIdentifiers->m_cbIdentifier;
              VdsTraceW(
                2,
                L"CVdsService::GetLunIdFromProviders, 4, Type=%ld, CodeSet=%ld, size=%lu",
                (unsigned int)m_rgIdentifiers->m_Type,
                (unsigned int)m_rgIdentifiers->m_CodeSet,
                *(_QWORD *)v28);
              m_rgbIdentifier = m_rgIdentifiers->m_rgbIdentifier;
              for ( i = 0; i < m_rgIdentifiers->m_cbIdentifier; ++i )
                VdsTraceW(2, L"ID identifier={%.2x}", *m_rgbIdentifier++);
              ++m_rgIdentifiers;
              ++v14;
            }
            while ( v14 < v37.m_deviceIdDescriptor.m_cIdentifiers );
            v2 = v32;
          }
        }
        if ( v30 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v30 = 0;
        }
        if ( !v11 )
        {
          v5 = 0;
          break;
        }
      }
      v5 = 1;
    }
  }
  else
  {
    v6 = lpFileName;
    if ( !lpFileName )
      v6 = L"UNKNOWN";
    VdsTrace(0, "CVdsService::GetLunIdFromProviders, 1, path=%ws, hr=%lX", v6, (unsigned int)LunInformationForDisk);
  }
  v17 = v2->Data4[7];
  v18 = v2->Data4[6];
  v19 = v2->Data4[5];
  v20 = v2->Data4[4];
  v21 = v2->Data4[3];
  v22 = v2->Data4[2];
  v23 = v2->Data4[1];
  v24 = v2->Data4[0];
  Data3 = v2->Data3;
  Data2 = v2->Data2;
  if ( !lpFileName )
    lpFileName = L"UNKNOWN";
  LODWORD(v29) = v32->Data1;
  VdsTraceEx(
    94,
    3,
    "LUN-Disk lookup from providers hResult:0x%08x IN [%ws] OUT LunId:{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
    v5,
    lpFileName,
    v29,
    Data2,
    Data3,
    v24,
    v23,
    v22,
    v21,
    v20,
    v19,
    v18,
    v17);
  CVdsService::EmptyLunInformation(&v37);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v35);
  return v5;
}

```

## disassembly

```asm
0x14002c7a0  mov     [rsp-8+arg_10], rbx
0x14002c7a5  push    rbp
0x14002c7a6  push    rsi
0x14002c7a7  push    rdi
0x14002c7a8  push    r12
0x14002c7aa  push    r13
0x14002c7ac  push    r14
0x14002c7ae  push    r15
0x14002c7b0  lea     rbp, [rsp-50h]
0x14002c7b5  sub     rsp, 150h
0x14002c7bc  mov     rax, cs:__security_cookie
0x14002c7c3  xor     rax, rsp
0x14002c7c6  mov     [rbp+80h+var_40], rax
0x14002c7ca  mov     rsi, rdx
0x14002c7cd  mov     [rbp+80h+var_F0], rdx
0x14002c7d1  mov     r14, rcx
0x14002c7d4  xorps   xmm0, xmm0
0x14002c7d7  movups  [rbp+80h+Buf1], xmm0
0x14002c7db  mov     ebx, 60h ; '`'
0x14002c7e0  mov     r8d, ebx; Size
0x14002c7e3  xor     edx, edx; Val
0x14002c7e5  lea     rcx, [rbp+80h+var_A0]; void *
0x14002c7e9  call    memset_0
0x14002c7ee  mov     [rbp+80h+var_F8], 0
0x14002c7f5  mov     [rbp+80h+var_100], 0
0x14002c7fd  lea     r8, aCvdsserviceGet_88; "CVdsService::GetLunIdFromProviders()"
0x14002c804  lea     edx, [rbx-2]
0x14002c807  lea     rcx, [rbp+80h+var_C0]
0x14002c80b  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002c811  nop
0x14002c812  mov     r8d, ebx; Size
0x14002c815  xor     edx, edx; Val
0x14002c817  lea     rcx, [rbp+80h+var_A0]; void *
0x14002c81b  call    memset_0
0x14002c820  xorps   xmm0, xmm0
0x14002c823  movups  xmmword ptr [rsi], xmm0
0x14002c826  lea     r8, [rbp+80h+var_F8]; unsigned int *
0x14002c82a  lea     rdx, [rbp+80h+var_A0]; struct _VDS_LUN_INFORMATION *
0x14002c82e  mov     rcx, r14; lpFileName
0x14002c831  call    ?GetLunInformationForDisk@CVdsService@@SAJPEBGPEAU_VDS_LUN_INFORMATION@@PEAK@Z; CVdsService::GetLunInformationForDisk(ushort const *,_VDS_LUN_INFORMATION *,ulong *)
0x14002c836  mov     r15d, eax
0x14002c839  test    eax, eax
0x14002c83b  jns     short loc_14002C865
0x14002c83d  lea     r12, aUnknown_0; "UNKNOWN"
0x14002c844  mov     r8, r14
0x14002c847  test    r14, r14
0x14002c84a  cmovz   r8, r12
0x14002c84e  mov     r9d, eax
0x14002c851  lea     rdx, aCvdsserviceGet_133; "CVdsService::GetLunIdFromProviders, 1, "...
0x14002c858  xor     ecx, ecx
0x14002c85a  call    cs:__imp_VdsTrace
0x14002c860  jmp     loc_14002CA11
0x14002c865  lea     rdx, [rbp+80h+Buf2]
0x14002c869  lea     rcx, ?m_lstHardwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstHardwareProviders
0x14002c870  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14002c876  movups  xmm0, xmmword ptr [rax]
0x14002c879  movdqu  [rbp+80h+Buf1], xmm0
0x14002c87e  lea     r12, aUnknown_0; "UNKNOWN"
0x14002c885  lea     rdx, [rbp+80h+var_B0]
0x14002c889  lea     rcx, ?m_lstHardwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstHardwareProviders
0x14002c890  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14002c896  movups  xmm0, xmmword ptr [rax]
0x14002c899  movdqu  [rbp+80h+Buf2], xmm0
0x14002c89e  mov     r8d, 10h; Size
0x14002c8a4  lea     rdx, [rbp+80h+Buf2]; Buf2
0x14002c8a8  lea     rcx, [rbp+80h+Buf1]; Buf1
0x14002c8ac  call    memcmp_0
0x14002c8b1  test    eax, eax
0x14002c8b3  jz      loc_14002CA11
0x14002c8b9  lea     rcx, [rbp+80h+Buf1]
0x14002c8bd  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14002c8c3  mov     r9, rax
0x14002c8c6  mov     rcx, [rax]
0x14002c8c9  mov     rax, [rcx]
0x14002c8cc  lea     r8, [rbp+80h+var_100]
0x14002c8d0  lea     rdx, IID_IVdsHwProviderPrivate
0x14002c8d7  mov     rcx, r9
0x14002c8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8df  mov     ebx, eax
0x14002c8e1  test    eax, eax
0x14002c8e3  jz      short loc_14002C92A
0x14002c8e5  mov     r8, r14
0x14002c8e8  test    r14, r14
0x14002c8eb  cmovz   r8, r12
0x14002c8ef  lea     rdx, aCvdsserviceGet_22; "CVdsService::GetLunIdFromProviders, 2, "...
0x14002c8f6  xor     ecx, ecx
0x14002c8f8  call    cs:__imp_VdsTrace
0x14002c8fe  test    ebx, ebx
0x14002c900  jns     short loc_14002C92A
0x14002c902  mov     [rsp+180h+var_158], 0; unsigned __int16 *
0x14002c90b  mov     [rsp+180h+var_160], 2000035h; unsigned int
0x14002c913  mov     r9d, ebx; unsigned int
0x14002c916  xor     r8d, r8d; void *
0x14002c919  xor     edx, edx; unsigned int
0x14002c91b  mov     ecx, 0C2000009h; unsigned int
0x14002c920  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14002c925  jmp     loc_14002C9F9
0x14002c92a  mov     rcx, [rbp+80h+var_100]
0x14002c92e  mov     rax, [rcx]
0x14002c931  mov     r9, rsi
0x14002c934  lea     r8, [rbp+80h+var_A0]
0x14002c938  mov     rdx, r14
0x14002c93b  mov     rax, [rax+18h]
0x14002c93f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c944  mov     r13d, eax
0x14002c947  test    eax, eax
0x14002c949  jz      loc_14002C9D7
0x14002c94f  mov     r8, r14
0x14002c952  test    r14, r14
0x14002c955  cmovz   r8, r12
0x14002c959  mov     r9d, eax
0x14002c95c  lea     rdx, aCvdsserviceGet_3; "CVdsService::GetLunIdFromProviders, 3 ["...
0x14002c963  mov     ecx, 2
0x14002c968  call    cs:__imp_VdsTrace
0x14002c96e  mov     rbx, [rbp+80h+var_A0.m_deviceIdDescriptor.m_rgIdentifiers]
0x14002c972  xor     edi, edi
0x14002c974  cmp     [rbp+80h+var_A0.m_deviceIdDescriptor.m_cIdentifiers], edi
0x14002c977  jbe     short loc_14002C9D7
0x14002c979  mov     eax, [rbx+8]
0x14002c97c  mov     [rsp+180h+var_160], eax
0x14002c980  mov     r9d, [rbx]
0x14002c983  mov     r8d, [rbx+4]
0x14002c987  lea     rdx, aCvdsserviceGet_113; "CVdsService::GetLunIdFromProviders, 4, "...
0x14002c98e  mov     ecx, 2
0x14002c993  call    cs:__imp_VdsTraceW
0x14002c999  mov     rsi, [rbx+10h]
0x14002c99d  xor     r15d, r15d
0x14002c9a0  cmp     [rbx+8], r15d
0x14002c9a4  jbe     short loc_14002C9C8
0x14002c9a6  movzx   r8d, byte ptr [rsi]
0x14002c9aa  lea     rdx, aIdIdentifier2x; "ID identifier={%.2x}"
0x14002c9b1  mov     ecx, 2
0x14002c9b6  call    cs:__imp_VdsTraceW
0x14002c9bc  inc     rsi
0x14002c9bf  inc     r15d
0x14002c9c2  cmp     r15d, [rbx+8]
0x14002c9c6  jb      short loc_14002C9A6
0x14002c9c8  add     rbx, 18h
0x14002c9cc  inc     edi
0x14002c9ce  cmp     edi, [rbp+80h+var_A0.m_deviceIdDescriptor.m_cIdentifiers]
0x14002c9d1  jb      short loc_14002C979
0x14002c9d3  mov     rsi, [rbp+80h+var_F0]
0x14002c9d7  mov     rcx, [rbp+80h+var_100]
0x14002c9db  test    rcx, rcx
0x14002c9de  jz      short loc_14002C9F4
0x14002c9e0  mov     rax, [rcx]
0x14002c9e3  mov     rax, [rax+10h]
0x14002c9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c9ec  mov     [rbp+80h+var_100], 0
0x14002c9f4  test    r13d, r13d
0x14002c9f7  jz      short loc_14002CA0E
0x14002c9f9  mov     r15d, 1
0x14002c9ff  lea     rcx, [rbp+80h+Buf1]
0x14002ca03  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14002ca09  jmp     loc_14002C885
0x14002ca0e  xor     r15d, r15d
0x14002ca11  movzx   eax, byte ptr [rsi+0Fh]
0x14002ca15  movzx   ecx, byte ptr [rsi+0Eh]
0x14002ca19  movzx   edx, byte ptr [rsi+0Dh]
0x14002ca1d  movzx   r8d, byte ptr [rsi+0Ch]
0x14002ca22  movzx   r9d, byte ptr [rsi+0Bh]
0x14002ca27  movzx   r10d, byte ptr [rsi+0Ah]
0x14002ca2c  movzx   r11d, byte ptr [rsi+9]
0x14002ca31  movzx   ebx, byte ptr [rsi+8]
0x14002ca35  movzx   edi, word ptr [rsi+6]
0x14002ca39  movzx   esi, word ptr [rsi+4]
0x14002ca3d  test    r14, r14
0x14002ca40  cmovz   r14, r12
0x14002ca44  mov     [rsp+180h+var_108], eax
0x14002ca48  mov     [rsp+180h+var_110], ecx
0x14002ca4c  mov     [rsp+180h+var_118], edx
0x14002ca50  mov     [rsp+180h+var_120], r8d
0x14002ca55  mov     [rsp+180h+var_128], r9d
0x14002ca5a  mov     [rsp+180h+var_130], r10d
0x14002ca5f  mov     [rsp+180h+var_138], r11d
0x14002ca64  mov     [rsp+180h+var_140], ebx
0x14002ca68  mov     [rsp+180h+var_148], edi
0x14002ca6c  mov     [rsp+180h+var_150], esi
0x14002ca70  mov     rax, [rbp+80h+var_F0]
0x14002ca74  mov     eax, [rax]
0x14002ca76  mov     dword ptr [rsp+180h+var_158], eax
0x14002ca7a  mov     qword ptr [rsp+180h+var_160], r14
0x14002ca7f  mov     r9d, r15d
0x14002ca82  lea     r8, aLunDiskLookupF; "LUN-Disk lookup from providers hResult:"...
0x14002ca89  mov     edx, 3
0x14002ca8e  lea     ecx, [rdx+5Bh]
0x14002ca91  call    cs:__imp_VdsTraceEx
0x14002ca97  lea     rcx, [rbp+80h+var_A0]; struct _VDS_LUN_INFORMATION *
0x14002ca9b  call    ?EmptyLunInformation@CVdsService@@CAJPEAU_VDS_LUN_INFORMATION@@@Z; CVdsService::EmptyLunInformation(_VDS_LUN_INFORMATION *)
0x14002caa0  nop
0x14002caa1  lea     rcx, [rbp+80h+var_C0]
0x14002caa5  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002caab  mov     eax, r15d
0x14002caae  mov     rcx, [rbp+80h+var_40]
0x14002cab2  xor     rcx, rsp; StackCookie
0x14002cab5  call    __security_check_cookie
0x14002caba  mov     rbx, [rsp+180h+arg_10]
0x14002cac2  add     rsp, 150h
0x14002cac9  pop     r15
0x14002cacb  pop     r14
0x14002cacd  pop     r13
0x14002cacf  pop     r12
0x14002cad1  pop     rdi
0x14002cad2  pop     rsi
0x14002cad3  pop     rbp
0x14002cad4  retn
```
