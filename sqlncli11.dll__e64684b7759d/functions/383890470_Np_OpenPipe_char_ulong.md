# Np::OpenPipe(char *,ulong)

- ea: `0x383890470`
- end: `0x38389063d`
- name: `?OpenPipe@Np@@AEAAKPEADK@Z`
- size: `461`
- prototype: `unsigned int(Np *__hidden this, char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x383890320`

## callees

- `0x383846430`
- `0x38387ca10`
- `0x383890470`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`

## import_xrefs

- `MSVCR100!_strnicmp_l` at `0x38389050c`
- `MSVCR100!_strnicmp_l` at `0x38389050c`
- `KERNEL32!CreateFileA` at `0x383890548`
- `KERNEL32!CreateFileA` at `0x3838905c5`
- `KERNEL32!CreateFileA` at `0x383890548`
- `KERNEL32!CreateFileA` at `0x3838905c5`
- `KERNEL32!WaitNamedPipeA` at `0x38389057d`
- `KERNEL32!WaitNamedPipeA` at `0x38389057d`
- `KERNEL32!SetNamedPipeHandleState` at `0x3838905f4`
- `KERNEL32!SetNamedPipeHandleState` at `0x3838905f4`
- `KERNEL32!GetLastError` at `0x383890560`
- `KERNEL32!GetLastError` at `0x3838f9ee3`
- `KERNEL32!GetLastError` at `0x3838fa085`
- `KERNEL32!GetLastError` at `0x383890560`
- `KERNEL32!GetLastError` at `0x3838f9ee3`
- `KERNEL32!GetLastError` at `0x3838fa085`
- `KERNEL32!GetTickCount` at `0x38389051a`
- `KERNEL32!GetTickCount` at `0x38389058b`
- `KERNEL32!GetTickCount` at `0x38389051a`
- `KERNEL32!GetTickCount` at `0x38389058b`
- `KERNEL32!CloseHandle` at `0x3838fa0e4`
- `KERNEL32!CloseHandle` at `0x3838fa0e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::OpenPipe(Np *this, char *a2)
{
  char v4; // r8
  unsigned int v5; // ebp
  const CHAR *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  DWORD TickCount; // r15d
  unsigned int v10; // edi
  HANDLE FileA; // rax
  DWORD v12; // esi
  HANDLE v13; // rax
  char *v15; // r8
  __int64 v16; // rdx
  char *v17; // rcx
  DWORD LastError; // edi
  DWORD Mode; // [rsp+88h] [rbp+10h] BYREF
  __int64 v20; // [rsp+90h] [rbp+18h] BYREF

  v20 = -1;
  v4 = bidGblFlags;
  if ( (bidGblFlags & 0x20004) == 0x20004 )
  {
    if ( off_383B486A0[0] )
      bidScopeEnterA(&v20, off_383B486A0[0], *((unsigned int *)this + 11));
    v4 = bidGblFlags;
  }
  v5 = 0;
  if ( *a2 != 92 )
  {
    v5 = 87;
    if ( (v4 & 2) == 0 || !off_383B465B8[0] )
      goto LABEL_24;
    SniErrorIdFromStringId(0xC3B9u);
    v15 = off_383B465B8[0];
    v16 = 1072128;
    v17 = off_383B43F38[0];
    goto LABEL_23;
  }
  if ( a2[1] != 92 )
  {
    v5 = 87;
    if ( (v4 & 2) == 0 || !off_383B465B0[0] )
      goto LABEL_24;
    SniErrorIdFromStringId(0xC3B9u);
    v15 = off_383B465B0[0];
    v16 = 1081344;
    v17 = off_383B43F30[0];
    goto LABEL_23;
  }
  v6 = a2 + 2;
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  v8 = StrChrA_SYS(v6);
  if ( !v8 )
  {
    v5 = 87;
    if ( (bidGblFlags & 2) == 0 || !off_383B465A8[0] )
      goto LABEL_24;
    SniErrorIdFromStringId(0xC3B9u);
    v15 = off_383B465A8[0];
    v16 = 1094656;
    v17 = off_383B43F28[0];
    goto LABEL_23;
  }
  if ( _strnicmp_l("pipe\\", (const char *)(v8 + 1), 5u, 0) )
  {
    v5 = 87;
    if ( (bidGblFlags & 2) == 0 || !off_383B465A0[0] )
      goto LABEL_24;
    SniErrorIdFromStringId(0xC3B9u);
    v15 = off_383B465A0[0];
    v16 = 1106944;
    v17 = off_383B43F20[0];
LABEL_23:
    bidTraceA(v17, v16, v15, *((unsigned int *)this + 28));
LABEL_24:
    SNISetLastError(*((unsigned int *)this + 28), 87, 50105);
    goto LABEL_14;
  }
  TickCount = GetTickCount();
  v10 = 0;
  FileA = CreateFileA(a2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
  *((_QWORD *)this + 8) = FileA;
  if ( FileA != (HANDLE)-1LL )
  {
LABEL_13:
    Mode = 2;
    if ( !SetNamedPipeHandleState(*((HANDLE *)this + 8), &Mode, 0, 0) )
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_383B46568[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceA(off_383B43EE8[0], 1181696, off_383B46568[0], *((unsigned int *)this + 28));
      }
      SNISetLastError(*((unsigned int *)this + 28), LastError, 50100);
      CloseHandle(*((HANDLE *)this + 8));
      *((_QWORD *)this + 8) = -1;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46560[0] )
        bidTraceA(off_383B43EE0[0], 1187840, off_383B46560[0], LastError);
LABEL_51:
      if ( v20 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
        off_383B15058();
      return LastError;
    }
LABEL_14:
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46558[0] )
      bidTraceA(off_383B43ED8[0], 1195008, off_383B46558[0], v5);
    if ( v20 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return v5;
  }
  while ( 1 )
  {
    v12 = GetLastError();
    if ( v12 != 231 )
      break;
    if ( !WaitNamedPipeA(a2, 5000 - v10) )
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_383B46588[0] )
      {
        SniErrorIdFromStringId(0xC3DCu);
        bidTraceA(off_383B43F08[0], 1146880, off_383B46588[0], *((unsigned int *)this + 28));
      }
      SNISetLastError(*((unsigned int *)this + 28), LastError, 50140);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46580[0] )
        bidTraceA(off_383B43F00[0], 1147904, off_383B46580[0], LastError);
      goto LABEL_51;
    }
    v10 = GetTickCount() - TickCount;
    if ( v10 > 0x1388 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B46578[0] )
      {
        SniErrorIdFromStringId(0xC3DCu);
        bidTraceA(off_383B43EF8[0], 1156096, off_383B46578[0], *((unsigned int *)this + 28));
      }
      SNISetLastError(*((unsigned int *)this + 28), 231, 50140);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46570[0] )
        bidTraceA(off_383B43EF0[0], 1157120, off_383B46570[0], 231);
      if ( v20 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
        off_383B15058();
      return 1460;
    }
    v13 = CreateFileA(a2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
    *((_QWORD *)this + 8) = v13;
    if ( v13 != (HANDLE)-1LL )
      goto LABEL_13;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B46598[0] )
  {
    SniErrorIdFromStringId(0xC3DCu);
    bidTraceA(off_383B43F18[0], 1138688, off_383B46598[0], *((unsigned int *)this + 28));
  }
  SNISetLastError(*((unsigned int *)this + 28), v12, 50140);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46590[0] )
    bidTraceA(off_383B43F10[0], 1139712, off_383B46590[0], v12);
  if ( v20 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return v12;
}

