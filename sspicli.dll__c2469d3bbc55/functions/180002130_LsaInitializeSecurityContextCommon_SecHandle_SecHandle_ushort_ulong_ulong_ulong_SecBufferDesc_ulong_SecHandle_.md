# LsaInitializeSecurityContextCommon(_SecHandle *,_SecHandle *,ushort *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)

- ea: `0x180002130`
- end: `0x180002735`
- name: `?LsaInitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAGKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z`
- size: `1541`
- prototype: `int(struct _SecHandle *, struct _SecHandle *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002050`
- `0x1800020c0`

## callees

- `0x180002130`
- `0x180002740`
- `0x180002780`
- `0x180003ee0`
- `0x180005370`
- `0x180005cc0`
- `0x18001c8e4`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800021fc`
- `ntdll!RtlLeaveCriticalSection` at `0x18000242d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000266f`
- `ntdll!RtlLeaveCriticalSection` at `0x180002723`
- `ntdll!RtlLeaveCriticalSection` at `0x1800021fc`
- `ntdll!RtlLeaveCriticalSection` at `0x18000242d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000266f`
- `ntdll!RtlLeaveCriticalSection` at `0x180002723`
- `ntdll!RtlEnterCriticalSection` at `0x1800021d7`
- `ntdll!RtlEnterCriticalSection` at `0x1800023fd`
- `ntdll!RtlEnterCriticalSection` at `0x18000263f`
- `ntdll!RtlEnterCriticalSection` at `0x1800021d7`
- `ntdll!RtlEnterCriticalSection` at `0x1800023fd`
- `ntdll!RtlEnterCriticalSection` at `0x18000263f`
- `ntdll!RtlInitUnicodeString` at `0x180002295`
- `ntdll!RtlInitUnicodeString` at `0x180002295`
- `ntdll!RtlNtStatusToDosError` at `0x18000250e`
- `ntdll!RtlNtStatusToDosError` at `0x18000250e`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18000259a`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18000259a`
- `ntdll!RtlFreeUnicodeString` at `0x1800024d2`
- `ntdll!RtlFreeUnicodeString` at `0x1800024d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002516`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026ed`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180002555`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180002555`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002301`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002301`

## pseudocode

