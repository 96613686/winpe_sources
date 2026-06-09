# BiGetNtPartitionPathCallback

- ea: `0x14003101c`
- end: `0x14003132a`
- name: `BiGetNtPartitionPathCallback`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400323e8`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x14000db18`
- `0x140030d30`
- `0x14003101c`
- `0x1400314d0`

## import_xrefs

- `ntoskrnl!swprintf_s` at `0x140031147`
- `ntoskrnl!swprintf_s` at `0x140031299`
- `ntoskrnl!swprintf_s` at `0x140031147`
- `ntoskrnl!swprintf_s` at `0x140031299`
- `ntoskrnl!_wcsicmp` at `0x1400311eb`
- `ntoskrnl!_wcsicmp` at `0x1400312c3`
- `ntoskrnl!_wcsicmp` at `0x1400311eb`
- `ntoskrnl!_wcsicmp` at `0x1400312c3`

## pseudocode

```c
char __fastcall BiGetNtPartitionPathCallback(__int64 a1, unsigned int a2, __int64 a3)
{
  wchar_t *v3; // r14
  wchar_t *v4; // rsi
  __int64 v5; // rbx
  _DWORD *v6; // r13
  char v7; // di
  unsigned __int64 v8; // rcx
  _DWORD *v9; // r15
  wchar_t *v10; // rbx
  int v11; // r14d
  wchar_t *v12; // rsi
  const wchar_t *v13; // rax
  _QWORD *v15; // rsi
  __int64 i; // rax
  __int64 v17; // r13
  int v18; // eax
  const wchar_t *PartitionVhdFilePath; // rax
  bool v20; // zf
  __int64 v21; // rcx
  __int64 ShareAccess; // [rsp+20h] [rbp-89h]
  PVOID P; // [rsp+30h] [rbp-79h] BYREF
  wchar_t *Dst; // [rsp+38h] [rbp-71h]
  void *FileHandle; // [rsp+40h] [rbp-69h] BYREF
  _QWORD *v26; // [rsp+48h] [rbp-61h]
  wchar_t *Str1; // [rsp+50h] [rbp-59h]
  _OWORD v28[2]; // [rsp+58h] [rbp-51h] BYREF
  __int64 v29; // [rsp+78h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp+17h] BYREF
  char v35; // [rsp+128h] [rbp+7Fh]

  v3 = *(wchar_t **)(a3 + 8);
  v4 = *(wchar_t **)(a3 + 16);
  v5 = *(_QWORD *)(a3 + 24);
  v6 = *(_DWORD **)(a3 + 40);
  v29 = 0;
  v7 = 0;
  FileHandle = 0;
  P = 0;
  v35 = *(_BYTE *)(a3 + 1);
  v26 = *(_QWORD **)(a3 + 32);
  memset(v28, 0, sizeof(v28));
  Str1 = v3;
  Dst = v4;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( (int)BiGetDriveLayoutBlock(a1, &P, v28) < 0 )
    return v7;
  if ( LODWORD(v28[0]) == 7 )
  {
    if ( *(_DWORD *)v5 != 7 )
      goto LABEL_8;
  }
  else if ( v3 )
  {
    goto LABEL_8;
  }
  v8 = *(_QWORD *)(v5 + 4) - *(_QWORD *)((char *)v28 + 4);
  if ( !v8 )
  {
    v8 = *(_QWORD *)(v5 + 12) - *(_QWORD *)((char *)v28 + 12);
    if ( !v8 )
      v8 = *(unsigned int *)(v5 + 20) - (unsigned __int64)DWORD1(v28[1]);
  }
  if ( v8 )
  {
    ExFreePoolWithTag_0(P, 0x4B444342u);
    return v7;
  }
LABEL_8:
  v9 = P;
  v10 = 0;
  if ( *(_DWORD *)P )
  {
    if ( *(_DWORD *)P == 1 )
      v11 = 0;
    else
      v11 = 2;
  }
  else
  {
    v11 = 1;
  }
  if ( !v6 )
  {
    if ( v11 == 1 )
    {
LABEL_35:
      v15 = 0;
      if ( !v11 )
      {
        if ( v6 )
        {
          v15 = v6;
        }
        else if ( v26 )
        {
          v15 = v26;
        }
      }
      for ( i = 0; ; i = (unsigned int)((_DWORD)P + 1) )
      {
        LODWORD(P) = i;
        if ( (unsigned int)i >= v9[1] )
          goto LABEL_22;
        v17 = 36 * i;
        v18 = v9[36 * i + 18];
        if ( v18 )
        {
          LODWORD(ShareAccess) = v18;
          swprintf_s(Dst, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, ShareAccess);
          if ( v35 )
          {
            PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(Dst);
            v10 = (wchar_t *)PartitionVhdFilePath;
            if ( PartitionVhdFilePath )
            {
              if ( !_wcsicmp(Str1, PartitionVhdFilePath) )
                goto LABEL_21;
              ExFreePoolWithTag_0(v10, 0x4B444342u);
              v10 = 0;
            }
          }
          if ( v11 == 1 )
          {
            if ( !v26 )
              continue;
            v20 = *v26 == *(_QWORD *)&v9[v17 + 14];
          }
          else
          {
            if ( !v15 )
              continue;
            v21 = *v15 - *(_QWORD *)&v9[v17 + 24];
            if ( *v15 == *(_QWORD *)&v9[v17 + 24] )
              v21 = v15[1] - *(_QWORD *)&v9[v17 + 26];
            v20 = v21 == 0;
          }
          if ( v20 )
            goto LABEL_21;
        }
      }
    }
LABEL_34:
    if ( v11 )
      goto LABEL_22;
    goto LABEL_35;
  }
  if ( v11 != 1 )
    goto LABEL_34;
  swprintf_s(v4, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, *v6);
  RtlInitUnicodeString_0(&DestinationString, v4);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile_0(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, 0) >= 0 )
  {
    ZwClose_0(FileHandle);
LABEL_21:
    v7 = 1;
  }
LABEL_22:
  ExFreePoolWithTag_0(v9, 0x4B444342u);
  v12 = Str1;
  if ( !Str1 || v35 || !v7 )
  {
LABEL_28:
    if ( !v10 )
      goto LABEL_30;
    goto LABEL_29;
  }
  v13 = (const wchar_t *)BiGetPartitionVhdFilePath(Dst);
  v10 = (wchar_t *)v13;
  if ( !v13 || _wcsicmp(v12, v13) )
  {
    v7 = 0;
    goto LABEL_28;
  }
LABEL_29:
  ExFreePoolWithTag_0(v10, 0x4B444342u);
LABEL_30:
  if ( v7 )
    *(_BYTE *)a3 = 1;
  return v7;
}

```

