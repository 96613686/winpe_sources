# SmscpParseArgs

- ea: `0x1400069d0`
- end: `0x140006f2a`
- name: `SmscpParseArgs`
- size: `1370`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140006680`

## callees

- `0x1400069d0`
- `0x140018350`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140006e8c`
- `ntdll!NtQuerySystemInformation` at `0x140006e8c`
- `ntdll!RtlAllocateHeap` at `0x140006c40`
- `ntdll!RtlAllocateHeap` at `0x140006d3f`
- `ntdll!RtlAllocateHeap` at `0x140006c40`
- `ntdll!RtlAllocateHeap` at `0x140006d3f`
- `ntdll!RtlFreeHeap` at `0x140006d1c`
- `ntdll!RtlFreeHeap` at `0x140006d1c`
- `ntdll!RtlAppendUnicodeToString` at `0x140006dc3`
- `ntdll!RtlAppendUnicodeToString` at `0x140006dea`
- `ntdll!RtlAppendUnicodeToString` at `0x140006dfa`
- `ntdll!RtlAppendUnicodeToString` at `0x140006e0f`
- `ntdll!RtlAppendUnicodeToString` at `0x140006dc3`
- `ntdll!RtlAppendUnicodeToString` at `0x140006dea`
- `ntdll!RtlAppendUnicodeToString` at `0x140006dfa`
- `ntdll!RtlAppendUnicodeToString` at `0x140006e0f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006dcf`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006ebe`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006ed7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006ef4`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006f0d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006f1f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006dcf`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006ebe`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006ed7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006ef4`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006f0d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140006f1f`
- `ntdll!NtMapViewOfSection` at `0x140006a7b`
- `ntdll!NtMapViewOfSection` at `0x140006ad0`
- `ntdll!NtMapViewOfSection` at `0x140006a7b`
- `ntdll!NtMapViewOfSection` at `0x140006ad0`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140006b76`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140006b8f`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140006b76`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140006b8f`
- `ntdll!NtDelayExecution` at `0x140006b89`
- `ntdll!NtDelayExecution` at `0x140006b89`
- `ntdll!wcstoul` at `0x140006a1a`
- `ntdll!wcstoul` at `0x140006a36`
- `ntdll!wcstoul` at `0x140006a1a`
- `ntdll!wcstoul` at `0x140006a36`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x140006ccc`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x140006d7b`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x140006ccc`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x140006d7b`

## pseudocode

