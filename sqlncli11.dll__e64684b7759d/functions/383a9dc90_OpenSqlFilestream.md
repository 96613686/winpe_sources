# OpenSqlFilestream

- ea: `0x383a9dc90`
- end: `0x383a9e0e2`
- name: `OpenSqlFilestream`
- size: `1106`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x3838434c0`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x383a9d460`
- `0x383a9d6c0`
- `0x383a9dc90`

## import_xrefs

- `MSVCR100!free` at `0x383a9e08a`
- `MSVCR100!free` at `0x383a9e095`
- `MSVCR100!free` at `0x383a9e08a`
- `MSVCR100!free` at `0x383a9e095`
- `ntdll!RtlNtStatusToDosError` at `0x383a9e003`
- `ntdll!RtlNtStatusToDosError` at `0x383a9e003`
- `ntdll!NtCreateFile` at `0x383a9df98`
- `ntdll!NtCreateFile` at `0x383a9df98`
- `KERNEL32!GetLastError` at `0x383a9e056`
- `KERNEL32!GetLastError` at `0x383a9e056`
- `KERNEL32!SetLastError` at `0x383a9e00b`
- `KERNEL32!SetLastError` at `0x383a9e00b`

## pseudocode

```c
void *__fastcall OpenSqlFilestream(
        unsigned __int16 *a1,
        unsigned int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned __int64 a5,
        union _LARGE_INTEGER *a6)
{
  char v7; // cl
  NTSTATUS v10; // ebx
  wchar_t *v11; // r8
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int v14; // r14d
  ULONG ShareAccess; // r15d
  ULONG CreateDisposition; // r12d
  ULONG CreateOptions; // edi
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r9
  ULONG v22; // eax
  void *v23; // rbx
  void *FileHandle; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-98h] BYREF
  PVOID EaBuffer; // [rsp+78h] [rbp-90h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h]
  PLARGE_INTEGER AllocationSize; // [rsp+88h] [rbp-80h]
  unsigned __int16 *v30; // [rsp+90h] [rbp-78h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int8 *v32; // [rsp+A8h] [rbp-60h]
  struct _UNICODE_STRING v33; // [rsp+B0h] [rbp-58h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v35; // [rsp+F0h] [rbp-18h] BYREF
  __int16 v36; // [rsp+F8h] [rbp-10h]

  v30 = a1;
  v7 = bidGblFlags;
  v32 = a4;
  AllocationSize = a6;
  v26 = -1;
  if ( (bidGblFlags & 4) != 0 )
  {
    if ( off_383B4AD40[0] )
    {
      bidScopeEnterW(&v26, off_383B4AD40[0], a1, a2);
      a4 = v32;
    }
    v7 = bidGblFlags;
  }
  FileHandle = (void *)-1LL;
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  EaBuffer = 0;
  v28 = 0;
  v33.Buffer = 0;
  if ( !a1 )
  {
    v10 = -1073741811;
    if ( (v7 & 2) != 0 && off_383B4A1E8[0] )
    {
      v11 = off_383B4A1E8[0];
      v12 = 481280;
LABEL_49:
      v21 = (unsigned int)v10;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  if ( !a4 || a5 < 0x10 )
  {
    v10 = -1073741811;
    if ( (v7 & 2) != 0 && off_383B4A250[0] )
    {
      v11 = off_383B4A250[0];
      v12 = 493568;
      goto LABEL_49;
    }
    goto LABEL_51;
  }
  if ( !a2 )
  {
    v14 = 1;
    CreateDisposition = 1;
    ShareAccess = 7;
LABEL_20:
    if ( (a3 & 0xFFFFFFE0) != 0 )
    {
      v10 = -1073741811;
      if ( (v7 & 2) != 0 && off_383B4A228[0] )
      {
        v11 = off_383B4A228[0];
        v12 = 538624;
        goto LABEL_49;
      }
    }
    else
    {
      CreateOptions = 0;
      if ( (a3 & 2) != 0 )
        CreateOptions = 8;
      if ( (a3 & 4) == 0 )
        CreateOptions |= 2u;
      if ( (a3 & 1) == 0 )
        CreateOptions |= 0x20u;
      if ( (a3 & 8) != 0 )
        CreateOptions |= 4u;
      if ( (a3 & 0x10) != 0 )
        CreateOptions |= 0x800u;
      v18 = FilestreamTransactionContextEaBuffer::InitializeEaBuffer(
              (FilestreamTransactionContextEaBuffer *)&EaBuffer,
              a4,
              a5);
      v10 = v18;
      if ( v18 >= 0 )
      {
        v10 = FilestreamNtPath::InitializeNtPath(&v33, v30, v19, v20);
        if ( v10 >= 0 )
        {
          ObjectAttributes.ObjectName = &v33;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.SecurityQualityOfService = &v35;
          ObjectAttributes.SecurityDescriptor = 0;
          v36 = 0;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 64;
          v35 = 12;
          v10 = NtCreateFile(
                  &FileHandle,
                  v14 | 0x100080,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  AllocationSize,
                  0,
                  ShareAccess,
                  CreateDisposition,
                  CreateOptions,
                  EaBuffer,
                  v28);
          if ( v10 < 0 )
          {
            FileHandle = (void *)-1LL;
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_383B4A210[0] )
              {
                v11 = off_383B4A210[0];
                v12 = 630784;
                goto LABEL_49;
              }
            }
          }
        }
        else if ( (bidGblFlags & 2) != 0 && off_383B4A258[0] )
        {
          v11 = off_383B4A258[0];
          v12 = 586752;
          goto LABEL_49;
        }
      }
      else if ( (bidGblFlags & 2) != 0 && off_383B4A230[0] )
      {
        v11 = off_383B4A230[0];
        v21 = (unsigned int)v18;
        v12 = 577536;
LABEL_50:
        bidTraceW(off_383B43530[0], v12, v11, v21);
        goto LABEL_51;
      }
    }
    goto LABEL_51;
  }
  v13 = a2 - 1;
  if ( !v13 )
  {
    v14 = 2;
    ShareAccess = 5;
    CreateDisposition = 4;
    goto LABEL_20;
  }
  if ( v13 == 1 )
  {
    v14 = 3;
    ShareAccess = 5;
    CreateDisposition = 4;
    goto LABEL_20;
  }
  v10 = -1073741811;
  if ( (v7 & 2) != 0 && off_383B4A268[0] )
  {
    v11 = off_383B4A268[0];
    v12 = 527360;
    goto LABEL_49;
  }
LABEL_51:
  v22 = RtlNtStatusToDosError(v10);
  SetLastError(v22);
  if ( (bidGblFlags & 2) != 0 && off_383B4A200[0] )
  {
    GetLastError();
    bidTraceW(off_383B43530[0], 640000, off_383B4A200[0], FileHandle);
  }
  v23 = FileHandle;
  free(v33.Buffer);
  free(EaBuffer);
  if ( v26 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return v23;
}

```

