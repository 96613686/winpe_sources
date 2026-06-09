# AslLogCreate

- ea: `0x14000b574`
- end: `0x14000b835`
- name: `AslLogCreate`
- size: `705`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400014c0`

## callees

- `0x14000166e`
- `0x140001686`
- `0x140001692`
- `0x1400016aa`
- `0x1400021a6`
- `0x14000b000`
- `0x14000b574`
- `0x14000bff8`
- `0x14000c0ac`
- `0x1400102a0`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000b6db`
- `KERNEL32!LoadLibraryExW` at `0x14000b6db`
- `KERNEL32!GetModuleFileNameW` at `0x14000b659`
- `KERNEL32!GetModuleFileNameW` at `0x14000b659`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000b715`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000b736`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000b715`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000b736`
- `ntdll!RtlAllocateHeap` at `0x14000b5b7`
- `ntdll!RtlAllocateHeap` at `0x14000b5b7`
- `ntdll!RtlInitializeCriticalSection` at `0x14000b5de`
- `ntdll!RtlInitializeCriticalSection` at `0x14000b5de`
- `ntdll!EtwEventRegister` at `0x14000b640`
- `ntdll!EtwEventRegister` at `0x14000b640`

## string_xrefs

- `0x14000b6ce`: `ntdll.dll`
- `0x14000b70e`: `%OSDataDrive%\SystemData\Temp`
- `0x14000b72f`: `%TEMP%`
- `0x14000b759`: `%s\Temp`

## pseudocode

