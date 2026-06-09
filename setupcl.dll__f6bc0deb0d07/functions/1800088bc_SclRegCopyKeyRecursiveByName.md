# SclRegCopyKeyRecursiveByName

- ea: `0x1800088bc`
- end: `0x180008bda`
- name: `SclRegCopyKeyRecursiveByName`
- size: `798`
- prototype: `__int64 __fastcall(void *, const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009cd0`

## callees

- `0x18000154c`
- `0x180001b98`
- `0x180001bc0`
- `0x180007fb0`
- `0x1800088bc`
- `0x180008d44`
- `0x180008e40`
- `0x18000a524`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008a12`
- `ntdll!RtlAllocateHeap` at `0x180008a12`
- `ntdll!RtlInitUnicodeString` at `0x180008913`
- `ntdll!RtlInitUnicodeString` at `0x180008920`
- `ntdll!RtlInitUnicodeString` at `0x180008913`
- `ntdll!RtlInitUnicodeString` at `0x180008920`
- `ntdll!NtClose` at `0x180008b76`
- `ntdll!NtClose` at `0x180008bb6`
- `ntdll!NtClose` at `0x180008b76`
- `ntdll!NtClose` at `0x180008bb6`
- `ntdll!RtlFreeHeap` at `0x180008ba7`
- `ntdll!RtlFreeHeap` at `0x180008ba7`

## string_xrefs

- `0x18000896a`: `(%lx): Failed to open source key [%ws].`
- `0x180008958`: `SclRegCopyKeyRecursiveByName`
- `0x1800089b7`: `SclRegCopyKeyRecursiveByName`
- `0x1800089ef`: `SclRegCopyKeyRecursiveByName`
- `0x1800089a6`: `Source key [%ws] didn't already exist`
- `0x180008a4e`: `(%lx): Failed to query object security for size.`
- `0x180008b3f`: `(%lx): Failed to create destination key [%ws].`
- `0x180008ad6`: `Target key [%ws] already exists`

## pseudocode

