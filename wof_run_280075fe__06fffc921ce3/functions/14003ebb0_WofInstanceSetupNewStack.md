# WofInstanceSetupNewStack

- ea: `0x14003ebb0`
- end: `0x14003ee57`
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
- `0x14003ebb0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003ec8b`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ed74`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ec8b`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ed74`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14003ec68`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14003ec68`
- `FLTMGR!FltClose` at `0x14003ed64`
- `FLTMGR!FltClose` at `0x14003ed64`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003ed3d`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003ed3d`

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
0x14003ebb0  mov     [rsp-8+arg_8], rbx
0x14003ebb5  mov     [rsp-8+arg_10], rsi
0x14003ebba  push    rbp
0x14003ebbb  push    rdi
0x14003ebbc  push    r12
0x14003ebbe  push    r13
0x14003ebc0  push    r15
0x14003ebc2  lea     rbp, [rsp-37h]
0x14003ebc7  sub     rsp, 90h
0x14003ebce  mov     rax, cs:__security_cookie
0x14003ebd5  xor     rax, rsp
0x14003ebd8  mov     [rbp+57h+var_28], rax
0x14003ebdc  mov     eax, [rcx+18h]
0x14003ebdf  lea     r12, WPP_MAIN_CB.Queue+10h
0x14003ebe6  mov     r13d, 4
0x14003ebec  mov     rdi, rcx
0x14003ebef  lea     r15d, [r13-3]
0x14003ebf3  test    al, 2
0x14003ebf5  jnz     loc_14003ED94
0x14003ebfb  cmp     cs:dword_140018458, 0
0x14003ec02  jz      loc_14003ED89
0x14003ec08  xor     sil, sil
0x14003ec0b  xor     ebx, ebx
0x14003ec0d  cmp     ebx, r13d
0x14003ec10  jnb     short loc_14003EC48
0x14003ec12  mov     eax, ebx
0x14003ec14  imul    rcx, rax, 1A8h
0x14003ec1b  cmp     [rcx+r12], sil
0x14003ec1f  jz      short loc_14003EC40
0x14003ec21  mov     rax, [rcx+r12+108h]
0x14003ec29  test    rax, rax
0x14003ec2c  jz      short loc_14003EC40
0x14003ec2e  mov     ecx, [rcx+r12+14h]
0x14003ec33  add     rcx, [rdi+8]
0x14003ec37  call    _guard_dispatch_icall
0x14003ec3c  test    eax, eax
0x14003ec3e  jns     short loc_14003EC45
0x14003ec40  add     ebx, r15d
0x14003ec43  jmp     short loc_14003EC0D
0x14003ec45  mov     sil, r15b
0x14003ec48  cmp     cs:dword_140018458, 2
0x14003ec4f  mov     bl, r15b
0x14003ec52  jnz     short loc_14003ECA5
0x14003ec54  mov     rcx, [rdi+8]
0x14003ec58  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x14003ec5c  mov     [rbp+57h+DiskDeviceObject], 0
0x14003ec64  mov     rcx, [rcx+70h]; Volume
0x14003ec68  call    cs:__imp_FltGetDiskDeviceObject
0x14003ec6f  nop     dword ptr [rax+rax+00h]
0x14003ec74  mov     [rdi], eax
0x14003ec76  test    eax, eax
0x14003ec78  js      loc_14003EE2E
0x14003ec7e  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x14003ec82  mov     ebx, [rcx+30h]
0x14003ec85  and     ebx, 100h
0x14003ec8b  call    cs:__imp_ObfDereferenceObject
0x14003ec92  nop     dword ptr [rax+rax+00h]
0x14003ec97  mov     eax, ebx
0x14003ec99  neg     eax
0x14003ec9b  sbb     cl, cl
0x14003ec9d  and     sil, cl
0x14003eca0  test    ebx, ebx
0x14003eca2  setnz   bl
0x14003eca5  test    sil, sil
0x14003eca8  jnz     loc_14003ED94
0x14003ecae  mov     rcx, [rdi+8]
0x14003ecb2  lea     rax, FileTag
0x14003ecb9  xorps   xmm0, xmm0
0x14003ecbc  mov     [rbp+57h+var_48.Buffer], rax
0x14003ecc0  lea     r9, [rbp+57h+FileHandle]
0x14003ecc4  mov     [rbp+57h+DiskDeviceObject], 0
0x14003eccc  lea     r8, [rbp+57h+DiskDeviceObject]
0x14003ecd0  mov     [rbp+57h+FileHandle], 0
0x14003ecd8  xor     edx, edx
0x14003ecda  mov     qword ptr [rbp+57h+var_48.Length], 40004h
0x14003ece2  movups  [rbp+57h+FileInformation], xmm0
0x14003ece6  mov     [rbp+57h+var_58], 0
0x14003eced  call    WofOpenReparseIndex
0x14003ecf2  mov     [rdi], eax
0x14003ecf4  test    eax, eax
0x14003ecf6  jns     short loc_14003ED03
0x14003ecf8  mov     dword ptr [rdi], 0
0x14003ecfe  jmp     loc_14003ED85
0x14003ed03  mov     rcx, [rdi+10h]
0x14003ed07  lea     rax, [rbp+57h+var_58]
0x14003ed0b  mov     rdx, [rbp+57h+DiskDeviceObject]; FileObject
0x14003ed0f  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14003ed13  mov     [rsp+0B0h+LengthReturned], rax; LengthReturned
0x14003ed18  mov     r9d, 10h; Length
0x14003ed1e  mov     [rsp+0B0h+RestartScan], r15b; RestartScan
0x14003ed23  lea     rax, [rbp+57h+var_48]
0x14003ed27  mov     rcx, [rcx+18h]; Instance
0x14003ed2b  mov     [rsp+0B0h+FileName], rax; FileName
0x14003ed30  mov     [rsp+0B0h+ReturnSingleEntry], r15b; ReturnSingleEntry
0x14003ed35  mov     [rsp+0B0h+FileInformationClass], 21h ; '!'; FileInformationClass
0x14003ed3d  call    cs:__imp_FltQueryDirectoryFile
0x14003ed44  nop     dword ptr [rax+rax+00h]
0x14003ed49  mov     [rdi], eax
0x14003ed4b  test    eax, eax
0x14003ed4d  js      short loc_14003ED60
0x14003ed4f  mov     eax, cs:FileTag
0x14003ed55  cmp     dword ptr [rbp+57h+FileInformation+8], eax
0x14003ed58  movzx   esi, sil
0x14003ed5c  cmovz   esi, r15d
0x14003ed60  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14003ed64  call    cs:__imp_FltClose
0x14003ed6b  nop     dword ptr [rax+rax+00h]
0x14003ed70  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x14003ed74  call    cs:__imp_ObfDereferenceObject
0x14003ed7b  nop     dword ptr [rax+rax+00h]
0x14003ed80  test    sil, sil
0x14003ed83  jnz     short loc_14003ED94
0x14003ed85  test    bl, bl
0x14003ed87  jnz     short loc_14003EDAB
0x14003ed89  mov     dword ptr [rdi], 0C000046Dh
0x14003ed8f  jmp     loc_14003EE2E
0x14003ed94  mov     rax, [rdi+8]
0x14003ed98  and     dword ptr [rax+38h], 0FFFFFFFEh
0x14003ed9c  lock add cs:dword_140018460, r15d
0x14003eda4  lock dec cs:dword_14001845C
0x14003edab  xor     ebx, ebx
0x14003edad  cmp     ebx, r13d
0x14003edb0  jnb     short loc_14003EE2E
0x14003edb2  mov     esi, ebx
0x14003edb4  imul    rcx, rsi, 1A8h
0x14003edbb  cmp     byte ptr [rcx+r12], 0
0x14003edc0  jz      short loc_14003EDED
0x14003edc2  mov     rax, [rcx+r12+0C0h]
0x14003edca  test    rax, rax
0x14003edcd  jz      short loc_14003EDED
0x14003edcf  mov     ecx, [rcx+r12+14h]
0x14003edd4  add     rcx, [rdi+8]
0x14003edd8  call    _guard_dispatch_icall
0x14003eddd  mov     [rdi], eax
0x14003eddf  test    eax, eax
0x14003ede1  js      short loc_14003EE20
0x14003ede3  mov     rax, [rdi+8]
0x14003ede7  mov     [rax+0ACh], ebx
0x14003eded  add     ebx, r15d
0x14003edf0  jmp     short loc_14003EDAD
0x14003edf2  dec     rsi
0x14003edf5  dec     ebx
0x14003edf7  imul    rcx, rsi, 1A8h
0x14003edfe  cmp     byte ptr [rcx+r12], 0
0x14003ee03  jz      short loc_14003EE20
0x14003ee05  mov     rax, [rcx+r12+80h]
0x14003ee0d  test    rax, rax
0x14003ee10  jz      short loc_14003EE20
0x14003ee12  mov     ecx, [rcx+r12+14h]
0x14003ee17  add     rcx, [rdi+8]
0x14003ee1b  call    _guard_dispatch_icall
0x14003ee20  test    ebx, ebx
0x14003ee22  jnz     short loc_14003EDF2
0x14003ee24  mov     rax, [rdi+8]
0x14003ee28  mov     [rax+0ACh], ebx
0x14003ee2e  mov     rcx, [rbp+57h+var_28]
0x14003ee32  xor     rcx, rsp; StackCookie
0x14003ee35  call    __security_check_cookie
0x14003ee3a  lea     r11, [rsp+0B0h+var_20]
0x14003ee42  mov     rbx, [r11+38h]
0x14003ee46  mov     rsi, [r11+40h]
0x14003ee4a  mov     rsp, r11
0x14003ee4d  pop     r15
0x14003ee4f  pop     r13
0x14003ee51  pop     r12
0x14003ee53  pop     rdi
0x14003ee54  pop     rbp
0x14003ee55  retn
```
