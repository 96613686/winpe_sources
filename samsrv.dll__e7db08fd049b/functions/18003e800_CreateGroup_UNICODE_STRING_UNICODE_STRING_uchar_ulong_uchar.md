# CreateGroup(_UNICODE_STRING *,_UNICODE_STRING *,uchar,ulong,uchar)

- ea: `0x18003e800`
- end: `0x18003ebb2`
- name: `?CreateGroup@@YAJPEAU_UNICODE_STRING@@0EKE@Z`
- size: `946`
- prototype: `NTSTATUS __fastcall(PCUNICODE_STRING Source, struct _UNICODE_STRING *, __int64, ULONG, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d938`

## callees

- `0x180020610`
- `0x18002cd80`
- `0x18003e800`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlApplyRXactNoFlush` at `0x18003eb81`
- `ntdll!RtlApplyRXactNoFlush` at `0x18003eb81`
- `ntdll!RtlStartRXact` at `0x18003e882`
- `ntdll!RtlStartRXact` at `0x18003e882`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003e8c1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003e8c1`
- `ntdll!RtlAppendUnicodeToString` at `0x18003e8af`
- `ntdll!RtlAppendUnicodeToString` at `0x18003e916`
- `ntdll!RtlAppendUnicodeToString` at `0x18003e8af`
- `ntdll!RtlAppendUnicodeToString` at `0x18003e916`
- `ntdll!RtlFreeHeap` at `0x18003eb74`
- `ntdll!RtlFreeHeap` at `0x18003eb74`
- `ntdll!RtlAllocateHeap` at `0x18003e9e9`
- `ntdll!RtlAllocateHeap` at `0x18003e9e9`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003eb56`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003eb56`
- `ntdll!RtlCopyUnicodeString` at `0x18003e89f`
- `ntdll!RtlCopyUnicodeString` at `0x18003e906`
- `ntdll!RtlCopyUnicodeString` at `0x18003e89f`
- `ntdll!RtlCopyUnicodeString` at `0x18003e906`
- `ntdll!RtlAddActionToRXact` at `0x18003e8f0`
- `ntdll!RtlAddActionToRXact` at `0x18003e8f0`

## pseudocode

