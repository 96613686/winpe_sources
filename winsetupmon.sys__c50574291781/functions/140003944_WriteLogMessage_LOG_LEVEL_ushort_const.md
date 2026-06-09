# WriteLogMessage(_LOG_LEVEL,ushort const *,...)

- ea: `0x140003944`
- end: `0x140003f42`
- name: `?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ`
- size: `1534`
- prototype: ``
- caller_count: `36`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140001380`
- `0x140001674`
- `0x140001748`
- `0x1400018a8`
- `0x140001a10`
- `0x140001a94`
- `0x140002a9c`
- `0x140002ba0`
- `0x1400030b8`
- `0x140003554`
- `0x14000362c`
- `0x140003f48`
- `0x1400040b4`
- `0x1400041ac`
- `0x140004260`
- `0x14000439c`
- `0x140004564`
- `0x140004670`
- `0x140004908`
- `0x140004c50`
- `0x140004e30`
- `0x140005164`
- `0x140005544`
- `0x1400056bc`
- `0x140005910`
- `0x140005de4`
- `0x140006924`
- `0x140006bd4`
- `0x140006f78`
- `0x1400071f4`
- `0x140007384`
- `0x140007800`
- `0x14001e808`
- `0x14001fcc0`
- `0x14001fe30`
- `0x14001ffd0`

## callees

- `0x140002e5c`
- `0x140003218`
- `0x140003944`
- `0x14000dd24`
- `0x14000f900`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140003c03`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003c03`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003a85`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003b88`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003a85`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003b88`
- `ntoskrnl!_vsnwprintf` at `0x140003b35`
- `ntoskrnl!_vsnwprintf` at `0x140003b35`
- `ntoskrnl!RtlTimeToTimeFields` at `0x1400039be`
- `ntoskrnl!RtlTimeToTimeFields` at `0x1400039be`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400039aa`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400039aa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003bb7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003f15`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003bb7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003f15`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400039e1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400039e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003d08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003d23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003edf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003d08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003d23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003edf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003e34`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003e34`
- `ntoskrnl!KeReleaseMutex` at `0x140003e91`
- `ntoskrnl!KeReleaseMutex` at `0x140003efd`
- `ntoskrnl!KeReleaseMutex` at `0x140003e91`
- `ntoskrnl!KeReleaseMutex` at `0x140003efd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003bda`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003bda`
- `FLTMGR!FltFlushBuffers` at `0x140003dfe`
- `FLTMGR!FltFlushBuffers` at `0x140003dfe`
- `FLTMGR!FltWriteFile` at `0x140003ce2`
- `FLTMGR!FltWriteFile` at `0x140003dd9`
- `FLTMGR!FltWriteFile` at `0x140003ce2`
- `FLTMGR!FltWriteFile` at `0x140003dd9`

## pseudocode

```c
void WriteLogMessage(int a1, const wchar_t *a2, ...)
{
  __int64 v2; // rbx
  char v3; // r14
  char v4; // r15
  unsigned __int16 Length; // r8
  unsigned __int16 v6; // dx
  unsigned __int64 v7; // rcx
  wchar_t *v8; // r10
  unsigned __int64 v9; // rbx
  __int16 v10; // dx
  int v11; // ecx
  int v12; // eax
  __int16 v13; // dx
  int v14; // eax
  PVOID *v15; // rbx
  __int64 v16; // rsi
  __int64 v17; // rax
  PVOID v18; // rcx
  __int64 v19; // rdi
  _OWORD *PoolWithTag; // rax
  _QWORD *v21; // rcx
  PVOID v22; // rcx
  struct _UNICODE_STRING BytesWritten; // [rsp+58h] [rbp-39h] BYREF
  PVOID Buffer[2]; // [rsp+68h] [rbp-29h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+78h] [rbp-19h] BYREF
  union _LARGE_INTEGER LocalTime; // [rsp+80h] [rbp-11h] BYREF
  struct _TIME_FIELDS TimeFields; // [rsp+88h] [rbp-9h] BYREF
  va_list Args; // [rsp+108h] [rbp+77h] BYREF

  va_start(Args, a2);
  v2 = a1;
  *(_OWORD *)Buffer = 0;
  LocalTime.QuadPart = 0;
  TimeFields = 0;
  SystemTime.QuadPart = MEMORY[0xFFFFF78000000014];
  ExSystemTimeToLocalTime(&SystemTime, &LocalTime);
  RtlTimeToTimeFields(&LocalTime, &TimeFields);
  if ( !stru_140019640.Buffer )
    return;
  v3 = 0;
  ExAcquireFastMutex(&stru_140019608);
  v4 = 1;
  BytesWritten.MaximumLength = stru_140019640.MaximumLength;
  *(_DWORD *)(&BytesWritten.MaximumLength + 1) = 0;
  BytesWritten.Buffer = stru_140019640.Buffer;
  stru_140019640.Length = 0;
  BytesWritten.Length = 0;
  if ( RtlUnicodeStringPrintf(
         &BytesWritten,
         L"%hd-%02hd-%02hd %02hd:%02hd:%02hd, ",
         (unsigned int)TimeFields.Year,
         (unsigned int)TimeFields.Month,
         TimeFields.Day,
         TimeFields.Hour,
         TimeFields.Minute,
         TimeFields.Second) >= 0 )
  {
    stru_140019640.Length += BytesWritten.Length;
    if ( RtlAppendUnicodeToString(&stru_140019640, &asc_140013140[13 * v2]) >= 0 )
    {
      Length = stru_140019640.Length;
      v6 = stru_140019640.MaximumLength - stru_140019640.Length;
      *(_DWORD *)&BytesWritten.Length = 0;
      *(_DWORD *)(&BytesWritten.MaximumLength + 1) = 0;
      if ( ((LOBYTE(stru_140019640.MaximumLength) - LOBYTE(stru_140019640.Length)) & 1) == 0 && v6 != 0xFFFF )
      {
        v7 = (unsigned __int64)stru_140019640.Length >> 1;
        v8 = &stru_140019640.Buffer[v7];
        if ( v8 || !v6 )
        {
          v9 = (unsigned __int64)v6 >> 1;
          if ( v9 )
          {
            v12 = _vsnwprintf(&stru_140019640.Buffer[v7], (unsigned __int64)v6 >> 1, a2, Args);
            if ( v12 < 0 || (v10 = v12, v12 > v9) )
            {
              v10 = v9;
              v11 = -2147483643;
            }
            else
            {
              v11 = 0;
            }
            Length = stru_140019640.Length;
          }
          else
          {
            v10 = 0;
            v11 = 0;
            if ( *a2 )
              v11 = v8 != 0 ? -2147483643 : -1073741811;
          }
          v13 = 2 * v10;
          v14 = 0;
          if ( v11 != -2147483643 )
            v14 = v11;
          if ( v14 >= 0 )
          {
            stru_140019640.Length = v13 + Length;
            if ( RtlAppendUnicodeToString(&stru_140019640, L"\r\n") >= 0
              && (int)Duplicate(&stru_140019640, (PUNICODE_STRING)Buffer) >= 0 )
            {
              ExReleaseFastMutex(&stru_140019608);
              v4 = 0;
              KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
              v3 = 1;
              if ( FileObject && Instance && !KeGetCurrentIrql() )
              {
                v15 = 0;
                *(_DWORD *)&BytesWritten.Length = 0;
                v16 = 0;
                while ( qword_140019540 != &qword_140019540 )
                {
                  if ( qword_140019578
                    && (qword_140019578 < (unsigned __int64)qword_140019580
                     || qword_140019580 <= (unsigned __int64)stru_140019640.Length) )
                  {
                    if ( (int)SplitLogFile() < 0 )
                      goto LABEL_53;
                    qword_140019580 = qword_140019578;
                  }
                  v15 = (PVOID *)qword_140019540;
                  if ( *((PVOID **)qword_140019540 + 1) != &qword_140019540 )
                    goto LABEL_50;
                  v17 = *(_QWORD *)qword_140019540;
                  if ( *(PVOID *)(*(_QWORD *)qword_140019540 + 8LL) != qword_140019540 )
                    goto LABEL_50;
                  qword_140019540 = *(PVOID *)qword_140019540;
                  *(_QWORD *)(v17 + 8) = &qword_140019540;
                  if ( FltWriteFile(
                         (PFLT_INSTANCE)Instance,
                         (PFILE_OBJECT)FileObject,
                         0,
                         *((unsigned __int16 *)v15 + 8),
                         v15[3],
                         0,
                         (PULONG)&BytesWritten.Length,
                         0,
                         0) < 0 )
                    goto LABEL_53;
                  v18 = v15[3];
                  v16 += *(unsigned int *)&BytesWritten.Length;
                  if ( v18 )
                  {
                    ExFreePoolWithTag(v18, 0x6E6D7377u);
                    v15[3] = 0;
                  }
                  if ( v15 )
                  {
                    ExFreePoolWithTag(v15, 0x6E6D7377u);
                    v15 = 0;
                  }
                  if ( qword_140019580 )
                    qword_140019580 -= v16;
                }
                if ( qword_140019578
                  && (qword_140019578 < (unsigned __int64)qword_140019580
                   || qword_140019580 <= (unsigned __int64)stru_140019640.Length) )
                {
                  if ( (int)SplitLogFile() < 0 )
                    goto LABEL_53;
                  qword_140019580 = qword_140019578;
                }
                *(_DWORD *)&BytesWritten.Length = 0;
                if ( FltWriteFile(
                       (PFLT_INSTANCE)Instance,
                       (PFILE_OBJECT)FileObject,
                       0,
                       LOWORD(Buffer[0]),
                       Buffer[1],
                       0,
                       (PULONG)&BytesWritten.Length,
                       0,
                       0) < 0 )
                {
LABEL_53:
                  if ( v15 )
                  {
                    v22 = v15[3];
                    if ( v22 )
                    {
                      ExFreePoolWithTag(v22, 0x6E6D7377u);
                      v15[3] = 0;
                    }
                    ExFreePoolWithTag(v15, 0x6E6D7377u);
                  }
                  goto LABEL_57;
                }
                v19 = *(unsigned int *)&BytesWritten.Length;
                FltFlushBuffers((PFLT_INSTANCE)Instance, (PFILE_OBJECT)FileObject);
                if ( qword_140019580 )
                  qword_140019580 -= v19;
LABEL_52:
                KeReleaseMutex(&Object, 0);
                v3 = 0;
                goto LABEL_53;
              }
              PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x20u, 0x6E6D7377u);
              if ( PoolWithTag )
              {
                PoolWithTag[1] = *(_OWORD *)Buffer;
                v21 = (_QWORD *)qword_140019548;
                *(_OWORD *)Buffer = 0;
                if ( *(PVOID **)qword_140019548 != &qword_140019540 )
LABEL_50:
                  __fastfail(3u);
                *(_QWORD *)PoolWithTag = &qword_140019540;
                v15 = 0;
                *((_QWORD *)PoolWithTag + 1) = v21;
                *v21 = PoolWithTag;
                qword_140019548 = (__int64)PoolWithTag;
                goto LABEL_52;
              }
            }
          }
        }
      }
    }
  }
