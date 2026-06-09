# SmpGetDumpDestination

- ea: `0x140011d24`
- end: `0x140011f5e`
- name: `SmpGetDumpDestination`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011438`

## callees

- `0x140011ac4`
- `0x140011bb0`
- `0x140011d24`
- `0x140012078`
- `0x1400120f8`
- `0x140012320`
- `0x1400124b8`
- `0x140013fd8`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140011ea9`
- `ntdll!RtlInitUnicodeString` at `0x140011ea9`
- `ntdll!NtOpenFile` at `0x140011e34`
- `ntdll!NtOpenFile` at `0x140011e34`
- `ntdll!NtClose` at `0x140011e4f`
- `ntdll!NtClose` at `0x140011e4f`
- `ntdll!RtlCompareMemory` at `0x140011f00`
- `ntdll!RtlCompareMemory` at `0x140011f00`
- `ntdll!RtlCreateUnicodeString` at `0x140011e8e`
- `ntdll!RtlCreateUnicodeString` at `0x140011e8e`

## pseudocode

```c
__int64 __fastcall SmpGetDumpDestination(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        PUNICODE_STRING DestinationString)
{
  bool v5; // zf
  __int64 v9; // r15
  __int64 result; // rax
  unsigned __int64 v11; // r14
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __m128i v14; // xmm1
  WCHAR *v15; // rbx
  unsigned __int16 v16; // r14
  void *FileHandle; // [rsp+38h] [rbp-69h] BYREF
  struct _UNICODE_STRING v18; // [rsp+40h] [rbp-61h] BYREF
  __int64 v19; // [rsp+50h] [rbp-51h] BYREF
  struct _UNICODE_STRING v20; // [rsp+58h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-9h] BYREF
  WCHAR SourceString[4]; // [rsp+A8h] [rbp+7h] BYREF

  v5 = *(_DWORD *)(a1 + 3992) == 4;
  *(_QWORD *)&v18.Length = 0;
  v19 = 0;
  wcscpy(SourceString, L"?:\\");
  v9 = 0;
  v20 = 0;
  if ( !v5 )
  {
    result = SmpQuerySameVolume(a3);
    if ( (int)result < 0 )
      return result;
    if ( *(_DWORD *)(a2 + 16) )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      FileHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      IoStatusBlock = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)a2;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u) >= 0 )
      {
        SmpQueryFileSize(FileHandle, &v19);
        NtClose(FileHandle);
        v9 = v19;
      }
    }
  }
  v11 = *(_QWORD *)(a1 + 4000);
  result = SmpQueryVolumeFreeSpace(a2, &v18);
  if ( (int)result >= 0 )
  {
    if ( v11 >= v9 + *(_QWORD *)&v18.Length )
    {
      v14 = *(__m128i *)a2;
      v15 = *(WCHAR **)(a2 + 8);
      v18 = *(struct _UNICODE_STRING *)a2;
      if ( v15 )
      {
        v16 = _mm_cvtsi128_si32(v14);
        if ( v16 >= 8u && RtlCompareMemory(v15, L"\\??\\", 8u) == 8 )
        {
          v18.Buffer = v15 + 4;
          v18.Length = v16 - 8;
        }
      }
      SmpEventWriteString(v12, &v18);
      v13 = -1073741670;
    }
    else
    {
      RtlInitUnicodeString(&v20, SourceString);
      SourceString[0] = *(_WORD *)(*(_QWORD *)(a4 + 8) + 8LL);
      v13 = SmpCreateTempFile(&v20, L"DUMP", DestinationString);
    }
    *(_DWORD *)(a2 + 20) = 1;
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x140011d24  mov     [rsp-8+arg_0], rbx
0x140011d29  push    rbp
0x140011d2a  push    rsi
0x140011d2b  push    rdi
0x140011d2c  push    r12
0x140011d2e  push    r13
0x140011d30  push    r14
0x140011d32  push    r15
0x140011d34  lea     rbp, [rsp-1Fh]
0x140011d39  sub     rsp, 0C0h
0x140011d40  mov     rax, cs:__security_cookie
0x140011d47  xor     rax, rsp
0x140011d4a  mov     [rbp+4Fh+var_40], rax
0x140011d4e  mov     r12, [rbp+4Fh+DestinationString]
0x140011d52  xor     ebx, ebx
0x140011d54  cmp     dword ptr [rcx+0F98h], 4
0x140011d5b  xorps   xmm0, xmm0
0x140011d5e  mov     r13, r9
0x140011d61  mov     [rbp+4Fh+var_C0], bl
0x140011d64  mov     r10, r8
0x140011d67  mov     qword ptr [rbp+4Fh+var_B0], rbx
0x140011d6b  lea     eax, [rbx+3Fh]
0x140011d6e  mov     [rbp+4Fh+var_A0], rbx
0x140011d72  mov     [rbp+4Fh+SourceString], ax
0x140011d76  mov     rdi, rdx
0x140011d79  mov     eax, dword ptr cs:asc_140026F78+2; ":\\"
0x140011d7f  mov     r14, rcx
0x140011d82  mov     [rbp+4Fh+var_46], eax
0x140011d85  mov     r15d, ebx
0x140011d88  movzx   eax, word ptr cs:asc_140026F78+6; ""
0x140011d8f  mov     [rbp+4Fh+var_42], ax
0x140011d93  movups  xmmword ptr [rbp+4Fh+var_98.Length], xmm0
0x140011d97  jnz     short loc_140011DA1
0x140011d99  mov     sil, 1
0x140011d9c  jmp     loc_140011E59
0x140011da1  lea     r8, [rbp+4Fh+var_C0]
0x140011da5  mov     rcx, r10; FileHandle
0x140011da8  call    SmpQuerySameVolume
0x140011dad  test    eax, eax
0x140011daf  js      loc_140011F37
0x140011db5  mov     sil, 1
0x140011db8  cmp     [rbp+4Fh+var_C0], sil
0x140011dbc  jnz     short loc_140011DE6
0x140011dbe  mov     rcx, rdi
0x140011dc1  call    SmpQueryFileExists
0x140011dc6  test    al, al
0x140011dc8  jz      short loc_140011DD7
0x140011dca  cmp     [rdi+10h], ebx
0x140011dcd  jz      short loc_140011DDC
0x140011dcf  mov     rcx, rdi
0x140011dd2  call    SmpDeleteFile
0x140011dd7  mov     sil, bl
0x140011dda  jmp     short loc_140011E59
0x140011ddc  mov     eax, 0C0000001h
0x140011de1  jmp     loc_140011F37
0x140011de6  cmp     [rdi+10h], ebx
0x140011de9  jz      short loc_140011E59
0x140011deb  xorps   xmm0, xmm0
0x140011dee  mov     [rsp+0F0h+OpenOptions], 60h ; '`'; OpenOptions
0x140011df6  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x140011dfa  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x140011e02  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140011e06  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x140011e0e  mov     edx, 100080h; DesiredAccess
0x140011e13  mov     [rbp+4Fh+FileHandle], rbx
0x140011e17  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140011e1b  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rbx
0x140011e1f  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x140011e23  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rdi
0x140011e27  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140011e2c  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x140011e34  call    cs:__imp_NtOpenFile
0x140011e3a  test    eax, eax
0x140011e3c  js      short loc_140011E59
0x140011e3e  mov     rcx, [rbp+4Fh+FileHandle]
0x140011e42  lea     rdx, [rbp+4Fh+var_A0]
0x140011e46  call    SmpQueryFileSize
0x140011e4b  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x140011e4f  call    cs:__imp_NtClose
0x140011e55  mov     r15, [rbp+4Fh+var_A0]
0x140011e59  mov     r14, [r14+0FA0h]
0x140011e60  lea     rdx, [rbp+4Fh+var_B0]
0x140011e64  mov     rcx, rdi
0x140011e67  call    SmpQueryVolumeFreeSpace
0x140011e6c  mov     ebx, eax
0x140011e6e  test    eax, eax
0x140011e70  js      loc_140011F37
0x140011e76  mov     rdx, qword ptr [rbp+4Fh+var_B0]
0x140011e7a  add     rdx, r15
0x140011e7d  cmp     r14, rdx
0x140011e80  jnb     short loc_140011ED2
0x140011e82  test    sil, sil
0x140011e85  jnz     short loc_140011EA1
0x140011e87  mov     rdx, [rdi+8]; SourceString
0x140011e8b  mov     rcx, r12; DestinationString
0x140011e8e  call    cs:__imp_RtlCreateUnicodeString
0x140011e94  test    al, al
0x140011e96  jnz     loc_140011F2E
0x140011e9c  jmp     loc_140011F29
0x140011ea1  lea     rdx, [rbp+4Fh+SourceString]; SourceString
0x140011ea5  lea     rcx, [rbp+4Fh+var_98]; DestinationString
0x140011ea9  call    cs:__imp_RtlInitUnicodeString
0x140011eaf  mov     rax, [r13+8]
0x140011eb3  lea     rdx, aDump; "DUMP"
0x140011eba  mov     r8, r12
0x140011ebd  movzx   ecx, word ptr [rax+8]
0x140011ec1  mov     [rbp+4Fh+SourceString], cx
0x140011ec5  lea     rcx, [rbp+4Fh+var_98]
0x140011ec9  call    SmpCreateTempFile
0x140011ece  mov     ebx, eax
0x140011ed0  jmp     short loc_140011F2E
0x140011ed2  movups  xmm1, xmmword ptr [rdi]
0x140011ed5  mov     rbx, [rdi+8]
0x140011ed9  movups  [rbp+4Fh+var_B0], xmm1
0x140011edd  test    rbx, rbx
0x140011ee0  jz      short loc_140011F20
0x140011ee2  movd    r14d, xmm1
0x140011ee7  mov     r15d, 8
0x140011eed  cmp     r14w, r15w
0x140011ef1  jb      short loc_140011F20
0x140011ef3  mov     r8d, r15d; Length
0x140011ef6  lea     rdx, asc_140026F90; "\\??\\"
0x140011efd  mov     rcx, rbx; Source1
0x140011f00  call    cs:__imp_RtlCompareMemory
0x140011f06  cmp     rax, r15
0x140011f09  jnz     short loc_140011F20
0x140011f0b  add     rbx, r15
0x140011f0e  mov     eax, 0FFF8h
0x140011f13  add     r14w, ax
0x140011f17  mov     qword ptr [rbp+4Fh+var_B0+8], rbx
0x140011f1b  mov     word ptr [rbp+4Fh+var_B0], r14w
0x140011f20  lea     rdx, [rbp+4Fh+var_B0]
0x140011f24  call    SmpEventWriteString
0x140011f29  mov     ebx, 0C000009Ah
0x140011f2e  movzx   eax, sil
0x140011f32  mov     [rdi+14h], eax
0x140011f35  mov     eax, ebx
0x140011f37  mov     rcx, [rbp+4Fh+var_40]
0x140011f3b  xor     rcx, rsp; StackCookie
0x140011f3e  call    __security_check_cookie
0x140011f43  mov     rbx, [rsp+0F0h+arg_0]
0x140011f4b  add     rsp, 0C0h
0x140011f52  pop     r15
0x140011f54  pop     r14
0x140011f56  pop     r13
0x140011f58  pop     r12
0x140011f5a  pop     rdi
0x140011f5b  pop     rsi
0x140011f5c  pop     rbp
0x140011f5d  retn
```