```c
NTSTATUS __fastcall CreateGroup(
        PCUNICODE_STRING Source,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        ULONG a4,
        unsigned __int8 a5)
{
  __int64 v5; // rsi
  int Length; // ebp
  int v8; // r14d
  unsigned int v10; // edx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  __int64 v13; // rax
  int v14; // r15d
  int v15; // r13d
  int v16; // ebp
  int v17; // r12d
  _DWORD *Heap; // rax
  _DWORD *v19; // r14
  char *v20; // rbx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // r15
  NTSTATUS v25; // eax
  struct _PEB *v26; // rcx
  NTSTATUS result; // eax
  USHORT v28; // [rsp+40h] [rbp-68h]
  USHORT v29; // [rsp+42h] [rbp-66h]
  unsigned int v30; // [rsp+44h] [rbp-64h]
  PWSTR Src; // [rsp+48h] [rbp-60h]
  PWSTR Buffer; // [rsp+50h] [rbp-58h]
  _DWORD v33[4]; // [rsp+58h] [rbp-50h] BYREF

  v5 = 192;
  Length = Source->Length;
  v8 = a2->Length;
  Src = Source->Buffer;
  Buffer = a2->Buffer;
  if ( a5 != 1 )
    v5 = 224;
  v28 = Source->Length;
  v29 = a2->Length;
  if ( *((_BYTE *)&Size + v5 + 24) == 1 )
    **(_DWORD **)((char *)&Size + v5 + 16) = a4;
  dword_1800EF708 = RtlStartRXact(P);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Groups\\Names\\");
  dword_1800EF708 = RtlAppendUnicodeStringToString(&KeyName, Source);
  dword_1800EF708 = RtlAddActionToRXact(P, 2u, &KeyName, a4, 0, 0);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Groups\\");
  dword_1800EF708 = SampRtlConvertUlongToUnicodeString(a4, v10, v11, 0, &KeyName);
  if ( a4 == 513 || (v12 = 0, a4 == 512) )
  {
    v33[0] = 500;
    v12 = 1;
  }
  if ( a4 == 514 )
  {
    if ( ProductType != NtProductLanManNt )
      goto LABEL_16;
    v33[v12] = 501;
  }
  else
  {
    if ( a4 != 513 )
      goto LABEL_16;
    if ( ((ProductType - 1) & 0xFFFFFFFD) == 0 )
    {
      v13 = v12++;
      v33[v13] = 501;
    }
    v33[v12] = 503;
  }
  ++v12;
LABEL_16:
  v14 = Length + 3;
  v15 = Length;
  v16 = v8 + 3;
  v17 = v8;
  v30 = ((v8 + 3) & 0xFFFFFFFC)
      + ((*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC)
      + 68
      + 4 * v12
      + (v14 & 0xFFFFFFFC);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
  v19 = Heap;
  if ( !Heap )
    dword_1800EF708 = -1073741670;
  Heap[1] = a4;
  v20 = (char *)(Heap + 17);
  Heap[2] = 7;
  *((_BYTE *)Heap + 16) = a5 != 0;
  *Heap = 65539;
  *((_BYTE *)Heap + 17) = 0;
  Heap[5] = 0;
  Heap[6] = *(_DWORD *)((char *)&Size + v5);
  Heap[7] = 65539;
  v21 = *(_DWORD *)((char *)&Size + v5) + 3;
  v19[9] = v15;
  v19[10] = 0;
  v19[8] = v21 & 0xFFFFFFFC;
  v22 = *(_DWORD *)((char *)&Size + v5) + 3;
  v19[12] = v17;
  v19[13] = 0;
  v19[11] = (v14 & 0xFFFFFFFC) + (v22 & 0xFFFFFFFC);
  v23 = *(_DWORD *)((char *)&Size + v5) + 3;
  v19[16] = v12;
  v19[14] = (v14 & 0xFFFFFFFC) + (v23 & 0xFFFFFFFC) + (v16 & 0xFFFFFFFC);
  v19[15] = 4 * v12;
  memcpy_0(v19 + 17, *(const void **)((char *)&Size + v5 + 8), *(unsigned int *)((char *)&Size + v5));
  memcpy_0(&v20[(*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC], Src, v28);
  v24 = v14 & 0xFFFFFFFC;
  memcpy_0(&v20[((*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC) + v24], Buffer, v29);
  memcpy_0(&v20[((*(_DWORD *)((char *)&Size + v5) + 3) & 0xFFFFFFFC) + (v16 & 0xFFFFFFFC) + v24], v33, 4LL * v12);
  v25 = RtlAddAttributeActionToRXact(
          P,
          2u,
          &KeyName,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          &SampCombinedAttributeName,
          3u,
          v19,
          v30);
  v26 = NtCurrentPeb();
  dword_1800EF708 = v25;
  RtlFreeHeap(v26->ProcessHeap, 0, v19);
  result = RtlApplyRXactNoFlush(P);
  dword_1800EF708 = result;
  return result;
}

```

## disassembly

