# SdpGetUserSid(ushort * *)

- ea: `0x1800271ec`
- end: `0x180027446`
- name: `?SdpGetUserSid@@YAJPEAPEAG@Z`
- size: `602`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180026bf4`

## callees

- `0x1800012a4`
- `0x180026fa0`
- `0x1800271ec`
- `0x180027aa0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180027233`
- `KERNEL32!GetCurrentThread` at `0x180027233`
- `KERNEL32!GetCurrentProcess` at `0x180027273`
- `KERNEL32!GetCurrentProcess` at `0x180027273`
- `KERNEL32!GetLastError` at `0x180027259`
- `KERNEL32!GetLastError` at `0x18002728c`
- `KERNEL32!GetLastError` at `0x1800272d1`
- `KERNEL32!GetLastError` at `0x1800273b4`
- `KERNEL32!GetLastError` at `0x1800273e6`
- `KERNEL32!GetLastError` at `0x180027259`
- `KERNEL32!GetLastError` at `0x18002728c`
- `KERNEL32!GetLastError` at `0x1800272d1`
- `KERNEL32!GetLastError` at `0x1800273b4`
- `KERNEL32!GetLastError` at `0x1800273e6`
- `KERNEL32!HeapAlloc` at `0x180027376`
- `KERNEL32!HeapAlloc` at `0x180027376`
- `KERNEL32!GetProcessHeap` at `0x18002732c`
- `KERNEL32!GetProcessHeap` at `0x180027368`
- `KERNEL32!GetProcessHeap` at `0x18002732c`
- `KERNEL32!GetProcessHeap` at `0x180027368`
- `KERNEL32!HeapFree` at `0x18002733a`
- `KERNEL32!HeapFree` at `0x18002733a`
- `KERNEL32!CloseHandle` at `0x18002734e`
- `KERNEL32!CloseHandle` at `0x18002734e`
- `KERNEL32!LocalFree` at `0x180027314`
- `KERNEL32!LocalFree` at `0x180027314`
- `ADVAPI32!OpenProcessToken` at `0x180027282`
- `ADVAPI32!OpenProcessToken` at `0x180027282`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800273dc`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800273dc`
- `ADVAPI32!OpenThreadToken` at `0x180027249`
- `ADVAPI32!OpenThreadToken` at `0x180027249`
- `ADVAPI32!GetTokenInformation` at `0x1800272c7`
- `ADVAPI32!GetTokenInformation` at `0x1800273aa`
- `ADVAPI32!GetTokenInformation` at `0x1800272c7`
- `ADVAPI32!GetTokenInformation` at `0x1800273aa`

## string_xrefs

- `0x1800272ff`: `SdpGetUserSid`
- `0x18002741d`: `SdpGetUserSid`

## pseudocode

```c
__int64 __fastcall SdpGetUserSid(unsigned __int16 **a1)
{
  unsigned __int16 *v1; // rsi
  PSID *v2; // r14
  signed int v4; // ebx
  unsigned int v5; // r8d
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  DWORD v13; // ebx
  HANDLE ProcessHeap; // rax
  signed int v15; // eax
  signed int v16; // eax
  int v17; // eax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int16 *v20; // [rsp+80h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+58h] BYREF

  v1 = 0;
  hMem = 0;
  v2 = 0;
  v20 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = 2280;
LABEL_19:
    SdpDebugTrace(1u, L"SdpGetUserSid", v5, v4);
    goto LABEL_20;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        goto LABEL_12;
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v4 < 0 )
    {
      v5 = 2287;
      goto LABEL_19;
    }
  }
LABEL_12:
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_17;
  v10 = GetLastError();
  v4 = v10;
  if ( v10 > 0 )
    v4 = (unsigned __int16)v10 | 0x80070000;
  if ( v4 != -2147024774 )
  {
    if ( v4 < 0 )
    {
LABEL_18:
      v5 = 2295;
      goto LABEL_19;
    }
LABEL_17:
    v4 = -2147418113;
    goto LABEL_18;
  }
  v13 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  v2 = (PSID *)HeapAlloc(ProcessHeap, 0, v13);
  if ( !v2 )
  {
    v4 = -2147024882;
    v5 = 2299;
    goto LABEL_19;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
  {
    v15 = GetLastError();
    v4 = v15;
    if ( v15 > 0 )
      v4 = (unsigned __int16)v15 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 2302;
      goto LABEL_19;
    }
  }
  if ( !ConvertSidToStringSidW(*v2, (LPWSTR *)&hMem) )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 > 0 )
      v4 = (unsigned __int16)v16 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 2305;
      goto LABEL_19;
    }
  }
  v17 = SdpStrCpy(&v20, (const unsigned __int16 *)hMem);
  v4 = v17;
  if ( v17 >= 0 )
  {
    *a1 = v20;
  }
  else
  {
    SdpDebugTrace(1u, L"SdpGetUserSid", 0x904u, v17);
    v1 = v20;
  }
