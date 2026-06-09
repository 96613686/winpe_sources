# WofInflateFile

- ea: `0x140036904`
- end: `0x140036e19`
- name: `WofInflateFile`
- size: `1301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1400338e0`
- `0x140036160`
- `0x1400364f0`
- `0x14003b550`
- `0x14003e820`

## callees

- `0x14000b4a4`
- `0x14000dc88`
- `0x14000de64`
- `0x14000ed74`
- `0x140011560`
- `0x140011640`
- `0x1400119c0`
- `0x140036620`
- `0x140036904`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140036bb0`
- `ntoskrnl!KeDelayExecutionThread` at `0x140036bb0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036c47`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036cbe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036c47`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036cbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036d91`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a2e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a2e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036c29`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036ca0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036c29`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036ca0`
- `FLTMGR!FltWriteFile` at `0x140036b8b`
- `FLTMGR!FltWriteFile` at `0x140036b8b`
- `FLTMGR!FltSetInformationFile` at `0x140036a9d`
- `FLTMGR!FltSetInformationFile` at `0x140036dd5`
- `FLTMGR!FltSetInformationFile` at `0x140036a9d`
- `FLTMGR!FltSetInformationFile` at `0x140036dd5`
- `FLTMGR!FltFsControlFile` at `0x140036c8d`
- `FLTMGR!FltFsControlFile` at `0x140036c8d`

## pseudocode

