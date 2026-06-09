# CreateUser(_UNICODE_STRING *,_UNICODE_STRING *,uchar,ulong,ulong,uchar,ulong,ulong,uchar)

- ea: `0x18003ec6c`
- end: `0x18003f34e`
- name: `?CreateUser@@YAJPEAU_UNICODE_STRING@@0EKKEKKE@Z`
- size: `1762`
- prototype: `NTSTATUS __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, __int64, ULONG, unsigned int, unsigned __int8, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003d938`

## callees

- `0x180020610`
- `0x18003ec6c`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlApplyRXactNoFlush` at `0x18003f327`
- `ntdll!RtlApplyRXactNoFlush` at `0x18003f327`
- `ntdll!RtlStartRXact` at `0x18003ecd0`
- `ntdll!RtlStartRXact` at `0x18003ecd0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003ed10`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003ed10`
- `ntdll!RtlAppendUnicodeToString` at `0x18003ecfd`
- `ntdll!RtlAppendUnicodeToString` at `0x18003ed61`
- `ntdll!RtlAppendUnicodeToString` at `0x18003ecfd`
- `ntdll!RtlAppendUnicodeToString` at `0x18003ed61`
- `ntdll!RtlFreeHeap` at `0x18003f268`
- `ntdll!RtlFreeHeap` at `0x18003f2b8`
- `ntdll!RtlFreeHeap` at `0x18003f268`
- `ntdll!RtlFreeHeap` at `0x18003f2b8`
- `ntdll!RtlAllocateHeap` at `0x18003edfb`
- `ntdll!RtlAllocateHeap` at `0x18003eed3`
- `ntdll!RtlAllocateHeap` at `0x18003edfb`
- `ntdll!RtlAllocateHeap` at `0x18003eed3`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003f24a`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003f29a`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003f314`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003f24a`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003f29a`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003f314`
- `ntdll!RtlCopyUnicodeString` at `0x18003eced`
- `ntdll!RtlCopyUnicodeString` at `0x18003ed51`
- `ntdll!RtlCopyUnicodeString` at `0x18003eced`
- `ntdll!RtlCopyUnicodeString` at `0x18003ed51`
- `ntdll!RtlAddActionToRXact` at `0x18003ed3b`
- `ntdll!RtlAddActionToRXact` at `0x18003ed3b`
- `ntdll!RtlInitUnicodeString` at `0x18003f2d9`
- `ntdll!RtlInitUnicodeString` at `0x18003f2d9`

## pseudocode

