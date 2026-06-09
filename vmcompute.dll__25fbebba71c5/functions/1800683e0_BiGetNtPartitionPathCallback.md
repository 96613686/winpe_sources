# BiGetNtPartitionPathCallback

- ea: `0x1800683e0`
- end: `0x180068738`
- name: `BiGetNtPartitionPathCallback`
- size: `856`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003bd0`
- `0x180003de4`
- `0x180068074`
- `0x1800683e0`
- `0x1800688f4`

## import_xrefs

- `ntdll!ZwClose` at `0x180068586`
- `ntdll!ZwClose` at `0x180068586`
- `ntdll!ZwOpenFile` at `0x180068572`
- `ntdll!ZwOpenFile` at `0x180068572`
- `ntdll!RtlFreeHeap` at `0x1800684d2`
- `ntdll!RtlFreeHeap` at `0x1800685a7`
- `ntdll!RtlFreeHeap` at `0x180068601`
- `ntdll!RtlFreeHeap` at `0x1800686e1`
- `ntdll!RtlFreeHeap` at `0x1800684d2`
- `ntdll!RtlFreeHeap` at `0x1800685a7`
- `ntdll!RtlFreeHeap` at `0x180068601`
- `ntdll!RtlFreeHeap` at `0x1800686e1`
- `ntdll!RtlInitUnicodeString` at `0x180068527`
- `ntdll!RtlInitUnicodeString` at `0x180068527`

## pseudocode

```c
char __fastcall BiGetNtPartitionPathCallback(__int64 a1, unsigned int a2, __int64 a3)
{
  wchar_t *v3; // r14
  wchar_t *v4; // rsi
  _QWORD *v5; // r13
  __int64 v6; // rbx
  char v7; // di
  _DWORD *v8; // r12
  _DWORD *v9; // r15
  wchar_t *v10; // rbx
  int v11; // r14d
  wchar_t *v12; // rsi
  const wchar_t *v13; // rax
  _QWORD *v15; // rsi
  __int64 v16; // r13
  const wchar_t *PartitionVhdFilePath; // rax
  bool v18; // zf
  __int64 ShareAccess; // [rsp+28h] [rbp-89h]
  PVOID P; // [rsp+38h] [rbp-79h] BYREF
  wchar_t *Buffer; // [rsp+40h] [rbp-71h]
  void *FileHandle; // [rsp+48h] [rbp-69h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-61h]
  _OWORD v24[2]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v25; // [rsp+78h] [rbp-39h]
  _QWORD *v26; // [rsp+80h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+17h] BYREF
  char v32; // [rsp+130h] [rbp+7Fh]

  v3 = *(wchar_t **)(a3 + 8);
  v4 = *(wchar_t **)(a3 + 16);
  v5 = *(_QWORD **)(a3 + 32);
  v6 = *(_QWORD *)(a3 + 24);
  v7 = 0;
  v8 = *(_DWORD **)(a3 + 40);
  v25 = 0;
  FileHandle = 0;
  P = 0;
  v32 = *(_BYTE *)(a3 + 1);
  String1 = v3;
  memset(v24, 0, sizeof(v24));
  Buffer = v4;
  v26 = v5;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( (int)BiGetDriveLayoutBlock(a1, &P, v24) < 0 )
    return v7;
  if ( LODWORD(v24[0]) == 7 )
  {
    if ( *(_DWORD *)v6 != 7 )
      goto LABEL_6;
  }
  else if ( v3 )
  {
    goto LABEL_6;
  }
  if ( *(_OWORD *)(v6 + 4) != *(_OWORD *)((char *)v24 + 4) || *(_DWORD *)(v6 + 20) != DWORD1(v24[1]) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    return v7;
  }
LABEL_6:
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
  if ( !v8 )
  {
    if ( v11 == 1 )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( v11 != 1 )
  {
LABEL_32:
    if ( v11 )
      goto LABEL_20;
LABEL_33:
    v15 = 0;
    if ( !v11 )
    {
      if ( v8 )
      {
        v15 = v8;
      }
      else if ( v5 )
      {
        v15 = v5;
      }
    }
    v16 = 0;
    if ( !*((_DWORD *)P + 1) )
      goto LABEL_20;
    while ( 1 )
    {
      if ( v9[36 * v16 + 18] )
      {
        LODWORD(ShareAccess) = v9[36 * v16 + 18];
        swprintf_s(Buffer, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, ShareAccess);
        if ( v32 )
        {
          PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(Buffer);
          v10 = (wchar_t *)PartitionVhdFilePath;
          if ( PartitionVhdFilePath )
          {
            if ( !wcsicmp(String1, PartitionVhdFilePath) )
              goto LABEL_19;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
            v10 = 0;
          }
        }
        if ( v11 == 1 )
        {
          if ( v26 )
          {
            v18 = *v26 == *(_QWORD *)&v9[36 * v16 + 14];
            goto LABEL_50;
          }
        }
        else if ( v15 && *v15 == *(_QWORD *)&v9[36 * v16 + 24] )
        {
          v18 = v15[1] == *(_QWORD *)&v9[36 * v16 + 26];
LABEL_50:
          if ( v18 )
            goto LABEL_19;
        }
      }
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= v9[1] )
        goto LABEL_20;
    }
  }
  swprintf_s(v4, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, *v8);
  RtlInitUnicodeString(&DestinationString, v4);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, 0) >= 0 )
  {
    ZwClose(FileHandle);
LABEL_19:
    v7 = 1;
  }
