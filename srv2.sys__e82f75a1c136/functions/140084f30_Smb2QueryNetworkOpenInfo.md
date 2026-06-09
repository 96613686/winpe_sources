# Smb2QueryNetworkOpenInfo

- ea: `0x140084f30`
- end: `0x140085250`
- name: `Smb2QueryNetworkOpenInfo`
- size: `800`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000f4d0`

## callees

- `0x140005070`
- `0x140038490`
- `0x1400384d0`
- `0x140084f30`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140084f7d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140084f7d`
- `ntoskrnl!NtQueryInformationFile` at `0x140085042`
- `ntoskrnl!NtQueryInformationFile` at `0x1400850be`
- `ntoskrnl!NtQueryInformationFile` at `0x140085178`
- `ntoskrnl!NtQueryInformationFile` at `0x140085042`
- `ntoskrnl!NtQueryInformationFile` at `0x1400850be`
- `ntoskrnl!NtQueryInformationFile` at `0x140085178`

## string_xrefs

- `0x140084f95`: `Smb2QueryNetworkOpenInfo`
- `0x140084fe5`: `Smb2QueryNetworkOpenInfo`
- `0x14008504e`: `Smb2QueryNetworkOpenInfo`
- `0x140085088`: `Smb2QueryNetworkOpenInfo`
- `0x1400850cd`: `Smb2QueryNetworkOpenInfo`
- `0x1400850f3`: `Smb2QueryNetworkOpenInfo`
- `0x14008511a`: `Smb2QueryNetworkOpenInfo`
- `0x140085187`: `Smb2QueryNetworkOpenInfo`
- `0x1400851eb`: `Smb2QueryNetworkOpenInfo`

## pseudocode