```c
NTSTATUS __fastcall CreateUser(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        ULONG a4,
        unsigned int a5,
        unsigned __int8 a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int8 a9)
{
  UNICODE_STRING v9; // xmm1
  PWSTR Buffer; // rcx
  __int16 v11; // r14
  size_t Length; // r13
  __int64 v13; // r15
  unsigned int v15; // edx
  unsigned int v16; // r8d
  int v17; // eax
  enum _NT_PRODUCT_TYPE v18; // ecx
  unsigned int v19; // esi
  __int64 v20; // rax
  __int64 v21; // rax
  char *Heap; // rax
  void *v23; // rdi
  int v24; // r12d
  unsigned int v25; // ecx
  _DWORD *v26; // rax
  _DWORD *v27; // r14
  int v28; // ecx
  int v29; // eax
  int v30; // ecx
  int v31; // eax
  int v32; // ecx
  unsigned int v33; // eax
  int v34; // ecx
  unsigned int v35; // eax
  int v36; // ecx
  unsigned int v37; // eax
  int v38; // ecx
  unsigned int v39; // eax
  unsigned int v40; // ecx
  unsigned int v41; // eax
  int v42; // eax
  unsigned int v43; // ecx
  int v44; // eax
  unsigned int v45; // ecx
  int v46; // eax
  unsigned int v47; // ecx
  int v48; // r8d
  unsigned int v49; // ecx
  int v50; // eax
  int v51; // eax
  int v52; // ecx
  int v53; // eax
  int v54; // ecx
  int v55; // eax
  int v56; // ecx
  int v57; // ecx
  int v58; // eax
  NTSTATUS v59; // eax
  struct _PEB *v60; // rcx
  NTSTATUS v61; // eax
  struct _PEB *v62; // rcx
  NTSTATUS result; // eax
  UNICODE_STRING Source; // [rsp+40h] [rbp-49h] BYREF
  ULONG v65; // [rsp+50h] [rbp-39h] BYREF
  int v66; // [rsp+58h] [rbp-31h] BYREF
  _DWORD v67[3]; // [rsp+5Ch] [rbp-2Dh]
  __int64 v68; // [rsp+68h] [rbp-21h]
  void *Src; // [rsp+70h] [rbp-19h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-11h] BYREF

  v9 = *a1;
  Buffer = a2->Buffer;
  v11 = 1;
  Length = a2->Length;
  v13 = 32LL * a8;
  DestinationString = 0;
  Src = Buffer;
  Source = v9;
  if ( *((_BYTE *)&Size + v13 + 24) == 1 )
    **(_DWORD **)((char *)&Size + v13 + 16) = a4;
  dword_1800EF708 = RtlStartRXact(P);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Users\\Names\\");
  dword_1800EF708 = RtlAppendUnicodeStringToString(&KeyName, &Source);
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, a4, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Users\\");
  v17 = SampRtlConvertUlongToUnicodeString(a4, v15, v16, 0, &KeyName);
  v18 = ProductType;
  dword_1800EF708 = v17;
  if ( a4 == 501 )
  {
    v19 = 0;
    if ( ProductType == NtProductLanManNt )
    {
LABEL_7:
      v20 = v19++;
      v67[2 * v20 - 1] = 514;
      v67[2 * v20] = 7;
      goto LABEL_8;
    }
  }
  v66 = 513;
  v19 = 1;
  v67[0] = 7;
  if ( a4 == 501 )
  {
    if ( ProductType != NtProductLanManNt )
      goto LABEL_11;
    goto LABEL_7;
  }
LABEL_8:
  if ( a4 == 500 && v18 == NtProductLanManNt )
  {
    v21 = v19++;
    v67[2 * v21 - 1] = 512;
    v67[2 * v21] = 7;
    goto LABEL_12;
  }
LABEL_11:
  v11 = 0;
LABEL_12:
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x50u);
  v23 = Heap;
  if ( !Heap )
    dword_1800EF708 = -1073741670;
  *(_QWORD *)(Heap + 60) = 0;
  *(_DWORD *)(Heap + 70) = 0;
  *(_QWORD *)Heap = 65539;
  v24 = Length + 3;
  *((_WORD *)Heap + 34) = a6 != 0 ? v11 + 1 : 0;
  *((_DWORD *)Heap + 14) = a7;
  *((_DWORD *)Heap + 13) = a5;
  *((_DWORD *)Heap + 12) = a4;
  *((union _LARGE_INTEGER *)Heap + 1) = SampHasNeverTime;
  *((union _LARGE_INTEGER *)Heap + 2) = SampHasNeverTime;
  *((union _LARGE_INTEGER *)Heap + 3) = SampHasNeverTime;
  *((union _LARGE_INTEGER *)Heap + 4) = SampWillNeverTime;
  *((union _LARGE_INTEGER *)Heap + 5) = SampHasNeverTime;
  v25 = (*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC;
  v68 = 8 * v19 + 3;
  v65 = ((Source.Length + 3) & 0xFFFFFFFC) + 8 * v19 + v25 + ((Length + 3) & 0xFFFFFFFC) + 204;
  v26 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v65);
  v27 = v26;
  if ( !v26 )
    dword_1800EF708 = -1073741670;
  *v26 = 0;
  v26[1] = *(_DWORD *)((char *)&Size + v13);
  v26[2] = 65539;
  v26[3] = (*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC;
  v26[4] = Source.Length;
  v26[5] = 0;
  v28 = Source.Length + 3;
  v29 = *(_DWORD *)((char *)&Size + v13) + 3;
  *(_QWORD *)(v27 + 7) = 0;
  v27[6] = (v29 & 0xFFFFFFFC) + (v28 & 0xFFFFFFFC);
  v30 = Source.Length + 3;
  v31 = *(_DWORD *)((char *)&Size + v13) + 3;
  v27[10] = Length;
  v27[11] = 0;
  v27[9] = (v31 & 0xFFFFFFFC) + (v30 & 0xFFFFFFFC);
  v32 = *(_DWORD *)((char *)&Size + v13);
  v33 = (Source.Length + 3) & 0xFFFFFFFC;
  *(_QWORD *)(v27 + 13) = 0;
  v27[12] = (v24 & 0xFFFFFFFC) + v33 + ((v32 + 3) & 0xFFFFFFFC);
  v34 = *(_DWORD *)((char *)&Size + v13);
  v35 = (Source.Length + 3) & 0xFFFFFFFC;
  *((_QWORD *)v27 + 8) = 0;
  v27[15] = (v24 & 0xFFFFFFFC) + v35 + ((v34 + 3) & 0xFFFFFFFC);
  v36 = *(_DWORD *)((char *)&Size + v13);
  v37 = (Source.Length + 3) & 0xFFFFFFFC;
  *(_QWORD *)(v27 + 19) = 0;
  v27[18] = (v24 & 0xFFFFFFFC) + v37 + ((v36 + 3) & 0xFFFFFFFC);
  v38 = *(_DWORD *)((char *)&Size + v13);
  v39 = (Source.Length + 3) & 0xFFFFFFFC;
  *((_QWORD *)v27 + 11) = 0;
  v27[21] = (v24 & 0xFFFFFFFC) + v39 + ((v38 + 3) & 0xFFFFFFFC);
  v40 = (*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC;
  v41 = (v24 & 0xFFFFFFFC) + ((Source.Length + 3) & 0xFFFFFFFC);
  *(_QWORD *)(v27 + 25) = 0;
  v27[24] = v41 + v40;
  v42 = Source.Length;
  v43 = (*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC;
  *((_QWORD *)v27 + 14) = 0;
  v27[27] = (v24 & 0xFFFFFFFC) + ((v42 + 3) & 0xFFFFFFFC) + v43;
  v44 = Source.Length;
  v45 = (*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC;
  *(_QWORD *)(v27 + 31) = 0;
  v27[30] = (v24 & 0xFFFFFFFC) + ((v44 + 3) & 0xFFFFFFFC) + v45;
  v46 = Source.Length;
  v47 = (*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC;
  *((_QWORD *)v27 + 17) = 0;
  v27[33] = (v24 & 0xFFFFFFFC) + ((v46 + 3) & 0xFFFFFFFC) + v47;
  v48 = v68;
  v49 = (*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC;
  v50 = Source.Length + 3;
  v27[37] = 8 * v19;
  v27[38] = v19;
  v48 &= 0xFFFFFFFC;
  v27[36] = (v24 & 0xFFFFFFFC) + (v50 & 0xFFFFFFFC) + v49;
  v51 = Source.Length + 3;
  v52 = *(_DWORD *)((char *)&Size + v13) + 3;
  *((_QWORD *)v27 + 20) = 0;
  v27[39] = (v24 & 0xFFFFFFFC) + v48 + (v51 & 0xFFFFFFFC) + (v52 & 0xFFFFFFFC);
  v53 = Source.Length + 3;
  v54 = *(_DWORD *)((char *)&Size + v13) + 3;
  *(_QWORD *)(v27 + 43) = 0;
  v27[42] = (v24 & 0xFFFFFFFC) + v48 + (v53 & 0xFFFFFFFC) + (v54 & 0xFFFFFFFC);
  v55 = Source.Length + 3;
  v56 = *(_DWORD *)((char *)&Size + v13) + 3;
  *((_QWORD *)v27 + 23) = 0;
  v27[45] = (v24 & 0xFFFFFFFC) + v48 + (v55 & 0xFFFFFFFC) + (v56 & 0xFFFFFFFC);
  v57 = *(_DWORD *)((char *)&Size + v13) + 3;
  v58 = Source.Length + 3;
  *(_QWORD *)(v27 + 49) = 0;
  v27[48] = (v24 & 0xFFFFFFFC) + v48 + (v58 & 0xFFFFFFFC) + (v57 & 0xFFFFFFFC);
  memcpy_0(v27 + 51, *(const void **)((char *)&Size + v13 + 8), *(unsigned int *)((char *)&Size + v13));
  memcpy_0((char *)v27 + ((*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC) + 204, Source.Buffer, Source.Length);
  memcpy_0(
    (char *)v27 + ((Source.Length + 3) & 0xFFFFFFFC) + ((*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC) + 204,
    Src,
    Length);
  memcpy_0(
    (char *)v27
  + ((*(_DWORD *)((char *)&Size + v13) + 3) & 0xFFFFFFFC)
  + ((Source.Length + 3) & 0xFFFFFFFC)
  + (v24 & 0xFFFFFFFC)
  + 204,
    &v66,
    8LL * v19);
  v59 = RtlAddAttributeActionToRXact(
          P,
          2u,
          &KeyName,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          &SampFixedAttributeName,
          3u,
          v23,
          0x50u);
  v60 = NtCurrentPeb();
  dword_1800EF708 = v59;
  RtlFreeHeap(v60->ProcessHeap, 0, v23);
  v61 = RtlAddAttributeActionToRXact(
          P,
          2u,
          &KeyName,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          &SampVariableAttributeName,
          3u,
          v27,
          v65);
  v62 = NtCurrentPeb();
  dword_1800EF708 = v61;
  RtlFreeHeap(v62->ProcessHeap, 0, v27);
  if ( !a9 )
  {
    v65 = 0;
    RtlInitUnicodeString(&DestinationString, L"UserDontShowInLogonUI");
    v65 = 1;
    dword_1800EF708 = RtlAddAttributeActionToRXact(
                        P,
                        2u,
                        &KeyName,
                        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                        &DestinationString,
                        3u,
                        &v65,
                        4u);
  }
  result = RtlApplyRXactNoFlush(P);
  dword_1800EF708 = result;
  return result;
}

```

