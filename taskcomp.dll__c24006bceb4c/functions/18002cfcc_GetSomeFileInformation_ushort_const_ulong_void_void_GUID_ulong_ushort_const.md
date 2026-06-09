# GetSomeFileInformation(ushort const *,ulong *,void * *,void * *,_GUID *,ulong,ushort * const)

- ea: `0x18002cfcc`
- end: `0x18002d160`
- name: `?GetSomeFileInformation@@YAJPEBGPEAKPEAPEAX2PEAU_GUID@@KQEAG@Z`
- size: `404`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned int *, void **, void **, struct _GUID *, unsigned int, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800149a4`

## callees

- `0x18002ceb0`
- `0x18002cfcc`
- `0x18002d168`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002d0d5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002d0d5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002d0e6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002d0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d139`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002d07f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002d07f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d031`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d031`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002d0c6`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002d0c6`

## pseudocode

```c
int __fastcall GetSomeFileInformation(
        const unsigned __int16 *a1,
        unsigned int *a2,
        void **a3,
        void **a4,
        struct _GUID *a5,
        unsigned int a6,
        unsigned __int16 *const a7)
{
  HANDLE FileW; // rax
  void *v11; // rdi
  int result; // eax
  DWORD LengthSid; // esi
  unsigned int v14; // ebx
  unsigned __int16 v15; // dx
  signed int LastError; // eax
  int v17; // ebx
  bool v18; // zf
  PSID v19; // rcx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-68h] BYREF
  PSID ppsidOwner; // [rsp+48h] [rbp-60h] BYREF
  _BYTE Buffer[4]; // [rsp+50h] [rbp-58h] BYREF
  struct _GUID v23; // [rsp+54h] [rbp-54h]

  ppsidOwner = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    NumberOfBytesRead = 0;
    if ( ReadFile(FileW, Buffer, 0x14u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 20 )
    {
      LengthSid = 0;
      *a5 = v23;
      if ( GetSecurityInfo(v11, SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, a4) || !IsValidSid(ppsidOwner) )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v14 = 0;
        LengthSid = GetLengthSid(ppsidOwner);
      }
      v17 = CloseFile(v11, v15, a7, v14);
      if ( v17 >= 0 )
      {
        v18 = gdwKeyElement == 0;
        v19 = ppsidOwner;
        *a2 = LengthSid;
        *a3 = v19;
        if ( v18 )
          SetMysteryDWORDValue();
      }
      return v17;
    }
    else
    {
      CloseHandle(v11);
      return -2147216626;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002cfcc  push    rbx
0x18002cfce  push    rbp
0x18002cfcf  push    rsi
0x18002cfd0  push    rdi
0x18002cfd1  push    r12
0x18002cfd3  push    r14
0x18002cfd5  push    r15
0x18002cfd7  sub     rsp, 70h
0x18002cfdb  mov     rax, cs:__security_cookie
0x18002cfe2  xor     rax, rsp
0x18002cfe5  mov     [rsp+0A8h+var_40], rax
0x18002cfea  mov     rbp, [rsp+0A8h+arg_20]
0x18002cff2  mov     rbx, r9
0x18002cff5  mov     r12, [rsp+0A8h+arg_30]
0x18002cffd  xor     r9d, r9d; lpSecurityAttributes
0x18002d000  mov     r15, r8
0x18002d003  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18002d00c  mov     r14, rdx
0x18002d00f  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002d017  mov     edx, 80000000h; dwDesiredAccess
0x18002d01c  mov     [rsp+0A8h+ppsidOwner], 0
0x18002d025  lea     r8d, [r9+1]; dwShareMode
0x18002d029  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d031  call    cs:__imp_CreateFileW
0x18002d037  mov     rdi, rax
0x18002d03a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d03e  jnz     short loc_18002D05B
0x18002d040  call    cs:__imp_GetLastError
0x18002d046  test    eax, eax
0x18002d048  jle     loc_18002D144
0x18002d04e  movzx   eax, ax
0x18002d051  or      eax, 80070000h
0x18002d056  jmp     loc_18002D144
0x18002d05b  lea     r9, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002d060  mov     [rsp+0A8h+NumberOfBytesRead], 0
0x18002d068  mov     r8d, 14h; nNumberOfBytesToRead
0x18002d06e  mov     qword ptr [rsp+0A8h+dwCreationDisposition], 0; lpOverlapped
0x18002d077  lea     rdx, [rsp+0A8h+Buffer]; lpBuffer
0x18002d07c  mov     rcx, rdi; hFile
0x18002d07f  call    cs:__imp_ReadFile
0x18002d085  test    eax, eax
0x18002d087  jz      loc_18002D136
0x18002d08d  cmp     [rsp+0A8h+NumberOfBytesRead], 14h
0x18002d092  jnz     loc_18002D136
0x18002d098  movups  xmm0, [rsp+0A8h+var_54]
0x18002d09d  xor     esi, esi
0x18002d09f  mov     [rsp+0A8h+ppSecurityDescriptor], rbx; ppSecurityDescriptor
0x18002d0a4  mov     [rsp+0A8h+hTemplateFile], rsi; ppSacl
0x18002d0a9  lea     r9, [rsp+0A8h+ppsidOwner]; ppsidOwner
0x18002d0ae  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rsi; ppDacl
0x18002d0b3  mov     rcx, rdi; handle
0x18002d0b6  movdqu  xmmword ptr [rbp+0], xmm0
0x18002d0bb  lea     edx, [rsi+1]; ObjectType
0x18002d0be  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rsi; ppsidGroup
0x18002d0c3  mov     r8d, edx; SecurityInfo
0x18002d0c6  call    cs:__imp_GetSecurityInfo
0x18002d0cc  test    eax, eax
0x18002d0ce  jnz     short loc_18002D0F0
0x18002d0d0  mov     rcx, [rsp+0A8h+ppsidOwner]; pSid
0x18002d0d5  call    cs:__imp_IsValidSid
0x18002d0db  test    eax, eax
0x18002d0dd  jz      short loc_18002D0F0
0x18002d0df  mov     rcx, [rsp+0A8h+ppsidOwner]; pSid
0x18002d0e4  xor     ebx, ebx
0x18002d0e6  call    cs:__imp_GetLengthSid
0x18002d0ec  mov     esi, eax
0x18002d0ee  jmp     short loc_18002D105
0x18002d0f0  call    cs:__imp_GetLastError
0x18002d0f6  mov     ebx, eax
0x18002d0f8  test    eax, eax
0x18002d0fa  jle     short loc_18002D105
0x18002d0fc  movzx   ebx, ax
0x18002d0ff  or      ebx, 80070000h
0x18002d105  mov     r9d, ebx; int
0x18002d108  mov     r8, r12; unsigned __int16 *
0x18002d10b  mov     rcx, rdi; hObject
0x18002d10e  call    ?CloseFile@@YAJPEAXGQEAGJ@Z; CloseFile(void *,ushort,ushort * const,long)
0x18002d113  mov     ebx, eax
0x18002d115  test    eax, eax
0x18002d117  js      short loc_18002D132
0x18002d119  cmp     cs:?gdwKeyElement@@3KA, 0; ulong gdwKeyElement
0x18002d120  mov     rcx, [rsp+0A8h+ppsidOwner]
0x18002d125  mov     [r14], esi
0x18002d128  mov     [r15], rcx
0x18002d12b  jnz     short loc_18002D132
0x18002d12d  call    ?SetMysteryDWORDValue@@YAXXZ; SetMysteryDWORDValue(void)
0x18002d132  mov     eax, ebx
0x18002d134  jmp     short loc_18002D144
0x18002d136  mov     rcx, rdi; hObject
0x18002d139  call    cs:__imp_CloseHandle
0x18002d13f  mov     eax, 8004130Eh
0x18002d144  mov     rcx, [rsp+0A8h+var_40]
0x18002d149  xor     rcx, rsp; StackCookie
0x18002d14c  call    __security_check_cookie
0x18002d151  add     rsp, 70h
0x18002d155  pop     r15
0x18002d157  pop     r14
0x18002d159  pop     r12
0x18002d15b  pop     rdi
0x18002d15c  pop     rsi
0x18002d15d  pop     rbp
0x18002d15e  pop     rbx
0x18002d15f  retn
```