```c
__int64 __fastcall WofInflateFile(__int64 a1, __int64 a2, _DWORD *a3, char a4)
{
  __int64 v4; // rax
  _DWORD *v5; // r12
  __int64 v6; // rdi
  __int64 (__fastcall *v10)(_DWORD *); // rax
  __int64 result; // rax
  __int64 *v12; // rdx
  unsigned int v13; // ebx
  char *PoolWithTag; // r15
  struct _FILE_OBJECT *v15; // rdx
  struct _FLT_INSTANCE *v16; // rcx
  __int64 v17; // rdx
  union _LARGE_INTEGER v18; // rcx
  int v19; // edx
  NTSTATUS v20; // edi
  int v21; // r9d
  int v22; // edx
  struct _FLT_INSTANCE *v23; // rcx
  int v24; // r9d
  struct _FILE_OBJECT *v25; // rdx
  struct _FLT_INSTANCE *v26; // rcx
  int Flags; // [rsp+28h] [rbp-81h]
  __int64 v28; // [rsp+60h] [rbp-49h] BYREF
  __int64 v29; // [rsp+68h] [rbp-41h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp-39h] BYREF
  ULONG BytesWritten; // [rsp+78h] [rbp-31h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp-29h] BYREF
  __int128 InputBuffer; // [rsp+88h] [rbp-21h] BYREF
  __m128i FileInformation; // [rsp+98h] [rbp-11h] BYREF
  __m128i v35; // [rsp+A8h] [rbp-1h]
  __int64 v36; // [rsp+B8h] [rbp+Fh]

  *(_QWORD *)&InputBuffer = a1;
  v28 = 0;
  v36 = 0;
  v4 = (unsigned int)a3[3];
  v5 = a3 + 16;
  ByteOffset.QuadPart = 0;
  v6 = a1;
  v29 = 0;
  FileInformation = 0;
  v35 = 0;
  BytesWritten = 0;
  v10 = (__int64 (__fastcall *)(_DWORD *))*((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v4 + 36);
  if ( v10 )
  {
    result = v10(a3 + 16);
    if ( (int)result < 0 )
      return result;
  }
  v12 = WPP_0d3c4c833653390108f193f53084a201_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qZ(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v12,
      10,
      11,
      (__int64)WPP_0d3c4c833653390108f193f53084a201_Traceguids,
      *(_QWORD *)(a2 + 32),
      *(_QWORD *)(a2 + 32) + 88LL);
  }
  result = (*((__int64 (__fastcall **)(_DWORD *, __int64 *, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
            + 53 * (unsigned int)a3[3]
            + 40))(
             v5,
             &v28,
             0);
  if ( (int)result < 0 )
    return result;
  v13 = 0x1000000;
  if ( v28 < 0x1000000 )
    v13 = (v28 + 4095) & 0xFFFFF000;
  while ( 1 )
  {
    PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v13, 0x49666F57u);
    if ( PoolWithTag )
      break;
    if ( v13 <= 0x8000 )
      return 3221225626LL;
    v13 = ((v13 >> 2) + 0x7FFF) & 0xFFFF8000;
  }
  if ( a4 )
  {
    v15 = *(struct _FILE_OBJECT **)(a2 + 32);
    v16 = *(struct _FLT_INSTANCE **)(a2 + 24);
    FileInformation = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    LODWORD(v36) = 0;
    v35 = FileInformation;
    FltSetInformationFile(v16, v15, &FileInformation, 0x28u, FileBasicInformation);
  }
  v17 = v28;
  v18.QuadPart = 0;
  while ( 1 )
  {
    ByteOffset = v18;
    if ( !v17 )
    {
      (*((void (__fastcall **)(_DWORD *, __int64 *, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
       + 53 * (unsigned int)a3[3]
       + 40))(
        v5,
        &v28,
        0);
      if ( v28 >= 4096 || (v20 = WofFlushFile(v6, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), 0, 0), v20 >= 0) )
      {
        v20 = WofMarkFileAsInflated(a2, a3);
        goto LABEL_37;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v24 = 14;
LABEL_31:
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        10,
        v24,
        (__int64)WPP_0d3c4c833653390108f193f53084a201_Traceguids,
        v20);
      goto LABEL_37;
    }
    if ( v17 < v13 )
      v13 = v17;
    LOBYTE(Flags) = 1;
    v20 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD *, int, union _LARGE_INTEGER, unsigned int, char *, _QWORD, __int64 *))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
           + 53 * (unsigned int)a3[3]
           + 30))(
            v6,
            0,
            0,
            *(_QWORD *)(a2 + 24),
            v5,
            Flags,
            v18,
            v13,
            PoolWithTag,
            0,
            &v29);
    if ( v20 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v24 = 12;
      goto LABEL_31;
    }
    v21 = v29;
    if ( (v29 & 0xFFF) != 0 )
    {
      memset(&PoolWithTag[v29], 0, 4096 - (v29 & 0xFFF));
      goto LABEL_21;
    }
    while ( 1 )
    {
      v20 = FltWriteFile(
              *(PFLT_INSTANCE *)(a2 + 24),
              *(PFILE_OBJECT *)(a2 + 32),
              &ByteOffset,
              (v21 + 4095) & 0xFFFFF000,
              PoolWithTag,
              0xFu,
              &BytesWritten,
              0,
              0);
      if ( v20 != -1073741740 )
        break;
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 1u, &Interval);
LABEL_21:
      v21 = v29;
    }
    if ( v20 < 0 )
      break;
    v17 = v28 - v29;
    v18.QuadPart = v29 + ByteOffset.QuadPart;
    v6 = InputBuffer;
    v28 -= v29;
  }
  InputBuffer = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      10,
      13,
      (__int64)WPP_0d3c4c833653390108f193f53084a201_Traceguids,
      v20);
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
  a3[2] |= 0x10u;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
  *((_QWORD *)&InputBuffer + 1) = v28 + ByteOffset.QuadPart;
  v23 = *(struct _FLT_INSTANCE **)(a2 + 24);
  *(_QWORD *)&InputBuffer = 0;
  FltFsControlFile(v23, *(PFILE_OBJECT *)(a2 + 32), 0x980C8u, &InputBuffer, 0x10u, 0, 0, 0);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
  a3[2] &= ~0x10u;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
LABEL_37:
  ExFreePoolWithTag(PoolWithTag, 0);
  if ( a4 )
  {
    v25 = *(struct _FILE_OBJECT **)(a2 + 32);
    v26 = *(struct _FLT_INSTANCE **)(a2 + 24);
    FileInformation = _mm_load_si128((const __m128i *)&_xmm_fffffffffffffffefffffffffffffffe);
    LODWORD(v36) = 0;
    v35 = FileInformation;
    FltSetInformationFile(v26, v25, &FileInformation, 0x28u, FileBasicInformation);
  }
  WofInflateTelemetry(a3, a2, (unsigned int)v20);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140036904  mov     [rsp-8+arg_18], rbx
0x140036909  push    rbp
0x14003690a  push    rsi
0x14003690b  push    rdi
0x14003690c  push    r12
0x14003690e  push    r13
0x140036910  push    r14
0x140036912  push    r15
0x140036914  lea     rbp, [rsp-27h]
0x140036919  sub     rsp, 0D0h
0x140036920  mov     rax, cs:__security_cookie
0x140036927  xor     rax, rsp
0x14003692a  mov     [rbp+57h+var_40], rax
0x14003692e  xor     ebx, ebx
0x140036930  mov     qword ptr [rbp+57h+InputBuffer], rcx
0x140036934  xor     eax, eax
0x140036936  mov     [rbp+57h+var_A0], rbx
0x14003693a  mov     [rbp+57h+var_48], rax
0x14003693e  lea     r15, WPP_MAIN_CB.Queue+10h
0x140036945  mov     eax, [r8+0Ch]
0x140036949  lea     r12, [r8+40h]
0x14003694d  xorps   xmm0, xmm0
0x140036950  mov     qword ptr [rbp+57h+ByteOffset], rbx
0x140036954  mov     rdi, rcx
0x140036957  mov     [rbp+57h+var_98], rbx
0x14003695b  imul    rcx, rax, 1A8h
0x140036962  movups  [rbp+57h+FileInformation], xmm0
0x140036966  movups  [rbp+57h+var_58], xmm0
0x14003696a  mov     r13b, r9b
0x14003696d  mov     [rbp+57h+var_88], ebx
0x140036970  mov     r14, r8
0x140036973  mov     rsi, rdx
0x140036976  mov     rax, [rcx+r15+120h]
0x14003697e  test    rax, rax
0x140036981  jz      short loc_140036993
0x140036983  mov     rcx, r12
0x140036986  call    _guard_dispatch_icall
0x14003698b  test    eax, eax
0x14003698d  js      loc_140036DF1
0x140036993  lea     rax, WPP_RECORDER_INITIALIZED
0x14003699a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400369a1  lea     rdx, WPP_0d3c4c833653390108f193f53084a201_Traceguids
0x1400369a8  jz      short loc_1400369DD
0x1400369aa  mov     rcx, [rsi+20h]
0x1400369ae  mov     r9d, 0Bh
0x1400369b4  lea     rax, [rcx+58h]
0x1400369b8  mov     [rsp+100h+BytesWritten], rax
0x1400369bd  lea     r8d, [r9-1]
0x1400369c1  mov     qword ptr [rsp+100h+Flags], rcx
0x1400369c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400369cd  mov     qword ptr [rsp+100h+FileInformationClass], rdx
0x1400369d2  mov     dl, 4
0x1400369d4  mov     rcx, [rcx+40h]
0x1400369d8  call    WPP_RECORDER_SF_qZ
0x1400369dd  mov     eax, [r14+0Ch]
0x1400369e1  lea     rdx, [rbp+57h+var_A0]
0x1400369e5  imul    rcx, rax, 1A8h
0x1400369ec  xor     r8d, r8d
0x1400369ef  mov     rax, [rcx+r15+140h]
0x1400369f7  mov     rcx, r12
0x1400369fa  call    _guard_dispatch_icall
0x1400369ff  test    eax, eax
0x140036a01  js      loc_140036DF1
0x140036a07  mov     rax, [rbp+57h+var_A0]
0x140036a0b  mov     ebx, 1000000h
0x140036a10  cmp     rax, rbx
0x140036a13  jge     short loc_140036A21
0x140036a15  lea     ebx, [rax+0FFFh]
0x140036a1b  and     ebx, 0FFFFF000h
0x140036a21  mov     edx, ebx; NumberOfBytes
0x140036a23  mov     ecx, 1; PoolType
0x140036a28  mov     r8d, 49666F57h; Tag
0x140036a2e  call    cs:__imp_ExAllocatePoolWithTag
0x140036a35  nop     dword ptr [rax+rax+00h]
0x140036a3a  mov     r15, rax
0x140036a3d  test    rax, rax
0x140036a40  jnz     short loc_140036A65
0x140036a42  cmp     ebx, 8000h
0x140036a48  jbe     short loc_140036A5B
0x140036a4a  shr     ebx, 2
0x140036a4d  add     ebx, 7FFFh
0x140036a53  and     ebx, 0FFFF8000h
0x140036a59  jmp     short loc_140036A21
0x140036a5b  mov     eax, 0C000009Ah
0x140036a60  jmp     loc_140036DF1
0x140036a65  test    r13b, r13b
0x140036a68  jz      short loc_140036AA9
0x140036a6a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140036a72  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140036a76  mov     rdx, [rsi+20h]; FileObject
0x140036a7a  mov     r9d, 28h ; '('; Length
0x140036a80  mov     rcx, [rsi+18h]; Instance
0x140036a84  movdqu  [rbp+57h+FileInformation], xmm0
0x140036a89  mov     dword ptr [rbp+57h+var_48], 0
0x140036a90  movdqu  [rbp+57h+var_58], xmm0
0x140036a95  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140036a9d  call    cs:__imp_FltSetInformationFile
0x140036aa4  nop     dword ptr [rax+rax+00h]
0x140036aa9  mov     rdx, [rbp+57h+var_A0]
0x140036aad  xor     ecx, ecx
0x140036aaf  mov     qword ptr [rbp+57h+ByteOffset], rcx
0x140036ab3  test    rdx, rdx
0x140036ab6  jz      loc_140036D13
0x140036abc  mov     r9, [rsi+18h]
0x140036ac0  mov     eax, ebx
0x140036ac2  cmp     rdx, rax
0x140036ac5  mov     eax, [r14+0Ch]
0x140036ac9  cmovl   ebx, edx
0x140036acc  xor     r8d, r8d
0x140036acf  imul    rdx, rax, 1A8h
0x140036ad6  lea     rax, WPP_MAIN_CB.Queue+10h
0x140036add  mov     rax, [rdx+rax+0F0h]
0x140036ae5  lea     rdx, [rbp+57h+var_98]
0x140036ae9  mov     [rsp+100h+var_B0], rdx
0x140036aee  xor     edx, edx
0x140036af0  mov     [rsp+100h+var_B8], 0
0x140036af9  mov     [rsp+100h+CallbackContext], r15
0x140036afe  mov     dword ptr [rsp+100h+CallbackRoutine], ebx
0x140036b02  mov     [rsp+100h+BytesWritten], rcx
0x140036b07  mov     rcx, rdi
0x140036b0a  mov     byte ptr [rsp+100h+Flags], 1
0x140036b0f  mov     qword ptr [rsp+100h+FileInformationClass], r12
0x140036b14  call    _guard_dispatch_icall
0x140036b19  mov     edi, eax
0x140036b1b  test    eax, eax
0x140036b1d  js      loc_140036CCF
0x140036b23  mov     r9, [rbp+57h+var_98]
0x140036b27  mov     rax, r9
0x140036b2a  and     eax, 0FFFh
0x140036b2f  jz      short loc_140036B49
0x140036b31  mov     r8d, 1000h
0x140036b37  lea     rcx, [r9+r15]; void *
0x140036b3b  sub     r8, rax; Size
0x140036b3e  xor     edx, edx; Val
0x140036b40  call    memset
0x140036b45  mov     r9, [rbp+57h+var_98]
0x140036b49  mov     rdx, [rsi+20h]; FileObject
0x140036b4d  lea     rax, [rbp+57h+var_88]
0x140036b51  mov     rcx, [rsi+18h]; InitiatingInstance
0x140036b55  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x140036b59  mov     [rsp+100h+CallbackContext], 0; CallbackContext
0x140036b62  add     r9d, 0FFFh
0x140036b69  mov     [rsp+100h+CallbackRoutine], 0; CallbackRoutine
0x140036b72  and     r9d, 0FFFFF000h; Length
0x140036b79  mov     [rsp+100h+BytesWritten], rax; BytesWritten
0x140036b7e  mov     [rsp+100h+Flags], 0Fh; Flags
0x140036b86  mov     qword ptr [rsp+100h+FileInformationClass], r15; Buffer
0x140036b8b  call    cs:__imp_FltWriteFile
0x140036b92  nop     dword ptr [rax+rax+00h]
0x140036b97  mov     edi, eax
0x140036b99  cmp     eax, 0C0000054h
0x140036b9e  jnz     short loc_140036BBE
0x140036ba0  lea     r8, [rbp+57h+Interval]; Interval
0x140036ba4  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFE7960h
0x140036bac  mov     dl, 1; Alertable
0x140036bae  xor     ecx, ecx; WaitMode
0x140036bb0  call    cs:__imp_KeDelayExecutionThread
0x140036bb7  nop     dword ptr [rax+rax+00h]
0x140036bbc  jmp     short loc_140036B45
0x140036bbe  test    edi, edi
0x140036bc0  js      short loc_140036BDF
0x140036bc2  mov     rdx, [rbp+57h+var_A0]
0x140036bc6  sub     rdx, [rbp+57h+var_98]
0x140036bca  mov     rcx, qword ptr [rbp+57h+ByteOffset]
0x140036bce  add     rcx, [rbp+57h+var_98]
0x140036bd2  mov     rdi, qword ptr [rbp+57h+InputBuffer]
0x140036bd6  mov     [rbp+57h+var_A0], rdx
0x140036bda  jmp     loc_140036AAF
0x140036bdf  xorps   xmm0, xmm0
0x140036be2  movups  [rbp+57h+InputBuffer], xmm0
0x140036be6  lea     rax, WPP_RECORDER_INITIALIZED
0x140036bed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036bf4  jz      short loc_140036C22
0x140036bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140036bfd  lea     rax, WPP_0d3c4c833653390108f193f53084a201_Traceguids
0x140036c04  mov     r9d, 0Dh
0x140036c0a  mov     [rsp+100h+Flags], edi
0x140036c0e  mov     dl, 2
0x140036c10  mov     qword ptr [rsp+100h+FileInformationClass], rax
0x140036c15  mov     rcx, [rcx+40h]
0x140036c19  lea     r8d, [r9-3]
0x140036c1d  call    WPP_RECORDER_SF_d
0x140036c22  mov     rcx, [r14]
0x140036c25  add     rcx, 20h ; ' '; FastMutex
0x140036c29  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140036c30  nop     dword ptr [rax+rax+00h]
0x140036c35  mov     eax, [r14+8]
0x140036c39  or      eax, 10h
0x140036c3c  mov     [r14+8], eax
0x140036c40  mov     rcx, [r14]
0x140036c43  add     rcx, 20h ; ' '; FastMutex
0x140036c47  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140036c4e  nop     dword ptr [rax+rax+00h]
0x140036c53  mov     rcx, qword ptr [rbp+57h+ByteOffset]
0x140036c57  lea     r9, [rbp+57h+InputBuffer]; InputBuffer
0x140036c5b  add     rcx, [rbp+57h+var_A0]
0x140036c5f  xor     edx, edx
0x140036c61  mov     [rsp+100h+CallbackRoutine], rdx; LengthReturned
0x140036c66  mov     r8d, 980C8h; FsControlCode
0x140036c6c  mov     dword ptr [rsp+100h+BytesWritten], edx; OutputBufferLength
0x140036c70  mov     qword ptr [rsp+100h+Flags], rdx; OutputBuffer
0x140036c75  mov     qword ptr [rbp+57h+InputBuffer+8], rcx
0x140036c79  mov     rcx, [rsi+18h]; Instance
0x140036c7d  mov     qword ptr [rbp+57h+InputBuffer], rdx
0x140036c81  mov     rdx, [rsi+20h]; FileObject
0x140036c85  mov     [rsp+100h+FileInformationClass], 10h; InputBufferLength
0x140036c8d  call    cs:__imp_FltFsControlFile
0x140036c94  nop     dword ptr [rax+rax+00h]
0x140036c99  mov     rcx, [r14]
0x140036c9c  add     rcx, 20h ; ' '; FastMutex
0x140036ca0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140036ca7  nop     dword ptr [rax+rax+00h]
0x140036cac  mov     eax, [r14+8]
0x140036cb0  and     eax, 0FFFFFFEFh
0x140036cb3  mov     [r14+8], eax
0x140036cb7  mov     rcx, [r14]
0x140036cba  add     rcx, 20h ; ' '; FastMutex
0x140036cbe  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140036cc5  nop     dword ptr [rax+rax+00h]
0x140036cca  jmp     loc_140036D8C
0x140036ccf  lea     rax, WPP_RECORDER_INITIALIZED
0x140036cd6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036cdd  jz      loc_140036D8C
0x140036ce3  mov     r9d, 0Ch
0x140036ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x140036cf0  lea     rax, WPP_0d3c4c833653390108f193f53084a201_Traceguids
0x140036cf7  mov     [rsp+100h+Flags], edi
0x140036cfb  mov     r8d, 0Ah
0x140036d01  mov     dl, 2
0x140036d03  mov     qword ptr [rsp+100h+FileInformationClass], rax
0x140036d08  mov     rcx, [rcx+40h]
0x140036d0c  call    WPP_RECORDER_SF_d
0x140036d11  jmp     short loc_140036D8C
0x140036d13  mov     eax, [r14+0Ch]
0x140036d17  xor     r8d, r8d
0x140036d1a  imul    rdx, rax, 1A8h
0x140036d21  lea     rax, WPP_MAIN_CB.Queue+10h
0x140036d28  mov     rcx, r12
0x140036d2b  mov     rax, [rdx+rax+140h]
0x140036d33  lea     rdx, [rbp+57h+var_A0]
0x140036d37  call    _guard_dispatch_icall
0x140036d3c  cmp     [rbp+57h+var_A0], 1000h
0x140036d44  jge     short loc_140036D7F
0x140036d46  mov     r8, [rsi+20h]
0x140036d4a  xor     r9d, r9d
0x140036d4d  mov     rdx, [rsi+18h]
0x140036d51  mov     rcx, rdi
0x140036d54  mov     byte ptr [rsp+100h+FileInformationClass], 0
0x140036d59  call    WofFlushFile
0x140036d5e  mov     edi, eax
0x140036d60  test    eax, eax
0x140036d62  jns     short loc_140036D7F
0x140036d64  lea     rax, WPP_RECORDER_INITIALIZED
0x140036d6b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036d72  jz      short loc_140036D8C
0x140036d74  mov     r9d, 0Eh
0x140036d7a  jmp     loc_140036CE9
0x140036d7f  mov     rdx, r14
0x140036d82  mov     rcx, rsi
0x140036d85  call    WofMarkFileAsInflated
0x140036d8a  mov     edi, eax
0x140036d8c  xor     edx, edx; Tag
0x140036d8e  mov     rcx, r15; P
0x140036d91  call    cs:__imp_ExFreePoolWithTag
0x140036d98  nop     dword ptr [rax+rax+00h]
0x140036d9d  test    r13b, r13b
0x140036da0  jz      short loc_140036DE1
0x140036da2  movdqa  xmm0, cs:__xmm@fffffffffffffffefffffffffffffffe
0x140036daa  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140036dae  mov     rdx, [rsi+20h]; FileObject
0x140036db2  mov     r9d, 28h ; '('; Length
0x140036db8  mov     rcx, [rsi+18h]; Instance
0x140036dbc  movdqu  [rbp+57h+FileInformation], xmm0
0x140036dc1  mov     dword ptr [rbp+57h+var_48], 0
0x140036dc8  movdqu  [rbp+57h+var_58], xmm0
0x140036dcd  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140036dd5  call    cs:__imp_FltSetInformationFile
0x140036ddc  nop     dword ptr [rax+rax+00h]
0x140036de1  mov     r8d, edi
0x140036de4  mov     rdx, rsi
0x140036de7  mov     rcx, r14
0x140036dea  call    WofInflateTelemetry
0x140036def  mov     eax, edi
0x140036df1  mov     rcx, [rbp+57h+var_40]
0x140036df5  xor     rcx, rsp; StackCookie
0x140036df8  call    __security_check_cookie
0x140036dfd  mov     rbx, [rsp+100h+arg_18]
0x140036e05  add     rsp, 0D0h
0x140036e0c  pop     r15
0x140036e0e  pop     r14
0x140036e10  pop     r13
0x140036e12  pop     r12
0x140036e14  pop     rdi
0x140036e15  pop     rsi
0x140036e16  pop     rbp
0x140036e17  retn
```