## disassembly

```asm
0x383a9dc90  mov     r11, rsp
0x383a9dc93  push    rbp
0x383a9dc94  push    rbx
0x383a9dc95  lea     rbp, [r11-48h]
0x383a9dc99  sub     rsp, 138h
0x383a9dca0  mov     rax, cs:__security_cookie
0x383a9dca7  xor     rax, rsp
0x383a9dcaa  mov     [rbp+40h+var_48], rax
0x383a9dcae  mov     [r11-18h], rsi
0x383a9dcb2  mov     [r11-20h], rdi
0x383a9dcb6  mov     [rbp+40h+var_B8], rcx
0x383a9dcba  mov     rdi, rcx
0x383a9dcbd  mov     ecx, cs:_bidGblFlags
0x383a9dcc3  mov     ebx, edx
0x383a9dcc5  mov     rdx, [rbp+40h+arg_28]
0x383a9dcc9  mov     esi, r8d
0x383a9dccc  xor     r8d, r8d
0x383a9dccf  mov     [r11-30h], r13
0x383a9dcd3  mov     r13, [rbp+40h+arg_20]
0x383a9dcd7  mov     [rbp+40h+var_A0], r9
0x383a9dcdb  mov     [rbp+40h+var_C0], rdx
0x383a9dcdf  mov     [rsp+140h+var_D8], 0FFFFFFFFFFFFFFFFh
0x383a9dce8  test    cl, 4
0x383a9dceb  jz      short loc_383A9DD36
0x383a9dced  mov     rax, cs:off_383B4AD40; "<OpenSqlFilestream|API>  '%s' %d %d %Id"...
0x383a9dcf4  test    rax, rax
0x383a9dcf7  jz      short loc_383A9DD30
0x383a9dcf9  mov     eax, r8d
0x383a9dcfc  test    rdx, rdx
0x383a9dcff  jz      short loc_383A9DD04
0x383a9dd01  mov     rax, [rdx]
0x383a9dd04  mov     rdx, cs:off_383B4AD40; "<OpenSqlFilestream|API>  '%s' %d %d %Id"...
0x383a9dd0b  mov     qword ptr [rsp+140h+ShareAccess], rax
0x383a9dd10  lea     rcx, [rsp+140h+var_D8]
0x383a9dd15  mov     r9d, ebx
0x383a9dd18  mov     r8, rdi
0x383a9dd1b  mov     qword ptr [rsp+140h+FileAttributes], r13
0x383a9dd20  mov     dword ptr [rsp+140h+AllocationSize], esi
0x383a9dd24  call    _bidScopeEnterW
0x383a9dd29  mov     r9, [rbp+40h+var_A0]
0x383a9dd2d  xor     r8d, r8d
0x383a9dd30  mov     ecx, cs:_bidGblFlags
0x383a9dd36  xor     eax, eax
0x383a9dd38  mov     [rsp+140h+var_20], r12
0x383a9dd40  mov     [rsp+140h+var_30], r14
0x383a9dd48  mov     [rsp+140h+var_38], r15
0x383a9dd50  mov     [rsp+140h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x383a9dd59  mov     qword ptr [rbp+40h+IoStatusBlock], 0
0x383a9dd61  mov     [rbp+40h+IoStatusBlock.Information], rax
0x383a9dd65  mov     [rsp+140h+var_D0], r8
0x383a9dd6a  mov     [rsp+140h+var_C8], r8
0x383a9dd6f  mov     [rbp+40h+var_98.Buffer], r8
0x383a9dd73  test    rdi, rdi
0x383a9dd76  jnz     short loc_383A9DDA7
0x383a9dd78  mov     ebx, 0C000000Dh
0x383a9dd7d  test    cl, 2
0x383a9dd80  jz      loc_383A9E001
0x383a9dd86  mov     rax, cs:off_383B4A1E8; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dd8d  test    rax, rax
0x383a9dd90  jz      loc_383A9E001
0x383a9dd96  mov     r8, cs:off_383B4A1E8; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dd9d  mov     edx, 75800h
0x383a9dda2  jmp     loc_383A9DFF2
0x383a9dda7  test    r9, r9
0x383a9ddaa  jz      loc_383A9DFD0
0x383a9ddb0  cmp     r13, 10h
0x383a9ddb4  jb      loc_383A9DFD0
0x383a9ddba  test    ebx, ebx
0x383a9ddbc  jz      short loc_383A9DE15
0x383a9ddbe  dec     ebx
0x383a9ddc0  jz      short loc_383A9DE05
0x383a9ddc2  dec     ebx
0x383a9ddc4  jz      short loc_383A9DDF5
0x383a9ddc6  mov     ebx, 0C000000Dh
0x383a9ddcb  test    cl, 2
0x383a9ddce  jz      loc_383A9E001
0x383a9ddd4  mov     rax, cs:off_383B4A268; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dddb  test    rax, rax
0x383a9ddde  jz      loc_383A9E001
0x383a9dde4  mov     r8, cs:off_383B4A268; "<OpenSqlFilestream|ERR>  %0X"
0x383a9ddeb  mov     edx, 80C00h
0x383a9ddf0  jmp     loc_383A9DFF2
0x383a9ddf5  mov     r14d, 3
0x383a9ddfb  lea     r15d, [r14+2]
0x383a9ddff  lea     r12d, [r14+1]
0x383a9de03  jmp     short loc_383A9DE22
0x383a9de05  mov     r14d, 2
0x383a9de0b  lea     r15d, [r14+3]
0x383a9de0f  lea     r12d, [r14+2]
0x383a9de13  jmp     short loc_383A9DE22
0x383a9de15  mov     r14d, 1
0x383a9de1b  mov     r12d, r14d
0x383a9de1e  lea     r15d, [r14+6]
0x383a9de22  test    esi, 0FFFFFFE0h
0x383a9de28  jz      short loc_383A9DE59
0x383a9de2a  mov     ebx, 0C000000Dh
0x383a9de2f  test    cl, 2
0x383a9de32  jz      loc_383A9E001
0x383a9de38  mov     rax, cs:off_383B4A228; "<OpenSqlFilestream|ERR>  %0X"
0x383a9de3f  test    rax, rax
0x383a9de42  jz      loc_383A9E001
0x383a9de48  mov     r8, cs:off_383B4A228; "<OpenSqlFilestream|ERR>  %0X"
0x383a9de4f  mov     edx, 83800h
0x383a9de54  jmp     loc_383A9DFF2
0x383a9de59  test    sil, 2
0x383a9de5d  mov     eax, 8
0x383a9de62  mov     edi, r8d
0x383a9de65  cmovnz  edi, eax
0x383a9de68  mov     eax, esi
0x383a9de6a  and     eax, 4
0x383a9de6d  test    al, al
0x383a9de6f  jnz     short loc_383A9DE74
0x383a9de71  or      edi, 2
0x383a9de74  mov     eax, esi
0x383a9de76  and     eax, 1
0x383a9de79  test    al, al
0x383a9de7b  jnz     short loc_383A9DE80
0x383a9de7d  or      edi, 20h
0x383a9de80  mov     eax, esi
0x383a9de82  and     eax, 8
0x383a9de85  test    al, al
0x383a9de87  jz      short loc_383A9DE8C
0x383a9de89  or      edi, 4
0x383a9de8c  and     esi, 10h
0x383a9de8f  test    sil, sil
0x383a9de92  jz      short loc_383A9DE98
0x383a9de94  bts     edi, 0Bh
0x383a9de98  lea     rcx, [rsp+140h+var_D0]; this
0x383a9de9d  mov     r8, r13; __int64
0x383a9dea0  mov     rdx, r9; unsigned __int8 *
0x383a9dea3  call    ?InitializeEaBuffer@FilestreamTransactionContextEaBuffer@@QEAAJPEAE_J@Z; FilestreamTransactionContextEaBuffer::InitializeEaBuffer(uchar *,__int64)
0x383a9dea8  mov     ebx, eax
0x383a9deaa  test    eax, eax
0x383a9deac  jns     short loc_383A9DEDF
0x383a9deae  test    byte ptr cs:_bidGblFlags, 2
0x383a9deb5  jz      loc_383A9E001
0x383a9debb  mov     rcx, cs:off_383B4A230; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dec2  test    rcx, rcx
0x383a9dec5  jz      loc_383A9E001
0x383a9decb  mov     r8, cs:off_383B4A230; "<OpenSqlFilestream|ERR>  %0X"
0x383a9ded2  mov     r9d, eax
0x383a9ded5  mov     edx, 8D000h
0x383a9deda  jmp     loc_383A9DFF5
0x383a9dedf  mov     rdx, [rbp+40h+var_B8]; unsigned __int16 *
0x383a9dee3  lea     rcx, [rbp+40h+var_98]; this
0x383a9dee7  call    ?InitializeNtPath@FilestreamNtPath@@QEAAJPEBG@Z; FilestreamNtPath::InitializeNtPath(ushort const *)
0x383a9deec  mov     ebx, eax
0x383a9deee  test    eax, eax
0x383a9def0  jns     short loc_383A9DF20
0x383a9def2  test    byte ptr cs:_bidGblFlags, 2
0x383a9def9  jz      loc_383A9E001
0x383a9deff  mov     rax, cs:off_383B4A258; "<OpenSqlFilestream|ERR>  %0X"
0x383a9df06  test    rax, rax
0x383a9df09  jz      loc_383A9E001
0x383a9df0f  mov     r8, cs:off_383B4A258; "<OpenSqlFilestream|ERR>  %0X"
0x383a9df16  mov     edx, 8F400h
0x383a9df1b  jmp     loc_383A9DFF2
0x383a9df20  xor     ecx, ecx
0x383a9df22  lea     rax, [rbp+40h+var_98]
0x383a9df26  or      r14d, 100080h
0x383a9df2d  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x383a9df31  lea     rax, [rbp+40h+var_58]
0x383a9df35  mov     [rbp+40h+ObjectAttributes.RootDirectory], rcx
0x383a9df39  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x383a9df3d  mov     eax, dword ptr [rsp+140h+var_C8]
0x383a9df41  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rcx
0x383a9df45  mov     [rsp+50h], eax; EaLength
0x383a9df49  mov     rax, [rsp+140h+var_D0]
0x383a9df4e  mov     [rbp+40h+var_50], cx
0x383a9df52  mov     [rsp+140h+EaBuffer], rax; EaBuffer
0x383a9df57  mov     rax, [rbp+40h+var_C0]
0x383a9df5b  mov     [rsp+140h+CreateOptions], edi; CreateOptions
0x383a9df5f  mov     [rsp+140h+CreateDisposition], r12d; CreateDisposition
0x383a9df64  mov     [rsp+140h+ShareAccess], r15d; ShareAccess
0x383a9df69  mov     [rsp+140h+FileAttributes], ecx; FileAttributes
0x383a9df6d  lea     rcx, [rsp+140h+FileHandle]; FileHandle
0x383a9df72  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x383a9df76  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x383a9df7a  mov     edx, r14d; DesiredAccess
0x383a9df7d  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x383a9df84  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x383a9df8b  mov     [rbp+40h+var_58], 0Ch
0x383a9df93  mov     [rsp+140h+AllocationSize], rax; AllocationSize
0x383a9df98  call    cs:__imp_NtCreateFile
0x383a9df9e  mov     ebx, eax
0x383a9dfa0  test    eax, eax
0x383a9dfa2  jns     short loc_383A9E001
0x383a9dfa4  test    byte ptr cs:_bidGblFlags, 2
0x383a9dfab  mov     [rsp+140h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x383a9dfb4  jz      short loc_383A9E001
0x383a9dfb6  mov     rax, cs:off_383B4A210; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dfbd  test    rax, rax
0x383a9dfc0  jz      short loc_383A9E001
0x383a9dfc2  mov     r8, cs:off_383B4A210; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dfc9  mov     edx, 9A000h
0x383a9dfce  jmp     short loc_383A9DFF2
0x383a9dfd0  mov     ebx, 0C000000Dh
0x383a9dfd5  test    cl, 2
0x383a9dfd8  jz      short loc_383A9E001
0x383a9dfda  mov     rax, cs:off_383B4A250; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dfe1  test    rax, rax
0x383a9dfe4  jz      short loc_383A9E001
0x383a9dfe6  mov     r8, cs:off_383B4A250; "<OpenSqlFilestream|ERR>  %0X"
0x383a9dfed  mov     edx, 78800h
0x383a9dff2  mov     r9d, ebx
0x383a9dff5  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9dffc  call    _bidTraceW
0x383a9e001  mov     ecx, ebx; Status
0x383a9e003  call    cs:__imp_RtlNtStatusToDosError
0x383a9e009  mov     ecx, eax; dwErrCode
0x383a9e00b  call    cs:__imp_SetLastError
0x383a9e011  test    byte ptr cs:_bidGblFlags, 2
0x383a9e018  mov     r15, [rsp+140h+var_38]
0x383a9e020  mov     r14, [rsp+140h+var_30]
0x383a9e028  mov     r13, [rsp+140h+var_28]
0x383a9e030  mov     r12, [rsp+140h+var_20]
0x383a9e038  mov     rdi, [rsp+140h+var_18]
0x383a9e040  mov     rsi, [rsp+130h]
0x383a9e048  jz      short loc_383A9E081
0x383a9e04a  mov     rax, cs:off_383B4A200; "<OpenSqlFilestream|API|RET>  %p %0X %d"
0x383a9e051  test    rax, rax
0x383a9e054  jz      short loc_383A9E081
0x383a9e056  call    cs:__imp_GetLastError
0x383a9e05c  mov     r8, cs:off_383B4A200; "<OpenSqlFilestream|API|RET>  %p %0X %d"
0x383a9e063  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9e06a  mov     r9, [rsp+140h+FileHandle]
0x383a9e06f  mov     [rsp+140h+FileAttributes], eax
0x383a9e073  mov     edx, 9C400h
0x383a9e078  mov     dword ptr [rsp+140h+AllocationSize], ebx
0x383a9e07c  call    _bidTraceW
0x383a9e081  mov     rcx, [rbp+40h+var_98.Buffer]; Block
0x383a9e085  mov     rbx, [rsp+140h+FileHandle]
0x383a9e08a  call    cs:__imp_free
0x383a9e090  mov     rcx, [rsp+140h+var_D0]; Block
0x383a9e095  call    cs:__imp_free
0x383a9e09b  cmp     [rsp+140h+var_D8], 0FFFFFFFFFFFFFFFFh
0x383a9e0a1  jz      short loc_383A9E0C9
0x383a9e0a3  test    byte ptr cs:_bidGblFlags, 4
0x383a9e0aa  jz      short loc_383A9E0C9
0x383a9e0ac  mov     rcx, cs:_bidID
0x383a9e0b3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a9e0b7  jz      short loc_383A9E0C9
0x383a9e0b9  lea     r9, [rsp+140h+var_D8]
0x383a9e0be  xor     r8d, r8d
0x383a9e0c1  xor     edx, edx
0x383a9e0c3  call    cs:off_383B15058
0x383a9e0c9  mov     rax, rbx
0x383a9e0cc  mov     rcx, [rbp+40h+var_48]
0x383a9e0d0  xor     rcx, rsp; StackCookie
0x383a9e0d3  call    __security_check_cookie
0x383a9e0d8  add     rsp, 138h
0x383a9e0df  pop     rbx
0x383a9e0e0  pop     rbp
0x383a9e0e1  retn
```