```c
__int64 __fastcall SclRegCopyKeyRecursiveByName(void *a1, const WCHAR *a2, const WCHAR *a3)
{
  int v6; // eax
  int v7; // ebx
  int Descriptor; // eax
  PVOID Heap; // rax
  void *v10; // rdi
  char v11; // r14
  __int64 v13; // [rsp+30h] [rbp-50h]
  SIZE_T Size; // [rsp+40h] [rbp-40h] BYREF
  HANDLE v15; // [rsp+48h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING v18; // [rsp+68h] [rbp-18h] BYREF
  ULONG v19; // [rsp+C8h] [rbp+48h] BYREF

  Size = 0;
  v19 = 0;
  v15 = 0;
  DestinationString = 0;
  v18 = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  RtlInitUnicodeString(&v18, a2);
  v6 = SclCreateKeyEx(a1, &DestinationString, 0x10F003Fu, 0, &v19, &v15);
  v7 = v6;
  if ( v6 < 0 )
  {
    SclLogGenericMessage(
      0,
      3,
      (int)SclEvent_Generic_Error,
      1104,
      (__int64)"SclRegCopyKeyRecursiveByName",
      "(%lx): Failed to open source key [%ws].",
      v6,
      a3);
    goto LABEL_27;
  }
  if ( v19 != 2 )
  {
    v7 = -1073741772;
    SclRegDeleteKey(v15);
    SclLogGenericMessage(
      0,
      3,
      (int)SclEvent_Generic_Error,
      1119,
      (__int64)"SclRegCopyKeyRecursiveByName",
      "Source key [%ws] didn't already exist",
      a3);
    goto LABEL_27;
  }
  Descriptor = SclSecurityGetDescriptor(v15, 0, 0, &Size);
  v7 = Descriptor;
  if ( Descriptor == -1073741789 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    v10 = Heap;
    if ( Heap )
      v7 = SclSecurityGetDescriptor(v15, Heap, (unsigned int)Size, (char *)&Size + 4);
    else
      v7 = -1073741801;
    if ( v7 >= 0 )
    {
LABEL_14:
      Handle = 0;
      v11 = 0;
      v7 = SclCreateKeyEx(a1, &v18, 0x10F003Fu, 0, &v19, &Handle);
      if ( v7 < 0 || (v7 = SclSecuritySetDescriptor(Handle, v10), v7 < 0) )
      {
        LODWORD(v13) = v7;
        SclLogGenericMessage(
          0,
          3,
          (int)SclEvent_Generic_Error,
          1180,
          (__int64)"SclRegCopyKeyRecursiveByName",
          "(%lx): Failed to create destination key [%ws].",
          v13,
          a2);
      }
      else if ( v19 == 2 )
      {
        v7 = -1073741771;
        SclLogGenericMessage(
          0,
          3,
          (int)SclEvent_Generic_Error,
          1189,
          (__int64)"SclRegCopyKeyRecursiveByName",
          "Target key [%ws] already exists",
          a2);
      }
      else
      {
        v11 = 1;
        v7 = SclRegCopyKeyRecursiveByHandle(0, Handle, (__int64)v15, 0, 0, 0, 0);
      }
      if ( Handle )
        NtClose(Handle);
      if ( v7 < 0 && v11 )
        SclRegDeleteKeyRecursive(a1, a2);
      goto LABEL_25;
    }
  }
  else
  {
    v10 = 0;
    if ( Descriptor >= 0 )
      v7 = -1073741823;
  }
  SclLogGenericMessage(
    0,
    3,
    (int)SclEvent_Generic_Error,
    1156,
    (__int64)"SclRegCopyKeyRecursiveByName",
    "(%lx): Failed to query object security for size.",
    v7);
  if ( v7 >= 0 )
    goto LABEL_14;
LABEL_25:
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
LABEL_27:
  if ( v15 )
    NtClose(v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800088bc  mov     [rsp-28h+arg_0], rbx
0x1800088c1  mov     [rsp-28h+arg_8], rsi
0x1800088c6  push    rbp
0x1800088c7  push    rdi
0x1800088c8  push    r12
0x1800088ca  push    r14
0x1800088cc  push    r15
0x1800088ce  mov     rbp, rsp
0x1800088d1  sub     rsp, 80h
0x1800088d8  mov     r15, rdx
0x1800088db  mov     dword ptr [rbp+Size], 0
0x1800088e2  mov     r12, rcx
0x1800088e5  mov     dword ptr [rbp+Size+4], 0
0x1800088ec  xorps   xmm0, xmm0
0x1800088ef  mov     [rbp+arg_18], 0
0x1800088f6  xorps   xmm1, xmm1
0x1800088f9  mov     [rbp+var_38], 0
0x180008901  mov     rdx, r8; SourceString
0x180008904  lea     rcx, [rbp+DestinationString]; DestinationString
0x180008908  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000890c  mov     rdi, r8
0x18000890f  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x180008913  call    cs:__imp_RtlInitUnicodeString
0x180008919  mov     rdx, r15; SourceString
0x18000891c  lea     rcx, [rbp+var_18]; DestinationString
0x180008920  call    cs:__imp_RtlInitUnicodeString
0x180008926  lea     rax, [rbp+var_38]
0x18000892a  xor     r9d, r9d
0x18000892d  mov     [rsp+80h+var_58], rax
0x180008932  lea     rdx, [rbp+DestinationString]
0x180008936  lea     rax, [rbp+arg_18]
0x18000893a  mov     r8d, 10F003Fh
0x180008940  mov     rcx, r12
0x180008943  mov     [rsp+80h+var_60], rax
0x180008948  call    SclCreateKeyEx
0x18000894d  mov     ebx, eax
0x18000894f  test    eax, eax
0x180008951  jns     short loc_180008992
0x180008953  mov     [rsp+80h+var_48], rdi
0x180008958  lea     rsi, aSclregcopykeyr_0; "SclRegCopyKeyRecursiveByName"
0x18000895f  mov     dword ptr [rsp+80h+var_50], eax
0x180008963  lea     r8, SclEvent_Generic_Error
0x18000896a  lea     rax, aLxFailedToOpen_6; "(%lx): Failed to open source key [%ws]."
0x180008971  mov     r9d, 450h
0x180008977  mov     [rsp+80h+var_58], rax
0x18000897c  mov     edx, 3
0x180008981  xor     ecx, ecx
0x180008983  mov     [rsp+80h+var_60], rsi
0x180008988  call    SclLogGenericMessage
0x18000898d  jmp     loc_180008BAD
0x180008992  cmp     [rbp+arg_18], 2
0x180008996  mov     rcx, [rbp+var_38]; Handle
0x18000899a  jz      short loc_1800089E1
0x18000899c  mov     ebx, 0C0000034h
0x1800089a1  call    SclRegDeleteKey
0x1800089a6  lea     rax, aSourceKeyWsDid; "Source key [%ws] didn't already exist"
0x1800089ad  mov     [rsp+80h+var_50], rdi
0x1800089b2  mov     [rsp+80h+var_58], rax
0x1800089b7  lea     rsi, aSclregcopykeyr_0; "SclRegCopyKeyRecursiveByName"
0x1800089be  mov     r9d, 45Fh
0x1800089c4  mov     [rsp+80h+var_60], rsi
0x1800089c9  lea     r8, SclEvent_Generic_Error
0x1800089d0  mov     edx, 3
0x1800089d5  xor     ecx, ecx
0x1800089d7  call    SclLogGenericMessage
0x1800089dc  jmp     loc_180008BAD
0x1800089e1  lea     r9, [rbp+Size]
0x1800089e5  xor     r8d, r8d
0x1800089e8  xor     edx, edx
0x1800089ea  call    SclSecurityGetDescriptor
0x1800089ef  lea     rsi, aSclregcopykeyr_0; "SclRegCopyKeyRecursiveByName"
0x1800089f6  mov     ebx, eax
0x1800089f8  cmp     eax, 0C0000023h
0x1800089fd  jnz     short loc_180008A43
0x1800089ff  mov     rcx, gs:60h
0x180008a08  xor     edx, edx; Flags
0x180008a0a  mov     r8d, dword ptr [rbp+Size]; Size
0x180008a0e  mov     rcx, [rcx+30h]; HeapHandle
0x180008a12  call    cs:__imp_RtlAllocateHeap
0x180008a18  mov     rdi, rax
0x180008a1b  test    rax, rax
0x180008a1e  jz      short loc_180008A38
0x180008a20  mov     r8d, dword ptr [rbp+Size]
0x180008a24  lea     r9, [rbp+Size+4]
0x180008a28  mov     rcx, [rbp+var_38]
0x180008a2c  mov     rdx, rax
0x180008a2f  call    SclSecurityGetDescriptor
0x180008a34  mov     ebx, eax
0x180008a36  jmp     short loc_180008A3D
0x180008a38  mov     ebx, 0C0000017h
0x180008a3d  test    ebx, ebx
0x180008a3f  jns     short loc_180008A84
0x180008a41  jmp     short loc_180008A4E
0x180008a43  xor     edi, edi
0x180008a45  test    eax, eax
0x180008a47  js      short loc_180008A4E
0x180008a49  mov     ebx, 0C0000001h
0x180008a4e  lea     rax, aLxFailedToQuer; "(%lx): Failed to query object security "...
0x180008a55  mov     dword ptr [rsp+80h+var_50], ebx
0x180008a59  mov     [rsp+80h+var_58], rax
0x180008a5e  lea     r8, SclEvent_Generic_Error
0x180008a65  mov     r9d, 484h
0x180008a6b  mov     [rsp+80h+var_60], rsi
0x180008a70  mov     edx, 3
0x180008a75  xor     ecx, ecx
0x180008a77  call    SclLogGenericMessage
0x180008a7c  test    ebx, ebx
0x180008a7e  js      loc_180008B90
0x180008a84  lea     rax, [rbp+Handle]
0x180008a88  mov     [rbp+Handle], 0
0x180008a90  mov     [rsp+80h+var_58], rax
0x180008a95  lea     rdx, [rbp+var_18]
0x180008a99  lea     rax, [rbp+arg_18]
0x180008a9d  xor     r9d, r9d
0x180008aa0  mov     r8d, 10F003Fh
0x180008aa6  mov     [rsp+80h+var_60], rax
0x180008aab  mov     rcx, r12
0x180008aae  xor     r14b, r14b
0x180008ab1  call    SclCreateKeyEx
0x180008ab6  mov     ebx, eax
0x180008ab8  test    eax, eax
0x180008aba  js      short loc_180008B3A
0x180008abc  mov     rcx, [rbp+Handle]; Handle
0x180008ac0  mov     rdx, rdi; SecurityDescriptor
0x180008ac3  call    SclSecuritySetDescriptor
0x180008ac8  mov     ebx, eax
0x180008aca  test    eax, eax
0x180008acc  js      short loc_180008B3A
0x180008ace  xor     ecx, ecx
0x180008ad0  cmp     [rbp+arg_18], 2
0x180008ad4  jnz     short loc_180008B08
0x180008ad6  lea     rax, aTargetKeyWsAlr; "Target key [%ws] already exists"
0x180008add  mov     [rsp+80h+var_50], r15
0x180008ae2  mov     [rsp+80h+var_58], rax
0x180008ae7  lea     r8, SclEvent_Generic_Error
0x180008aee  mov     r9d, 4A5h
0x180008af4  mov     [rsp+80h+var_60], rsi
0x180008af9  lea     edx, [rcx+3]
0x180008afc  mov     ebx, 0C0000035h
0x180008b01  call    SclLogGenericMessage
0x180008b06  jmp     short loc_180008B6D
0x180008b08  mov     r8, [rbp+var_38]
0x180008b0c  xor     r9d, r9d
0x180008b0f  mov     rdx, [rbp+Handle]
0x180008b13  mov     r14b, 1
0x180008b16  mov     [rsp+80h+var_50], 0
0x180008b1f  mov     [rsp+80h+var_58], 0
0x180008b28  mov     [rsp+80h+var_60], 0
0x180008b31  call    SclRegCopyKeyRecursiveByHandle
0x180008b36  mov     ebx, eax
0x180008b38  jmp     short loc_180008B6D
0x180008b3a  mov     [rsp+80h+var_48], r15
0x180008b3f  lea     rax, aLxFailedToCrea_0; "(%lx): Failed to create destination key"...
0x180008b46  mov     dword ptr [rsp+80h+var_50], ebx
0x180008b4a  lea     r8, SclEvent_Generic_Error
0x180008b51  mov     [rsp+80h+var_58], rax
0x180008b56  mov     r9d, 49Ch
0x180008b5c  mov     edx, 3
0x180008b61  mov     [rsp+80h+var_60], rsi
0x180008b66  xor     ecx, ecx
0x180008b68  call    SclLogGenericMessage
0x180008b6d  mov     rcx, [rbp+Handle]; Handle
0x180008b71  test    rcx, rcx
0x180008b74  jz      short loc_180008B7C
0x180008b76  call    cs:__imp_NtClose
0x180008b7c  test    ebx, ebx
0x180008b7e  jns     short loc_180008B90
0x180008b80  test    r14b, r14b
0x180008b83  jz      short loc_180008B90
0x180008b85  mov     rdx, r15
0x180008b88  mov     rcx, r12
0x180008b8b  call    SclRegDeleteKeyRecursive
0x180008b90  test    rdi, rdi
0x180008b93  jz      short loc_180008BAD
0x180008b95  mov     rcx, gs:60h
0x180008b9e  mov     r8, rdi; P
0x180008ba1  xor     edx, edx; Flags
0x180008ba3  mov     rcx, [rcx+30h]; HeapHandle
0x180008ba7  call    cs:__imp_RtlFreeHeap
0x180008bad  mov     rcx, [rbp+var_38]; Handle
0x180008bb1  test    rcx, rcx
0x180008bb4  jz      short loc_180008BBC
0x180008bb6  call    cs:__imp_NtClose
0x180008bbc  lea     r11, [rsp+80h+var_s0]
0x180008bc4  mov     eax, ebx
0x180008bc6  mov     rbx, [r11+30h]
0x180008bca  mov     rsi, [r11+38h]
0x180008bce  mov     rsp, r11
0x180008bd1  pop     r15
0x180008bd3  pop     r14
0x180008bd5  pop     r12
0x180008bd7  pop     rdi
0x180008bd8  pop     rbp
0x180008bd9  retn
```
