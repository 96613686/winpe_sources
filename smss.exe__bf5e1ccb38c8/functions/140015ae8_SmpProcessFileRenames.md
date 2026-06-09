# SmpProcessFileRenames

- ea: `0x140015ae8`
- end: `0x140015ebc`
- name: `SmpProcessFileRenames`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x14000c638`

## callees

- `0x1400010ec`
- `0x14000d450`
- `0x14000d494`
- `0x14000d608`
- `0x14000e2e8`
- `0x140014100`
- `0x14001426c`
- `0x1400153bc`
- `0x1400158e4`
- `0x14001598c`
- `0x140015ae8`
- `0x140015ef8`
- `0x140016958`
- `0x140016b94`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140015c96`
- `ntdll!RtlInitUnicodeString` at `0x140015c96`
- `ntdll!NtClose` at `0x140015d7b`
- `ntdll!NtClose` at `0x140015d7b`
- `ntdll!RtlAdjustPrivilege` at `0x140015b41`
- `ntdll!RtlAdjustPrivilege` at `0x140015dff`
- `ntdll!RtlAdjustPrivilege` at `0x140015b41`
- `ntdll!RtlAdjustPrivilege` at `0x140015dff`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e1f`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e32`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e4d`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e63`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e1f`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e32`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e4d`
- `ntdll!RtlDeleteRegistryValue` at `0x140015e63`
- `ntdll!RtlWriteRegistryValue` at `0x140015e8c`
- `ntdll!RtlWriteRegistryValue` at `0x140015e8c`

## string_xrefs

- `0x140015e7f`: `ClearTempFiles`
- `0x140015e15`: `PendingFileRenameOperations`
- `0x140015e3d`: `PendingFileRenameOperations`
- `0x140015e25`: `PendingFileRenameOperations2`
- `0x140015e53`: `PendingFileRenameOperations2`
- `0x140015e46`: `\REGISTRY\MACHINE\OSDATA\Session Manager`
- `0x140015e5c`: `\REGISTRY\MACHINE\OSDATA\Session Manager`
- `0x140015d90`: `SmpProcessFileRenames`

## pseudocode

```c
__int64 __fastcall SmpProcessFileRenames(int a1)
{
  char v1; // bl
  __int64 *v2; // rax
  unsigned int v3; // r13d
  __int64 v4; // rsi
  _WORD *v5; // r14
  unsigned __int16 *v6; // r15
  bool v7; // r12
  unsigned __int16 v8; // cx
  _QWORD *v9; // rdi
  _WORD *v10; // rax
  bool v11; // zf
  __int64 v12; // rdx
  int v13; // ebx
  __int64 v14; // r9
  USHORT Length; // cx
  PWSTR Buffer; // rax
  unsigned int v17; // r14d
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  char v21; // al
  __int64 v22; // rdx
  int ValueData; // [rsp+30h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-41h] BYREF
  __int64 v26; // [rsp+40h] [rbp-39h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  int v28[4]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v29[96]; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int8 OldValue; // [rsp+E8h] [rbp+6Fh] BYREF
  char v32; // [rsp+F0h] [rbp+77h]
  char v33; // [rsp+F8h] [rbp+7Fh]

  OldValue = 1;
  Handle = 0;
  ValueData = 0;
  v1 = 0;
  memset(v29, 0, 28);
  v32 = 0;
  DestinationString = 0;
  *(_OWORD *)v28 = 0;
  if ( SmpAllowProtectedRenames && RtlAdjustPrivilege(0x12u, 1u, 0, &OldValue) < 0 )
    OldValue = 1;
  if ( SmpClearTempFiles )
    SmpClearTemporaryFiles();
  SmpEventWrite(&SmssEvt_ProcessFileRenames_Start);
  v2 = (__int64 *)SmpFileRenameList;
  v3 = 0;
  v4 = SmpFileRenameList;
  ValueData = 0;
  while ( v2 != &SmpFileRenameList )
  {
    v5 = (_WORD *)(v4 + 32);
    v26 = v4;
    v6 = (unsigned __int16 *)(v4 + 16);
    Handle = 0;
    v33 = 0;
    v7 = 1;
    SmpEventWriteString2(&SmpFileRenameList, v4 + 16, v4 + 32);
    v8 = *(_WORD *)(v4 + 16);
    v9 = (_QWORD *)(v4 + 24);
    if ( v8 >= 4u )
    {
      v10 = (_WORD *)*v9;
      if ( *(_WORD *)*v9 == 42 )
      {
        v11 = v10[1] == 48;
        v33 = 1;
        v7 = !v11;
        v8 -= 4;
        *v6 = v8;
        *(_WORD *)(v4 + 18) -= 4;
        *v9 = v10 + 2;
      }
    }
    if ( *v5 )
    {
      v28[0] = 48;
      *(_QWORD *)&v28[2] = 0;
      *(_DWORD *)&v29[8] = 64;
      *(_QWORD *)v29 = v4 + 16;
      *(_OWORD *)&v29[16] = 0;
      v13 = SmpOpenTargetFile((int)&Handle, 1114112, (int)v28, 0, 3u);
      if ( v13 >= 0 )
      {
        if ( !v7 || (unsigned __int8)SmpPathCanBeTrustedIsNotARedirection(Handle) )
        {
          RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v4 + 40));
          Length = DestinationString.Length;
          Buffer = DestinationString.Buffer;
          if ( DestinationString.Length >= 4u && *DestinationString.Buffer == 42 )
          {
            DestinationString.MaximumLength -= 4;
            Length = DestinationString.Length - 4;
            Buffer = DestinationString.Buffer + 2;
            DestinationString.Length -= 4;
            DestinationString.Buffer += 2;
          }
          if ( *Buffer == 33 || *Buffer == 64 )
          {
            v17 = 1;
            DestinationString.Buffer = Buffer + 1;
            DestinationString.MaximumLength -= 2;
            DestinationString.Length = Length - 2;
          }
          else
          {
            v17 = 0;
          }
          LOBYTE(v14) = v7;
          v18 = SmpRenameTargetFile(&DestinationString, Handle, v17, v14);
          v13 = v18;
          if ( v18 < 0
            && v17
            && v18 == -1073741790
            && (LOBYTE(v19) = v7,
                v13 = SmpTryOverwriteReadonlyFile(&DestinationString, Handle, v19),
                (int)(v13 + 0x80000000) >= 0)
            && v13 != -1073741638 )
          {
            LOBYTE(v20) = v7;
            v5 = (_WORD *)(v4 + 32);
            v13 = SmpShuffleMove(&DestinationString, Handle, v20);
            if ( v13 >= 0 )
              ValueData = 1;
          }
          else
          {
            v5 = (_WORD *)(v4 + 32);
          }
        }
        else
        {
          v13 = -1073740533;
        }
      }
    }
    else
    {
      v12 = 64;
      if ( *(_WORD *)*v9 == 64 )
      {
        *v9 += 2LL;
        *v6 = v8 - 2;
      }
      LOBYTE(v12) = v7;
      v13 = SmpForceDeleteTargetFile(v4 + 16, v12, 48);
    }
    if ( Handle )
      NtClose(Handle);
    if ( v13 < 0 )
    {
      SmpLogFailureString("SmpProcessFileRenames", 7205, *v9, (unsigned int)v13);
      v21 = SmpLogPFROError(v4 + 16, v5, (unsigned int)v13);
      v1 = v21 | v32;
      v32 |= v21;
    }
    else
    {
      v1 = v32;
      ++v3;
    }
    if ( v33 == 1 )
    {
      *v6 += 4;
      *(_WORD *)(v4 + 18) += 4;
      *v9 -= 4LL;
    }
    v4 = *(_QWORD *)v4;
    SmpFreeSavedRegistryEntry(v26);
    v2 = (__int64 *)SmpFileRenameList;
  }
  if ( !OldValue )
    RtlAdjustPrivilege(0x12u, 0, 0, &OldValue);
  RtlDeleteRegistryValue(2u, L"Session Manager", L"PendingFileRenameOperations");
  RtlDeleteRegistryValue(2u, L"Session Manager", L"PendingFileRenameOperations2");
  if ( a1 )
  {
    RtlDeleteRegistryValue(0, L"\\REGISTRY\\MACHINE\\OSDATA\\Session Manager", L"PendingFileRenameOperations");
    RtlDeleteRegistryValue(0, L"\\REGISTRY\\MACHINE\\OSDATA\\Session Manager", L"PendingFileRenameOperations2");
  }
  if ( ValueData )
    RtlWriteRegistryValue(2u, L"Session Manager", L"ClearTempFiles", 4u, &ValueData, 4u);
  LOBYTE(v22) = v1;
  SmpFinishPFROLogging(v3, v22);
  return SmpEventWrite(&SmssEvt_ProcessFileRenames_Stop);
}