```c
__int64 __fastcall Smb2QueryNetworkOpenInfo(__int64 a1, __int64 a2, _OWORD *a3)
{
  struct _FILE_OBJECT *v4; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  PDEVICE_OBJECT v10; // r14
  PFAST_IO_DISPATCH FastIoDispatch; // rdi
  __int64 v12; // rdx
  unsigned __int8 (__fastcall *FastIoQueryNetworkOpenInfo)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  NTSTATUS v15; // eax
  NTSTATUS Status; // r12d
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned __int8 (__fastcall *FastIoQueryStandardInfo)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rdi
  __int64 v20; // rdx
  unsigned __int8 (__fastcall *FastIoQueryBasicInfo)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r12
  __int64 v22; // rdx
  char FileInformationClasse; // [rsp+20h] [rbp-49h]
  int FileInformationClass; // [rsp+20h] [rbp-49h]
  int FileInformationClassf; // [rsp+20h] [rbp-49h]
  int FileInformationClassa; // [rsp+20h] [rbp-49h]
  int FileInformationClassb; // [rsp+20h] [rbp-49h]
  int FileInformationClassc; // [rsp+20h] [rbp-49h]
  int FileInformationClassd; // [rsp+20h] [rbp-49h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-39h] BYREF
  __int128 v31; // [rsp+40h] [rbp-29h] BYREF
  __int64 v32; // [rsp+50h] [rbp-19h]
  __int128 FileInformation; // [rsp+58h] [rbp-11h] BYREF
  __int128 v34; // [rsp+68h] [rbp-1h]
  __int64 v35; // [rsp+78h] [rbp+Fh]

  v35 = 0;
  v4 = *(struct _FILE_OBJECT **)(a2 + 96);
  FileInformation = 0;
  v32 = 0;
  v34 = 0;
  v31 = 0;
  IoStatusBlock = 0;
  RelatedDeviceObject = IoGetRelatedDeviceObject(v4);
  v8 = a1 + 584;
  FileInformationClasse = 1;
  LOBYTE(v9) = 2;
  v10 = RelatedDeviceObject;
  FastIoDispatch = RelatedDeviceObject->DriverObject->FastIoDispatch;
  SRV2_PERF_ENTER_EX(v8, v9, 1984, "Smb2QueryNetworkOpenInfo", FileInformationClasse);
  if ( FastIoDispatch )
  {
    if ( FastIoDispatch->SizeOfFastIoDispatch > 0x70 )
    {
      FastIoQueryNetworkOpenInfo = (unsigned __int8 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))FastIoDispatch->FastIoQueryNetworkOpenInfo;
      if ( FastIoQueryNetworkOpenInfo )
      {
        LOBYTE(v12) = 1;
        if ( FastIoQueryNetworkOpenInfo(*(_QWORD *)(a2 + 96), v12, a3, &IoStatusBlock, v10) )
        {
          LOBYTE(FileInformationClass) = 1;
          SRV2_PERF_ENTER_EX(v8, 0, 1999, "Smb2QueryNetworkOpenInfo", FileInformationClass);
          return (unsigned int)IoStatusBlock.Status;
        }
      }
    }
  }
  v15 = NtQueryInformationFile(*(HANDLE *)(a2 + 88), &IoStatusBlock, a3, 0x38u, FileNetworkOpenInformation);
  LOBYTE(FileInformationClassf) = 1;
  Status = v15;
  SRV2_PERF_ENTER_EX(v8, 0, 2015, "Smb2QueryNetworkOpenInfo", FileInformationClassf);
  if ( Status < 0 )
  {
    if ( FastIoDispatch && FastIoDispatch->SizeOfFastIoDispatch > 0x20 )
    {
      FastIoQueryBasicInfo = (unsigned __int8 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))FastIoDispatch->FastIoQueryBasicInfo;
      LOBYTE(FileInformationClassa) = 1;
      LOBYTE(v17) = 2;
      SRV2_PERF_ENTER_EX(v8, v17, 2039, "Smb2QueryNetworkOpenInfo", FileInformationClassa);
      if ( FastIoQueryBasicInfo )
      {
        LOBYTE(v22) = 1;
        if ( FastIoQueryBasicInfo(*(_QWORD *)(a2 + 96), v22, &FileInformation, &IoStatusBlock, v10) )
        {
          Status = IoStatusBlock.Status;
LABEL_11:
          LOBYTE(FileInformationClassb) = 1;
          SRV2_PERF_ENTER_EX(v8, 0, 2060, "Smb2QueryNetworkOpenInfo", FileInformationClassb);
          if ( Status < 0 )
            return (unsigned int)Status;
          if ( FastIoDispatch && FastIoDispatch->SizeOfFastIoDispatch > 0x28 )
          {
            FastIoQueryStandardInfo = (unsigned __int8 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))FastIoDispatch->FastIoQueryStandardInfo;
            LOBYTE(FileInformationClassc) = 1;
            LOBYTE(v18) = 2;
            SRV2_PERF_ENTER_EX(v8, v18, 2080, "Smb2QueryNetworkOpenInfo", FileInformationClassc);
            if ( FastIoQueryStandardInfo )
            {
              LOBYTE(v20) = 1;
              if ( FastIoQueryStandardInfo(*(_QWORD *)(a2 + 96), v20, &v31, &IoStatusBlock, v10) )
              {
                Status = IoStatusBlock.Status;
LABEL_18:
                LOBYTE(FileInformationClassd) = 1;
                SRV2_PERF_ENTER_EX(v8, 0, 2101, "Smb2QueryNetworkOpenInfo", FileInformationClassd);
                if ( Status >= 0 )
                {
                  *a3 = FileInformation;
                  a3[1] = v34;
                  a3[2] = v31;
                  *((_DWORD *)a3 + 12) = v35;
                }
                return (unsigned int)Status;
              }
            }
          }
          else
          {
            LOBYTE(FileInformationClassc) = 1;
            LOBYTE(v18) = 2;
            SRV2_PERF_ENTER_EX(v8, v18, 2080, "Smb2QueryNetworkOpenInfo", FileInformationClassc);
          }
          Status = NtQueryInformationFile(*(HANDLE *)(a2 + 88), &IoStatusBlock, &v31, 0x18u, FileStandardInformation);
          goto LABEL_18;
        }
      }
    }
    else
    {
      LOBYTE(FileInformationClassa) = 1;
      LOBYTE(v17) = 2;
      SRV2_PERF_ENTER_EX(v8, v17, 2039, "Smb2QueryNetworkOpenInfo", FileInformationClassa);
    }
    Status = NtQueryInformationFile(*(HANDLE *)(a2 + 88), &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    goto LABEL_11;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140084f30  push    rbp
0x140084f32  push    rbx
0x140084f33  push    rsi
0x140084f34  push    rdi
0x140084f35  push    r14
0x140084f37  push    r15
0x140084f39  lea     rbp, [rsp-2Fh]
0x140084f3e  sub     rsp, 98h
0x140084f45  mov     rax, cs:__security_cookie
0x140084f4c  xor     rax, rsp
0x140084f4f  mov     [rbp+57h+var_40], rax
0x140084f53  xorps   xmm0, xmm0
0x140084f56  xor     eax, eax
0x140084f58  mov     rbx, rcx
0x140084f5b  mov     [rbp+57h+var_48], rax
0x140084f5f  mov     rcx, [rdx+60h]; FileObject
0x140084f63  mov     r15, r8
0x140084f66  movups  [rbp+57h+FileInformation], xmm0
0x140084f6a  mov     [rbp+57h+var_70], rax
0x140084f6e  mov     rsi, rdx
0x140084f71  movups  [rbp+57h+var_58], xmm0
0x140084f75  movups  [rbp+57h+var_80], xmm0
0x140084f79  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140084f7d  call    cs:__imp_IoGetRelatedDeviceObject
0x140084f84  nop     dword ptr [rax+rax+00h]
0x140084f89  add     rbx, 248h
0x140084f90  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x140084f95  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140084f9c  mov     r8d, 7C0h
0x140084fa2  mov     dl, 2
0x140084fa4  mov     r14, rax
0x140084fa7  mov     rcx, [rax+8]
0x140084fab  mov     rdi, [rcx+50h]
0x140084faf  mov     rcx, rbx
0x140084fb2  call    SRV2_PERF_ENTER_EX
0x140084fb7  test    rdi, rdi
0x140084fba  jz      short loc_140085021
0x140084fbc  cmp     dword ptr [rdi], 70h ; 'p'
0x140084fbf  jbe     short loc_140085021
0x140084fc1  mov     rax, [rdi+70h]
0x140084fc5  test    rax, rax
0x140084fc8  jz      short loc_140085021
0x140084fca  mov     rcx, [rsi+60h]
0x140084fce  lea     r9, [rbp+57h+IoStatusBlock]
0x140084fd2  mov     r8, r15
0x140084fd5  mov     qword ptr [rsp+0C0h+FileInformationClass], r14
0x140084fda  mov     dl, 1
0x140084fdc  call    _guard_dispatch_icall
0x140084fe1  test    al, al
0x140084fe3  jz      short loc_140085021
0x140084fe5  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140084fec  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x140084ff1  xor     edx, edx
0x140084ff3  mov     r8d, 7CFh
0x140084ff9  mov     rcx, rbx
0x140084ffc  call    SRV2_PERF_ENTER_EX
0x140085001  mov     eax, dword ptr [rbp+57h+IoStatusBlock]
0x140085004  mov     rcx, [rbp+57h+var_40]
0x140085008  xor     rcx, rsp; StackCookie
0x14008500b  call    __security_check_cookie
0x140085010  add     rsp, 98h
0x140085017  pop     r15
0x140085019  pop     r14
0x14008501b  pop     rdi
0x14008501c  pop     rsi
0x14008501d  pop     rbx
0x14008501e  pop     rbp
0x14008501f  retn
0x140085021  mov     rcx, [rsi+58h]; FileHandle
0x140085025  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140085029  mov     r9d, 38h ; '8'; Length
0x14008502f  mov     [rsp+0C0h+var_30], r12
0x140085037  mov     r8, r15; FileInformation
0x14008503a  mov     [rsp+0C0h+FileInformationClass], 22h ; '"'; FileInformationClass
0x140085042  call    cs:__imp_NtQueryInformationFile
0x140085049  nop     dword ptr [rax+rax+00h]
0x14008504e  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140085055  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x14008505a  xor     edx, edx
0x14008505c  mov     r8d, 7DFh
0x140085062  mov     rcx, rbx
0x140085065  mov     r12d, eax
0x140085068  call    SRV2_PERF_ENTER_EX
0x14008506d  test    r12d, r12d
0x140085070  js      short loc_14008507F
0x140085072  mov     eax, r12d
0x140085075  mov     r12, [rsp+0C0h+var_30]
0x14008507d  jmp     short loc_140085004
0x14008507f  test    rdi, rdi
0x140085082  jnz     loc_14008523C
0x140085088  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x14008508f  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x140085094  mov     r8d, 7F7h
0x14008509a  mov     dl, 2
0x14008509c  mov     rcx, rbx
0x14008509f  call    SRV2_PERF_ENTER_EX
0x1400850a4  mov     rcx, [rsi+58h]; FileHandle
0x1400850a8  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1400850ac  mov     r9d, 28h ; '('; Length
0x1400850b2  mov     [rsp+0C0h+FileInformationClass], 4; FileInformationClass
0x1400850ba  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400850be  call    cs:__imp_NtQueryInformationFile
0x1400850c5  nop     dword ptr [rax+rax+00h]
0x1400850ca  mov     r12d, eax
0x1400850cd  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x1400850d4  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x1400850d9  xor     edx, edx
0x1400850db  mov     r8d, 80Ch
0x1400850e1  mov     rcx, rbx
0x1400850e4  call    SRV2_PERF_ENTER_EX
0x1400850e9  test    r12d, r12d
0x1400850ec  js      short loc_140085072
0x1400850ee  test    rdi, rdi
0x1400850f1  jnz     short loc_140085111
0x1400850f3  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x1400850fa  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x1400850ff  mov     r8d, 820h
0x140085105  mov     dl, 2
0x140085107  mov     rcx, rbx
0x14008510a  call    SRV2_PERF_ENTER_EX
0x14008510f  jmp     short loc_14008515E
0x140085111  cmp     dword ptr [rdi], 28h ; '('
0x140085114  jbe     short loc_1400850F3
0x140085116  mov     rdi, [rdi+28h]
0x14008511a  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140085121  mov     r8d, 820h
0x140085127  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x14008512c  mov     dl, 2
0x14008512e  mov     rcx, rbx
0x140085131  call    SRV2_PERF_ENTER_EX
0x140085136  test    rdi, rdi
0x140085139  jz      short loc_14008515E
0x14008513b  mov     rcx, [rsi+60h]
0x14008513f  lea     r9, [rbp+57h+IoStatusBlock]
0x140085143  lea     r8, [rbp+57h+var_80]
0x140085147  mov     qword ptr [rsp+0C0h+FileInformationClass], r14
0x14008514c  mov     dl, 1
0x14008514e  mov     rax, rdi
0x140085151  call    _guard_dispatch_icall
0x140085156  test    al, al
0x140085158  jnz     loc_140085247
0x14008515e  mov     rcx, [rsi+58h]; FileHandle
0x140085162  lea     r8, [rbp+57h+var_80]; FileInformation
0x140085166  mov     r9d, 18h; Length
0x14008516c  mov     [rsp+0C0h+FileInformationClass], 5; FileInformationClass
0x140085174  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140085178  call    cs:__imp_NtQueryInformationFile
0x14008517f  nop     dword ptr [rax+rax+00h]
0x140085184  mov     r12d, eax
0x140085187  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x14008518e  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x140085193  xor     edx, edx
0x140085195  mov     r8d, 835h
0x14008519b  mov     rcx, rbx
0x14008519e  call    SRV2_PERF_ENTER_EX
0x1400851a3  test    r12d, r12d
0x1400851a6  js      loc_140085072
0x1400851ac  mov     rax, qword ptr [rbp+57h+FileInformation]
0x1400851b0  mov     [r15], rax
0x1400851b3  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x1400851b7  mov     [r15+8], rax
0x1400851bb  mov     rax, qword ptr [rbp+57h+var_58]
0x1400851bf  mov     [r15+10h], rax
0x1400851c3  mov     rax, qword ptr [rbp+57h+var_58+8]
0x1400851c7  mov     [r15+18h], rax
0x1400851cb  mov     rax, qword ptr [rbp+57h+var_80]
0x1400851cf  mov     [r15+20h], rax
0x1400851d3  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1400851d7  mov     [r15+28h], rax
0x1400851db  mov     eax, dword ptr [rbp+57h+var_48]
0x1400851de  mov     [r15+30h], eax
0x1400851e2  jmp     loc_140085072
0x1400851e7  mov     r12, [rdi+20h]
0x1400851eb  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x1400851f2  mov     r8d, 7F7h
0x1400851f8  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x1400851fd  mov     dl, 2
0x1400851ff  mov     rcx, rbx
0x140085202  call    SRV2_PERF_ENTER_EX
0x140085207  test    r12, r12
0x14008520a  jz      loc_1400850A4
0x140085210  mov     rcx, [rsi+60h]
0x140085214  lea     r9, [rbp+57h+IoStatusBlock]
0x140085218  lea     r8, [rbp+57h+FileInformation]
0x14008521c  mov     qword ptr [rsp+0C0h+FileInformationClass], r14
0x140085221  mov     dl, 1
0x140085223  mov     rax, r12
0x140085226  call    _guard_dispatch_icall
0x14008522b  test    al, al
0x14008522d  jz      loc_1400850A4
0x140085233  mov     r12d, dword ptr [rbp+57h+IoStatusBlock]
0x140085237  jmp     loc_1400850CD
0x14008523c  cmp     dword ptr [rdi], 20h ; ' '
0x14008523f  jbe     loc_140085088
0x140085245  jmp     short loc_1400851E7
0x140085247  mov     r12d, dword ptr [rbp+57h+IoStatusBlock]
0x14008524b  jmp     loc_140085187
```
