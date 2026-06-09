# CreateAlias(_UNICODE_STRING *,_UNICODE_STRING *,uchar,ulong,ulong)

- ea: `0x18003dd78`
- end: `0x18003e2cd`
- name: `?CreateAlias@@YAJPEAU_UNICODE_STRING@@0EKK@Z`
- size: `1365`
- prototype: `NTSTATUS __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, __int64, ULONG, ULONG)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003e2d4`

## callees

- `0x180020610`
- `0x18003d82c`
- `0x18003d8b0`
- `0x18003dd78`
- `0x18004b9c4`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlApplyRXactNoFlush` at `0x18003e2a9`
- `ntdll!RtlApplyRXactNoFlush` at `0x18003e2a9`
- `ntdll!RtlStartRXact` at `0x18003dde6`
- `ntdll!RtlStartRXact` at `0x18003dde6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003de27`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003de27`
- `ntdll!RtlAppendUnicodeToString` at `0x18003de13`
- `ntdll!RtlAppendUnicodeToString` at `0x18003e226`
- `ntdll!RtlAppendUnicodeToString` at `0x18003de13`
- `ntdll!RtlAppendUnicodeToString` at `0x18003e226`
- `ntdll!RtlFreeHeap` at `0x18003e024`
- `ntdll!RtlFreeHeap` at `0x18003e041`
- `ntdll!RtlFreeHeap` at `0x18003e1ff`
- `ntdll!RtlFreeHeap` at `0x18003e29c`
- `ntdll!RtlFreeHeap` at `0x18003e024`
- `ntdll!RtlFreeHeap` at `0x18003e041`
- `ntdll!RtlFreeHeap` at `0x18003e1ff`
- `ntdll!RtlFreeHeap` at `0x18003e29c`
- `ntdll!RtlAllocateHeap` at `0x18003df92`
- `ntdll!RtlAllocateHeap` at `0x18003e09b`
- `ntdll!RtlAllocateHeap` at `0x18003df92`
- `ntdll!RtlAllocateHeap` at `0x18003e09b`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003e27e`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003e27e`
- `ntdll!RtlCopyUnicodeString` at `0x18003de03`
- `ntdll!RtlCopyUnicodeString` at `0x18003e216`
- `ntdll!RtlCopyUnicodeString` at `0x18003de03`
- `ntdll!RtlCopyUnicodeString` at `0x18003e216`
- `ntdll!RtlAddActionToRXact` at `0x18003de4e`
- `ntdll!RtlAddActionToRXact` at `0x18003de4e`
- `ntdll!RtlCopySid` at `0x18003dfac`
- `ntdll!RtlCopySid` at `0x18003dfed`
- `ntdll!RtlCopySid` at `0x18003dfac`
- `ntdll!RtlCopySid` at `0x18003dfed`
- `ntdll!RtlLengthSid` at `0x18003df66`
- `ntdll!RtlLengthSid` at `0x18003df77`
- `ntdll!RtlLengthSid` at `0x18003df9e`
- `ntdll!RtlLengthSid` at `0x18003dfd1`
- `ntdll!RtlLengthSid` at `0x18003dfdf`
- `ntdll!RtlLengthSid` at `0x18003df66`
- `ntdll!RtlLengthSid` at `0x18003df77`
- `ntdll!RtlLengthSid` at `0x18003df9e`
- `ntdll!RtlLengthSid` at `0x18003dfd1`
- `ntdll!RtlLengthSid` at `0x18003dfdf`

## pseudocode