```

## disassembly

```asm
0x140015ae8  mov     [rsp-8+arg_0], ecx
0x140015aec  push    rbp
0x140015aed  push    rbx
0x140015aee  push    rsi
0x140015aef  push    rdi
0x140015af0  push    r12
0x140015af2  push    r13
0x140015af4  push    r14
0x140015af6  push    r15
0x140015af8  lea     rbp, [rsp-1Fh]
0x140015afd  sub     rsp, 98h
0x140015b04  xor     edi, edi
0x140015b06  mov     [rbp+57h+OldValue], 1
0x140015b0a  xorps   xmm0, xmm0
0x140015b0d  mov     [rbp+57h+Handle], rdi
0x140015b11  xor     eax, eax
0x140015b13  mov     [rbp+57h+var_A0], edi
0x140015b16  cmp     cs:SmpAllowProtectedRenames, dil
0x140015b1d  mov     bl, dil
0x140015b20  movups  [rbp+57h+var_68], xmm0
0x140015b24  mov     [rbp+57h+arg_10], bl
0x140015b27  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140015b2b  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140015b2f  movups  [rbp+57h+var_68+0Ch], xmm0
0x140015b33  jz      short loc_140015B4F
0x140015b35  lea     r9, [rbp+57h+OldValue]; OldValue
0x140015b39  xor     r8d, r8d; ForThread
0x140015b3c  mov     dl, 1; NewValue
0x140015b3e  lea     ecx, [rdi+12h]; Privilege
0x140015b41  call    cs:__imp_RtlAdjustPrivilege
0x140015b47  test    eax, eax
0x140015b49  jns     short loc_140015B4F
0x140015b4b  mov     [rbp+57h+OldValue], 1
0x140015b4f  cmp     cs:SmpClearTempFiles, edi
0x140015b55  jz      short loc_140015B5C
0x140015b57  call    SmpClearTemporaryFiles
0x140015b5c  lea     rcx, SmssEvt_ProcessFileRenames_Start; EventDescriptor
0x140015b63  call    SmpEventWrite
0x140015b68  mov     rax, cs:SmpFileRenameList
0x140015b6f  mov     r13d, edi
0x140015b72  mov     rsi, rax
0x140015b75  mov     [rbp+57h+var_A0], edi
0x140015b78  mov     r14d, 4
0x140015b7e  lea     rcx, SmpFileRenameList
0x140015b85  cmp     rax, rcx
0x140015b88  jz      loc_140015DED
0x140015b8e  lea     r14, [rsi+20h]
0x140015b92  mov     [rbp+57h+var_90], rsi
0x140015b96  lea     r15, [rsi+10h]
0x140015b9a  mov     [rbp+57h+Handle], rdi
0x140015b9e  mov     r8, r14
0x140015ba1  mov     [rbp+57h+arg_18], dil
0x140015ba5  mov     rdx, r15
0x140015ba8  mov     r12b, 1
0x140015bab  call    SmpEventWriteString2
0x140015bb0  movzx   ecx, word ptr [r15]
0x140015bb4  lea     rdi, [rsi+18h]
0x140015bb8  mov     edx, 4
0x140015bbd  lea     r8d, [rdx+2Ch]
0x140015bc1  cmp     cx, dx
0x140015bc4  jb      short loc_140015BF3
0x140015bc6  mov     rax, [rdi]
0x140015bc9  cmp     word ptr [rax], 2Ah ; '*'
0x140015bcd  jnz     short loc_140015BF3
0x140015bcf  cmp     [rax+2], r8w
0x140015bd4  mov     [rbp+57h+arg_18], 1
0x140015bd8  setnz   r12b
0x140015bdc  sub     cx, dx
0x140015bdf  mov     edx, 0FFFCh
0x140015be4  mov     [r15], cx
0x140015be8  add     [rsi+12h], dx
0x140015bec  add     rax, 4
0x140015bf0  mov     [rdi], rax
0x140015bf3  xor     eax, eax
0x140015bf5  cmp     [r14], ax
0x140015bf9  jnz     short loc_140015C29
0x140015bfb  mov     rax, [rdi]
0x140015bfe  mov     edx, 40h ; '@'
0x140015c03  cmp     [rax], dx
0x140015c06  jnz     short loc_140015C17
0x140015c08  add     rax, 2
0x140015c0c  sub     cx, 2
0x140015c10  mov     [rdi], rax
0x140015c13  mov     [r15], cx
0x140015c17  mov     dl, r12b
0x140015c1a  mov     rcx, r15
0x140015c1d  call    SmpForceDeleteTargetFile
0x140015c22  mov     ebx, eax
0x140015c24  jmp     loc_140015D72
0x140015c29  mov     [rbp+57h+var_78], r8d
0x140015c2d  lea     rcx, [rbp+57h+Handle]; int
0x140015c31  xorps   xmm0, xmm0
0x140015c34  mov     qword ptr [rbp+57h+var_78+8], rax
0x140015c38  lea     r8, [rbp+57h+var_78]; int
0x140015c3c  mov     dword ptr [rbp+57h+var_68+8], 40h ; '@'
0x140015c43  xor     r9d, r9d; int
0x140015c46  mov     qword ptr [rbp+57h+var_68], r15
0x140015c4a  mov     edx, 110000h; int
0x140015c4f  mov     dword ptr [rsp+0D0h+ValueData], 3; ULONG
0x140015c57  movdqu  [rbp+57h+var_58], xmm0
0x140015c5c  call    SmpOpenTargetFile
0x140015c61  mov     ebx, eax
0x140015c63  test    eax, eax
0x140015c65  js      loc_140015D72
0x140015c6b  cmp     r12b, 1
0x140015c6f  jnz     short loc_140015C8E
0x140015c71  mov     rcx, [rbp+57h+Handle]
0x140015c75  xor     r8d, r8d
0x140015c78  mov     rdx, r15
0x140015c7b  call    SmpPathCanBeTrustedIsNotARedirection
0x140015c80  test    al, al
0x140015c82  jnz     short loc_140015C8E
0x140015c84  mov     ebx, 0C000050Bh
0x140015c89  jmp     loc_140015D72
0x140015c8e  mov     rdx, [rsi+28h]; SourceString
0x140015c92  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140015c96  call    cs:__imp_RtlInitUnicodeString
0x140015c9c  movzx   ecx, [rbp+57h+DestinationString.Length]
0x140015ca0  mov     edx, 4
0x140015ca5  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140015ca9  cmp     cx, dx
0x140015cac  jb      short loc_140015CCE
0x140015cae  cmp     word ptr [rax], 2Ah ; '*'
0x140015cb2  jnz     short loc_140015CCE
0x140015cb4  mov     r8d, 0FFFCh
0x140015cba  add     [rbp+57h+DestinationString.MaximumLength], r8w
0x140015cbf  add     cx, r8w
0x140015cc3  add     rax, rdx
0x140015cc6  mov     [rbp+57h+DestinationString.Length], cx
0x140015cca  mov     [rbp+57h+DestinationString.Buffer], rax
0x140015cce  cmp     word ptr [rax], 21h ; '!'
0x140015cd2  jz      short loc_140015CE3
0x140015cd4  mov     edx, 40h ; '@'
0x140015cd9  cmp     [rax], dx
0x140015cdc  jz      short loc_140015CE3
0x140015cde  xor     r14d, r14d
0x140015ce1  jmp     short loc_140015D01
0x140015ce3  add     rax, 2
0x140015ce7  mov     r14d, 1
0x140015ced  mov     [rbp+57h+DestinationString.Buffer], rax
0x140015cf1  mov     eax, 0FFFEh
0x140015cf6  add     cx, ax
0x140015cf9  add     [rbp+57h+DestinationString.MaximumLength], ax
0x140015cfd  mov     [rbp+57h+DestinationString.Length], cx
0x140015d01  mov     rdx, [rbp+57h+Handle]
0x140015d05  lea     rcx, [rbp+57h+DestinationString]
0x140015d09  mov     r9b, r12b
0x140015d0c  mov     r8d, r14d
0x140015d0f  call    SmpRenameTargetFile
0x140015d14  mov     ebx, eax
0x140015d16  test    eax, eax
0x140015d18  jns     short loc_140015D6E
0x140015d1a  test    r14d, r14d
0x140015d1d  jz      short loc_140015D6E
0x140015d1f  cmp     eax, 0C0000022h
0x140015d24  jnz     short loc_140015D6E
0x140015d26  mov     rdx, [rbp+57h+Handle]
0x140015d2a  lea     rcx, [rbp+57h+DestinationString]
0x140015d2e  mov     r8b, r12b
0x140015d31  call    SmpTryOverwriteReadonlyFile
0x140015d36  mov     ecx, 80000000h
0x140015d3b  mov     ebx, eax
0x140015d3d  add     eax, ecx
0x140015d3f  test    ecx, eax
0x140015d41  jnz     short loc_140015D6E
0x140015d43  cmp     ebx, 0C00000BAh
0x140015d49  jz      short loc_140015D6E
0x140015d4b  mov     rdx, [rbp+57h+Handle]
0x140015d4f  lea     rcx, [rbp+57h+DestinationString]
0x140015d53  mov     r8b, r12b
0x140015d56  call    SmpShuffleMove
0x140015d5b  lea     r14, [rsi+20h]
0x140015d5f  mov     ebx, eax
0x140015d61  test    eax, eax
0x140015d63  js      short loc_140015D72
0x140015d65  mov     [rbp+57h+var_A0], 1
0x140015d6c  jmp     short loc_140015D72
0x140015d6e  lea     r14, [rsi+20h]
0x140015d72  mov     rcx, [rbp+57h+Handle]; Handle
0x140015d76  test    rcx, rcx
0x140015d79  jz      short loc_140015D81
0x140015d7b  call    cs:__imp_NtClose
0x140015d81  test    ebx, ebx
0x140015d83  js      short loc_140015D8D
0x140015d85  mov     bl, [rbp+57h+arg_10]
0x140015d88  inc     r13d
0x140015d8b  jmp     short loc_140015DBA
0x140015d8d  mov     r8, [rdi]
0x140015d90  lea     rcx, aSmpprocessfile; "SmpProcessFileRenames"
0x140015d97  mov     r9d, ebx
0x140015d9a  mov     edx, 1C25h
0x140015d9f  call    SmpLogFailureString
0x140015da4  mov     r8d, ebx
0x140015da7  mov     rdx, r14
0x140015daa  mov     rcx, r15
0x140015dad  call    SmpLogPFROError
0x140015db2  mov     bl, [rbp+57h+arg_10]
0x140015db5  or      bl, al
0x140015db7  mov     [rbp+57h+arg_10], bl
0x140015dba  cmp     [rbp+57h+arg_18], 1
0x140015dbe  mov     r14d, 4
0x140015dc4  jnz     short loc_140015DD3
0x140015dc6  add     [r15], r14w
0x140015dca  add     [rsi+12h], r14w
0x140015dcf  add     qword ptr [rdi], 0FFFFFFFFFFFFFFFCh
0x140015dd3  mov     rcx, [rbp+57h+var_90]
0x140015dd7  mov     rsi, [rsi]
0x140015dda  call    SmpFreeSavedRegistryEntry
0x140015ddf  mov     rax, cs:SmpFileRenameList
0x140015de6  xor     edi, edi
0x140015de8  jmp     loc_140015B7E
0x140015ded  cmp     [rbp+57h+OldValue], dil
0x140015df1  jnz     short loc_140015E05
0x140015df3  xor     edx, edx; NewValue
0x140015df5  lea     r9, [rbp+57h+OldValue]; OldValue
0x140015df9  xor     r8d, r8d; ForThread
0x140015dfc  lea     ecx, [rdx+12h]; Privilege
0x140015dff  call    cs:__imp_RtlAdjustPrivilege
0x140015e05  lea     rsi, Path; "Session Manager"
0x140015e0c  mov     r15d, 2
0x140015e12  mov     rdx, rsi; Path
0x140015e15  lea     r8, aPendingfileren_0; "PendingFileRenameOperations"
0x140015e1c  mov     ecx, r15d; RelativeTo
0x140015e1f  call    cs:__imp_RtlDeleteRegistryValue
0x140015e25  lea     r8, aPendingfileren; "PendingFileRenameOperations2"
0x140015e2c  mov     rdx, rsi; Path
0x140015e2f  mov     ecx, r15d; RelativeTo
0x140015e32  call    cs:__imp_RtlDeleteRegistryValue
0x140015e38  cmp     [rbp+57h+arg_0], edi
0x140015e3b  jz      short loc_140015E69
0x140015e3d  lea     r8, aPendingfileren_0; "PendingFileRenameOperations"
0x140015e44  xor     ecx, ecx; RelativeTo
0x140015e46  lea     rdx, aRegistryMachin_23; "\\REGISTRY\\MACHINE\\OSDATA\\Session Ma"...
0x140015e4d  call    cs:__imp_RtlDeleteRegistryValue
0x140015e53  lea     r8, aPendingfileren; "PendingFileRenameOperations2"
0x140015e5a  xor     ecx, ecx; RelativeTo
0x140015e5c  lea     rdx, aRegistryMachin_23; "\\REGISTRY\\MACHINE\\OSDATA\\Session Ma"...
0x140015e63  call    cs:__imp_RtlDeleteRegistryValue
0x140015e69  cmp     [rbp+57h+var_A0], edi
0x140015e6c  jz      short loc_140015E92
0x140015e6e  lea     rax, [rbp+57h+var_A0]
0x140015e72  mov     [rsp+0D0h+ValueLength], r14d; ValueLength
0x140015e77  mov     r9d, r14d; ValueType
0x140015e7a  mov     [rsp+0D0h+ValueData], rax; ValueData
0x140015e7f  lea     r8, aCleartempfiles; "ClearTempFiles"
0x140015e86  mov     rdx, rsi; Path
0x140015e89  mov     ecx, r15d; RelativeTo
0x140015e8c  call    cs:__imp_RtlWriteRegistryValue
0x140015e92  mov     dl, bl
0x140015e94  mov     ecx, r13d
0x140015e97  call    SmpFinishPFROLogging
0x140015e9c  lea     rcx, SmssEvt_ProcessFileRenames_Stop; EventDescriptor
0x140015ea3  call    SmpEventWrite
0x140015ea8  add     rsp, 98h
0x140015eaf  pop     r15
0x140015eb1  pop     r14
0x140015eb3  pop     r13
0x140015eb5  pop     r12
0x140015eb7  pop     rdi
0x140015eb8  pop     rsi
0x140015eb9  pop     rbx
0x140015eba  pop     rbp
0x140015ebb  retn
```
