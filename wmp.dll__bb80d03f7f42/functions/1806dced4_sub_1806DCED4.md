# sub_1806DCED4

- ea: `0x1806dced4`
- end: `0x1806dd5a5`
- name: `sub_1806DCED4`
- size: `1745`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1806dda54`

## callees

- `0x180121ad0`
- `0x180159430`
- `0x18015947c`
- `0x180184410`
- `0x1801b79bc`
- `0x1801b7bdc`
- `0x1806dcbd4`
- `0x1806dced4`
- `0x18074be40`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1806dd426`
- `KERNEL32!CreateThread` at `0x1806dd426`
- `KERNEL32!CreateEventW` at `0x1806dd153`
- `KERNEL32!CreateEventW` at `0x1806dd2ef`
- `KERNEL32!CreateEventW` at `0x1806dd153`
- `KERNEL32!CreateEventW` at `0x1806dd2ef`
- `KERNEL32!SetEvent` at `0x1806dd26c`
- `KERNEL32!SetEvent` at `0x1806dd26c`
- `KERNEL32!GetCurrentProcess` at `0x1806dd1cc`
- `KERNEL32!GetCurrentProcess` at `0x1806dd1df`
- `KERNEL32!GetCurrentProcess` at `0x1806dd365`
- `KERNEL32!GetCurrentProcess` at `0x1806dd378`
- `KERNEL32!GetCurrentProcess` at `0x1806dd1cc`
- `KERNEL32!GetCurrentProcess` at `0x1806dd1df`
- `KERNEL32!GetCurrentProcess` at `0x1806dd365`
- `KERNEL32!GetCurrentProcess` at `0x1806dd378`
- `KERNEL32!CloseHandle` at `0x1806dd4b7`
- `KERNEL32!CloseHandle` at `0x1806dd4cf`
- `KERNEL32!CloseHandle` at `0x1806dd4ef`
- `KERNEL32!CloseHandle` at `0x1806dd508`
- `KERNEL32!CloseHandle` at `0x1806dd521`
- `KERNEL32!CloseHandle` at `0x1806dd53a`
- `KERNEL32!CloseHandle` at `0x1806dd4b7`
- `KERNEL32!CloseHandle` at `0x1806dd4cf`
- `KERNEL32!CloseHandle` at `0x1806dd4ef`
- `KERNEL32!CloseHandle` at `0x1806dd508`
- `KERNEL32!CloseHandle` at `0x1806dd521`
- `KERNEL32!CloseHandle` at `0x1806dd53a`
- `KERNEL32!LeaveCriticalSection` at `0x1806dcfad`
- `KERNEL32!LeaveCriticalSection` at `0x1806dd102`
- `KERNEL32!LeaveCriticalSection` at `0x1806dcfad`
- `KERNEL32!LeaveCriticalSection` at `0x1806dd102`
- `KERNEL32!EnterCriticalSection` at `0x1806dcf64`
- `KERNEL32!EnterCriticalSection` at `0x1806dd003`
- `KERNEL32!EnterCriticalSection` at `0x1806dcf64`
- `KERNEL32!EnterCriticalSection` at `0x1806dd003`
- `KERNEL32!GetLastError` at `0x1806dd16d`
- `KERNEL32!GetLastError` at `0x1806dd281`
- `KERNEL32!GetLastError` at `0x1806dd309`
- `KERNEL32!GetLastError` at `0x1806dd440`
- `KERNEL32!GetLastError` at `0x1806dd16d`
- `KERNEL32!GetLastError` at `0x1806dd281`
- `KERNEL32!GetLastError` at `0x1806dd309`
- `KERNEL32!GetLastError` at `0x1806dd440`
- `KERNEL32!DuplicateHandle` at `0x1806dd20d`
- `KERNEL32!DuplicateHandle` at `0x1806dd3a6`
- `KERNEL32!DuplicateHandle` at `0x1806dd20d`
- `KERNEL32!DuplicateHandle` at `0x1806dd3a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1806dd028`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1806dd028`

## pseudocode

```c
__int64 __fastcall sub_1806DCED4(__int64 a1, unsigned int a2)
{
  PVOID *v3; // rcx
  signed int Instance; // ebx
  PVOID *v5; // rcx
  HANDLE *v6; // rax
  HANDLE *v7; // r14
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  void *v11; // rdi
  void *v12; // rbx
  HANDLE v13; // rax
  HANDLE *v14; // rbp
  BOOL v15; // edi
  signed int v16; // eax
  HANDLE v17; // rax
  signed int v18; // eax
  HANDLE v19; // rax
  void *v20; // rdi
  void *v21; // rbx
  HANDLE v22; // rax
  HANDLE *v23; // r15
  BOOL v24; // edi
  HANDLE Thread; // rax
  signed int v26; // eax
  PVOID *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  HANDLE v30; // rcx
  HANDLE v31; // rcx
  unsigned int v33; // [rsp+98h] [rbp+10h] BYREF

  v33 = a2;
  v3 = (PVOID *)RequestContext;
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_180121AD0(*((_QWORD *)RequestContext + 2), 33, qword_180872238, a2);
    v3 = (PVOID *)RequestContext;
  }
  if ( v3 != &RequestContext && (*((_DWORD *)v3 + 7) & 0x200000) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    sub_180184410(v3[2], 34, qword_180872238);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  sub_1806DCBD4(a1 + 48, &v33);
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_180184410(*((_QWORD *)RequestContext + 2), 35, qword_180872238);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  if ( *(_QWORD *)(a1 + 104) || *(_DWORD *)(a1 + 116) != 1 )
    goto LABEL_33;
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_180184410(*((_QWORD *)RequestContext + 2), 36, qword_180872238);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  Instance = CoCreateInstance(&stru_180838668, 0, 1u, &stru_1808056F0, (LPVOID *)(a1 + 104));
  v5 = (PVOID *)RequestContext;
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_180121AD0(*((_QWORD *)RequestContext + 2), 37, qword_180872238, (unsigned int)Instance);
    v5 = (PVOID *)RequestContext;
  }
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, __int64))(**(_QWORD **)(a1 + 104) + 24LL))(
                 *(_QWORD *)(a1 + 104),
                 *(_QWORD *)(a1 + 8),
                 qword_180872228,
                 a1 + 112);
    v5 = (PVOID *)RequestContext;
    if ( RequestContext == &RequestContext )
      goto LABEL_32;
    if ( (*((_DWORD *)RequestContext + 7) & 0x200000) != 0 && *((_BYTE *)RequestContext + 25) >= 5u )
    {
      sub_1801B79BC(*((_QWORD *)RequestContext + 2), 38, qword_180872238, (unsigned int)Instance, *(_DWORD *)(a1 + 112));
      v5 = (PVOID *)RequestContext;
    }
  }
  if ( v5 != &RequestContext && (*((_DWORD *)v5 + 7) & 0x200000) != 0 && *((_BYTE *)v5 + 25) >= 5u )
    sub_180184410(v5[2], 39, qword_180872238);
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  if ( Instance < 0 )
  {
LABEL_99:
    v27 = (PVOID *)RequestContext;
    goto LABEL_100;
  }
