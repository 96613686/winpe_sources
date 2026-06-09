# CMachineId::CMachineId(MCID_CREATE_TYPE)

- ea: `0x180006700`
- end: `0x18000683b`
- name: `??0CMachineId@@QEAA@W4MCID_CREATE_TYPE@@@Z`
- size: `315`
- prototype: `CMachineId *__fastcall(CMachineId *)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180002488`
- `0x180003428`
- `0x180004ac0`
- `0x180004f90`
- `0x180005660`

## callees

- `0x180006700`
- `0x180006850`
- `0x18000d038`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000682d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000682d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006801`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000681c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006801`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000681c`
- `KERNEL32!GetComputerNameW` at `0x180006738`
- `KERNEL32!GetComputerNameW` at `0x180006738`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006772`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006772`

## pseudocode

```c
CMachineId *__fastcall CMachineId::CMachineId(CMachineId *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  CHAR *v4; // r8
  CMachineId *v5; // rdx
  CMachineId *v6; // rcx
  int LastError; // eax
  DWORD v9; // eax
  DWORD nSize; // [rsp+40h] [rbp-48h] BYREF
  CHAR MultiByteStr[16]; // [rsp+48h] [rbp-40h] BYREF
  WCHAR Buffer[16]; // [rsp+58h] [rbp-30h] BYREF

  *(_OWORD *)a1 = 0;
  v2 = 16;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 0, 0, 0);
    __debugbreak();
  }
  if ( !WideCharToMultiByte(1u, 0, Buffer, -1, MultiByteStr, 16, 0, 0) )
  {
    v9 = GetLastError();
    TrkRaiseWin32Error(v9);
  }
  if ( nSize + 1 > 0x10 )
  {
    RaiseException(0x8007007B, 0, 0, 0);
    __debugbreak();
  }
  v3 = 2147483646;
  v4 = MultiByteStr;
  v5 = a1;
  do
  {
    if ( !v3 )
      break;
    if ( !*v4 )
      break;
    *(_BYTE *)v5 = *v4++;
    v5 = (CMachineId *)((char *)v5 + 1);
    --v3;
    --v2;
  }
  while ( v2 );
  v6 = (CMachineId *)((char *)v5 - 1);
  if ( v2 )
    v6 = v5;
  *(_BYTE *)v6 = 0;
  CMachineId::Normalize(a1);
  CMachineId::Normalize(a1);
  return a1;
}

```

## disassembly

```asm
0x180006700  mov     [rsp+arg_8], rbx
0x180006705  push    rdi
0x180006706  sub     rsp, 80h
0x18000670d  mov     rax, cs:__security_cookie
0x180006714  xor     rax, rsp
0x180006717  mov     [rsp+88h+var_10], rax
0x18000671c  xorps   xmm0, xmm0
0x18000671f  lea     rdx, [rsp+88h+nSize]; nSize
0x180006724  movups  xmmword ptr [rcx], xmm0
0x180006727  mov     rdi, rcx
0x18000672a  mov     ebx, 10h
0x18000672f  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x180006734  mov     [rsp+88h+nSize], ebx
0x180006738  call    cs:__imp_GetComputerNameW
0x18000673e  test    eax, eax
0x180006740  jz      loc_180006808
0x180006746  xor     eax, eax
0x180006748  lea     r8, [rsp+88h+Buffer]; lpWideCharStr
0x18000674d  mov     [rsp+88h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180006752  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180006758  mov     [rsp+88h+lpDefaultChar], rax; lpDefaultChar
0x18000675d  xor     edx, edx; dwFlags
0x18000675f  lea     rax, [rsp+88h+MultiByteStr]
0x180006764  mov     [rsp+88h+cbMultiByte], ebx; cbMultiByte
0x180006768  mov     ecx, 1; CodePage
0x18000676d  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x180006772  call    cs:__imp_WideCharToMultiByte
0x180006778  test    eax, eax
0x18000677a  jz      loc_18000682D
0x180006780  mov     eax, [rsp+88h+nSize]
0x180006784  inc     eax
0x180006786  cmp     eax, ebx
0x180006788  ja      short loc_1800067F4
0x18000678a  mov     ecx, 7FFFFFFEh
0x18000678f  lea     r8, [rsp+88h+MultiByteStr]
0x180006794  mov     rdx, rdi
0x180006797  test    rcx, rcx
0x18000679a  jz      short loc_1800067B5
0x18000679c  movzx   eax, byte ptr [r8]
0x1800067a0  test    al, al
0x1800067a2  jz      short loc_1800067B5
0x1800067a4  mov     [rdx], al
0x1800067a6  inc     r8
0x1800067a9  inc     rdx
0x1800067ac  dec     rcx
0x1800067af  sub     rbx, 1
0x1800067b3  jnz     short loc_180006797
0x1800067b5  test    rbx, rbx
0x1800067b8  lea     rcx, [rdx-1]
0x1800067bc  cmovnz  rcx, rdx
0x1800067c0  mov     byte ptr [rcx], 0
0x1800067c3  mov     rcx, rdi; this
0x1800067c6  call    ?Normalize@CMachineId@@QEAAXXZ; CMachineId::Normalize(void)
0x1800067cb  mov     rcx, rdi; this
0x1800067ce  call    ?Normalize@CMachineId@@QEAAXXZ; CMachineId::Normalize(void)
0x1800067d3  mov     rax, rdi
0x1800067d6  mov     rcx, [rsp+88h+var_10]
0x1800067db  xor     rcx, rsp; StackCookie
0x1800067de  call    __security_check_cookie
0x1800067e3  mov     rbx, [rsp+88h+arg_8]
0x1800067eb  add     rsp, 80h
0x1800067f2  pop     rdi
0x1800067f3  retn
0x1800067f4  xor     r9d, r9d; lpArguments
0x1800067f7  xor     r8d, r8d; nNumberOfArguments
0x1800067fa  xor     edx, edx; dwExceptionFlags
0x1800067fc  mov     ecx, 8007007Bh; dwExceptionCode
0x180006801  call    cs:__imp_RaiseException
0x180006807  int     3; Trap to Debugger
0x180006808  call    cs:__imp_GetLastError
0x18000680e  test    eax, eax
0x180006810  jg      short loc_180006823
0x180006812  xor     r9d, r9d; lpArguments
0x180006815  xor     r8d, r8d; nNumberOfArguments
0x180006818  xor     edx, edx; dwExceptionFlags
0x18000681a  mov     ecx, eax; dwExceptionCode
0x18000681c  call    cs:__imp_RaiseException
0x180006822  int     3; Trap to Debugger
0x180006823  movzx   eax, ax
0x180006826  or      eax, 80070000h
0x18000682b  jmp     short loc_180006812
0x18000682d  call    cs:__imp_GetLastError
0x180006833  mov     ecx, eax; int
0x180006835  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
```
