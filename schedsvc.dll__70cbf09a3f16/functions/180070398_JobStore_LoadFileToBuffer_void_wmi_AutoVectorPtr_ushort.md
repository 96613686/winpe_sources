# JobStore::LoadFileToBuffer(void *,wmi::AutoVectorPtr<ushort> &)

- ea: `0x180070398`
- end: `0x1800704f4`
- name: `?LoadFileToBuffer@JobStore@@CAJPEAXAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `348`
- prototype: `signed int __fastcall(HANDLE hFile, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18006eae0`

## callees

- `0x18001a260`
- `0x180030f80`
- `0x1800408b0`
- `0x180070398`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800703c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007048a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800703c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007048a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007042a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180070480`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007042a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180070480`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800703bf`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800703bf`

## pseudocode

```c
signed int __fastcall JobStore::LoadFileToBuffer(HANDLE hFile, __int64 a2)
{
  signed int result; // eax
  DWORD v5; // esi
  char *v6; // rbx
  signed int LastError; // eax
  unsigned int v8; // edi
  __int64 v9; // rcx
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-10h] BYREF
  __int16 Buffer; // [rsp+70h] [rbp+30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+38h] BYREF

  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(hFile, &FileSize) )
    goto LABEL_2;
  if ( FileSize.HighPart )
    return -2147024882;
  if ( !FileSize.LowPart || (FileSize.LowPart & 1) != 0 )
    return -2147024809;
  NumberOfBytesRead = 0;
  Buffer = 0;
  if ( ReadFile(hFile, &Buffer, 2u, &NumberOfBytesRead, 0) )
  {
    if ( NumberOfBytesRead == 2 && Buffer == -257 )
    {
      v5 = FileSize.LowPart >> 1;
      v6 = (char *)operator new(saturated_mul(FileSize.LowPart >> 1, 2u));
      if ( ReadFile(hFile, v6, 2 * v5, &NumberOfBytesRead, 0) )
      {
        v9 = 2LL * (v5 - 1);
        if ( NumberOfBytesRead == v9 )
        {
          *(_WORD *)&v6[v9] = 0;
          wmi::AutoVectorPtr<unsigned short>::operator=(a2, v6);
          operator delete(0);
          return 0;
        }
        v8 = -2147467259;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      operator delete(v6);
      return v8;
    }
    return -2147024809;
  }
LABEL_2:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180070398  mov     [rsp-18h+arg_0], rbx
0x18007039d  mov     [rsp-18h+arg_8], rsi
0x1800703a2  push    rbp
0x1800703a3  push    rdi
0x1800703a4  push    r14
0x1800703a6  mov     rbp, rsp
0x1800703a9  sub     rsp, 40h
0x1800703ad  mov     r14, rdx
0x1800703b0  mov     qword ptr [rbp+FileSize], 0
0x1800703b8  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800703bc  mov     rdi, rcx
0x1800703bf  call    cs:__imp_GetFileSizeEx
0x1800703c5  test    eax, eax
0x1800703c7  jnz     short loc_1800703E4
0x1800703c9  call    cs:__imp_GetLastError
0x1800703cf  test    eax, eax
0x1800703d1  jle     loc_1800704E1
0x1800703d7  movzx   eax, ax
0x1800703da  or      eax, 80070000h
0x1800703df  jmp     loc_1800704E1
0x1800703e4  cmp     dword ptr [rbp+FileSize+4], 0
0x1800703e8  jz      short loc_1800703F4
0x1800703ea  mov     eax, 8007000Eh
0x1800703ef  jmp     loc_1800704E1
0x1800703f4  mov     eax, dword ptr [rbp+FileSize]
0x1800703f7  test    eax, eax
0x1800703f9  jz      loc_1800704DC
0x1800703ff  test    al, 1
0x180070401  jnz     loc_1800704DC
0x180070407  xor     eax, eax
0x180070409  mov     [rbp+NumberOfBytesRead], 0
0x180070410  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180070414  mov     [rbp+Buffer], ax
0x180070418  lea     rdx, [rbp+Buffer]; lpBuffer
0x18007041c  mov     [rsp+40h+lpOverlapped], rax; lpOverlapped
0x180070421  mov     rcx, rdi; hFile
0x180070424  lea     ebx, [rax+2]
0x180070427  mov     r8d, ebx; nNumberOfBytesToRead
0x18007042a  call    cs:__imp_ReadFile
0x180070430  test    eax, eax
0x180070432  jz      short loc_1800703C9
0x180070434  cmp     [rbp+NumberOfBytesRead], ebx
0x180070437  jnz     loc_1800704DC
0x18007043d  mov     ecx, 0FEFFh
0x180070442  cmp     [rbp+Buffer], cx
0x180070446  jnz     loc_1800704DC
0x18007044c  mov     esi, dword ptr [rbp+FileSize]
0x18007044f  lea     rcx, [rbx-3]
0x180070453  shr     esi, 1
0x180070455  mov     eax, ebx
0x180070457  mul     rsi
0x18007045a  cmovb   rax, rcx
0x18007045e  mov     rcx, rax; dwBytes
0x180070461  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070466  lea     r8d, [rsi+rsi]; nNumberOfBytesToRead
0x18007046a  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x180070473  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180070477  mov     rdx, rax; lpBuffer
0x18007047a  mov     rcx, rdi; hFile
0x18007047d  mov     rbx, rax
0x180070480  call    cs:__imp_ReadFile
0x180070486  test    eax, eax
0x180070488  jnz     short loc_1800704A1
0x18007048a  call    cs:__imp_GetLastError
0x180070490  mov     edi, eax
0x180070492  test    eax, eax
0x180070494  jle     short loc_1800704B4
0x180070496  movzx   edi, ax
0x180070499  or      edi, 80070000h
0x18007049f  jmp     short loc_1800704B4
0x1800704a1  mov     eax, [rbp+NumberOfBytesRead]
0x1800704a4  lea     ecx, [rsi-1]
0x1800704a7  add     rcx, rcx
0x1800704aa  cmp     rax, rcx
0x1800704ad  jz      short loc_1800704C0
0x1800704af  mov     edi, 80004005h
0x1800704b4  mov     rcx, rbx; void *
0x1800704b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800704bc  mov     eax, edi
0x1800704be  jmp     short loc_1800704E1
0x1800704c0  xor     eax, eax
0x1800704c2  mov     rdx, rbx
0x1800704c5  mov     [rcx+rbx], ax
0x1800704c9  mov     rcx, r14
0x1800704cc  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x1800704d1  xor     ecx, ecx; void *
0x1800704d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800704d8  xor     eax, eax
0x1800704da  jmp     short loc_1800704E1
0x1800704dc  mov     eax, 80070057h
0x1800704e1  mov     rbx, [rsp+40h+arg_0]
0x1800704e6  mov     rsi, [rsp+40h+arg_8]
0x1800704eb  add     rsp, 40h
0x1800704ef  pop     r14
0x1800704f1  pop     rdi
0x1800704f2  pop     rbp
0x1800704f3  retn
```