LABEL_33:
  v6 = (HANDLE *)sub_180159430(24);
  v7 = v6;
  if ( !v6 )
  {
    Instance = -2147024882;
    goto LABEL_90;
  }
  *v6 = (HANDLE)a1;
  v6[1] = 0;
  v6[2] = 0;
  if ( !*(_QWORD *)(a1 + 32) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a1 + 32) = EventW;
    if ( EventW )
    {
      Instance = 0;
    }
    else
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
    }
    if ( RequestContext != &RequestContext
      && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
      && *((_BYTE *)RequestContext + 25) >= 5u )
    {
      sub_1801B7BDC(*((_QWORD *)RequestContext + 2), 40, qword_180872238, (unsigned int)Instance, *(_QWORD *)(a1 + 32));
    }
    if ( Instance < 0 )
      goto LABEL_90;
  }
  CurrentProcess = GetCurrentProcess();
  v11 = *(void **)(a1 + 32);
  v12 = CurrentProcess;
  v13 = GetCurrentProcess();
  v14 = v7 + 1;
  v15 = DuplicateHandle(v13, v11, v12, v7 + 1, 0, 0, 2u);
  Instance = !v15 ? 0x80070006 : 0;
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_180121AD0(*((_QWORD *)RequestContext + 2), 41, qword_180872238, (unsigned int)Instance);
  }
  if ( !v15 )
    goto LABEL_90;
  if ( SetEvent(*(HANDLE *)(a1 + 32)) )
  {
    Instance = 0;
  }
  else
  {
    v16 = GetLastError();
    Instance = v16;
    if ( v16 > 0 )
      Instance = (unsigned __int16)v16 | 0x80070000;
  }
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_180121AD0(*((_QWORD *)RequestContext + 2), 42, qword_180872238, (unsigned int)Instance);
  }
  if ( Instance < 0 )
    goto LABEL_90;
  if ( !*(_QWORD *)(a1 + 40) )
  {
    v17 = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a1 + 40) = v17;
    if ( v17 )
    {
      Instance = 0;
    }
    else
    {
      v18 = GetLastError();
      Instance = v18;
      if ( v18 > 0 )
        Instance = (unsigned __int16)v18 | 0x80070000;
    }
    if ( RequestContext != &RequestContext
      && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
      && *((_BYTE *)RequestContext + 25) >= 5u )
    {
      sub_1801B7BDC(*((_QWORD *)RequestContext + 2), 43, qword_180872238, (unsigned int)Instance, *(_QWORD *)(a1 + 40));
    }
    if ( Instance < 0 )
      goto LABEL_90;
  }
  v19 = GetCurrentProcess();
  v20 = *(void **)(a1 + 40);
  v21 = v19;
  v22 = GetCurrentProcess();
  v23 = v7 + 2;
  v24 = DuplicateHandle(v22, v20, v21, v7 + 2, 0, 0, 2u);
  Instance = !v24 ? 0x80070006 : 0;
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_180121AD0(*((_QWORD *)RequestContext + 2), 44, qword_180872238, (unsigned int)Instance);
  }
  if ( !v24 )
    goto LABEL_90;
  if ( *(_QWORD *)(a1 + 24) )
  {
    if ( *v23 )
    {
      CloseHandle(*v23);
      *v23 = 0;
    }
    if ( *v14 )
    {
      CloseHandle(*v14);
      *v14 = 0;
    }
    goto LABEL_98;
  }
  Thread = CreateThread(0, 0, sub_1806DDD40, v7, 0, 0);
  *(_QWORD *)(a1 + 24) = Thread;
  if ( Thread )
  {
    Instance = 0;
  }
  else
  {
    v26 = GetLastError();
    Instance = v26;
    if ( v26 > 0 )
      Instance = (unsigned __int16)v26 | 0x80070000;
  }
  v27 = (PVOID *)RequestContext;
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x200000) != 0
    && *((_BYTE *)RequestContext + 25) >= 5u )
  {
    sub_1801B7BDC(*((_QWORD *)RequestContext + 2), 45, qword_180872238, (unsigned int)Instance, *(_QWORD *)(a1 + 24));
    v27 = (PVOID *)RequestContext;
  }
  if ( Instance < 0 )
  {
LABEL_90:
    v28 = *(void **)(a1 + 40);
    if ( v28 )
    {
      CloseHandle(v28);
      *(_QWORD *)(a1 + 40) = 0;
    }
    v29 = *(void **)(a1 + 32);
    if ( v29 )
    {
      CloseHandle(v29);
      *(_QWORD *)(a1 + 32) = 0;
    }
    v30 = v7[2];
    if ( v30 )
    {
      CloseHandle(v30);
      v7[2] = 0;
    }
    v31 = v7[1];
    if ( v31 )
    {
      CloseHandle(v31);
      v7[1] = 0;
    }
LABEL_98:
    j_j__o_free(v7);
    goto LABEL_99;
  }
