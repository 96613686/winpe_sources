# InitializeTelemetryAssertsKM

- ea: `0x140010ab8`
- end: `0x140010c5e`
- name: `InitializeTelemetryAssertsKM`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140020080`

## callees

- `0x140010ab8`
- `0x140010c64`
- `0x140011f80`
- `0x140012280`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140010b11`
- `ntoskrnl!ExAllocatePool2` at `0x140010b11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c43`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010b46`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010b46`
- `ntoskrnl!RtlFreeAnsiString` at `0x140010c2f`
- `ntoskrnl!RtlFreeAnsiString` at `0x140010c2f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140010b97`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140010b97`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140010bb8`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140010bb8`
- `ntoskrnl!RtlInitAnsiString` at `0x140010af3`
- `ntoskrnl!RtlInitAnsiString` at `0x140010c0b`
- `ntoskrnl!RtlInitAnsiString` at `0x140010af3`
- `ntoskrnl!RtlInitAnsiString` at `0x140010c0b`

## string_xrefs

- `0x140010b61`: `ImagePath`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKM(const void **a1)
{
  NTSTATUS RegistryValues; // ebx
  void *Pool2; // rax
  void *v5; // rdi
  __int64 i; // rcx
  _STRING DestinationString; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-69h] BYREF
  struct _STRING v9; // [rsp+50h] [rbp-59h] BYREF
  struct _STRING v10; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v11[18]; // [rsp+70h] [rbp-39h] BYREF

  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RegistryValues = -1073741801;
  RtlInitAnsiString(&DestinationString, 0);
  Pool2 = (void *)ExAllocatePool2(64, *(unsigned __int16 *)a1 + 2LL, 1953657665);
  v5 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, a1[1], *(unsigned __int16 *)a1);
    SourceString = 0;
    RtlInitUnicodeString(&SourceString, 0);
    memset(v11, 0, 0x70u);
    LODWORD(v11[1]) = 32;
    v11[2] = L"ImagePath";
    LODWORD(v11[4]) = 2;
    v11[3] = &SourceString;
    RegistryValues = RtlQueryRegistryValuesEx(0, v5, v11, 0, 0);
    if ( RegistryValues >= 0 )
    {
      RegistryValues = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 1u);
      ExFreePoolWithTag(SourceString.Buffer, 0);
      if ( RegistryValues >= 0 )
      {
        for ( i = (unsigned int)DestinationString.Length - 1; (_DWORD)i; i = (unsigned int)(i - 1) )
        {
          if ( DestinationString.Buffer[i] == 92 )
          {
            if ( (_DWORD)i != DestinationString.Length )
            {
              v9 = 0;
              RtlInitAnsiString(&v9, &DestinationString.Buffer[(unsigned int)(i + 1)]);
              v10 = v9;
              RegistryValues = InitializeTelemetryAssertsKMWorkerInternal(&v10);
            }
            break;
          }
        }
        RtlFreeAnsiString(&DestinationString);
      }
    }
    ExFreePoolWithTag(v5, 0x74727341u);
  }
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x140010ab8  push    rbp
0x140010aba  push    rbx
0x140010abb  push    rsi
0x140010abc  push    rdi
0x140010abd  lea     rbp, [rsp-3Fh]
0x140010ac2  sub     rsp, 0E8h
0x140010ac9  xorps   xmm0, xmm0
0x140010acc  mov     rsi, rcx
0x140010acf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140010ad3  xor     eax, eax
0x140010ad5  lock xadd cs:g_AssertsOperational, eax
0x140010add  test    eax, eax
0x140010adf  jz      short loc_140010AE8
0x140010ae1  xor     eax, eax
0x140010ae3  jmp     loc_140010C51
0x140010ae8  xor     edx, edx; SourceString
0x140010aea  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140010aee  mov     ebx, 0C0000017h
0x140010af3  call    cs:__imp_RtlInitAnsiString
0x140010afa  nop     dword ptr [rax+rax+00h]
0x140010aff  movzx   edx, word ptr [rsi]
0x140010b02  mov     ecx, 40h ; '@'
0x140010b07  add     rdx, 2
0x140010b0b  mov     r8d, 74727341h
0x140010b11  call    cs:__imp_ExAllocatePool2
0x140010b18  nop     dword ptr [rax+rax+00h]
0x140010b1d  mov     rdi, rax
0x140010b20  test    rax, rax
0x140010b23  jz      loc_140010C4F
0x140010b29  movzx   r8d, word ptr [rsi]; Size
0x140010b2d  mov     rcx, rax; void *
0x140010b30  mov     rdx, [rsi+8]; Src
0x140010b34  call    memmove
0x140010b39  xorps   xmm0, xmm0
0x140010b3c  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x140010b40  xor     edx, edx; SourceString
0x140010b42  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140010b46  call    cs:__imp_RtlInitUnicodeString
0x140010b4d  nop     dword ptr [rax+rax+00h]
0x140010b52  xor     edx, edx; Val
0x140010b54  lea     rcx, [rbp+57h+var_90]; void *
0x140010b58  lea     r8d, [rdx+70h]; Size
0x140010b5c  call    memset
0x140010b61  lea     rax, aImagepath; "ImagePath"
0x140010b68  mov     [rbp+57h+var_88], 20h ; ' '
0x140010b6f  mov     [rbp+57h+var_80], rax
0x140010b73  lea     r8, [rbp+57h+var_90]
0x140010b77  lea     rax, [rbp+57h+SourceString]
0x140010b7b  mov     [rbp+57h+var_70], 2
0x140010b82  xor     r9d, r9d
0x140010b85  mov     [rbp+57h+var_78], rax
0x140010b89  mov     rdx, rdi
0x140010b8c  mov     [rsp+100h+var_E0], 0
0x140010b95  xor     ecx, ecx
0x140010b97  call    cs:__imp_RtlQueryRegistryValuesEx
0x140010b9e  nop     dword ptr [rax+rax+00h]
0x140010ba3  mov     ebx, eax
0x140010ba5  test    eax, eax
0x140010ba7  js      loc_140010C3B
0x140010bad  mov     r8b, 1; AllocateDestinationString
0x140010bb0  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140010bb4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140010bb8  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140010bbf  nop     dword ptr [rax+rax+00h]
0x140010bc4  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x140010bc8  xor     edx, edx; Tag
0x140010bca  mov     ebx, eax
0x140010bcc  call    cs:__imp_ExFreePoolWithTag
0x140010bd3  nop     dword ptr [rax+rax+00h]
0x140010bd8  test    ebx, ebx
0x140010bda  js      short loc_140010C3B
0x140010bdc  movzx   edx, [rbp+57h+DestinationString.Length]
0x140010be0  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140010be4  lea     ecx, [rdx-1]
0x140010be7  test    ecx, ecx
0x140010be9  jz      short loc_140010C2B
0x140010beb  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140010bf0  jz      short loc_140010BF6
0x140010bf2  dec     ecx
0x140010bf4  jmp     short loc_140010BE7
0x140010bf6  cmp     ecx, edx
0x140010bf8  jz      short loc_140010C2B
0x140010bfa  lea     edx, [rcx+1]
0x140010bfd  xorps   xmm0, xmm0
0x140010c00  add     rdx, r8; SourceString
0x140010c03  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x140010c07  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm0
0x140010c0b  call    cs:__imp_RtlInitAnsiString
0x140010c12  nop     dword ptr [rax+rax+00h]
0x140010c17  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Length]
0x140010c1b  lea     rcx, [rbp+57h+var_A0]
0x140010c1f  movdqa  [rbp+57h+var_A0], xmm0
0x140010c24  call    InitializeTelemetryAssertsKMWorkerInternal
0x140010c29  mov     ebx, eax
0x140010c2b  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x140010c2f  call    cs:__imp_RtlFreeAnsiString
0x140010c36  nop     dword ptr [rax+rax+00h]
0x140010c3b  mov     edx, 74727341h; Tag
0x140010c40  mov     rcx, rdi; P
0x140010c43  call    cs:__imp_ExFreePoolWithTag
0x140010c4a  nop     dword ptr [rax+rax+00h]
0x140010c4f  mov     eax, ebx
0x140010c51  add     rsp, 0E8h
0x140010c58  pop     rdi
0x140010c59  pop     rsi
0x140010c5a  pop     rbx
0x140010c5b  pop     rbp
0x140010c5c  retn
```
