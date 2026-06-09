# SyspartEnumerateDisks

- ea: `0x1400323e8`
- end: `0x1400325e2`
- name: `SyspartEnumerateDisks`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140030ee8`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x14003101c`
- `0x140032314`
- `0x1400323e8`

## import_xrefs

- `ntoskrnl!swprintf_s` at `0x14003257c`
- `ntoskrnl!swprintf_s` at `0x14003257c`
- `ntoskrnl!ExAllocatePool2` at `0x140032493`
- `ntoskrnl!ExAllocatePool2` at `0x140032528`
- `ntoskrnl!ExAllocatePool2` at `0x140032493`
- `ntoskrnl!ExAllocatePool2` at `0x140032528`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x1400324cf`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x1400324cf`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x140032467`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x140032467`

## pseudocode

```c
__int64 __fastcall SyspartEnumerateDisks(__int64 a1, __int64 a2)
{
  NTSTATUS v3; // ebx
  ULONG i; // edi
  _WORD *Pool2; // rsi
  wchar_t *v6; // r14
  wchar_t **v7; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Context; // [rsp+D0h] [rbp+50h] BYREF
  void *DirectoryHandle; // [rsp+D8h] [rbp+58h] BYREF

  Context = 0;
  DirectoryHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString_0(&DestinationString, L"\\Device");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenDirectoryObject(&DirectoryHandle, 1u, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    for ( i = 4096; ; i += 4096 )
    {
      Pool2 = (_WORD *)ExAllocatePool2(256, i, 1263556947);
      if ( !Pool2 )
      {
        v3 = -1073741801;
        goto LABEL_17;
      }
      Context = 0;
      v3 = ZwQueryDirectoryObject(DirectoryHandle, Pool2, i, 0, 1u, &Context, 0);
      if ( v3 != 261 )
        break;
      ExFreePoolWithTag_0(Pool2, 0);
    }
    ZwClose_0(DirectoryHandle);
    DirectoryHandle = 0;
    if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147483622 )
    {
      v6 = (wchar_t *)ExAllocatePool2(256, 106, 1263556947);
      if ( v6 )
      {
        v3 = 0;
        v7 = (wchar_t **)Pool2;
        if ( *Pool2 )
        {
          do
          {
            if ( (unsigned __int8)SiIsValidDiskDevice(v7[1], v7[3]) )
            {
              swprintf_s(v6, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", 0, 0);
              if ( (unsigned __int8)BiGetNtPartitionPathCallback(v6, 0, a2) )
                break;
            }
            v7 += 4;
          }
          while ( *(_WORD *)v7 );
        }
        ExFreePoolWithTag_0(v6, 0);
      }
      else
      {
        v3 = -1073741801;
      }
    }
    ExFreePoolWithTag_0(Pool2, 0);
  }
LABEL_17:
  if ( DirectoryHandle )
    ZwClose_0(DirectoryHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400323e8  mov     [rsp-38h+arg_0], rcx
0x1400323ed  push    rbp
0x1400323ee  push    rbx
0x1400323ef  push    rsi
0x1400323f0  push    rdi
0x1400323f1  push    r12
0x1400323f3  push    r14
0x1400323f5  push    r15
0x1400323f7  mov     rbp, rsp
0x1400323fa  sub     rsp, 80h
0x140032401  xorps   xmm0, xmm0
0x140032404  lea     rcx, [rbp+DestinationString]; DestinationString
0x140032408  xor     r12d, r12d
0x14003240b  mov     r15, rdx
0x14003240e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140032412  xor     eax, eax
0x140032414  mov     [rbp+arg_10], r12d
0x140032418  lea     rdx, aDevice; "\\Device"
0x14003241f  mov     dword ptr [rbp+arg_0], r12d
0x140032423  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140032427  mov     [rbp+DirectoryHandle], r12
0x14003242b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003242f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140032433  call    RtlInitUnicodeString_0
0x140032438  lea     rax, [rbp+DestinationString]
0x14003243c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140032443  xorps   xmm0, xmm0
0x140032446  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14003244a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003244e  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x140032452  lea     edx, [r12+1]; DesiredAccess
0x140032457  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14003245e  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x140032462  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140032467  call    cs:__imp_ZwOpenDirectoryObject
0x14003246e  nop     dword ptr [rax+rax+00h]
0x140032473  mov     ebx, eax
0x140032475  test    eax, eax
0x140032477  js      loc_1400325BF
0x14003247d  mov     r14d, 1000h
0x140032483  mov     edi, r14d
0x140032486  mov     edx, edi
0x140032488  mov     ecx, 100h
0x14003248d  mov     r8d, 4B505953h
0x140032493  call    cs:__imp_ExAllocatePool2
0x14003249a  nop     dword ptr [rax+rax+00h]
0x14003249f  mov     rsi, rax
0x1400324a2  test    rax, rax
0x1400324a5  jz      loc_1400325BA
0x1400324ab  mov     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x1400324af  lea     rax, [rbp+arg_10]
0x1400324b3  mov     [rsp+80h+ReturnLength], r12; ReturnLength
0x1400324b8  xor     r9d, r9d; ReturnSingleEntry
0x1400324bb  mov     [rsp+80h+Context], rax; Context
0x1400324c0  mov     r8d, edi; BufferLength
0x1400324c3  mov     rdx, rsi; Buffer
0x1400324c6  mov     [rsp+80h+RestartScan], 1; RestartScan
0x1400324cb  mov     [rbp+arg_10], r12d
0x1400324cf  call    cs:__imp_ZwQueryDirectoryObject
0x1400324d6  nop     dword ptr [rax+rax+00h]
0x1400324db  mov     ebx, eax
0x1400324dd  cmp     eax, 105h
0x1400324e2  jnz     short loc_1400324F3
0x1400324e4  xor     edx, edx; Tag
0x1400324e6  mov     rcx, rsi; P
0x1400324e9  call    ExFreePoolWithTag_0
0x1400324ee  add     edi, r14d
0x1400324f1  jmp     short loc_140032486
0x1400324f3  mov     rcx, [rbp+DirectoryHandle]; Handle
0x1400324f7  call    ZwClose_0
0x1400324fc  mov     edx, 80000000h
0x140032501  mov     [rbp+DirectoryHandle], r12
0x140032505  lea     eax, [rbx+rdx]
0x140032508  test    edx, eax
0x14003250a  jnz     short loc_140032518
0x14003250c  cmp     ebx, 8000001Ah
0x140032512  jnz     loc_1400325AE
0x140032518  mov     edx, 6Ah ; 'j'
0x14003251d  mov     ecx, 100h
0x140032522  mov     r8d, 4B505953h
0x140032528  call    cs:__imp_ExAllocatePool2
0x14003252f  nop     dword ptr [rax+rax+00h]
0x140032534  mov     r14, rax
0x140032537  test    rax, rax
0x14003253a  jnz     short loc_140032543
0x14003253c  mov     ebx, 0C0000017h
0x140032541  jmp     short loc_1400325AE
0x140032543  mov     ebx, r12d
0x140032546  mov     rdi, rsi
0x140032549  cmp     [rsi], r12w
0x14003254d  jz      short loc_1400325A4
0x14003254f  mov     rdx, [rdi+18h]; wchar_t *
0x140032553  lea     r8, [rbp+arg_0]
0x140032557  mov     rcx, [rdi+8]; Str1
0x14003255b  call    SiIsValidDiskDevice
0x140032560  test    al, al
0x140032562  jz      short loc_14003259A
0x140032564  mov     r9d, dword ptr [rbp+arg_0]
0x140032568  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%lu\\Partition%lu"
0x14003256f  mov     edx, 35h ; '5'; SizeInWords
0x140032574  mov     qword ptr [rsp+80h+RestartScan], r12
0x140032579  mov     rcx, r14; Dst
0x14003257c  call    cs:__imp_swprintf_s
0x140032583  nop     dword ptr [rax+rax+00h]
0x140032588  mov     edx, dword ptr [rbp+arg_0]
0x14003258b  mov     r8, r15
0x14003258e  mov     rcx, r14
0x140032591  call    BiGetNtPartitionPathCallback
0x140032596  test    al, al
0x140032598  jnz     short loc_1400325A4
0x14003259a  add     rdi, 20h ; ' '
0x14003259e  cmp     [rdi], r12w
0x1400325a2  jnz     short loc_14003254F
0x1400325a4  xor     edx, edx; Tag
0x1400325a6  mov     rcx, r14; P
0x1400325a9  call    ExFreePoolWithTag_0
0x1400325ae  xor     edx, edx; Tag
0x1400325b0  mov     rcx, rsi; P
0x1400325b3  call    ExFreePoolWithTag_0
0x1400325b8  jmp     short loc_1400325BF
0x1400325ba  mov     ebx, 0C0000017h
0x1400325bf  mov     rcx, [rbp+DirectoryHandle]; Handle
0x1400325c3  test    rcx, rcx
0x1400325c6  jz      short loc_1400325CD
0x1400325c8  call    ZwClose_0
0x1400325cd  mov     eax, ebx
0x1400325cf  add     rsp, 80h
0x1400325d6  pop     r15
0x1400325d8  pop     r14
0x1400325da  pop     r12
0x1400325dc  pop     rdi
0x1400325dd  pop     rsi
0x1400325de  pop     rbx
0x1400325df  pop     rbp
0x1400325e0  retn
```
