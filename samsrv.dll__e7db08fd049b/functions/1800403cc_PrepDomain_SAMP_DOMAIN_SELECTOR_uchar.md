# PrepDomain(_SAMP_DOMAIN_SELECTOR,uchar)

- ea: `0x1800403cc`
- end: `0x180040a9e`
- name: `?PrepDomain@@YAJW4_SAMP_DOMAIN_SELECTOR@@E@Z`
- size: `1746`
- prototype: `NTSTATUS __fastcall(unsigned int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003d938`
- `0x18003e2d4`

## callees

- `0x18002cd80`
- `0x18002d720`
- `0x1800403cc`
- `0x180041560`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlApplyRXactNoFlush` at `0x180040a6e`
- `ntdll!RtlApplyRXactNoFlush` at `0x180040a6e`
- `ntdll!RtlStartRXact` at `0x1800404ab`
- `ntdll!RtlStartRXact` at `0x1800404ab`
- `ntdll!RtlAppendUnicodeToString` at `0x180040877`
- `ntdll!RtlAppendUnicodeToString` at `0x1800408c5`
- `ntdll!RtlAppendUnicodeToString` at `0x18004090f`
- `ntdll!RtlAppendUnicodeToString` at `0x180040959`
- `ntdll!RtlAppendUnicodeToString` at `0x1800409a3`
- `ntdll!RtlAppendUnicodeToString` at `0x1800409ed`
- `ntdll!RtlAppendUnicodeToString` at `0x180040a37`
- `ntdll!RtlAppendUnicodeToString` at `0x180040877`
- `ntdll!RtlAppendUnicodeToString` at `0x1800408c5`
- `ntdll!RtlAppendUnicodeToString` at `0x18004090f`
- `ntdll!RtlAppendUnicodeToString` at `0x180040959`
- `ntdll!RtlAppendUnicodeToString` at `0x1800409a3`
- `ntdll!RtlAppendUnicodeToString` at `0x1800409ed`
- `ntdll!RtlAppendUnicodeToString` at `0x180040a37`
- `ntdll!NtQuerySystemTime` at `0x180040530`
- `ntdll!NtQuerySystemTime` at `0x180040530`
- `ntdll!RtlFreeHeap` at `0x180040806`
- `ntdll!RtlFreeHeap` at `0x180040857`
- `ntdll!RtlFreeHeap` at `0x180040806`
- `ntdll!RtlFreeHeap` at `0x180040857`
- `ntdll!RtlAllocateHeap` at `0x1800404e0`
- `ntdll!RtlAllocateHeap` at `0x1800406cf`
- `ntdll!RtlAllocateHeap` at `0x1800404e0`
- `ntdll!RtlAllocateHeap` at `0x1800406cf`
- `ntdll!RtlAddAttributeActionToRXact` at `0x1800407e8`
- `ntdll!RtlAddAttributeActionToRXact` at `0x180040839`
- `ntdll!RtlAddAttributeActionToRXact` at `0x1800407e8`
- `ntdll!RtlAddAttributeActionToRXact` at `0x180040839`
- `ntdll!RtlCopyUnicodeString` at `0x1800404c5`
- `ntdll!RtlCopyUnicodeString` at `0x180040867`
- `ntdll!RtlCopyUnicodeString` at `0x1800408b5`
- `ntdll!RtlCopyUnicodeString` at `0x1800408ff`
- `ntdll!RtlCopyUnicodeString` at `0x180040949`
- `ntdll!RtlCopyUnicodeString` at `0x180040993`
- `ntdll!RtlCopyUnicodeString` at `0x1800409dd`
- `ntdll!RtlCopyUnicodeString` at `0x180040a27`
- `ntdll!RtlCopyUnicodeString` at `0x1800404c5`
- `ntdll!RtlCopyUnicodeString` at `0x180040867`
- `ntdll!RtlCopyUnicodeString` at `0x1800408b5`
- `ntdll!RtlCopyUnicodeString` at `0x1800408ff`
- `ntdll!RtlCopyUnicodeString` at `0x180040949`
- `ntdll!RtlCopyUnicodeString` at `0x180040993`
- `ntdll!RtlCopyUnicodeString` at `0x1800409dd`
- `ntdll!RtlCopyUnicodeString` at `0x180040a27`
- `ntdll!RtlAddActionToRXact` at `0x18004089f`
- `ntdll!RtlAddActionToRXact` at `0x1800408e9`
- `ntdll!RtlAddActionToRXact` at `0x180040933`
- `ntdll!RtlAddActionToRXact` at `0x18004097d`
- `ntdll!RtlAddActionToRXact` at `0x1800409c7`
- `ntdll!RtlAddActionToRXact` at `0x180040a11`
- `ntdll!RtlAddActionToRXact` at `0x180040a5b`
- `ntdll!RtlAddActionToRXact` at `0x18004089f`
- `ntdll!RtlAddActionToRXact` at `0x1800408e9`
- `ntdll!RtlAddActionToRXact` at `0x180040933`
- `ntdll!RtlAddActionToRXact` at `0x18004097d`
- `ntdll!RtlAddActionToRXact` at `0x1800409c7`
- `ntdll!RtlAddActionToRXact` at `0x180040a11`
- `ntdll!RtlAddActionToRXact` at `0x180040a5b`
- `ntdll!RtlLengthSid` at `0x18004069c`
- `ntdll!RtlLengthSid` at `0x180040709`
- `ntdll!RtlLengthSid` at `0x18004071e`
- `ntdll!RtlLengthSid` at `0x180040748`
- `ntdll!RtlLengthSid` at `0x180040784`
- `ntdll!RtlLengthSid` at `0x18004069c`
- `ntdll!RtlLengthSid` at `0x180040709`
- `ntdll!RtlLengthSid` at `0x18004071e`
- `ntdll!RtlLengthSid` at `0x180040748`
- `ntdll!RtlLengthSid` at `0x180040784`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180040416`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180040416`

## pseudocode

```c
NTSTATUS __fastcall PrepDomain(unsigned int a1, char a2)
{
  _BOOL8 v4; // rdx
  int v5; // edx
  int v6; // ecx
  ULONG v7; // r8d
  ULONG v8; // r12d
  ULONG v9; // ebp
  __int64 *v10; // r14
  __int64 *v11; // r15
  char *Heap; // rax
  char *ValueData; // rdi
  struct _PSAMP_DEFINED_DOMAINS *v14; // rcx
  _DWORD *v15; // rax
  _DWORD *v16; // r13
  ULONG v17; // eax
  PSID v18; // rcx
  ULONG v19; // eax
  int v20; // ecx
  ULONG v21; // eax
  int v22; // ecx
  ULONG v23; // eax
  NTSTATUS v24; // eax
  struct _PEB *v25; // rcx
  NTSTATUS v26; // eax
  struct _PEB *v27; // rcx
  NTSTATUS result; // eax
  ULONG v29; // [rsp+40h] [rbp-188h]
  unsigned int ValueDataSize; // [rsp+44h] [rbp-184h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-178h] BYREF
  __int16 v32; // [rsp+168h] [rbp-60h]
  char v33; // [rsp+16Ah] [rbp-5Eh]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  GetVersionExW(&VersionInformation);
  v4 = v33 == 1 && (v32 & 0x200) != 0;
  SetCurrentDomain(a1, v4);
  if ( a1 )
  {
    v29 = 2;
    v10 = &qword_1800F0810;
    v9 = 0;
    v11 = qword_1800F0818;
    v8 = 3;
    if ( ProductType != NtProductLanManNt )
      v8 = v7;
  }
  else
  {
    v8 = 0;
    v29 = 0;
    if ( ProductType == NtProductLanManNt )
      v9 = v6 + 8;
    else
      v9 = 4 - (v5 != 0);
    v10 = &qword_1800F07F0;
    v11 = qword_1800F07F8;
  }
  dword_1800EF708 = RtlStartRXact(P);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x170u);
  ValueData = Heap;
  if ( !Heap )
    dword_1800EF708 = -1073741670;
  memset_0(Heap, 0, 0x170u);
  *((_DWORD *)ValueData + 23) = dword_1800EF778;
  *(_DWORD *)ValueData = 65539;
  *((_DWORD *)ValueData + 19) = 8;
  *((_DWORD *)ValueData + 18) = 1000;
  *((_DWORD *)ValueData + 22) = 1;
  NtQuerySystemTime((PLARGE_INTEGER)ValueData + 1);
  *((_QWORD *)ValueData + 3) = 0xFFFFDE4000000000uLL;
  *((union _LARGE_INTEGER *)ValueData + 4) = SampImmediatelyDeltaTime;
  *((union _LARGE_INTEGER *)ValueData + 5) = SampNeverDeltaTime;
  *((_DWORD *)ValueData + 13) = -2;
  *((_DWORD *)ValueData + 15) = -2;
  *((_QWORD *)ValueData + 2) = 0;
  ValueData[96] = 0;
  *((_DWORD *)ValueData + 12) = -1705032704;
  *((_DWORD *)ValueData + 14) = -1705032704;
  *((_WORD *)ValueData + 42) = 10;
  *((_QWORD *)ValueData + 8) = 0;
  if ( a2 )
  {
    v14 = SampDefinedDomains;
    *((_WORD *)ValueData + 51) = *((_WORD *)SampDefinedDomains + 979) | 2;
    *(_OWORD *)(ValueData + 104) = *(_OWORD *)((char *)v14 + 1960);
    *(_OWORD *)(ValueData + 120) = *(_OWORD *)((char *)v14 + 1976);
    *(_OWORD *)(ValueData + 136) = *(_OWORD *)((char *)v14 + 1992);
    *(_OWORD *)(ValueData + 152) = *(_OWORD *)((char *)v14 + 2008);
    *(_OWORD *)(ValueData + 168) = *(_OWORD *)((char *)v14 + 2024);
    *(_OWORD *)(ValueData + 184) = *(_OWORD *)((char *)v14 + 2040);
    *(_OWORD *)(ValueData + 200) = *(_OWORD *)((char *)v14 + 2056);
    *(_OWORD *)(ValueData + 216) = *(_OWORD *)((char *)v14 + 2072);
    *((_DWORD *)ValueData + 90) = *((_DWORD *)v14 + 554);
    *((_DWORD *)ValueData + 91) = *((_DWORD *)v14 + 555);
    *(_OWORD *)(ValueData + 232) = *(_OWORD *)((char *)v14 + 2088);
    *(_OWORD *)(ValueData + 248) = *(_OWORD *)((char *)v14 + 2104);
    *(_OWORD *)(ValueData + 264) = *(_OWORD *)((char *)v14 + 2120);
    *(_OWORD *)(ValueData + 280) = *(_OWORD *)((char *)v14 + 2136);
    *(_OWORD *)(ValueData + 296) = *(_OWORD *)((char *)v14 + 2152);
    *(_OWORD *)(ValueData + 312) = *(_OWORD *)((char *)v14 + 2168);
    *(_OWORD *)(ValueData + 328) = *(_OWORD *)((char *)v14 + 2184);
    *(_OWORD *)(ValueData + 344) = *(_OWORD *)((char *)v14 + 2200);
  }
  ValueDataSize = ((*(_DWORD *)v10 + 3) & 0xFFFFFFFC) + ((RtlLengthSid(qword_1800EF7C0) + 3) & 0xFFFFFFFC) + 48;
  v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ValueDataSize);
  v16 = v15;
  if ( !v15 )
    dword_1800EF708 = -1073741670;
  *v15 = 0;
  v15[1] = *(_DWORD *)v10;
  v15[2] = 65539;
  v15[3] = (*(_DWORD *)v10 + 3) & 0xFFFFFFFC;
  v17 = RtlLengthSid(qword_1800EF7C0);
  v18 = qword_1800EF7C0;
  v16[4] = v17;
  v16[5] = 0;
  v19 = RtlLengthSid(v18);
  v20 = *(_DWORD *)v10 + 3;
  *(_QWORD *)(v16 + 7) = 0;
  v16[6] = ((v19 + 3) & 0xFFFFFFFC) + (v20 & 0xFFFFFFFC);
  v21 = RtlLengthSid(qword_1800EF7C0);
  v22 = *(_DWORD *)v10 + 3;
  *((_QWORD *)v16 + 5) = 0;
  v16[9] = ((v21 + 3) & 0xFFFFFFFC) + (v22 & 0xFFFFFFFC);
  memcpy_0(v16 + 12, (const void *)*v11, *(unsigned int *)v10);
  v23 = RtlLengthSid(qword_1800EF7C0);
  memcpy_0((char *)v16 + ((*(_DWORD *)v10 + 3) & 0xFFFFFFFC) + 48, qword_1800EF7C0, v23);
  v24 = RtlAddAttributeActionToRXact(
          P,
          2u,
          &KeyName,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          &SampFixedAttributeName,
          3u,
          ValueData,
          0x170u);
  v25 = NtCurrentPeb();
  dword_1800EF708 = v24;
  RtlFreeHeap(v25->ProcessHeap, 0, ValueData);
  v26 = RtlAddAttributeActionToRXact(
          P,
          2u,
          &KeyName,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          &SampVariableAttributeName,
          3u,
          v16,
          ValueDataSize);
  v27 = NtCurrentPeb();
  dword_1800EF708 = v26;
  RtlFreeHeap(v27->ProcessHeap, 0, v16);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Users");
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, v29, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Users\\Names");
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, 0, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Groups");
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, v8, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Groups\\Names");
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, 0, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Aliases");
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, v9, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Aliases\\Names");
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, 0, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Aliases\\Members");
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, 0, 0, 0);
  result = RtlApplyRXactNoFlush(P);
  dword_1800EF708 = result;
  return result;
}