LABEL_20:
  if ( hMem )
    LocalFree(hMem);
  if ( v1 )
    operator delete(v1);
  if ( v2 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v2);
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800271ec  push    rbp
0x1800271ee  push    rbx
0x1800271ef  push    rsi
0x1800271f0  push    rdi
0x1800271f1  push    r13
0x1800271f3  push    r14
0x1800271f5  push    r15
0x1800271f7  mov     rbp, rsp
0x1800271fa  sub     rsp, 30h
0x1800271fe  xor     esi, esi
0x180027200  mov     [rbp+hMem], 0
0x180027208  xor     r14d, r14d
0x18002720b  mov     [rbp+arg_10], rsi
0x18002720f  mov     [rbp+TokenHandle], rsi
0x180027213  mov     r15, rcx
0x180027216  mov     [rbp+TokenInformationLength], esi
0x180027219  test    rcx, rcx
0x18002721c  jnz     short loc_180027233
0x18002721e  mov     ebx, 80070057h
0x180027223  mov     r8d, 8E8h
0x180027229  mov     ecx, 1
0x18002722e  jmp     loc_1800272FC
0x180027233  call    cs:__imp_GetCurrentThread
0x180027239  xor     r8d, r8d; OpenAsSelf
0x18002723c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180027240  mov     rcx, rax; ThreadHandle
0x180027243  lea     edi, [r8+8]
0x180027247  mov     edx, edi; DesiredAccess
0x180027249  call    cs:__imp_OpenThreadToken
0x18002724f  mov     r13d, 80070000h
0x180027255  test    eax, eax
0x180027257  jnz     short loc_1800272AD
0x180027259  call    cs:__imp_GetLastError
0x18002725f  mov     ebx, eax
0x180027261  test    eax, eax
0x180027263  jle     short loc_18002726B
0x180027265  movzx   ebx, ax
0x180027268  or      ebx, r13d
0x18002726b  cmp     ebx, 800703F0h
0x180027271  jnz     short loc_18002729E
0x180027273  call    cs:__imp_GetCurrentProcess
0x180027279  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002727d  mov     edx, edi; DesiredAccess
0x18002727f  mov     rcx, rax; ProcessHandle
0x180027282  call    cs:__imp_OpenProcessToken
0x180027288  test    eax, eax
0x18002728a  jnz     short loc_1800272AD
0x18002728c  call    cs:__imp_GetLastError
0x180027292  mov     ebx, eax
0x180027294  test    eax, eax
0x180027296  jle     short loc_18002729E
0x180027298  movzx   ebx, ax
0x18002729b  or      ebx, r13d
0x18002729e  test    ebx, ebx
0x1800272a0  jns     short loc_1800272AD
0x1800272a2  mov     r8d, 8EFh
0x1800272a8  jmp     loc_180027229
0x1800272ad  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800272b1  lea     rax, [rbp+TokenInformationLength]
0x1800272b5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800272b9  xor     r8d, r8d; TokenInformation
0x1800272bc  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800272c1  lea     edi, [r8+1]
0x1800272c5  mov     edx, edi; TokenInformationClass
0x1800272c7  call    cs:__imp_GetTokenInformation
0x1800272cd  test    eax, eax
0x1800272cf  jnz     short loc_1800272EF
0x1800272d1  call    cs:__imp_GetLastError
0x1800272d7  mov     ebx, eax
0x1800272d9  test    eax, eax
0x1800272db  jle     short loc_1800272E3
0x1800272dd  movzx   ebx, ax
0x1800272e0  or      ebx, r13d
0x1800272e3  cmp     ebx, 8007007Ah
0x1800272e9  jz      short loc_180027365
0x1800272eb  test    ebx, ebx
0x1800272ed  js      short loc_1800272F4
0x1800272ef  mov     ebx, 8000FFFFh
0x1800272f4  mov     r8d, 8F7h; int
0x1800272fa  mov     ecx, edi; Level
0x1800272fc  mov     r9d, ebx; int
0x1800272ff  lea     rdx, aSdpgetusersid; "SdpGetUserSid"
0x180027306  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002730b  mov     rcx, [rbp+hMem]; hMem
0x18002730f  test    rcx, rcx
0x180027312  jz      short loc_18002731A
0x180027314  call    cs:__imp_LocalFree
0x18002731a  test    rsi, rsi
0x18002731d  jz      short loc_180027327
0x18002731f  mov     rcx, rsi; Block
0x180027322  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027327  test    r14, r14
0x18002732a  jz      short loc_180027340
0x18002732c  call    cs:__imp_GetProcessHeap
0x180027332  mov     r8, r14; lpMem
0x180027335  xor     edx, edx; dwFlags
0x180027337  mov     rcx, rax; hHeap
0x18002733a  call    cs:__imp_HeapFree
0x180027340  mov     rcx, [rbp+TokenHandle]; hObject
0x180027344  lea     rax, [rcx-1]
0x180027348  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002734c  ja      short loc_180027354
0x18002734e  call    cs:__imp_CloseHandle
0x180027354  mov     eax, ebx
0x180027356  add     rsp, 30h
0x18002735a  pop     r15
0x18002735c  pop     r14
0x18002735e  pop     r13
0x180027360  pop     rdi
0x180027361  pop     rsi
0x180027362  pop     rbx
0x180027363  pop     rbp
0x180027364  retn
0x180027365  mov     ebx, [rbp+TokenInformationLength]
0x180027368  call    cs:__imp_GetProcessHeap
0x18002736e  mov     r8d, ebx; dwBytes
0x180027371  xor     edx, edx; dwFlags
0x180027373  mov     rcx, rax; hHeap
0x180027376  call    cs:__imp_HeapAlloc
0x18002737c  mov     r14, rax
0x18002737f  test    rax, rax
0x180027382  jnz     short loc_180027394
0x180027384  mov     ebx, 8007000Eh
0x180027389  mov     r8d, 8FBh
0x18002738f  jmp     loc_1800272FA
0x180027394  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180027398  lea     rax, [rbp+TokenInformationLength]
0x18002739c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800273a0  mov     r8, r14; TokenInformation
0x1800273a3  mov     edx, edi; TokenInformationClass
0x1800273a5  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800273aa  call    cs:__imp_GetTokenInformation
0x1800273b0  test    eax, eax
0x1800273b2  jnz     short loc_1800273D5
0x1800273b4  call    cs:__imp_GetLastError
0x1800273ba  mov     ebx, eax
0x1800273bc  test    eax, eax
0x1800273be  jle     short loc_1800273C6
0x1800273c0  movzx   ebx, ax
0x1800273c3  or      ebx, r13d
0x1800273c6  test    ebx, ebx
0x1800273c8  jns     short loc_1800273D5
0x1800273ca  mov     r8d, 8FEh
0x1800273d0  jmp     loc_1800272FA
0x1800273d5  mov     rcx, [r14]; Sid
0x1800273d8  lea     rdx, [rbp+hMem]; StringSid
0x1800273dc  call    cs:__imp_ConvertSidToStringSidW
0x1800273e2  test    eax, eax
0x1800273e4  jnz     short loc_180027407
0x1800273e6  call    cs:__imp_GetLastError
0x1800273ec  mov     ebx, eax
0x1800273ee  test    eax, eax
0x1800273f0  jle     short loc_1800273F8
0x1800273f2  movzx   ebx, ax
0x1800273f5  or      ebx, r13d
0x1800273f8  test    ebx, ebx
0x1800273fa  jns     short loc_180027407
0x1800273fc  mov     r8d, 901h
0x180027402  jmp     loc_1800272FA
0x180027407  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x18002740b  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18002740f  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180027414  mov     ebx, eax
0x180027416  test    eax, eax
0x180027418  jns     short loc_18002743A
0x18002741a  mov     r9d, eax; int
0x18002741d  lea     rdx, aSdpgetusersid; "SdpGetUserSid"
0x180027424  mov     r8d, 904h; int
0x18002742a  mov     ecx, edi; Level
0x18002742c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027431  mov     rsi, [rbp+arg_10]
0x180027435  jmp     loc_18002730B
0x18002743a  mov     rax, [rbp+arg_10]
0x18002743e  mov     [r15], rax
0x180027441  jmp     loc_18002730B
```