```c
NTSTATUS __fastcall CreateAlias(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, __int64 a3, ULONG a4, ULONG a5)
{
  __int64 v5; // r14
  struct _UNICODE_STRING *v7; // rbx
  int v8; // edi
  void *v9; // rbp
  char *Heap; // r13
  __int64 v11; // rcx
  ULONG v12; // r12d
  ULONG v13; // edx
  void *v14; // rax
  void *v15; // rsi
  ULONG v16; // ecx
  ULONG v17; // ecx
  __int64 v18; // rcx
  ULONG v19; // eax
  char *v20; // rbx
  ULONG v21; // eax
  _DWORD *v22; // rax
  _DWORD *v23; // rbp
  unsigned int v24; // ebx
  int v25; // eax
  int v26; // esi
  unsigned int v27; // ecx
  int v28; // eax
  unsigned int v29; // edx
  unsigned int v30; // r8d
  NTSTATUS v31; // eax
  struct _PEB *v32; // rcx
  NTSTATUS result; // eax
  UNICODE_STRING Source; // [rsp+40h] [rbp-48h] BYREF
  USHORT Length; // [rsp+A0h] [rbp+18h]
  unsigned int v38; // [rsp+B0h] [rbp+28h]

  v5 = 32LL * a5;
  Source = *a1;
  v7 = a2;
  Length = a2->Length;
  v8 = 1;
  v9 = 0;
  Heap = 0;
  if ( *((_BYTE *)&Size + v5 + 24) == 1 )
    **(_DWORD **)((char *)&Size + v5 + 16) = a4;
  dword_1800EF708 = RtlStartRXact(P);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Aliases\\Names\\");
  dword_1800EF708 = RtlAppendUnicodeStringToString(&KeyName, &Source);
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, a4, 0, 0);
  v12 = 0;
  if ( a4 == 544 )
  {
    v15 = BuildAccountSid(v11, 0x1F4u);
    if ( ProductType == NtProductLanManNt )
    {
      v8 = 2;
      v9 = BuildAccountSid(v18, 0x200u);
      if ( ProductType == NtProductLanManNt )
        goto LABEL_27;
    }
    if ( !qword_1800F0960 )
      goto LABEL_27;
    v17 = 512;
    goto LABEL_15;
  }
  if ( a4 != 545 )
  {
    if ( a4 != 546 )
    {
      if ( a4 != 581 )
      {
LABEL_7:
        v8 = 0;
        goto LABEL_33;
      }
      v13 = 503;
      goto LABEL_9;
    }
    if ( ((ProductType - 1) & 0xFFFFFFFD) != 0 )
    {
      v16 = 514;
LABEL_22:
      v14 = BuildPrimaryDomainSid(v16);
      goto LABEL_10;
    }
    v15 = BuildAccountSid(v11, 0x1F5u);
    if ( !qword_1800F0960 )
      goto LABEL_27;
    v17 = 514;
LABEL_15:
    v8 = 2;
    v9 = BuildPrimaryDomainSid(v17);
    goto LABEL_27;
  }
  v11 = (unsigned int)ProductType;
  if ( ((ProductType - 1) & 0xFFFFFFFD) == 0 )
  {
    if ( !qword_1800F0960 )
      goto LABEL_7;
    v16 = 513;
    goto LABEL_22;
  }
  if ( ProductType == NtProductLanManNt )
    v13 = 513;
  else
    v13 = 500;
LABEL_9:
  v14 = BuildAccountSid(v11, v13);
LABEL_10:
  v15 = v14;
LABEL_27:
  v12 = RtlLengthSid(v15);
  if ( v9 )
    v12 += RtlLengthSid(v9);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  v19 = RtlLengthSid(v15);
  dword_1800EF708 = RtlCopySid(v19, Heap, v15);
  dword_1800EF708 = UpdateAliasXReference(a4, v15);
  if ( v9 )
  {
    v20 = &Heap[RtlLengthSid(v15)];
    v21 = RtlLengthSid(v9);
    dword_1800EF708 = RtlCopySid(v21, v20, v9);
    v7 = a2;
    dword_1800EF708 = UpdateAliasXReference(a4, v9);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
LABEL_33:
  v38 = ((a1->Length + 3) & 0xFFFFFFFC)
      + v12
      + ((v7->Length + 3) & 0xFFFFFFFC)
      + ((*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC)
      + 52;
  v22 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v38);
  v23 = v22;
  if ( !v22 )
    dword_1800EF708 = -1073741670;
  v24 = a1->Length;
  *v22 = a4;
  v22[1] = 0;
  v22[2] = *(_DWORD *)((char *)&Size + v5);
  v22[3] = 65539;
  v22[4] = (*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC;
  v22[5] = Source.Length;
  v22[6] = 0;
  v25 = *(_DWORD *)((char *)&Size + v5) + 3;
  v23[9] = 0;
  v23[7] = (v25 & 0xFFFFFFFC) + ((v24 + 3) & 0xFFFFFFFC);
  v23[8] = Length;
  v26 = Length + 3;
  v27 = (Source.Length + 3) & 0xFFFFFFFC;
  v28 = *(_DWORD *)((char *)&Size + v5) + 3;
  v23[12] = v8;
  v23[11] = v12;
  v23[10] = (v26 & 0xFFFFFFFC) + (v28 & 0xFFFFFFFC) + v27;
  memcpy_0(v23 + 13, *(const void **)((char *)&Size + v5 + 8), *(unsigned int *)((char *)&Size + v5));
  memcpy_0((char *)v23 + ((*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC) + 52, a1->Buffer, v24);
  memcpy_0(
    (char *)v23 + ((Source.Length + 3) & 0xFFFFFFFC) + ((*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC) + 52,
    a2->Buffer,
    a2->Length);
  memcpy_0(
    (char *)v23
  + ((*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC)
  + ((Source.Length + 3) & 0xFFFFFFFC)
  + (v26 & 0xFFFFFFFC)
  + 52,
    Heap,
    v12);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Aliases\\");
  dword_1800EF708 = SampRtlConvertUlongToUnicodeString(a4, v29, v30, 0, &KeyName);
  v31 = RtlAddAttributeActionToRXact(
          P,
          2u,
          &KeyName,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          &SampCombinedAttributeName,
          3u,
          v23,
          v38);
  v32 = NtCurrentPeb();
  dword_1800EF708 = v31;
  RtlFreeHeap(v32->ProcessHeap, 0, v23);
  result = RtlApplyRXactNoFlush(P);
  dword_1800EF708 = result;
  return result;
}

```

