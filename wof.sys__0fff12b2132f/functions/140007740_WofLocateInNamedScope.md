# WofLocateInNamedScope

- ea: `0x140007740`
- end: `0x140007870`
- name: `WofLocateInNamedScope`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140033180`
- `0x1400350c8`

## callees

- `0x140007740`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14000781e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000781e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140007807`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140007807`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000783b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000783b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400077c7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400077c7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000784c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000784c`
- `FLTMGR!FltGetFileNameInformation` at `0x1400077a6`
- `FLTMGR!FltGetFileNameInformation` at `0x1400077a6`

## pseudocode

```c
NTSTATUS __fastcall WofLocateInNamedScope(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FAST_MUTEX *a2,
        struct _LIST_ENTRY **a3)
{
  NTSTATUS result; // eax
  struct _LIST_ENTRY **p_Blink; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  UCHAR OperationFlags; // r15
  BOOLEAN v9; // r15
  struct _LIST_ENTRY *v10; // rbp
  struct _LIST_ENTRY *i; // r14
  const UNICODE_STRING *v12; // rcx
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return -1073741772;
  p_Blink = &a2[2].Event.Header.WaitListHead.Blink;
  if ( *p_Blink == (struct _LIST_ENTRY *)p_Blink )
    return -1073741772;
  Iopb = a1->Iopb;
  FileNameInformation = 0;
  String2 = 0;
  OperationFlags = Iopb->OperationFlags;
  result = FltGetFileNameInformation(a1, 0x4000101u, &FileNameInformation);
  if ( result >= 0 )
  {
    v9 = (unsigned __int8)~OperationFlags >> 7;
    v10 = 0;
    ExAcquireFastMutexUnsafe(a2);
    for ( i = *p_Blink; i != (struct _LIST_ENTRY *)p_Blink; v10 = 0 )
    {
      v12 = (const UNICODE_STRING *)&i[1].Blink;
      if ( FileNameInformation->Name.Length > LOWORD(i[1].Blink) )
      {
        String2 = FileNameInformation->Name;
        String2.Length = v12->Length;
        if ( !RtlCompareUnicodeString(v12, &String2, v9) )
        {
          v10 = i;
          if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)&i[1]) )
            break;
        }
      }
      i = i->Flink;
    }
    ExReleaseFastMutexUnsafe(a2);
    FltReleaseFileNameInformation(FileNameInformation);
    if ( v10 )
    {
      *a3 = v10;
      return 0;
    }
    return -1073741772;
  }
  return result;
}

```

## disassembly

```asm
0x140007740  mov     [rsp+arg_10], rbx
0x140007745  mov     [rsp+arg_18], rbp
0x14000774a  push    rsi
0x14000774b  push    rdi
0x14000774c  push    r15
0x14000774e  sub     rsp, 30h
0x140007752  mov     rdi, r8
0x140007755  mov     rbx, rdx
0x140007758  test    rdx, rdx
0x14000775b  jnz     short loc_140007776
0x14000775d  mov     eax, 0C0000034h
0x140007762  mov     rbx, [rsp+48h+arg_10]
0x140007767  mov     rbp, [rsp+48h+arg_18]
0x14000776c  add     rsp, 30h
0x140007770  pop     r15
0x140007772  pop     rdi
0x140007773  pop     rsi
0x140007774  retn
0x140007776  lea     rsi, [rdx+98h]
0x14000777d  cmp     [rsi], rsi
0x140007780  jz      short loc_14000775D
0x140007782  mov     rax, [rcx+10h]
0x140007786  lea     r8, [rsp+48h+FileNameInformation]; FileNameInformation
0x14000778b  xorps   xmm0, xmm0
0x14000778e  mov     [rsp+48h+FileNameInformation], 0
0x140007797  movups  xmmword ptr [rsp+48h+String2.Length], xmm0
0x14000779c  mov     edx, 4000101h; NameOptions
0x1400077a1  movzx   r15d, byte ptr [rax+6]
0x1400077a6  call    cs:__imp_FltGetFileNameInformation
0x1400077ad  nop     dword ptr [rax+rax+00h]
0x1400077b2  test    eax, eax
0x1400077b4  js      short loc_140007762
0x1400077b6  not     r15b
0x1400077b9  mov     [rsp+48h+arg_0], r14
0x1400077be  mov     rcx, rbx; FastMutex
0x1400077c1  shr     r15b, 7
0x1400077c5  xor     ebp, ebp
0x1400077c7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400077ce  nop     dword ptr [rax+rax+00h]
0x1400077d3  mov     r14, [rsi]
0x1400077d6  cmp     r14, rsi
0x1400077d9  jz      short loc_140007838
0x1400077db  mov     rdx, [rsp+48h+FileNameInformation]
0x1400077e0  lea     rcx, [r14+18h]; String1
0x1400077e4  movzx   eax, word ptr [rcx]
0x1400077e7  cmp     [rdx+8], ax
0x1400077eb  jbe     short loc_14000782E
0x1400077ed  movups  xmm0, xmmword ptr [rdx+8]
0x1400077f1  movzx   r8d, r15b; CaseInSensitive
0x1400077f5  lea     rdx, [rsp+48h+String2]; String2
0x1400077fa  movups  xmmword ptr [rsp+48h+String2.Length], xmm0
0x1400077ff  movzx   eax, word ptr [rcx]
0x140007802  mov     [rsp+48h+String2.Length], ax
0x140007807  call    cs:__imp_RtlCompareUnicodeString
0x14000780e  nop     dword ptr [rax+rax+00h]
0x140007813  test    eax, eax
0x140007815  jnz     short loc_14000782E
0x140007817  lea     rcx, [r14+10h]; RunRef
0x14000781b  mov     rbp, r14
0x14000781e  call    cs:__imp_ExAcquireRundownProtection
0x140007825  nop     dword ptr [rax+rax+00h]
0x14000782a  test    al, al
0x14000782c  jnz     short loc_140007838
0x14000782e  mov     r14, [r14]
0x140007831  xor     ebp, ebp
0x140007833  cmp     r14, rsi
0x140007836  jnz     short loc_1400077DB
0x140007838  mov     rcx, rbx; FastMutex
0x14000783b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140007842  nop     dword ptr [rax+rax+00h]
0x140007847  mov     rcx, [rsp+48h+FileNameInformation]; FileNameInformation
0x14000784c  call    cs:__imp_FltReleaseFileNameInformation
0x140007853  nop     dword ptr [rax+rax+00h]
0x140007858  mov     r14, [rsp+48h+arg_0]
0x14000785d  test    rbp, rbp
0x140007860  jz      loc_14000775D
0x140007866  mov     [rdi], rbp
0x140007869  xor     eax, eax
0x14000786b  jmp     loc_140007762
```
