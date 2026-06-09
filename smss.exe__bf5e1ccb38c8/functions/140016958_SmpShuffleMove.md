# SmpShuffleMove

- ea: `0x140016958`
- end: `0x140016b8c`
- name: `SmpShuffleMove`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015ae8`

## callees

- `0x140011ac4`
- `0x1400130f4`
- `0x1400158e4`
- `0x140015ef8`
- `0x140016958`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140016ac2`
- `ntdll!RtlInitUnicodeString` at `0x140016ac2`
- `ntdll!NtOpenFile` at `0x140016a93`
- `ntdll!NtOpenFile` at `0x140016a93`
- `ntdll!NtClose` at `0x140016a0c`
- `ntdll!NtClose` at `0x140016a1b`
- `ntdll!NtClose` at `0x140016aa5`
- `ntdll!NtClose` at `0x140016a0c`
- `ntdll!NtClose` at `0x140016a1b`
- `ntdll!NtClose` at `0x140016aa5`
- `ntdll!RtlFreeUnicodeString` at `0x1400169fd`
- `ntdll!RtlFreeUnicodeString` at `0x1400169fd`

## pseudocode

```c
__int64 __fastcall SmpShuffleMove(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rsi
  char v7; // al
  NTSTATUS v8; // ebx
  unsigned __int16 v9; // cx
  int v11; // r9d
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // r9
  HANDLE FileHandle; // [rsp+30h] [rbp-89h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-81h] BYREF
  __int128 v17; // [rsp+48h] [rbp-71h] BYREF
  int v18[4]; // [rsp+58h] [rbp-61h] BYREF
  __m256i v19; // [rsp+68h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+Fh] BYREF
  HANDLE Handle; // [rsp+138h] [rbp+7Fh] BYREF

  *(_QWORD *)&UnicodeString.Length = 0;
  v3 = -1;
  Handle = 0;
  UnicodeString.Buffer = 0;
  FileHandle = (HANDLE)-1LL;
  memset(&v19, 0, 28);
  DestinationString = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  if ( a3 != 1 || (v7 = SmpCheckFolderForRedirections(a1, &FileHandle), v3 = (__int64)FileHandle, v7) )
  {
    v9 = *(_WORD *)a1 >> 1;
    if ( v9 )
    {
      while ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * v9) != 92 )
      {
        if ( !--v9 )
          goto LABEL_7;
      }
      *((_QWORD *)&v17 + 1) = *(_QWORD *)(a1 + 8);
      LOWORD(v17) = 2 * v9;
      WORD1(v17) = 2 * v9;
      FileHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      IoStatusBlock = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = NtOpenFile(&FileHandle, 2u, &ObjectAttributes, &IoStatusBlock, 3u, 0);
      if ( FileHandle )
        NtClose(FileHandle);
      if ( v8 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, (PCWSTR)SmpTempFilesDir.Buffer + 4);
        v8 = SmpCreateTempFile(&DestinationString, L"SMSS-PFRO", &UnicodeString);
        if ( v8 >= 0 )
        {
          v18[0] = 48;
          LOBYTE(v11) = 1;
          *(_QWORD *)&v18[2] = 0;
          v19.m256i_i32[2] = 64;
          v19.m256i_i64[0] = a1;
          *(_OWORD *)&v19.m256i_u64[2] = 0;
          v8 = SmpOpenTargetFile((int)&Handle, 1114112, (int)v18, v11, 3u);
          if ( v8 >= 0 )
          {
            LOBYTE(v12) = a3;
            v8 = SmpRenameTargetFile(&UnicodeString, Handle, 1, v12);
            if ( v8 >= 0 )
            {
              LOBYTE(v13) = a3;
              v8 = SmpRenameTargetFile(a1, a2, 1, v13);
              if ( v8 >= 0 )
              {
                v8 = 0;
              }
              else
              {
                LOBYTE(v14) = a3;
                SmpRenameTargetFile(a1, Handle, 1, v14);
              }
            }
          }
        }
      }
    }
    else
    {
LABEL_7:
      v8 = -1073741811;
    }
  }
  else
  {
    v8 = -1073740533;
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( Handle )
    NtClose(Handle);
  if ( v3 != -1 )
    NtClose((HANDLE)v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140016958  push    rbp
0x14001695a  push    rbx
0x14001695b  push    rsi
0x14001695c  push    rdi
0x14001695d  push    r14
0x14001695f  push    r15
0x140016961  lea     rbp, [rsp-2Fh]
0x140016966  sub     rsp, 0E8h
0x14001696d  xorps   xmm0, xmm0
0x140016970  mov     qword ptr [rsp+110h+UnicodeString.Length], 0
0x140016979  xor     eax, eax
0x14001697b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001697f  mov     [rbp+57h+Handle], rax
0x140016983  xorps   xmm1, xmm1
0x140016986  mov     [rbp+57h+UnicodeString.Buffer], rax
0x14001698a  mov     r14b, r8b
0x14001698d  mov     [rsp+110h+FileHandle], rsi
0x140016992  mov     r15, rdx
0x140016995  mov     rdi, rcx
0x140016998  movups  [rbp+57h+var_A8], xmm0
0x14001699c  movups  [rbp+57h+var_A8+0Ch], xmm0
0x1400169a0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400169a4  movups  [rbp+57h+var_C8], xmm1
0x1400169a8  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x1400169ac  cmp     r8b, 1
0x1400169b0  jnz     short loc_1400169CC
0x1400169b2  lea     rdx, [rsp+110h+FileHandle]
0x1400169b7  call    SmpCheckFolderForRedirections
0x1400169bc  mov     rsi, [rsp+110h+FileHandle]
0x1400169c1  test    al, al
0x1400169c3  jnz     short loc_1400169CC
0x1400169c5  mov     ebx, 0C000050Bh
0x1400169ca  jmp     short loc_1400169F1
0x1400169cc  movzx   ecx, word ptr [rdi]
0x1400169cf  shr     cx, 1
0x1400169d2  jz      short loc_1400169EC
0x1400169d4  mov     rdx, [rdi+8]
0x1400169d8  movzx   eax, cx
0x1400169db  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x1400169e0  jz      short loc_140016A33
0x1400169e2  mov     eax, 0FFFFh
0x1400169e7  add     cx, ax
0x1400169ea  jnz     short loc_1400169D8
0x1400169ec  mov     ebx, 0C000000Dh
0x1400169f1  cmp     [rbp+57h+UnicodeString.Buffer], 0
0x1400169f6  jz      short loc_140016A03
0x1400169f8  lea     rcx, [rsp+110h+UnicodeString]; UnicodeString
0x1400169fd  call    cs:__imp_RtlFreeUnicodeString
0x140016a03  mov     rcx, [rbp+57h+Handle]; Handle
0x140016a07  test    rcx, rcx
0x140016a0a  jz      short loc_140016A12
0x140016a0c  call    cs:__imp_NtClose
0x140016a12  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140016a16  jz      short loc_140016A21
0x140016a18  mov     rcx, rsi; Handle
0x140016a1b  call    cs:__imp_NtClose
0x140016a21  mov     eax, ebx
0x140016a23  add     rsp, 0E8h
0x140016a2a  pop     r15
0x140016a2c  pop     r14
0x140016a2e  pop     rdi
0x140016a2f  pop     rsi
0x140016a30  pop     rbx
0x140016a31  pop     rbp
0x140016a32  retn
0x140016a33  add     cx, cx
0x140016a36  mov     qword ptr [rbp+57h+var_C8+8], rdx
0x140016a3a  mov     word ptr [rbp+57h+var_C8], cx
0x140016a3e  mov     word ptr [rbp+57h+var_C8+2], cx
0x140016a42  xor     eax, eax
0x140016a44  mov     [rsp+110h+OpenOptions], 0; OpenOptions
0x140016a4c  xorps   xmm0, xmm0
0x140016a4f  mov     [rsp+110h+FileHandle], rax
0x140016a54  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140016a58  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140016a5c  lea     rax, [rbp+57h+var_C8]
0x140016a60  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016a68  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016a6c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016a70  mov     edx, 2; DesiredAccess
0x140016a75  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140016a7d  lea     rcx, [rsp+110h+FileHandle]; FileHandle
0x140016a82  mov     [rsp+110h+ShareAccess], 3; ShareAccess
0x140016a8a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140016a8e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016a93  call    cs:__imp_NtOpenFile
0x140016a99  mov     rcx, [rsp+110h+FileHandle]; Handle
0x140016a9e  mov     ebx, eax
0x140016aa0  test    rcx, rcx
0x140016aa3  jz      short loc_140016AAB
0x140016aa5  call    cs:__imp_NtClose
0x140016aab  test    ebx, ebx
0x140016aad  js      loc_1400169F1
0x140016ab3  mov     rdx, cs:SmpTempFilesDir.Buffer
0x140016aba  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140016abe  add     rdx, 8; SourceString
0x140016ac2  call    cs:__imp_RtlInitUnicodeString
0x140016ac8  lea     r8, [rsp+110h+UnicodeString]
0x140016acd  lea     rdx, aSmssPfro; "SMSS-PFRO"
0x140016ad4  lea     rcx, [rbp+57h+DestinationString]
0x140016ad8  call    SmpCreateTempFile
0x140016add  mov     ebx, eax
0x140016adf  test    eax, eax
0x140016ae1  js      loc_1400169F1
0x140016ae7  xorps   xmm0, xmm0
0x140016aea  mov     [rbp+57h+var_B8], 30h ; '0'
0x140016af1  mov     r9b, 1; int
0x140016af4  mov     qword ptr [rbp+57h+var_B8+8], 0
0x140016afc  lea     r8, [rbp+57h+var_B8]; int
0x140016b00  mov     dword ptr [rbp+57h+var_A8+8], 40h ; '@'
0x140016b07  mov     edx, 110000h; int
0x140016b0c  mov     qword ptr [rbp+57h+var_A8], rdi
0x140016b10  lea     rcx, [rbp+57h+Handle]; int
0x140016b14  mov     [rsp+110h+ShareAccess], 3; ULONG
0x140016b1c  movdqu  [rbp+57h+var_98], xmm0
0x140016b21  call    SmpOpenTargetFile
0x140016b26  mov     ebx, eax
0x140016b28  test    eax, eax
0x140016b2a  js      loc_1400169F1
0x140016b30  mov     rdx, [rbp+57h+Handle]
0x140016b34  lea     rcx, [rsp+110h+UnicodeString]
0x140016b39  mov     r9b, r14b
0x140016b3c  mov     r8d, 1
0x140016b42  call    SmpRenameTargetFile
0x140016b47  mov     ebx, eax
0x140016b49  test    eax, eax
0x140016b4b  js      loc_1400169F1
0x140016b51  mov     r9b, r14b
0x140016b54  mov     r8d, 1
0x140016b5a  mov     rdx, r15
0x140016b5d  mov     rcx, rdi
0x140016b60  call    SmpRenameTargetFile
0x140016b65  mov     ebx, eax
0x140016b67  test    eax, eax
0x140016b69  jns     short loc_140016B85
0x140016b6b  mov     rdx, [rbp+57h+Handle]
0x140016b6f  mov     r9b, r14b
0x140016b72  mov     r8d, 1
0x140016b78  mov     rcx, rdi
0x140016b7b  call    SmpRenameTargetFile
0x140016b80  jmp     loc_1400169F1
0x140016b85  xor     ebx, ebx
0x140016b87  jmp     loc_1400169F1
```
