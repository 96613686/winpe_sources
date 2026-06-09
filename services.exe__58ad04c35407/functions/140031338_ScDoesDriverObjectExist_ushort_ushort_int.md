# ScDoesDriverObjectExist(ushort *,ushort *,int *)

- ea: `0x140031338`
- end: `0x14003160f`
- name: `?ScDoesDriverObjectExist@@YAKPEAG0PEAH@Z`
- size: `727`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, PCWSTR, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140072ed0`

## callees

- `0x140004c58`
- `0x14001f99c`
- `0x140021ef4`
- `0x140031338`

## import_xrefs

- `ntdll!NtClose` at `0x1400315d6`
- `ntdll!NtClose` at `0x1400315d6`
- `ntdll!RtlNtStatusToDosError` at `0x14003143b`
- `ntdll!RtlNtStatusToDosError` at `0x14003143b`
- `ntdll!RtlInitUnicodeString` at `0x1400313b4`
- `ntdll!RtlInitUnicodeString` at `0x140031490`
- `ntdll!RtlInitUnicodeString` at `0x1400313b4`
- `ntdll!RtlInitUnicodeString` at `0x140031490`
- `ntdll!RtlFreeHeap` at `0x140031539`
- `ntdll!RtlFreeHeap` at `0x1400315f3`
- `ntdll!RtlFreeHeap` at `0x140031539`
- `ntdll!RtlFreeHeap` at `0x1400315f3`
- `ntdll!NtQueryDirectoryObject` at `0x1400314bc`
- `ntdll!NtQueryDirectoryObject` at `0x1400314bc`
- `ntdll!NtOpenDirectoryObject` at `0x1400313e5`
- `ntdll!NtOpenDirectoryObject` at `0x1400313e5`
- `ntdll!RtlCompareUnicodeString` at `0x1400314ec`
- `ntdll!RtlCompareUnicodeString` at `0x1400314ec`
- `ntdll!RtlAllocateHeap` at `0x14003139b`
- `ntdll!RtlAllocateHeap` at `0x140031551`
- `ntdll!RtlAllocateHeap` at `0x14003139b`
- `ntdll!RtlAllocateHeap` at `0x140031551`

## pseudocode

```c
__int64 __fastcall ScDoesDriverObjectExist(PCWSTR SourceString, PCWSTR a2, int *a3)
{
  ULONG v4; // ebx
  ULONG v7; // r12d
  UNICODE_STRING *Heap; // r15
  NTSTATUS v9; // eax
  unsigned int v10; // edi
  PRPC_ASYNC_STATE v11; // rcx
  __int64 v12; // rdx
  int v13; // esi
  NTSTATUS v14; // eax
  const UNICODE_STRING *i; // r14
  ULONG Context; // [rsp+40h] [rbp-49h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-39h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-19h] BYREF
  ULONG ReturnLength; // [rsp+108h] [rbp+7Fh] BYREF

  DestinationString = 0;
  Context = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ReturnLength = 0;
  v4 = 8;
  FileHandle = 0;
  v7 = 0x2000;
  String2 = 0;
  Heap = (UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2000u);
  if ( Heap )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = NtOpenDirectoryObject(&FileHandle, 3u, &ObjectAttributes);
    v10 = v9;
    if ( v9 >= 0 )
    {
      RtlInitUnicodeString(&String2, a2);
      v13 = 0;
      while ( 1 )
      {
        v14 = NtQueryDirectoryObject(FileHandle, Heap, v7, 0, 1u, &Context, &ReturnLength);
        v10 = v14;
        if ( v14 == -2147483622 )
        {
          v13 = 0;
LABEL_36:
          *a3 = v13;
          goto LABEL_37;
        }
        if ( v14 < 0 )
          break;
        for ( i = Heap; i->Length; i += 2 )
        {
          if ( !RtlCompareUnicodeString(i, &String2, 1u) )
          {
            v13 = 1;
            break;
          }
        }
        if ( v10 != 261 || v13 )
          goto LABEL_36;
        if ( v7 + 512 < v7 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->StubInfo, 26, WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids);
          }
          v4 = 534;
          goto LABEL_38;
        }
        v7 += 512;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        Heap = (UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v7);
        if ( !Heap )
          goto LABEL_38;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v12 = 25;
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    if ( v9 != -1073741766 && v9 != -1073741772 )
    {
      if ( v9 != -1073741790 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v12 = 24;
LABEL_9:
          WPP_SF_d(v11->StubInfo, v12, WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids, v10);
        }
      }
LABEL_10:
      v4 = RtlNtStatusToDosError(v10);
      goto LABEL_38;
    }
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_dS(
        WPP_GLOBAL_Control->StubInfo,
        23,
        (unsigned int)WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids,
        v9,
        (__int64)SourceString);
    *a3 = 0;
