# Pca::MergeSdb::Utils::MergeSdbpUtilGetFileLastWriteTimeForFile(Pca::MergeSdb::Utils::TimeValue &,ushort const *)

- ea: `0x14002cb08`
- end: `0x14002cc6b`
- name: `?MergeSdbpUtilGetFileLastWriteTimeForFile@Utils@MergeSdb@Pca@@YAKAEAVTimeValue@123@PEBG@Z`
- size: `355`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils *this, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x14002c36c`

## callees

- `0x14001008c`
- `0x14002cb08`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14002cb76`
- `msvcrt!_wcsnicmp` at `0x14002cb76`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14002cb91`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14002cb91`
- `ntdll!RtlInitUnicodeStringEx` at `0x14002cc31`
- `ntdll!RtlInitUnicodeStringEx` at `0x14002cc31`
- `ntdll!RtlNtStatusToDosError` at `0x14002cb9b`
- `ntdll!RtlNtStatusToDosError` at `0x14002cbf5`
- `ntdll!RtlNtStatusToDosError` at `0x14002cb9b`
- `ntdll!RtlNtStatusToDosError` at `0x14002cbf5`
- `ntdll!NtQueryInformationByName` at `0x14002cbeb`
- `ntdll!NtQueryInformationByName` at `0x14002cbeb`

## string_xrefs

