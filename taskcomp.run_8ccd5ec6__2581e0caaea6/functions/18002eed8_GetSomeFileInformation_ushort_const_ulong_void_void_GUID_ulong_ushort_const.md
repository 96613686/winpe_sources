# GetSomeFileInformation(ushort const *,ulong *,void * *,void * *,_GUID *,ulong,ushort * const)

- ea: `0x18002eed8`
- end: `0x18002f09d`
- name: `?GetSomeFileInformation@@YAJPEBGPEAKPEAPEAX2PEAU_GUID@@KQEAG@Z`
- size: `453`
- prototype: `int(const unsigned __int16 *, unsigned int *, void **, void **, struct _GUID *, unsigned int, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800156a4`

## callees

- `0x18002ed9c`
- `0x18002eed8`
- `0x18002f0a4`
- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002eff9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002eff9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f010`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f06f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f06f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ef97`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ef97`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ef3d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ef3d`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002efe4`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002efe4`

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
0x18002eed8  push    rbx
0x18002eeda  push    rbp
0x18002eedb  push    rsi
0x18002eedc  push    rdi
0x18002eedd  push    r12
0x18002eedf  push    r14
0x18002eee1  push    r15
0x18002eee3  sub     rsp, 70h
0x18002eee7  mov     rax, cs:__security_cookie
0x18002eeee  xor     rax, rsp
0x18002eef1  mov     [rsp+0A8h+var_40], rax
0x18002eef6  mov     rbp, [rsp+0A8h+arg_20]
0x18002eefe  mov     rbx, r9
0x18002ef01  mov     r12, [rsp+0A8h+arg_30]
0x18002ef09  xor     r9d, r9d; lpSecurityAttributes
0x18002ef0c  mov     r15, r8
0x18002ef0f  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18002ef18  mov     r14, rdx
0x18002ef1b  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002ef23  mov     edx, 80000000h; dwDesiredAccess
0x18002ef28  mov     [rsp+0A8h+ppsidOwner], 0
0x18002ef31  lea     r8d, [r9+1]; dwShareMode
0x18002ef35  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18002ef3d  call    cs:__imp_CreateFileW
0x18002ef44  nop     dword ptr [rax+rax+00h]
0x18002ef49  mov     rdi, rax
0x18002ef4c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ef50  jnz     short loc_18002EF73
0x18002ef52  call    cs:__imp_GetLastError
0x18002ef59  nop     dword ptr [rax+rax+00h]
0x18002ef5e  test    eax, eax
0x18002ef60  jle     loc_18002F080
0x18002ef66  movzx   eax, ax
0x18002ef69  or      eax, 80070000h
0x18002ef6e  jmp     loc_18002F080
0x18002ef73  lea     r9, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002ef78  mov     [rsp+0A8h+NumberOfBytesRead], 0
0x18002ef80  mov     r8d, 14h; nNumberOfBytesToRead
0x18002ef86  mov     qword ptr [rsp+0A8h+dwCreationDisposition], 0; lpOverlapped
0x18002ef8f  lea     rdx, [rsp+0A8h+Buffer]; lpBuffer
0x18002ef94  mov     rcx, rdi; hFile
0x18002ef97  call    cs:__imp_ReadFile
0x18002ef9e  nop     dword ptr [rax+rax+00h]
0x18002efa3  test    eax, eax
0x18002efa5  jz      loc_18002F06C
0x18002efab  cmp     [rsp+0A8h+NumberOfBytesRead], 14h
0x18002efb0  jnz     loc_18002F06C
0x18002efb6  movups  xmm0, [rsp+0A8h+var_54]
0x18002efbb  xor     esi, esi
0x18002efbd  mov     [rsp+0A8h+ppSecurityDescriptor], rbx; ppSecurityDescriptor
0x18002efc2  mov     [rsp+0A8h+hTemplateFile], rsi; ppSacl
0x18002efc7  lea     r9, [rsp+0A8h+ppsidOwner]; ppsidOwner
0x18002efcc  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rsi; ppDacl
0x18002efd1  mov     rcx, rdi; handle
0x18002efd4  movdqu  xmmword ptr [rbp+0], xmm0
0x18002efd9  lea     edx, [rsi+1]; ObjectType
0x18002efdc  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rsi; ppsidGroup
0x18002efe1  mov     r8d, edx; SecurityInfo
0x18002efe4  call    cs:__imp_GetSecurityInfo
0x18002efeb  nop     dword ptr [rax+rax+00h]
0x18002eff0  test    eax, eax
0x18002eff2  jnz     short loc_18002F020
0x18002eff4  mov     rcx, [rsp+0A8h+ppsidOwner]; pSid
0x18002eff9  call    cs:__imp_IsValidSid
0x18002f000  nop     dword ptr [rax+rax+00h]
0x18002f005  test    eax, eax
0x18002f007  jz      short loc_18002F020
0x18002f009  mov     rcx, [rsp+0A8h+ppsidOwner]; pSid
0x18002f00e  xor     ebx, ebx
0x18002f010  call    cs:__imp_GetLengthSid
0x18002f017  nop     dword ptr [rax+rax+00h]
0x18002f01c  mov     esi, eax
0x18002f01e  jmp     short loc_18002F03B
0x18002f020  call    cs:__imp_GetLastError
0x18002f027  nop     dword ptr [rax+rax+00h]
0x18002f02c  mov     ebx, eax
0x18002f02e  test    eax, eax
0x18002f030  jle     short loc_18002F03B
0x18002f032  movzx   ebx, ax
0x18002f035  or      ebx, 80070000h
0x18002f03b  mov     r9d, ebx; int
0x18002f03e  mov     r8, r12; unsigned __int16 *
0x18002f041  mov     rcx, rdi; hObject
0x18002f044  call    ?CloseFile@@YAJPEAXGQEAGJ@Z; CloseFile(void *,ushort,ushort * const,long)
0x18002f049  mov     ebx, eax
0x18002f04b  test    eax, eax
0x18002f04d  js      short loc_18002F068
0x18002f04f  cmp     cs:?gdwKeyElement@@3KA, 0; ulong gdwKeyElement
0x18002f056  mov     rcx, [rsp+0A8h+ppsidOwner]
0x18002f05b  mov     [r14], esi
0x18002f05e  mov     [r15], rcx
0x18002f061  jnz     short loc_18002F068
0x18002f063  call    ?SetMysteryDWORDValue@@YAXXZ; SetMysteryDWORDValue(void)
0x18002f068  mov     eax, ebx
0x18002f06a  jmp     short loc_18002F080
0x18002f06c  mov     rcx, rdi; hObject
0x18002f06f  call    cs:__imp_CloseHandle
0x18002f076  nop     dword ptr [rax+rax+00h]
0x18002f07b  mov     eax, 8004130Eh
0x18002f080  mov     rcx, [rsp+0A8h+var_40]
0x18002f085  xor     rcx, rsp; StackCookie
0x18002f088  call    __security_check_cookie
0x18002f08d  add     rsp, 70h
0x18002f091  pop     r15
0x18002f093  pop     r14
0x18002f095  pop     r12
0x18002f097  pop     rdi
0x18002f098  pop     rsi
0x18002f099  pop     rbp
0x18002f09a  pop     rbx
0x18002f09b  retn
```