```asm
0x18003e800  mov     [rsp+arg_10], rbx
0x18003e805  push    rbp
0x18003e806  push    rsi
0x18003e807  push    rdi
0x18003e808  push    r12
0x18003e80a  push    r13
0x18003e80c  push    r14
0x18003e80e  push    r15
0x18003e810  sub     rsp, 70h
0x18003e814  mov     rax, cs:__security_cookie
0x18003e81b  xor     rax, rsp
0x18003e81e  mov     [rsp+0A8h+var_40], rax
0x18003e823  mov     rax, [rcx+8]
0x18003e827  mov     esi, 0C0h
0x18003e82c  movzx   ebp, word ptr [rcx]
0x18003e82f  mov     r15d, 1
0x18003e835  cmp     [rsp+0A8h+arg_20], r15b
0x18003e83d  mov     ebx, r9d
0x18003e840  movzx   r14d, word ptr [rdx]
0x18003e844  mov     rdi, rcx
0x18003e847  mov     [rsp+0A8h+Src], rax
0x18003e84c  mov     rax, [rdx+8]
0x18003e850  mov     [rsp+0A8h+var_58], rax
0x18003e855  lea     eax, [rsi+20h]
0x18003e858  cmovnz  esi, eax
0x18003e85b  mov     [rsp+0A8h+var_68], bp
0x18003e860  lea     rax, Size
0x18003e867  mov     [rsp+0A8h+var_66], r14w
0x18003e86d  cmp     [rsi+rax+18h], r15b
0x18003e872  jnz     short loc_18003E87B
0x18003e874  mov     rax, [rsi+rax+10h]
0x18003e879  mov     [rax], ebx
0x18003e87b  mov     rcx, cs:P; Context
0x18003e882  call    cs:__imp_RtlStartRXact
0x18003e888  mov     rdx, cs:qword_1800EF7C8; SourceString
0x18003e88f  lea     r12, KeyName
0x18003e896  mov     rcx, r12; DestinationString
0x18003e899  mov     cs:dword_1800EF708, eax
0x18003e89f  call    cs:__imp_RtlCopyUnicodeString
0x18003e8a5  lea     rdx, aGroupsNames; "\\Groups\\Names\\"
0x18003e8ac  mov     rcx, r12; Destination
0x18003e8af  call    cs:__imp_RtlAppendUnicodeToString
0x18003e8b5  mov     rdx, rdi; Source
0x18003e8b8  mov     rcx, r12; Destination
0x18003e8bb  mov     cs:dword_1800EF708, eax
0x18003e8c1  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003e8c7  mov     rcx, cs:P; Context
0x18003e8ce  mov     r9d, ebx; ValueType
0x18003e8d1  mov     r8, r12; KeyName
0x18003e8d4  mov     [rsp+0A8h+ValueDataSize], 0; ValueDataSize
0x18003e8dc  mov     edx, 2; ActionType
0x18003e8e1  mov     cs:dword_1800EF708, eax
0x18003e8e7  mov     [rsp+0A8h+ValueData], 0; ValueData
0x18003e8f0  call    cs:__imp_RtlAddActionToRXact
0x18003e8f6  mov     rdx, cs:qword_1800EF7C8; SourceString
0x18003e8fd  mov     rcx, r12; DestinationString
0x18003e900  mov     cs:dword_1800EF708, eax
0x18003e906  call    cs:__imp_RtlCopyUnicodeString
0x18003e90c  lea     rdx, aGroups; "\\Groups\\"
0x18003e913  mov     rcx, r12; Destination
0x18003e916  call    cs:__imp_RtlAppendUnicodeToString
0x18003e91c  xor     r9d, r9d; unsigned __int8
0x18003e91f  mov     [rsp+0A8h+ValueData], r12; struct _UNICODE_STRING *
0x18003e924  mov     ecx, ebx; Value
0x18003e926  mov     cs:dword_1800EF708, eax
0x18003e92c  call    ?SampRtlConvertUlongToUnicodeString@@YAJKKKEPEAU_UNICODE_STRING@@@Z; SampRtlConvertUlongToUnicodeString(ulong,ulong,ulong,uchar,_UNICODE_STRING *)
0x18003e931  mov     cs:dword_1800EF708, eax
0x18003e937  mov     eax, 201h
0x18003e93c  cmp     ebx, eax
0x18003e93e  jz      short loc_18003E94A
0x18003e940  xor     edi, edi
0x18003e942  cmp     ebx, 200h
0x18003e948  jnz     short loc_18003E955
0x18003e94a  mov     [rsp+0A8h+var_50], 1F4h
0x18003e952  mov     edi, r15d
0x18003e955  cmp     ebx, 202h
0x18003e95b  jnz     short loc_18003E972
0x18003e95d  cmp     cs:ProductType, 2
0x18003e964  jnz     short loc_18003E99E
0x18003e966  mov     eax, edi
0x18003e968  mov     [rsp+rax*4+0A8h+var_50], 1F5h
0x18003e970  jmp     short loc_18003E99B
0x18003e972  cmp     ebx, eax
0x18003e974  jnz     short loc_18003E99E
0x18003e976  mov     eax, cs:ProductType
0x18003e97c  dec     eax
0x18003e97e  test    eax, 0FFFFFFFDh
0x18003e983  jnz     short loc_18003E991
0x18003e985  mov     eax, edi
0x18003e987  inc     edi
0x18003e989  mov     [rsp+rax*4+0A8h+var_50], 1F5h
0x18003e991  mov     eax, edi
0x18003e993  mov     [rsp+rax*4+0A8h+var_50], 1F7h
0x18003e99b  add     edi, r15d
0x18003e99e  mov     edx, 0FFFFFFFCh
0x18003e9a3  lea     rax, Size
0x18003e9aa  mov     ecx, [rsi+rax]
0x18003e9ad  lea     r15d, [rbp+3]
0x18003e9b1  add     ecx, 3
0x18003e9b4  mov     r13d, ebp
0x18003e9b7  and     ecx, edx
0x18003e9b9  lea     ebp, [r14+3]
0x18003e9bd  add     ecx, 44h ; 'D'
0x18003e9c0  mov     eax, ebp
0x18003e9c2  and     eax, edx
0x18003e9c4  mov     r12d, r14d
0x18003e9c7  lea     ecx, [rcx+rdi*4]
0x18003e9ca  add     ecx, eax
0x18003e9cc  mov     eax, r15d
0x18003e9cf  and     eax, edx
0x18003e9d1  xor     edx, edx; Flags
0x18003e9d3  add     eax, ecx
0x18003e9d5  mov     rcx, gs:60h
0x18003e9de  mov     r8d, eax; Size
0x18003e9e1  mov     [rsp+0A8h+var_64], eax
0x18003e9e5  mov     rcx, [rcx+30h]; HeapHandle
0x18003e9e9  call    cs:__imp_RtlAllocateHeap
0x18003e9ef  xor     r8d, r8d
0x18003e9f2  mov     r14, rax
0x18003e9f5  test    rax, rax
0x18003e9f8  jnz     short loc_18003EA04
0x18003e9fa  mov     cs:dword_1800EF708, 0C000009Ah
0x18003ea04  cmp     [rsp+0A8h+arg_20], r8b
0x18003ea0c  lea     rdx, Size
0x18003ea13  mov     [rax+4], ebx
0x18003ea16  lea     rbx, [r14+44h]
0x18003ea1a  mov     dword ptr [rax+8], 7
0x18003ea21  setnz   cl
0x18003ea24  mov     [rax+10h], cl
0x18003ea27  mov     ecx, 10003h
0x18003ea2c  mov     [rax], ecx
0x18003ea2e  mov     [rax+11h], r8b
0x18003ea32  mov     [rax+14h], r8d
0x18003ea36  mov     eax, [rsi+rdx]
0x18003ea39  mov     [r14+18h], eax
0x18003ea3d  mov     [r14+1Ch], ecx
0x18003ea41  mov     ecx, ebp
0x18003ea43  mov     eax, [rsi+rdx]
0x18003ea46  and     ecx, 0FFFFFFFCh
0x18003ea49  add     eax, 3
0x18003ea4c  mov     [r14+24h], r13d
0x18003ea50  and     eax, 0FFFFFFFCh
0x18003ea53  mov     [r14+28h], r8d
0x18003ea57  mov     [r14+20h], eax
0x18003ea5b  lea     r13, Size
0x18003ea62  mov     eax, [rsi+r13]
0x18003ea66  mov     edx, r15d
0x18003ea69  add     eax, 3
0x18003ea6c  mov     [r14+30h], r12d
0x18003ea70  and     eax, 0FFFFFFFCh
0x18003ea73  mov     [r14+34h], r8d
0x18003ea77  and     edx, 0FFFFFFFCh
0x18003ea7a  add     eax, edx
0x18003ea7c  mov     [r14+2Ch], eax
0x18003ea80  mov     eax, [rsi+r13]
0x18003ea84  add     eax, 3
0x18003ea87  mov     [r14+40h], edi
0x18003ea8b  and     eax, 0FFFFFFFCh
0x18003ea8e  add     eax, edx
0x18003ea90  add     ecx, eax
0x18003ea92  lea     eax, ds:0[rdi*4]
0x18003ea99  mov     [r14+38h], ecx
0x18003ea9d  mov     rcx, rbx; void *
0x18003eaa0  mov     [r14+3Ch], eax
0x18003eaa4  mov     r8d, [rsi+r13]; Size
0x18003eaa8  mov     rdx, [rsi+r13+8]; Src
0x18003eaad  call    memcpy_0
0x18003eab2  mov     ecx, [rsi+r13]
0x18003eab6  mov     r12d, 0FFFFFFFCh
0x18003eabc  movzx   r8d, [rsp+0A8h+var_68]; Size
0x18003eac2  add     ecx, 3
0x18003eac5  mov     rdx, [rsp+0A8h+Src]; Src
0x18003eaca  and     rcx, r12
0x18003eacd  add     rcx, rbx; void *
0x18003ead0  call    memcpy_0
0x18003ead5  mov     ecx, [rsi+r13]
0x18003ead9  and     r15, r12
0x18003eadc  movzx   r8d, [rsp+0A8h+var_66]; Size
0x18003eae2  add     ecx, 3
0x18003eae5  mov     rdx, [rsp+0A8h+var_58]; Src
0x18003eaea  and     rcx, r12
0x18003eaed  add     rcx, rbx
0x18003eaf0  add     rcx, r15; void *
0x18003eaf3  call    memcpy_0
0x18003eaf8  mov     ecx, [rsi+r13]
0x18003eafc  lea     rdx, [rsp+0A8h+var_50]; Src
0x18003eb01  add     ecx, 3
0x18003eb04  mov     r8d, edi
0x18003eb07  and     rcx, r12
0x18003eb0a  shl     r8, 2; Size
0x18003eb0e  add     rcx, rbx
0x18003eb11  and     rbp, r12
0x18003eb14  add     rcx, rbp
0x18003eb17  add     rcx, r15; void *
0x18003eb1a  call    memcpy_0
0x18003eb1f  mov     eax, [rsp+0A8h+var_64]
0x18003eb23  lea     r8, KeyName; KeyName
0x18003eb2a  mov     [rsp+0A8h+var_70], eax; ValueDataSize
0x18003eb2e  or      r9, 0FFFFFFFFFFFFFFFFh; KeyHandle
0x18003eb32  mov     [rsp+0A8h+var_78], r14; ValueData
0x18003eb37  lea     rax, ?SampCombinedAttributeName@@3U_UNICODE_STRING@@A; _UNICODE_STRING SampCombinedAttributeName
0x18003eb3e  mov     [rsp+0A8h+ValueDataSize], 3; ValueType
0x18003eb46  mov     [rsp+0A8h+ValueData], rax; ValueName
0x18003eb4b  mov     rcx, cs:P; Context
0x18003eb52  lea     edx, [r9+3]; ActionType
0x18003eb56  call    cs:__imp_RtlAddAttributeActionToRXact
0x18003eb5c  mov     rcx, gs:60h
0x18003eb65  mov     r8, r14; P
0x18003eb68  xor     edx, edx; Flags
0x18003eb6a  mov     cs:dword_1800EF708, eax
0x18003eb70  mov     rcx, [rcx+30h]; HeapHandle
0x18003eb74  call    cs:__imp_RtlFreeHeap
0x18003eb7a  mov     rcx, cs:P; Context
0x18003eb81  call    cs:__imp_RtlApplyRXactNoFlush
0x18003eb87  mov     cs:dword_1800EF708, eax
0x18003eb8d  mov     rcx, [rsp+0A8h+var_40]
0x18003eb92  xor     rcx, rsp; StackCookie
0x18003eb95  call    __security_check_cookie
0x18003eb9a  mov     rbx, [rsp+0A8h+arg_10]
0x18003eba2  add     rsp, 70h
0x18003eba6  pop     r15
0x18003eba8  pop     r14
0x18003ebaa  pop     r13
0x18003ebac  pop     r12
0x18003ebae  pop     rdi
0x18003ebaf  pop     rsi
0x18003ebb0  pop     rbp
0x18003ebb1  retn
```