## disassembly

```asm
0x14003101c  mov     [rsp-8+arg_10], r8
0x140031021  mov     [rsp-8+arg_8], edx
0x140031025  push    rbp
0x140031026  push    rbx
0x140031027  push    rsi
0x140031028  push    rdi
0x140031029  push    r13
0x14003102b  push    r14
0x14003102d  push    r15
0x14003102f  lea     rbp, [rsp-27h]
0x140031034  sub     rsp, 0D0h
0x14003103b  mov     r14, [r8+8]
0x14003103f  lea     rdx, [rbp+57h+P]
0x140031043  mov     rsi, [r8+10h]
0x140031047  xorps   xmm0, xmm0
0x14003104a  mov     rbx, [r8+18h]
0x14003104e  xor     eax, eax
0x140031050  mov     r13, [r8+28h]
0x140031054  xorps   xmm1, xmm1
0x140031057  mov     [rbp+57h+var_88], rax
0x14003105b  xor     dil, dil
0x14003105e  mov     [rbp+57h+FileHandle], rax
0x140031062  mov     [rbp+57h+P], rax
0x140031066  mov     al, [r8+1]
0x14003106a  mov     [rbp+57h+arg_18], al
0x14003106d  mov     rax, [r8+20h]
0x140031071  lea     r8, [rbp+57h+var_A8]
0x140031075  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140031079  mov     [rbp+57h+var_B8], rax
0x14003107d  movups  [rbp+57h+var_A8], xmm0
0x140031081  mov     [rbp+57h+Str1], r14
0x140031085  movups  [rbp+57h+var_98], xmm0
0x140031089  mov     [rbp+57h+Dst], rsi
0x14003108d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140031091  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140031095  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140031099  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14003109d  call    BiGetDriveLayoutBlock
0x1400310a2  test    eax, eax
0x1400310a4  js      loc_14003121C
0x1400310aa  cmp     dword ptr [rbp+57h+var_A8], 7
0x1400310ae  jnz     short loc_1400310F5
0x1400310b0  cmp     dword ptr [rbx], 7
0x1400310b3  jnz     short loc_1400310EF
0x1400310b5  mov     rcx, [rbx+4]
0x1400310b9  sub     rcx, qword ptr [rbp+57h+var_A8+4]
0x1400310bd  jnz     short loc_1400310D2
0x1400310bf  mov     rcx, [rbx+0Ch]
0x1400310c3  sub     rcx, qword ptr [rbp+57h+var_A8+0Ch]
0x1400310c7  jnz     short loc_1400310D2
0x1400310c9  mov     eax, dword ptr [rbp+57h+var_98+4]
0x1400310cc  mov     ecx, [rbx+14h]
0x1400310cf  sub     rcx, rax
0x1400310d2  test    rcx, rcx
0x1400310d5  jnz     short loc_1400310FC
0x1400310d7  mov     r15, [rbp+57h+P]
0x1400310db  xor     ebx, ebx
0x1400310dd  mov     ecx, [r15]
0x1400310e0  test    ecx, ecx
0x1400310e2  jz      short loc_140031114
0x1400310e4  cmp     ecx, 1
0x1400310e7  jz      short loc_14003110F
0x1400310e9  lea     r14d, [rbx+2]
0x1400310ed  jmp     short loc_14003111A
0x1400310ef  cmp     dword ptr [rbp+57h+var_A8], 7
0x1400310f3  jz      short loc_1400310D7
0x1400310f5  test    r14, r14
0x1400310f8  jnz     short loc_1400310D7
0x1400310fa  jmp     short loc_1400310B5
0x1400310fc  mov     rcx, [rbp+57h+P]; P
0x140031100  mov     edx, 4B444342h; Tag
0x140031105  call    ExFreePoolWithTag_0
0x14003110a  jmp     loc_14003121C
0x14003110f  xor     r14d, r14d
0x140031112  jmp     short loc_14003111A
0x140031114  mov     r14d, 1
0x14003111a  test    r13, r13
0x14003111d  jz      loc_140031232
0x140031123  cmp     r14d, 1
0x140031127  jnz     loc_140031238
0x14003112d  mov     eax, [r13+0]
0x140031131  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x140031138  mov     r9d, [rbp+57h+arg_8]
0x14003113c  lea     edx, [r14+34h]; SizeInWords
0x140031140  mov     rcx, rsi; Dst
0x140031143  mov     dword ptr [rsp+100h+ShareAccess], eax
0x140031147  call    cs:__imp_swprintf_s
0x14003114e  nop     dword ptr [rax+rax+00h]
0x140031153  mov     rdx, rsi; SourceString
0x140031156  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003115a  call    RtlInitUnicodeString_0
0x14003115f  lea     rax, [rbp+57h+DestinationString]
0x140031163  mov     [rsp+100h+OpenOptions], ebx; OpenOptions
0x140031167  xorps   xmm0, xmm0
0x14003116a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14003116e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140031172  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140031179  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003117d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140031181  mov     edx, 80000000h; DesiredAccess
0x140031186  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14003118d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140031191  mov     dword ptr [rsp+100h+ShareAccess], 3; ShareAccess
0x140031199  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003119e  call    ZwOpenFile_0
0x1400311a3  test    eax, eax
0x1400311a5  js      short loc_1400311B3
0x1400311a7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400311ab  call    ZwClose_0
0x1400311b0  mov     dil, 1
0x1400311b3  mov     edx, 4B444342h; Tag
0x1400311b8  mov     rcx, r15; P
0x1400311bb  call    ExFreePoolWithTag_0
0x1400311c0  mov     rsi, [rbp+57h+Str1]
0x1400311c4  test    rsi, rsi
0x1400311c7  jz      short loc_1400311FE
0x1400311c9  cmp     [rbp+57h+arg_18], 0
0x1400311cd  jnz     short loc_1400311FE
0x1400311cf  test    dil, dil
0x1400311d2  jz      short loc_1400311FE
0x1400311d4  mov     rcx, [rbp+57h+Dst]; SourceString
0x1400311d8  call    BiGetPartitionVhdFilePath
0x1400311dd  mov     rbx, rax
0x1400311e0  test    rax, rax
0x1400311e3  jz      short loc_1400311FB
0x1400311e5  mov     rdx, rax; Str2
0x1400311e8  mov     rcx, rsi; Str1
0x1400311eb  call    cs:__imp__wcsicmp
0x1400311f2  nop     dword ptr [rax+rax+00h]
0x1400311f7  test    eax, eax
0x1400311f9  jz      short loc_140031203
0x1400311fb  xor     dil, dil
0x1400311fe  test    rbx, rbx
0x140031201  jz      short loc_140031210
0x140031203  mov     edx, 4B444342h; Tag
0x140031208  mov     rcx, rbx; P
0x14003120b  call    ExFreePoolWithTag_0
0x140031210  test    dil, dil
0x140031213  jz      short loc_14003121C
0x140031215  mov     rax, [rbp+57h+arg_10]
0x140031219  mov     byte ptr [rax], 1
0x14003121c  mov     al, dil
0x14003121f  add     rsp, 0D0h
0x140031226  pop     r15
0x140031228  pop     r14
0x14003122a  pop     r13
0x14003122c  pop     rdi
0x14003122d  pop     rsi
0x14003122e  pop     rbx
0x14003122f  pop     rbp
0x140031230  retn
0x140031232  cmp     r14d, 1
0x140031236  jz      short loc_140031241
0x140031238  test    r14d, r14d
0x14003123b  jnz     loc_1400311B3
0x140031241  xor     esi, esi
0x140031243  test    r14d, r14d
0x140031246  jnz     short loc_14003125D
0x140031248  test    r13, r13
0x14003124b  jz      short loc_140031252
0x14003124d  mov     rsi, r13
0x140031250  jmp     short loc_14003125D
0x140031252  mov     rcx, [rbp+57h+var_B8]
0x140031256  test    rcx, rcx
0x140031259  cmovnz  rsi, rcx
0x14003125d  xor     eax, eax
0x14003125f  mov     dword ptr [rbp+57h+P], eax
0x140031262  cmp     eax, [r15+4]
0x140031266  jnb     loc_1400311B3
0x14003126c  lea     r13, [rax+rax*8]
0x140031270  shl     r13, 4
0x140031274  mov     eax, [r15+r13+48h]
0x140031279  test    eax, eax
0x14003127b  jz      loc_140031320
0x140031281  mov     r9d, [rbp+57h+arg_8]
0x140031285  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x14003128c  mov     rcx, [rbp+57h+Dst]; Dst
0x140031290  mov     edx, 35h ; '5'; SizeInWords
0x140031295  mov     dword ptr [rsp+100h+ShareAccess], eax
0x140031299  call    cs:__imp_swprintf_s
0x1400312a0  nop     dword ptr [rax+rax+00h]
0x1400312a5  cmp     [rbp+57h+arg_18], dil
0x1400312a9  jz      short loc_1400312E6
0x1400312ab  mov     rcx, [rbp+57h+Dst]; SourceString
0x1400312af  call    BiGetPartitionVhdFilePath
0x1400312b4  mov     rbx, rax
0x1400312b7  test    rax, rax
0x1400312ba  jz      short loc_1400312E6
0x1400312bc  mov     rcx, [rbp+57h+Str1]; Str1
0x1400312c0  mov     rdx, rax; Str2
0x1400312c3  call    cs:__imp__wcsicmp
0x1400312ca  nop     dword ptr [rax+rax+00h]
0x1400312cf  test    eax, eax
0x1400312d1  jz      loc_1400311B0
0x1400312d7  mov     edx, 4B444342h; Tag
0x1400312dc  mov     rcx, rbx; P
0x1400312df  call    ExFreePoolWithTag_0
0x1400312e4  xor     ebx, ebx
0x1400312e6  cmp     r14d, 1
0x1400312ea  jnz     short loc_1400312FF
0x1400312ec  mov     rcx, [rbp+57h+var_B8]
0x1400312f0  test    rcx, rcx
0x1400312f3  jz      short loc_140031320
0x1400312f5  mov     rax, [r15+r13+38h]
0x1400312fa  cmp     [rcx], rax
0x1400312fd  jmp     short loc_14003131A
0x1400312ff  test    rsi, rsi
0x140031302  jz      short loc_140031320
0x140031304  mov     rcx, [rsi]
0x140031307  sub     rcx, [r15+r13+60h]
0x14003130c  jnz     short loc_140031317
0x14003130e  mov     rcx, [rsi+8]
0x140031312  sub     rcx, [r15+r13+68h]
0x140031317  test    rcx, rcx
0x14003131a  jz      loc_1400311B0
0x140031320  mov     eax, dword ptr [rbp+57h+P]
0x140031323  inc     eax
0x140031325  jmp     loc_14003125F
```
