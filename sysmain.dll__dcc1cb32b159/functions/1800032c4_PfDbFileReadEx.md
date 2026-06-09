# PfDbFileReadEx

- ea: `0x1800032c4`
- end: `0x180003914`
- name: `PfDbFileReadEx`
- size: `1616`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008bf04`
- `0x1800ad4c8`
- `0x1800b1234`

## callees

- `0x180002d84`
- `0x1800032c4`
- `0x18000391c`
- `0x180003b00`
- `0x1800059d0`
- `0x180006170`
- `0x18002341c`
- `0x180031e50`
- `0x180078746`
- `0x1800b7010`

## import_xrefs

- `msvcrt!_wcsupr_s` at `0x18000352f`
- `msvcrt!_wcsupr_s` at `0x18000352f`
- `ntdll!NtQueryInformationThread` at `0x18000332d`
- `ntdll!NtQueryInformationThread` at `0x18000332d`
- `ntdll!RtlNtStatusToDosError` at `0x180003875`
- `ntdll!RtlNtStatusToDosError` at `0x180003875`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000330c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000333e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003846`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000330c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000333e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003846`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000374f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000374f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034fc`

## pseudocode

```c
__int64 __fastcall PfDbFileReadEx(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  _QWORD *v5; // r12
  HANDLE CurrentThread; // rax
  int v9; // eax
  int v10; // esi
  HANDLE v11; // rax
  int v12; // r8d
  void *v13; // r15
  HANDLE v14; // rax
  int v15; // eax
  __int128 v16; // xmm1
  __int64 v17; // rax
  __int128 v18; // xmm0
  unsigned __int64 v19; // r14
  unsigned int v20; // eax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rcx
  __int128 v23; // xmm0
  __int64 v24; // rax
  unsigned int v25; // eax
  __int16 v26; // r14
  __int64 v27; // rbx
  void *v28; // rax
  const void *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int8 *v32; // r8
  __int64 v33; // r9
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // r9
  __int64 v37; // r9
  __int64 v38; // r9
  __int64 v39; // r9
  __int64 v40; // r9
  __int64 v41; // r9
  __int64 v42; // rax
  __int64 v43; // rbx
  __int64 (__fastcall *v44)(__int64, __int64, unsigned __int64, _QWORD); // rax
  __int64 v45; // r14
  int v46; // r12d
  unsigned int Ranges; // ebx
  unsigned int i; // r12d
  __int64 v49; // rax
  unsigned __int64 v50; // rbx
  __int128 v51; // xmm0
  __int64 v52; // xmm1_8
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // r14
  __int64 v56; // r10
  int v57; // eax
  __int64 v58; // r14
  HANDLE v59; // rax
  size_t v61; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v62; // [rsp+38h] [rbp-81h]
  size_t Size; // [rsp+40h] [rbp-79h]
  unsigned __int64 v64; // [rsp+48h] [rbp-71h]
  _OWORD v65[2]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v66[44]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-19h]
  unsigned __int64 v68; // [rsp+A8h] [rbp-11h]
  __int128 v69; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v70; // [rsp+C0h] [rbp+7h]
  __int64 v71; // [rsp+D0h] [rbp+17h]
  __int64 v72; // [rsp+D8h] [rbp+1Fh]
  unsigned __int64 ThreadInformation; // [rsp+120h] [rbp+67h] BYREF
  __int64 v74; // [rsp+130h] [rbp+77h]

  v74 = a3;
  memset(v65, 0, sizeof(v65));
  v71 = 0;
  v5 = (_QWORD *)a3;
  v69 = 0;
  v70 = 0;
  CurrentThread = GetCurrentThread();
  LODWORD(ThreadInformation) = 0;
  v9 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v9 < 0 )
  {
    RtlNtStatusToDosError(v9);
    v10 = 8;
  }
  else
  {
    v10 = ThreadInformation;
  }
  v11 = GetCurrentThread();
  PfSetPagePriorityThread(v11);
  if ( *(_DWORD *)a1 != 15 || 10000 * (unsigned int)PfDbFileVerifyCommon(a1, a2, v12, 0, (__int64)PfDbRangeListVerify) )
  {
    Ranges = 11;
  }
  else
  {
    v13 = 0;
    if ( v10 != 8 )
    {
      v14 = GetCurrentThread();
      PfSetPagePriorityThread(v14);
      v10 = 8;
    }
    v15 = *(_DWORD *)(a1 + 48);
    v16 = *(_OWORD *)(a1 + 32);
    *(_OWORD *)&v66[28] = 0;
    *(_DWORD *)&v66[32] = v15;
    v17 = *(_QWORD *)(a4 + 604);
    *(__m128i *)&v66[12] = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)&v66[36] = v17;
    v18 = *(_OWORD *)(a1 + 16);
    *(_OWORD *)&v66[16] = v16;
    *(_OWORD *)v66 = v18;
    PfDbDatabaseInitialize(a4, v66);
    v19 = a1 + *(unsigned int *)(a1 + 8);
    v20 = 0;
LABEL_8:
    v62 = v20;
    if ( v20 >= *(_DWORD *)(a1 + 52) )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 64); ++i )
      {
        v49 = *(unsigned int *)(a4 + 576);
        v50 = (v19 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        memset(v65, 0, 24);
        v51 = *(_OWORD *)(v50 + 16);
        v61 = v50 + v49;
        v52 = *(_QWORD *)(v50 + 32);
        v53 = *(_QWORD *)(v50 + 8);
        v65[0] = v51;
        *((_QWORD *)&v65[1] + 1) = v53;
        *(_QWORD *)&v65[1] = v52;
        v54 = PfDbSourceCreate(a4, v65);
        v55 = v54;
        if ( !v54 )
          goto LABEL_45;
        *(_OWORD *)(v54 + 40) = *(_OWORD *)(v50 + 40);
        memcpy_0((void *)(v54 + 88), (const void *)(v50 + 88), (unsigned int)(*(_DWORD *)(a4 + 576) - 88));
        v56 = v74;
        v57 = v50 + 56;
        v58 = v55 + 56;
        ThreadInformation = v50 + 56;
        if ( *(_QWORD *)(v74 + 8) )
        {
          Ranges = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, _QWORD))(v74 + 8))(
                     a1,
                     v58,
                     v50 + 56,
                     *(_QWORD *)(v74 + 24));
          if ( Ranges )
            goto LABEL_46;
          v57 = ThreadInformation;
          v56 = v74;
        }
        Ranges = PfDbFileReadRanges(a4, a1, (unsigned int)&v61, v57, v58, v56);
        if ( Ranges )
          goto LABEL_46;
        v19 = v61;
      }
      Ranges = 0;
    }
    else
    {
      v21 = (v19 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      v22 = v21 + *(unsigned int *)(a4 + 568);
      v68 = v21;
      v23 = *(_OWORD *)(v21 + 32);
      *(_QWORD *)&v66[24] = *(_QWORD *)(v21 + 56);
      *(_QWORD *)&v66[16] = v22;
      *(_WORD *)&v66[26] &= ~1u;
      *(_OWORD *)v66 = v23;
      v19 = v22 + 2LL * ((unsigned int)*(unsigned __int16 *)&v66[24] + 1);
      v24 = PfDbVolumeCreate(a4, v66);
      v67 = v24;
      if ( v24 )
      {
        memcpy_0((void *)(v24 + 72), (const void *)(v21 + 72), (unsigned int)(*(_DWORD *)(a4 + 568) - 72));
        if ( !*v5 )
        {
LABEL_11:
          v25 = 0;
          while ( 1 )
          {
            LODWORD(ThreadInformation) = v25;
            if ( v25 >= *(_DWORD *)(v21 + 16) )
            {
              v20 = v62 + 1;
              goto LABEL_8;
            }
            LODWORD(v61) = *(_DWORD *)(a4 + 572);
            v64 = (v19 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            memset(v65, 0, sizeof(v65));
            v26 = (((*(_QWORD *)(v64 + 16) >> 1) & 1) << 7) | 0x10;
            v27 = *(_QWORD *)(v64 + 16) >> 2;
            v72 = 8 * (*(_WORD *)(v64 + 16) & 1LL);
            if ( v13 )
              HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v13);
            Size = (unsigned int)(2 * v27 + 2);
            v28 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, Size);
            v13 = v28;
            if ( !v28 )
            {
              Ranges = 8;
              goto LABEL_47;
            }
            v29 = (const void *)(v64 + (unsigned int)v61);
            memcpy_0(v28, v29, Size);
            _wcsupr_s((wchar_t *)v13, Size >> 1);
            WORD4(v69) = v26;
            v61 = (size_t)v29 + Size;
            *(_QWORD *)&v69 = v72;
            *(_DWORD *)((char *)&v69 + 10) = *(_DWORD *)((char *)v65 + 10);
            HIWORD(v69) = HIWORD(v65[0]);
            HIDWORD(v70) = HIDWORD(v65[1]);
            v30 = -1;
            *(_QWORD *)&v70 = v13;
            do
              ++v30;
            while ( *((_WORD *)v13 + v30) );
            v31 = 314159;
            DWORD2(v70) = v30;
            v32 = (unsigned __int8 *)v13;
            v33 = 2LL * (unsigned int)v30;
            if ( (unsigned __int64)v33 >= 8 )
            {
              do
              {
                v33 -= 8;
                v34 = v32[7];
                v35 = 37
                    * (v32[6]
                     + 37
                     * (v32[5] + 37 * (v32[4] + 37 * (v32[3] + 37 * (v32[2] + 37 * (v32[1] + 37 * (*v32 + 37 * v31)))))));
                v32 += 8;
                v31 = v34 + v35;
              }
              while ( v33 >= 8 );
            }
            v36 = v33 - 1;
            if ( !v36 )
              goto LABEL_31;
            v37 = v36 - 1;
            if ( !v37 )
              goto LABEL_30;
            v38 = v37 - 1;
            if ( !v38 )
              goto LABEL_29;
            v39 = v38 - 1;
            if ( !v39 )
              goto LABEL_28;
            v40 = v39 - 1;
            if ( !v40 )
              goto LABEL_27;
            v41 = v40 - 1;
            if ( !v41 )
              goto LABEL_26;
            if ( v41 == 1 )
              break;
LABEL_32:
            v71 = v31;
            v42 = PfDbSectionCreate(a4, v67, &v69);
            v43 = v42;
            if ( !v42 )
            {
              Ranges = 8;
              goto LABEL_37;
            }
            memcpy_0((void *)(v42 + 64), (const void *)(v64 + 64), (unsigned int)(*(_DWORD *)(a4 + 572) - 64));
            v44 = (__int64 (__fastcall *)(__int64, __int64, unsigned __int64, _QWORD))v5[1];
            v45 = v43 + 32;
            v46 = v64;
            if ( v44 )
            {
              Ranges = v44(a1, v43 + 32, v64 + 32, *(_QWORD *)(v74 + 24));
              if ( Ranges )
                goto LABEL_37;
            }
            Ranges = PfDbFileReadRanges(a4, a1, (unsigned int)&v61, v46 + 32, v45, v74);
            if ( Ranges )
              goto LABEL_37;
            v19 = v61;
            v25 = ThreadInformation + 1;
            v5 = (_QWORD *)v74;
            v21 = v68;
          }
          v31 = *v32++ + 37 * v31;
LABEL_26:
          v31 = *v32++ + 37 * v31;
LABEL_27:
          v31 = *v32++ + 37 * v31;
LABEL_28:
          v31 = *v32++ + 37 * v31;
LABEL_29:
          v31 = *v32++ + 37 * v31;
LABEL_30:
          v31 = *v32++ + 37 * v31;
LABEL_31:
          v31 = *v32 + 37 * v31;
          goto LABEL_32;
        }
        Ranges = ((__int64 (__fastcall *)(__int64, __int64, unsigned __int64, _QWORD))*v5)(a1, v67, v21, v5[3]);
        if ( !Ranges )
        {
          v21 = v68;
          goto LABEL_11;
        }
      }
      else
      {
LABEL_45:
        Ranges = 8;
      }
    }
LABEL_46:
    if ( v13 )
LABEL_37:
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v13);
  }
LABEL_47:
  if ( v10 != 8 )
  {
    v59 = GetCurrentThread();
    PfSetPagePriorityThread(v59);
  }
  return Ranges;
}

```

