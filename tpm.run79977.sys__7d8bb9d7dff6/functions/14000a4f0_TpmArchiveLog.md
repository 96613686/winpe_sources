# TpmArchiveLog

- ea: `0x14000a4f0`
- end: `0x14000aa90`
- name: `TpmArchiveLog`
- size: `1440`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400110f0`
- `0x1400179c4`
- `0x1400211dc`

## callees

- `0x140009f70`
- `0x140009fc8`
- `0x14000a0a4`
- `0x14000a3d0`
- `0x14000a4f0`
- `0x14000bf68`
- `0x140039740`
- `0x140039780`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x14000a7ac`
- `ntoskrnl!ZwCreateFile` at `0x14000a9ea`
- `ntoskrnl!ZwCreateFile` at `0x14000a7ac`
- `ntoskrnl!ZwCreateFile` at `0x14000a9ea`
- `ntoskrnl!ZwWriteFile` at `0x14000a7ef`
- `ntoskrnl!ZwWriteFile` at `0x14000a8a6`
- `ntoskrnl!ZwWriteFile` at `0x14000aa29`
- `ntoskrnl!ZwWriteFile` at `0x14000a7ef`
- `ntoskrnl!ZwWriteFile` at `0x14000a8a6`
- `ntoskrnl!ZwWriteFile` at `0x14000aa29`
- `ntoskrnl!ZwClose` at `0x14000a8c1`
- `ntoskrnl!ZwClose` at `0x14000aa5e`
- `ntoskrnl!ZwClose` at `0x14000a8c1`
- `ntoskrnl!ZwClose` at `0x14000aa5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a5ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a653`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a743`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a981`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a5ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a653`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a743`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a981`

## pseudocode

```c
__int64 TpmArchiveLog()
{
  unsigned __int8 *v0; // r15
  unsigned __int8 *v1; // rsi
  unsigned __int8 *v2; // r14
  NTSTATUS Value; // ebx
  int v4; // edi
  ULONG v5; // ebx
  unsigned __int8 *v6; // rax
  __int64 v7; // rcx
  unsigned __int8 *v8; // rax
  __int64 v9; // rcx
  ULONG Length[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v12; // [rsp+68h] [rbp-98h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v16; // [rsp+98h] [rbp-68h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v18; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR SourceString[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR v20[264]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int64 retaddr; // [rsp+568h] [rbp+468h]

  v16 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(SourceString, 0, 0x208u);
  memset(v20, 0, 0x208u);
  FileHandle = 0;
  *(_QWORD *)Length = 0;
  IoStatusBlock = 0;
  v12 = 0;
  v0 = 0;
  v1 = 0;
  v2 = 0;
  DestinationString = 0;
  Value = TpmRegistry::OpenKey(1, 131097, Length);
  if ( Value >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"PlatformLogFile");
    Value = (*((__int64 (__fastcall **)(PKDPC, _QWORD, struct _UNICODE_STRING *, __int64, WCHAR *, _QWORD, int *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
             + 235))(
              WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
              *(_QWORD *)Length,
              &DestinationString,
              520,
              SourceString,
              0,
              &v12);
    if ( Value >= 0 && v12 != 1 )
      Value = -1073741823;
  }
  TpmRegistry::CloseKey(*(struct WDFKEY__ **)Length);
  if ( Value >= 0 )
  {
    Length[0] = 0;
    *(_QWORD *)&DestinationString.Length = 0;
    v12 = 0;
    v18 = 0;
    v4 = TpmRegistry::OpenKey(1, 131097, &DestinationString);
    if ( v4 >= 0 )
    {
      RtlInitUnicodeString(&v18, L"WBCL");
      v4 = (*((__int64 (__fastcall **)(PKDPC, _QWORD, struct _UNICODE_STRING *, _QWORD, _QWORD, ULONG *, int *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
            + 235))(
             WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
             *(_QWORD *)&DestinationString.Length,
             &v18,
             0,
             0,
             Length,
             &v12);
      if ( v4 >= 0 && v12 != 3 )
        v4 = -1073741823;
    }
    TpmRegistry::CloseKey(*(struct WDFKEY__ **)&DestinationString.Length);
    Value = 0;
    if ( v4 != -2147483643 )
      Value = v4;
    if ( Value >= 0 )
    {
      v5 = Length[0];
      v1 = TpmAlloc(1, Length[0], retaddr);
      if ( !v1 )
      {
LABEL_14:
        Value = -1073741670;
        goto LABEL_30;
      }
      Length[0] = v5;
      Value = TpmRegistry::QueryValue(1, L"WBCL", 3, v1, v5, Length);
      if ( Value >= 0 )
      {
        Value = TpmEnsureDirExists();
        if ( Value >= 0 )
        {
          RtlInitUnicodeString(&v16, SourceString);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          ObjectAttributes.ObjectName = &v16;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Value = ZwCreateFile(&FileHandle, 0x40100000u, &ObjectAttributes, &IoStatusBlock, 0, 4u, 0, 0, 0x60u, 0, 0);
          if ( Value >= 0 )
          {
            Value = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, v1, Length[0], 0, 0);
            if ( Value >= 0 )
            {
              Length[0] = 0;
              if ( (int)TpmRegistry::QueryValue(1, L"WBCLTrustpoint", 3, 0, 0, Length) < 0 )
                goto LABEL_23;
              v6 = TpmAlloc(1, Length[0], retaddr);
              v0 = v6;
              if ( !v6 )
                goto LABEL_14;
              Value = TpmRegistry::QueryValue(v7, L"WBCLTrustpoint", v6, Length);
              if ( Value >= 0 )
              {
                Value = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, v0, Length[0], 0, 0);
                if ( Value >= 0 )
                {
LABEL_23:
                  ZwClose(FileHandle);
                  FileHandle = 0;
                  Length[0] = 0;
                  if ( (int)TpmRegistry::QueryValue(1, L"WBCLDrtm", 3, 0, 0, Length) < 0 )
                  {
                    Value = 0;
                  }
                  else
                  {
                    v8 = TpmAlloc(1, Length[0], retaddr);
                    v2 = v8;
                    if ( !v8 )
                      goto LABEL_14;
                    Value = TpmRegistry::QueryValue(v9, L"WBCLDrtm", v8, Length);
                    if ( Value >= 0 )
                    {
                      Value = TpmRegistry::QueryValue(1, L"PlatformLogFileDrtm", 1, v20, 520, 0);
                      if ( Value >= 0 )
                      {
                        RtlInitUnicodeString(&v16, v20);
                        ObjectAttributes.Length = 48;
                        ObjectAttributes.RootDirectory = 0;
                        ObjectAttributes.Attributes = 576;
                        ObjectAttributes.ObjectName = &v16;
                        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                        Value = ZwCreateFile(
                                  &FileHandle,
                                  0x40100000u,
                                  &ObjectAttributes,
                                  &IoStatusBlock,
                                  0,
                                  4u,
                                  0,
                                  0,
                                  0x60u,
                                  0,
                                  0);
                        if ( Value >= 0 )
                          Value = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, v2, Length[0], 0, 0);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_30:
  TpmFree(v2);
  TpmFree(v0);
  TpmFree(v1);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x14000a4f0  push    rbp
0x14000a4f2  push    rbx
0x14000a4f3  push    rsi
0x14000a4f4  push    rdi
0x14000a4f5  push    r12
0x14000a4f7  push    r13
0x14000a4f9  push    r14
0x14000a4fb  push    r15
0x14000a4fd  lea     rbp, [rsp-428h]
0x14000a505  sub     rsp, 528h
0x14000a50c  mov     rax, cs:__security_cookie
0x14000a513  xor     rax, rsp
0x14000a516  mov     [rbp+460h+var_50], rax
0x14000a51d  xorps   xmm1, xmm1
0x14000a520  lea     rcx, [rbp+460h+SourceString]; void *
0x14000a524  xorps   xmm0, xmm0
0x14000a527  mov     ebx, 208h
0x14000a52c  mov     r8d, ebx; Size
0x14000a52f  xor     edx, edx; Val
0x14000a531  movups  xmmword ptr [rbp+460h+var_4C8.Length], xmm0
0x14000a535  movups  xmmword ptr [rbp+460h+ObjectAttributes.Length], xmm1
0x14000a539  movups  xmmword ptr [rbp+460h+ObjectAttributes.ObjectName], xmm1
0x14000a53d  movups  xmmword ptr [rbp+460h+ObjectAttributes.SecurityDescriptor], xmm1
0x14000a541  call    memset
0x14000a546  mov     r8d, ebx; Size
0x14000a549  lea     rcx, [rbp+460h+var_260]; void *
0x14000a550  xor     edx, edx; Val
0x14000a552  call    memset
0x14000a557  xor     r12d, r12d
0x14000a55a  lea     r8, [rsp+560h+Length]
0x14000a55f  xorps   xmm0, xmm0
0x14000a562  mov     [rsp+560h+FileHandle], r12
0x14000a567  mov     edx, 20019h
0x14000a56c  mov     qword ptr [rsp+560h+Length], r12
0x14000a571  movups  xmmword ptr [rbp+460h+IoStatusBlock], xmm0
0x14000a575  lea     r13d, [r12+1]
0x14000a57a  mov     [rsp+560h+var_4F8], r12d
0x14000a57f  mov     ecx, r13d
0x14000a582  mov     r15d, r12d
0x14000a585  mov     esi, r12d
0x14000a588  mov     r14d, r12d
0x14000a58b  movups  xmmword ptr [rsp+560h+DestinationString.Length], xmm0
0x14000a590  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)
0x14000a595  mov     ebx, eax
0x14000a597  mov     edi, 0C0000001h
0x14000a59c  test    eax, eax
0x14000a59e  js      short loc_14000A608
0x14000a5a0  lea     rdx, aPlatformlogfil; "PlatformLogFile"
0x14000a5a7  lea     rcx, [rsp+560h+DestinationString]; DestinationString
0x14000a5ac  call    cs:__imp_RtlInitUnicodeString
0x14000a5b3  nop     dword ptr [rax+rax+00h]
0x14000a5b8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000a5bf  lea     rcx, [rsp+560h+var_4F8]
0x14000a5c4  mov     rdx, qword ptr [rsp+560h+Length]
0x14000a5c9  lea     r8, [rsp+560h+DestinationString]
0x14000a5ce  mov     qword ptr [rsp+560h+ShareAccess], rcx
0x14000a5d3  mov     r9d, 208h
0x14000a5d9  lea     rcx, [rbp+460h+SourceString]
0x14000a5dd  mov     qword ptr [rsp+560h+FileAttributes], r12
0x14000a5e2  mov     rax, [rax+758h]
0x14000a5e9  mov     [rsp+560h+AllocationSize], rcx
0x14000a5ee  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000a5f5  call    _guard_dispatch_icall
0x14000a5fa  mov     ebx, eax
0x14000a5fc  test    eax, eax
0x14000a5fe  js      short loc_14000A608
0x14000a600  cmp     [rsp+560h+var_4F8], r13d
0x14000a605  cmovnz  ebx, edi
0x14000a608  mov     rcx, qword ptr [rsp+560h+Length]; struct WDFKEY__ *
0x14000a60d  call    ?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z; TpmRegistry::CloseKey(WDFKEY__ *)
0x14000a612  test    ebx, ebx
0x14000a614  js      loc_14000AA3C
0x14000a61a  xorps   xmm0, xmm0
0x14000a61d  mov     [rsp+560h+Length], r12d
0x14000a622  lea     r8, [rsp+560h+DestinationString]
0x14000a627  mov     qword ptr [rsp+560h+DestinationString.Length], r12
0x14000a62c  mov     edx, 20019h
0x14000a631  mov     [rsp+560h+var_4F8], r12d
0x14000a636  mov     ecx, r13d
0x14000a639  movups  xmmword ptr [rbp+460h+var_488.Length], xmm0
0x14000a63d  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)
0x14000a642  mov     edi, eax
0x14000a644  test    eax, eax
0x14000a646  js      short loc_14000A6B1
0x14000a648  lea     rdx, aWbcl; "WBCL"
0x14000a64f  lea     rcx, [rbp+460h+var_488]; DestinationString
0x14000a653  call    cs:__imp_RtlInitUnicodeString
0x14000a65a  nop     dword ptr [rax+rax+00h]
0x14000a65f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000a666  lea     rcx, [rsp+560h+var_4F8]
0x14000a66b  mov     rdx, qword ptr [rsp+560h+DestinationString.Length]
0x14000a670  lea     r8, [rbp+460h+var_488]
0x14000a674  mov     qword ptr [rsp+560h+ShareAccess], rcx
0x14000a679  xor     r9d, r9d
0x14000a67c  lea     rcx, [rsp+560h+Length]
0x14000a681  mov     rax, [rax+758h]
0x14000a688  mov     qword ptr [rsp+560h+FileAttributes], rcx
0x14000a68d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000a694  mov     [rsp+560h+AllocationSize], r12
0x14000a699  call    _guard_dispatch_icall
0x14000a69e  mov     edi, eax
0x14000a6a0  test    eax, eax
0x14000a6a2  js      short loc_14000A6B1
0x14000a6a4  cmp     [rsp+560h+var_4F8], 3
0x14000a6a9  mov     eax, 0C0000001h
0x14000a6ae  cmovnz  edi, eax
0x14000a6b1  mov     rcx, qword ptr [rsp+560h+DestinationString.Length]; struct WDFKEY__ *
0x14000a6b6  call    ?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z; TpmRegistry::CloseKey(WDFKEY__ *)
0x14000a6bb  cmp     edi, 80000005h
0x14000a6c1  mov     ebx, r12d
0x14000a6c4  cmovnz  ebx, edi
0x14000a6c7  test    ebx, ebx
0x14000a6c9  js      loc_14000AA3C
0x14000a6cf  mov     ebx, [rsp+560h+Length]
0x14000a6d3  mov     r8, [rbp+468h]; unsigned __int64
0x14000a6da  mov     edx, ebx; unsigned __int64
0x14000a6dc  mov     cl, r13b; bool
0x14000a6df  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14000a6e4  mov     rsi, rax
0x14000a6e7  test    rax, rax
0x14000a6ea  jnz     short loc_14000A6F6
0x14000a6ec  mov     ebx, 0C000009Ah
0x14000a6f1  jmp     loc_14000AA3C
0x14000a6f6  lea     rax, [rsp+560h+Length]
0x14000a6fb  mov     [rsp+560h+Length], ebx
0x14000a6ff  mov     qword ptr [rsp+560h+FileAttributes], rax
0x14000a704  lea     rdx, aWbcl; "WBCL"
0x14000a70b  mov     edi, 3
0x14000a710  mov     dword ptr [rsp+560h+AllocationSize], ebx
0x14000a714  mov     r8d, edi
0x14000a717  mov     r9, rsi
0x14000a71a  mov     ecx, r13d
0x14000a71d  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14000a722  mov     ebx, eax
0x14000a724  test    eax, eax
0x14000a726  js      loc_14000AA3C
0x14000a72c  call    TpmEnsureDirExists
0x14000a731  mov     ebx, eax
0x14000a733  test    eax, eax
0x14000a735  js      loc_14000AA3C
0x14000a73b  lea     rdx, [rbp+460h+SourceString]; SourceString
0x14000a73f  lea     rcx, [rbp+460h+var_4C8]; DestinationString
0x14000a743  call    cs:__imp_RtlInitUnicodeString
0x14000a74a  nop     dword ptr [rax+rax+00h]
0x14000a74f  mov     [rsp+560h+EaLength], r12d; EaLength
0x14000a754  lea     rax, [rbp+460h+var_4C8]
0x14000a758  mov     [rsp+560h+EaBuffer], r12; EaBuffer
0x14000a75d  lea     r9, [rbp+460h+IoStatusBlock]; IoStatusBlock
0x14000a761  mov     [rsp+560h+CreateOptions], 60h ; '`'; CreateOptions
0x14000a769  lea     r8, [rbp+460h+ObjectAttributes]; ObjectAttributes
0x14000a76d  mov     [rsp+560h+CreateDisposition], r12d; CreateDisposition
0x14000a772  lea     rcx, [rsp+560h+FileHandle]; FileHandle
0x14000a777  mov     [rsp+560h+ShareAccess], r12d; ShareAccess
0x14000a77c  xorps   xmm0, xmm0
0x14000a77f  mov     [rsp+560h+FileAttributes], 4; FileAttributes
0x14000a787  mov     edx, 40100000h; DesiredAccess
0x14000a78c  mov     [rsp+560h+AllocationSize], r12; AllocationSize
0x14000a791  mov     [rbp+460h+ObjectAttributes.Length], 30h ; '0'
0x14000a798  mov     [rbp+460h+ObjectAttributes.RootDirectory], r12
0x14000a79c  mov     [rbp+460h+ObjectAttributes.Attributes], 240h
0x14000a7a3  mov     [rbp+460h+ObjectAttributes.ObjectName], rax
0x14000a7a7  movdqu  xmmword ptr [rbp+460h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a7ac  call    cs:__imp_ZwCreateFile
0x14000a7b3  nop     dword ptr [rax+rax+00h]
0x14000a7b8  mov     ebx, eax
0x14000a7ba  test    eax, eax
0x14000a7bc  js      loc_14000AA3C
0x14000a7c2  mov     eax, [rsp+560h+Length]
0x14000a7c6  xor     r9d, r9d; ApcContext
0x14000a7c9  mov     rcx, [rsp+560h+FileHandle]; FileHandle
0x14000a7ce  xor     r8d, r8d; ApcRoutine
0x14000a7d1  mov     qword ptr [rsp+560h+CreateOptions], r12; Key
0x14000a7d6  xor     edx, edx; Event
0x14000a7d8  mov     qword ptr [rsp+560h+CreateDisposition], r12; ByteOffset
0x14000a7dd  mov     [rsp+560h+ShareAccess], eax; Length
0x14000a7e1  lea     rax, [rbp+460h+IoStatusBlock]
0x14000a7e5  mov     qword ptr [rsp+560h+FileAttributes], rsi; Buffer
0x14000a7ea  mov     [rsp+560h+AllocationSize], rax; IoStatusBlock
0x14000a7ef  call    cs:__imp_ZwWriteFile
0x14000a7f6  nop     dword ptr [rax+rax+00h]
0x14000a7fb  mov     ebx, eax
0x14000a7fd  test    eax, eax
0x14000a7ff  js      loc_14000AA3C
0x14000a805  lea     rax, [rsp+560h+Length]
0x14000a80a  mov     [rsp+560h+Length], r12d
0x14000a80f  mov     qword ptr [rsp+560h+FileAttributes], rax
0x14000a814  lea     rdx, aWbcltrustpoint; "WBCLTrustpoint"
0x14000a81b  xor     r9d, r9d
0x14000a81e  mov     dword ptr [rsp+560h+AllocationSize], r12d
0x14000a823  mov     r8d, edi
0x14000a826  mov     ecx, r13d
0x14000a829  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14000a82e  test    eax, eax
0x14000a830  js      loc_14000A8BC
0x14000a836  mov     eax, [rsp+560h+Length]
0x14000a83a  mov     [rsp+560h+Length], eax
0x14000a83e  mov     r8, [rbp+468h]; unsigned __int64
0x14000a845  mov     edx, eax; unsigned __int64
0x14000a847  mov     cl, r13b; bool
0x14000a84a  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14000a84f  mov     r15, rax
0x14000a852  test    rax, rax
0x14000a855  jz      loc_14000A6EC
0x14000a85b  lea     r9, [rsp+560h+Length]
0x14000a860  mov     r8, rax
0x14000a863  lea     rdx, aWbcltrustpoint; "WBCLTrustpoint"
0x14000a86a  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGPEAEPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,uchar *,ulong *)
0x14000a86f  mov     ebx, eax
0x14000a871  test    eax, eax
0x14000a873  js      loc_14000AA3C
0x14000a879  mov     eax, [rsp+560h+Length]
0x14000a87d  xor     r9d, r9d; ApcContext
0x14000a880  mov     rcx, [rsp+560h+FileHandle]; FileHandle
0x14000a885  xor     r8d, r8d; ApcRoutine
0x14000a888  mov     qword ptr [rsp+560h+CreateOptions], r12; Key
0x14000a88d  xor     edx, edx; Event
0x14000a88f  mov     qword ptr [rsp+560h+CreateDisposition], r12; ByteOffset
0x14000a894  mov     [rsp+560h+ShareAccess], eax; Length
0x14000a898  lea     rax, [rbp+460h+IoStatusBlock]
0x14000a89c  mov     qword ptr [rsp+560h+FileAttributes], r15; Buffer
0x14000a8a1  mov     [rsp+560h+AllocationSize], rax; IoStatusBlock
0x14000a8a6  call    cs:__imp_ZwWriteFile
0x14000a8ad  nop     dword ptr [rax+rax+00h]
0x14000a8b2  mov     ebx, eax
0x14000a8b4  test    eax, eax
0x14000a8b6  js      loc_14000AA3C
0x14000a8bc  mov     rcx, [rsp+560h+FileHandle]; Handle
0x14000a8c1  call    cs:__imp_ZwClose
0x14000a8c8  nop     dword ptr [rax+rax+00h]
0x14000a8cd  lea     rax, [rsp+560h+Length]
0x14000a8d2  mov     [rsp+560h+FileHandle], r12
0x14000a8d7  mov     qword ptr [rsp+560h+FileAttributes], rax
0x14000a8dc  lea     rdx, aWbcldrtm; "WBCLDrtm"
0x14000a8e3  xor     r9d, r9d
0x14000a8e6  mov     dword ptr [rsp+560h+AllocationSize], r12d
0x14000a8eb  mov     r8d, edi
0x14000a8ee  mov     [rsp+560h+Length], r12d
0x14000a8f3  mov     ecx, r13d
0x14000a8f6  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14000a8fb  test    eax, eax
0x14000a8fd  js      loc_14000AA39
0x14000a903  mov     eax, [rsp+560h+Length]
0x14000a907  mov     [rsp+560h+Length], eax
0x14000a90b  mov     r8, [rbp+468h]; unsigned __int64
0x14000a912  mov     edx, eax; unsigned __int64
0x14000a914  mov     cl, r13b; bool
0x14000a917  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14000a91c  mov     r14, rax
0x14000a91f  test    rax, rax
0x14000a922  jz      loc_14000A6EC
0x14000a928  lea     r9, [rsp+560h+Length]
0x14000a92d  mov     r8, rax
0x14000a930  lea     rdx, aWbcldrtm; "WBCLDrtm"
0x14000a937  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGPEAEPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,uchar *,ulong *)
0x14000a93c  mov     ebx, eax
0x14000a93e  test    eax, eax
0x14000a940  js      loc_14000AA3C
0x14000a946  mov     qword ptr [rsp+560h+FileAttributes], r12
0x14000a94b  lea     r9, [rbp+460h+var_260]
0x14000a952  mov     r8d, r13d
0x14000a955  mov     dword ptr [rsp+560h+AllocationSize], 208h
0x14000a95d  lea     rdx, aPlatformlogfil_0; "PlatformLogFileDrtm"
0x14000a964  mov     ecx, r13d
0x14000a967  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14000a96c  mov     ebx, eax
0x14000a96e  test    eax, eax
0x14000a970  js      loc_14000AA3C
0x14000a976  lea     rdx, [rbp+460h+var_260]; SourceString
0x14000a97d  lea     rcx, [rbp+460h+var_4C8]; DestinationString
0x14000a981  call    cs:__imp_RtlInitUnicodeString
0x14000a988  nop     dword ptr [rax+rax+00h]
0x14000a98d  mov     [rsp+560h+EaLength], r12d; EaLength
0x14000a992  lea     rax, [rbp+460h+var_4C8]
0x14000a996  mov     [rsp+560h+EaBuffer], r12; EaBuffer
0x14000a99b  lea     r9, [rbp+460h+IoStatusBlock]; IoStatusBlock
0x14000a99f  mov     [rsp+560h+CreateOptions], 60h ; '`'; CreateOptions
0x14000a9a7  lea     r8, [rbp+460h+ObjectAttributes]; ObjectAttributes
0x14000a9ab  mov     [rsp+560h+CreateDisposition], r12d; CreateDisposition
0x14000a9b0  lea     rcx, [rsp+560h+FileHandle]; FileHandle
0x14000a9b5  mov     [rsp+560h+ShareAccess], r12d; ShareAccess
0x14000a9ba  xorps   xmm0, xmm0
0x14000a9bd  mov     [rsp+560h+FileAttributes], 4; FileAttributes
0x14000a9c5  mov     edx, 40100000h; DesiredAccess
0x14000a9ca  mov     [rsp+560h+AllocationSize], r12; AllocationSize
0x14000a9cf  mov     [rbp+460h+ObjectAttributes.Length], 30h ; '0'
0x14000a9d6  mov     [rbp+460h+ObjectAttributes.RootDirectory], r12
0x14000a9da  mov     [rbp+460h+ObjectAttributes.Attributes], 240h
0x14000a9e1  mov     [rbp+460h+ObjectAttributes.ObjectName], rax
0x14000a9e5  movdqu  xmmword ptr [rbp+460h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a9ea  call    cs:__imp_ZwCreateFile
0x14000a9f1  nop     dword ptr [rax+rax+00h]
0x14000a9f6  mov     ebx, eax
0x14000a9f8  test    eax, eax
0x14000a9fa  js      short loc_14000AA3C
0x14000a9fc  mov     eax, [rsp+560h+Length]
0x14000aa00  xor     r9d, r9d; ApcContext
0x14000aa03  mov     rcx, [rsp+560h+FileHandle]; FileHandle
0x14000aa08  xor     r8d, r8d; ApcRoutine
0x14000aa0b  mov     qword ptr [rsp+560h+CreateOptions], r12; Key
0x14000aa10  xor     edx, edx; Event
  ... truncated ...
```