## disassembly

```asm
0x18003dd78  mov     rax, rsp
0x18003dd7b  mov     [rax+20h], rbx
0x18003dd7f  mov     [rax+18h], r8b
0x18003dd83  mov     [rax+10h], rdx
0x18003dd87  mov     [rax+8], rcx
0x18003dd8b  push    rbp
0x18003dd8c  push    rsi
0x18003dd8d  push    rdi
0x18003dd8e  push    r12
0x18003dd90  push    r13
0x18003dd92  push    r14
0x18003dd94  push    r15
0x18003dd96  sub     rsp, 50h
0x18003dd9a  movups  xmm0, xmmword ptr [rcx]
0x18003dd9d  mov     r14d, [rsp+88h+arg_20]
0x18003dda5  xor     esi, esi
0x18003dda7  shl     r14, 5
0x18003ddab  mov     r15d, r9d
0x18003ddae  movdqu  xmmword ptr [rax-48h], xmm0
0x18003ddb3  movzx   eax, word ptr [rdx]
0x18003ddb6  mov     rbx, rdx
0x18003ddb9  mov     [rsp+88h+arg_10], ax
0x18003ddc1  lea     edi, [rsi+1]
0x18003ddc4  lea     rax, Size
0x18003ddcb  mov     ebp, esi
0x18003ddcd  mov     r13d, esi
0x18003ddd0  cmp     [r14+rax+18h], dil
0x18003ddd5  jnz     short loc_18003DDDF
0x18003ddd7  mov     rax, [r14+rax+10h]
0x18003dddc  mov     [rax], r9d
0x18003dddf  mov     rcx, cs:P; Context
0x18003dde6  call    cs:__imp_RtlStartRXact
0x18003ddec  mov     rdx, cs:qword_1800EF7C8; SourceString
0x18003ddf3  lea     r12, KeyName
0x18003ddfa  mov     rcx, r12; DestinationString
0x18003ddfd  mov     cs:dword_1800EF708, eax
0x18003de03  call    cs:__imp_RtlCopyUnicodeString
0x18003de09  lea     rdx, Source; "\\Aliases\\Names\\"
0x18003de10  mov     rcx, r12; Destination
0x18003de13  call    cs:__imp_RtlAppendUnicodeToString
0x18003de19  lea     rdx, [rsp+88h+Source]; Source
0x18003de1e  mov     rcx, r12; Destination
0x18003de21  mov     cs:dword_1800EF708, eax
0x18003de27  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003de2d  mov     rcx, cs:P; Context
0x18003de34  mov     r9d, r15d; ValueType
0x18003de37  mov     r8, r12; KeyName
0x18003de3a  mov     [rsp+88h+ValueDataSize], esi; ValueDataSize
0x18003de3e  mov     edx, 2; ActionType
0x18003de43  mov     cs:dword_1800EF708, eax
0x18003de49  mov     [rsp+88h+ValueData], rsi; ValueData
0x18003de4e  call    cs:__imp_RtlAddActionToRXact
0x18003de54  mov     cs:dword_1800EF708, eax
0x18003de5a  mov     r12d, esi
0x18003de5d  mov     eax, r15d
0x18003de60  sub     eax, 220h
0x18003de65  jz      loc_18003DF17
0x18003de6b  sub     eax, edi
0x18003de6d  jz      short loc_18003DED8
0x18003de6f  sub     eax, edi
0x18003de71  jz      short loc_18003DE91
0x18003de73  cmp     eax, 23h ; '#'
0x18003de76  jz      short loc_18003DE7F
0x18003de78  mov     edi, esi
0x18003de7a  jmp     loc_18003E047
0x18003de7f  mov     edx, 1F7h
0x18003de84  call    ?BuildAccountSid@@YAPEAXW4_SAMP_DOMAIN_SELECTOR@@K@Z; BuildAccountSid(_SAMP_DOMAIN_SELECTOR,ulong)
0x18003de89  mov     rsi, rax
0x18003de8c  jmp     loc_18003DF63
0x18003de91  mov     eax, cs:ProductType
0x18003de97  dec     eax
0x18003de99  test    eax, 0FFFFFFFDh
0x18003de9e  jz      short loc_18003DEA7
0x18003dea0  mov     ecx, 202h
0x18003dea5  jmp     short loc_18003DF0D
0x18003dea7  mov     edx, 1F5h
0x18003deac  call    ?BuildAccountSid@@YAPEAXW4_SAMP_DOMAIN_SELECTOR@@K@Z; BuildAccountSid(_SAMP_DOMAIN_SELECTOR,ulong)
0x18003deb1  cmp     cs:qword_1800F0960, rbp
0x18003deb8  mov     rsi, rax
0x18003debb  jz      loc_18003DF63
0x18003dec1  mov     ecx, 202h; unsigned int
0x18003dec6  mov     edi, 2
0x18003decb  call    ?BuildPrimaryDomainSid@@YAPEAXK@Z; BuildPrimaryDomainSid(ulong)
0x18003ded0  mov     rbp, rax
0x18003ded3  jmp     loc_18003DF63
0x18003ded8  mov     ecx, cs:ProductType
0x18003dede  lea     eax, [rcx-1]
0x18003dee1  test    eax, 0FFFFFFFDh
0x18003dee6  jz      short loc_18003DEFB
0x18003dee8  cmp     ecx, 2
0x18003deeb  jnz     short loc_18003DEF4
0x18003deed  mov     edx, 201h
0x18003def2  jmp     short loc_18003DE84
0x18003def4  mov     edx, 1F4h
0x18003def9  jmp     short loc_18003DE84
0x18003defb  cmp     cs:qword_1800F0960, rsi
0x18003df02  jz      loc_18003DE78
0x18003df08  mov     ecx, 201h; unsigned int
0x18003df0d  call    ?BuildPrimaryDomainSid@@YAPEAXK@Z; BuildPrimaryDomainSid(ulong)
0x18003df12  jmp     loc_18003DE89
0x18003df17  mov     edx, 1F4h
0x18003df1c  call    ?BuildAccountSid@@YAPEAXW4_SAMP_DOMAIN_SELECTOR@@K@Z; BuildAccountSid(_SAMP_DOMAIN_SELECTOR,ulong)
0x18003df21  mov     rsi, rax
0x18003df24  mov     eax, cs:ProductType
0x18003df2a  cmp     eax, 2
0x18003df2d  jnz     short loc_18003DF48
0x18003df2f  mov     edx, 200h
0x18003df34  mov     edi, eax
0x18003df36  call    ?BuildAccountSid@@YAPEAXW4_SAMP_DOMAIN_SELECTOR@@K@Z; BuildAccountSid(_SAMP_DOMAIN_SELECTOR,ulong)
0x18003df3b  mov     rbp, rax
0x18003df3e  mov     eax, cs:ProductType
0x18003df44  cmp     eax, edi
0x18003df46  jz      short loc_18003DF5B
0x18003df48  cmp     cs:qword_1800F0960, r12
0x18003df4f  jz      short loc_18003DF5B
0x18003df51  mov     ecx, 200h
0x18003df56  jmp     loc_18003DEC6
0x18003df5b  test    edi, edi
0x18003df5d  jz      loc_18003E047
0x18003df63  mov     rcx, rsi; Sid
0x18003df66  call    cs:__imp_RtlLengthSid
0x18003df6c  mov     r12d, eax
0x18003df6f  test    rbp, rbp
0x18003df72  jz      short loc_18003DF80
0x18003df74  mov     rcx, rbp; Sid
0x18003df77  call    cs:__imp_RtlLengthSid
0x18003df7d  add     r12d, eax
0x18003df80  mov     rcx, gs:60h
0x18003df89  xor     edx, edx; Flags
0x18003df8b  mov     r8d, r12d; Size
0x18003df8e  mov     rcx, [rcx+30h]; HeapHandle
0x18003df92  call    cs:__imp_RtlAllocateHeap
0x18003df98  mov     rcx, rsi; Sid
0x18003df9b  mov     r13, rax
0x18003df9e  call    cs:__imp_RtlLengthSid
0x18003dfa4  mov     r8, rsi; SourceSid
0x18003dfa7  mov     rdx, r13; DestinationSid
0x18003dfaa  mov     ecx, eax; DestinationSidLength
0x18003dfac  call    cs:__imp_RtlCopySid
0x18003dfb2  mov     rdx, rsi; void *
0x18003dfb5  mov     ecx, r15d; unsigned int
0x18003dfb8  mov     cs:dword_1800EF708, eax
0x18003dfbe  call    ?UpdateAliasXReference@@YAJKPEAX@Z; UpdateAliasXReference(ulong,void *)
0x18003dfc3  mov     cs:dword_1800EF708, eax
0x18003dfc9  test    rbp, rbp
0x18003dfcc  jz      short loc_18003E012
0x18003dfce  mov     rcx, rsi; Sid
0x18003dfd1  call    cs:__imp_RtlLengthSid
0x18003dfd7  mov     ebx, eax
0x18003dfd9  mov     rcx, rbp; Sid
0x18003dfdc  add     rbx, r13
0x18003dfdf  call    cs:__imp_RtlLengthSid
0x18003dfe5  mov     r8, rbp; SourceSid
0x18003dfe8  mov     rdx, rbx; DestinationSid
0x18003dfeb  mov     ecx, eax; DestinationSidLength
0x18003dfed  call    cs:__imp_RtlCopySid
0x18003dff3  mov     rdx, rbp; void *
0x18003dff6  mov     ecx, r15d; unsigned int
0x18003dff9  mov     cs:dword_1800EF708, eax
0x18003dfff  call    ?UpdateAliasXReference@@YAJKPEAX@Z; UpdateAliasXReference(ulong,void *)
0x18003e004  mov     rbx, [rsp+88h+arg_8]
0x18003e00c  mov     cs:dword_1800EF708, eax
0x18003e012  mov     rcx, gs:60h
0x18003e01b  mov     r8, rsi; P
0x18003e01e  xor     edx, edx; Flags
0x18003e020  mov     rcx, [rcx+30h]; HeapHandle
0x18003e024  call    cs:__imp_RtlFreeHeap
0x18003e02a  test    rbp, rbp
0x18003e02d  jz      short loc_18003E047
0x18003e02f  mov     rcx, gs:60h
0x18003e038  mov     r8, rbp; P
0x18003e03b  xor     edx, edx; Flags
0x18003e03d  mov     rcx, [rcx+30h]; HeapHandle
0x18003e041  call    cs:__imp_RtlFreeHeap
0x18003e047  movzx   ecx, word ptr [rbx]
0x18003e04a  lea     r9, Size
0x18003e051  mov     eax, [r14+r9]
0x18003e055  add     ecx, 3
0x18003e058  mov     rsi, [rsp+88h+arg_0]
0x18003e060  mov     r8d, 0FFFFFFFCh
0x18003e066  and     ecx, r8d
0x18003e069  add     eax, 3
0x18003e06c  add     ecx, r12d
0x18003e06f  and     eax, r8d
0x18003e072  add     eax, 34h ; '4'
0x18003e075  movzx   edx, word ptr [rsi]
0x18003e078  add     edx, 3
0x18003e07b  and     edx, r8d
0x18003e07e  add     ecx, edx
0x18003e080  xor     edx, edx; Flags
0x18003e082  add     eax, ecx
0x18003e084  mov     rcx, gs:60h
0x18003e08d  mov     r8d, eax; Size
0x18003e090  mov     [rsp+88h+arg_20], eax
0x18003e097  mov     rcx, [rcx+30h]; HeapHandle
0x18003e09b  call    cs:__imp_RtlAllocateHeap
0x18003e0a1  xor     r8d, r8d
0x18003e0a4  mov     rbp, rax
0x18003e0a7  test    rax, rax
0x18003e0aa  jnz     short loc_18003E0B6
0x18003e0ac  mov     cs:dword_1800EF708, 0C000009Ah
0x18003e0b6  movzx   ebx, word ptr [rsi]
0x18003e0b9  lea     r9, Size
0x18003e0c0  mov     [rax], r15d
0x18003e0c3  mov     edx, 0FFFFFFFCh
0x18003e0c8  mov     [rax+4], r8d
0x18003e0cc  mov     ecx, [r14+r9]
0x18003e0d0  mov     [rax+8], ecx
0x18003e0d3  mov     dword ptr [rax+0Ch], 10003h
0x18003e0da  mov     ecx, [r14+r9]
0x18003e0de  add     ecx, 3
0x18003e0e1  and     ecx, edx
0x18003e0e3  mov     [rax+10h], ecx
0x18003e0e6  lea     ecx, [rbx+3]
0x18003e0e9  movzx   eax, [rsp+88h+Source.Length]
0x18003e0ee  and     ecx, edx
0x18003e0f0  mov     [rbp+14h], eax
0x18003e0f3  mov     [rbp+18h], r8d
0x18003e0f7  mov     eax, [r14+r9]
0x18003e0fb  add     eax, 3
0x18003e0fe  mov     [rbp+24h], r8d
0x18003e102  and     eax, edx
0x18003e104  add     ecx, eax
0x18003e106  movzx   eax, [rsp+88h+arg_10]
0x18003e10e  mov     [rbp+1Ch], ecx
0x18003e111  mov     [rbp+20h], eax
0x18003e114  movzx   ecx, [rsp+88h+Source.Length]
0x18003e119  lea     esi, [rax+3]
0x18003e11c  add     ecx, 3
0x18003e11f  mov     eax, [r14+r9]
0x18003e123  and     ecx, edx
0x18003e125  add     eax, 3
0x18003e128  mov     [rbp+30h], edi
0x18003e12b  and     eax, edx
0x18003e12d  mov     [rbp+2Ch], r12d
0x18003e131  add     ecx, eax
0x18003e133  lea     rdi, [rbp+34h]
0x18003e137  mov     eax, esi
0x18003e139  and     eax, edx
0x18003e13b  add     ecx, eax
0x18003e13d  mov     [rbp+28h], ecx
0x18003e140  mov     rcx, rdi; void *
0x18003e143  mov     r8d, [r14+r9]; Size
0x18003e147  mov     rdx, [r14+r9+8]; Src
0x18003e14c  call    memcpy_0
0x18003e151  mov     rdx, [rsp+88h+arg_0]
0x18003e159  lea     rax, Size
0x18003e160  mov     ecx, [r14+rax]
0x18003e164  mov     r8d, ebx; Size
0x18003e167  add     ecx, 3
0x18003e16a  mov     ebx, 0FFFFFFFCh
0x18003e16f  and     rcx, rbx
0x18003e172  mov     rdx, [rdx+8]; Src
0x18003e176  add     rcx, rdi; void *
0x18003e179  call    memcpy_0
0x18003e17e  movzx   eax, [rsp+88h+Source.Length]
0x18003e183  lea     r9, Size
0x18003e18a  mov     ecx, [r14+r9]
0x18003e18e  add     eax, 3
0x18003e191  mov     rdx, [rsp+88h+arg_8]
0x18003e199  add     ecx, 3
0x18003e19c  and     rax, rbx
0x18003e19f  and     rcx, rbx
0x18003e1a2  add     rax, rdi
0x18003e1a5  add     rcx, rax; void *
0x18003e1a8  movzx   r8d, word ptr [rdx]; Size
0x18003e1ac  mov     rdx, [rdx+8]; Src
0x18003e1b0  call    memcpy_0
0x18003e1b5  movzx   edx, [rsp+88h+Source.Length]
0x18003e1ba  lea     rax, Size
0x18003e1c1  mov     ecx, [r14+rax]
0x18003e1c5  add     edx, 3
0x18003e1c8  add     ecx, 3
0x18003e1cb  mov     r8d, r12d; Size
0x18003e1ce  and     rcx, rbx
0x18003e1d1  and     rdx, rbx
0x18003e1d4  add     rcx, rdi
0x18003e1d7  and     rsi, rbx
0x18003e1da  add     rcx, rdx
0x18003e1dd  mov     rdx, r13; Src
0x18003e1e0  add     rcx, rsi; void *
0x18003e1e3  call    memcpy_0
0x18003e1e8  test    r13, r13
0x18003e1eb  jz      short loc_18003E205
0x18003e1ed  mov     rcx, gs:60h
0x18003e1f6  mov     r8, r13; P
0x18003e1f9  xor     edx, edx; Flags
0x18003e1fb  mov     rcx, [rcx+30h]; HeapHandle
0x18003e1ff  call    cs:__imp_RtlFreeHeap
0x18003e205  mov     rdx, cs:qword_1800EF7C8; SourceString
0x18003e20c  lea     rbx, KeyName
0x18003e213  mov     rcx, rbx; DestinationString
0x18003e216  call    cs:__imp_RtlCopyUnicodeString
0x18003e21c  lea     rdx, aAliases; "\\Aliases\\"
0x18003e223  mov     rcx, rbx; Destination
0x18003e226  call    cs:__imp_RtlAppendUnicodeToString
0x18003e22c  xor     r9d, r9d; unsigned __int8
0x18003e22f  mov     [rsp+88h+ValueData], rbx; struct _UNICODE_STRING *
0x18003e234  mov     ecx, r15d; Value
0x18003e237  mov     cs:dword_1800EF708, eax
  ... truncated ...
```
