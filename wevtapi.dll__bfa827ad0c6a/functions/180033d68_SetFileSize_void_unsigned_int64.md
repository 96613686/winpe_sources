# SetFileSize(void *,unsigned __int64)

- ea: `0x180033d68`
- end: `0x180033dda`
- name: `?SetFileSize@@YAKPEAX_K@Z`
- size: `114`
- prototype: `unsigned int __fastcall(void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800314f0`
- `0x180031f14`
- `0x18003459c`

## callees

- `0x180023548`
- `0x180033d68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d8c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180033d82`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180033d82`

## pseudocode

```c
__int64 __fastcall SetFileSize(void *a1, __int64 a2)
{
  DWORD LastError; // ebx
  __int64 FileInformation; // [rsp+38h] [rbp+10h] BYREF

  FileInformation = a2;
  if ( SetFileInformationByHandle(a1, FileEndOfFileInfo, &FileInformation, 8u) )
    return 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180033d68  push    rbx
0x180033d6a  sub     rsp, 20h
0x180033d6e  mov     r9d, 8; dwBufferSize
0x180033d74  mov     [rsp+28h+FileInformation], rdx
0x180033d79  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x180033d7e  lea     edx, [r9-2]; FileInformationClass
0x180033d82  call    cs:__imp_SetFileInformationByHandle
0x180033d88  test    eax, eax
0x180033d8a  jnz     short loc_180033DD2
0x180033d8c  call    cs:__imp_GetLastError
0x180033d92  mov     ebx, eax
0x180033d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d9b  lea     rax, WPP_GLOBAL_Control
0x180033da2  cmp     rcx, rax
0x180033da5  jz      short loc_180033DCE
0x180033da7  test    dword ptr [rcx+1Ch], 8000h
0x180033dae  jz      short loc_180033DCE
0x180033db0  cmp     byte ptr [rcx+19h], 2
0x180033db4  jb      short loc_180033DCE
0x180033db6  mov     rcx, [rcx+10h]
0x180033dba  lea     r8, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids
0x180033dc1  mov     edx, 0Ch
0x180033dc6  mov     r9d, ebx
0x180033dc9  call    WPP_SF_D
0x180033dce  mov     eax, ebx
0x180033dd0  jmp     short loc_180033DD4
0x180033dd2  xor     eax, eax
0x180033dd4  add     rsp, 20h
0x180033dd8  pop     rbx
0x180033dd9  retn
```
