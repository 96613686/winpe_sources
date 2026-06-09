# WofInstanceSetupNewStack

- ea: `0x14003ec00`
- end: `0x14003eea7`
- name: `WofInstanceSetupNewStack`
- size: `679`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, installer_update`

## callees

- `0x14000bcbc`
- `0x140011560`
- `0x140011640`
- `0x14003ec00`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003ecdb`
- `ntoskrnl!ObfDereferenceObject` at `0x14003edc4`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ecdb`
- `ntoskrnl!ObfDereferenceObject` at `0x14003edc4`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14003ecb8`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14003ecb8`
- `FLTMGR!FltClose` at `0x14003edb4`
- `FLTMGR!FltClose` at `0x14003edb4`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003ed8d`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003ed8d`

## pseudocode

```c
void __fastcall WofInstanceSetupNewStack(NTSTATUS *Parameter)
{
  char v2; // si
  unsigned int i; // ebx
  __int64 v4; // rcx
  int (__fastcall *v5)(_QWORD); // rax
  bool v6; // bl
  __int64 v7; // rcx
  NTSTATUS v8; // eax
  ULONG v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  NTSTATUS v12; // eax
  unsigned int j; // ebx
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 (__fastcall *v16)(_QWORD); // rax
  int v17; // eax
  __int64 v18; // rcx
  void (__fastcall *v19)(_QWORD); // rax
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+50h] [rbp-9h] BYREF
  ULONG LengthReturned; // [rsp+58h] [rbp-1h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp+7h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+68h] [rbp+Fh] BYREF
  __int128 FileInformation; // [rsp+78h] [rbp+1Fh] BYREF

  if ( (Parameter[6] & 2) != 0 )
    goto LABEL_21;
  if ( !dword_140018458 )
  {
LABEL_20:
    *Parameter = -1073740691;
    return;
  }
  v2 = 0;
  for ( i = 0; i < 4; ++i )
  {
    v4 = 424LL * i;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v4) )
    {
      v5 = *(int (__fastcall **)(_QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v4 + 264);
      if ( v5 )
      {
        if ( v5(*((_QWORD *)Parameter + 1) + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v4 + 20)) >= 0 )
        {
          v2 = 1;
          break;
        }
      }
    }
  }
  v6 = 1;
  if ( dword_140018458 == 2 )
  {
    v7 = *((_QWORD *)Parameter + 1);
    DiskDeviceObject = 0;
    v8 = FltGetDiskDeviceObject(*(PFLT_VOLUME *)(v7 + 112), &DiskDeviceObject);
    *Parameter = v8;
    if ( v8 < 0 )
      return;
    v9 = DiskDeviceObject->Flags & 0x100;
    ObfDereferenceObject(DiskDeviceObject);
    v2 = v9 != 0 ? v2 : 0;
    v6 = v9 != 0;
  }
  if ( v2 )
    goto LABEL_21;
  v10 = *((_QWORD *)Parameter + 1);
  FileName.Buffer = (PWSTR)&FileTag;
  DiskDeviceObject = 0;
  FileHandle = 0;
  *(_QWORD *)&FileName.Length = 262148;
  FileInformation = 0;
  LengthReturned = 0;
  v11 = WofOpenReparseIndex(v10, 0, (PFILE_OBJECT *)&DiskDeviceObject, &FileHandle);
  *Parameter = v11;
  if ( v11 < 0 )
  {
    *Parameter = 0;
    goto LABEL_19;
  }
  v12 = FltQueryDirectoryFile(
          *(PFLT_INSTANCE *)(*((_QWORD *)Parameter + 2) + 24LL),
          (PFILE_OBJECT)DiskDeviceObject,
          &FileInformation,
          0x10u,
          FileReparsePointInformation,
          1u,
          &FileName,
          1u,
          &LengthReturned);
  *Parameter = v12;
  if ( v12 >= 0 )
    v2 = DWORD2(FileInformation) == FileTag;
  FltClose(FileHandle);
  ObfDereferenceObject(DiskDeviceObject);
  if ( v2 )
  {
LABEL_21:
    *(_DWORD *)(*((_QWORD *)Parameter + 1) + 56LL) &= ~1u;
    _InterlockedAdd(&dword_140018460, 1u);
    _InterlockedDecrement(&dword_14001845C);
    goto LABEL_22;
  }
LABEL_19:
  if ( !v6 )
    goto LABEL_20;
LABEL_22:
  for ( j = 0; j < 4; ++j )
  {
    v14 = j;
    v15 = 424LL * j;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v15) )
    {
      v16 = *(__int64 (__fastcall **)(_QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v15 + 192);
      if ( v16 )
      {
        v17 = v16(
                *((_QWORD *)Parameter + 1)
              + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v15 + 20));
        *Parameter = v17;
        if ( v17 < 0 )
        {
          while ( j )
          {
            --v14;
            --j;
            v18 = 424 * v14;
            if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v14) )
            {
              v19 = *(void (__fastcall **)(_QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v18 + 128);
              if ( v19 )
                v19(
                  *((_QWORD *)Parameter + 1)
                + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v18 + 20));
            }
          }
          *(_DWORD *)(*((_QWORD *)Parameter + 1) + 172LL) = 0;
          return;
        }
        *(_DWORD *)(*((_QWORD *)Parameter + 1) + 172LL) = j;
      }
    }
  }
}

