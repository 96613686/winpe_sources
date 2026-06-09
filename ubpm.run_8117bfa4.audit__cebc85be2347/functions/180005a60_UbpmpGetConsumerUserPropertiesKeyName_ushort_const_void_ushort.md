# UbpmpGetConsumerUserPropertiesKeyName(ushort const *,void *,ushort * *)

- ea: `0x180005a60`
- end: `0x1800060c4`
- name: `?UbpmpGetConsumerUserPropertiesKeyName@@YAKPEBGPEAXPEAPEAG@Z`
- size: `1636`
- prototype: `unsigned int __fastcall(PCNZWCH lpString1, PSID Sid, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007000`
- `0x180033340`

## callees

- `0x180005a60`
- `0x1800150c0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180005eb4`
- `ntdll!RtlFreeHeap` at `0x180005f18`
- `ntdll!RtlFreeHeap` at `0x180005f4e`
- `ntdll!RtlFreeHeap` at `0x180005eb4`
- `ntdll!RtlFreeHeap` at `0x180005f18`
- `ntdll!RtlFreeHeap` at `0x180005f4e`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180005b7b`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180006027`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180005b7b`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180006027`
- `ntdll!RtlInitUnicodeString` at `0x180005b5a`
- `ntdll!RtlInitUnicodeString` at `0x180005b5a`
- `ntdll!RtlAllocateHeap` at `0x180005b2a`
- `ntdll!RtlAllocateHeap` at `0x180005c1a`
- `ntdll!RtlAllocateHeap` at `0x180005b2a`
- `ntdll!RtlAllocateHeap` at `0x180005c1a`
- `ntdll!RtlNtStatusToDosError` at `0x180006083`
- `ntdll!RtlNtStatusToDosError` at `0x180006083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006038`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006061`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000609b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006061`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000609b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005ba5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005bc1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005ba5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005bc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005edf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ef5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005edf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ef5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005ad9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005ad9`

## string_xrefs

- `0x180005acd`: `NT TASK`

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
0x180005a60  mov     rax, rsp
0x180005a63  push    rbx
0x180005a64  push    rbp
0x180005a65  push    r12
0x180005a67  push    r13
0x180005a69  sub     rsp, 68h
0x180005a6d  xor     r13d, r13d
0x180005a70  xorps   xmm0, xmm0
0x180005a73  mov     [rax+8], r13d
0x180005a77  mov     r12, r8
0x180005a7a  mov     [rax+20h], r13
0x180005a7e  mov     rbp, rdx
0x180005a81  mov     [rax-58h], r13
0x180005a85  mov     rbx, rcx
0x180005a88  movups  xmmword ptr [rax-50h], xmm0
0x180005a8c  test    rcx, rcx
0x180005a8f  jz      loc_1800060BA
0x180005a95  test    rdx, rdx
0x180005a98  jz      loc_1800060BA
0x180005a9e  test    r8, r8
0x180005aa1  jz      loc_1800060BA
0x180005aa7  mov     [rax+10h], rsi
0x180005aab  mov     r8, rcx; lpString1
0x180005aae  mov     [rax-28h], rdi
0x180005ab2  mov     r9d, 7; cchCount1
0x180005ab8  mov     dword ptr [rax-60h], 7
0x180005abf  mov     edx, 1; dwCmpFlags
0x180005ac4  mov     [rax-30h], r14
0x180005ac8  mov     ecx, 7Fh; Locale
0x180005acd  lea     rax, String2; "NT TASK"
0x180005ad4  mov     [rsp+88h+lpString2], rax; lpString2
0x180005ad9  call    cs:__imp_CompareStringW
0x180005ae0  nop     dword ptr [rax+rax+00h]
0x180005ae5  lea     rcx, [rbx+0Eh]
0x180005ae9  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180005af0  cmp     eax, 2
0x180005af3  cmovnz  rcx, rbx
0x180005af7  mov     rbx, rdi
0x180005afa  cmp     word ptr [rcx], 5Ch ; '\'
0x180005afe  lea     rsi, [rcx+2]
0x180005b02  cmovnz  rsi, rcx
0x180005b06  inc     rbx
0x180005b09  cmp     [rsi+rbx*2], r13w
0x180005b0e  jnz     short loc_180005B06
0x180005b10  mov     rcx, gs:60h
0x180005b19  lea     r8d, ds:2[rbx*2]; Size
0x180005b21  mov     edx, 8; Flags
0x180005b26  mov     rcx, [rcx+30h]; HeapHandle
0x180005b2a  call    cs:__imp_RtlAllocateHeap
0x180005b31  nop     dword ptr [rax+rax+00h]
0x180005b36  mov     r14, rax
0x180005b39  test    rax, rax
0x180005b3c  jz      loc_18000605C
0x180005b42  mov     [rsp+88h+var_38], r15
0x180005b47  mov     r15, r13
0x180005b4a  test    ebx, ebx
0x180005b4c  jnz     loc_180005F5F
0x180005b52  mov     rdx, r14; SourceString
0x180005b55  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180005b5a  call    cs:__imp_RtlInitUnicodeString
0x180005b61  nop     dword ptr [rax+rax+00h]
0x180005b66  lea     r9, [rsp+88h+Size]
0x180005b6e  xor     r8d, r8d
0x180005b71  mov     edx, 57h ; 'W'
0x180005b76  lea     rcx, [rsp+88h+DestinationString]
0x180005b7b  call    cs:__imp_RtlCreateVirtualAccountSid
0x180005b82  nop     dword ptr [rax+rax+00h]
0x180005b87  cmp     eax, 0C0000023h
0x180005b8c  jz      loc_180005FFE
0x180005b92  test    eax, eax
0x180005b94  js      loc_180006081
0x180005b9a  lea     rdx, [rsp+88h+StringSid]; StringSid
0x180005ba2  mov     rcx, r15; Sid
0x180005ba5  call    cs:__imp_ConvertSidToStringSidW
0x180005bac  nop     dword ptr [rax+rax+00h]
0x180005bb1  test    eax, eax
0x180005bb3  jz      loc_180006038
0x180005bb9  lea     rdx, [rsp+88h+var_58]; StringSid
0x180005bbe  mov     rcx, rbp; Sid
0x180005bc1  call    cs:__imp_ConvertSidToStringSidW
0x180005bc8  nop     dword ptr [rax+rax+00h]
0x180005bcd  test    eax, eax
0x180005bcf  jz      loc_180006038
0x180005bd5  mov     rcx, [rsp+88h+StringSid]
0x180005bdd  mov     rax, rdi
0x180005be0  cmp     [rcx+rax*2+2], r13w
0x180005be6  lea     rax, [rax+1]
0x180005bea  jnz     short loc_180005BE0
0x180005bec  mov     rcx, [rsp+88h+var_58]
0x180005bf1  inc     rdi
0x180005bf4  cmp     [rcx+rdi*2], r13w
0x180005bf9  jnz     short loc_180005BF1
0x180005bfb  mov     rcx, gs:60h
0x180005c04  lea     ebx, [rax+28h]
0x180005c07  add     ebx, edi
0x180005c09  mov     edx, 8; Flags
0x180005c0e  mov     rcx, [rcx+30h]; HeapHandle
0x180005c12  lea     r8d, ds:2[rbx*2]; Size
0x180005c1a  call    cs:__imp_RtlAllocateHeap
0x180005c21  nop     dword ptr [rax+rax+00h]
0x180005c26  mov     rsi, rax
0x180005c29  test    rax, rax
0x180005c2c  jz      loc_180006096
0x180005c32  mov     r11d, ebx
0x180005c35  test    ebx, ebx
0x180005c37  jz      loc_180005F37
0x180005c3d  cmp     r11, 7FFFFFFFh
0x180005c44  ja      loc_1800060B1
0x180005c4a  mov     rdx, [rsp+88h+var_58]
0x180005c4f  mov     ebx, 7FFFFFFEh
0x180005c54  mov     ecx, ebx
0x180005c56  mov     r8d, r11d
0x180005c59  mov     r9, rax
0x180005c5c  nop     dword ptr [rax+00h]
0x180005c60  test    rcx, rcx
0x180005c63  jz      short loc_180005C82
0x180005c65  movzx   eax, word ptr [rdx]
0x180005c68  test    ax, ax
0x180005c6b  jz      short loc_180005C82
0x180005c6d  mov     [r9], ax
0x180005c71  add     rdx, 2
0x180005c75  add     r9, 2
0x180005c79  dec     rcx
0x180005c7c  sub     r8, 1
0x180005c80  jnz     short loc_180005C60
0x180005c82  test    r8, r8
0x180005c85  lea     rcx, [r9-2]
0x180005c89  cmovnz  rcx, r9
0x180005c8d  mov     [rcx], r13w
0x180005c91  jz      loc_180005F37
0x180005c97  mov     rcx, r11
0x180005c9a  mov     rax, rsi
0x180005c9d  nop     dword ptr [rax]
0x180005ca0  cmp     [rax], r13w
0x180005ca4  jz      short loc_180005CBC
0x180005ca6  add     rax, 2
0x180005caa  sub     rcx, 1
0x180005cae  jnz     short loc_180005CA0
0x180005cb0  mov     edi, 80070057h
0x180005cb5  mov     rax, r13
0x180005cb8  mov     ecx, edi
0x180005cba  jmp     short loc_180005CCA
0x180005cbc  mov     rax, r11
0x180005cbf  mov     edi, 80070057h
0x180005cc4  sub     rax, rcx
0x180005cc7  mov     ecx, r13d
0x180005cca  test    ecx, ecx
0x180005ccc  js      loc_180005F37
0x180005cd2  mov     r8, r11
0x180005cd5  lea     r10, asc_180043528; "\\"
0x180005cdc  lea     r9, [rsi+rax*2]
0x180005ce0  mov     rcx, rbx
0x180005ce3  mov     rdx, r10
0x180005ce6  sub     r8, rax
0x180005ce9  jz      short loc_180005D12
0x180005ceb  nop     dword ptr [rax+rax+00h]
0x180005cf0  test    rcx, rcx
0x180005cf3  jz      short loc_180005D12
0x180005cf5  movzx   eax, word ptr [rdx]
0x180005cf8  test    ax, ax
0x180005cfb  jz      short loc_180005D12
0x180005cfd  mov     [r9], ax
0x180005d01  add     rdx, 2
0x180005d05  add     r9, 2
0x180005d09  dec     rcx
0x180005d0c  sub     r8, 1
0x180005d10  jnz     short loc_180005CF0
0x180005d12  test    r8, r8
0x180005d15  lea     rcx, [r9-2]
0x180005d19  cmovnz  rcx, r9
0x180005d1d  mov     [rcx], r13w
0x180005d21  jz      loc_180005F37
0x180005d27  mov     rcx, r11
0x180005d2a  mov     rax, rsi
0x180005d2d  nop     dword ptr [rax]
0x180005d30  cmp     [rax], r13w
0x180005d34  jz      short loc_180005D47
0x180005d36  add     rax, 2
0x180005d3a  sub     rcx, 1
0x180005d3e  jnz     short loc_180005D30
0x180005d40  mov     rax, r13
0x180005d43  mov     ecx, edi
0x180005d45  jmp     short loc_180005D50
0x180005d47  mov     rax, r11
0x180005d4a  sub     rax, rcx
0x180005d4d  mov     ecx, r13d
0x180005d50  test    ecx, ecx
0x180005d52  js      loc_180005F37
0x180005d58  mov     r8, r11
0x180005d5b  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ubp"...
0x180005d62  lea     r9, [rsi+rax*2]
0x180005d66  mov     rcx, rbx
0x180005d69  sub     r8, rax
0x180005d6c  jz      short loc_180005D92
0x180005d6e  xchg    ax, ax
0x180005d70  test    rcx, rcx
0x180005d73  jz      short loc_180005D92
0x180005d75  movzx   eax, word ptr [rdx]
0x180005d78  test    ax, ax
0x180005d7b  jz      short loc_180005D92
0x180005d7d  mov     [r9], ax
0x180005d81  add     rdx, 2
0x180005d85  add     r9, 2
0x180005d89  dec     rcx
0x180005d8c  sub     r8, 1
0x180005d90  jnz     short loc_180005D70
0x180005d92  test    r8, r8
0x180005d95  lea     rcx, [r9-2]
0x180005d99  cmovnz  rcx, r9
0x180005d9d  mov     [rcx], r13w
0x180005da1  jz      loc_180005F37
0x180005da7  mov     rcx, r11
0x180005daa  mov     rax, rsi
0x180005dad  nop     dword ptr [rax]
0x180005db0  cmp     [rax], r13w
0x180005db4  jz      short loc_180005DC7
0x180005db6  add     rax, 2
0x180005dba  sub     rcx, 1
0x180005dbe  jnz     short loc_180005DB0
0x180005dc0  mov     rax, r13
0x180005dc3  mov     ecx, edi
0x180005dc5  jmp     short loc_180005DD0
0x180005dc7  mov     rax, r11
0x180005dca  sub     rax, rcx
0x180005dcd  mov     ecx, r13d
0x180005dd0  test    ecx, ecx
0x180005dd2  js      loc_180005F37
0x180005dd8  mov     rdx, r11
0x180005ddb  lea     r8, [rsi+rax*2]
0x180005ddf  mov     rcx, rbx
0x180005de2  sub     rdx, rax
0x180005de5  jz      short loc_180005E0A
0x180005de7  test    rcx, rcx
0x180005dea  jz      short loc_180005E0A
0x180005dec  movzx   eax, word ptr [r10]
0x180005df0  test    ax, ax
0x180005df3  jz      short loc_180005E0A
0x180005df5  mov     [r8], ax
0x180005df9  add     r10, 2
0x180005dfd  add     r8, 2
0x180005e01  dec     rcx
0x180005e04  sub     rdx, 1
0x180005e08  jnz     short loc_180005DE7
0x180005e0a  test    rdx, rdx
0x180005e0d  lea     rcx, [r8-2]
0x180005e11  cmovnz  rcx, r8
0x180005e15  mov     [rcx], r13w
0x180005e19  jz      loc_180005F37
0x180005e1f  mov     rcx, r11
0x180005e22  mov     rax, rsi
0x180005e25  cmp     [rax], r13w
0x180005e29  jz      short loc_180005E3A
0x180005e2b  add     rax, 2
0x180005e2f  sub     rcx, 1
0x180005e33  jnz     short loc_180005E25
0x180005e35  mov     rax, r13
0x180005e38  jmp     short loc_180005E43
0x180005e3a  mov     rax, r11
0x180005e3d  mov     edi, r13d
0x180005e40  sub     rax, rcx
0x180005e43  test    edi, edi
0x180005e45  js      loc_180005F37
0x180005e4b  mov     rcx, [rsp+88h+StringSid]
0x180005e53  lea     rdx, [rsi+rax*2]
0x180005e57  sub     r11, rax
0x180005e5a  jz      short loc_180005E81
0x180005e5c  nop     dword ptr [rax+00h]
0x180005e60  test    rbx, rbx
0x180005e63  jz      short loc_180005E81
0x180005e65  movzx   eax, word ptr [rcx]
0x180005e68  test    ax, ax
0x180005e6b  jz      short loc_180005E81
0x180005e6d  mov     [rdx], ax
0x180005e70  add     rcx, 2
0x180005e74  add     rdx, 2
0x180005e78  dec     rbx
0x180005e7b  sub     r11, 1
0x180005e7f  jnz     short loc_180005E60
0x180005e81  test    r11, r11
0x180005e84  lea     rcx, [rdx-2]
0x180005e88  cmovnz  rcx, rdx
0x180005e8c  mov     [rcx], r13w
0x180005e90  jz      loc_180005F37
0x180005e96  mov     [r12], rsi
0x180005e9a  mov     ebx, r13d
0x180005e9d  test    r15, r15
0x180005ea0  jz      short loc_180005EC0
0x180005ea2  mov     rcx, gs:60h
0x180005eab  mov     r8, r15; P
0x180005eae  xor     edx, edx; Flags
0x180005eb0  mov     rcx, [rcx+30h]; HeapHandle
0x180005eb4  call    cs:__imp_RtlFreeHeap
0x180005ebb  nop     dword ptr [rax+rax+00h]
0x180005ec0  mov     r15, [rsp+88h+var_38]
0x180005ec5  mov     rcx, [rsp+88h+StringSid]; hMem
0x180005ecd  mov     rdi, [rsp+88h+var_28]
0x180005ed2  mov     rsi, [rsp+88h+arg_8]
0x180005eda  test    rcx, rcx
0x180005edd  jz      short loc_180005EEB
0x180005edf  call    cs:__imp_LocalFree
  ... truncated ...
```