```

## disassembly

```asm
0x1800403cc  push    rbx
0x1800403ce  push    rbp
0x1800403cf  push    rsi
0x1800403d0  push    rdi
0x1800403d1  push    r12
0x1800403d3  push    r13
0x1800403d5  push    r14
0x1800403d7  push    r15
0x1800403d9  sub     rsp, 188h
0x1800403e0  mov     rax, cs:__security_cookie
0x1800403e7  xor     rax, rsp
0x1800403ea  mov     [rsp+1C8h+var_58], rax
0x1800403f2  mov     r13b, dl
0x1800403f5  mov     ebx, ecx
0x1800403f7  xor     edx, edx; Val
0x1800403f9  lea     rcx, [rsp+1C8h+VersionInformation.dwMajorVersion]; void *
0x1800403fe  mov     r8d, 118h; Size
0x180040404  call    memset_0
0x180040409  lea     rcx, [rsp+1C8h+VersionInformation]; lpVersionInformation
0x18004040e  mov     [rsp+1C8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180040416  call    cs:__imp_GetVersionExW
0x18004041c  mov     r8d, 1
0x180040422  cmp     [rsp+1C8h+var_5E], r8b
0x18004042a  jnz     short loc_180040440
0x18004042c  mov     eax, 200h
0x180040431  test    [rsp+1C8h+var_60], ax
0x180040439  jz      short loc_180040440
0x18004043b  mov     edx, r8d
0x18004043e  jmp     short loc_180040442
0x180040440  xor     edx, edx
0x180040442  mov     ecx, ebx
0x180040444  call    ?SetCurrentDomain@@YAXW4_SAMP_DOMAIN_SELECTOR@@@Z; SetCurrentDomain(_SAMP_DOMAIN_SELECTOR)
0x180040449  mov     esi, 2
0x18004044e  test    ebx, ebx
0x180040450  jnz     short loc_18004047F
0x180040452  xor     ebx, ebx
0x180040454  cmp     cs:ProductType, esi
0x18004045a  mov     r12d, ebx
0x18004045d  mov     [rsp+1C8h+var_188], ebx
0x180040461  jnz     short loc_180040468
0x180040463  lea     ebp, [rcx+8]
0x180040466  jmp     short loc_18004046F
0x180040468  neg     edx
0x18004046a  sbb     ebp, ebp
0x18004046c  add     ebp, 4
0x18004046f  lea     r14, qword_1800F07F0
0x180040476  lea     r15, qword_1800F07F8
0x18004047d  jmp     short loc_1800404A4
0x18004047f  xor     ebx, ebx
0x180040481  mov     [rsp+1C8h+var_188], esi
0x180040485  cmp     cs:ProductType, esi
0x18004048b  lea     r14, qword_1800F0810
0x180040492  mov     ebp, ebx
0x180040494  lea     r15, qword_1800F0818
0x18004049b  lea     r12d, [rbx+3]
0x18004049f  jz      short loc_1800404A4
0x1800404a1  mov     r12d, r8d
0x1800404a4  mov     rcx, cs:P; Context
0x1800404ab  call    cs:__imp_RtlStartRXact
0x1800404b1  mov     rdx, cs:qword_1800EF7C8; SourceString
0x1800404b8  lea     rcx, KeyName; DestinationString
0x1800404bf  mov     cs:dword_1800EF708, eax
0x1800404c5  call    cs:__imp_RtlCopyUnicodeString
0x1800404cb  mov     rcx, gs:60h
0x1800404d4  xor     edx, edx; Flags
0x1800404d6  mov     r8d, 170h; Size
0x1800404dc  mov     rcx, [rcx+30h]; HeapHandle
0x1800404e0  call    cs:__imp_RtlAllocateHeap
0x1800404e6  mov     rdi, rax
0x1800404e9  test    rax, rax
0x1800404ec  jnz     short loc_1800404F8
0x1800404ee  mov     cs:dword_1800EF708, 0C000009Ah
0x1800404f8  xor     edx, edx; Val
0x1800404fa  mov     r8d, 170h; Size
0x180040500  mov     rcx, rdi; void *
0x180040503  call    memset_0
0x180040508  mov     eax, cs:dword_1800EF778
0x18004050e  lea     rcx, [rdi+8]; SystemTime
0x180040512  mov     [rdi+5Ch], eax
0x180040515  mov     dword ptr [rdi], 10003h
0x18004051b  mov     dword ptr [rdi+4Ch], 8
0x180040522  mov     dword ptr [rdi+48h], 3E8h
0x180040529  mov     dword ptr [rdi+58h], 1
0x180040530  call    cs:__imp_NtQuerySystemTime
0x180040536  mov     rax, cs:qword_1800CBFA8
0x18004053d  mov     edx, 9A5F4400h
0x180040542  mov     rcx, cs:qword_1800CBFA0
0x180040549  mov     [rdi+18h], rax
0x18004054d  mov     rax, cs:?SampImmediatelyDeltaTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampImmediatelyDeltaTime
0x180040554  mov     [rdi+20h], rax
0x180040558  mov     rax, cs:?SampNeverDeltaTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampNeverDeltaTime
0x18004055f  mov     [rdi+28h], rax
0x180040563  mov     eax, 0FFFFFFFEh
0x180040568  mov     [rdi+34h], eax
0x18004056b  mov     [rdi+3Ch], eax
0x18004056e  mov     [rdi+10h], rcx
0x180040572  mov     [rdi+60h], bl
0x180040575  mov     [rdi+30h], edx
0x180040578  mov     [rdi+38h], edx
0x18004057b  mov     word ptr [rdi+54h], 0Ah
0x180040581  mov     [rdi+40h], rcx
0x180040585  test    r13b, r13b
0x180040588  jz      loc_180040695
0x18004058e  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180040595  movzx   eax, word ptr [rcx+7A6h]
0x18004059c  or      ax, si
0x18004059f  mov     [rdi+66h], ax
0x1800405a3  movups  xmm0, xmmword ptr [rcx+7A8h]
0x1800405aa  movups  xmmword ptr [rdi+68h], xmm0
0x1800405ae  movups  xmm1, xmmword ptr [rcx+7B8h]
0x1800405b5  movups  xmmword ptr [rdi+78h], xmm1
0x1800405b9  movups  xmm0, xmmword ptr [rcx+7C8h]
0x1800405c0  movups  xmmword ptr [rdi+88h], xmm0
0x1800405c7  movups  xmm1, xmmword ptr [rcx+7D8h]
0x1800405ce  movups  xmmword ptr [rdi+98h], xmm1
0x1800405d5  movups  xmm0, xmmword ptr [rcx+7E8h]
0x1800405dc  movups  xmmword ptr [rdi+0A8h], xmm0
0x1800405e3  movups  xmm1, xmmword ptr [rcx+7F8h]
0x1800405ea  movups  xmmword ptr [rdi+0B8h], xmm1
0x1800405f1  movups  xmm0, xmmword ptr [rcx+808h]
0x1800405f8  movups  xmmword ptr [rdi+0C8h], xmm0
0x1800405ff  movups  xmm1, xmmword ptr [rcx+818h]
0x180040606  movups  xmmword ptr [rdi+0D8h], xmm1
0x18004060d  mov     eax, [rcx+8A8h]
0x180040613  mov     [rdi+168h], eax
0x180040619  mov     eax, [rcx+8ACh]
0x18004061f  mov     [rdi+16Ch], eax
0x180040625  movups  xmm0, xmmword ptr [rcx+828h]
0x18004062c  movups  xmmword ptr [rdi+0E8h], xmm0
0x180040633  movups  xmm1, xmmword ptr [rcx+838h]
0x18004063a  movups  xmmword ptr [rdi+0F8h], xmm1
0x180040641  movups  xmm0, xmmword ptr [rcx+848h]
0x180040648  movups  xmmword ptr [rdi+108h], xmm0
0x18004064f  movups  xmm1, xmmword ptr [rcx+858h]
0x180040656  movups  xmmword ptr [rdi+118h], xmm1
0x18004065d  movups  xmm0, xmmword ptr [rcx+868h]
0x180040664  movups  xmmword ptr [rdi+128h], xmm0
0x18004066b  movups  xmm1, xmmword ptr [rcx+878h]
0x180040672  movups  xmmword ptr [rdi+138h], xmm1
0x180040679  movups  xmm0, xmmword ptr [rcx+888h]
0x180040680  movups  xmmword ptr [rdi+148h], xmm0
0x180040687  movups  xmm1, xmmword ptr [rcx+898h]
0x18004068e  movups  xmmword ptr [rdi+158h], xmm1
0x180040695  mov     rcx, cs:qword_1800EF7C0; Sid
0x18004069c  call    cs:__imp_RtlLengthSid
0x1800406a2  mov     ecx, [r14]
0x1800406a5  mov     edx, 0FFFFFFFCh
0x1800406aa  add     eax, 3
0x1800406ad  add     ecx, 3
0x1800406b0  and     ecx, edx
0x1800406b2  and     eax, edx
0x1800406b4  add     eax, 30h ; '0'
0x1800406b7  xor     edx, edx; Flags
0x1800406b9  add     eax, ecx
0x1800406bb  mov     rcx, gs:60h
0x1800406c4  mov     r8d, eax; Size
0x1800406c7  mov     [rsp+1C8h+var_184], eax
0x1800406cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800406cf  call    cs:__imp_RtlAllocateHeap
0x1800406d5  mov     r13, rax
0x1800406d8  test    rax, rax
0x1800406db  jnz     short loc_1800406E7
0x1800406dd  mov     cs:dword_1800EF708, 0C000009Ah
0x1800406e7  mov     [rax], ebx
0x1800406e9  mov     ecx, [r14]
0x1800406ec  mov     [rax+4], ecx
0x1800406ef  mov     dword ptr [rax+8], 10003h
0x1800406f6  mov     ecx, [r14]
0x1800406f9  add     ecx, 3
0x1800406fc  and     ecx, 0FFFFFFFCh
0x1800406ff  mov     [rax+0Ch], ecx
0x180040702  mov     rcx, cs:qword_1800EF7C0; Sid
0x180040709  call    cs:__imp_RtlLengthSid
0x18004070f  mov     rcx, cs:qword_1800EF7C0; Sid
0x180040716  mov     [r13+10h], eax
0x18004071a  mov     [r13+14h], ebx
0x18004071e  call    cs:__imp_RtlLengthSid
0x180040724  mov     ecx, [r14]
0x180040727  add     eax, 3
0x18004072a  add     ecx, 3
0x18004072d  mov     qword ptr [r13+1Ch], 0
0x180040735  and     ecx, 0FFFFFFFCh
0x180040738  and     eax, 0FFFFFFFCh
0x18004073b  add     ecx, eax
0x18004073d  mov     [r13+18h], ecx
0x180040741  mov     rcx, cs:qword_1800EF7C0; Sid
0x180040748  call    cs:__imp_RtlLengthSid
0x18004074e  mov     ecx, [r14]
0x180040751  lea     rbx, [r13+30h]
0x180040755  add     ecx, 3
0x180040758  mov     qword ptr [r13+28h], 0
0x180040760  and     ecx, 0FFFFFFFCh
0x180040763  add     eax, 3
0x180040766  and     eax, 0FFFFFFFCh
0x180040769  add     ecx, eax
0x18004076b  mov     [r13+24h], ecx
0x18004076f  mov     rcx, rbx; void *
0x180040772  mov     r8d, [r14]; Size
0x180040775  mov     rdx, [r15]; Src
0x180040778  call    memcpy_0
0x18004077d  mov     rcx, cs:qword_1800EF7C0; Sid
0x180040784  call    cs:__imp_RtlLengthSid
0x18004078a  mov     ecx, [r14]
0x18004078d  mov     r14d, 3
0x180040793  mov     rdx, cs:qword_1800EF7C0; Src
0x18004079a  add     ecx, r14d
0x18004079d  mov     r8d, eax; Size
0x1800407a0  mov     eax, 0FFFFFFFCh
0x1800407a5  and     rcx, rax
0x1800407a8  add     rcx, rbx; void *
0x1800407ab  call    memcpy_0
0x1800407b0  mov     rcx, cs:P; Context
0x1800407b7  lea     rax, ?SampFixedAttributeName@@3U_UNICODE_STRING@@A; _UNICODE_STRING SampFixedAttributeName
0x1800407be  mov     [rsp+1C8h+ValueDataSize], 170h; ValueDataSize
0x1800407c6  lea     r15, KeyName
0x1800407cd  mov     [rsp+1C8h+ValueData], rdi; ValueData
0x1800407d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800407d6  mov     [rsp+1C8h+ValueType], r14d; ValueType
0x1800407db  mov     r9, rbx; KeyHandle
0x1800407de  mov     r8, r15; KeyName
0x1800407e1  mov     [rsp+1C8h+ValueName], rax; ValueName
0x1800407e6  mov     edx, esi; ActionType
0x1800407e8  call    cs:__imp_RtlAddAttributeActionToRXact
0x1800407ee  mov     rcx, gs:60h
0x1800407f7  mov     r8, rdi; P
0x1800407fa  xor     edx, edx; Flags
0x1800407fc  mov     cs:dword_1800EF708, eax
0x180040802  mov     rcx, [rcx+30h]; HeapHandle
0x180040806  call    cs:__imp_RtlFreeHeap
0x18004080c  mov     eax, [rsp+1C8h+var_184]
0x180040810  mov     r9, rbx; KeyHandle
0x180040813  mov     rcx, cs:P; Context
0x18004081a  mov     r8, r15; KeyName
0x18004081d  mov     [rsp+1C8h+ValueDataSize], eax; ValueDataSize
0x180040821  mov     edx, esi; ActionType
0x180040823  mov     [rsp+1C8h+ValueData], r13; ValueData
0x180040828  lea     rax, ?SampVariableAttributeName@@3U_UNICODE_STRING@@A; _UNICODE_STRING SampVariableAttributeName
0x18004082f  mov     [rsp+1C8h+ValueType], r14d; ValueType
0x180040834  mov     [rsp+1C8h+ValueName], rax; ValueName
0x180040839  call    cs:__imp_RtlAddAttributeActionToRXact
0x18004083f  mov     rcx, gs:60h
0x180040848  mov     r8, r13; P
0x18004084b  mov     cs:dword_1800EF708, eax
0x180040851  xor     edx, edx; Flags
0x180040853  mov     rcx, [rcx+30h]; HeapHandle
0x180040857  call    cs:__imp_RtlFreeHeap
0x18004085d  mov     rdx, cs:qword_1800EF7C8; SourceString
0x180040864  mov     rcx, r15; DestinationString
0x180040867  call    cs:__imp_RtlCopyUnicodeString
0x18004086d  lea     rdx, aUsers; "\\Users"
0x180040874  mov     rcx, r15; Destination
0x180040877  call    cs:__imp_RtlAppendUnicodeToString
0x18004087d  mov     r9d, [rsp+1C8h+var_188]; ValueType
0x180040882  xor     ebx, ebx
0x180040884  mov     rcx, cs:P; Context
0x18004088b  mov     r8, r15; KeyName
0x18004088e  mov     [rsp+1C8h+ValueType], ebx; ValueDataSize
0x180040892  mov     edx, esi; ActionType
0x180040894  mov     [rsp+1C8h+ValueName], rbx; ValueData
0x180040899  mov     cs:dword_1800EF708, eax
0x18004089f  call    cs:__imp_RtlAddActionToRXact
0x1800408a5  mov     rdx, cs:qword_1800EF7C8; SourceString
0x1800408ac  mov     rcx, r15; DestinationString
0x1800408af  mov     cs:dword_1800EF708, eax
0x1800408b5  call    cs:__imp_RtlCopyUnicodeString
0x1800408bb  lea     rdx, aUsersNames; "\\Users\\Names"
0x1800408c2  mov     rcx, r15; Destination
0x1800408c5  call    cs:__imp_RtlAppendUnicodeToString
0x1800408cb  mov     rcx, cs:P; Context
0x1800408d2  xor     r9d, r9d; ValueType
0x1800408d5  mov     r8, r15; KeyName
0x1800408d8  mov     [rsp+1C8h+ValueType], ebx; ValueDataSize
0x1800408dc  mov     edx, esi; ActionType
0x1800408de  mov     cs:dword_1800EF708, eax
0x1800408e4  mov     [rsp+1C8h+ValueName], rbx; ValueData
0x1800408e9  call    cs:__imp_RtlAddActionToRXact
0x1800408ef  mov     rdx, cs:qword_1800EF7C8; SourceString
0x1800408f6  mov     rcx, r15; DestinationString
0x1800408f9  mov     cs:dword_1800EF708, eax
0x1800408ff  call    cs:__imp_RtlCopyUnicodeString
0x180040905  lea     rdx, aGroups_0; "\\Groups"
0x18004090c  mov     rcx, r15; Destination
0x18004090f  call    cs:__imp_RtlAppendUnicodeToString
0x180040915  mov     rcx, cs:P; Context
0x18004091c  mov     r9d, r12d; ValueType
0x18004091f  mov     r8, r15; KeyName
0x180040922  mov     [rsp+1C8h+ValueType], ebx; ValueDataSize
0x180040926  mov     edx, esi; ActionType
0x180040928  mov     cs:dword_1800EF708, eax
0x18004092e  mov     [rsp+1C8h+ValueName], rbx; ValueData
0x180040933  call    cs:__imp_RtlAddActionToRXact
0x180040939  mov     rdx, cs:qword_1800EF7C8; SourceString
0x180040940  mov     rcx, r15; DestinationString
0x180040943  mov     cs:dword_1800EF708, eax
0x180040949  call    cs:__imp_RtlCopyUnicodeString
0x18004094f  lea     rdx, aGroupsNames_0; "\\Groups\\Names"
0x180040956  mov     rcx, r15; Destination
0x180040959  call    cs:__imp_RtlAppendUnicodeToString
0x18004095f  mov     rcx, cs:P; Context
0x180040966  xor     r9d, r9d; ValueType
  ... truncated ...
```
