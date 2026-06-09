# WcRemoveTombstonesFromDirectory

- ea: `0x14001cff0`
- end: `0x14001d1cf`
- name: `WcRemoveTombstonesFromDirectory`
- size: `479`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400278a4`

## callees

- `0x1400020c4`
- `0x14001c244`
- `0x14001cff0`
- `0x140020434`
- `0x14002b94c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001d084`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d084`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d1b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d1b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d186`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d186`
- `ntoskrnl!ExAllocatePool2` at `0x14001d03c`
- `ntoskrnl!ExAllocatePool2` at `0x14001d03c`
- `FLTMGR!FltClose` at `0x14001d19b`
- `FLTMGR!FltClose` at `0x14001d19b`

## pseudocode

```c
__int64 __fastcall WcRemoveTombstonesFromDirectory(__int64 a1, struct _FLT_INSTANCE *a2, struct _FILE_OBJECT *a3)
{
  unsigned int *Pool2; // rsi
  int v8; // ebx
  UCHAR v9; // bl
  int v10; // edx
  unsigned int *i; // rdi
  __int64 v12; // rax
  __int64 v13; // [rsp+38h] [rbp-21h]
  PVOID Object; // [rsp+50h] [rbp-9h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-1h] BYREF
  UNICODE_STRING v16; // [rsp+60h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  int v18; // [rsp+D8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  Object = 0;
  DestinationString = 0;
  v16 = 0;
  Pool2 = (unsigned int *)ExAllocatePool2(256, 0x10000, 1701069655);
  if ( !Pool2 )
    return 3221225626LL;
  v8 = WcReopenFile(a2, a3, &FileHandle, (PFILE_OBJECT *)&Object);
  if ( v8 >= 0 )
  {
    v9 = 1;
    RtlInitUnicodeString(&DestinationString, L"*");
LABEL_5:
    v8 = WcEnumerateDirectory(
           a2,
           (struct _FILE_OBJECT *)Object,
           0x3Cu,
           &DestinationString,
           0,
           v9,
           0x10000u,
           Pool2,
           &v18);
    if ( v8 < 0 )
    {
      if ( v8 == -2147483642 )
      {
        v8 = 0;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v13) = v8;
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v10,
          19,
          16,
          (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
          180,
          v13);
      }
    }
    else
    {
      for ( i = Pool2; ; i = (unsigned int *)((char *)i + v12) )
      {
        if ( i[17] == -1610612705 )
        {
          v16.Buffer = (PWSTR)(i + 22);
          v16.Length = *((_WORD *)i + 30);
          v16.MaximumLength = v16.Length;
          v8 = WcDeleteTombstone(a1, a2, (struct _FILE_OBJECT *)Object, FileHandle, &v16);
          if ( v8 < 0 )
            break;
        }
        v12 = *i;
        if ( !(_DWORD)v12 )
        {
          v9 = 0;
          goto LABEL_5;
        }
      }
    }
  }
  ExFreePoolWithTag(Pool2, 0x65644357u);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001cff0  push    rbp
0x14001cff2  push    rbx
0x14001cff3  push    rsi
0x14001cff4  push    rdi
0x14001cff5  push    r14
0x14001cff7  push    r15
0x14001cff9  lea     rbp, [rsp-2Fh]
0x14001cffe  sub     rsp, 88h
0x14001d005  mov     rbx, r8
0x14001d008  mov     [rbp+57h+FileHandle], 0
0x14001d010  mov     r14, rdx
0x14001d013  mov     [rbp+57h+Object], 0
0x14001d01b  mov     r15, rcx
0x14001d01e  xorps   xmm0, xmm0
0x14001d021  xorps   xmm1, xmm1
0x14001d024  mov     edx, 10000h
0x14001d029  mov     ecx, 100h
0x14001d02e  mov     r8d, 65644357h
0x14001d034  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001d038  movups  [rbp+57h+var_50], xmm1
0x14001d03c  call    cs:__imp_ExAllocatePool2
0x14001d043  nop     dword ptr [rax+rax+00h]
0x14001d048  mov     rsi, rax
0x14001d04b  test    rax, rax
0x14001d04e  jnz     short loc_14001D05A
0x14001d050  mov     eax, 0C000009Ah
0x14001d055  jmp     loc_14001D1BE
0x14001d05a  lea     r9, [rbp+57h+Object]; PFILE_OBJECT *
0x14001d05e  mov     rdx, rbx; FileObject
0x14001d061  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14001d065  mov     rcx, r14; Instance
0x14001d068  call    WcReopenFile
0x14001d06d  mov     ebx, eax
0x14001d06f  test    eax, eax
0x14001d071  js      loc_14001D17E
0x14001d077  lea     rdx, asc_14000A9A8; "*"
0x14001d07e  mov     bl, 1
0x14001d080  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001d084  call    cs:__imp_RtlInitUnicodeString
0x14001d08b  nop     dword ptr [rax+rax+00h]
0x14001d090  mov     rdx, [rbp+57h+Object]
0x14001d094  lea     rax, [rbp+57h+arg_18]
0x14001d098  mov     [rsp+0B0h+var_70], rax
0x14001d09d  lea     r9, [rbp+57h+DestinationString]
0x14001d0a1  mov     [rsp+0B0h+var_78], rsi
0x14001d0a6  mov     r8d, 3Ch ; '<'
0x14001d0ac  mov     [rsp+0B0h+var_80], 10000h
0x14001d0b4  mov     rcx, r14
0x14001d0b7  mov     byte ptr [rsp+0B0h+var_88], bl
0x14001d0bb  mov     dword ptr [rsp+0B0h+var_90], 0
0x14001d0c3  call    WcEnumerateDirectory
0x14001d0c8  mov     ebx, eax
0x14001d0ca  test    eax, eax
0x14001d0cc  js      short loc_14001D122
0x14001d0ce  mov     rdi, rsi
0x14001d0d1  cmp     dword ptr [rdi+44h], 0A000001Fh
0x14001d0d8  jnz     short loc_14001D110
0x14001d0da  mov     r9, [rbp+57h+FileHandle]
0x14001d0de  lea     rax, [rdi+58h]
0x14001d0e2  mov     r8, [rbp+57h+Object]
0x14001d0e6  mov     rdx, r14
0x14001d0e9  mov     qword ptr [rbp+57h+var_50+8], rax
0x14001d0ed  mov     rcx, r15
0x14001d0f0  movzx   eax, word ptr [rdi+3Ch]
0x14001d0f4  mov     word ptr [rbp+57h+var_50], ax
0x14001d0f8  mov     word ptr [rbp+57h+var_50+2], ax
0x14001d0fc  lea     rax, [rbp+57h+var_50]
0x14001d100  mov     [rsp+0B0h+var_90], rax
0x14001d105  call    WcDeleteTombstone
0x14001d10a  mov     ebx, eax
0x14001d10c  test    eax, eax
0x14001d10e  js      short loc_14001D17E
0x14001d110  mov     eax, [rdi]
0x14001d112  test    eax, eax
0x14001d114  jz      short loc_14001D11B
0x14001d116  add     rdi, rax
0x14001d119  jmp     short loc_14001D0D1
0x14001d11b  xor     bl, bl
0x14001d11d  jmp     loc_14001D090
0x14001d122  cmp     ebx, 80000006h
0x14001d128  jnz     short loc_14001D12E
0x14001d12a  xor     ebx, ebx
0x14001d12c  jmp     short loc_14001D17E
0x14001d12e  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d135  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d13c  jz      short loc_14001D17E
0x14001d13e  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001d145  lea     rax, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x14001d14c  mov     dword ptr [rsp+0B0h+var_78], ebx
0x14001d150  mov     r9d, 10h
0x14001d156  mov     [rsp+0B0h+var_80], 2B4h
0x14001d15e  mov     dl, 2
0x14001d160  mov     [rsp+0B0h+var_88], rax
0x14001d165  lea     rax, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x14001d16c  mov     rcx, [rcx+40h]
0x14001d170  lea     r8d, [r9+3]
0x14001d174  mov     [rsp+0B0h+var_90], rax
0x14001d179  call    WPP_RECORDER_SF_sDd
0x14001d17e  mov     edx, 65644357h; Tag
0x14001d183  mov     rcx, rsi; P
0x14001d186  call    cs:__imp_ExFreePoolWithTag
0x14001d18d  nop     dword ptr [rax+rax+00h]
0x14001d192  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001d196  test    rcx, rcx
0x14001d199  jz      short loc_14001D1A7
0x14001d19b  call    cs:__imp_FltClose
0x14001d1a2  nop     dword ptr [rax+rax+00h]
0x14001d1a7  mov     rcx, [rbp+57h+Object]; Object
0x14001d1ab  test    rcx, rcx
0x14001d1ae  jz      short loc_14001D1BC
0x14001d1b0  call    cs:__imp_ObfDereferenceObject
0x14001d1b7  nop     dword ptr [rax+rax+00h]
0x14001d1bc  mov     eax, ebx
0x14001d1be  add     rsp, 88h
0x14001d1c5  pop     r15
0x14001d1c7  pop     r14
0x14001d1c9  pop     rdi
0x14001d1ca  pop     rsi
0x14001d1cb  pop     rbx
0x14001d1cc  pop     rbp
0x14001d1cd  retn
```