```c
NTSTATUS __fastcall SmscpParseArgs(unsigned int a1, __int64 a2, int *a3, struct _UNICODE_STRING *a4)
{
  unsigned int v8; // eax
  const wchar_t *v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // eax
  NTSTATUS result; // eax
  UNICODE_STRING *v13; // r13
  int i; // ecx
  int v15; // edx
  unsigned int v16; // edx
  SIZE_T v17; // r8
  char v18; // cl
  unsigned int v19; // r12d
  int v20; // ecx
  unsigned int v21; // edx
  __int64 v22; // rax
  WCHAR *Heap; // rax
  int v25; // eax
  NTSTATUS v26; // eax
  ULONG v27; // ebx
  unsigned __int64 v28; // rcx
  WCHAR *v29; // rax
  ULONG v30; // r8d
  __int64 v31; // rbx
  int v32; // eax
  int Length; // r8d
  int v34; // eax
  int SystemInformation; // [rsp+50h] [rbp-20h] BYREF
  union _LARGE_INTEGER SectionOffset; // [rsp+58h] [rbp-18h] BYREF
  ULONG_PTR ViewSize[2]; // [rsp+60h] [rbp-10h] BYREF
  ULONG RetunedLength; // [rsp+A0h] [rbp+30h] BYREF

  SystemInformation = 0;
  RetunedLength = 0;
  if ( a1 <= 2 )
    return -1073741585;
  *a3 = 0;
  v8 = wcstoul(*(const wchar_t **)(a2 + 8), 0, 16);
  v9 = *(const wchar_t **)(a2 + 16);
  v10 = v8;
  SectionOffset.QuadPart = 0;
  ViewSize[0] = 0;
  v11 = wcstoul(v9, 0, 16);
  result = NtMapViewOfSection(
             (HANDLE)v11,
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             &SmpMappedView,
             0,
             0,
             &SectionOffset,
             ViewSize,
             ViewUnmap,
             0,
             2u);
  if ( result >= 0 )
  {
    SectionOffset.QuadPart = 0;
    ViewSize[0] = 0;
    result = NtMapViewOfSection(
               (HANDLE)v10,
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               &SmscpSharedWindow,
               0,
               0,
               &SectionOffset,
               ViewSize,
               ViewUnmap,
               0,
               4u);
    if ( result >= 0 )
    {
      v13 = 0;
      SmpDefaultLibPath.Buffer = (PWSTR)((char *)SmpMappedView + *((_QWORD *)SmpMappedView + 1));
      SmpDefaultLibPath.Length = *((_WORD *)SmpMappedView + 8);
      SmpDefaultLibPath.MaximumLength = SmpDefaultLibPath.Length + 2;
      SmpS0InitCmd.Buffer = (PWSTR)((char *)SmpMappedView + *((_QWORD *)SmpMappedView + 3));
      SmpS0InitCmd.Length = *((_WORD *)SmpMappedView + 16);
      SmpS0InitCmd.MaximumLength = SmpS0InitCmd.Length + 2;
      SmscpInitExecuteCmd.Buffer = (PWSTR)((char *)SmpMappedView + *((_QWORD *)SmpMappedView + 5));
      SmscpInitExecuteCmd.Length = *((_WORD *)SmpMappedView + 24);
      SmscpInitExecuteCmd.MaximumLength = SmscpInitExecuteCmd.Length + 2;
      SmscpSubsystemRegistered = (HANDLE)*((_QWORD *)SmscpSharedWindow + 1);
      ViewSize[0] = -2500000;
      for ( i = RtlGetCurrentServiceSessionId(); i == -1; i = RtlGetCurrentServiceSessionId() )
        NtDelayExecution(0, (LARGE_INTEGER *)ViewSize);
      v15 = 0;
      if ( *(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 704LL) == i )
        v15 = 8;
      v16 = *a3 & 0xFFFFFFF7 | v15;
      LODWORD(v17) = 0;
      *a3 = v16;
      v18 = v16 ^ (4 * *(_DWORD *)SmpMappedView);
      RetunedLength = 0;
      v19 = 3;
      v20 = v16 ^ v18 & 4;
      v21 = 3;
      *a3 = v20;
      if ( a1 > 3 )
      {
        do
        {
          v22 = -1;
          while ( *(_WORD *)(*(_QWORD *)(a2 + 8LL * v21) + 2 * v22++ + 2) != 0 )
            ;
          ++v21;
          v17 = (unsigned int)(v17 + 2 * v22 + 2);
          RetunedLength = v17;
        }
        while ( v21 < a1 );
        if ( (_DWORD)v17 )
        {
LABEL_13:
          Heap = (WCHAR *)RtlAllocateHeap(
                            *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                            SmBaseTag + 786432,
                            v17);
          a4->Buffer = Heap;
          if ( !Heap )
            return -1073741801;
          a4->Length = 0;
          a4->MaximumLength = RetunedLength;
          *Heap = 0;
          v25 = *a3;
          if ( (*a3 & 2) == 0 )
          {
            v31 = a1 - 1;
            if ( (unsigned int)v31 > 3 )
            {
              do
              {
                RtlAppendUnicodeToString(a4, *(PCWSTR *)(a2 + 8LL * v19));
                RtlAppendUnicodeToString(a4, L" ");
                ++v19;
              }
              while ( v19 < (unsigned int)v31 );
            }
            RtlAppendUnicodeToString(a4, *(PCWSTR *)(a2 + 8 * v31));
            return 0;
          }
          if ( (v25 & 1) == 0 )
          {
            if ( (v25 & 8) != 0 )
              RtlAppendUnicodeStringToString(a4, &SmpS0InitCmd);
            else
              RtlAppendUnicodeStringToString(a4, &SmscpInitExecuteCmd);
            return 0;
          }
          v26 = LdrQueryImageFileExecutionOptions(v13, L"Debugger", 1u, a4->Buffer, 0x30u, &RetunedLength);
          if ( v26 == -2147483643 )
          {
            v27 = RetunedLength;
            v28 = RetunedLength + v13->MaximumLength + 2LL;
            if ( v28 <= RetunedLength || v28 > 0xFFFE )
              goto LABEL_42;
            RetunedLength += v13->MaximumLength + 2;
            RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, a4->Buffer);
            v29 = (WCHAR *)RtlAllocateHeap(
                             *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                             SmBaseTag + 786432,
                             RetunedLength);
            a4->Buffer = v29;
            if ( !v29 )
              return -1073741801;
            a4->MaximumLength = RetunedLength;
            v26 = LdrQueryImageFileExecutionOptions(v13, L"Debugger", 1u, v29, v27, &RetunedLength);
          }
          if ( v26 >= 0 )
          {
            v30 = RetunedLength & 0xFFFFFFFE;
            RetunedLength = v30;
            if ( v30 > 2 && !a4->Buffer[((unsigned __int64)v30 >> 1) - 1] )
            {
              v30 -= 2;
              RetunedLength = v30;
            }
            a4->Length = v30;
            RtlAppendUnicodeToString(a4, L" ");
LABEL_29:
            RtlAppendUnicodeStringToString(a4, v13);
            return 0;
          }
LABEL_42:
          if ( (*(_BYTE *)a3 & 8) != 0
            && NtQuerySystemInformation(SystemFlagsInformation, &SystemInformation, 4u, 0) >= 0
            && (SystemInformation & 0x4000004) != 0
            && (int)SmscpIsDebuggerPresent() >= 0 )
          {
            RtlAppendUnicodeStringToString(a4, &stru_14001FC50);
            v34 = SystemInformation;
            if ( (SystemInformation & 0x20000) != 0 )
            {
              RtlAppendUnicodeStringToString(a4, &stru_14001FC40);
              v34 = SystemInformation;
            }
            if ( (v34 & 0x4000000) != 0 )
              RtlAppendUnicodeStringToString(a4, &stru_14001FC30);
          }
          goto LABEL_29;
        }
      }
      v32 = *a3;
      if ( (*a3 & 8) != 0 )
      {
        Length = SmpS0InitCmd.Length;
        if ( (v32 & 4) == 0 )
        {
          Length = SmpS0InitCmd.Length + 50;
          v13 = &SmpS0InitCmd;
LABEL_40:
          v32 |= 1u;
        }
      }
      else
      {
        if ( !SmscpInitExecuteCmd.Length )
        {
          Length = 74;
          v13 = (UNICODE_STRING *)&SmscpDefaultCmd;
          goto LABEL_40;
        }
        Length = SmscpInitExecuteCmd.Length;
      }
      v17 = (unsigned int)(Length + 2);
      *a3 = v32 | 2;
      RetunedLength = v17;
      goto LABEL_13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400069d0  mov     [rsp-28h+arg_18], rsi
0x1400069d5  push    rbp
0x1400069d6  push    rdi
0x1400069d7  push    r12
0x1400069d9  push    r14
0x1400069db  push    r15
0x1400069dd  mov     rbp, rsp
0x1400069e0  sub     rsp, 70h
0x1400069e4  xor     r12d, r12d
0x1400069e7  mov     r14, r9
0x1400069ea  mov     [rbp+SystemInformation], r12d
0x1400069ee  mov     r15, r8
0x1400069f1  mov     [rbp+RetunedLength], r12d
0x1400069f5  mov     rsi, rdx
0x1400069f8  mov     edi, ecx
0x1400069fa  cmp     ecx, 2
0x1400069fd  jbe     loc_140006C79
0x140006a03  mov     [r8], r12d
0x140006a06  xor     edx, edx; EndPtr
0x140006a08  mov     rcx, [rsi+8]; Str
0x140006a0c  mov     r8d, 10h; Radix
0x140006a12  mov     [rsp+70h+arg_8], rbx
0x140006a1a  call    cs:__imp_wcstoul
0x140006a20  mov     rcx, [rsi+10h]; Str
0x140006a24  xor     edx, edx; EndPtr
0x140006a26  mov     r8d, 10h; Radix
0x140006a2c  mov     ebx, eax
0x140006a2e  mov     qword ptr [rbp+var_18], r12
0x140006a32  mov     [rbp+var_10], r12
0x140006a36  call    cs:__imp_wcstoul
0x140006a3c  mov     [rsp+70h+AccessProtection], 2; AccessProtection
0x140006a44  lea     r8, SmpMappedView; BaseAddress
0x140006a4b  mov     [rsp+70h+AllocationType], r12d; AllocationType
0x140006a50  xor     r9d, r9d; ZeroBits
0x140006a53  mov     ecx, eax; SectionHandle
0x140006a55  mov     rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140006a5c  mov     [rsp+70h+InheritDisposition], 2; InheritDisposition
0x140006a64  lea     rax, [rbp+var_10]
0x140006a68  mov     [rsp+70h+ViewSize], rax; ViewSize
0x140006a6d  lea     rax, [rbp+var_18]
0x140006a71  mov     [rsp+70h+SectionOffset], rax; SectionOffset
0x140006a76  mov     [rsp+70h+CommitSize], r12; CommitSize
0x140006a7b  call    cs:__imp_NtMapViewOfSection
0x140006a81  test    eax, eax
0x140006a83  js      loc_140006C5C
0x140006a89  mov     [rsp+70h+AccessProtection], 4; AccessProtection
0x140006a91  lea     rax, [rbp+var_10]
0x140006a95  mov     [rsp+70h+AllocationType], r12d; AllocationType
0x140006a9a  lea     r8, SmscpSharedWindow; BaseAddress
0x140006aa1  mov     [rsp+70h+InheritDisposition], 2; InheritDisposition
0x140006aa9  mov     ecx, ebx; SectionHandle
0x140006aab  mov     [rsp+70h+ViewSize], rax; ViewSize
0x140006ab0  xor     r9d, r9d; ZeroBits
0x140006ab3  lea     rax, [rbp+var_18]
0x140006ab7  mov     qword ptr [rbp+var_18], r12
0x140006abb  mov     [rsp+70h+SectionOffset], rax; SectionOffset
0x140006ac0  mov     rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140006ac7  mov     [rsp+70h+CommitSize], r12; CommitSize
0x140006acc  mov     [rbp+var_10], r12
0x140006ad0  call    cs:__imp_NtMapViewOfSection
0x140006ad6  test    eax, eax
0x140006ad8  js      loc_140006C5C
0x140006ade  mov     rdx, cs:SmpMappedView
0x140006ae5  mov     [rsp+70h+arg_10], r13
0x140006aed  mov     r13d, r12d
0x140006af0  mov     rcx, [rdx+8]
0x140006af4  add     rcx, rdx
0x140006af7  mov     cs:SmpDefaultLibPath.Buffer, rcx
0x140006afe  movzx   eax, word ptr [rdx+10h]
0x140006b02  mov     cs:SmpDefaultLibPath.Length, ax
0x140006b09  add     ax, 2
0x140006b0d  mov     cs:SmpDefaultLibPath.MaximumLength, ax
0x140006b14  mov     rcx, [rdx+18h]
0x140006b18  add     rcx, rdx
0x140006b1b  mov     cs:SmpS0InitCmd.Buffer, rcx
0x140006b22  movzx   eax, word ptr [rdx+20h]
0x140006b26  mov     cs:SmpS0InitCmd.Length, ax
0x140006b2d  add     ax, 2
0x140006b31  mov     cs:SmpS0InitCmd.MaximumLength, ax
0x140006b38  mov     rcx, [rdx+28h]
0x140006b3c  add     rcx, rdx
0x140006b3f  mov     cs:SmscpInitExecuteCmd.Buffer, rcx
0x140006b46  movzx   eax, word ptr [rdx+30h]
0x140006b4a  mov     cs:SmscpInitExecuteCmd.Length, ax
0x140006b51  add     ax, 2
0x140006b55  mov     cs:SmscpInitExecuteCmd.MaximumLength, ax
0x140006b5c  mov     rax, cs:SmscpSharedWindow
0x140006b63  mov     rcx, [rax+8]
0x140006b67  mov     cs:SmscpSubsystemRegistered, rcx
0x140006b6e  mov     [rbp+var_10], 0FFFFFFFFFFD9DA60h
0x140006b76  call    cs:__imp_RtlGetCurrentServiceSessionId
0x140006b7c  mov     ecx, eax
0x140006b7e  cmp     eax, 0FFFFFFFFh
0x140006b81  jnz     short loc_140006B9C
0x140006b83  lea     rdx, [rbp+var_10]; Interval
0x140006b87  xor     ecx, ecx; Alertable
0x140006b89  call    cs:__imp_NtDelayExecution
0x140006b8f  call    cs:__imp_RtlGetCurrentServiceSessionId
0x140006b95  mov     ecx, eax
0x140006b97  cmp     eax, 0FFFFFFFFh
0x140006b9a  jz      short loc_140006B83
0x140006b9c  mov     rax, gs:60h
0x140006ba5  mov     edx, r12d
0x140006ba8  mov     r8d, 8
0x140006bae  cmp     [rax+2C0h], ecx
0x140006bb4  mov     eax, [r15]
0x140006bb7  cmovz   edx, r8d
0x140006bbb  and     eax, 0FFFFFFF7h
0x140006bbe  or      edx, eax
0x140006bc0  mov     r8d, r12d
0x140006bc3  mov     [r15], edx
0x140006bc6  mov     rax, cs:SmpMappedView
0x140006bcd  mov     ecx, [rax]
0x140006bcf  shl     ecx, 2
0x140006bd2  xor     ecx, edx
0x140006bd4  mov     [rbp+RetunedLength], r12d
0x140006bd8  and     ecx, 4
0x140006bdb  mov     r12d, 3
0x140006be1  xor     ecx, edx
0x140006be3  mov     edx, r12d
0x140006be6  mov     [r15], ecx
0x140006be9  cmp     edi, r12d
0x140006bec  jbe     loc_140006E1C
0x140006bf2  mov     eax, edx
0x140006bf4  mov     rcx, [rsi+rax*8]
0x140006bf8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140006bff  nop
0x140006c00  cmp     [rcx+rax*2+2], r13w
0x140006c06  lea     rax, [rax+1]
0x140006c0a  jnz     short loc_140006C00
0x140006c0c  lea     r8d, [r8+rax*2]
0x140006c10  inc     edx
0x140006c12  add     r8d, 2; Size
0x140006c16  mov     [rbp+RetunedLength], r8d
0x140006c1a  cmp     edx, edi
0x140006c1c  jb      short loc_140006BF2
0x140006c1e  test    r8d, r8d
0x140006c21  jz      loc_140006E1C
0x140006c27  mov     rcx, gs:60h
0x140006c30  mov     edx, cs:SmBaseTag
0x140006c36  add     edx, 0C0000h; Flags
0x140006c3c  mov     rcx, [rcx+30h]; HeapHandle
0x140006c40  call    cs:__imp_RtlAllocateHeap
0x140006c46  mov     [r14+8], rax
0x140006c4a  test    rax, rax
0x140006c4d  jnz     short loc_140006C80
0x140006c4f  mov     eax, 0C0000017h
0x140006c54  mov     r13, [rsp+70h+arg_10]
0x140006c5c  mov     rbx, [rsp+70h+arg_8]
0x140006c64  mov     rsi, [rsp+70h+arg_18]
0x140006c6c  add     rsp, 70h
0x140006c70  pop     r15
0x140006c72  pop     r14
0x140006c74  pop     r12
0x140006c76  pop     rdi
0x140006c77  pop     rbp
0x140006c78  retn
0x140006c79  mov     eax, 0C00000EFh
0x140006c7e  jmp     short loc_140006C64
0x140006c80  xor     ecx, ecx
0x140006c82  mov     [r14], cx
0x140006c86  movzx   ecx, word ptr [rbp+RetunedLength]
0x140006c8a  mov     [r14+2], cx
0x140006c8f  xor     ecx, ecx
0x140006c91  mov     [rax], cx
0x140006c94  mov     eax, [r15]
0x140006c97  test    al, 2
0x140006c99  jz      loc_140006DD7
0x140006c9f  test    al, 1
0x140006ca1  jz      loc_140006EFF
0x140006ca7  mov     r9, [r14+8]; Buffer
0x140006cab  lea     rax, [rbp+RetunedLength]
0x140006caf  mov     [rsp+70h+SectionOffset], rax; RetunedLength
0x140006cb4  lea     rdx, ValueName; "Debugger"
0x140006cbb  mov     r8d, 1; ValueSize
0x140006cc1  mov     dword ptr [rsp+70h+CommitSize], 30h ; '0'; BufferSize
0x140006cc9  mov     rcx, r13; SubKey
0x140006ccc  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x140006cd2  cmp     eax, 80000005h
0x140006cd7  jnz     loc_140006D81
0x140006cdd  mov     ebx, [rbp+RetunedLength]
0x140006ce0  movzx   edx, word ptr [r13+2]
0x140006ce5  add     edx, ebx
0x140006ce7  mov     ecx, edx
0x140006ce9  add     rcx, 2
0x140006ced  cmp     rcx, rbx
0x140006cf0  jbe     loc_140006E70
0x140006cf6  cmp     rcx, 0FFFEh
0x140006cfd  ja      loc_140006E70
0x140006d03  lea     eax, [rdx+2]
0x140006d06  xor     edx, edx; Flags
0x140006d08  mov     [rbp+RetunedLength], eax
0x140006d0b  mov     rcx, gs:60h
0x140006d14  mov     r8, [r14+8]; BaseAddress
0x140006d18  mov     rcx, [rcx+30h]; HeapHandle
0x140006d1c  call    cs:__imp_RtlFreeHeap
0x140006d22  mov     rcx, gs:60h
0x140006d2b  mov     edx, cs:SmBaseTag
0x140006d31  mov     r8d, [rbp+RetunedLength]; Size
0x140006d35  add     edx, 0C0000h; Flags
0x140006d3b  mov     rcx, [rcx+30h]; HeapHandle
0x140006d3f  call    cs:__imp_RtlAllocateHeap
0x140006d45  mov     [r14+8], rax
0x140006d49  test    rax, rax
0x140006d4c  jz      loc_140006C4F
0x140006d52  movzx   ecx, word ptr [rbp+RetunedLength]
0x140006d56  lea     rdx, ValueName; "Debugger"
0x140006d5d  mov     [r14+2], cx
0x140006d62  mov     r9, rax; Buffer
0x140006d65  lea     rcx, [rbp+RetunedLength]
0x140006d69  mov     r8d, 1; ValueSize
0x140006d6f  mov     [rsp+70h+SectionOffset], rcx; RetunedLength
0x140006d74  mov     rcx, r13; SubKey
0x140006d77  mov     dword ptr [rsp+70h+CommitSize], ebx; BufferSize
0x140006d7b  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x140006d81  test    eax, eax
0x140006d83  js      loc_140006E70
0x140006d89  mov     r8d, [rbp+RetunedLength]
0x140006d8d  and     r8d, 0FFFFFFFEh
0x140006d91  mov     [rbp+RetunedLength], r8d
0x140006d95  cmp     r8d, 2
0x140006d99  jbe     short loc_140006DB5
0x140006d9b  mov     rax, [r14+8]
0x140006d9f  mov     ecx, r8d
0x140006da2  shr     rcx, 1
0x140006da5  cmp     word ptr [rax+rcx*2-2], 0
0x140006dab  jnz     short loc_140006DB5
0x140006dad  add     r8d, 0FFFFFFFEh
0x140006db1  mov     [rbp+RetunedLength], r8d
0x140006db5  lea     rdx, Source; " "
0x140006dbc  mov     [r14], r8w
0x140006dc0  mov     rcx, r14; Destination
0x140006dc3  call    cs:__imp_RtlAppendUnicodeToString
0x140006dc9  mov     rdx, r13; Source
0x140006dcc  mov     rcx, r14; Destination
0x140006dcf  call    cs:__imp_RtlAppendUnicodeStringToString
0x140006dd5  jmp     short loc_140006E15
0x140006dd7  lea     ebx, [rdi-1]
0x140006dda  cmp     ebx, r12d
0x140006ddd  jbe     short loc_140006E08
0x140006ddf  nop
0x140006de0  mov     edx, r12d
0x140006de3  mov     rcx, r14; Destination
0x140006de6  mov     rdx, [rsi+rdx*8]; Source
0x140006dea  call    cs:__imp_RtlAppendUnicodeToString
0x140006df0  lea     rdx, Source; " "
0x140006df7  mov     rcx, r14; Destination
0x140006dfa  call    cs:__imp_RtlAppendUnicodeToString
0x140006e00  inc     r12d
0x140006e03  cmp     r12d, ebx
0x140006e06  jb      short loc_140006DE0
0x140006e08  mov     rdx, [rsi+rbx*8]; Source
0x140006e0c  mov     rcx, r14; Destination
0x140006e0f  call    cs:__imp_RtlAppendUnicodeToString
0x140006e15  xor     eax, eax
0x140006e17  jmp     loc_140006C54
0x140006e1c  mov     eax, [r15]
0x140006e1f  test    al, 8
0x140006e21  jz      short loc_140006E3C
0x140006e23  movzx   r8d, cs:SmpS0InitCmd.Length
0x140006e2b  test    al, 4
0x140006e2d  jnz     short loc_140006E5D
0x140006e2f  add     r8d, 32h ; '2'
0x140006e33  lea     r13, SmpS0InitCmd
0x140006e3a  jmp     short loc_140006E5A
0x140006e3c  movzx   ecx, cs:SmscpInitExecuteCmd.Length
0x140006e43  test    cx, cx
0x140006e46  jz      short loc_140006E4D
0x140006e48  mov     r8d, ecx
0x140006e4b  jmp     short loc_140006E5D
0x140006e4d  mov     r8d, 4Ah ; 'J'
0x140006e53  lea     r13, SmscpDefaultCmd
0x140006e5a  or      eax, 1
0x140006e5d  or      eax, 2
0x140006e60  add     r8d, 2
0x140006e64  mov     [r15], eax
0x140006e67  mov     [rbp+RetunedLength], r8d
0x140006e6b  jmp     loc_140006C27
0x140006e70  test    byte ptr [r15], 8
0x140006e74  jz      loc_140006DC9
0x140006e7a  xor     r9d, r9d; ReturnLength
0x140006e7d  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x140006e81  mov     r8d, 4; SystemInformationLength
0x140006e87  mov     ecx, 9; SystemInformationClass
0x140006e8c  call    cs:__imp_NtQuerySystemInformation
0x140006e92  test    eax, eax
0x140006e94  js      loc_140006DC9
0x140006e9a  test    [rbp+SystemInformation], 4000004h
0x140006ea1  jz      loc_140006DC9
0x140006ea7  call    SmscpIsDebuggerPresent
0x140006eac  test    eax, eax
0x140006eae  js      loc_140006DC9
0x140006eb4  lea     rdx, stru_14001FC50; Source
0x140006ebb  mov     rcx, r14; Destination
0x140006ebe  call    cs:__imp_RtlAppendUnicodeStringToString
0x140006ec4  mov     eax, [rbp+SystemInformation]
0x140006ec7  bt      eax, 11h
0x140006ecb  jnb     short loc_140006EE0
0x140006ecd  lea     rdx, stru_14001FC40; Source
0x140006ed4  mov     rcx, r14; Destination
  ... truncated ...
```
