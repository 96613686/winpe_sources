# WofDeleteAlternateStream

- ea: `0x14000ac54`
- end: `0x14000adfb`
- name: `WofDeleteAlternateStream`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000ac34`
- `0x14003d9a0`

## callees

- `0x14000ac54`
- `0x140011560`
- `0x140039aa0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000adcb`
- `ntoskrnl!ObfDereferenceObject` at `0x14000adcb`
- `FLTMGR!FltQueryInformationFile` at `0x14000ad1e`
- `FLTMGR!FltQueryInformationFile` at `0x14000ad1e`
- `FLTMGR!FltSetInformationFile` at `0x14000acce`
- `FLTMGR!FltSetInformationFile` at `0x14000ad59`
- `FLTMGR!FltSetInformationFile` at `0x14000ad7f`
- `FLTMGR!FltSetInformationFile` at `0x14000adab`
- `FLTMGR!FltSetInformationFile` at `0x14000acce`
- `FLTMGR!FltSetInformationFile` at `0x14000ad59`
- `FLTMGR!FltSetInformationFile` at `0x14000ad7f`
- `FLTMGR!FltSetInformationFile` at `0x14000adab`
- `FLTMGR!FltClose` at `0x14000adbb`
- `FLTMGR!FltClose` at `0x14000adbb`

## pseudocode

```c
NTSTATUS __fastcall WofDeleteAlternateStream(__int64 a1, struct _FILE_OBJECT *a2, __int64 a3)
{
  NTSTATUS result; // eax
  struct _FLT_INSTANCE *v5; // rcx
  NTSTATUS v6; // esi
  struct _FLT_INSTANCE *v7; // rcx
  struct _FLT_INSTANCE *v8; // rcx
  NTSTATUS v9; // eax
  struct _FLT_INSTANCE *v10; // rcx
  __int64 FileInformationClass; // [rsp+28h] [rbp-19h]
  char FileInformation[8]; // [rsp+48h] [rbp+7h] BYREF
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp+Fh] BYREF
  ULONG LengthReturned; // [rsp+58h] [rbp+17h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp+1Fh] BYREF
  _OWORD v16[2]; // [rsp+68h] [rbp+27h] BYREF
  __int64 v17; // [rsp+88h] [rbp+47h]

  FileObject = 0;
  FileHandle = 0;
  FileInformation[0] = 0;
  result = WofRelativeStreamOpen(a1, a2, a3, 0, FileInformationClass, &FileObject, &FileHandle);
  if ( result >= 0 )
  {
    v5 = *(struct _FLT_INSTANCE **)(a1 + 120);
    FileInformation[0] = 1;
    v6 = FltSetInformationFile(v5, FileObject, FileInformation, 1u, FileDispositionInformation);
    if ( v6 == -1073741535 )
    {
      v7 = *(struct _FLT_INSTANCE **)(a1 + 120);
      v17 = 0;
      LengthReturned = 0;
      memset(v16, 0, sizeof(v16));
      if ( FltQueryInformationFile(v7, FileObject, v16, 0x28u, FileBasicInformation, &LengthReturned) >= 0
        && (v17 & 1) != 0 )
      {
        v8 = *(struct _FLT_INSTANCE **)(a1 + 120);
        LODWORD(v17) = v17 & 0xFFFFFFFE;
        FltSetInformationFile(v8, FileObject, v16, 0x28u, FileBasicInformation);
        v9 = FltSetInformationFile(
               *(PFLT_INSTANCE *)(a1 + 120),
               FileObject,
               FileInformation,
               1u,
               FileDispositionInformation);
        v10 = *(struct _FLT_INSTANCE **)(a1 + 120);
        LODWORD(v17) = v17 | 1;
        v6 = v9;
        FltSetInformationFile(v10, FileObject, v16, 0x28u, FileBasicInformation);
      }
    }
    FltClose(FileHandle);
    ObfDereferenceObject(FileObject);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14000ac54  mov     r11, rsp
0x14000ac57  mov     [r11+18h], rsi
0x14000ac5b  mov     [r11+20h], rdi
0x14000ac5f  push    rbp
0x14000ac60  lea     rbp, [r11-5Fh]
0x14000ac64  sub     rsp, 90h
0x14000ac6b  mov     rax, cs:__security_cookie
0x14000ac72  xor     rax, rsp
0x14000ac75  mov     [rbp+57h+var_8], rax
0x14000ac79  lea     rax, [rbp+57h+FileHandle]
0x14000ac7d  mov     [rbp+57h+FileObject], 0
0x14000ac85  mov     [r11-68h], rax
0x14000ac89  xor     r9d, r9d
0x14000ac8c  lea     rax, [rbp+57h+FileObject]
0x14000ac90  mov     [rbp+57h+FileHandle], 0
0x14000ac98  mov     [r11-70h], rax
0x14000ac9c  mov     rdi, rcx
0x14000ac9f  mov     [rbp+57h+FileInformation], 0
0x14000aca3  call    WofRelativeStreamOpen
0x14000aca8  test    eax, eax
0x14000acaa  js      loc_14000ADD9
0x14000acb0  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14000acb4  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000acb8  mov     rcx, [rdi+78h]; Instance
0x14000acbc  mov     r9d, 1; Length
0x14000acc2  mov     [rbp+57h+FileInformation], 1
0x14000acc6  mov     [rsp+90h+FileInformationClass], 0Dh; FileInformationClass
0x14000acce  call    cs:__imp_FltSetInformationFile
0x14000acd5  nop     dword ptr [rax+rax+00h]
0x14000acda  mov     esi, eax
0x14000acdc  cmp     eax, 0C0000121h
0x14000ace1  jnz     loc_14000ADB7
0x14000ace7  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14000aceb  lea     r8, [rbp+57h+var_30]; FileInformation
0x14000acef  mov     rcx, [rdi+78h]; Instance
0x14000acf3  xor     eax, eax
0x14000acf5  xorps   xmm0, xmm0
0x14000acf8  mov     [rbp+57h+var_10], rax
0x14000acfc  mov     [rbp+57h+var_40], eax
0x14000acff  mov     r9d, 28h ; '('; Length
0x14000ad05  lea     rax, [rbp+57h+var_40]
0x14000ad09  mov     [rsp+90h+LengthReturned], rax; LengthReturned
0x14000ad0e  mov     [rsp+90h+FileInformationClass], 4; FileInformationClass
0x14000ad16  movups  [rbp+57h+var_30], xmm0
0x14000ad1a  movups  [rbp+57h+var_20], xmm0
0x14000ad1e  call    cs:__imp_FltQueryInformationFile
0x14000ad25  nop     dword ptr [rax+rax+00h]
0x14000ad2a  test    eax, eax
0x14000ad2c  js      loc_14000ADB7
0x14000ad32  mov     eax, dword ptr [rbp+57h+var_10]
0x14000ad35  test    al, 1
0x14000ad37  jz      short loc_14000ADB7
0x14000ad39  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14000ad3d  lea     r8, [rbp+57h+var_30]; FileInformation
0x14000ad41  mov     rcx, [rdi+78h]; Instance
0x14000ad45  and     eax, 0FFFFFFFEh
0x14000ad48  mov     r9d, 28h ; '('; Length
0x14000ad4e  mov     dword ptr [rbp+57h+var_10], eax
0x14000ad51  mov     [rsp+90h+FileInformationClass], 4; FileInformationClass
0x14000ad59  call    cs:__imp_FltSetInformationFile
0x14000ad60  nop     dword ptr [rax+rax+00h]
0x14000ad65  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14000ad69  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000ad6d  mov     rcx, [rdi+78h]; Instance
0x14000ad71  mov     r9d, 1; Length
0x14000ad77  mov     [rsp+90h+FileInformationClass], 0Dh; FileInformationClass
0x14000ad7f  call    cs:__imp_FltSetInformationFile
0x14000ad86  nop     dword ptr [rax+rax+00h]
0x14000ad8b  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14000ad8f  lea     r8, [rbp+57h+var_30]; FileInformation
0x14000ad93  mov     rcx, [rdi+78h]; Instance
0x14000ad97  mov     r9d, 28h ; '('; Length
0x14000ad9d  or      dword ptr [rbp+57h+var_10], 1
0x14000ada1  mov     esi, eax
0x14000ada3  mov     [rsp+90h+FileInformationClass], 4; FileInformationClass
0x14000adab  call    cs:__imp_FltSetInformationFile
0x14000adb2  nop     dword ptr [rax+rax+00h]
0x14000adb7  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000adbb  call    cs:__imp_FltClose
0x14000adc2  nop     dword ptr [rax+rax+00h]
0x14000adc7  mov     rcx, [rbp+57h+FileObject]; Object
0x14000adcb  call    cs:__imp_ObfDereferenceObject
0x14000add2  nop     dword ptr [rax+rax+00h]
0x14000add7  mov     eax, esi
0x14000add9  mov     rcx, [rbp+57h+var_8]
0x14000addd  xor     rcx, rsp; StackCookie
0x14000ade0  call    __security_check_cookie
0x14000ade5  lea     r11, [rsp+90h+var_s0]
0x14000aded  mov     rsi, [r11+20h]
0x14000adf1  mov     rdi, [r11+28h]
0x14000adf5  mov     rsp, r11
0x14000adf8  pop     rbp
0x14000adf9  retn
```