- `0x14002cc17`: `Pca::MergeSdb::Utils::MergeSdbpUtilGetFileLastWriteTimeForFile`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::MergeSdbpUtilGetFileLastWriteTimeForFile(
        Pca::MergeSdb::Utils *this,
        const WCHAR *a2,
        const unsigned __int16 *a3)
{
  NTSTATUS inited; // eax
  int v6; // ebx
  ULONG v7; // edi
  NTSTATUS v8; // ebx
  ULONG v9; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-69h] BYREF
  __int128 v12; // [rsp+40h] [rbp-59h] BYREF
  __int128 v13; // [rsp+50h] [rbp-49h]
  __int128 v14; // [rsp+60h] [rbp-39h]
  __int128 v15; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v16[24]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v17; // [rsp+98h] [rbp-1h]

  DestinationString = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  memset_0(v16, 0, 0x48u);
  *(_QWORD *)this = 0;
  if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
    inited = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0);
  else
    inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  v6 = inited;
  v7 = RtlNtStatusToDosError(inited);
  if ( v6 >= 0 )
  {
    LODWORD(v12) = 48;
    *(_QWORD *)&v13 = &DestinationString;
    *((_QWORD *)&v12 + 1) = 0;
    DWORD2(v13) = 64;
    v14 = 0;
    v8 = NtQueryInformationByName(&v12, &v15, v16, 72, 68);
    v9 = RtlNtStatusToDosError(v8);
    v7 = v9;
    if ( v8 >= 0 )
    {
      v7 = 0;
      *(_QWORD *)this = v17;
    }
    else
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::MergeSdbpUtilGetFileLastWriteTimeForFile",
        816,
        "Failed to get timestamp from %S. (%d)",
        a2,
        v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14002cb08  mov     [rsp-8+arg_10], rbx
0x14002cb0d  mov     [rsp-8+arg_18], rsi
0x14002cb12  push    rbp
0x14002cb13  push    rdi
0x14002cb14  push    r14
0x14002cb16  lea     rbp, [rsp-47h]
0x14002cb1b  sub     rsp, 0E0h
0x14002cb22  mov     rax, cs:__security_cookie
0x14002cb29  xor     rax, rsp
0x14002cb2c  mov     [rbp+57h+var_20], rax
0x14002cb30  xorps   xmm1, xmm1
0x14002cb33  xorps   xmm0, xmm0
0x14002cb36  mov     rsi, rdx
0x14002cb39  mov     r14, rcx
0x14002cb3c  xor     edx, edx; Val
0x14002cb3e  lea     rcx, [rbp+57h+var_70]; void *
0x14002cb42  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002cb46  movups  [rbp+57h+var_B0], xmm1
0x14002cb4a  lea     r8d, [rdx+48h]; Size
0x14002cb4e  movups  [rbp+57h+var_A0], xmm1
0x14002cb52  movups  [rbp+57h+var_90], xmm1
0x14002cb56  movups  [rbp+57h+var_80], xmm0
0x14002cb5a  call    memset_0
0x14002cb5f  mov     r8d, 0Ch; MaxCount
0x14002cb65  mov     qword ptr [r14], 0
0x14002cb6c  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x14002cb73  mov     rcx, rsi; String1
0x14002cb76  call    cs:__imp__wcsnicmp
0x14002cb7c  test    eax, eax
0x14002cb7e  jz      loc_14002CC2A
0x14002cb84  xor     r9d, r9d
0x14002cb87  lea     rdx, [rbp+57h+DestinationString]
0x14002cb8b  xor     r8d, r8d
0x14002cb8e  mov     rcx, rsi
0x14002cb91  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14002cb97  mov     ecx, eax; Status
0x14002cb99  mov     ebx, eax
0x14002cb9b  call    cs:__imp_RtlNtStatusToDosError
0x14002cba1  mov     edi, eax
0x14002cba3  test    ebx, ebx
0x14002cba5  js      loc_14002CC45
0x14002cbab  lea     rax, [rbp+57h+DestinationString]
0x14002cbaf  mov     dword ptr [rbp+57h+var_B0], 30h ; '0'
0x14002cbb6  xorps   xmm0, xmm0
0x14002cbb9  mov     qword ptr [rbp+57h+var_A0], rax
0x14002cbbd  mov     r9d, 48h ; 'H'
0x14002cbc3  mov     qword ptr [rbp+57h+var_B0+8], 0
0x14002cbcb  lea     r8, [rbp+57h+var_70]
0x14002cbcf  mov     dword ptr [rbp+57h+var_A0+8], 40h ; '@'
0x14002cbd6  lea     rdx, [rbp+57h+var_80]
0x14002cbda  mov     dword ptr [rsp+0F0h+var_D0], 44h ; 'D'
0x14002cbe2  lea     rcx, [rbp+57h+var_B0]
0x14002cbe6  movdqu  [rbp+57h+var_90], xmm0
0x14002cbeb  call    cs:__imp_NtQueryInformationByName
0x14002cbf1  mov     ecx, eax; Status
0x14002cbf3  mov     ebx, eax
0x14002cbf5  call    cs:__imp_RtlNtStatusToDosError
0x14002cbfb  mov     edi, eax
0x14002cbfd  test    ebx, ebx
0x14002cbff  jns     short loc_14002CC3C
0x14002cc01  mov     [rsp+0F0h+var_C8], eax
0x14002cc05  lea     r9, aFailedToGetTim_0; "Failed to get timestamp from %S. (%d)"
0x14002cc0c  mov     r8d, 330h
0x14002cc12  mov     [rsp+0F0h+var_D0], rsi
0x14002cc17  lea     rdx, aPcaMergesdbUti_8; "Pca::MergeSdb::Utils::MergeSdbpUtilGetF"...
0x14002cc1e  mov     ecx, 1
0x14002cc23  call    AslLogCallPrintf
0x14002cc28  jmp     short loc_14002CC45
0x14002cc2a  mov     rdx, rsi; SourceString
0x14002cc2d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002cc31  call    cs:__imp_RtlInitUnicodeStringEx
0x14002cc37  jmp     loc_14002CB97
0x14002cc3c  mov     rax, [rbp+57h+var_58]
0x14002cc40  xor     edi, edi
0x14002cc42  mov     [r14], rax
0x14002cc45  mov     eax, edi
0x14002cc47  mov     rcx, [rbp+57h+var_20]
0x14002cc4b  xor     rcx, rsp; StackCookie
0x14002cc4e  call    __security_check_cookie
0x14002cc53  lea     r11, [rsp+0F0h+var_10]
0x14002cc5b  mov     rbx, [r11+30h]
0x14002cc5f  mov     rsi, [r11+38h]
0x14002cc63  mov     rsp, r11
0x14002cc66  pop     r14
0x14002cc68  pop     rdi
0x14002cc69  pop     rbp
0x14002cc6a  retn
```