```c
__int64 __fastcall LsaInitializeSecurityContextCommon(
        struct _SecHandle *a1,
        struct _SecHandle *a2,
        const char *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        struct _SecBufferDesc *a7,
        unsigned int a8,
        struct _SecHandle *a9,
        struct _SecBufferDesc *a10,
        unsigned int *a11,
        union _LARGE_INTEGER *a12,
        unsigned __int8 a13)
{
  unsigned int v16; // eax
  unsigned int v17; // r12d
  struct _SecBufferDesc *v18; // rcx
  __int64 *v19; // r14
  ULONG_PTR dwLower; // rax
  struct _SecBufferDesc *v21; // rax
  int v22; // eax
  int v23; // ebx
  bool v24; // zf
  int v25; // edi
  unsigned int i; // ecx
  __int64 v27; // rax
  unsigned int *v28; // r13
  _QWORD *Value; // rax
  __int64 v30; // rcx
  NTSTATUS v31; // ebx
  struct _SecHandle *v32; // r13
  ULONG_PTR dwUpper; // rax
  ULONG_PTR v34; // rcx
  struct _SecHandle *v35; // r15
  int v36; // eax
  __int64 v37; // r8
  struct _SecBufferDesc *v38; // rdi
  __int64 v39; // r13
  _BYTE *v40; // rax
  __int64 v41; // rcx
  __int64 v43; // rcx
  ULONG v44; // eax
  HLOCAL v45; // rax
  unsigned int v46; // ecx
  unsigned int k; // edi
  __int64 v48; // rcx
  void *v49; // rcx
  unsigned int j; // edi
  __int64 v51; // rdx
  __int64 v52; // rsi
  _BYTE *v53; // rax
  __int64 v54; // rcx
  bool v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+84h] [rbp-7Ch]
  int v57; // [rsp+88h] [rbp-78h] BYREF
  struct _SecBufferDesc *v58; // [rsp+90h] [rbp-70h] BYREF
  struct _SecHandle *v59; // [rsp+98h] [rbp-68h]
  unsigned int *v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-50h]
  _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v64[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v65; // [rsp+D8h] [rbp-28h]
  __int128 v66; // [rsp+E0h] [rbp-20h] BYREF
  struct _SecHandle v67; // [rsp+F0h] [rbp-10h] BYREF
  struct _SecHandle v68; // [rsp+100h] [rbp+0h] BYREF

  v59 = a9;
  v60 = a11;
  v65 = (__int64 *)a12;
  v61 = 0;
  v62 = 0;
  v55 = 0;
  v64[0] = 0;
  v64[1] = 0;
  v57 = 0;
  v56 = a4;
  DestinationString = 0;
  v67.dwUpper = -1;
  v66 = 0;
  v67.dwLower = -1;
  v68 = 0;
  RtlEnterCriticalSection(&SecVMListLock);
  if ( SecVMListAvailable < 0x13 )
  {
    if ( SecVMListSize > 0xFFFFFFF || (v45 = LocalReAlloc(SecVMList, 32LL * SecVMListSize, 2u)) == 0 )
    {
      RtlLeaveCriticalSection(&SecVMListLock);
      v43 = 0;
LABEL_86:
      v31 = -2146893056;
      goto LABEL_50;
    }
    v46 = SecVMListSize;
    SecVMList = v45;
    SecVMListSize *= 2;
    v16 = SecVMListAvailable - 19 + v46;
  }
  else
  {
    v16 = SecVMListAvailable - 19;
  }
  SecVMListAvailable = v16;
  RtlLeaveCriticalSection(&SecVMListLock);
  v17 = 19;
  if ( a2 )
  {
    v68 = *a2;
    v18 = (struct _SecBufferDesc *)qword_18003FFB0;
    v19 = qword_18003FFB0;
    if ( a7 )
      v18 = a7;
    v58 = v18;
    if ( a10 )
      v19 = (__int64 *)a10;
    if ( !a1 )
    {
      dwLower = a2->dwLower;
      goto LABEL_17;
    }
  }
  else
  {
    if ( !a1 )
    {
      v31 = -2146893055;
      v43 = 19;
LABEL_50:
      SecpReleaseVMSpots(v43);
LABEL_51:
      v44 = RtlNtStatusToDosError(v31);
      SetLastError(v44);
      return SspNtStatusToSecStatus((unsigned int)v31);
    }
    v21 = (struct _SecBufferDesc *)qword_18003FFB0;
    v19 = qword_18003FFB0;
    a2 = (struct _SecHandle *)v64;
    if ( a10 )
      v19 = (__int64 *)a10;
    if ( a7 )
      v21 = a7;
    v58 = v21;
  }
  *((_QWORD *)&v66 + 1) = a1->dwUpper;
  dwLower = a1->dwLower;
LABEL_17:
  *(_QWORD *)&v66 = dwLower;
  if ( !a13 )
  {
    if ( !a3 || RtlCreateUnicodeStringFromAsciiz(&DestinationString, a3) )
    {
      v22 = 16;
      goto LABEL_19;
    }
    v43 = 19;
    goto LABEL_86;
  }
  RtlInitUnicodeString(&DestinationString, (PCWSTR)a3);
  v22 = 0;
LABEL_19:
  v23 = v56;
  v24 = (v56 & 0x100) == 0;
  v25 = v56 & 0x100;
  v57 = v22;
  v56 = v25;
  if ( !v24 )
  {
    for ( i = 0; i < *((_DWORD *)v19 + 1); ++i )
    {
      v27 = v19[1];
      if ( *(_DWORD *)(v27 + 16LL * i + 4) == 2 )
      {
        *(_QWORD *)(v27 + 16LL * i + 8) = 0;
        *(_DWORD *)(v19[1] + 16LL * i) = 0;
      }
    }
  }
  v24 = (DllState & 0x20000000) == 0;
  v28 = v60;
  *v60 = 0;
  if ( !v24 )
  {
    Value = 0;
    goto LABEL_26;
  }
  Value = TlsGetValue(SecTlsIP);
  if ( !Value )
  {
LABEL_26:
    v30 = 0;
    goto LABEL_27;
  }
  v30 = Value[5];
LABEL_27:
  v31 = SspipProcessSecurityContext(
          &v66,
          &v68,
          (__int64)&DestinationString,
          v58,
          v23,
          a6,
          &v67,
          (__int64)v19,
          v28,
          v65,
          &v55,
          (__int64)&v61,
          &v57,
          (__int64)Value,
          v30);
  if ( !a13 )
    RtlFreeUnicodeString(&DestinationString);
  v32 = v59;
  dwUpper = v67.dwUpper;
  v34 = v67.dwLower;
  *v59 = v67;
  if ( v31 >= 0 && v55 )
  {
    v58 = 0;
    if ( a2 == (struct _SecHandle *)v64 || (v35 = a2, (v57 & 0x20) != 0) )
      v35 = v32;
    v35->dwUpper = dwUpper;
    v35->dwLower = v34;
    v36 = SecLocatePackageById(v34, &v58);
    v38 = v58;
    if ( v36 >= 0 )
    {
      if ( !v58[11].pBuffers )
      {
LABEL_73:
        v31 = -2146893055;
        goto LABEL_74;
      }
      v39 = v62;
      if ( v62 )
      {
        RtlEnterCriticalSection(&SecVMListLock);
        v40 = SecVMList;
        v41 = 2LL * SecVMListElements++;
        *((_QWORD *)SecVMList + v41) = v39;
        v40[8 * v41 + 8] = 1;
        RtlLeaveCriticalSection(&SecVMListLock);
        v17 = 18;
      }
      v36 = ((__int64 (__fastcall *)(ULONG_PTR, __int64 *))v38[11].pBuffers->pvBuffer)(v35->dwUpper, &v61);
      v32 = v59;
      if ( v36 >= 0 )
      {
        if ( v38[11].pBuffers )
        {
LABEL_39:
          v25 = v56;
          goto LABEL_40;
        }
        goto LABEL_73;
      }
    }
    v31 = v36;
LABEL_74:
    if ( a2 == (struct _SecHandle *)v64 || (v57 & 0x20) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_PPD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v37, v35->dwUpper, v35->dwLower, v31);
      LsaDeleteSecurityContext(v32);
      v32->dwUpper = -2;
    }
    else
    {
      v35->dwLower = (ULONG_PTR)v38;
    }
    goto LABEL_39;
  }
LABEL_40:
  if ( (v31 & 0xC0000000) != 0xC0000000 && (*v60 & 0x100) != 0 )
  {
    for ( j = 0; j < *((_DWORD *)v19 + 1); ++j )
    {
      v51 = v19[1] + 16LL * j;
      if ( (unsigned int)(*(_DWORD *)(v51 + 4) - 2) <= 1 )
      {
        if ( *(_DWORD *)v51 )
        {
          v52 = *(_QWORD *)(v51 + 8);
          if ( v52 )
          {
            if ( v17 )
            {
              RtlEnterCriticalSection(&SecVMListLock);
              v53 = SecVMList;
              v54 = 2LL * SecVMListElements++;
              *((_QWORD *)SecVMList + v54) = v52;
              v53[8 * v54 + 8] = 1;
              RtlLeaveCriticalSection(&SecVMListLock);
              --v17;
            }
          }
        }
      }
    }
  }
  else if ( v25 )
  {
    for ( k = 0; k < *((_DWORD *)v19 + 1); ++k )
    {
      v48 = v19[1];
      if ( (unsigned int)(*(_DWORD *)(v48 + 16LL * k + 4) - 2) <= 1 )
      {
        v49 = *(void **)(v48 + 16LL * k + 8);
        if ( v49 )
        {
          if ( SecpLsaInprocDispatch )
            (*(void (**)(void))SecpLsaInprocDispatch)();
          else
            LocalFree(v49);
          *(_DWORD *)(v19[1] + 16LL * k) = 0;
          *(_QWORD *)(v19[1] + 16LL * k + 8) = 0;
        }
      }
    }
  }
  SecpReleaseVMSpots(v17);
  if ( v31 < 0 )
    goto LABEL_51;
  return SspNtStatusToSecStatus((unsigned int)v31);
}

```