LABEL_20:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  v12 = String1;
  if ( !String1 || v32 || !v7 )
  {
LABEL_26:
    if ( !v10 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v13 = (const wchar_t *)BiGetPartitionVhdFilePath(Buffer);
  v10 = (wchar_t *)v13;
  if ( !v13 || wcsicmp(v12, v13) )
  {
    v7 = 0;
    goto LABEL_26;
  }
LABEL_27:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
LABEL_28:
  if ( v7 )
    *(_BYTE *)a3 = 1;
  return v7;
}

```

## disassembly

```asm
0x1800683e0  mov     rax, rsp
0x1800683e3  mov     [rax+8], rbx
0x1800683e7  mov     [rax+18h], r8
0x1800683eb  mov     [rax+10h], edx
0x1800683ee  push    rbp
0x1800683ef  push    rsi
0x1800683f0  push    rdi
0x1800683f1  push    r12
0x1800683f3  push    r13
0x1800683f5  push    r14
0x1800683f7  push    r15
0x1800683f9  lea     rbp, [rax-5Fh]
0x1800683fd  sub     rsp, 0D0h
0x180068404  mov     r14, [r8+8]
0x180068408  xorps   xmm0, xmm0
0x18006840b  mov     rsi, [r8+10h]
0x18006840f  xor     edx, edx
0x180068411  mov     r13, [r8+20h]
0x180068415  xorps   xmm1, xmm1
0x180068418  mov     rbx, [r8+18h]
0x18006841c  xor     dil, dil
0x18006841f  mov     r12, [r8+28h]
0x180068423  mov     [rbp+57h+var_90], rdx
0x180068427  mov     [rbp+57h+FileHandle], rdx
0x18006842b  mov     [rbp+57h+P], rdx
0x18006842f  mov     dl, [r8+1]
0x180068433  lea     r8, [rbp+57h+var_B0]
0x180068437  mov     [rbp+57h+arg_18], dl
0x18006843a  lea     rdx, [rbp+57h+P]
0x18006843e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180068442  mov     [rbp+57h+String1], r14
0x180068446  movups  [rbp+57h+var_B0], xmm0
0x18006844a  mov     [rbp+57h+Buffer], rsi
0x18006844e  movups  [rbp+57h+var_A0], xmm0
0x180068452  mov     [rbp+57h+var_88], r13
0x180068456  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006845a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18006845e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180068462  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180068466  call    BiGetDriveLayoutBlock
0x18006846b  test    eax, eax
0x18006846d  js      loc_180068619
0x180068473  cmp     dword ptr [rbp+57h+var_B0], 7
0x180068477  jnz     short loc_1800684B8
0x180068479  cmp     dword ptr [rbx], 7
0x18006847c  jnz     short loc_1800684B2
0x18006847e  mov     rax, [rbx+4]
0x180068482  cmp     rax, qword ptr [rbp+57h+var_B0+4]
0x180068486  jnz     short loc_1800684BF
0x180068488  mov     rax, [rbx+0Ch]
0x18006848c  cmp     rax, qword ptr [rbp+57h+var_B0+0Ch]
0x180068490  jnz     short loc_1800684BF
0x180068492  mov     eax, [rbx+14h]
0x180068495  cmp     eax, dword ptr [rbp+57h+var_A0+4]
0x180068498  jnz     short loc_1800684BF
0x18006849a  mov     r15, [rbp+57h+P]
0x18006849e  xor     ebx, ebx
0x1800684a0  mov     ecx, [r15]
0x1800684a3  test    ecx, ecx
0x1800684a5  jz      short loc_1800684E8
0x1800684a7  cmp     ecx, 1
0x1800684aa  jz      short loc_1800684E3
0x1800684ac  lea     r14d, [rbx+2]
0x1800684b0  jmp     short loc_1800684EE
0x1800684b2  cmp     dword ptr [rbp+57h+var_B0], 7
0x1800684b6  jz      short loc_18006849A
0x1800684b8  test    r14, r14
0x1800684bb  jnz     short loc_18006849A
0x1800684bd  jmp     short loc_18006847E
0x1800684bf  mov     rcx, gs:60h
0x1800684c8  xor     edx, edx; Flags
0x1800684ca  mov     r8, [rbp+57h+P]; P
0x1800684ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800684d2  call    cs:__imp_RtlFreeHeap
0x1800684d9  nop     dword ptr [rax+rax+00h]
0x1800684de  jmp     loc_180068619
0x1800684e3  xor     r14d, r14d
0x1800684e6  jmp     short loc_1800684EE
0x1800684e8  mov     r14d, 1
0x1800684ee  test    r12, r12
0x1800684f1  jz      loc_180068638
0x1800684f7  cmp     r14d, 1
0x1800684fb  jnz     loc_18006863E
0x180068501  mov     eax, [r12]
0x180068505  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x18006850c  mov     r9d, [rbp+57h+arg_8]
0x180068510  lea     edx, [r14+34h]; BufferCount
0x180068514  mov     rcx, rsi; Buffer
0x180068517  mov     [rsp+100h+ShareAccess], eax
0x18006851b  call    swprintf_s
0x180068520  mov     rdx, rsi; SourceString
0x180068523  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180068527  call    cs:__imp_RtlInitUnicodeString
0x18006852e  nop     dword ptr [rax+rax+00h]
0x180068533  lea     rax, [rbp+57h+DestinationString]
0x180068537  mov     [rsp+28h], ebx; OpenOptions
0x18006853b  xorps   xmm0, xmm0
0x18006853e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180068542  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180068546  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006854d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180068551  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180068555  mov     edx, 80000000h; DesiredAccess
0x18006855a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180068561  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180068565  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x18006856d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180068572  call    cs:__imp_ZwOpenFile
0x180068579  nop     dword ptr [rax+rax+00h]
0x18006857e  test    eax, eax
0x180068580  js      short loc_180068595
0x180068582  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180068586  call    cs:__imp_ZwClose
0x18006858d  nop     dword ptr [rax+rax+00h]
0x180068592  mov     dil, 1
0x180068595  mov     rcx, gs:60h
0x18006859e  mov     r8, r15; P
0x1800685a1  xor     edx, edx; Flags
0x1800685a3  mov     rcx, [rcx+30h]; HeapHandle
0x1800685a7  call    cs:__imp_RtlFreeHeap
0x1800685ae  nop     dword ptr [rax+rax+00h]
0x1800685b3  mov     rsi, [rbp+57h+String1]
0x1800685b7  test    rsi, rsi
0x1800685ba  jz      short loc_1800685EA
0x1800685bc  cmp     [rbp+57h+arg_18], 0
0x1800685c0  jnz     short loc_1800685EA
0x1800685c2  test    dil, dil
0x1800685c5  jz      short loc_1800685EA
0x1800685c7  mov     rcx, [rbp+57h+Buffer]; SourceString
0x1800685cb  call    BiGetPartitionVhdFilePath
0x1800685d0  mov     rbx, rax
0x1800685d3  test    rax, rax
0x1800685d6  jz      short loc_1800685E7
0x1800685d8  mov     rdx, rax; String2
0x1800685db  mov     rcx, rsi; String1
0x1800685de  call    _wcsicmp
0x1800685e3  test    eax, eax
0x1800685e5  jz      short loc_1800685EF
0x1800685e7  xor     dil, dil
0x1800685ea  test    rbx, rbx
0x1800685ed  jz      short loc_18006860D
0x1800685ef  mov     rcx, gs:60h
0x1800685f8  mov     r8, rbx; P
0x1800685fb  xor     edx, edx; Flags
0x1800685fd  mov     rcx, [rcx+30h]; HeapHandle
0x180068601  call    cs:__imp_RtlFreeHeap
0x180068608  nop     dword ptr [rax+rax+00h]
0x18006860d  test    dil, dil
0x180068610  jz      short loc_180068619
0x180068612  mov     rax, [rbp+57h+arg_10]
0x180068616  mov     byte ptr [rax], 1
0x180068619  mov     rbx, [rsp+100h+arg_0]
0x180068621  mov     al, dil
0x180068624  add     rsp, 0D0h
0x18006862b  pop     r15
0x18006862d  pop     r14
0x18006862f  pop     r13
0x180068631  pop     r12
0x180068633  pop     rdi
0x180068634  pop     rsi
0x180068635  pop     rbp
0x180068636  retn
0x180068638  cmp     r14d, 1
0x18006863c  jz      short loc_180068647
0x18006863e  test    r14d, r14d
0x180068641  jnz     loc_180068595
0x180068647  xor     esi, esi
0x180068649  test    r14d, r14d
0x18006864c  jnz     short loc_18006865F
0x18006864e  test    r12, r12
0x180068651  jz      short loc_180068658
0x180068653  mov     rsi, r12
0x180068656  jmp     short loc_18006865F
0x180068658  test    r13, r13
0x18006865b  cmovnz  rsi, r13
0x18006865f  xor     r13d, r13d
0x180068662  cmp     [r15+4], ebx
0x180068666  jbe     loc_180068595
0x18006866c  lea     r12, ds:0[r13*8]
0x180068674  add     r12, r13
0x180068677  add     r12, r12
0x18006867a  mov     eax, [r15+r12*8+48h]
0x18006867f  test    eax, eax
0x180068681  jz      loc_180068726
0x180068687  mov     r9d, [rbp+57h+arg_8]
0x18006868b  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x180068692  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180068696  mov     edx, 35h ; '5'; BufferCount
0x18006869b  mov     [rsp+100h+ShareAccess], eax
0x18006869f  call    swprintf_s
0x1800686a4  cmp     [rbp+57h+arg_18], dil
0x1800686a8  jz      short loc_1800686EF
0x1800686aa  mov     rcx, [rbp+57h+Buffer]; SourceString
0x1800686ae  call    BiGetPartitionVhdFilePath
0x1800686b3  mov     rbx, rax
0x1800686b6  test    rax, rax
0x1800686b9  jz      short loc_1800686EF
0x1800686bb  mov     rcx, [rbp+57h+String1]; String1
0x1800686bf  mov     rdx, rax; String2
0x1800686c2  call    _wcsicmp
0x1800686c7  test    eax, eax
0x1800686c9  jz      loc_180068592
0x1800686cf  mov     rcx, gs:60h
0x1800686d8  mov     r8, rbx; P
0x1800686db  xor     edx, edx; Flags
0x1800686dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800686e1  call    cs:__imp_RtlFreeHeap
0x1800686e8  nop     dword ptr [rax+rax+00h]
0x1800686ed  xor     ebx, ebx
0x1800686ef  cmp     r14d, 1
0x1800686f3  jnz     short loc_180068708
0x1800686f5  mov     rcx, [rbp+57h+var_88]
0x1800686f9  test    rcx, rcx
0x1800686fc  jz      short loc_180068726
0x1800686fe  mov     rax, [r15+r12*8+38h]
0x180068703  cmp     [rcx], rax
0x180068706  jmp     short loc_180068720
0x180068708  test    rsi, rsi
0x18006870b  jz      short loc_180068726
0x18006870d  mov     rax, [rsi]
0x180068710  cmp     rax, [r15+r12*8+60h]
0x180068715  jnz     short loc_180068726
0x180068717  mov     rax, [rsi+8]
0x18006871b  cmp     rax, [r15+r12*8+68h]
0x180068720  jz      loc_180068592
0x180068726  inc     r13d
0x180068729  cmp     r13d, [r15+4]
0x18006872d  jb      loc_18006866C
0x180068733  jmp     loc_180068595
```
