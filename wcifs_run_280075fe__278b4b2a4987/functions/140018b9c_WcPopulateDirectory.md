# WcPopulateDirectory

- ea: `0x140018b9c`
- end: `0x140018e1f`
- name: `WcPopulateDirectory`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140017f64`

## callees

- `0x1400020c4`
- `0x1400048a4`
- `0x140018b9c`
- `0x14002b8fc`
- `0x140030d54`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140018c8a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018ca9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018c8a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018ca9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018c09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018df8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018df8`
- `ntoskrnl!ExAllocatePool2` at `0x140018bd7`
- `ntoskrnl!ExAllocatePool2` at `0x140018bd7`

## pseudocode

```c
__int64 __fastcall WcPopulateDirectory(
        __int64 *a1,
        __int64 a2,
        struct _LIST_ENTRY *a3,
        struct _FILE_OBJECT *a4,
        void *a5,
        char *a6,
        _QWORD *a7)
{
  unsigned int *Pool2; // rbp
  char v11; // r14
  __int64 v12; // rsi
  char v13; // bl
  __int64 v14; // r15
  int v15; // edx
  int v16; // ebx
  unsigned int *i; // rdi
  int v18; // eax
  int v19; // edx
  __int64 v20; // rax
  char v21[8]; // [rsp+38h] [rbp-70h]
  _BYTE v22[8]; // [rsp+50h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-50h] BYREF

  DestinationString = 0;
  Pool2 = (unsigned int *)ExAllocatePool2(256, 0x10000, 1701069655);
  if ( !Pool2 )
    return 3221225626LL;
  v11 = 1;
  v12 = 0;
  v13 = 1;
  RtlInitUnicodeString(&DestinationString, L"*");
  v14 = *a1;
LABEL_4:
  v16 = WcEnumerateDirectory(
          **(_QWORD **)(v14 + 24),
          *(_QWORD *)(*(_QWORD *)(v14 + 24) + 16LL),
          12,
          (unsigned int)&DestinationString,
          0,
          v13,
          0x10000,
          (__int64)Pool2,
          (__int64)v22);
  if ( v16 >= 0 )
  {
    for ( i = Pool2; ; i = (unsigned int *)((char *)i + v20) )
    {
      DestinationString.Buffer = (PWSTR)(i + 3);
      DestinationString.Length = *((_WORD *)i + 4);
      DestinationString.MaximumLength = DestinationString.Length;
      if ( !RtlEqualUnicodeString(&DestinationString, &stru_14000A5C0, 1u)
        && !RtlEqualUnicodeString(&DestinationString, &stru_14000A5D0, 1u) )
      {
        v18 = WcPopulateFile(&DestinationString, a1, a2, a5, a3, a4, 0, 0);
        v16 = 0;
        if ( v18 != -1073741267 )
          v16 = v18;
        if ( v16 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_sDZd(
              WPP_GLOBAL_Control->DeviceExtension,
              v19,
              10,
              25,
              (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
              105,
              (__int64)&DestinationString,
              v16);
          }
          goto LABEL_22;
        }
        v11 = 0;
        ++v12;
      }
      v20 = *i;
      if ( !(_DWORD)v20 )
      {
        v13 = 0;
        goto LABEL_4;
      }
    }
  }
  if ( v16 == -2147483642 )
  {
    v16 = 0;
    *a6 = v11;
    if ( a7 )
      *a7 = v12;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    *(_DWORD *)v21 = v16;
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      10,
      24,
      (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
      49,
      *(_QWORD *)v21);
  }
LABEL_22:
  ExFreePoolWithTag(Pool2, 0x65644357u);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140018b9c  mov     rax, rsp
0x140018b9f  mov     [rax+8], rbx
0x140018ba3  mov     [rax+18h], r8
0x140018ba7  mov     [rax+10h], rdx
0x140018bab  push    rbp
0x140018bac  push    rsi
0x140018bad  push    rdi
0x140018bae  push    r12
0x140018bb0  push    r13
0x140018bb2  push    r14
0x140018bb4  push    r15
0x140018bb6  sub     rsp, 70h
0x140018bba  mov     r12, rcx
0x140018bbd  xorps   xmm0, xmm0
0x140018bc0  mov     ecx, 100h
0x140018bc5  mov     edx, 10000h
0x140018bca  mov     r8d, 65644357h
0x140018bd0  mov     r13, r9
0x140018bd3  movups  xmmword ptr [rax-50h], xmm0
0x140018bd7  call    cs:__imp_ExAllocatePool2
0x140018bde  nop     dword ptr [rax+rax+00h]
0x140018be3  mov     rbp, rax
0x140018be6  test    rax, rax
0x140018be9  jnz     short loc_140018BF5
0x140018beb  mov     eax, 0C000009Ah
0x140018bf0  jmp     loc_140018E06
0x140018bf5  mov     r14b, 1
0x140018bf8  lea     rdx, asc_14000A9A8; "*"
0x140018bff  xor     esi, esi
0x140018c01  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x140018c06  mov     bl, r14b
0x140018c09  call    cs:__imp_RtlInitUnicodeString
0x140018c10  nop     dword ptr [rax+rax+00h]
0x140018c15  mov     r15, [r12]
0x140018c19  mov     rcx, [r15+18h]
0x140018c1d  lea     rax, [rsp+0A8h+var_58]
0x140018c22  mov     [rsp+0A8h+var_68], rax
0x140018c27  lea     r9, [rsp+0A8h+DestinationString]
0x140018c2c  mov     qword ptr [rsp+0A8h+var_70], rbp
0x140018c31  mov     r8d, 0Ch
0x140018c37  mov     dword ptr [rsp+0A8h+var_78], 10000h
0x140018c3f  mov     rdx, [rcx+10h]
0x140018c43  mov     rcx, [rcx]
0x140018c46  mov     byte ptr [rsp+0A8h+FileObject], bl
0x140018c4a  mov     dword ptr [rsp+0A8h+var_88], 0
0x140018c52  call    WcEnumerateDirectory
0x140018c57  mov     ebx, eax
0x140018c59  test    eax, eax
0x140018c5b  js      loc_140018D79
0x140018c61  mov     rdi, rbp
0x140018c64  lea     rax, [rdi+0Ch]
0x140018c68  mov     r8b, 1; CaseInSensitive
0x140018c6b  mov     [rsp+0A8h+DestinationString.Buffer], rax
0x140018c70  lea     rdx, stru_14000A5C0; String2
0x140018c77  movzx   eax, word ptr [rdi+8]
0x140018c7b  lea     rcx, [rsp+0A8h+DestinationString]; String1
0x140018c80  mov     [rsp+0A8h+DestinationString.Length], ax
0x140018c85  mov     [rsp+0A8h+DestinationString.MaximumLength], ax
0x140018c8a  call    cs:__imp_RtlEqualUnicodeString
0x140018c91  nop     dword ptr [rax+rax+00h]
0x140018c96  test    al, al
0x140018c98  jnz     short loc_140018D04
0x140018c9a  mov     r8b, 1; CaseInSensitive
0x140018c9d  lea     rdx, stru_14000A5D0; String2
0x140018ca4  lea     rcx, [rsp+0A8h+DestinationString]; String1
0x140018ca9  call    cs:__imp_RtlEqualUnicodeString
0x140018cb0  nop     dword ptr [rax+rax+00h]
0x140018cb5  test    al, al
0x140018cb7  jnz     short loc_140018D04
0x140018cb9  mov     r9, [rsp+0A8h+arg_20]
0x140018cc1  lea     rcx, [rsp+0A8h+DestinationString]; FileName
0x140018cc6  mov     r8, [rsp+0A8h+arg_8]
0x140018cce  mov     rdx, r12
0x140018cd1  mov     [rsp+0A8h+var_70], al; char
0x140018cd5  mov     [rsp+0A8h+var_78], al; char
0x140018cd9  mov     rax, [rsp+0A8h+arg_10]
0x140018ce1  mov     [rsp+0A8h+FileObject], r13; FileObject
0x140018ce6  mov     [rsp+0A8h+var_88], rax; __int64
0x140018ceb  call    WcPopulateFile
0x140018cf0  xor     ebx, ebx
0x140018cf2  cmp     eax, 0C000022Dh
0x140018cf7  cmovnz  ebx, eax
0x140018cfa  test    ebx, ebx
0x140018cfc  js      short loc_140018D19
0x140018cfe  xor     r14b, r14b
0x140018d01  inc     rsi
0x140018d04  mov     eax, [rdi]
0x140018d06  test    eax, eax
0x140018d08  jz      short loc_140018D12
0x140018d0a  add     rdi, rax
0x140018d0d  jmp     loc_140018C64
0x140018d12  xor     bl, bl
0x140018d14  jmp     loc_140018C19
0x140018d19  lea     rax, WPP_RECORDER_INITIALIZED
0x140018d20  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018d27  jz      loc_140018DF0
0x140018d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d34  lea     rax, [rsp+0A8h+DestinationString]
0x140018d39  mov     dword ptr [rsp+0A8h+var_68], ebx
0x140018d3d  mov     r9d, 19h
0x140018d43  mov     qword ptr [rsp+0A8h+var_70], rax
0x140018d48  mov     dl, 2
0x140018d4a  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140018d51  mov     dword ptr [rsp+0A8h+var_78], 869h
0x140018d59  mov     rcx, [rcx+40h]
0x140018d5d  mov     [rsp+0A8h+FileObject], rax
0x140018d62  lea     r8d, [r9-0Fh]
0x140018d66  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018d6d  mov     [rsp+0A8h+var_88], rax
0x140018d72  call    WPP_RECORDER_SF_sDZd
0x140018d77  jmp     short loc_140018DF0
0x140018d79  cmp     ebx, 80000006h
0x140018d7f  jnz     short loc_140018DA0
0x140018d81  mov     rax, [rsp+0A8h+arg_28]
0x140018d89  xor     ebx, ebx
0x140018d8b  mov     [rax], r14b
0x140018d8e  mov     rax, [rsp+0A8h+arg_30]
0x140018d96  test    rax, rax
0x140018d99  jz      short loc_140018DF0
0x140018d9b  mov     [rax], rsi
0x140018d9e  jmp     short loc_140018DF0
0x140018da0  lea     rax, WPP_RECORDER_INITIALIZED
0x140018da7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018dae  jz      short loc_140018DF0
0x140018db0  mov     rcx, cs:WPP_GLOBAL_Control
0x140018db7  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140018dbe  mov     dword ptr [rsp+0A8h+var_70], ebx
0x140018dc2  mov     r9d, 18h
0x140018dc8  mov     dword ptr [rsp+0A8h+var_78], 831h
0x140018dd0  mov     dl, 2
0x140018dd2  mov     [rsp+0A8h+FileObject], rax
0x140018dd7  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018dde  mov     rcx, [rcx+40h]
0x140018de2  lea     r8d, [r9-0Eh]
0x140018de6  mov     [rsp+0A8h+var_88], rax
0x140018deb  call    WPP_RECORDER_SF_sDd
0x140018df0  mov     edx, 65644357h; Tag
0x140018df5  mov     rcx, rbp; P
0x140018df8  call    cs:__imp_ExFreePoolWithTag
0x140018dff  nop     dword ptr [rax+rax+00h]
0x140018e04  mov     eax, ebx
0x140018e06  mov     rbx, [rsp+0A8h+arg_0]
0x140018e0e  add     rsp, 70h
0x140018e12  pop     r15
0x140018e14  pop     r14
0x140018e16  pop     r13
0x140018e18  pop     r12
0x140018e1a  pop     rdi
0x140018e1b  pop     rsi
0x140018e1c  pop     rbp
0x140018e1d  retn
```