```

## disassembly

```asm
0x383890470  mov     r11, rsp
0x383890473  push    rbp
0x383890474  push    rsi
0x383890475  push    rdi
0x383890476  push    r14
0x383890478  push    r15
0x38389047a  sub     rsp, 50h
0x38389047e  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x383890486  mov     [r11+8], rbx
0x38389048a  mov     r14, rdx
0x38389048d  mov     rbx, rcx
0x383890490  mov     qword ptr [r11+18h], 0FFFFFFFFFFFFFFFFh
0x383890498  mov     r8d, cs:_bidGblFlags
0x38389049f  mov     eax, r8d
0x3838904a2  and     eax, 20004h
0x3838904a7  cmp     eax, 20004h
0x3838904ac  jz      loc_3838F9CC4
0x3838904b2  xor     ebp, ebp
0x3838904b4  cmp     byte ptr [r14], 5Ch ; '\'
0x3838904b8  jnz     loc_3838F9CFB
0x3838904be  lea     rcx, [r14+1]
0x3838904c2  cmp     byte ptr [rcx], 5Ch ; '\'
0x3838904c5  jnz     loc_3838F9D55
0x3838904cb  inc     rcx; lpCurrentChar
0x3838904ce  or      rdx, 0FFFFFFFFFFFFFFFFh
0x3838904d2  nop     dword ptr [rax+00000000h]
0x3838904d9  nop     dword ptr [rax+00000000h]
0x3838904e0  inc     rdx
0x3838904e3  cmp     [rcx+rdx], bpl
0x3838904e7  jnz     short loc_3838904E0
0x3838904e9  mov     r8b, 5Ch ; '\'
0x3838904ec  call    StrChrA_SYS
0x3838904f1  test    rax, rax
0x3838904f4  jz      loc_3838F9D8B
0x3838904fa  xor     r9d, r9d; Locale
0x3838904fd  lea     r8d, [r9+5]; MaxCount
0x383890501  lea     rdx, [rax+1]; String2
0x383890505  lea     rcx, aPipe_0; "pipe\\"
0x38389050c  call    cs:__imp__strnicmp_l
0x383890512  test    eax, eax
0x383890514  jnz     loc_3838F9DC5
0x38389051a  call    cs:__imp_GetTickCount
0x383890520  mov     r15d, eax
0x383890523  mov     edi, ebp
0x383890525  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x38389052a  mov     [rsp+78h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x383890532  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x38389053a  xor     r9d, r9d; lpSecurityAttributes
0x38389053d  xor     r8d, r8d; dwShareMode
0x383890540  mov     edx, 0C0000000h; dwDesiredAccess
0x383890545  mov     rcx, r14; lpFileName
0x383890548  call    cs:__imp_CreateFileA
0x38389054e  mov     [rbx+40h], rax
0x383890552  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383890556  jnz     short loc_3838905D7
0x383890558  nop     dword ptr [rax+rax+00000000h]
0x383890560  call    cs:__imp_GetLastError
0x383890566  mov     esi, eax
0x383890568  cmp     eax, 0E7h
0x38389056d  jnz     loc_3838F9FB8
0x383890573  mov     edx, 1388h
0x383890578  sub     edx, edi; nTimeOut
0x38389057a  mov     rcx, r14; lpNamedPipeName
0x38389057d  call    cs:__imp_WaitNamedPipeA
0x383890583  test    eax, eax
0x383890585  jz      loc_3838F9EE3
0x38389058b  call    cs:__imp_GetTickCount
0x383890591  mov     edi, eax
0x383890593  sub     edi, r15d
0x383890596  cmp     edi, 1388h
0x38389059c  ja      loc_3838F9E09
0x3838905a2  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x3838905a7  mov     [rsp+78h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x3838905af  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x3838905b7  xor     r9d, r9d; lpSecurityAttributes
0x3838905ba  xor     r8d, r8d; dwShareMode
0x3838905bd  mov     edx, 0C0000000h; dwDesiredAccess
0x3838905c2  mov     rcx, r14; lpFileName
0x3838905c5  call    cs:__imp_CreateFileA
0x3838905cb  mov     [rbx+40h], rax
0x3838905cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x3838905d3  jz      short loc_383890560
0x3838905d5  jmp     short $+2
0x3838905d7  mov     [rsp+78h+Mode], 2
0x3838905e2  xor     r9d, r9d; lpCollectDataTimeout
0x3838905e5  xor     r8d, r8d; lpMaxCollectionCount
0x3838905e8  lea     rdx, [rsp+78h+Mode]; lpMode
0x3838905f0  mov     rcx, [rbx+40h]; hNamedPipe
0x3838905f4  call    cs:__imp_SetNamedPipeHandleState
0x3838905fa  test    eax, eax
0x3838905fc  jz      loc_3838FA085
0x383890602  mov     eax, cs:_bidGblFlags
0x383890608  and     eax, 20002h
0x38389060d  cmp     eax, 20002h
0x383890612  jz      loc_3838FA131
0x383890618  cmp     [rsp+78h+arg_10], 0FFFFFFFFFFFFFFFFh
0x383890621  jnz     loc_3838FA162
0x383890627  mov     eax, ebp
0x383890629  mov     rbx, [rsp+78h+arg_0]
0x383890631  add     rsp, 50h
0x383890635  pop     r15
0x383890637  pop     r14
0x383890639  pop     rdi
0x38389063a  pop     rsi
0x38389063b  pop     rbp
0x38389063c  retn
0x3838f9cc4  mov     rax, cs:off_383B486A0; "<Np::OpenPipe|API|SNI> %u#, szPipeName:"...
0x3838f9ccb  test    rax, rax
0x3838f9cce  jz      short loc_3838F9CEF
0x3838f9cd0  mov     [rsp+78h+dwCreationDisposition], 1388h
0x3838f9cd8  mov     r9, rdx
0x3838f9cdb  mov     r8d, [rcx+2Ch]
0x3838f9cdf  mov     rdx, cs:off_383B486A0; "<Np::OpenPipe|API|SNI> %u#, szPipeName:"...
0x3838f9ce6  lea     rcx, [r11+18h]
0x3838f9cea  call    _bidScopeEnterA
0x3838f9cef  mov     r8d, cs:_bidGblFlags
0x3838f9cf6  jmp     loc_3838904B2
0x3838f9cfb  mov     ebp, 57h ; 'W'
0x3838f9d00  test    r8b, 2
0x3838f9d04  jz      short loc_3838F9D40
0x3838f9d06  mov     rax, cs:off_383B465B8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9d0d  test    rax, rax
0x3838f9d10  jz      short loc_3838F9D40
0x3838f9d12  mov     ecx, 0C3B9h; unsigned int
0x3838f9d17  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f9d1c  mov     r8, cs:off_383B465B8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9d23  mov     edx, 105C00h
0x3838f9d28  mov     rcx, cs:off_383B43F38; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9d2f  mov     [rsp+78h+dwFlagsAndAttributes], ebp
0x3838f9d33  mov     r9d, [rbx+70h]
0x3838f9d37  mov     [rsp+78h+dwCreationDisposition], eax
0x3838f9d3b  call    _bidTraceA
0x3838f9d40  mov     edx, ebp
0x3838f9d42  mov     r8d, 0C3B9h
0x3838f9d48  mov     ecx, [rbx+70h]
0x3838f9d4b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838f9d50  jmp     loc_383890602
0x3838f9d55  mov     ebp, 57h ; 'W'
0x3838f9d5a  test    r8b, 2
0x3838f9d5e  jz      short loc_3838F9D40
0x3838f9d60  mov     rax, cs:off_383B465B0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9d67  test    rax, rax
0x3838f9d6a  jz      short loc_3838F9D40
0x3838f9d6c  mov     ecx, 0C3B9h; unsigned int
0x3838f9d71  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f9d76  mov     r8, cs:off_383B465B0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9d7d  mov     edx, 108000h
0x3838f9d82  mov     rcx, cs:off_383B43F30; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9d89  jmp     short loc_3838F9D2F
0x3838f9d8b  lea     ebp, [rax+57h]
0x3838f9d8e  test    byte ptr cs:_bidGblFlags, 2
0x3838f9d95  jz      short loc_3838F9D40
0x3838f9d97  mov     rax, cs:off_383B465A8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9d9e  test    rax, rax
0x3838f9da1  jz      short loc_3838F9D40
0x3838f9da3  mov     ecx, 0C3B9h; unsigned int
0x3838f9da8  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f9dad  mov     r8, cs:off_383B465A8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9db4  mov     edx, 10B400h
0x3838f9db9  mov     rcx, cs:off_383B43F28; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9dc0  jmp     loc_3838F9D2F
0x3838f9dc5  mov     ebp, 57h ; 'W'
0x3838f9dca  test    byte ptr cs:_bidGblFlags, 2
0x3838f9dd1  jz      loc_3838F9D40
0x3838f9dd7  mov     rax, cs:off_383B465A0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9dde  test    rax, rax
0x3838f9de1  jz      loc_3838F9D40
0x3838f9de7  mov     ecx, 0C3B9h; unsigned int
0x3838f9dec  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f9df1  mov     r8, cs:off_383B465A0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9df8  mov     edx, 10E400h
0x3838f9dfd  mov     rcx, cs:off_383B43F20; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9e04  jmp     loc_3838F9D2F
0x3838f9e09  test    byte ptr cs:_bidGblFlags, 2
0x3838f9e10  jz      short loc_3838F9E50
0x3838f9e12  mov     rax, cs:off_383B46578; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9e19  test    rax, rax
0x3838f9e1c  jz      short loc_3838F9E50
0x3838f9e1e  mov     ecx, 0C3DCh; unsigned int
0x3838f9e23  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f9e28  mov     [rsp+78h+dwFlagsAndAttributes], 0E7h
0x3838f9e30  mov     [rsp+78h+dwCreationDisposition], eax
0x3838f9e34  mov     r9d, [rbx+70h]
0x3838f9e38  mov     r8, cs:off_383B46578; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9e3f  mov     edx, 11A400h
0x3838f9e44  mov     rcx, cs:off_383B43EF8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9e4b  call    _bidTraceA
0x3838f9e50  mov     edx, 0E7h
0x3838f9e55  mov     r8d, 0C3DCh
0x3838f9e5b  mov     ecx, [rbx+70h]
0x3838f9e5e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838f9e63  mov     r11d, cs:_bidGblFlags
0x3838f9e6a  and     r11d, 20002h
0x3838f9e71  cmp     r11d, 20002h
0x3838f9e78  jnz     short loc_3838F9EA5
0x3838f9e7a  mov     rax, cs:off_383B46570; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x3838f9e81  test    rax, rax
0x3838f9e84  jz      short loc_3838F9EA5
0x3838f9e86  mov     r9d, 0E7h
0x3838f9e8c  mov     r8, cs:off_383B46570; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x3838f9e93  mov     edx, 11A800h
0x3838f9e98  mov     rcx, cs:off_383B43EF0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9e9f  call    _bidTraceA
0x3838f9ea4  nop
0x3838f9ea5  cmp     [rsp+78h+arg_10], 0FFFFFFFFFFFFFFFFh
0x3838f9eae  jz      short loc_3838F9ED9
0x3838f9eb0  test    byte ptr cs:_bidGblFlags, 4
0x3838f9eb7  jz      short loc_3838F9ED9
0x3838f9eb9  mov     rcx, cs:_bidID
0x3838f9ec0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838f9ec4  jz      short loc_3838F9ED9
0x3838f9ec6  lea     r9, [rsp+78h+arg_10]
0x3838f9ece  xor     r8d, r8d
0x3838f9ed1  xor     edx, edx
0x3838f9ed3  call    cs:off_383B15058
0x3838f9ed9  mov     eax, 5B4h
0x3838f9ede  jmp     loc_383890629
0x3838f9ee3  call    cs:__imp_GetLastError
0x3838f9ee9  mov     edi, eax
0x3838f9eeb  test    byte ptr cs:_bidGblFlags, 2
0x3838f9ef2  jz      short loc_3838F9F2E
0x3838f9ef4  mov     rax, cs:off_383B46588; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9efb  test    rax, rax
0x3838f9efe  jz      short loc_3838F9F2E
0x3838f9f00  mov     ecx, 0C3DCh; unsigned int
0x3838f9f05  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f9f0a  mov     [rsp+78h+dwFlagsAndAttributes], edi
0x3838f9f0e  mov     [rsp+78h+dwCreationDisposition], eax
0x3838f9f12  mov     r9d, [rbx+70h]
0x3838f9f16  mov     r8, cs:off_383B46588; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9f1d  mov     edx, 118000h
0x3838f9f22  mov     rcx, cs:off_383B43F08; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9f29  call    _bidTraceA
0x3838f9f2e  mov     r8d, 0C3DCh
0x3838f9f34  mov     edx, edi
0x3838f9f36  mov     ecx, [rbx+70h]
0x3838f9f39  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838f9f3e  mov     r11d, cs:_bidGblFlags
0x3838f9f45  and     r11d, 20002h
0x3838f9f4c  cmp     r11d, 20002h
0x3838f9f53  jnz     short loc_3838F9F7D
0x3838f9f55  mov     rax, cs:off_383B46580; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x3838f9f5c  test    rax, rax
0x3838f9f5f  jz      short loc_3838F9F7D
0x3838f9f61  mov     r9d, edi
0x3838f9f64  mov     r8, cs:off_383B46580; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x3838f9f6b  mov     edx, 118400h
0x3838f9f70  mov     rcx, cs:off_383B43F00; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9f77  call    _bidTraceA
0x3838f9f7c  nop
0x3838f9f7d  cmp     [rsp+78h+arg_10], 0FFFFFFFFFFFFFFFFh
0x3838f9f86  jz      short loc_3838F9FB1
0x3838f9f88  test    byte ptr cs:_bidGblFlags, 4
0x3838f9f8f  jz      short loc_3838F9FB1
0x3838f9f91  mov     rcx, cs:_bidID
0x3838f9f98  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838f9f9c  jz      short loc_3838F9FB1
0x3838f9f9e  lea     r9, [rsp+78h+arg_10]
0x3838f9fa6  xor     r8d, r8d
0x3838f9fa9  xor     edx, edx
0x3838f9fab  call    cs:off_383B15058
0x3838f9fb1  mov     eax, edi
0x3838f9fb3  jmp     loc_383890629
0x3838f9fb8  test    byte ptr cs:_bidGblFlags, 2
0x3838f9fbf  jz      short loc_3838F9FFB
0x3838f9fc1  mov     rax, cs:off_383B46598; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9fc8  test    rax, rax
0x3838f9fcb  jz      short loc_3838F9FFB
0x3838f9fcd  mov     ecx, 0C3DCh; unsigned int
0x3838f9fd2  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f9fd7  mov     [rsp+78h+dwFlagsAndAttributes], esi
0x3838f9fdb  mov     [rsp+78h+dwCreationDisposition], eax
0x3838f9fdf  mov     r9d, [rbx+70h]
0x3838f9fe3  mov     r8, cs:off_383B46598; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x3838f9fea  mov     edx, 116000h
0x3838f9fef  mov     rcx, cs:off_383B43F18; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f9ff6  call    _bidTraceA
0x3838f9ffb  mov     r8d, 0C3DCh
0x3838fa001  mov     edx, esi
0x3838fa003  mov     ecx, [rbx+70h]
0x3838fa006  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838fa00b  mov     r11d, cs:_bidGblFlags
0x3838fa012  and     r11d, 20002h
0x3838fa019  cmp     r11d, 20002h
0x3838fa020  jnz     short loc_3838FA04A
0x3838fa022  mov     rax, cs:off_383B46590; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x3838fa029  test    rax, rax
0x3838fa02c  jz      short loc_3838FA04A
0x3838fa02e  mov     r9d, esi
0x3838fa031  mov     r8, cs:off_383B46590; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x3838fa038  mov     edx, 116400h
0x3838fa03d  mov     rcx, cs:off_383B43F10; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa044  call    _bidTraceA
0x3838fa049  nop
0x3838fa04a  cmp     [rsp+78h+arg_10], 0FFFFFFFFFFFFFFFFh
0x3838fa053  jz      short loc_3838FA07E
0x3838fa055  test    byte ptr cs:_bidGblFlags, 4
0x3838fa05c  jz      short loc_3838FA07E
0x3838fa05e  mov     rcx, cs:_bidID
0x3838fa065  cmp     rcx, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
