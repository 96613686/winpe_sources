# UbpmpGetConsumerUserPropertiesKeyName(ushort const *,void *,ushort * *)

- ea: `0x1800051b0`
- end: `0x1800057a7`
- name: `?UbpmpGetConsumerUserPropertiesKeyName@@YAKPEBGPEAXPEAPEAG@Z`
- size: `1527`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PSID Sid, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006650`
- `0x180031010`

## callees

- `0x1800051b0`
- `0x18000f9a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800055d4`
- `ntdll!RtlFreeHeap` at `0x180005626`
- `ntdll!RtlFreeHeap` at `0x180005655`
- `ntdll!RtlFreeHeap` at `0x1800055d4`
- `ntdll!RtlFreeHeap` at `0x180005626`
- `ntdll!RtlFreeHeap` at `0x180005655`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800052b9`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180005728`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800052b9`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180005728`
- `ntdll!RtlInitUnicodeString` at `0x18000529e`
- `ntdll!RtlInitUnicodeString` at `0x18000529e`
- `ntdll!RtlAllocateHeap` at `0x180005274`
- `ntdll!RtlAllocateHeap` at `0x18000534a`
- `ntdll!RtlAllocateHeap` at `0x180005274`
- `ntdll!RtlAllocateHeap` at `0x18000534a`
- `ntdll!RtlNtStatusToDosError` at `0x180005772`
- `ntdll!RtlNtStatusToDosError` at `0x180005772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005733`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005756`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005784`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005756`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005784`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005609`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005609`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005229`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005229`

## string_xrefs

- `0x18000521d`: `NT TASK`

## pseudocode

```c
__int64 __fastcall UbpmpGetConsumerUserPropertiesKeyName(PCNZWCH lpString1, PSID Sid, unsigned __int16 **a3)
{
  int v6; // eax
  PCNZWCH v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rbx
  PCNZWCH v10; // rsi
  WCHAR *Heap; // r14
  void *v12; // r15
  NTSTATUS v13; // eax
  __int64 v14; // rax
  unsigned int v16; // ebx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  __int64 v19; // r11
  LPWSTR v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned __int16 *v24; // r9
  unsigned __int16 *v25; // rcx
  __int64 v26; // rcx
  int v27; // edi
  __int64 v28; // rax
  int v29; // ecx
  const wchar_t *v30; // r10
  unsigned __int16 *v31; // r9
  __int64 v32; // rcx
  const wchar_t *v33; // rdx
  __int64 v34; // r8
  unsigned __int16 *v35; // rcx
  __int64 v36; // rcx
  unsigned __int16 *v37; // rax
  __int64 v38; // rax
  int v39; // ecx
  const WCHAR *v40; // rdx
  unsigned __int16 *v41; // r9
  __int64 v42; // rcx
  __int64 v43; // r8
  unsigned __int16 *v44; // rcx
  __int64 v45; // rcx
  unsigned __int16 *v46; // rax
  __int64 v47; // rax
  int v48; // ecx
  unsigned __int16 *v49; // r8
  __int64 v50; // rcx
  __int64 v51; // rdx
  unsigned __int16 *v52; // rcx
  __int64 v53; // rcx
  unsigned __int16 *v54; // rax
  __int64 v55; // rax
  LPWSTR v56; // rcx
  unsigned __int16 *v57; // rdx
  __int64 i; // r11
  unsigned __int16 *v59; // rcx
  ULONG v60; // ebx
  unsigned int v62; // edx
  __int64 v63; // rcx
  __int16 v64; // ax
  __int64 v65; // rax
  __m128 v66; // xmm3
  __m128 v67; // xmm4
  void *v68; // rax
  signed int LastError; // eax
  LPWSTR v70; // [rsp+30h] [rbp-58h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-50h] BYREF
  SIZE_T Size; // [rsp+90h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+A8h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  StringSid = 0;
  v70 = 0;
  DestinationString = 0;
  if ( !lpString1 || !Sid || !a3 )
    return 87;
  v6 = CompareStringW(0x7Fu, 1u, lpString1, 7, L"NT TASK", 7);
  v7 = lpString1 + 7;
  v8 = -1;
  if ( v6 != 2 )
    v7 = lpString1;
  v9 = -1;
  v10 = v7 + 1;
  if ( *v7 != 92 )
    v10 = v7;
  do
    ++v9;
  while ( v10[v9] );
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)(2 * v9 + 2));
  if ( Heap )
  {
    v12 = 0;
    if ( (_DWORD)v9 )
    {
      v62 = 0;
      if ( (unsigned int)v9 < 8 || Heap <= &v10[(unsigned int)(v9 - 1)] && &Heap[(unsigned int)(v9 - 1)] >= v10 )
        goto LABEL_113;
      do
      {
        v65 = v62;
        v62 += 8;
        v66 = (__m128)_mm_loadu_si128((const __m128i *)&v10[v65]);
        v67 = (__m128)_mm_cmpeq_epi16((__m128i)v66, (__m128i)_xmm);
        *(__m128 *)&Heap[v65] = _mm_or_ps(
                                  _mm_and_ps(
                                    _mm_or_ps(
                                      _mm_andnot_ps(v67, (__m128)_mm_loadu_si128((const __m128i *)&Heap[v65])),
                                      _mm_and_ps((__m128)_mm_load_si128((const __m128i *)&_xmm), v67)),
                                    v67),
                                  _mm_andnot_ps(v67, v66));
      }
      while ( v62 < ((unsigned int)v9 & 0xFFFFFFF8) );
      if ( v62 < (unsigned int)v9 )
      {
LABEL_113:
        do
        {
          v63 = v62;
          v64 = v10[v63];
          if ( v64 == 92 )
            v64 = 45;
          ++v62;
          Heap[v63] = v64;
        }
        while ( v62 < (unsigned int)v9 );
      }
    }
    RtlInitUnicodeString(&DestinationString, Heap);
    v13 = RtlCreateVirtualAccountSid(&DestinationString, 87, 0, &Size);
    if ( v13 != -1073741789 )
    {
LABEL_12:
      if ( v13 < 0 )
      {
        v60 = RtlNtStatusToDosError(v13);
      }
      else
      {
        if ( !ConvertSidToStringSidW(v12, &StringSid) || !ConvertSidToStringSidW(Sid, &v70) )
        {
          LastError = GetLastError();
          v60 = LastError;
          if ( LastError > 0 )
            v60 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_81;
        }
        v14 = -1;
        while ( StringSid[++v14] != 0 )
          ;
        do
          ++v8;
        while ( v70[v8] );
        v16 = v8 + v14 + 40;
        v17 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v16 + 2);
        v18 = v17;
        if ( v17 )
        {
          v19 = v16;
          if ( v16 )
          {
            if ( v16 > 0x7FFFFFFFuLL )
            {
              *v17 = 0;
            }
            else
            {
              v20 = v70;
              v21 = 2147483646;
              v22 = 2147483646;
              v23 = (unsigned int)v19;
              v24 = v17;
              do
              {
                if ( !v22 )
                  break;
                if ( !*v20 )
                  break;
                *v24++ = *v20++;
                --v22;
                --v23;
              }
              while ( v23 );
              v25 = v24 - 1;
              if ( v23 )
                v25 = v24;
              *v25 = 0;
              if ( v23 )
              {
                v26 = v19;
                while ( *v17 )
                {
                  ++v17;
                  if ( !--v26 )
                  {
                    v27 = -2147024809;
                    v28 = 0;
                    v29 = -2147024809;
                    goto LABEL_33;
                  }
                }
                v27 = -2147024809;
                v28 = v19 - v26;
                v29 = 0;
LABEL_33:
                if ( v29 >= 0 )
                {
                  v30 = L"\\";
                  v31 = &v18[v28];
                  v32 = 2147483646;
                  v33 = L"\\";
                  v34 = v19 - v28;
                  if ( v19 != v28 )
                  {
                    do
                    {
                      if ( !v32 )
                        break;
                      if ( !*v33 )
                        break;
                      *v31++ = *v33++;
                      --v32;
                      --v34;
                    }
                    while ( v34 );
                  }
                  v35 = v31 - 1;
                  if ( v34 )
                    v35 = v31;
                  *v35 = 0;
                  if ( v34 )
                  {
                    v36 = v19;
                    v37 = v18;
                    while ( *v37 )
                    {
                      ++v37;
                      if ( !--v36 )
                      {
                        v38 = 0;
                        v39 = -2147024809;
                        goto LABEL_46;
                      }
                    }
                    v38 = v19 - v36;
                    v39 = 0;
LABEL_46:
                    if ( v39 >= 0 )
                    {
                      v40 = L"System\\CurrentControlSet\\Control\\Ubpm";
                      v41 = &v18[v38];
                      v42 = 2147483646;
                      v43 = v19 - v38;
                      if ( v19 != v38 )
                      {
                        do
                        {
                          if ( !v42 )
                            break;
                          if ( !*v40 )
                            break;
                          *v41++ = *v40++;
                          --v42;
                          --v43;
                        }
                        while ( v43 );
                      }
                      v44 = v41 - 1;
                      if ( v43 )
                        v44 = v41;
                      *v44 = 0;
                      if ( v43 )
                      {
                        v45 = v19;
                        v46 = v18;
                        while ( *v46 )
                        {
                          ++v46;
                          if ( !--v45 )
                          {
                            v47 = 0;
                            v48 = -2147024809;
                            goto LABEL_59;
                          }
                        }
                        v47 = v19 - v45;
                        v48 = 0;
LABEL_59:
                        if ( v48 >= 0 )
                        {
                          v49 = &v18[v47];
                          v50 = 2147483646;
                          v51 = v19 - v47;
                          if ( v19 != v47 )
                          {
                            do
                            {
                              if ( !v50 )
                                break;
                              if ( !*v30 )
                                break;
                              *v49++ = *v30++;
                              --v50;
                              --v51;
                            }
                            while ( v51 );
                          }
                          v52 = v49 - 1;
                          if ( v51 )
                            v52 = v49;
                          *v52 = 0;
                          if ( v51 )
                          {
                            v53 = v19;
                            v54 = v18;
                            while ( *v54 )
                            {
                              ++v54;
                              if ( !--v53 )
                              {
                                v55 = 0;
                                goto LABEL_72;
                              }
                            }
                            v27 = 0;
                            v55 = v19 - v53;
LABEL_72:
                            if ( v27 >= 0 )
                            {
                              v56 = StringSid;
                              v57 = &v18[v55];
                              for ( i = v19 - v55; i; --i )
                              {
                                if ( !v21 )
                                  break;
                                if ( !*v56 )
                                  break;
                                *v57++ = *v56++;
                                --v21;
                              }
                              v59 = v57 - 1;
                              if ( i )
                                v59 = v57;
                              *v59 = 0;
                              if ( i )
                              {
                                *a3 = v18;
                                v60 = 0;
                                goto LABEL_81;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          v60 = 111;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
        }
        else
        {
          SetLastError(8u);
          v60 = 14;
        }
      }
LABEL_81:
      if ( v12 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      goto LABEL_83;
    }
    v68 = UbpmAlloc((unsigned int)Size);
    v12 = v68;
    if ( v68 )
    {
      v13 = RtlCreateVirtualAccountSid(&DestinationString, 87, v68, &Size);
      goto LABEL_12;
    }
    v60 = 14;
  }
  else
  {
    SetLastError(8u);
    v60 = 14;
  }
LABEL_83:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v70 )
    LocalFree(v70);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v60;
}

```

## disassembly

```asm
0x1800051b0  mov     rax, rsp
0x1800051b3  push    rbx
0x1800051b4  push    rbp
0x1800051b5  push    r12
0x1800051b7  push    r13
0x1800051b9  sub     rsp, 68h
0x1800051bd  xor     r13d, r13d
0x1800051c0  xorps   xmm0, xmm0
0x1800051c3  mov     [rax+8], r13d
0x1800051c7  mov     r12, r8
0x1800051ca  mov     [rax+20h], r13
0x1800051ce  mov     rbp, rdx
0x1800051d1  mov     [rax-58h], r13
0x1800051d5  mov     rbx, rcx
0x1800051d8  movups  xmmword ptr [rax-50h], xmm0
0x1800051dc  test    rcx, rcx
0x1800051df  jz      loc_18000579D
0x1800051e5  test    rdx, rdx
0x1800051e8  jz      loc_18000579D
0x1800051ee  test    r8, r8
0x1800051f1  jz      loc_18000579D
0x1800051f7  mov     [rax+10h], rsi
0x1800051fb  mov     r8, rcx; lpString1
0x1800051fe  mov     [rax-28h], rdi
0x180005202  mov     r9d, 7; cchCount1
0x180005208  mov     dword ptr [rax-60h], 7
0x18000520f  mov     edx, 1; dwCmpFlags
0x180005214  mov     [rax-30h], r14
0x180005218  mov     ecx, 7Fh; Locale
0x18000521d  lea     rax, String2; "NT TASK"
0x180005224  mov     [rsp+88h+lpString2], rax; lpString2
0x180005229  call    cs:__imp_CompareStringW
0x18000522f  lea     rcx, [rbx+0Eh]
0x180005233  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000523a  cmp     eax, 2
0x18000523d  cmovnz  rcx, rbx
0x180005241  mov     rbx, rdi
0x180005244  cmp     word ptr [rcx], 5Ch ; '\'
0x180005248  lea     rsi, [rcx+2]
0x18000524c  cmovnz  rsi, rcx
0x180005250  inc     rbx
0x180005253  cmp     [rsi+rbx*2], r13w
0x180005258  jnz     short loc_180005250
0x18000525a  mov     rcx, gs:60h
0x180005263  lea     r8d, ds:2[rbx*2]; Size
0x18000526b  mov     edx, 8; Flags
0x180005270  mov     rcx, [rcx+30h]; HeapHandle
0x180005274  call    cs:__imp_RtlAllocateHeap
0x18000527a  mov     r14, rax
0x18000527d  test    rax, rax
0x180005280  jz      loc_180005751
0x180005286  mov     [rsp+88h+var_38], r15
0x18000528b  mov     r15, r13
0x18000528e  test    ebx, ebx
0x180005290  jnz     loc_180005660
0x180005296  mov     rdx, r14; SourceString
0x180005299  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18000529e  call    cs:__imp_RtlInitUnicodeString
0x1800052a4  lea     r9, [rsp+88h+Size]
0x1800052ac  xor     r8d, r8d
0x1800052af  mov     edx, 57h ; 'W'
0x1800052b4  lea     rcx, [rsp+88h+DestinationString]
0x1800052b9  call    cs:__imp_RtlCreateVirtualAccountSid
0x1800052bf  cmp     eax, 0C0000023h
0x1800052c4  jz      loc_1800056FF
0x1800052ca  test    eax, eax
0x1800052cc  js      loc_180005770
0x1800052d2  lea     rdx, [rsp+88h+StringSid]; StringSid
0x1800052da  mov     rcx, r15; Sid
0x1800052dd  call    cs:__imp_ConvertSidToStringSidW
0x1800052e3  test    eax, eax
0x1800052e5  jz      loc_180005733
0x1800052eb  lea     rdx, [rsp+88h+var_58]; StringSid
0x1800052f0  mov     rcx, rbp; Sid
0x1800052f3  call    cs:__imp_ConvertSidToStringSidW
0x1800052f9  test    eax, eax
0x1800052fb  jz      loc_180005733
0x180005301  mov     rcx, [rsp+88h+StringSid]
0x180005309  mov     rax, rdi
0x18000530c  nop     dword ptr [rax+00h]
0x180005310  cmp     [rcx+rax*2+2], r13w
0x180005316  lea     rax, [rax+1]
0x18000531a  jnz     short loc_180005310
0x18000531c  mov     rcx, [rsp+88h+var_58]
0x180005321  inc     rdi
0x180005324  cmp     [rcx+rdi*2], r13w
0x180005329  jnz     short loc_180005321
0x18000532b  mov     rcx, gs:60h
0x180005334  lea     ebx, [rax+28h]
0x180005337  add     ebx, edi
0x180005339  mov     edx, 8; Flags
0x18000533e  mov     rcx, [rcx+30h]; HeapHandle
0x180005342  lea     r8d, ds:2[rbx*2]; Size
0x18000534a  call    cs:__imp_RtlAllocateHeap
0x180005350  mov     rsi, rax
0x180005353  test    rax, rax
0x180005356  jz      loc_18000577F
0x18000535c  mov     r11d, ebx
0x18000535f  test    ebx, ebx
0x180005361  jz      loc_18000563E
0x180005367  cmp     r11, 7FFFFFFFh
0x18000536e  ja      loc_180005794
0x180005374  mov     rdx, [rsp+88h+var_58]
0x180005379  mov     ebx, 7FFFFFFEh
0x18000537e  mov     ecx, ebx
0x180005380  mov     r8d, r11d
0x180005383  mov     r9, rax
0x180005386  test    rcx, rcx
0x180005389  jz      short loc_1800053A8
0x18000538b  movzx   eax, word ptr [rdx]
0x18000538e  test    ax, ax
0x180005391  jz      short loc_1800053A8
0x180005393  mov     [r9], ax
0x180005397  add     rdx, 2
0x18000539b  add     r9, 2
0x18000539f  dec     rcx
0x1800053a2  sub     r8, 1
0x1800053a6  jnz     short loc_180005386
0x1800053a8  test    r8, r8
0x1800053ab  lea     rcx, [r9-2]
0x1800053af  cmovnz  rcx, r9
0x1800053b3  mov     [rcx], r13w
0x1800053b7  jz      loc_18000563E
0x1800053bd  mov     rcx, r11
0x1800053c0  mov     rax, rsi
0x1800053c3  cmp     [rax], r13w
0x1800053c7  jz      short loc_1800053DF
0x1800053c9  add     rax, 2
0x1800053cd  sub     rcx, 1
0x1800053d1  jnz     short loc_1800053C3
0x1800053d3  mov     edi, 80070057h
0x1800053d8  mov     rax, r13
0x1800053db  mov     ecx, edi
0x1800053dd  jmp     short loc_1800053ED
0x1800053df  mov     rax, r11
0x1800053e2  mov     edi, 80070057h
0x1800053e7  sub     rax, rcx
0x1800053ea  mov     ecx, r13d
0x1800053ed  test    ecx, ecx
0x1800053ef  js      loc_18000563E
0x1800053f5  mov     r8, r11
0x1800053f8  lea     r10, asc_180040608; "\\"
0x1800053ff  lea     r9, [rsi+rax*2]
0x180005403  mov     rcx, rbx
0x180005406  mov     rdx, r10
0x180005409  sub     r8, rax
0x18000540c  jz      short loc_180005432
0x18000540e  xchg    ax, ax
0x180005410  test    rcx, rcx
0x180005413  jz      short loc_180005432
0x180005415  movzx   eax, word ptr [rdx]
0x180005418  test    ax, ax
0x18000541b  jz      short loc_180005432
0x18000541d  mov     [r9], ax
0x180005421  add     rdx, 2
0x180005425  add     r9, 2
0x180005429  dec     rcx
0x18000542c  sub     r8, 1
0x180005430  jnz     short loc_180005410
0x180005432  test    r8, r8
0x180005435  lea     rcx, [r9-2]
0x180005439  cmovnz  rcx, r9
0x18000543d  mov     [rcx], r13w
0x180005441  jz      loc_18000563E
0x180005447  mov     rcx, r11
0x18000544a  mov     rax, rsi
0x18000544d  nop     dword ptr [rax]
0x180005450  cmp     [rax], r13w
0x180005454  jz      short loc_180005467
0x180005456  add     rax, 2
0x18000545a  sub     rcx, 1
0x18000545e  jnz     short loc_180005450
0x180005460  mov     rax, r13
0x180005463  mov     ecx, edi
0x180005465  jmp     short loc_180005470
0x180005467  mov     rax, r11
0x18000546a  sub     rax, rcx
0x18000546d  mov     ecx, r13d
0x180005470  test    ecx, ecx
0x180005472  js      loc_18000563E
0x180005478  mov     r8, r11
0x18000547b  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ubp"...
0x180005482  lea     r9, [rsi+rax*2]
0x180005486  mov     rcx, rbx
0x180005489  sub     r8, rax
0x18000548c  jz      short loc_1800054B2
0x18000548e  xchg    ax, ax
0x180005490  test    rcx, rcx
0x180005493  jz      short loc_1800054B2
0x180005495  movzx   eax, word ptr [rdx]
0x180005498  test    ax, ax
0x18000549b  jz      short loc_1800054B2
0x18000549d  mov     [r9], ax
0x1800054a1  add     rdx, 2
0x1800054a5  add     r9, 2
0x1800054a9  dec     rcx
0x1800054ac  sub     r8, 1
0x1800054b0  jnz     short loc_180005490
0x1800054b2  test    r8, r8
0x1800054b5  lea     rcx, [r9-2]
0x1800054b9  cmovnz  rcx, r9
0x1800054bd  mov     [rcx], r13w
0x1800054c1  jz      loc_18000563E
0x1800054c7  mov     rcx, r11
0x1800054ca  mov     rax, rsi
0x1800054cd  nop     dword ptr [rax]
0x1800054d0  cmp     [rax], r13w
0x1800054d4  jz      short loc_1800054E7
0x1800054d6  add     rax, 2
0x1800054da  sub     rcx, 1
0x1800054de  jnz     short loc_1800054D0
0x1800054e0  mov     rax, r13
0x1800054e3  mov     ecx, edi
0x1800054e5  jmp     short loc_1800054F0
0x1800054e7  mov     rax, r11
0x1800054ea  sub     rax, rcx
0x1800054ed  mov     ecx, r13d
0x1800054f0  test    ecx, ecx
0x1800054f2  js      loc_18000563E
0x1800054f8  mov     rdx, r11
0x1800054fb  lea     r8, [rsi+rax*2]
0x1800054ff  mov     rcx, rbx
0x180005502  sub     rdx, rax
0x180005505  jz      short loc_18000552A
0x180005507  test    rcx, rcx
0x18000550a  jz      short loc_18000552A
0x18000550c  movzx   eax, word ptr [r10]
0x180005510  test    ax, ax
0x180005513  jz      short loc_18000552A
0x180005515  mov     [r8], ax
0x180005519  add     r10, 2
0x18000551d  add     r8, 2
0x180005521  dec     rcx
0x180005524  sub     rdx, 1
0x180005528  jnz     short loc_180005507
0x18000552a  test    rdx, rdx
0x18000552d  lea     rcx, [r8-2]
0x180005531  cmovnz  rcx, r8
0x180005535  mov     [rcx], r13w
0x180005539  jz      loc_18000563E
0x18000553f  mov     rcx, r11
0x180005542  mov     rax, rsi
0x180005545  cmp     [rax], r13w
0x180005549  jz      short loc_18000555A
0x18000554b  add     rax, 2
0x18000554f  sub     rcx, 1
0x180005553  jnz     short loc_180005545
0x180005555  mov     rax, r13
0x180005558  jmp     short loc_180005563
0x18000555a  mov     rax, r11
0x18000555d  mov     edi, r13d
0x180005560  sub     rax, rcx
0x180005563  test    edi, edi
0x180005565  js      loc_18000563E
0x18000556b  mov     rcx, [rsp+88h+StringSid]
0x180005573  lea     rdx, [rsi+rax*2]
0x180005577  sub     r11, rax
0x18000557a  jz      short loc_1800055A1
0x18000557c  nop     dword ptr [rax+00h]
0x180005580  test    rbx, rbx
0x180005583  jz      short loc_1800055A1
0x180005585  movzx   eax, word ptr [rcx]
0x180005588  test    ax, ax
0x18000558b  jz      short loc_1800055A1
0x18000558d  mov     [rdx], ax
0x180005590  add     rcx, 2
0x180005594  add     rdx, 2
0x180005598  dec     rbx
0x18000559b  sub     r11, 1
0x18000559f  jnz     short loc_180005580
0x1800055a1  test    r11, r11
0x1800055a4  lea     rcx, [rdx-2]
0x1800055a8  cmovnz  rcx, rdx
0x1800055ac  mov     [rcx], r13w
0x1800055b0  jz      loc_18000563E
0x1800055b6  mov     [r12], rsi
0x1800055ba  mov     ebx, r13d
0x1800055bd  test    r15, r15
0x1800055c0  jz      short loc_1800055DA
0x1800055c2  mov     rcx, gs:60h
0x1800055cb  mov     r8, r15; P
0x1800055ce  xor     edx, edx; Flags
0x1800055d0  mov     rcx, [rcx+30h]; HeapHandle
0x1800055d4  call    cs:__imp_RtlFreeHeap
0x1800055da  mov     r15, [rsp+88h+var_38]
0x1800055df  mov     rcx, [rsp+88h+StringSid]; hMem
0x1800055e7  mov     rdi, [rsp+88h+var_28]
0x1800055ec  mov     rsi, [rsp+88h+arg_8]
0x1800055f4  test    rcx, rcx
0x1800055f7  jz      short loc_1800055FF
0x1800055f9  call    cs:__imp_LocalFree
0x1800055ff  mov     rcx, [rsp+88h+var_58]; hMem
0x180005604  test    rcx, rcx
0x180005607  jz      short loc_18000560F
0x180005609  call    cs:__imp_LocalFree
0x18000560f  test    r14, r14
0x180005612  jz      short loc_18000562C
0x180005614  mov     rcx, gs:60h
0x18000561d  mov     r8, r14; P
0x180005620  xor     edx, edx; Flags
  ... truncated ...
```
