# Smb2QueryNetworkOpenInfo

- ea: `0x140084f80`
- end: `0x1400852a0`
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
- `0x140084f80`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140084fcd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140084fcd`
- `ntoskrnl!NtQueryInformationFile` at `0x140085092`
- `ntoskrnl!NtQueryInformationFile` at `0x14008510e`
- `ntoskrnl!NtQueryInformationFile` at `0x1400851c8`
- `ntoskrnl!NtQueryInformationFile` at `0x140085092`
- `ntoskrnl!NtQueryInformationFile` at `0x14008510e`
- `ntoskrnl!NtQueryInformationFile` at `0x1400851c8`

## string_xrefs

- `0x140084fe5`: `Smb2QueryNetworkOpenInfo`
- `0x140085035`: `Smb2QueryNetworkOpenInfo`
- `0x14008509e`: `Smb2QueryNetworkOpenInfo`
- `0x1400850d8`: `Smb2QueryNetworkOpenInfo`
- `0x14008511d`: `Smb2QueryNetworkOpenInfo`
- `0x140085143`: `Smb2QueryNetworkOpenInfo`
- `0x14008516a`: `Smb2QueryNetworkOpenInfo`
- `0x1400851d7`: `Smb2QueryNetworkOpenInfo`
- `0x14008523b`: `Smb2QueryNetworkOpenInfo`

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
0x140084f80  push    rbp
0x140084f82  push    rbx
0x140084f83  push    rsi
0x140084f84  push    rdi
0x140084f85  push    r14
0x140084f87  push    r15
0x140084f89  lea     rbp, [rsp-2Fh]
0x140084f8e  sub     rsp, 98h
0x140084f95  mov     rax, cs:__security_cookie
0x140084f9c  xor     rax, rsp
0x140084f9f  mov     [rbp+57h+var_40], rax
0x140084fa3  xorps   xmm0, xmm0
0x140084fa6  xor     eax, eax
0x140084fa8  mov     rbx, rcx
0x140084fab  mov     [rbp+57h+var_48], rax
0x140084faf  mov     rcx, [rdx+60h]; FileObject
0x140084fb3  mov     r15, r8
0x140084fb6  movups  [rbp+57h+FileInformation], xmm0
0x140084fba  mov     [rbp+57h+var_70], rax
0x140084fbe  mov     rsi, rdx
0x140084fc1  movups  [rbp+57h+var_58], xmm0
0x140084fc5  movups  [rbp+57h+var_80], xmm0
0x140084fc9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140084fcd  call    cs:__imp_IoGetRelatedDeviceObject
0x140084fd4  nop     dword ptr [rax+rax+00h]
0x140084fd9  add     rbx, 248h
0x140084fe0  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x140084fe5  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140084fec  mov     r8d, 7C0h
0x140084ff2  mov     dl, 2
0x140084ff4  mov     r14, rax
0x140084ff7  mov     rcx, [rax+8]
0x140084ffb  mov     rdi, [rcx+50h]
0x140084fff  mov     rcx, rbx
0x140085002  call    SRV2_PERF_ENTER_EX
0x140085007  test    rdi, rdi
0x14008500a  jz      short loc_140085071
0x14008500c  cmp     dword ptr [rdi], 70h ; 'p'
0x14008500f  jbe     short loc_140085071
0x140085011  mov     rax, [rdi+70h]
0x140085015  test    rax, rax
0x140085018  jz      short loc_140085071
0x14008501a  mov     rcx, [rsi+60h]
0x14008501e  lea     r9, [rbp+57h+IoStatusBlock]
0x140085022  mov     r8, r15
0x140085025  mov     qword ptr [rsp+0C0h+FileInformationClass], r14
0x14008502a  mov     dl, 1
0x14008502c  call    _guard_dispatch_icall
0x140085031  test    al, al
0x140085033  jz      short loc_140085071
0x140085035  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x14008503c  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x140085041  xor     edx, edx
0x140085043  mov     r8d, 7CFh
0x140085049  mov     rcx, rbx
0x14008504c  call    SRV2_PERF_ENTER_EX
0x140085051  mov     eax, dword ptr [rbp+57h+IoStatusBlock]
0x140085054  mov     rcx, [rbp+57h+var_40]
0x140085058  xor     rcx, rsp; StackCookie
0x14008505b  call    __security_check_cookie
0x140085060  add     rsp, 98h
0x140085067  pop     r15
0x140085069  pop     r14
0x14008506b  pop     rdi
0x14008506c  pop     rsi
0x14008506d  pop     rbx
0x14008506e  pop     rbp
0x14008506f  retn
0x140085071  mov     rcx, [rsi+58h]; FileHandle
0x140085075  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140085079  mov     r9d, 38h ; '8'; Length
0x14008507f  mov     [rsp+0C0h+var_30], r12
0x140085087  mov     r8, r15; FileInformation
0x14008508a  mov     [rsp+0C0h+FileInformationClass], 22h ; '"'; FileInformationClass
0x140085092  call    cs:__imp_NtQueryInformationFile
0x140085099  nop     dword ptr [rax+rax+00h]
0x14008509e  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x1400850a5  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x1400850aa  xor     edx, edx
0x1400850ac  mov     r8d, 7DFh
0x1400850b2  mov     rcx, rbx
0x1400850b5  mov     r12d, eax
0x1400850b8  call    SRV2_PERF_ENTER_EX
0x1400850bd  test    r12d, r12d
0x1400850c0  js      short loc_1400850CF
0x1400850c2  mov     eax, r12d
0x1400850c5  mov     r12, [rsp+0C0h+var_30]
0x1400850cd  jmp     short loc_140085054
0x1400850cf  test    rdi, rdi
0x1400850d2  jnz     loc_14008528C
0x1400850d8  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x1400850df  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x1400850e4  mov     r8d, 7F7h
0x1400850ea  mov     dl, 2
0x1400850ec  mov     rcx, rbx
0x1400850ef  call    SRV2_PERF_ENTER_EX
0x1400850f4  mov     rcx, [rsi+58h]; FileHandle
0x1400850f8  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1400850fc  mov     r9d, 28h ; '('; Length
0x140085102  mov     [rsp+0C0h+FileInformationClass], 4; FileInformationClass
0x14008510a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14008510e  call    cs:__imp_NtQueryInformationFile
0x140085115  nop     dword ptr [rax+rax+00h]
0x14008511a  mov     r12d, eax
0x14008511d  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140085124  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x140085129  xor     edx, edx
0x14008512b  mov     r8d, 80Ch
0x140085131  mov     rcx, rbx
0x140085134  call    SRV2_PERF_ENTER_EX
0x140085139  test    r12d, r12d
0x14008513c  js      short loc_1400850C2
0x14008513e  test    rdi, rdi
0x140085141  jnz     short loc_140085161
0x140085143  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x14008514a  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x14008514f  mov     r8d, 820h
0x140085155  mov     dl, 2
0x140085157  mov     rcx, rbx
0x14008515a  call    SRV2_PERF_ENTER_EX
0x14008515f  jmp     short loc_1400851AE
0x140085161  cmp     dword ptr [rdi], 28h ; '('
0x140085164  jbe     short loc_140085143
0x140085166  mov     rdi, [rdi+28h]
0x14008516a  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140085171  mov     r8d, 820h
0x140085177  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x14008517c  mov     dl, 2
0x14008517e  mov     rcx, rbx
0x140085181  call    SRV2_PERF_ENTER_EX
0x140085186  test    rdi, rdi
0x140085189  jz      short loc_1400851AE
0x14008518b  mov     rcx, [rsi+60h]
0x14008518f  lea     r9, [rbp+57h+IoStatusBlock]
0x140085193  lea     r8, [rbp+57h+var_80]
0x140085197  mov     qword ptr [rsp+0C0h+FileInformationClass], r14
0x14008519c  mov     dl, 1
0x14008519e  mov     rax, rdi
0x1400851a1  call    _guard_dispatch_icall
0x1400851a6  test    al, al
0x1400851a8  jnz     loc_140085297
0x1400851ae  mov     rcx, [rsi+58h]; FileHandle
0x1400851b2  lea     r8, [rbp+57h+var_80]; FileInformation
0x1400851b6  mov     r9d, 18h; Length
0x1400851bc  mov     [rsp+0C0h+FileInformationClass], 5; FileInformationClass
0x1400851c4  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400851c8  call    cs:__imp_NtQueryInformationFile
0x1400851cf  nop     dword ptr [rax+rax+00h]
0x1400851d4  mov     r12d, eax
0x1400851d7  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x1400851de  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x1400851e3  xor     edx, edx
0x1400851e5  mov     r8d, 835h
0x1400851eb  mov     rcx, rbx
0x1400851ee  call    SRV2_PERF_ENTER_EX
0x1400851f3  test    r12d, r12d
0x1400851f6  js      loc_1400850C2
0x1400851fc  mov     rax, qword ptr [rbp+57h+FileInformation]
0x140085200  mov     [r15], rax
0x140085203  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x140085207  mov     [r15+8], rax
0x14008520b  mov     rax, qword ptr [rbp+57h+var_58]
0x14008520f  mov     [r15+10h], rax
0x140085213  mov     rax, qword ptr [rbp+57h+var_58+8]
0x140085217  mov     [r15+18h], rax
0x14008521b  mov     rax, qword ptr [rbp+57h+var_80]
0x14008521f  mov     [r15+20h], rax
0x140085223  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140085227  mov     [r15+28h], rax
0x14008522b  mov     eax, dword ptr [rbp+57h+var_48]
0x14008522e  mov     [r15+30h], eax
0x140085232  jmp     loc_1400850C2
0x140085237  mov     r12, [rdi+20h]
0x14008523b  lea     r9, aSmb2querynetwo; "Smb2QueryNetworkOpenInfo"
0x140085242  mov     r8d, 7F7h
0x140085248  mov     byte ptr [rsp+0C0h+FileInformationClass], 1
0x14008524d  mov     dl, 2
0x14008524f  mov     rcx, rbx
0x140085252  call    SRV2_PERF_ENTER_EX
0x140085257  test    r12, r12
0x14008525a  jz      loc_1400850F4
0x140085260  mov     rcx, [rsi+60h]
0x140085264  lea     r9, [rbp+57h+IoStatusBlock]
0x140085268  lea     r8, [rbp+57h+FileInformation]
0x14008526c  mov     qword ptr [rsp+0C0h+FileInformationClass], r14
0x140085271  mov     dl, 1
0x140085273  mov     rax, r12
0x140085276  call    _guard_dispatch_icall
0x14008527b  test    al, al
0x14008527d  jz      loc_1400850F4
0x140085283  mov     r12d, dword ptr [rbp+57h+IoStatusBlock]
0x140085287  jmp     loc_14008511D
0x14008528c  cmp     dword ptr [rdi], 20h ; ' '
0x14008528f  jbe     loc_1400850D8
0x140085295  jmp     short loc_140085237
0x140085297  mov     r12d, dword ptr [rbp+57h+IoStatusBlock]
0x14008529b  jmp     loc_1400851D7
```