## disassembly

```asm
0x180002130  mov     [rsp-8+arg_0], rbx
0x180002135  push    rbp
0x180002136  push    rsi
0x180002137  push    rdi
0x180002138  push    r12
0x18000213a  push    r13
0x18000213c  push    r14
0x18000213e  push    r15
0x180002140  lea     rbp, [rsp-20h]
0x180002145  sub     rsp, 120h
0x18000214c  mov     rax, cs:__security_cookie
0x180002153  xor     rax, rsp
0x180002156  mov     [rbp+50h+var_40], rax
0x18000215a  mov     rax, [rbp+50h+arg_40]
0x180002161  xorps   xmm0, xmm0
0x180002164  mov     r15, [rbp+50h+arg_48]
0x18000216b  mov     rbx, rcx
0x18000216e  mov     rdi, [rbp+50h+arg_30]
0x180002175  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000217c  mov     [rbp+50h+var_B8], rax
0x180002180  xorps   xmm1, xmm1
0x180002183  mov     rax, [rbp+50h+arg_50]
0x18000218a  mov     r13, r8
0x18000218d  mov     [rbp+50h+var_B0], rax
0x180002191  mov     rsi, rdx
0x180002194  mov     rax, [rbp+50h+arg_58]
0x18000219b  mov     [rbp+50h+var_78], rax
0x18000219f  xor     eax, eax
0x1800021a1  mov     [rbp+50h+var_A8], rax
0x1800021a5  mov     [rbp+50h+var_A0], rax
0x1800021a9  mov     [rbp+50h+var_D0], al
0x1800021ac  mov     [rbp+50h+var_88], rax
0x1800021b0  mov     [rbp+50h+var_80], rax
0x1800021b4  mov     [rbp+50h+var_C8], eax
0x1800021b7  mov     [rbp+50h+var_CC], r9d
0x1800021bb  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x1800021bf  mov     [rbp+50h+var_58], 0FFFFFFFFFFFFFFFFh
0x1800021c7  movups  [rbp+50h+var_70], xmm0
0x1800021cb  mov     [rbp+50h+var_60], 0FFFFFFFFFFFFFFFFh
0x1800021d3  movups  [rbp+50h+var_50], xmm1
0x1800021d7  call    cs:__imp_RtlEnterCriticalSection
0x1800021dd  mov     eax, cs:?SecVMListAvailable@@3KA; ulong SecVMListAvailable
0x1800021e3  cmp     eax, 13h
0x1800021e6  jb      loc_180002530
0x1800021ec  add     eax, 0FFFFFFEDh
0x1800021ef  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800021f6  mov     cs:?SecVMListAvailable@@3KA, eax; ulong SecVMListAvailable
0x1800021fc  call    cs:__imp_RtlLeaveCriticalSection
0x180002202  mov     r12d, 13h
0x180002208  test    rsi, rsi
0x18000220b  jz      short loc_180002245
0x18000220d  mov     rax, [rsi+8]
0x180002211  test    rdi, rdi
0x180002214  mov     qword ptr [rbp+50h+var_50+8], rax
0x180002218  mov     rax, [rsi]
0x18000221b  mov     qword ptr [rbp+50h+var_50], rax
0x18000221f  lea     rax, qword_18003FFB0
0x180002226  mov     rcx, rax
0x180002229  mov     r14, rax
0x18000222c  cmovnz  rcx, rdi
0x180002230  test    r15, r15
0x180002233  mov     [rbp+50h+var_C0], rcx
0x180002237  cmovnz  r14, r15
0x18000223b  test    rbx, rbx
0x18000223e  jnz     short loc_18000226E
0x180002240  mov     rax, [rsi]
0x180002243  jmp     short loc_180002279
0x180002245  test    rbx, rbx
0x180002248  jz      loc_1800024FF
0x18000224e  lea     rax, qword_18003FFB0
0x180002255  test    r15, r15
0x180002258  mov     r14, rax
0x18000225b  lea     rsi, [rbp+50h+var_88]
0x18000225f  cmovnz  r14, r15
0x180002263  test    rdi, rdi
0x180002266  cmovnz  rax, rdi
0x18000226a  mov     [rbp+50h+var_C0], rax
0x18000226e  mov     rax, [rbx+8]
0x180002272  mov     qword ptr [rbp+50h+var_70+8], rax
0x180002276  mov     rax, [rbx]
0x180002279  movzx   r15d, [rbp+50h+arg_60]
0x180002281  mov     qword ptr [rbp+50h+var_70], rax
0x180002285  test    r15b, r15b
0x180002288  jz      loc_18000251E
0x18000228e  mov     rdx, r13; SourceString
0x180002291  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x180002295  call    cs:__imp_RtlInitUnicodeString
0x18000229b  xor     r9d, r9d
0x18000229e  mov     eax, r9d
0x1800022a1  mov     ebx, [rbp+50h+var_CC]
0x1800022a4  mov     edi, ebx
0x1800022a6  and     edi, 100h
0x1800022ac  mov     [rbp+50h+var_C8], eax
0x1800022af  mov     [rbp+50h+var_CC], edi
0x1800022b2  jz      short loc_1800022E3
0x1800022b4  cmp     dword ptr [r14+4], 0
0x1800022b9  mov     ecx, r9d
0x1800022bc  jbe     short loc_1800022E3
0x1800022be  mov     rax, [r14+8]
0x1800022c2  mov     edx, ecx
0x1800022c4  add     rdx, rdx
0x1800022c7  cmp     dword ptr [rax+rdx*8+4], 2
0x1800022cc  jnz     short loc_1800022DB
0x1800022ce  mov     [rax+rdx*8+8], r9
0x1800022d3  mov     rax, [r14+8]
0x1800022d7  mov     [rax+rdx*8], r9d
0x1800022db  inc     ecx
0x1800022dd  cmp     ecx, [r14+4]
0x1800022e1  jb      short loc_1800022BE
0x1800022e3  test    cs:DllState, 20000000h
0x1800022ed  mov     r13, [rbp+50h+var_B0]
0x1800022f1  mov     [r13+0], r9d
0x1800022f5  jnz     loc_18000258B
0x1800022fb  mov     ecx, cs:SecTlsIP; dwTlsIndex
0x180002301  call    cs:__imp_TlsGetValue
0x180002307  test    rax, rax
0x18000230a  jnz     loc_1800024DD
0x180002310  xor     r9d, r9d
0x180002313  mov     rcx, r9
0x180002316  mov     r9, [rbp+50h+var_C0]
0x18000231a  lea     r8, [rbp+50h+DestinationString]
0x18000231e  mov     [rsp+150h+var_E0], rcx
0x180002323  lea     rdx, [rbp+50h+var_50]
0x180002327  mov     [rsp+150h+var_E8], rax
0x18000232c  lea     rcx, [rbp+50h+var_70]
0x180002330  lea     rax, [rbp+50h+var_C8]
0x180002334  mov     [rsp+150h+var_F0], rax
0x180002339  lea     rax, [rbp+50h+var_A8]
0x18000233d  mov     [rsp+150h+var_F8], rax
0x180002342  lea     rax, [rbp+50h+var_D0]
0x180002346  mov     [rsp+150h+var_100], rax
0x18000234b  mov     rax, [rbp+50h+var_78]
0x18000234f  mov     [rsp+150h+var_108], rax
0x180002354  lea     rax, [rbp+50h+var_60]
0x180002358  mov     [rsp+150h+var_110], r13
0x18000235d  mov     [rsp+150h+var_118], r14
0x180002362  mov     [rsp+150h+var_120], rax
0x180002367  mov     eax, [rbp+50h+arg_28]
0x18000236d  mov     [rsp+150h+var_128], eax
0x180002371  mov     dword ptr [rsp+150h+var_130], ebx
0x180002375  call    SspipProcessSecurityContext
0x18000237a  mov     ebx, eax
0x18000237c  test    r15b, r15b
0x18000237f  jz      loc_1800024CE
0x180002385  mov     r13, [rbp+50h+var_B8]
0x180002389  mov     rax, [rbp+50h+var_58]
0x18000238d  mov     rcx, [rbp+50h+var_60]
0x180002391  mov     [r13+8], rax
0x180002395  mov     [r13+0], rcx
0x180002399  test    ebx, ebx
0x18000239b  js      loc_18000246E
0x1800023a1  cmp     [rbp+50h+var_D0], 0
0x1800023a5  jz      loc_18000246E
0x1800023ab  lea     rdx, [rbp+50h+var_88]
0x1800023af  mov     [rbp+50h+var_C0], 0
0x1800023b7  cmp     rsi, rdx
0x1800023ba  jnz     loc_1800024ED
0x1800023c0  mov     r15, r13
0x1800023c3  lea     rdx, [rbp+50h+var_C0]
0x1800023c7  mov     [r15+8], rax
0x1800023cb  mov     [r15], rcx
0x1800023ce  call    SecLocatePackageById
0x1800023d3  mov     rdi, [rbp+50h+var_C0]
0x1800023d7  test    eax, eax
0x1800023d9  js      loc_1800024E6
0x1800023df  cmp     qword ptr [rdi+0B8h], 0
0x1800023e7  jz      loc_180002685
0x1800023ed  mov     r13, [rbp+50h+var_A0]
0x1800023f1  test    r13, r13
0x1800023f4  jz      short loc_180002439
0x1800023f6  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800023fd  call    cs:__imp_RtlEnterCriticalSection
0x180002403  mov     edx, cs:?SecVMListElements@@3KA; ulong SecVMListElements
0x180002409  mov     rax, cs:?SecVMList@@3PEAU_VM_LIST_ENTRY@@EA; _VM_LIST_ENTRY * SecVMList
0x180002410  mov     ecx, edx
0x180002412  add     rcx, rcx
0x180002415  inc     edx
0x180002417  mov     cs:?SecVMListElements@@3KA, edx; ulong SecVMListElements
0x18000241d  mov     [rax+rcx*8], r13
0x180002421  mov     byte ptr [rax+rcx*8+8], 1
0x180002426  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000242d  call    cs:__imp_RtlLeaveCriticalSection
0x180002433  mov     r12d, 12h
0x180002439  mov     rax, [rdi+0B8h]
0x180002440  lea     rdx, [rbp+50h+var_A8]
0x180002444  mov     rcx, [r15+8]
0x180002448  mov     rax, [rax+8]
0x18000244c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002451  mov     r13, [rbp+50h+var_B8]
0x180002455  test    eax, eax
0x180002457  js      loc_1800024E6
0x18000245d  cmp     qword ptr [rdi+0B8h], 0
0x180002465  jz      loc_180002685
0x18000246b  mov     edi, [rbp+50h+var_CC]
0x18000246e  mov     eax, ebx
0x180002470  and     eax, 0C0000000h
0x180002475  cmp     eax, 0C0000000h
0x18000247a  jz      short loc_18000248C
0x18000247c  mov     rax, [rbp+50h+var_B0]
0x180002480  test    dword ptr [rax], 100h
0x180002486  jnz     loc_180002600
0x18000248c  test    edi, edi
0x18000248e  jnz     loc_1800025B0
0x180002494  mov     ecx, r12d
0x180002497  call    SecpReleaseVMSpots
0x18000249c  test    ebx, ebx
0x18000249e  js      short loc_18000250C
0x1800024a0  mov     ecx, ebx
0x1800024a2  call    SspNtStatusToSecStatus
0x1800024a7  mov     rcx, [rbp+50h+var_40]
0x1800024ab  xor     rcx, rsp; StackCookie
0x1800024ae  call    __security_check_cookie
0x1800024b3  mov     rbx, [rsp+150h+arg_0]
0x1800024bb  add     rsp, 120h
0x1800024c2  pop     r15
0x1800024c4  pop     r14
0x1800024c6  pop     r13
0x1800024c8  pop     r12
0x1800024ca  pop     rdi
0x1800024cb  pop     rsi
0x1800024cc  pop     rbp
0x1800024cd  retn
0x1800024ce  lea     rcx, [rbp+50h+DestinationString]; UnicodeString
0x1800024d2  call    cs:__imp_RtlFreeUnicodeString
0x1800024d8  jmp     loc_180002385
0x1800024dd  mov     rcx, [rax+28h]
0x1800024e1  jmp     loc_180002316
0x1800024e6  mov     ebx, eax
0x1800024e8  jmp     loc_18000268A
0x1800024ed  test    byte ptr [rbp+50h+var_C8], 20h
0x1800024f1  mov     r15, rsi
0x1800024f4  jz      loc_1800023C3
0x1800024fa  jmp     loc_1800023C0
0x1800024ff  mov     ebx, 80090301h
0x180002504  mov     ecx, r12d
0x180002507  call    SecpReleaseVMSpots
0x18000250c  mov     ecx, ebx; Status
0x18000250e  call    cs:__imp_RtlNtStatusToDosError
0x180002514  mov     ecx, eax; dwErrCode
0x180002516  call    cs:__imp_SetLastError
0x18000251c  jmp     short loc_1800024A0
0x18000251e  test    r13, r13
0x180002521  jnz     short loc_180002593
0x180002523  mov     eax, 10h
0x180002528  xor     r9d, r9d
0x18000252b  jmp     loc_1800022A1
0x180002530  mov     eax, cs:?SecVMListSize@@3KA; ulong SecVMListSize
0x180002536  cmp     eax, 0FFFFFFFh
0x18000253b  ja      loc_18000271C
0x180002541  mov     rcx, cs:?SecVMList@@3PEAU_VM_LIST_ENTRY@@EA; hMem
0x180002548  lea     edx, [rax+rax]
0x18000254b  shl     rdx, 4; uBytes
0x18000254f  mov     r8d, 2; uFlags
0x180002555  call    cs:__imp_LocalReAlloc
0x18000255b  test    rax, rax
0x18000255e  jz      loc_18000271C
0x180002564  mov     ecx, cs:?SecVMListSize@@3KA; ulong SecVMListSize
0x18000256a  mov     edx, cs:?SecVMListAvailable@@3KA; ulong SecVMListAvailable
0x180002570  mov     cs:?SecVMList@@3PEAU_VM_LIST_ENTRY@@EA, rax; _VM_LIST_ENTRY * SecVMList
0x180002577  add     edx, 0FFFFFFEDh
0x18000257a  lea     eax, [rcx+rcx]
0x18000257d  mov     cs:?SecVMListSize@@3KA, eax; ulong SecVMListSize
0x180002583  lea     eax, [rdx+rcx]
0x180002586  jmp     loc_1800021EF
0x18000258b  mov     rax, r9
0x18000258e  jmp     loc_180002313
0x180002593  mov     rdx, r13; Source
0x180002596  lea     rcx, [rbp+50h+DestinationString]; Destination
0x18000259a  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x1800025a0  test    al, al
0x1800025a2  jnz     loc_180002523
0x1800025a8  mov     ecx, r12d
0x1800025ab  jmp     loc_18000272B
0x1800025b0  xor     edi, edi
0x1800025b2  cmp     [r14+4], edi
0x1800025b6  jbe     loc_180002494
0x1800025bc  mov     rcx, [r14+8]
0x1800025c0  mov     esi, edi
0x1800025c2  add     rsi, rsi
0x1800025c5  mov     eax, [rcx+rsi*8+4]
0x1800025c9  sub     eax, 2
0x1800025cc  cmp     eax, 1
0x1800025cf  ja      loc_18000270B
0x1800025d5  mov     rcx, [rcx+rsi*8+8]; hMem
0x1800025da  test    rcx, rcx
0x1800025dd  jz      loc_18000270B
0x1800025e3  mov     rax, cs:SecpLsaInprocDispatch
0x1800025ea  test    rax, rax
0x1800025ed  jz      loc_1800026ED
0x1800025f3  mov     rax, [rax]
0x1800025f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025fb  jmp     loc_1800026F3
0x180002600  xor     edi, edi
0x180002602  cmp     [r14+4], edi
0x180002606  jbe     loc_180002494
0x18000260c  nop     dword ptr [rax+00h]
0x180002610  mov     edx, edi
0x180002612  shl     rdx, 4
0x180002616  add     rdx, [r14+8]
0x18000261a  mov     eax, [rdx+4]
  ... truncated ...
```