## disassembly

```asm
0x18003ec6c  mov     [rsp-8+arg_10], rbx
0x18003ec71  push    rbp
0x18003ec72  push    rsi
0x18003ec73  push    rdi
0x18003ec74  push    r12
0x18003ec76  push    r13
0x18003ec78  push    r14
0x18003ec7a  push    r15
0x18003ec7c  lea     rbp, [rsp-7]
0x18003ec81  sub     rsp, 90h
0x18003ec88  movups  xmm1, xmmword ptr [rcx]
0x18003ec8b  mov     r15d, [rbp+37h+arg_38]
0x18003ec8f  lea     rax, Size
0x18003ec96  mov     rcx, [rdx+8]
0x18003ec9a  mov     r14d, 1
0x18003eca0  movzx   r13d, word ptr [rdx]
0x18003eca4  xorps   xmm0, xmm0
0x18003eca7  shl     r15, 5
0x18003ecab  mov     ebx, r9d
0x18003ecae  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18003ecb2  mov     [rbp+37h+Src], rcx
0x18003ecb6  movdqu  xmmword ptr [rbp+37h+Source.Length], xmm1
0x18003ecbb  cmp     [r15+rax+18h], r14b
0x18003ecc0  jnz     short loc_18003ECC9
0x18003ecc2  mov     rax, [r15+rax+10h]
0x18003ecc7  mov     [rax], ebx
0x18003ecc9  mov     rcx, cs:P; Context
0x18003ecd0  call    cs:__imp_RtlStartRXact
0x18003ecd6  mov     rdx, cs:qword_1800EF7C8; SourceString
0x18003ecdd  lea     rdi, KeyName
0x18003ece4  mov     rcx, rdi; DestinationString
0x18003ece7  mov     cs:dword_1800EF708, eax
0x18003eced  call    cs:__imp_RtlCopyUnicodeString
0x18003ecf3  lea     rdx, aUsersNames_0; "\\Users\\Names\\"
0x18003ecfa  mov     rcx, rdi; Destination
0x18003ecfd  call    cs:__imp_RtlAppendUnicodeToString
0x18003ed03  lea     rdx, [rbp+37h+Source]; Source
0x18003ed07  mov     rcx, rdi; Destination
0x18003ed0a  mov     cs:dword_1800EF708, eax
0x18003ed10  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003ed16  mov     rcx, cs:P; Context
0x18003ed1d  xor     r12d, r12d
0x18003ed20  mov     [rsp+0C0h+ValueDataSize], r12d; ValueDataSize
0x18003ed25  mov     r9d, ebx; ValueType
0x18003ed28  mov     r8, rdi; KeyName
0x18003ed2b  mov     cs:dword_1800EF708, eax
0x18003ed31  mov     [rsp+0C0h+ValueData], r12; ValueData
0x18003ed36  lea     edx, [r12+2]; ActionType
0x18003ed3b  call    cs:__imp_RtlAddActionToRXact
0x18003ed41  mov     rdx, cs:qword_1800EF7C8; SourceString
0x18003ed48  mov     rcx, rdi; DestinationString
0x18003ed4b  mov     cs:dword_1800EF708, eax
0x18003ed51  call    cs:__imp_RtlCopyUnicodeString
0x18003ed57  lea     rdx, aUsers_1; "\\Users\\"
0x18003ed5e  mov     rcx, rdi; Destination
0x18003ed61  call    cs:__imp_RtlAppendUnicodeToString
0x18003ed67  xor     r9d, r9d; unsigned __int8
0x18003ed6a  mov     [rsp+0C0h+ValueData], rdi; struct _UNICODE_STRING *
0x18003ed6f  mov     ecx, ebx; Value
0x18003ed71  mov     cs:dword_1800EF708, eax
0x18003ed77  call    ?SampRtlConvertUlongToUnicodeString@@YAJKKKEPEAU_UNICODE_STRING@@@Z; SampRtlConvertUlongToUnicodeString(ulong,ulong,ulong,uchar,_UNICODE_STRING *)
0x18003ed7c  mov     ecx, cs:ProductType
0x18003ed82  lea     edx, [r12+7]
0x18003ed87  mov     cs:dword_1800EF708, eax
0x18003ed8d  mov     eax, 1F5h
0x18003ed92  cmp     ebx, eax
0x18003ed94  jnz     short loc_18003ED9E
0x18003ed96  mov     esi, r12d
0x18003ed99  cmp     ecx, 2
0x18003ed9c  jz      short loc_18003EDB4
0x18003ed9e  mov     [rbp+37h+var_68], 201h
0x18003eda5  mov     esi, r14d
0x18003eda8  mov     [rbp+37h+var_64], edx
0x18003edab  cmp     ebx, eax
0x18003edad  jnz     short loc_18003EDC5
0x18003edaf  cmp     ecx, 2
0x18003edb2  jnz     short loc_18003EDE5
0x18003edb4  mov     eax, esi
0x18003edb6  add     esi, r14d
0x18003edb9  mov     [rbp+rax*8+37h+var_68], 202h
0x18003edc1  mov     [rbp+rax*8+37h+var_64], edx
0x18003edc5  cmp     ebx, 1F4h
0x18003edcb  jnz     short loc_18003EDE5
0x18003edcd  cmp     ecx, 2
0x18003edd0  jnz     short loc_18003EDE5
0x18003edd2  mov     eax, esi
0x18003edd4  add     esi, r14d
0x18003edd7  mov     [rbp+rax*8+37h+var_68], 200h
0x18003eddf  mov     [rbp+rax*8+37h+var_64], edx
0x18003ede3  jmp     short loc_18003EDE8
0x18003ede5  mov     r14d, r12d
0x18003ede8  mov     rcx, gs:60h
0x18003edf1  xor     edx, edx; Flags
0x18003edf3  mov     rcx, [rcx+30h]; HeapHandle
0x18003edf7  lea     r8d, [rdx+50h]; Size
0x18003edfb  call    cs:__imp_RtlAllocateHeap
0x18003ee01  mov     rdi, rax
0x18003ee04  test    rax, rax
0x18003ee07  jnz     short loc_18003EE13
0x18003ee09  mov     cs:dword_1800EF708, 0C000009Ah
0x18003ee13  mov     [rax+3Ch], r12
0x18003ee17  lea     rcx, Size
0x18003ee1e  mov     [rax+46h], r12d
0x18003ee22  mov     r8d, 0FFFFFFFCh
0x18003ee28  mov     qword ptr [rax], 10003h
0x18003ee2f  lea     r12d, [r13+3]
0x18003ee33  inc     r14w
0x18003ee37  neg     [rbp+37h+arg_28]
0x18003ee3a  sbb     ax, ax
0x18003ee3d  and     ax, r14w
0x18003ee41  mov     [rdi+44h], ax
0x18003ee45  mov     eax, [rbp+37h+arg_30]
0x18003ee48  mov     [rdi+38h], eax
0x18003ee4b  mov     eax, [rbp+37h+arg_20]
0x18003ee4e  mov     [rdi+34h], eax
0x18003ee51  mov     [rdi+30h], ebx
0x18003ee54  lea     ebx, ds:0[rsi*8]
0x18003ee5b  mov     rax, cs:?SampHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampHasNeverTime
0x18003ee62  mov     [rdi+8], rax
0x18003ee66  mov     rax, cs:?SampHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampHasNeverTime
0x18003ee6d  mov     [rdi+10h], rax
0x18003ee71  mov     rax, cs:?SampHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampHasNeverTime
0x18003ee78  mov     [rdi+18h], rax
0x18003ee7c  mov     rax, cs:?SampWillNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampWillNeverTime
0x18003ee83  mov     [rdi+20h], rax
0x18003ee87  mov     rax, cs:?SampHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampHasNeverTime
0x18003ee8e  mov     [rdi+28h], rax
0x18003ee92  lea     eax, [rbx+3]
0x18003ee95  mov     ecx, [r15+rcx]
0x18003ee99  movzx   edx, [rbp+37h+Source.Length]
0x18003ee9d  add     ecx, 3
0x18003eea0  and     ecx, r8d
0x18003eea3  mov     [rbp+37h+var_58], rax
0x18003eea7  add     ecx, ebx
0x18003eea9  add     edx, 3
0x18003eeac  and     edx, r8d
0x18003eeaf  mov     eax, r12d
0x18003eeb2  add     ecx, edx
0x18003eeb4  and     eax, r8d
0x18003eeb7  add     eax, 0CCh
0x18003eebc  xor     edx, edx; Flags
0x18003eebe  add     eax, ecx
0x18003eec0  mov     rcx, gs:60h
0x18003eec9  mov     r8d, eax; Size
0x18003eecc  mov     [rbp+37h+var_70], eax
0x18003eecf  mov     rcx, [rcx+30h]; HeapHandle
0x18003eed3  call    cs:__imp_RtlAllocateHeap
0x18003eed9  xor     r10d, r10d
0x18003eedc  mov     r14, rax
0x18003eedf  test    rax, rax
0x18003eee2  jnz     short loc_18003EEEE
0x18003eee4  mov     cs:dword_1800EF708, 0C000009Ah
0x18003eeee  mov     [rax], r10d
0x18003eef1  lea     r8, Size
0x18003eef8  mov     ecx, [r15+r8]
0x18003eefc  mov     r11d, 3
0x18003ef02  mov     [rax+4], ecx
0x18003ef05  mov     edx, r12d
0x18003ef08  mov     dword ptr [rax+8], 10003h
0x18003ef0f  mov     ecx, [r15+r8]
0x18003ef13  add     ecx, r11d
0x18003ef16  lea     r9d, [r11-7]
0x18003ef1a  and     ecx, r9d
0x18003ef1d  and     edx, r9d
0x18003ef20  mov     [rax+0Ch], ecx
0x18003ef23  movzx   eax, [rbp+37h+Source.Length]
0x18003ef27  mov     [r14+10h], eax
0x18003ef2b  mov     [r14+14h], r10d
0x18003ef2f  movzx   ecx, [rbp+37h+Source.Length]
0x18003ef33  mov     eax, [r15+r8]
0x18003ef37  add     ecx, r11d
0x18003ef3a  add     eax, r11d
0x18003ef3d  mov     [r14+1Ch], r10
0x18003ef41  and     ecx, r9d
0x18003ef44  and     eax, r9d
0x18003ef47  add     ecx, eax
0x18003ef49  mov     [r14+18h], ecx
0x18003ef4d  movzx   ecx, [rbp+37h+Source.Length]
0x18003ef51  mov     eax, [r15+r8]
0x18003ef55  add     ecx, r11d
0x18003ef58  add     eax, r11d
0x18003ef5b  mov     [r14+28h], r13d
0x18003ef5f  and     eax, r9d
0x18003ef62  mov     [r14+2Ch], r10d
0x18003ef66  and     ecx, r9d
0x18003ef69  add     ecx, eax
0x18003ef6b  mov     [r14+24h], ecx
0x18003ef6f  movzx   eax, [rbp+37h+Source.Length]
0x18003ef73  mov     ecx, [r15+r8]
0x18003ef77  add     eax, r11d
0x18003ef7a  and     eax, r9d
0x18003ef7d  mov     [r14+34h], r10
0x18003ef81  add     ecx, r11d
0x18003ef84  add     eax, edx
0x18003ef86  and     ecx, r9d
0x18003ef89  add     ecx, eax
0x18003ef8b  mov     [r14+30h], ecx
0x18003ef8f  movzx   eax, [rbp+37h+Source.Length]
0x18003ef93  mov     ecx, [r15+r8]
0x18003ef97  add     eax, r11d
0x18003ef9a  and     eax, r9d
0x18003ef9d  mov     [r14+40h], r10
0x18003efa1  add     ecx, r11d
0x18003efa4  add     eax, edx
0x18003efa6  and     ecx, r9d
0x18003efa9  add     ecx, eax
0x18003efab  mov     [r14+3Ch], ecx
0x18003efaf  movzx   eax, [rbp+37h+Source.Length]
0x18003efb3  mov     ecx, [r15+r8]
0x18003efb7  add     eax, r11d
0x18003efba  and     eax, r9d
0x18003efbd  mov     [r14+4Ch], r10
0x18003efc1  add     ecx, r11d
0x18003efc4  add     eax, edx
0x18003efc6  and     ecx, r9d
0x18003efc9  add     ecx, eax
0x18003efcb  mov     [r14+48h], ecx
0x18003efcf  movzx   eax, [rbp+37h+Source.Length]
0x18003efd3  mov     ecx, [r15+r8]
0x18003efd7  add     eax, r11d
0x18003efda  and     eax, r9d
0x18003efdd  mov     [r14+58h], r10
0x18003efe1  add     ecx, r11d
0x18003efe4  add     eax, edx
0x18003efe6  and     ecx, r9d
0x18003efe9  add     ecx, eax
0x18003efeb  mov     [r14+54h], ecx
0x18003efef  movzx   eax, [rbp+37h+Source.Length]
0x18003eff3  mov     ecx, [r15+r8]
0x18003eff7  add     eax, r11d
0x18003effa  and     eax, r9d
0x18003effd  add     ecx, r11d
0x18003f000  and     ecx, r9d
0x18003f003  add     eax, edx
0x18003f005  mov     [r14+64h], r10
0x18003f009  add     ecx, eax
0x18003f00b  mov     [r14+60h], ecx
0x18003f00f  mov     ecx, [r15+r8]
0x18003f013  movzx   eax, [rbp+37h+Source.Length]
0x18003f017  add     ecx, r11d
0x18003f01a  and     ecx, r9d
0x18003f01d  mov     [r14+70h], r10
0x18003f021  add     eax, r11d
0x18003f024  and     eax, r9d
0x18003f027  add     eax, edx
0x18003f029  add     ecx, eax
0x18003f02b  mov     [r14+6Ch], ecx
0x18003f02f  mov     ecx, [r15+r8]
0x18003f033  movzx   eax, [rbp+37h+Source.Length]
0x18003f037  add     ecx, r11d
0x18003f03a  and     ecx, r9d
0x18003f03d  mov     [r14+7Ch], r10
0x18003f041  add     eax, r11d
0x18003f044  and     eax, r9d
0x18003f047  add     eax, edx
0x18003f049  add     ecx, eax
0x18003f04b  mov     [r14+78h], ecx
0x18003f04f  mov     ecx, [r15+r8]
0x18003f053  movzx   eax, [rbp+37h+Source.Length]
0x18003f057  add     ecx, r11d
0x18003f05a  and     ecx, r9d
0x18003f05d  mov     [r14+88h], r10
0x18003f064  add     eax, r11d
0x18003f067  and     eax, r9d
0x18003f06a  add     eax, edx
0x18003f06c  add     ecx, eax
0x18003f06e  mov     [r14+84h], ecx
0x18003f075  mov     ecx, [r15+r8]
0x18003f079  movzx   eax, [rbp+37h+Source.Length]
0x18003f07d  add     ecx, r11d
0x18003f080  mov     r8, [rbp+37h+var_58]
0x18003f084  and     ecx, r9d
0x18003f087  add     eax, r11d
0x18003f08a  mov     [r14+94h], ebx
0x18003f091  and     eax, r9d
0x18003f094  mov     [r14+98h], esi
0x18003f09b  add     eax, edx
0x18003f09d  lea     rbx, Size
0x18003f0a4  add     ecx, eax
0x18003f0a6  and     r8d, r9d
0x18003f0a9  mov     [r14+90h], ecx
0x18003f0b0  movzx   eax, [rbp+37h+Source.Length]
0x18003f0b4  mov     ecx, [r15+rbx]
0x18003f0b8  add     eax, r11d
0x18003f0bb  add     ecx, r11d
0x18003f0be  mov     [r14+0A0h], r10
0x18003f0c5  and     ecx, r9d
0x18003f0c8  and     eax, r9d
0x18003f0cb  add     eax, r8d
0x18003f0ce  add     ecx, eax
0x18003f0d0  add     ecx, edx
0x18003f0d2  mov     [r14+9Ch], ecx
0x18003f0d9  movzx   eax, [rbp+37h+Source.Length]
0x18003f0dd  mov     ecx, [r15+rbx]
0x18003f0e1  add     eax, r11d
0x18003f0e4  add     ecx, r11d
0x18003f0e7  mov     [r14+0ACh], r10
0x18003f0ee  and     ecx, r9d
0x18003f0f1  and     eax, r9d
0x18003f0f4  add     eax, r8d
  ... truncated ...
```