```

## disassembly

```asm
0x14003ec00  mov     [rsp-8+arg_8], rbx
0x14003ec05  mov     [rsp-8+arg_10], rsi
0x14003ec0a  push    rbp
0x14003ec0b  push    rdi
0x14003ec0c  push    r12
0x14003ec0e  push    r13
0x14003ec10  push    r15
0x14003ec12  lea     rbp, [rsp-37h]
0x14003ec17  sub     rsp, 90h
0x14003ec1e  mov     rax, cs:__security_cookie
0x14003ec25  xor     rax, rsp
0x14003ec28  mov     [rbp+57h+var_28], rax
0x14003ec2c  mov     eax, [rcx+18h]
0x14003ec2f  lea     r12, WPP_MAIN_CB.Queue+10h
0x14003ec36  mov     r13d, 4
0x14003ec3c  mov     rdi, rcx
0x14003ec3f  lea     r15d, [r13-3]
0x14003ec43  test    al, 2
0x14003ec45  jnz     loc_14003EDE4
0x14003ec4b  cmp     cs:dword_140018458, 0
0x14003ec52  jz      loc_14003EDD9
0x14003ec58  xor     sil, sil
0x14003ec5b  xor     ebx, ebx
0x14003ec5d  cmp     ebx, r13d
0x14003ec60  jnb     short loc_14003EC98
0x14003ec62  mov     eax, ebx
0x14003ec64  imul    rcx, rax, 1A8h
0x14003ec6b  cmp     [rcx+r12], sil
0x14003ec6f  jz      short loc_14003EC90
0x14003ec71  mov     rax, [rcx+r12+108h]
0x14003ec79  test    rax, rax
0x14003ec7c  jz      short loc_14003EC90
0x14003ec7e  mov     ecx, [rcx+r12+14h]
0x14003ec83  add     rcx, [rdi+8]
0x14003ec87  call    _guard_dispatch_icall
0x14003ec8c  test    eax, eax
0x14003ec8e  jns     short loc_14003EC95
0x14003ec90  add     ebx, r15d
0x14003ec93  jmp     short loc_14003EC5D
0x14003ec95  mov     sil, r15b
0x14003ec98  cmp     cs:dword_140018458, 2
0x14003ec9f  mov     bl, r15b
0x14003eca2  jnz     short loc_14003ECF5
0x14003eca4  mov     rcx, [rdi+8]
0x14003eca8  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x14003ecac  mov     [rbp+57h+DiskDeviceObject], 0
0x14003ecb4  mov     rcx, [rcx+70h]; Volume
0x14003ecb8  call    cs:__imp_FltGetDiskDeviceObject
0x14003ecbf  nop     dword ptr [rax+rax+00h]
0x14003ecc4  mov     [rdi], eax
0x14003ecc6  test    eax, eax
0x14003ecc8  js      loc_14003EE7E
0x14003ecce  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x14003ecd2  mov     ebx, [rcx+30h]
0x14003ecd5  and     ebx, 100h
0x14003ecdb  call    cs:__imp_ObfDereferenceObject
0x14003ece2  nop     dword ptr [rax+rax+00h]
0x14003ece7  mov     eax, ebx
0x14003ece9  neg     eax
0x14003eceb  sbb     cl, cl
0x14003eced  and     sil, cl
0x14003ecf0  test    ebx, ebx
0x14003ecf2  setnz   bl
0x14003ecf5  test    sil, sil
0x14003ecf8  jnz     loc_14003EDE4
0x14003ecfe  mov     rcx, [rdi+8]
0x14003ed02  lea     rax, FileTag
0x14003ed09  xorps   xmm0, xmm0
0x14003ed0c  mov     [rbp+57h+var_48.Buffer], rax
0x14003ed10  lea     r9, [rbp+57h+FileHandle]
0x14003ed14  mov     [rbp+57h+DiskDeviceObject], 0
0x14003ed1c  lea     r8, [rbp+57h+DiskDeviceObject]
0x14003ed20  mov     [rbp+57h+FileHandle], 0
0x14003ed28  xor     edx, edx
0x14003ed2a  mov     qword ptr [rbp+57h+var_48.Length], 40004h
0x14003ed32  movups  [rbp+57h+FileInformation], xmm0
0x14003ed36  mov     [rbp+57h+var_58], 0
0x14003ed3d  call    WofOpenReparseIndex
0x14003ed42  mov     [rdi], eax
0x14003ed44  test    eax, eax
0x14003ed46  jns     short loc_14003ED53
0x14003ed48  mov     dword ptr [rdi], 0
0x14003ed4e  jmp     loc_14003EDD5
0x14003ed53  mov     rcx, [rdi+10h]
0x14003ed57  lea     rax, [rbp+57h+var_58]
0x14003ed5b  mov     rdx, [rbp+57h+DiskDeviceObject]; FileObject
0x14003ed5f  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14003ed63  mov     [rsp+0B0h+LengthReturned], rax; LengthReturned
0x14003ed68  mov     r9d, 10h; Length
0x14003ed6e  mov     [rsp+0B0h+RestartScan], r15b; RestartScan
0x14003ed73  lea     rax, [rbp+57h+var_48]
0x14003ed77  mov     rcx, [rcx+18h]; Instance
0x14003ed7b  mov     [rsp+0B0h+FileName], rax; FileName
0x14003ed80  mov     [rsp+0B0h+ReturnSingleEntry], r15b; ReturnSingleEntry
0x14003ed85  mov     [rsp+0B0h+FileInformationClass], 21h ; '!'; FileInformationClass
0x14003ed8d  call    cs:__imp_FltQueryDirectoryFile
0x14003ed94  nop     dword ptr [rax+rax+00h]
0x14003ed99  mov     [rdi], eax
0x14003ed9b  test    eax, eax
0x14003ed9d  js      short loc_14003EDB0
0x14003ed9f  mov     eax, cs:FileTag
0x14003eda5  cmp     dword ptr [rbp+57h+FileInformation+8], eax
0x14003eda8  movzx   esi, sil
0x14003edac  cmovz   esi, r15d
0x14003edb0  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14003edb4  call    cs:__imp_FltClose
0x14003edbb  nop     dword ptr [rax+rax+00h]
0x14003edc0  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x14003edc4  call    cs:__imp_ObfDereferenceObject
0x14003edcb  nop     dword ptr [rax+rax+00h]
0x14003edd0  test    sil, sil
0x14003edd3  jnz     short loc_14003EDE4
0x14003edd5  test    bl, bl
0x14003edd7  jnz     short loc_14003EDFB
0x14003edd9  mov     dword ptr [rdi], 0C000046Dh
0x14003eddf  jmp     loc_14003EE7E
0x14003ede4  mov     rax, [rdi+8]
0x14003ede8  and     dword ptr [rax+38h], 0FFFFFFFEh
0x14003edec  lock add cs:dword_140018460, r15d
0x14003edf4  lock dec cs:dword_14001845C
0x14003edfb  xor     ebx, ebx
0x14003edfd  cmp     ebx, r13d
0x14003ee00  jnb     short loc_14003EE7E
0x14003ee02  mov     esi, ebx
0x14003ee04  imul    rcx, rsi, 1A8h
0x14003ee0b  cmp     byte ptr [rcx+r12], 0
0x14003ee10  jz      short loc_14003EE3D
0x14003ee12  mov     rax, [rcx+r12+0C0h]
0x14003ee1a  test    rax, rax
0x14003ee1d  jz      short loc_14003EE3D
0x14003ee1f  mov     ecx, [rcx+r12+14h]
0x14003ee24  add     rcx, [rdi+8]
0x14003ee28  call    _guard_dispatch_icall
0x14003ee2d  mov     [rdi], eax
0x14003ee2f  test    eax, eax
0x14003ee31  js      short loc_14003EE70
0x14003ee33  mov     rax, [rdi+8]
0x14003ee37  mov     [rax+0ACh], ebx
0x14003ee3d  add     ebx, r15d
0x14003ee40  jmp     short loc_14003EDFD
0x14003ee42  dec     rsi
0x14003ee45  dec     ebx
0x14003ee47  imul    rcx, rsi, 1A8h
0x14003ee4e  cmp     byte ptr [rcx+r12], 0
0x14003ee53  jz      short loc_14003EE70
0x14003ee55  mov     rax, [rcx+r12+80h]
0x14003ee5d  test    rax, rax
0x14003ee60  jz      short loc_14003EE70
0x14003ee62  mov     ecx, [rcx+r12+14h]
0x14003ee67  add     rcx, [rdi+8]
0x14003ee6b  call    _guard_dispatch_icall
0x14003ee70  test    ebx, ebx
0x14003ee72  jnz     short loc_14003EE42
0x14003ee74  mov     rax, [rdi+8]
0x14003ee78  mov     [rax+0ACh], ebx
0x14003ee7e  mov     rcx, [rbp+57h+var_28]
0x14003ee82  xor     rcx, rsp; StackCookie
0x14003ee85  call    __security_check_cookie
0x14003ee8a  lea     r11, [rsp+0B0h+var_20]
0x14003ee92  mov     rbx, [r11+38h]
0x14003ee96  mov     rsi, [r11+40h]
0x14003ee9a  mov     rsp, r11
0x14003ee9d  pop     r15
0x14003ee9f  pop     r13
0x14003eea1  pop     r12
0x14003eea3  pop     rdi
0x14003eea4  pop     rbp
0x14003eea5  retn
```
