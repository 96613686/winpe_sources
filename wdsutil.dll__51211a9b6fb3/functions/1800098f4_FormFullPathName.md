# FormFullPathName

- ea: `0x1800098f4`
- end: `0x1800099c4`
- name: `FormFullPathName`
- size: `208`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800099cc`

## callees

- `0x1800098f4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009986`
- `KERNEL32!GetLastError` at `0x180009986`
- `KERNEL32!HeapAlloc` at `0x18000994a`
- `KERNEL32!HeapAlloc` at `0x18000994a`
- `KERNEL32!GetProcessHeap` at `0x180009933`
- `KERNEL32!GetProcessHeap` at `0x180009933`
- `KERNEL32!SetLastError` at `0x180009996`
- `KERNEL32!SetLastError` at `0x1800099ac`
- `KERNEL32!SetLastError` at `0x180009996`
- `KERNEL32!SetLastError` at `0x1800099ac`
- `KERNEL32!GetFullPathNameW` at `0x18000991c`
- `KERNEL32!GetFullPathNameW` at `0x18000996b`
- `KERNEL32!GetFullPathNameW` at `0x18000991c`
- `KERNEL32!GetFullPathNameW` at `0x18000996b`

## pseudocode

```c
WCHAR *__fastcall FormFullPathName(LPCWSTR lpFileName)
{
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  DWORD LastError; // ebx

  if ( lpFileName && *lpFileName )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    if ( FullPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v4 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
      v5 = v4;
      if ( v4 )
      {
        LastError = 0;
        if ( !GetFullPathNameW(lpFileName, FullPathNameW, v4, 0) )
          goto LABEL_9;
      }
      else
      {
        LastError = 14;
      }
LABEL_10:
      SetLastError(LastError);
      return v5;
    }
    v5 = 0;
LABEL_9:
    LastError = GetLastError();
    goto LABEL_10;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x1800098f4  push    rbx
0x1800098f6  push    rbp
0x1800098f7  push    rsi
0x1800098f8  push    rdi
0x1800098f9  sub     rsp, 28h
0x1800098fd  mov     rdi, rcx
0x180009900  test    rcx, rcx
0x180009903  jz      loc_1800099A7
0x180009909  xor     eax, eax
0x18000990b  cmp     ax, [rcx]
0x18000990e  jz      loc_1800099A7
0x180009914  xor     r9d, r9d; lpFilePart
0x180009917  xor     r8d, r8d; lpBuffer
0x18000991a  xor     edx, edx; nBufferLength
0x18000991c  call    cs:__imp_GetFullPathNameW
0x180009923  nop     dword ptr [rax+rax+00h]
0x180009928  mov     ebp, eax
0x18000992a  test    eax, eax
0x18000992c  jz      short loc_180009984
0x18000992e  mov     ebx, ebp
0x180009930  add     rbx, rbx
0x180009933  call    cs:__imp_GetProcessHeap
0x18000993a  nop     dword ptr [rax+rax+00h]
0x18000993f  mov     r8, rbx; dwBytes
0x180009942  mov     edx, 8; dwFlags
0x180009947  mov     rcx, rax; hHeap
0x18000994a  call    cs:__imp_HeapAlloc
0x180009951  nop     dword ptr [rax+rax+00h]
0x180009956  mov     rsi, rax
0x180009959  test    rax, rax
0x18000995c  jz      short loc_18000997D
0x18000995e  xor     r9d, r9d; lpFilePart
0x180009961  mov     r8, rax; lpBuffer
0x180009964  mov     edx, ebp; nBufferLength
0x180009966  mov     rcx, rdi; lpFileName
0x180009969  xor     ebx, ebx
0x18000996b  call    cs:__imp_GetFullPathNameW
0x180009972  nop     dword ptr [rax+rax+00h]
0x180009977  test    eax, eax
0x180009979  jnz     short loc_180009994
0x18000997b  jmp     short loc_180009986
0x18000997d  mov     ebx, 0Eh
0x180009982  jmp     short loc_180009994
0x180009984  xor     esi, esi
0x180009986  call    cs:__imp_GetLastError
0x18000998d  nop     dword ptr [rax+rax+00h]
0x180009992  mov     ebx, eax
0x180009994  mov     ecx, ebx; dwErrCode
0x180009996  call    cs:__imp_SetLastError
0x18000999d  nop     dword ptr [rax+rax+00h]
0x1800099a2  mov     rax, rsi
0x1800099a5  jmp     short loc_1800099BA
0x1800099a7  mov     ecx, 57h ; 'W'; dwErrCode
0x1800099ac  call    cs:__imp_SetLastError
0x1800099b3  nop     dword ptr [rax+rax+00h]
0x1800099b8  xor     eax, eax
0x1800099ba  add     rsp, 28h
0x1800099be  pop     rdi
0x1800099bf  pop     rsi
0x1800099c0  pop     rbp
0x1800099c1  pop     rbx
0x1800099c2  retn
```
