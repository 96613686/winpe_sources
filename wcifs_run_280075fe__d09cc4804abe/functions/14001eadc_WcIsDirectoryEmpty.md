# WcIsDirectoryEmpty

- ea: `0x14001eadc`
- end: `0x14001ecaf`
- name: `WcIsDirectoryEmpty`
- size: `467`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001ecb8`
- `0x140023c40`
- `0x140027854`

## callees

- `0x1400020c4`
- `0x140014c90`
- `0x14001eadc`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ebd7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ebf6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ebd7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ebf6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001eb1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001eb1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ec30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ec30`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb38`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb38`

## pseudocode

```c
__int64 __fastcall WcIsDirectoryEmpty(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, char *a3)
{
  unsigned int *Pool2; // rbp
  char v8; // si
  int v9; // ebx
  char i; // al
  int v11; // edx
  unsigned int *j; // rdi
  __int64 v13; // rax
  __int64 v14; // [rsp+38h] [rbp-60h]
  UNICODE_STRING String1; // [rsp+50h] [rbp-48h] BYREF
  struct _UNICODE_STRING v16; // [rsp+60h] [rbp-38h] BYREF
  __int64 v17; // [rsp+B8h] [rbp+20h] BYREF

  LODWORD(v17) = 0;
  v16 = 0;
  String1 = 0;
  RtlInitUnicodeString(&v16, L"*");
  Pool2 = (unsigned int *)ExAllocatePool2(256, 0x10000, 1701069655);
  if ( !Pool2 )
    return 3221225626LL;
  v8 = 1;
  v9 = 0;
  for ( i = 1; ; i = 0 )
  {
    if ( !v8 )
      goto LABEL_15;
    v9 = WcEnumerateDirectoryWithMerge(Instance, FileObject, 60, &v16, 0, i, 0x10000u, (__int64)Pool2, 0, &v17);
    if ( v9 < 0 )
      break;
    for ( j = Pool2; ; j = (unsigned int *)((char *)j + v13) )
    {
      String1.Buffer = (PWSTR)(j + 22);
      String1.Length = *((_WORD *)j + 30);
      String1.MaximumLength = String1.Length;
      if ( !RtlEqualUnicodeString(&String1, &stru_14000A600, 1u)
        && !RtlEqualUnicodeString(&String1, &stru_14000A610, 1u) )
      {
        break;
      }
      v13 = *j;
      if ( !(_DWORD)v13 )
        goto LABEL_12;
    }
    v8 = 0;
LABEL_12:
    ;
  }
  if ( v9 == -2147483642 )
  {
    v9 = 0;
LABEL_15:
    *a3 = v8;
    goto LABEL_16;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v14) = v9;
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      10,
      200,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      252,
      v14);
  }
LABEL_16:
  ExFreePoolWithTag(Pool2, 0x65644357u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001eadc  mov     rax, rsp
0x14001eadf  mov     [rax+8], rbx
0x14001eae3  mov     [rax+10h], rbp
0x14001eae7  push    rsi
0x14001eae8  push    rdi
0x14001eae9  push    r12
0x14001eaeb  push    r14
0x14001eaed  push    r15
0x14001eaef  sub     rsp, 70h
0x14001eaf3  mov     r15, rdx
0x14001eaf6  mov     dword ptr [rax+20h], 0
0x14001eafd  mov     r12, rcx
0x14001eb00  lea     rdx, asc_14000A9A8; "*"
0x14001eb07  xorps   xmm0, xmm0
0x14001eb0a  lea     rcx, [rax-38h]; DestinationString
0x14001eb0e  xorps   xmm1, xmm1
0x14001eb11  mov     r14, r8
0x14001eb14  movups  xmmword ptr [rax-38h], xmm0
0x14001eb18  movups  xmmword ptr [rax-48h], xmm1
0x14001eb1c  call    cs:__imp_RtlInitUnicodeString
0x14001eb23  nop     dword ptr [rax+rax+00h]
0x14001eb28  mov     edx, 10000h
0x14001eb2d  mov     ecx, 100h
0x14001eb32  mov     r8d, 65644357h
0x14001eb38  call    cs:__imp_ExAllocatePool2
0x14001eb3f  nop     dword ptr [rax+rax+00h]
0x14001eb44  mov     rbp, rax
0x14001eb47  test    rax, rax
0x14001eb4a  jnz     short loc_14001EB56
0x14001eb4c  mov     eax, 0C000009Ah
0x14001eb51  jmp     loc_14001EC3E
0x14001eb56  mov     sil, 1
0x14001eb59  xor     ebx, ebx
0x14001eb5b  mov     al, sil
0x14001eb5e  test    sil, sil
0x14001eb61  jz      loc_14001EC25
0x14001eb67  lea     rcx, [rsp+98h+arg_18]
0x14001eb6f  mov     r8d, 3Ch ; '<'
0x14001eb75  mov     [rsp+98h+var_50], rcx; __int64
0x14001eb7a  lea     r9, [rsp+98h+var_38]
0x14001eb7f  mov     [rsp+98h+var_58], 0; char
0x14001eb84  mov     rdx, r15; FileObject
0x14001eb87  mov     [rsp+98h+var_60], rbp; __int64
0x14001eb8c  mov     rcx, r12; Instance
0x14001eb8f  mov     [rsp+98h+var_68], 10000h; int
0x14001eb97  mov     [rsp+98h+var_70], al; char
0x14001eb9b  mov     [rsp+98h+var_78], 0; int
0x14001eba3  call    WcEnumerateDirectoryWithMerge
0x14001eba8  mov     ebx, eax
0x14001ebaa  test    eax, eax
0x14001ebac  js      short loc_14001EC1B
0x14001ebae  mov     rdi, rbp
0x14001ebb1  lea     rcx, [rdi+58h]
0x14001ebb5  mov     r8b, 1; CaseInSensitive
0x14001ebb8  mov     [rsp+98h+String1.Buffer], rcx
0x14001ebbd  lea     rdx, stru_14000A600; String2
0x14001ebc4  movzx   ecx, word ptr [rdi+3Ch]
0x14001ebc8  mov     [rsp+98h+String1.Length], cx
0x14001ebcd  mov     [rsp+98h+String1.MaximumLength], cx
0x14001ebd2  lea     rcx, [rsp+98h+String1]; String1
0x14001ebd7  call    cs:__imp_RtlEqualUnicodeString
0x14001ebde  nop     dword ptr [rax+rax+00h]
0x14001ebe3  test    al, al
0x14001ebe5  jnz     short loc_14001EC06
0x14001ebe7  mov     r8b, 1; CaseInSensitive
0x14001ebea  lea     rdx, stru_14000A610; String2
0x14001ebf1  lea     rcx, [rsp+98h+String1]; String1
0x14001ebf6  call    cs:__imp_RtlEqualUnicodeString
0x14001ebfd  nop     dword ptr [rax+rax+00h]
0x14001ec02  test    al, al
0x14001ec04  jz      short loc_14001EC11
0x14001ec06  mov     eax, [rdi]
0x14001ec08  test    eax, eax
0x14001ec0a  jz      short loc_14001EC14
0x14001ec0c  add     rdi, rax
0x14001ec0f  jmp     short loc_14001EBB1
0x14001ec11  xor     sil, sil
0x14001ec14  xor     al, al
0x14001ec16  jmp     loc_14001EB5E
0x14001ec1b  cmp     ebx, 80000006h
0x14001ec21  jnz     short loc_14001EC58
0x14001ec23  xor     ebx, ebx
0x14001ec25  mov     [r14], sil
0x14001ec28  mov     edx, 65644357h; Tag
0x14001ec2d  mov     rcx, rbp; P
0x14001ec30  call    cs:__imp_ExFreePoolWithTag
0x14001ec37  nop     dword ptr [rax+rax+00h]
0x14001ec3c  mov     eax, ebx
0x14001ec3e  lea     r11, [rsp+98h+var_28]
0x14001ec43  mov     rbx, [r11+30h]
0x14001ec47  mov     rbp, [r11+38h]
0x14001ec4b  mov     rsp, r11
0x14001ec4e  pop     r15
0x14001ec50  pop     r14
0x14001ec52  pop     r12
0x14001ec54  pop     rdi
0x14001ec55  pop     rsi
0x14001ec56  retn
0x14001ec58  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ec5f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ec66  jz      short loc_14001EC28
0x14001ec68  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec6f  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001ec76  mov     dword ptr [rsp+98h+var_60], ebx
0x14001ec7a  mov     r9d, 0C8h
0x14001ec80  mov     [rsp+98h+var_68], 22FCh
0x14001ec88  mov     r8d, 0Ah
0x14001ec8e  mov     qword ptr [rsp+98h+var_70], rax
0x14001ec93  mov     dl, 2
0x14001ec95  mov     rcx, [rcx+40h]
0x14001ec99  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001eca0  mov     qword ptr [rsp+98h+var_78], rax
0x14001eca5  call    WPP_RECORDER_SF_sDd
0x14001ecaa  jmp     loc_14001EC28
```