```c
__int64 AslLogCreate()
{
  char *Heap; // rax
  char *v1; // rbx
  int v2; // edi
  PVOID ProcessHeap; // rcx
  HMODULE v4; // rbp
  wchar_t *v6; // rax
  WCHAR *v7; // rsi
  HMODULE Library; // rax
  __int64 v9; // rcx
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  __int64 NtSystemRoot; // rax
  const char *v12; // rsi
  int DefaultFlags; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  _BYTE *v16; // rcx
  _BYTE *v17; // rax
  unsigned int v18; // ecx
  WCHAR *v19; // [rsp+28h] [rbp-470h]
  DWORD CurrentProcessId_0; // [rsp+30h] [rbp-468h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-248h] BYREF

  AslLogger = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2D8u);
  v1 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  *((_QWORD *)Heap + 90) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 104));
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_OWORD *)v1 + 9) = 0;
  *((_OWORD *)v1 + 10) = 0;
  *((_OWORD *)v1 + 11) = 0;
  if ( !ProcessHeap )
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v1 + 18) = ProcessHeap;
  *((_QWORD *)v1 + 21) = 4096;
  EtwEventRegister(AE_LOG, 0, 0, v1 + 712);
  GetModuleFileNameW(0, Filename, 0x104u);
  if ( GetLastError_0() )
  {
    v4 = 0;
LABEL_7:
    v2 = -1073741823;
LABEL_8:
    AslLogDelete(v1);
    goto LABEL_9;
  }
  v6 = wcsrchr_0(Filename, 0x5Cu);
  if ( v6 )
    v7 = v6 + 1;
  else
    v7 = Filename;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v4 = Library;
  if ( Library
    && (RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                   Library,
                                                                   "RtlIsStateSeparationEnabled")) != 0
    && RtlIsStateSeparationEnabled() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_7;
    }
  }
  else
  {
    NtSystemRoot = AslPathGetNtSystemRoot(v9);
    v2 = RtlStringCchPrintfW(Dst, 260, L"%s\\Temp", NtSystemRoot);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v19 = v7;
  v12 = "SdbInst";
  v2 = RtlStringCchPrintfW(v1 + 192, 260, L"%s\\AslLog_%S_%s_%d.txt", Dst, "SdbInst", v19, CurrentProcessId_0);
  if ( v2 < 0 )
    goto LABEL_8;
  *(_QWORD *)v1 = v1 + 8;
  DefaultFlags = AslLogGetDefaultFlags();
  v14 = 64;
  *(_DWORD *)(*(_QWORD *)v1 + 80LL) = DefaultFlags;
  v15 = 2147483646;
  v16 = *(_BYTE **)v1;
  do
  {
    if ( !v15 )
      break;
    if ( !*v12 )
      break;
    *v16++ = *v12++;
    --v15;
    --v14;
  }
  while ( v14 );
  v17 = v16 - 1;
  if ( v14 )
    v17 = v16;
  *v17 = 0;
  v18 = *((_DWORD *)v1 + 40);
  if ( v18 <= 0x1000 )
  {
    v18 = 4096;
LABEL_35:
    *(_DWORD *)(*(_QWORD *)v1 + 76LL) = v18;
    goto LABEL_36;
  }
  if ( v18 == (v18 & -v18) )
    goto LABEL_35;
LABEL_36:
  v2 = 0;
  AslLogger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary_0(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000b574  push    rbx
0x14000b576  push    rbp
0x14000b577  push    rsi
0x14000b578  push    rdi
0x14000b579  push    r15
0x14000b57b  sub     rsp, 470h
0x14000b582  mov     rax, cs:__security_cookie
0x14000b589  xor     rax, rsp
0x14000b58c  mov     [rsp+498h+var_38], rax
0x14000b594  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger AslLogger
0x14000b59f  mov     edx, 8; Flags
0x14000b5a4  mov     rcx, gs:60h
0x14000b5ad  mov     r8d, 2D8h; Size
0x14000b5b3  mov     rcx, [rcx+30h]; HeapHandle
0x14000b5b7  call    cs:__imp_RtlAllocateHeap
0x14000b5bd  mov     rbx, rax
0x14000b5c0  test    rax, rax
0x14000b5c3  jnz     short loc_14000B5CF
0x14000b5c5  mov     edi, 0C0000017h
0x14000b5ca  jmp     loc_14000B684
0x14000b5cf  lea     rcx, [rax+68h]; CriticalSection
0x14000b5d3  mov     qword ptr [rax+2D0h], 0
0x14000b5de  call    cs:__imp_RtlInitializeCriticalSection
0x14000b5e4  mov     rax, gs:60h
0x14000b5ed  xorps   xmm0, xmm0
0x14000b5f0  mov     rcx, [rax+30h]
0x14000b5f4  movups  xmmword ptr [rbx+90h], xmm0
0x14000b5fb  movups  xmmword ptr [rbx+0A0h], xmm0
0x14000b602  movups  xmmword ptr [rbx+0B0h], xmm0
0x14000b609  test    rcx, rcx
0x14000b60c  jnz     short loc_14000B61B
0x14000b60e  mov     rax, gs:60h
0x14000b617  mov     rcx, [rax+30h]
0x14000b61b  mov     [rbx+90h], rcx
0x14000b622  mov     qword ptr [rbx+0A8h], 1000h
0x14000b62d  lea     r9, [rbx+2C8h]
0x14000b634  xor     r8d, r8d
0x14000b637  xor     edx, edx
0x14000b639  lea     rcx, AE_LOG
0x14000b640  call    cs:__imp_EtwEventRegister
0x14000b646  mov     r15d, 104h
0x14000b64c  lea     rdx, [rsp+498h+Filename]; lpFilename
0x14000b654  mov     r8d, r15d; nSize
0x14000b657  xor     ecx, ecx; hModule
0x14000b659  call    cs:__imp_GetModuleFileNameW
0x14000b65f  call    GetLastError_0
0x14000b664  test    eax, eax
0x14000b666  jz      short loc_14000B6A4
0x14000b668  xor     ebp, ebp
0x14000b66a  mov     edi, 0C0000001h
0x14000b66f  mov     rcx, rbx; P
0x14000b672  call    AslLogDelete
0x14000b677  test    rbp, rbp
0x14000b67a  jz      short loc_14000B684
0x14000b67c  mov     rcx, rbp; hLibModule
0x14000b67f  call    FreeLibrary_0
0x14000b684  mov     eax, edi
0x14000b686  mov     rcx, [rsp+498h+var_38]
0x14000b68e  xor     rcx, rsp; StackCookie
0x14000b691  call    __security_check_cookie
0x14000b696  add     rsp, 470h
0x14000b69d  pop     r15
0x14000b69f  pop     rdi
0x14000b6a0  pop     rsi
0x14000b6a1  pop     rbp
0x14000b6a2  pop     rbx
0x14000b6a3  retn
0x14000b6a4  mov     edx, 5Ch ; '\'; Ch
0x14000b6a9  lea     rcx, [rsp+498h+Filename]; Str
0x14000b6b1  call    wcsrchr_0
0x14000b6b6  mov     rsi, rax
0x14000b6b9  test    rax, rax
0x14000b6bc  jnz     short loc_14000B6C8
0x14000b6be  lea     rsi, [rsp+498h+Filename]
0x14000b6c6  jmp     short loc_14000B6CC
0x14000b6c8  add     rsi, 2
0x14000b6cc  xor     edx, edx; hFile
0x14000b6ce  lea     rcx, LibFileName; "ntdll.dll"
0x14000b6d5  mov     r8d, 800h; dwFlags
0x14000b6db  call    cs:__imp_LoadLibraryExW
0x14000b6e1  mov     rbp, rax
0x14000b6e4  test    rax, rax
0x14000b6e7  jz      short loc_14000B751
0x14000b6e9  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x14000b6f0  mov     rcx, rax; hModule
0x14000b6f3  call    GetProcAddress_0
0x14000b6f8  test    rax, rax
0x14000b6fb  jz      short loc_14000B751
0x14000b6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b702  test    al, al
0x14000b704  jz      short loc_14000B751
0x14000b706  mov     r8d, r15d; nSize
0x14000b709  lea     rdx, [rsp+498h+Dst]; lpDst
0x14000b70e  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x14000b715  call    cs:__imp_ExpandEnvironmentStringsW
0x14000b71b  test    eax, eax
0x14000b71d  jz      short loc_14000B727
0x14000b71f  cmp     [rsp+498h+Dst], 25h ; '%'
0x14000b725  jnz     short loc_14000B777
0x14000b727  mov     r8d, r15d; nSize
0x14000b72a  lea     rdx, [rsp+498h+Dst]; lpDst
0x14000b72f  lea     rcx, aTemp; "%TEMP%"
0x14000b736  call    cs:__imp_ExpandEnvironmentStringsW
0x14000b73c  test    eax, eax
0x14000b73e  jz      loc_14000B66A
0x14000b744  cmp     [rsp+498h+Dst], 25h ; '%'
0x14000b74a  jnz     short loc_14000B777
0x14000b74c  jmp     loc_14000B66A
0x14000b751  call    AslPathGetNtSystemRoot
0x14000b756  mov     r9, rax
0x14000b759  lea     r8, aSTemp; "%s\\Temp"
0x14000b760  mov     rdx, r15
0x14000b763  lea     rcx, [rsp+498h+Dst]
0x14000b768  call    RtlStringCchPrintfW
0x14000b76d  mov     edi, eax
0x14000b76f  test    eax, eax
0x14000b771  js      loc_14000B66F
0x14000b777  call    GetCurrentProcessId_0
0x14000b77c  mov     [rsp+498h+var_468], eax
0x14000b780  lea     rcx, [rbx+0C0h]
0x14000b787  mov     [rsp+498h+var_470], rsi
0x14000b78c  lea     r9, [rsp+498h+Dst]
0x14000b791  lea     rsi, aSdbinst; "SdbInst"
0x14000b798  mov     rdx, r15
0x14000b79b  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x14000b7a2  mov     [rsp+498h+var_478], rsi
0x14000b7a7  call    RtlStringCchPrintfW
0x14000b7ac  mov     edi, eax
0x14000b7ae  test    eax, eax
0x14000b7b0  js      loc_14000B66F
0x14000b7b6  lea     rax, [rbx+8]
0x14000b7ba  mov     [rbx], rax
0x14000b7bd  call    AslLogGetDefaultFlags
0x14000b7c2  mov     rcx, [rbx]
0x14000b7c5  mov     edx, 40h ; '@'
0x14000b7ca  mov     [rcx+50h], eax
0x14000b7cd  mov     eax, 7FFFFFFEh
0x14000b7d2  mov     rcx, [rbx]
0x14000b7d5  test    rax, rax
0x14000b7d8  jz      short loc_14000B7F4
0x14000b7da  mov     r8b, [rsi]
0x14000b7dd  test    r8b, r8b
0x14000b7e0  jz      short loc_14000B7F4
0x14000b7e2  mov     [rcx], r8b
0x14000b7e5  inc     rsi
0x14000b7e8  inc     rcx
0x14000b7eb  dec     rax
0x14000b7ee  sub     rdx, 1
0x14000b7f2  jnz     short loc_14000B7D5
0x14000b7f4  test    rdx, rdx
0x14000b7f7  lea     rax, [rcx-1]
0x14000b7fb  cmovnz  rax, rcx
0x14000b7ff  mov     byte ptr [rax], 0
0x14000b802  mov     ecx, [rbx+0A0h]
0x14000b808  cmp     ecx, 1000h
0x14000b80e  jbe     short loc_14000B81C
0x14000b810  mov     eax, ecx
0x14000b812  neg     eax
0x14000b814  and     eax, ecx
0x14000b816  cmp     ecx, eax
0x14000b818  jnz     short loc_14000B827
0x14000b81a  jmp     short loc_14000B821
0x14000b81c  mov     ecx, 1000h
0x14000b821  mov     rax, [rbx]
0x14000b824  mov     [rax+4Ch], ecx
0x14000b827  xor     edi, edi
0x14000b829  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger AslLogger
0x14000b830  jmp     loc_14000B677
```
