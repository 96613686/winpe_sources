# FormFinalPathNameByHandle

- ea: `0x18003beb4`
- end: `0x18003bf94`
- name: `FormFinalPathNameByHandle`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x18003bf9c`
- `0x18003db20`

## callees

- `0x18003beb4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003bf11`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003bf52`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003bf11`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003bf52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bf25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bf25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bf36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bf36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf67`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameByHandle(char *hFile, int a2)
{
  DWORD v3; // edi
  int v4; // edx
  int v5; // edx
  DWORD v6; // ecx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v8; // r14d
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  DWORD LastError; // ebx

  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL || (a2 & 0xFFFFFFF8) != 0 )
  {
    v6 = 87;
    goto LABEL_19;
  }
  v3 = 0;
  if ( !a2 )
  {
LABEL_10:
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v3);
    if ( FinalPathNameByHandleW )
    {
      v8 = FinalPathNameByHandleW + 1;
      v9 = 2LL * (FinalPathNameByHandleW + 1);
      ProcessHeap = GetProcessHeap();
      v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
      v12 = v11;
      if ( v11 )
      {
        LastError = 0;
        if ( !GetFinalPathNameByHandleW(hFile, v11, v8, v3) )
          goto LABEL_16;
      }
      else
      {
        LastError = 14;
      }
LABEL_17:
      SetLastError(LastError);
      return v12;
    }
    v12 = 0;
LABEL_16:
    LastError = GetLastError();
    goto LABEL_17;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v3 = 1;
    goto LABEL_10;
  }
  v3 = 2;
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_10;
  if ( v5 == 2 )
  {
    v3 = 4;
    goto LABEL_10;
  }
  v6 = 50;
LABEL_19:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18003beb4  push    rbx
0x18003beb6  push    rbp
0x18003beb7  push    rsi
0x18003beb8  push    rdi
0x18003beb9  push    r14
0x18003bebb  sub     rsp, 20h
0x18003bebf  lea     rax, [rcx-1]
0x18003bec3  mov     rbp, rcx
0x18003bec6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003beca  ja      loc_18003BF7C
0x18003bed0  test    edx, 0FFFFFFF8h
0x18003bed6  jnz     loc_18003BF7C
0x18003bedc  xor     edi, edi
0x18003bede  test    edx, edx
0x18003bee0  jz      short loc_18003BF09
0x18003bee2  sub     edx, 1
0x18003bee5  jz      short loc_18003BF04
0x18003bee7  mov     edi, 2
0x18003beec  sub     edx, 1
0x18003beef  jz      short loc_18003BF09
0x18003bef1  cmp     edx, edi
0x18003bef3  jz      short loc_18003BEFD
0x18003bef5  lea     ecx, [rdi+30h]; hFile
0x18003bef8  jmp     loc_18003BF81
0x18003befd  mov     edi, 4
0x18003bf02  jmp     short loc_18003BF09
0x18003bf04  mov     edi, 1
0x18003bf09  mov     r9d, edi; dwFlags
0x18003bf0c  xor     r8d, r8d; cchFilePath
0x18003bf0f  xor     edx, edx; lpszFilePath
0x18003bf11  call    cs:__imp_GetFinalPathNameByHandleW
0x18003bf17  test    eax, eax
0x18003bf19  jz      short loc_18003BF65
0x18003bf1b  lea     r14d, [rax+1]
0x18003bf1f  mov     ebx, r14d
0x18003bf22  add     rbx, rbx
0x18003bf25  call    cs:__imp_GetProcessHeap
0x18003bf2b  mov     r8, rbx; dwBytes
0x18003bf2e  mov     edx, 8; dwFlags
0x18003bf33  mov     rcx, rax; hHeap
0x18003bf36  call    cs:__imp_HeapAlloc
0x18003bf3c  mov     rsi, rax
0x18003bf3f  test    rax, rax
0x18003bf42  jz      short loc_18003BF5E
0x18003bf44  mov     r9d, edi; dwFlags
0x18003bf47  mov     r8d, r14d; cchFilePath
0x18003bf4a  mov     rdx, rax; lpszFilePath
0x18003bf4d  mov     rcx, rbp; hFile
0x18003bf50  xor     ebx, ebx
0x18003bf52  call    cs:__imp_GetFinalPathNameByHandleW
0x18003bf58  test    eax, eax
0x18003bf5a  jnz     short loc_18003BF6F
0x18003bf5c  jmp     short loc_18003BF67
0x18003bf5e  mov     ebx, 0Eh
0x18003bf63  jmp     short loc_18003BF6F
0x18003bf65  xor     esi, esi
0x18003bf67  call    cs:__imp_GetLastError
0x18003bf6d  mov     ebx, eax
0x18003bf6f  mov     ecx, ebx; dwErrCode
0x18003bf71  call    cs:__imp_SetLastError
0x18003bf77  mov     rax, rsi
0x18003bf7a  jmp     short loc_18003BF89
0x18003bf7c  mov     ecx, 57h ; 'W'; dwErrCode
0x18003bf81  call    cs:__imp_SetLastError
0x18003bf87  xor     eax, eax
0x18003bf89  add     rsp, 20h
0x18003bf8d  pop     r14
0x18003bf8f  pop     rdi
0x18003bf90  pop     rsi
0x18003bf91  pop     rbp
0x18003bf92  pop     rbx
0x18003bf93  retn
```