LABEL_57:
  if ( Buffer[1] )
  {
    ExFreePoolWithTag(Buffer[1], 0x6E6D7377u);
    Buffer[1] = 0;
  }
  if ( v3 )
    KeReleaseMutex(&Object, 0);
  if ( v4 )
    ExReleaseFastMutex(&stru_140019608);
}

```

## disassembly

```asm
0x140003944  mov     rax, rsp
0x140003947  mov     [rax+10h], rdx
0x14000394b  mov     [rax+18h], r8
0x14000394f  mov     [rax+20h], r9
0x140003953  push    rbp
0x140003954  push    rbx
0x140003955  push    rsi
0x140003956  push    rdi
0x140003957  push    r12
0x140003959  push    r13
0x14000395b  push    r14
0x14000395d  push    r15
0x14000395f  lea     rbp, [rax-5Fh]
0x140003963  sub     rsp, 0A8h
0x14000396a  mov     rax, cs:__security_cookie
0x140003971  xor     rax, rsp
0x140003974  mov     [rbp+57h+var_50], rax
0x140003978  xorps   xmm0, xmm0
0x14000397b  movsxd  rbx, ecx
0x14000397e  xor     r12d, r12d
0x140003981  lea     rdx, [rbp+57h+LocalTime]; LocalTime
0x140003985  mov     qword ptr [rbp+57h+SystemTime], r12
0x140003989  lea     rcx, [rbp+57h+SystemTime]; SystemTime
0x14000398d  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x140003991  mov     qword ptr [rbp+57h+LocalTime], r12
0x140003995  mov     rax, 0FFFFF78000000014h
0x14000399f  movups  xmmword ptr [rbp+57h+TimeFields.Year], xmm0
0x1400039a3  mov     rax, [rax]
0x1400039a6  mov     qword ptr [rbp+57h+SystemTime], rax
0x1400039aa  call    cs:__imp_ExSystemTimeToLocalTime
0x1400039b1  nop     dword ptr [rax+rax+00h]
0x1400039b6  lea     rdx, [rbp+57h+TimeFields]; TimeFields
0x1400039ba  lea     rcx, [rbp+57h+LocalTime]; Time
0x1400039be  call    cs:__imp_RtlTimeToTimeFields
0x1400039c5  nop     dword ptr [rax+rax+00h]
0x1400039ca  cmp     cs:stru_140019640.Buffer, r12
0x1400039d1  jz      loc_140003F21
0x1400039d7  lea     rcx, stru_140019608; FastMutex
0x1400039de  mov     r14b, r12b
0x1400039e1  call    cs:__imp_ExAcquireFastMutex
0x1400039e8  nop     dword ptr [rax+rax+00h]
0x1400039ed  movzx   eax, cs:stru_140019640.MaximumLength
0x1400039f4  mov     r15b, 1
0x1400039f7  movsx   ecx, [rbp+57h+TimeFields.Minute]
0x1400039fb  movsx   edx, [rbp+57h+TimeFields.Hour]
0x1400039ff  movsx   r10d, [rbp+57h+TimeFields.Day]
0x140003a04  movsx   r9d, [rbp+57h+TimeFields.Month]
0x140003a09  movsx   r8d, [rbp+57h+TimeFields.Year]
0x140003a0e  mov     word ptr [rbp+57h+var_90+2], ax
0x140003a12  xor     eax, eax
0x140003a14  mov     [rbp+57h+var_90+4], eax
0x140003a17  mov     rax, cs:stru_140019640.Buffer
0x140003a1e  mov     [rbp+57h+var_88], rax
0x140003a22  movsx   eax, [rbp+57h+TimeFields.Second]
0x140003a26  mov     dword ptr [rsp+0E0h+CallbackRoutine], eax
0x140003a2a  mov     dword ptr [rsp+0E0h+BytesWritten], ecx
0x140003a2e  lea     rcx, [rbp+57h+var_90]; struct _UNICODE_STRING *
0x140003a32  mov     [rsp+0E0h+Flags], edx
0x140003a36  lea     rdx, aHd02hd02hd02hd; "%hd-%02hd-%02hd %02hd:%02hd:%02hd, "
0x140003a3d  mov     cs:stru_140019640.Length, r12w
0x140003a45  mov     word ptr [rbp+57h+var_90], r12w
0x140003a4a  mov     dword ptr [rsp+0E0h+Timeout], r10d
0x140003a4f  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x140003a54  mov     r13d, 6E6D7377h
0x140003a5a  test    eax, eax
0x140003a5c  js      loc_140003ED3
0x140003a62  movzx   eax, word ptr [rbp+57h+var_90]
0x140003a66  lea     rsi, stru_140019640
0x140003a6d  add     cs:stru_140019640.Length, ax
0x140003a74  mov     rcx, rsi; Destination
0x140003a77  lea     rax, asc_140013140; "            "
0x140003a7e  imul    rdx, rbx, 1Ah
0x140003a82  add     rdx, rax; Source
0x140003a85  call    cs:__imp_RtlAppendUnicodeToString
0x140003a8c  nop     dword ptr [rax+rax+00h]
0x140003a91  test    eax, eax
0x140003a93  js      loc_140003ED3
0x140003a99  movzx   edx, cs:stru_140019640.MaximumLength
0x140003aa0  lea     r11, [rbp+57h+Args]
0x140003aa4  movzx   r8d, cs:stru_140019640.Length
0x140003aac  xor     eax, eax
0x140003aae  sub     dx, r8w
0x140003ab2  mov     qword ptr [rbp+57h+var_90], r12
0x140003ab6  mov     [rbp+57h+var_90+4], eax
0x140003ab9  test    r15b, dl
0x140003abc  jnz     loc_140003ED3
0x140003ac2  cmp     r12w, dx
0x140003ac6  ja      loc_140003ED3
0x140003acc  mov     eax, 0FFFEh
0x140003ad1  cmp     dx, ax
0x140003ad4  ja      loc_140003ED3
0x140003ada  mov     rax, cs:stru_140019640.Buffer
0x140003ae1  mov     ecx, r8d
0x140003ae4  shr     rcx, 1
0x140003ae7  lea     r10, [rax+rcx*2]
0x140003aeb  test    r10, r10
0x140003aee  jnz     short loc_140003AF9
0x140003af0  test    dx, dx
0x140003af3  jnz     loc_140003ED3
0x140003af9  mov     rax, [rbp+57h+Format]
0x140003afd  mov     edi, 80000005h
0x140003b02  movzx   ebx, dx
0x140003b05  shr     rbx, 1
0x140003b08  jnz     short loc_140003B29
0x140003b0a  mov     rdx, r12
0x140003b0d  mov     ecx, r12d
0x140003b10  cmp     [rax], r12w
0x140003b14  jz      short loc_140003B5F
0x140003b16  neg     r10
0x140003b19  sbb     ecx, ecx
0x140003b1b  and     ecx, 0BFFFFFF8h
0x140003b21  add     ecx, 0C000000Dh
0x140003b27  jmp     short loc_140003B5F
0x140003b29  mov     r9, r11; Args
0x140003b2c  mov     r8, rax; Format
0x140003b2f  mov     rdx, rbx; Count
0x140003b32  mov     rcx, r10; Dest
0x140003b35  call    cs:__imp__vsnwprintf
0x140003b3c  nop     dword ptr [rax+rax+00h]
0x140003b41  test    eax, eax
0x140003b43  js      short loc_140003B52
0x140003b45  movsxd  rdx, eax
0x140003b48  cmp     rdx, rbx
0x140003b4b  ja      short loc_140003B52
0x140003b4d  mov     ecx, r12d
0x140003b50  jmp     short loc_140003B57
0x140003b52  mov     rdx, rbx
0x140003b55  mov     ecx, edi
0x140003b57  movzx   r8d, cs:stru_140019640.Length
0x140003b5f  add     dx, dx
0x140003b62  mov     eax, r12d
0x140003b65  cmp     ecx, edi
0x140003b67  cmovnz  eax, ecx
0x140003b6a  test    eax, eax
0x140003b6c  js      loc_140003ED3
0x140003b72  add     r8w, dx
0x140003b76  mov     rcx, rsi; Destination
0x140003b79  lea     rdx, Source; "\r\n"
0x140003b80  mov     cs:stru_140019640.Length, r8w
0x140003b88  call    cs:__imp_RtlAppendUnicodeToString
0x140003b8f  nop     dword ptr [rax+rax+00h]
0x140003b94  test    eax, eax
0x140003b96  js      loc_140003ED3
0x140003b9c  lea     rdx, [rbp+57h+Buffer]; DestinationString
0x140003ba0  mov     rcx, rsi; SourceString
0x140003ba3  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x140003ba8  test    eax, eax
0x140003baa  js      loc_140003ED3
0x140003bb0  lea     rcx, stru_140019608; FastMutex
0x140003bb7  call    cs:__imp_ExReleaseFastMutex
0x140003bbe  nop     dword ptr [rax+rax+00h]
0x140003bc3  xor     r9d, r9d; Alertable
0x140003bc6  mov     [rsp+0E0h+Timeout], r12; Timeout
0x140003bcb  xor     r8d, r8d; WaitMode
0x140003bce  lea     rcx, Object; Object
0x140003bd5  xor     edx, edx; WaitReason
0x140003bd7  mov     r15b, r12b
0x140003bda  call    cs:__imp_KeWaitForSingleObject
0x140003be1  nop     dword ptr [rax+rax+00h]
0x140003be6  cmp     cs:FileObject, r12
0x140003bed  mov     r14b, 1
0x140003bf0  jz      loc_140003E29
0x140003bf6  cmp     cs:Instance, r12
0x140003bfd  jz      loc_140003E29
0x140003c03  call    cs:__imp_KeGetCurrentIrql
0x140003c0a  nop     dword ptr [rax+rax+00h]
0x140003c0f  test    al, al
0x140003c11  jnz     loc_140003E29
0x140003c17  mov     rbx, r12
0x140003c1a  mov     [rbp+57h+var_90], r12d
0x140003c1e  mov     rsi, r12
0x140003c21  lea     rdi, qword_140019540
0x140003c28  cmp     cs:qword_140019540, rdi
0x140003c2f  mov     rax, cs:qword_140019578
0x140003c36  jz      loc_140003D58
0x140003c3c  test    rax, rax
0x140003c3f  jz      short loc_140003C82
0x140003c41  mov     rcx, cs:qword_140019580
0x140003c48  mov     rax, cs:qword_140019578
0x140003c4f  cmp     rax, rcx
0x140003c52  jb      short loc_140003C67
0x140003c54  movzx   ecx, cs:stru_140019640.Length
0x140003c5b  mov     rax, cs:qword_140019580
0x140003c62  cmp     rax, rcx
0x140003c65  ja      short loc_140003C82
0x140003c67  call    SplitLogFile
0x140003c6c  test    eax, eax
0x140003c6e  js      loc_140003EA0
0x140003c74  mov     rax, cs:qword_140019578
0x140003c7b  mov     cs:qword_140019580, rax
0x140003c82  mov     rbx, cs:qword_140019540
0x140003c89  cmp     [rbx+8], rdi
0x140003c8d  jnz     loc_140003E6D
0x140003c93  mov     rax, [rbx]
0x140003c96  cmp     [rax+8], rbx
0x140003c9a  jnz     loc_140003E6D
0x140003ca0  mov     cs:qword_140019540, rax
0x140003ca7  xor     r8d, r8d; ByteOffset
0x140003caa  mov     [rax+8], rdi
0x140003cae  lea     rax, [rbp+57h+var_90]
0x140003cb2  movzx   r9d, word ptr [rbx+10h]; Length
0x140003cb7  mov     rdx, cs:FileObject; FileObject
0x140003cbe  mov     rcx, cs:Instance; InitiatingInstance
0x140003cc5  mov     [rsp+40h], r12; CallbackContext
0x140003cca  mov     [rsp+0E0h+CallbackRoutine], r12; CallbackRoutine
0x140003ccf  mov     [rsp+0E0h+BytesWritten], rax; BytesWritten
0x140003cd4  mov     rax, [rbx+18h]
0x140003cd8  mov     [rsp+0E0h+Flags], r12d; Flags
0x140003cdd  mov     [rsp+0E0h+Timeout], rax; Buffer
0x140003ce2  call    cs:__imp_FltWriteFile
0x140003ce9  nop     dword ptr [rax+rax+00h]
0x140003cee  test    eax, eax
0x140003cf0  js      loc_140003EA0
0x140003cf6  mov     eax, [rbp+57h+var_90]
0x140003cf9  mov     rcx, [rbx+18h]; P
0x140003cfd  add     rsi, rax
0x140003d00  test    rcx, rcx
0x140003d03  jz      short loc_140003D18
0x140003d05  mov     edx, r13d; Tag
0x140003d08  call    cs:__imp_ExFreePoolWithTag
0x140003d0f  nop     dword ptr [rax+rax+00h]
0x140003d14  mov     [rbx+18h], r12
0x140003d18  test    rbx, rbx
0x140003d1b  jz      short loc_140003D32
0x140003d1d  mov     edx, r13d; Tag
0x140003d20  mov     rcx, rbx; P
0x140003d23  call    cs:__imp_ExFreePoolWithTag
0x140003d2a  nop     dword ptr [rax+rax+00h]
0x140003d2f  mov     rbx, r12
0x140003d32  mov     rax, cs:qword_140019580
0x140003d39  test    rax, rax
0x140003d3c  jz      loc_140003C28
0x140003d42  mov     rax, cs:qword_140019580
0x140003d49  sub     rax, rsi
0x140003d4c  mov     cs:qword_140019580, rax
0x140003d53  jmp     loc_140003C28
0x140003d58  test    rax, rax
0x140003d5b  jz      short loc_140003D9E
0x140003d5d  mov     rcx, cs:qword_140019580
0x140003d64  mov     rax, cs:qword_140019578
0x140003d6b  cmp     rax, rcx
0x140003d6e  jb      short loc_140003D83
0x140003d70  movzx   ecx, cs:stru_140019640.Length
0x140003d77  mov     rax, cs:qword_140019580
0x140003d7e  cmp     rax, rcx
0x140003d81  ja      short loc_140003D9E
0x140003d83  call    SplitLogFile
0x140003d88  test    eax, eax
0x140003d8a  js      loc_140003EA0
0x140003d90  mov     rax, cs:qword_140019578
0x140003d97  mov     cs:qword_140019580, rax
0x140003d9e  movzx   r9d, word ptr [rbp+57h+Buffer]; Length
0x140003da3  lea     rax, [rbp+57h+var_90]
0x140003da7  mov     rdx, cs:FileObject; FileObject
0x140003dae  xor     r8d, r8d; ByteOffset
0x140003db1  mov     rcx, cs:Instance; InitiatingInstance
0x140003db8  mov     [rsp+40h], r12; CallbackContext
0x140003dbd  mov     [rsp+0E0h+CallbackRoutine], r12; CallbackRoutine
0x140003dc2  mov     [rsp+0E0h+BytesWritten], rax; BytesWritten
0x140003dc7  mov     rax, [rbp+57h+Buffer+8]
0x140003dcb  mov     [rsp+0E0h+Flags], r12d; Flags
0x140003dd0  mov     [rsp+0E0h+Timeout], rax; Buffer
0x140003dd5  mov     [rbp+57h+var_90], r12d
0x140003dd9  call    cs:__imp_FltWriteFile
0x140003de0  nop     dword ptr [rax+rax+00h]
0x140003de5  test    eax, eax
0x140003de7  js      loc_140003EA0
0x140003ded  mov     rdx, cs:FileObject; FileObject
0x140003df4  mov     rcx, cs:Instance; Instance
0x140003dfb  mov     edi, [rbp+57h+var_90]
0x140003dfe  call    cs:__imp_FltFlushBuffers
0x140003e05  nop     dword ptr [rax+rax+00h]
0x140003e0a  mov     rax, cs:qword_140019580
0x140003e11  test    rax, rax
0x140003e14  jz      short loc_140003E88
0x140003e16  mov     rax, cs:qword_140019580
0x140003e1d  sub     rax, rdi
0x140003e20  mov     cs:qword_140019580, rax
0x140003e27  jmp     short loc_140003E88
0x140003e29  mov     edx, 20h ; ' '; NumberOfBytes
0x140003e2e  mov     r8d, r13d; Tag
0x140003e31  lea     ecx, [rdx-1Fh]; PoolType
0x140003e34  call    cs:__imp_ExAllocatePoolWithTag
0x140003e3b  nop     dword ptr [rax+rax+00h]
0x140003e40  test    rax, rax
0x140003e43  jz      loc_140003ED3
0x140003e49  movaps  xmm0, xmmword ptr [rbp+57h+Buffer]
0x140003e4d  lea     rdi, qword_140019540
0x140003e54  movdqu  xmmword ptr [rax+10h], xmm0
0x140003e59  mov     rcx, cs:qword_140019548
0x140003e60  xorps   xmm1, xmm1
0x140003e63  movdqa  xmmword ptr [rbp+57h+Buffer], xmm1
0x140003e68  cmp     [rcx], rdi
0x140003e6b  jz      short loc_140003E74
0x140003e6d  mov     ecx, 3
0x140003e72  int     29h; Win8: RtlFailFast(ecx)
0x140003e74  mov     [rax], rdi
0x140003e77  mov     rbx, r12
0x140003e7a  mov     [rax+8], rcx
0x140003e7e  mov     [rcx], rax
  ... truncated ...
```
