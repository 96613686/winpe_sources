# SyspartEnumerateDisks

- ea: `0x140032438`
- end: `0x140032632`
- name: `SyspartEnumerateDisks`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140030f38`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x14003106c`
- `0x140032364`
- `0x140032438`

## import_xrefs

- `ntoskrnl!swprintf_s` at `0x1400325cc`
- `ntoskrnl!swprintf_s` at `0x1400325cc`
- `ntoskrnl!ExAllocatePool2` at `0x1400324e3`
- `ntoskrnl!ExAllocatePool2` at `0x140032578`
- `ntoskrnl!ExAllocatePool2` at `0x1400324e3`
- `ntoskrnl!ExAllocatePool2` at `0x140032578`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x14003251f`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x14003251f`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x1400324b7`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x1400324b7`

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
0x140032438  mov     [rsp-38h+arg_0], rcx
0x14003243d  push    rbp
0x14003243e  push    rbx
0x14003243f  push    rsi
0x140032440  push    rdi
0x140032441  push    r12
0x140032443  push    r14
0x140032445  push    r15
0x140032447  mov     rbp, rsp
0x14003244a  sub     rsp, 80h
0x140032451  xorps   xmm0, xmm0
0x140032454  lea     rcx, [rbp+DestinationString]; DestinationString
0x140032458  xor     r12d, r12d
0x14003245b  mov     r15, rdx
0x14003245e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140032462  xor     eax, eax
0x140032464  mov     [rbp+arg_10], r12d
0x140032468  lea     rdx, aDevice; "\\Device"
0x14003246f  mov     dword ptr [rbp+arg_0], r12d
0x140032473  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140032477  mov     [rbp+DirectoryHandle], r12
0x14003247b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003247f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140032483  call    RtlInitUnicodeString_0
0x140032488  lea     rax, [rbp+DestinationString]
0x14003248c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140032493  xorps   xmm0, xmm0
0x140032496  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14003249a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003249e  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x1400324a2  lea     edx, [r12+1]; DesiredAccess
0x1400324a7  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400324ae  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x1400324b2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400324b7  call    cs:__imp_ZwOpenDirectoryObject
0x1400324be  nop     dword ptr [rax+rax+00h]
0x1400324c3  mov     ebx, eax
0x1400324c5  test    eax, eax
0x1400324c7  js      loc_14003260F
0x1400324cd  mov     r14d, 1000h
0x1400324d3  mov     edi, r14d
0x1400324d6  mov     edx, edi
0x1400324d8  mov     ecx, 100h
0x1400324dd  mov     r8d, 4B505953h
0x1400324e3  call    cs:__imp_ExAllocatePool2
0x1400324ea  nop     dword ptr [rax+rax+00h]
0x1400324ef  mov     rsi, rax
0x1400324f2  test    rax, rax
0x1400324f5  jz      loc_14003260A
0x1400324fb  mov     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x1400324ff  lea     rax, [rbp+arg_10]
0x140032503  mov     [rsp+80h+ReturnLength], r12; ReturnLength
0x140032508  xor     r9d, r9d; ReturnSingleEntry
0x14003250b  mov     [rsp+80h+Context], rax; Context
0x140032510  mov     r8d, edi; BufferLength
0x140032513  mov     rdx, rsi; Buffer
0x140032516  mov     [rsp+80h+RestartScan], 1; RestartScan
0x14003251b  mov     [rbp+arg_10], r12d
0x14003251f  call    cs:__imp_ZwQueryDirectoryObject
0x140032526  nop     dword ptr [rax+rax+00h]
0x14003252b  mov     ebx, eax
0x14003252d  cmp     eax, 105h
0x140032532  jnz     short loc_140032543
0x140032534  xor     edx, edx; Tag
0x140032536  mov     rcx, rsi; P
0x140032539  call    ExFreePoolWithTag_0
0x14003253e  add     edi, r14d
0x140032541  jmp     short loc_1400324D6
0x140032543  mov     rcx, [rbp+DirectoryHandle]; Handle
0x140032547  call    ZwClose_0
0x14003254c  mov     edx, 80000000h
0x140032551  mov     [rbp+DirectoryHandle], r12
0x140032555  lea     eax, [rbx+rdx]
0x140032558  test    edx, eax
0x14003255a  jnz     short loc_140032568
0x14003255c  cmp     ebx, 8000001Ah
0x140032562  jnz     loc_1400325FE
0x140032568  mov     edx, 6Ah ; 'j'
0x14003256d  mov     ecx, 100h
0x140032572  mov     r8d, 4B505953h
0x140032578  call    cs:__imp_ExAllocatePool2
0x14003257f  nop     dword ptr [rax+rax+00h]
0x140032584  mov     r14, rax
0x140032587  test    rax, rax
0x14003258a  jnz     short loc_140032593
0x14003258c  mov     ebx, 0C0000017h
0x140032591  jmp     short loc_1400325FE
0x140032593  mov     ebx, r12d
0x140032596  mov     rdi, rsi
0x140032599  cmp     [rsi], r12w
0x14003259d  jz      short loc_1400325F4
0x14003259f  mov     rdx, [rdi+18h]; wchar_t *
0x1400325a3  lea     r8, [rbp+arg_0]
0x1400325a7  mov     rcx, [rdi+8]; Str1
0x1400325ab  call    SiIsValidDiskDevice
0x1400325b0  test    al, al
0x1400325b2  jz      short loc_1400325EA
0x1400325b4  mov     r9d, dword ptr [rbp+arg_0]
0x1400325b8  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%lu\\Partition%lu"
0x1400325bf  mov     edx, 35h ; '5'; SizeInWords
0x1400325c4  mov     qword ptr [rsp+80h+RestartScan], r12
0x1400325c9  mov     rcx, r14; Dst
0x1400325cc  call    cs:__imp_swprintf_s
0x1400325d3  nop     dword ptr [rax+rax+00h]
0x1400325d8  mov     edx, dword ptr [rbp+arg_0]
0x1400325db  mov     r8, r15
0x1400325de  mov     rcx, r14
0x1400325e1  call    BiGetNtPartitionPathCallback
0x1400325e6  test    al, al
0x1400325e8  jnz     short loc_1400325F4
0x1400325ea  add     rdi, 20h ; ' '
0x1400325ee  cmp     [rdi], r12w
0x1400325f2  jnz     short loc_14003259F
0x1400325f4  xor     edx, edx; Tag
0x1400325f6  mov     rcx, r14; P
0x1400325f9  call    ExFreePoolWithTag_0
0x1400325fe  xor     edx, edx; Tag
0x140032600  mov     rcx, rsi; P
0x140032603  call    ExFreePoolWithTag_0
0x140032608  jmp     short loc_14003260F
0x14003260a  mov     ebx, 0C0000017h
0x14003260f  mov     rcx, [rbp+DirectoryHandle]; Handle
0x140032613  test    rcx, rcx
0x140032616  jz      short loc_14003261D
0x140032618  call    ZwClose_0
0x14003261d  mov     eax, ebx
0x14003261f  add     rsp, 80h
0x140032626  pop     r15
0x140032628  pop     r14
0x14003262a  pop     r12
0x14003262c  pop     rdi
0x14003262d  pop     rsi
0x14003262e  pop     rbx
0x14003262f  pop     rbp
0x140032630  retn
```