LABEL_100:
  if ( v27 != &RequestContext && (*((_DWORD *)v27 + 7) & 0x200000) != 0 && *((_BYTE *)v27 + 25) >= 5u )
    sub_180121AD0(v27[2], 46, qword_180872238, (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1806dced4  mov     [rsp+arg_8], edx
0x1806dced8  push    rbx
0x1806dced9  push    rbp
0x1806dceda  push    rsi
0x1806dcedb  push    rdi
0x1806dcedc  push    r12
0x1806dcede  push    r13
0x1806dcee0  push    r14
0x1806dcee2  push    r15
0x1806dcee4  sub     rsp, 48h
0x1806dcee8  mov     r9d, edx
0x1806dceeb  mov     rsi, rcx
0x1806dceee  mov     rcx, cs:RequestContext
0x1806dcef5  lea     r14, RequestContext
0x1806dcefc  lea     rbp, qword_180872238
0x1806dcf03  mov     r13b, 5
0x1806dcf06  mov     r15d, 200000h
0x1806dcf0c  cmp     rcx, r14
0x1806dcf0f  jz      short loc_1806DCF35
0x1806dcf11  test    [rcx+1Ch], r15d
0x1806dcf15  jz      short loc_1806DCF35
0x1806dcf17  cmp     [rcx+19h], r13b
0x1806dcf1b  jb      short loc_1806DCF35
0x1806dcf1d  mov     rcx, [rcx+10h]
0x1806dcf21  mov     edx, 21h ; '!'
0x1806dcf26  mov     r8, rbp
0x1806dcf29  call    sub_180121AD0
0x1806dcf2e  mov     rcx, cs:RequestContext
0x1806dcf35  xor     r12d, r12d
0x1806dcf38  mov     ebx, r12d
0x1806dcf3b  cmp     rcx, r14
0x1806dcf3e  jz      short loc_1806DCF5D
0x1806dcf40  test    [rcx+1Ch], r15d
0x1806dcf44  jz      short loc_1806DCF5D
0x1806dcf46  cmp     [rcx+19h], r13b
0x1806dcf4a  jb      short loc_1806DCF5D
0x1806dcf4c  mov     rcx, [rcx+10h]
0x1806dcf50  lea     edx, [r12+22h]
0x1806dcf55  mov     r8, rbp
0x1806dcf58  call    sub_180184410
0x1806dcf5d  lea     rdi, [rsi+40h]
0x1806dcf61  mov     rcx, rdi; lpCriticalSection
0x1806dcf64  call    cs:EnterCriticalSection
0x1806dcf6b  nop     dword ptr [rax+rax+00h]
0x1806dcf70  lea     rcx, [rsi+30h]
0x1806dcf74  lea     rdx, [rsp+88h+arg_8]
0x1806dcf7c  call    sub_1806DCBD4
0x1806dcf81  mov     rcx, cs:RequestContext
0x1806dcf88  cmp     rcx, r14
0x1806dcf8b  jz      short loc_1806DCFAA
0x1806dcf8d  test    [rcx+1Ch], r15d
0x1806dcf91  jz      short loc_1806DCFAA
0x1806dcf93  cmp     [rcx+19h], r13b
0x1806dcf97  jb      short loc_1806DCFAA
0x1806dcf99  mov     rcx, [rcx+10h]
0x1806dcf9d  mov     edx, 23h ; '#'
0x1806dcfa2  mov     r8, rbp
0x1806dcfa5  call    sub_180184410
0x1806dcfaa  mov     rcx, rdi; lpCriticalSection
0x1806dcfad  call    cs:LeaveCriticalSection
0x1806dcfb4  nop     dword ptr [rax+rax+00h]
0x1806dcfb9  lea     r14, [rsi+68h]
0x1806dcfbd  cmp     [r14], r12
0x1806dcfc0  jnz     loc_1806DD116
0x1806dcfc6  cmp     dword ptr [rsi+74h], 1
0x1806dcfca  jnz     loc_1806DD116
0x1806dcfd0  mov     rcx, cs:RequestContext
0x1806dcfd7  lea     rax, RequestContext
0x1806dcfde  cmp     rcx, rax
0x1806dcfe1  jz      short loc_1806DD000
0x1806dcfe3  test    [rcx+1Ch], r15d
0x1806dcfe7  jz      short loc_1806DD000
0x1806dcfe9  cmp     [rcx+19h], r13b
0x1806dcfed  jb      short loc_1806DD000
0x1806dcfef  mov     rcx, [rcx+10h]
0x1806dcff3  mov     edx, 24h ; '$'
0x1806dcff8  mov     r8, rbp
0x1806dcffb  call    sub_180184410
0x1806dd000  mov     rcx, rdi; lpCriticalSection
0x1806dd003  call    cs:EnterCriticalSection
0x1806dd00a  nop     dword ptr [rax+rax+00h]
0x1806dd00f  xor     edx, edx; pUnkOuter
0x1806dd011  mov     [rsp+88h+ppv], r14; ppv
0x1806dd016  lea     r9, stru_1808056F0; riid
0x1806dd01d  lea     rcx, stru_180838668; rclsid
0x1806dd024  lea     r8d, [rdx+1]; dwClsContext
0x1806dd028  call    cs:CoCreateInstance
0x1806dd02f  nop     dword ptr [rax+rax+00h]
0x1806dd034  mov     ebx, eax
0x1806dd036  mov     rcx, cs:RequestContext
0x1806dd03d  lea     rax, RequestContext
0x1806dd044  cmp     rcx, rax
0x1806dd047  jz      short loc_1806DD070
0x1806dd049  test    [rcx+1Ch], r15d
0x1806dd04d  jz      short loc_1806DD070
0x1806dd04f  cmp     [rcx+19h], r13b
0x1806dd053  jb      short loc_1806DD070
0x1806dd055  mov     rcx, [rcx+10h]
0x1806dd059  mov     edx, 25h ; '%'
0x1806dd05e  mov     r9d, ebx
0x1806dd061  mov     r8, rbp
0x1806dd064  call    sub_180121AD0
0x1806dd069  mov     rcx, cs:RequestContext
0x1806dd070  test    ebx, ebx
0x1806dd072  js      short loc_1806DD0D6
0x1806dd074  mov     rcx, [r14]
0x1806dd077  lea     r9, [rsi+70h]
0x1806dd07b  mov     rdx, [rsi+8]
0x1806dd07f  lea     r8, qword_180872228
0x1806dd086  mov     rax, [rcx]
0x1806dd089  mov     rax, [rax+18h]
0x1806dd08d  call    cs:__guard_dispatch_icall_fptr
0x1806dd093  mov     ebx, eax
0x1806dd095  mov     rcx, cs:RequestContext
0x1806dd09c  lea     rax, RequestContext
0x1806dd0a3  cmp     rcx, rax
0x1806dd0a6  jz      short loc_1806DD0FF
0x1806dd0a8  test    [rcx+1Ch], r15d
0x1806dd0ac  jz      short loc_1806DD0D6
0x1806dd0ae  cmp     [rcx+19h], r13b
0x1806dd0b2  jb      short loc_1806DD0D6
0x1806dd0b4  mov     eax, [rsi+70h]
0x1806dd0b7  mov     edx, 26h ; '&'
0x1806dd0bc  mov     rcx, [rcx+10h]
0x1806dd0c0  mov     r9d, ebx
0x1806dd0c3  mov     r8, rbp
0x1806dd0c6  mov     dword ptr [rsp+88h+ppv], eax
0x1806dd0ca  call    sub_1801B79BC
0x1806dd0cf  mov     rcx, cs:RequestContext
0x1806dd0d6  lea     r14, RequestContext
0x1806dd0dd  cmp     rcx, r14
0x1806dd0e0  jz      short loc_1806DD0FF
0x1806dd0e2  test    [rcx+1Ch], r15d
0x1806dd0e6  jz      short loc_1806DD0FF
0x1806dd0e8  cmp     [rcx+19h], r13b
0x1806dd0ec  jb      short loc_1806DD0FF
0x1806dd0ee  mov     rcx, [rcx+10h]
0x1806dd0f2  mov     edx, 27h ; '''
0x1806dd0f7  mov     r8, rbp
0x1806dd0fa  call    sub_180184410
0x1806dd0ff  mov     rcx, rdi; lpCriticalSection
0x1806dd102  call    cs:LeaveCriticalSection
0x1806dd109  nop     dword ptr [rax+rax+00h]
0x1806dd10e  test    ebx, ebx
0x1806dd110  js      loc_1806DD557
0x1806dd116  mov     ecx, 18h
0x1806dd11b  call    sub_180159430
0x1806dd120  mov     r14, rax
0x1806dd123  test    rax, rax
0x1806dd126  jz      loc_1806DD4E1
0x1806dd12c  mov     [rax], rsi
0x1806dd12f  mov     [rax+8], r12
0x1806dd133  mov     [rax+10h], r12
0x1806dd137  test    ebx, ebx
0x1806dd139  js      loc_1806DD4E6
0x1806dd13f  cmp     [rsi+20h], r12
0x1806dd143  jnz     loc_1806DD1CC
0x1806dd149  xor     r9d, r9d; lpName
0x1806dd14c  xor     r8d, r8d; bInitialState
0x1806dd14f  xor     edx, edx; bManualReset
0x1806dd151  xor     ecx, ecx; lpEventAttributes
0x1806dd153  call    cs:CreateEventW
0x1806dd15a  nop     dword ptr [rax+rax+00h]
0x1806dd15f  mov     [rsi+20h], rax
0x1806dd163  test    rax, rax
0x1806dd166  jz      short loc_1806DD16D
0x1806dd168  mov     ebx, r12d
0x1806dd16b  jmp     short loc_1806DD188
0x1806dd16d  call    cs:GetLastError
0x1806dd174  nop     dword ptr [rax+rax+00h]
0x1806dd179  mov     ebx, eax
0x1806dd17b  test    eax, eax
0x1806dd17d  jle     short loc_1806DD188
0x1806dd17f  movzx   ebx, ax
0x1806dd182  or      ebx, 80070000h
0x1806dd188  mov     rcx, cs:RequestContext
0x1806dd18f  lea     rdi, RequestContext
0x1806dd196  cmp     rcx, rdi
0x1806dd199  jz      short loc_1806DD1C4
0x1806dd19b  test    [rcx+1Ch], r15d
0x1806dd19f  jz      short loc_1806DD1C4
0x1806dd1a1  cmp     [rcx+19h], r13b
0x1806dd1a5  jb      short loc_1806DD1C4
0x1806dd1a7  mov     rax, [rsi+20h]
0x1806dd1ab  mov     edx, 28h ; '('
0x1806dd1b0  mov     rcx, [rcx+10h]
0x1806dd1b4  mov     r9d, ebx
0x1806dd1b7  mov     r8, rbp
0x1806dd1ba  mov     [rsp+88h+ppv], rax
0x1806dd1bf  call    sub_1801B7BDC
0x1806dd1c4  test    ebx, ebx
0x1806dd1c6  js      loc_1806DD4E6
0x1806dd1cc  call    cs:GetCurrentProcess
0x1806dd1d3  nop     dword ptr [rax+rax+00h]
0x1806dd1d8  mov     rdi, [rsi+20h]
0x1806dd1dc  mov     rbx, rax
0x1806dd1df  call    cs:GetCurrentProcess
0x1806dd1e6  nop     dword ptr [rax+rax+00h]
0x1806dd1eb  mov     [rsp+88h+dwOptions], 2; dwOptions
0x1806dd1f3  lea     rbp, [r14+8]
0x1806dd1f7  mov     r9, rbp; lpTargetHandle
0x1806dd1fa  mov     [rsp+88h+bInheritHandle], r12d; bInheritHandle
0x1806dd1ff  mov     rcx, rax; hSourceProcessHandle
0x1806dd202  mov     dword ptr [rsp+88h+ppv], r12d; dwDesiredAccess
0x1806dd207  mov     r8, rbx; hTargetProcessHandle
0x1806dd20a  mov     rdx, rdi; hSourceHandle
0x1806dd20d  call    cs:DuplicateHandle
0x1806dd214  nop     dword ptr [rax+rax+00h]
0x1806dd219  mov     edi, eax
0x1806dd21b  lea     ecx, [rax-1]
0x1806dd21e  neg     ecx
0x1806dd220  sbb     ebx, ebx
0x1806dd222  and     ebx, 80070006h
0x1806dd228  mov     rcx, cs:RequestContext
0x1806dd22f  lea     rax, RequestContext
0x1806dd236  cmp     rcx, rax
0x1806dd239  jz      short loc_1806DD25F
0x1806dd23b  test    [rcx+1Ch], r15d
0x1806dd23f  jz      short loc_1806DD25F
0x1806dd241  cmp     [rcx+19h], r13b
0x1806dd245  jb      short loc_1806DD25F
0x1806dd247  mov     rcx, [rcx+10h]
0x1806dd24b  lea     r8, qword_180872238
0x1806dd252  mov     edx, 29h ; ')'
0x1806dd257  mov     r9d, ebx
0x1806dd25a  call    sub_180121AD0
0x1806dd25f  cmp     edi, 1
0x1806dd262  jnz     loc_1806DD4E6
0x1806dd268  mov     rcx, [rsi+20h]; hEvent
0x1806dd26c  call    cs:SetEvent
0x1806dd273  nop     dword ptr [rax+rax+00h]
0x1806dd278  cmp     eax, edi
0x1806dd27a  jnz     short loc_1806DD281
0x1806dd27c  mov     ebx, r12d
0x1806dd27f  jmp     short loc_1806DD29C
0x1806dd281  call    cs:GetLastError
0x1806dd288  nop     dword ptr [rax+rax+00h]
0x1806dd28d  mov     ebx, eax
0x1806dd28f  test    eax, eax
0x1806dd291  jle     short loc_1806DD29C
0x1806dd293  movzx   ebx, ax
0x1806dd296  or      ebx, 80070000h
0x1806dd29c  mov     rcx, cs:RequestContext
0x1806dd2a3  lea     rdi, RequestContext
0x1806dd2aa  cmp     rcx, rdi
0x1806dd2ad  jz      short loc_1806DD2D3
0x1806dd2af  test    [rcx+1Ch], r15d
0x1806dd2b3  jz      short loc_1806DD2D3
0x1806dd2b5  cmp     [rcx+19h], r13b
0x1806dd2b9  jb      short loc_1806DD2D3
0x1806dd2bb  mov     rcx, [rcx+10h]
0x1806dd2bf  lea     r8, qword_180872238
0x1806dd2c6  mov     edx, 2Ah ; '*'
0x1806dd2cb  mov     r9d, ebx
0x1806dd2ce  call    sub_180121AD0
0x1806dd2d3  test    ebx, ebx
0x1806dd2d5  js      loc_1806DD4E6
0x1806dd2db  cmp     [rsi+28h], r12
0x1806dd2df  jnz     loc_1806DD365
0x1806dd2e5  xor     r9d, r9d; lpName
0x1806dd2e8  xor     r8d, r8d; bInitialState
0x1806dd2eb  xor     edx, edx; bManualReset
0x1806dd2ed  xor     ecx, ecx; lpEventAttributes
0x1806dd2ef  call    cs:CreateEventW
0x1806dd2f6  nop     dword ptr [rax+rax+00h]
0x1806dd2fb  mov     [rsi+28h], rax
0x1806dd2ff  test    rax, rax
0x1806dd302  jz      short loc_1806DD309
0x1806dd304  mov     ebx, r12d
0x1806dd307  jmp     short loc_1806DD324
0x1806dd309  call    cs:GetLastError
0x1806dd310  nop     dword ptr [rax+rax+00h]
0x1806dd315  mov     ebx, eax
0x1806dd317  test    eax, eax
0x1806dd319  jle     short loc_1806DD324
0x1806dd31b  movzx   ebx, ax
0x1806dd31e  or      ebx, 80070000h
0x1806dd324  mov     rcx, cs:RequestContext
0x1806dd32b  cmp     rcx, rdi
0x1806dd32e  jz      short loc_1806DD35D
0x1806dd330  test    [rcx+1Ch], r15d
0x1806dd334  jz      short loc_1806DD35D
0x1806dd336  cmp     [rcx+19h], r13b
0x1806dd33a  jb      short loc_1806DD35D
0x1806dd33c  mov     rax, [rsi+28h]
0x1806dd340  lea     r8, qword_180872238
0x1806dd347  mov     rcx, [rcx+10h]
0x1806dd34b  mov     edx, 2Bh ; '+'
0x1806dd350  mov     r9d, ebx
0x1806dd353  mov     [rsp+88h+ppv], rax
0x1806dd358  call    sub_1801B7BDC
0x1806dd35d  test    ebx, ebx
0x1806dd35f  js      loc_1806DD4E6
0x1806dd365  call    cs:GetCurrentProcess
0x1806dd36c  nop     dword ptr [rax+rax+00h]
0x1806dd371  mov     rdi, [rsi+28h]
0x1806dd375  mov     rbx, rax
0x1806dd378  call    cs:GetCurrentProcess
0x1806dd37f  nop     dword ptr [rax+rax+00h]
0x1806dd384  mov     [rsp+88h+dwOptions], 2; dwOptions
  ... truncated ...
```