LABEL_37:
    v4 = 0;
  }
LABEL_38:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v4;
}

```

## disassembly

```asm
0x140031338  push    rbp
0x14003133a  push    rbx
0x14003133b  push    rsi
0x14003133c  push    rdi
0x14003133d  push    r12
0x14003133f  push    r13
0x140031341  push    r14
0x140031343  push    r15
0x140031345  lea     rbp, [rsp-1Fh]
0x14003134a  sub     rsp, 0A8h
0x140031351  xorps   xmm0, xmm0
0x140031354  xor     eax, eax
0x140031356  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003135a  mov     [rbp+57h+var_A0], eax
0x14003135d  mov     rsi, rcx
0x140031360  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140031364  mov     [rbp+57h+arg_18], eax
0x140031367  lea     ebx, [rax+8]
0x14003136a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14003136e  mov     [rbp+57h+FileHandle], rax
0x140031372  mov     r13, r8
0x140031375  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140031379  mov     r14, rdx
0x14003137c  mov     r12d, 2000h
0x140031382  xorps   xmm1, xmm1
0x140031385  mov     r8d, r12d; Size
0x140031388  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x14003138c  mov     rcx, gs:60h
0x140031395  mov     edx, ebx; Flags
0x140031397  mov     rcx, [rcx+30h]; HeapHandle
0x14003139b  call    cs:__imp_RtlAllocateHeap
0x1400313a1  mov     r15, rax
0x1400313a4  test    rax, rax
0x1400313a7  jz      loc_1400315CD
0x1400313ad  mov     rdx, rsi; SourceString
0x1400313b0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400313b4  call    cs:__imp_RtlInitUnicodeString
0x1400313ba  xor     eax, eax
0x1400313bc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400313c3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400313c7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400313cb  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x1400313ce  lea     edx, [rbx-5]; DesiredAccess
0x1400313d1  lea     rax, [rbp+57h+DestinationString]
0x1400313d5  xorps   xmm0, xmm0
0x1400313d8  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400313dc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400313e0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400313e5  call    cs:__imp_NtOpenDirectoryObject
0x1400313eb  mov     edi, eax
0x1400313ed  test    eax, eax
0x1400313ef  jns     loc_140031489
0x1400313f5  cmp     eax, 0C000003Ah
0x1400313fa  jz      short loc_140031448
0x1400313fc  cmp     eax, 0C0000034h
0x140031401  jz      short loc_140031448
0x140031403  cmp     eax, 0C0000022h
0x140031408  jz      short loc_140031439
0x14003140a  mov     rcx, cs:WPP_GLOBAL_Control
0x140031411  lea     rdx, WPP_GLOBAL_Control
0x140031418  cmp     rcx, rdx
0x14003141b  jz      short loc_140031439
0x14003141d  test    byte ptr [rcx+1Ch], 1
0x140031421  jz      short loc_140031439
0x140031423  lea     edx, [rbx+10h]
0x140031426  mov     rcx, [rcx+10h]
0x14003142a  lea     r8, WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids
0x140031431  mov     r9d, edi
0x140031434  call    WPP_SF_d
0x140031439  mov     ecx, edi; Status
0x14003143b  call    cs:__imp_RtlNtStatusToDosError
0x140031441  mov     ebx, eax
0x140031443  jmp     loc_1400315CD
0x140031448  mov     rcx, cs:WPP_GLOBAL_Control
0x14003144f  lea     rdx, WPP_GLOBAL_Control
0x140031456  cmp     rcx, rdx
0x140031459  jz      short loc_14003147E
0x14003145b  test    byte ptr [rcx+1Ch], 4
0x14003145f  jz      short loc_14003147E
0x140031461  mov     rcx, [rcx+10h]
0x140031465  lea     r8, WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids
0x14003146c  mov     edx, 17h
0x140031471  mov     qword ptr [rsp+0E0h+RestartScan], rsi
0x140031476  mov     r9d, edi
0x140031479  call    WPP_SF_dS
0x14003147e  xor     ecx, ecx
0x140031480  mov     [r13+0], ecx
0x140031484  jmp     loc_1400315CB
0x140031489  mov     rdx, r14; SourceString
0x14003148c  lea     rcx, [rbp+57h+String2]; DestinationString
0x140031490  call    cs:__imp_RtlInitUnicodeString
0x140031496  xor     esi, esi
0x140031498  mov     rcx, [rbp+57h+FileHandle]; DirectoryHandle
0x14003149c  lea     rax, [rbp+57h+arg_18]
0x1400314a0  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1400314a5  xor     r9d, r9d; ReturnSingleEntry
0x1400314a8  lea     rax, [rbp+57h+var_A0]
0x1400314ac  mov     r8d, r12d; BufferLength
0x1400314af  mov     [rsp+0E0h+Context], rax; Context
0x1400314b4  mov     rdx, r15; Buffer
0x1400314b7  mov     [rsp+0E0h+RestartScan], 1; RestartScan
0x1400314bc  call    cs:__imp_NtQueryDirectoryObject
0x1400314c2  xor     ecx, ecx
0x1400314c4  mov     edi, eax
0x1400314c6  cmp     eax, 8000001Ah
0x1400314cb  jz      loc_1400315C5
0x1400314d1  test    eax, eax
0x1400314d3  js      loc_14003159A
0x1400314d9  mov     r14, r15
0x1400314dc  cmp     [r14], cx
0x1400314e0  jz      short loc_140031503
0x1400314e2  mov     r8b, 1; CaseInsensitive
0x1400314e5  lea     rdx, [rbp+57h+String2]; String2
0x1400314e9  mov     rcx, r14; String1
0x1400314ec  call    cs:__imp_RtlCompareUnicodeString
0x1400314f2  xor     ecx, ecx
0x1400314f4  test    eax, eax
0x1400314f6  jz      short loc_1400314FE
0x1400314f8  add     r14, 20h ; ' '
0x1400314fc  jmp     short loc_1400314DC
0x1400314fe  mov     esi, 1
0x140031503  cmp     edi, 105h
0x140031509  jnz     loc_1400315C7
0x14003150f  test    esi, esi
0x140031511  jnz     loc_1400315C7
0x140031517  lea     eax, [r12+200h]
0x14003151f  cmp     eax, r12d
0x140031522  jb      short loc_140031565
0x140031524  mov     rcx, gs:60h
0x14003152d  mov     r8, r15; P
0x140031530  xor     edx, edx; Flags
0x140031532  mov     r12d, eax
0x140031535  mov     rcx, [rcx+30h]; HeapHandle
0x140031539  call    cs:__imp_RtlFreeHeap
0x14003153f  mov     rcx, gs:60h
0x140031548  mov     r8d, r12d; Size
0x14003154b  mov     edx, ebx; Flags
0x14003154d  mov     rcx, [rcx+30h]; HeapHandle
0x140031551  call    cs:__imp_RtlAllocateHeap
0x140031557  mov     r15, rax
0x14003155a  test    rax, rax
0x14003155d  jnz     loc_140031498
0x140031563  jmp     short loc_1400315CD
0x140031565  mov     rcx, cs:WPP_GLOBAL_Control
0x14003156c  lea     rdx, WPP_GLOBAL_Control
0x140031573  cmp     rcx, rdx
0x140031576  jz      short loc_140031593
0x140031578  test    byte ptr [rcx+1Ch], 1
0x14003157c  jz      short loc_140031593
0x14003157e  mov     rcx, [rcx+10h]
0x140031582  lea     r8, WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids
0x140031589  mov     edx, 1Ah
0x14003158e  call    WPP_SF_
0x140031593  mov     ebx, 216h
0x140031598  jmp     short loc_1400315CD
0x14003159a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400315a1  lea     rdx, WPP_GLOBAL_Control
0x1400315a8  cmp     rcx, rdx
0x1400315ab  jz      loc_140031439
0x1400315b1  test    byte ptr [rcx+1Ch], 1
0x1400315b5  jz      loc_140031439
0x1400315bb  mov     edx, 19h
0x1400315c0  jmp     loc_140031426
0x1400315c5  mov     esi, ecx
0x1400315c7  mov     [r13+0], esi
0x1400315cb  mov     ebx, ecx
0x1400315cd  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400315d1  test    rcx, rcx
0x1400315d4  jz      short loc_1400315DC
0x1400315d6  call    cs:__imp_NtClose
0x1400315dc  test    r15, r15
0x1400315df  jz      short loc_1400315F9
0x1400315e1  mov     rcx, gs:60h
0x1400315ea  mov     r8, r15; P
0x1400315ed  xor     edx, edx; Flags
0x1400315ef  mov     rcx, [rcx+30h]; HeapHandle
0x1400315f3  call    cs:__imp_RtlFreeHeap
0x1400315f9  mov     eax, ebx
0x1400315fb  add     rsp, 0A8h
0x140031602  pop     r15
0x140031604  pop     r14
0x140031606  pop     r13
0x140031608  pop     r12
0x14003160a  pop     rdi
0x14003160b  pop     rsi
0x14003160c  pop     rbx
0x14003160d  pop     rbp
0x14003160e  retn
```