## disassembly

```asm
0x1800032c4  mov     [rsp-8+arg_8], rbx
0x1800032c9  mov     [rsp-8+arg_10], r8
0x1800032ce  push    rbp
0x1800032cf  push    rsi
0x1800032d0  push    rdi
0x1800032d1  push    r12
0x1800032d3  push    r13
0x1800032d5  push    r14
0x1800032d7  push    r15
0x1800032d9  lea     rbp, [rsp-27h]
0x1800032de  sub     rsp, 0E0h
0x1800032e5  xorps   xmm0, xmm0
0x1800032e8  xorps   xmm1, xmm1
0x1800032eb  xor     eax, eax
0x1800032ed  mov     r13, r9
0x1800032f0  movups  [rbp+57h+var_C0], xmm0
0x1800032f4  mov     [rbp+57h+var_40], rax
0x1800032f8  mov     r12, r8
0x1800032fb  movups  [rbp+57h+var_B0], xmm0
0x1800032ff  mov     ebx, edx
0x180003301  mov     rdi, rcx
0x180003304  movups  [rbp+57h+var_60], xmm1
0x180003308  movups  [rbp+57h+var_50], xmm1
0x18000330c  call    cs:__imp_GetCurrentThread
0x180003312  xor     r14d, r14d
0x180003315  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x180003319  mov     rcx, rax; ThreadHandle
0x18000331c  mov     dword ptr [rbp+57h+ThreadInformation], r14d
0x180003320  mov     [rsp+110h+ReturnLength], r14; ReturnLength
0x180003325  lea     r9d, [r14+4]; ThreadInformationLength
0x180003329  lea     edx, [r14+18h]; ThreadInformationClass
0x18000332d  call    cs:__imp_NtQueryInformationThread
0x180003333  test    eax, eax
0x180003335  js      loc_180003873
0x18000333b  mov     esi, dword ptr [rbp+57h+ThreadInformation]
0x18000333e  call    cs:__imp_GetCurrentThread
0x180003344  mov     rcx, rax; ThreadHandle
0x180003347  mov     edx, 1
0x18000334c  call    PfSetPagePriorityThread
0x180003351  cmp     dword ptr [rdi], 0Fh
0x180003354  jnz     loc_18000390A
0x18000335a  lea     rax, PfDbRangeListVerify
0x180003361  xor     r9d, r9d
0x180003364  mov     edx, ebx
0x180003366  mov     [rsp+110h+ReturnLength], rax
0x18000336b  mov     rcx, rdi
0x18000336e  call    PfDbFileVerifyCommon
0x180003373  imul    ecx, eax, 2710h
0x180003379  test    ecx, ecx
0x18000337b  jnz     loc_18000390A
0x180003381  mov     r15, r14
0x180003384  cmp     esi, 8
0x180003387  jz      short loc_18000339E
0x180003389  call    cs:__imp_GetCurrentThread
0x18000338f  mov     rcx, rax; ThreadHandle
0x180003392  mov     edx, esi
0x180003394  call    PfSetPagePriorityThread
0x180003399  mov     esi, 8
0x18000339e  mov     eax, [rdi+30h]
0x1800033a1  lea     rdx, [rbp+57h+var_A0]
0x1800033a5  movups  xmm1, xmmword ptr [rdi+20h]
0x1800033a9  mov     rcx, r13
0x1800033ac  xorps   xmm0, xmm0
0x1800033af  movups  [rbp+57h+var_84], xmm0
0x1800033b3  mov     dword ptr [rbp+57h+var_84+4], eax
0x1800033b6  movdqa  xmm0, cs:__xmm@00000010000000100000001000000010
0x1800033be  mov     rax, [r13+25Ch]
0x1800033c5  movups  [rbp+57h+var_A0+0Ch], xmm0
0x1800033c9  mov     qword ptr [rbp+57h+var_84+8], rax
0x1800033cd  movups  xmm0, xmmword ptr [rdi+10h]
0x1800033d1  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x1800033d5  movups  [rbp+57h+var_A0], xmm0
0x1800033d9  call    PfDbDatabaseInitialize
0x1800033de  mov     r14d, [rdi+8]
0x1800033e2  add     r14, rdi
0x1800033e5  xor     eax, eax
0x1800033e7  mov     [rsp+110h+var_D8], eax
0x1800033eb  cmp     eax, [rdi+34h]
0x1800033ee  jnb     loc_180003765
0x1800033f4  mov     ecx, [r13+238h]
0x1800033fb  lea     rbx, [r14+7]
0x1800033ff  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180003403  mov     edx, 0FFFEh
0x180003408  add     rcx, rbx
0x18000340b  mov     [rbp+57h+var_68], rbx
0x18000340f  movups  xmm1, xmmword ptr [rbx+30h]
0x180003413  movups  xmm0, xmmword ptr [rbx+20h]
0x180003417  movups  xmmword ptr [rbp-39h], xmm1
0x18000341b  mov     rax, [rbp-31h]
0x18000341f  shr     rax, 10h
0x180003423  and     ax, dx
0x180003426  mov     [rbp+57h+var_90], rcx
0x18000342a  mov     [rbp+57h+var_86], ax
0x18000342e  lea     rdx, [rbp+57h+var_A0]
0x180003432  movzx   eax, [rbp+57h+var_88]
0x180003436  inc     eax
0x180003438  movups  [rbp+57h+var_A0], xmm0
0x18000343c  lea     r14, [rcx+rax*2]
0x180003440  mov     rcx, r13
0x180003443  call    PfDbVolumeCreate
0x180003448  mov     [rbp+57h+var_70], rax
0x18000344c  test    rax, rax
0x18000344f  jz      loc_180003833
0x180003455  mov     r8d, [r13+238h]
0x18000345c  lea     rdx, [rbx+48h]; Src
0x180003460  sub     r8d, 48h ; 'H'; Size
0x180003464  lea     rcx, [rax+48h]; void *
0x180003468  call    memcpy_0
0x18000346d  mov     rax, [r12]
0x180003471  test    rax, rax
0x180003474  jnz     loc_180003889
0x18000347a  xor     eax, eax
0x18000347c  lea     edx, [rax+1]
0x18000347f  mov     dword ptr [rbp+57h+ThreadInformation], eax
0x180003482  cmp     eax, [rbx+10h]
0x180003485  jnb     loc_18000375A
0x18000348b  mov     eax, [r13+23Ch]
0x180003492  lea     rcx, [r14+7]
0x180003496  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000349a  mov     dword ptr [rsp+110h+var_E0], eax
0x18000349e  xorps   xmm0, xmm0
0x1800034a1  mov     [rbp+57h+var_C8], rcx
0x1800034a5  movups  [rbp+57h+var_C0], xmm0
0x1800034a9  mov     rbx, [rcx+10h]
0x1800034ad  movzx   eax, word ptr [rcx+10h]
0x1800034b1  mov     r14, rbx
0x1800034b4  shr     r14, 1
0x1800034b7  and     rax, rdx
0x1800034ba  and     r14w, dx
0x1800034be  shl     rax, 3
0x1800034c2  shl     r14w, 7
0x1800034c7  or      r14w, 10h
0x1800034cc  shr     rbx, 2
0x1800034d0  mov     [rbp+57h+var_38], rax
0x1800034d4  movups  [rbp+57h+var_B0], xmm0
0x1800034d8  test    r15, r15
0x1800034db  jnz     loc_180003706
0x1800034e1  mov     rcx, cs:PfSvcGlobals
0x1800034e8  lea     eax, ds:2[rbx*2]
0x1800034ef  mov     r8d, eax; dwBytes
0x1800034f2  mov     [rbp+57h+Size], rax
0x1800034f6  xor     edx, edx; dwFlags
0x1800034f8  mov     rcx, [rcx+58h]; hHeap
0x1800034fc  call    cs:__imp_HeapAlloc
0x180003502  mov     r15, rax
0x180003505  test    rax, rax
0x180003508  jz      loc_1800038D3
0x18000350e  mov     ebx, dword ptr [rsp+110h+var_E0]
0x180003512  mov     rcx, rax; void *
0x180003515  add     rbx, [rbp+57h+var_C8]
0x180003519  mov     r8, [rbp+57h+Size]; Size
0x18000351d  mov     rdx, rbx; Src
0x180003520  call    memcpy_0
0x180003525  mov     rdx, [rbp+57h+Size]
0x180003529  mov     rcx, r15; String
0x18000352c  shr     rdx, 1; Size
0x18000352f  call    cs:__imp__wcsupr_s
0x180003535  mov     rax, [rbp+57h+Size]
0x180003539  add     rax, rbx
0x18000353c  mov     word ptr [rbp+57h+var_60+8], r14w
0x180003541  mov     [rsp+110h+var_E0], rax
0x180003546  mov     rax, [rbp+57h+var_38]
0x18000354a  mov     qword ptr [rbp+57h+var_60], rax
0x18000354e  mov     eax, dword ptr [rbp+57h+var_C0+0Ah]
0x180003551  mov     dword ptr [rbp+57h+var_60+0Ah], eax
0x180003554  movzx   eax, word ptr [rbp+57h+var_C0+0Eh]
0x180003558  mov     word ptr [rbp+57h+var_60+0Eh], ax
0x18000355c  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18000355f  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x180003562  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003566  xor     r14d, r14d
0x180003569  mov     qword ptr [rbp+57h+var_50], r15
0x18000356d  inc     rax
0x180003570  cmp     [r15+rax*2], r14w
0x180003575  jnz     short loc_18000356D
0x180003577  mov     r9d, eax
0x18000357a  mov     ecx, 4CB2Fh
0x18000357f  mov     dword ptr [rbp+57h+var_50+8], r9d
0x180003583  mov     r8, r15
0x180003586  add     r9, r9
0x180003589  cmp     r9, 8
0x18000358d  jb      short loc_1800035FC
0x18000358f  movzx   eax, byte ptr [r8]
0x180003593  sub     r9, 8
0x180003597  imul    rcx, 25h ; '%'
0x18000359b  add     rcx, rax
0x18000359e  movzx   eax, byte ptr [r8+1]
0x1800035a3  imul    rdx, rcx, 25h ; '%'
0x1800035a7  add     rdx, rax
0x1800035aa  movzx   eax, byte ptr [r8+2]
0x1800035af  imul    rcx, rdx, 25h ; '%'
0x1800035b3  add     rcx, rax
0x1800035b6  movzx   eax, byte ptr [r8+3]
0x1800035bb  imul    rdx, rcx, 25h ; '%'
0x1800035bf  add     rdx, rax
0x1800035c2  movzx   eax, byte ptr [r8+4]
0x1800035c7  imul    rcx, rdx, 25h ; '%'
0x1800035cb  add     rcx, rax
0x1800035ce  movzx   eax, byte ptr [r8+5]
0x1800035d3  imul    rdx, rcx, 25h ; '%'
0x1800035d7  add     rdx, rax
0x1800035da  movzx   eax, byte ptr [r8+6]
0x1800035df  imul    rcx, rdx, 25h ; '%'
0x1800035e3  add     rcx, rax
0x1800035e6  movzx   eax, byte ptr [r8+7]
0x1800035eb  imul    rcx, 25h ; '%'
0x1800035ef  add     r8, 8
0x1800035f3  add     rcx, rax
0x1800035f6  cmp     r9, 8
0x1800035fa  jge     short loc_18000358F
0x1800035fc  sub     r9, 1
0x180003600  jz      short loc_18000366A
0x180003602  sub     r9, 1
0x180003606  jz      short loc_18000365C
0x180003608  sub     r9, 1
0x18000360c  jz      short loc_18000364E
0x18000360e  sub     r9, 1
0x180003612  jz      short loc_180003640
0x180003614  sub     r9, 1
0x180003618  jz      short loc_180003632
0x18000361a  sub     r9, 1
0x18000361e  jnz     loc_1800038AC
0x180003624  movzx   eax, byte ptr [r8]
0x180003628  imul    rcx, 25h ; '%'
0x18000362c  add     rcx, rax
0x18000362f  inc     r8
0x180003632  movzx   eax, byte ptr [r8]
0x180003636  imul    rcx, 25h ; '%'
0x18000363a  add     rcx, rax
0x18000363d  inc     r8
0x180003640  movzx   eax, byte ptr [r8]
0x180003644  imul    rcx, 25h ; '%'
0x180003648  add     rcx, rax
0x18000364b  inc     r8
0x18000364e  movzx   eax, byte ptr [r8]
0x180003652  imul    rcx, 25h ; '%'
0x180003656  add     rcx, rax
0x180003659  inc     r8
0x18000365c  movzx   eax, byte ptr [r8]
0x180003660  imul    rcx, 25h ; '%'
0x180003664  add     rcx, rax
0x180003667  inc     r8
0x18000366a  movzx   eax, byte ptr [r8]
0x18000366e  imul    rcx, 25h ; '%'
0x180003672  add     rcx, rax
0x180003675  mov     rdx, [rbp+57h+var_70]
0x180003679  lea     r8, [rbp+57h+var_60]
0x18000367d  mov     [rbp+57h+var_40], rcx
0x180003681  mov     rcx, r13
0x180003684  call    PfDbSectionCreate
0x180003689  mov     rbx, rax
0x18000368c  test    rax, rax
0x18000368f  jz      loc_1800038C9
0x180003695  mov     r8d, [r13+23Ch]
0x18000369c  lea     rcx, [rax+40h]; void *
0x1800036a0  mov     rdx, [rbp+57h+var_C8]
0x1800036a4  sub     r8d, 40h ; '@'; Size
0x1800036a8  add     rdx, 40h ; '@'; Src
0x1800036ac  call    memcpy_0
0x1800036b1  mov     rax, [r12+8]
0x1800036b6  lea     r14, [rbx+20h]
0x1800036ba  mov     r12, [rbp+57h+var_C8]
0x1800036be  test    rax, rax
0x1800036c1  jnz     short loc_180003721
0x1800036c3  mov     rax, [rbp+57h+arg_10]
0x1800036c7  lea     r9, [r12+20h]
0x1800036cc  mov     [rsp+110h+var_E8], rax
0x1800036d1  lea     r8, [rsp+110h+var_E0]
0x1800036d6  mov     rdx, rdi
0x1800036d9  mov     [rsp+110h+ReturnLength], r14
0x1800036de  mov     rcx, r13
0x1800036e1  call    PfDbFileReadRanges
0x1800036e6  mov     ebx, eax
0x1800036e8  test    eax, eax
0x1800036ea  jnz     short loc_18000373F
0x1800036ec  mov     eax, dword ptr [rbp+57h+ThreadInformation]
0x1800036ef  lea     edx, [rbx+1]
0x1800036f2  mov     r14, [rsp+110h+var_E0]
0x1800036f7  add     eax, edx
0x1800036f9  mov     r12, [rbp+57h+arg_10]
0x1800036fd  mov     rbx, [rbp+57h+var_68]
0x180003701  jmp     loc_18000347F
0x180003706  mov     rcx, cs:PfSvcGlobals
0x18000370d  mov     r8, r15; lpMem
0x180003710  xor     edx, edx; dwFlags
0x180003712  mov     rcx, [rcx+58h]; hHeap
0x180003716  call    cs:__imp_HeapFree
0x18000371c  jmp     loc_1800034E1
0x180003721  mov     r9, [rbp+57h+arg_10]
0x180003725  lea     r8, [r12+20h]
0x18000372a  mov     rdx, r14
0x18000372d  mov     rcx, rdi
0x180003730  mov     r9, [r9+18h]
0x180003734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003739  mov     ebx, eax
0x18000373b  test    eax, eax
0x18000373d  jz      short loc_1800036C3
0x18000373f  mov     rcx, cs:PfSvcGlobals
0x180003746  mov     r8, r15; lpMem
0x180003749  xor     edx, edx; dwFlags
  ... truncated ...
```
