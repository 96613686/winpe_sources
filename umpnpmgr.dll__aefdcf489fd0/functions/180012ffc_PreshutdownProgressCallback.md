# PreshutdownProgressCallback

- ea: `0x180012ffc`
- end: `0x1800132b9`
- name: `PreshutdownProgressCallback`
- size: `701`
- prototype: `_BOOL8 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180013744`

## callees

- `0x1800010e0`
- `0x1800040f0`
- `0x180011964`
- `0x180012ffc`
- `0x180013370`
- `0x18001a010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800131d0`
- `ntdll!RtlFreeHeap` at `0x1800131e6`
- `ntdll!RtlFreeHeap` at `0x18001327c`
- `ntdll!RtlFreeHeap` at `0x180013293`
- `ntdll!RtlFreeHeap` at `0x1800131d0`
- `ntdll!RtlFreeHeap` at `0x1800131e6`
- `ntdll!RtlFreeHeap` at `0x18001327c`
- `ntdll!RtlFreeHeap` at `0x180013293`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800131ee`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800131ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001303c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001303c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013065`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013065`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001312e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013170`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001312e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013170`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001329b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001329b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001304e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001317a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001304e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001317a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013263`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013263`

## string_xrefs

- `0x180013033`: `WMsgApi.dll`

## pseudocode

```c
_BOOL8 __fastcall PreshutdownProgressCallback(_DWORD *a1)
{
  DWORD LastError; // ebx
  HMODULE Library; // rax
  int v4; // r11d
  UINT v5; // ebx
  int v6; // r9d
  unsigned int v7; // r9d
  unsigned __int64 v8; // r10
  unsigned __int64 v9; // r11
  unsigned int StringW; // eax
  __int64 v11; // rsi
  __int64 v12; // r14
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  PVOID v15; // rax
  void *v16; // rsi
  NTSTATUS v17; // ebx
  WCHAR *v18; // rbx
  RPC_STATUS v19; // eax
  unsigned __int64 v21; // [rsp+70h] [rbp+18h] BYREF
  __int64 Buffer; // [rsp+78h] [rbp+20h] BYREF

  LastError = 0;
  v21 = 0;
  Buffer = 0;
  if ( !PnpServicePreshutdown )
    goto LABEL_43;
  if ( qword_180023738 )
  {
    if ( !qword_180023730 )
    {
      LastError = 127;
      goto LABEL_43;
    }
  }
  else
  {
    Library = LoadLibraryExW(L"WMsgApi.dll", 0, 0);
    qword_180023738 = (__int64)Library;
    if ( !Library )
      goto LABEL_4;
    qword_180023730 = (__int64)GetProcAddress(Library, "WmsgPostNotifyMessage");
    if ( !qword_180023730 )
      goto LABEL_4;
  }
  if ( *a1 == 1 )
  {
    v5 = 800;
LABEL_20:
    v6 = 0;
    goto LABEL_21;
  }
  if ( (unsigned int)(*a1 - 2) >= 2 )
  {
    LastError = 13;
    goto LABEL_43;
  }
  v4 = a1[1];
  v5 = 801;
  if ( !v4 )
    goto LABEL_20;
  v6 = 100;
  if ( v4 == -1 )
  {
LABEL_21:
    dword_18002372C = v6;
    goto LABEL_22;
  }
  RtlULongLongMult((unsigned int)a1[2], 100, &v21);
  if ( v21 / v9 <= v8 )
    LODWORD(v8) = v21 / v9;
  if ( (unsigned int)v8 <= dword_18002372C )
  {
    if ( dword_18002372C < v7 )
      ++dword_18002372C;
  }
  else
  {
    dword_18002372C = v8;
  }
LABEL_22:
  StringW = LoadStringW(PnpDllModuleHandle, v5, (LPWSTR)&Buffer, 0);
  v11 = StringW;
  if ( !StringW )
  {
LABEL_4:
    LastError = GetLastError();
    goto LABEL_43;
  }
  v12 = StringW + 1;
  v13 = (WCHAR *)PnpHeapAlloc(2 * v12);
  v14 = v13;
  if ( !v13 )
  {
    LastError = 8;
    goto LABEL_43;
  }
  if ( !LoadStringW(PnpDllModuleHandle, v5, v13, v12) )
  {
    LastError = GetLastError();
LABEL_42:
    RtlFreeHeap(PnpHeapHandle, 0, v14);
    goto LABEL_43;
  }
  v14[v11] = 0;
  if ( v5 == 800 )
  {
    v18 = v14;
LABEL_35:
    v16 = 0;
    goto LABEL_36;
  }
  v15 = PnpHeapAlloc(2 * v12);
  v16 = v15;
  if ( !v15 )
  {
    LastError = 8;
    goto LABEL_42;
  }
  v17 = RtlStringCchPrintfW(v15, v12, v14, (unsigned int)dword_18002372C);
  RtlFreeHeap(PnpHeapHandle, 0, v14);
  if ( v17 < 0 )
  {
    RtlFreeHeap(PnpHeapHandle, 0, v16);
    LastError = RtlNtStatusToDosErrorNoTeb(v17);
    if ( LastError )
      goto LABEL_43;
    v18 = 0;
    v14 = 0;
    goto LABEL_35;
  }
  v14 = 0;
  v18 = (WCHAR *)v16;
LABEL_36:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
      (unsigned int)dword_18002372C);
  v19 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, WCHAR *))qword_180023730)(0, 768, 0, v18);
  LastError = I_RpcMapWin32Status(v19);
  if ( v16 )
    RtlFreeHeap(PnpHeapHandle, 0, v16);
  if ( v14 )
    goto LABEL_42;
LABEL_43:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180012ffc  mov     [rsp+arg_0], rbx
0x180013001  push    rbp
0x180013002  push    rsi
0x180013003  push    rdi
0x180013004  push    r14
0x180013006  push    r15
0x180013008  sub     rsp, 30h
0x18001300c  xor     ebx, ebx
0x18001300e  mov     rdi, rcx
0x180013011  cmp     cs:PnpServicePreshutdown, ebx
0x180013017  mov     [rsp+58h+arg_10], rbx
0x18001301c  mov     [rsp+58h+Buffer], rbx
0x180013021  jz      loc_180013299
0x180013027  cmp     cs:qword_180023738, rbx
0x18001302e  jnz     short loc_180013096
0x180013030  xor     r8d, r8d; dwFlags
0x180013033  lea     rcx, LibFileName; "WMsgApi.dll"
0x18001303a  xor     edx, edx; hFile
0x18001303c  call    cs:__imp_LoadLibraryExW
0x180013042  mov     cs:qword_180023738, rax
0x180013049  test    rax, rax
0x18001304c  jnz     short loc_18001305B
0x18001304e  call    cs:__imp_GetLastError
0x180013054  mov     ebx, eax
0x180013056  jmp     loc_180013299
0x18001305b  lea     rdx, ProcName; "WmsgPostNotifyMessage"
0x180013062  mov     rcx, rax; hModule
0x180013065  call    cs:__imp_GetProcAddress
0x18001306b  mov     cs:qword_180023730, rax
0x180013072  test    rax, rax
0x180013075  jz      short loc_18001304E
0x180013077  mov     ecx, [rdi]
0x180013079  sub     ecx, 1
0x18001307c  jz      loc_18001310E
0x180013082  sub     ecx, 1
0x180013085  jz      short loc_1800130A9
0x180013087  cmp     ecx, 1
0x18001308a  jz      short loc_1800130A9
0x18001308c  mov     ebx, 0Dh
0x180013091  jmp     loc_180013299
0x180013096  cmp     cs:qword_180023730, rbx
0x18001309d  jnz     short loc_180013077
0x18001309f  mov     ebx, 7Fh
0x1800130a4  jmp     loc_180013299
0x1800130a9  mov     r11d, [rdi+4]
0x1800130ad  mov     esi, 321h
0x1800130b2  mov     ebx, esi
0x1800130b4  test    r11d, r11d
0x1800130b7  jz      short loc_180013113
0x1800130b9  mov     r10d, 0FFFFFFFFh
0x1800130bf  mov     r9d, 64h ; 'd'
0x1800130c5  cmp     r11d, r10d
0x1800130c8  jz      short loc_180013116
0x1800130ca  mov     ecx, [rdi+8]
0x1800130cd  lea     r8, [rsp+58h+arg_10]
0x1800130d2  mov     edx, r9d
0x1800130d5  call    RtlULongLongMult
0x1800130da  mov     rax, [rsp+58h+arg_10]
0x1800130df  xor     edx, edx
0x1800130e1  div     r11
0x1800130e4  cmp     rax, r10
0x1800130e7  cmovbe  r10d, eax
0x1800130eb  mov     eax, cs:dword_18002372C
0x1800130f1  cmp     r10d, eax
0x1800130f4  jbe     short loc_1800130FF
0x1800130f6  mov     cs:dword_18002372C, r10d
0x1800130fd  jmp     short loc_18001311D
0x1800130ff  cmp     eax, r9d
0x180013102  jnb     short loc_18001311D
0x180013104  inc     eax
0x180013106  mov     cs:dword_18002372C, eax
0x18001310c  jmp     short loc_18001311D
0x18001310e  mov     ebx, 320h
0x180013113  xor     r9d, r9d
0x180013116  mov     cs:dword_18002372C, r9d
0x18001311d  mov     rcx, cs:PnpDllModuleHandle; hInstance
0x180013124  lea     r8, [rsp+58h+Buffer]; lpBuffer
0x180013129  xor     r9d, r9d; cchBufferMax
0x18001312c  mov     edx, ebx; uID
0x18001312e  call    cs:__imp_LoadStringW
0x180013134  mov     esi, eax
0x180013136  test    eax, eax
0x180013138  jz      loc_18001304E
0x18001313e  lea     r14d, [rsi+1]
0x180013142  lea     rbp, [r14+r14]
0x180013146  mov     r15d, r14d
0x180013149  mov     rcx, rbp
0x18001314c  call    PnpHeapAlloc
0x180013151  mov     rdi, rax
0x180013154  test    rax, rax
0x180013157  jnz     short loc_180013161
0x180013159  lea     ebx, [rax+8]
0x18001315c  jmp     loc_180013299
0x180013161  mov     rcx, cs:PnpDllModuleHandle; hInstance
0x180013168  mov     r9d, r14d; cchBufferMax
0x18001316b  mov     r8, rdi; lpBuffer
0x18001316e  mov     edx, ebx; uID
0x180013170  call    cs:__imp_LoadStringW
0x180013176  test    eax, eax
0x180013178  jnz     short loc_180013187
0x18001317a  call    cs:__imp_GetLastError
0x180013180  mov     ebx, eax
0x180013182  jmp     loc_180013287
0x180013187  xor     eax, eax
0x180013189  mov     [rdi+rsi*2], ax
0x18001318d  cmp     ebx, 320h
0x180013193  jz      short loc_18001320B
0x180013195  mov     rcx, rbp
0x180013198  call    PnpHeapAlloc
0x18001319d  mov     rsi, rax
0x1800131a0  test    rax, rax
0x1800131a3  jnz     short loc_1800131AD
0x1800131a5  lea     ebx, [rax+8]
0x1800131a8  jmp     loc_180013287
0x1800131ad  mov     r9d, cs:dword_18002372C
0x1800131b4  mov     r8, rdi
0x1800131b7  mov     rdx, r15
0x1800131ba  mov     rcx, rsi
0x1800131bd  call    RtlStringCchPrintfW
0x1800131c2  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x1800131c9  mov     r8, rdi; P
0x1800131cc  xor     edx, edx; Flags
0x1800131ce  mov     ebx, eax
0x1800131d0  call    cs:__imp_RtlFreeHeap
0x1800131d6  test    ebx, ebx
0x1800131d8  jns     short loc_180013204
0x1800131da  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x1800131e1  mov     r8, rsi; P
0x1800131e4  xor     edx, edx; Flags
0x1800131e6  call    cs:__imp_RtlFreeHeap
0x1800131ec  mov     ecx, ebx; Status
0x1800131ee  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800131f4  mov     ebx, eax
0x1800131f6  test    eax, eax
0x1800131f8  jnz     loc_180013299
0x1800131fe  xor     ebx, ebx
0x180013200  xor     edi, edi
0x180013202  jmp     short loc_18001320E
0x180013204  xor     edi, edi
0x180013206  mov     rbx, rsi
0x180013209  jmp     short loc_180013210
0x18001320b  mov     rbx, rdi
0x18001320e  xor     esi, esi
0x180013210  mov     rcx, cs:WPP_GLOBAL_Control
0x180013217  lea     rax, WPP_GLOBAL_Control
0x18001321e  cmp     rcx, rax
0x180013221  jz      short loc_180013248
0x180013223  test    dword ptr [rcx+1Ch], 80000h
0x18001322a  jz      short loc_180013248
0x18001322c  mov     r9d, cs:dword_18002372C
0x180013233  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18001323a  mov     rcx, [rcx+10h]
0x18001323e  mov     edx, 42h ; 'B'
0x180013243  call    WPP_SF_d
0x180013248  mov     rax, cs:qword_180023730
0x18001324f  mov     r9, rbx
0x180013252  xor     r8d, r8d
0x180013255  mov     edx, 300h
0x18001325a  xor     ecx, ecx
0x18001325c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013261  mov     ecx, eax; Status
0x180013263  call    cs:__imp_I_RpcMapWin32Status
0x180013269  mov     ebx, eax
0x18001326b  test    rsi, rsi
0x18001326e  jz      short loc_180013282
0x180013270  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180013277  mov     r8, rsi; P
0x18001327a  xor     edx, edx; Flags
0x18001327c  call    cs:__imp_RtlFreeHeap
0x180013282  test    rdi, rdi
0x180013285  jz      short loc_180013299
0x180013287  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x18001328e  mov     r8, rdi; P
0x180013291  xor     edx, edx; Flags
0x180013293  call    cs:__imp_RtlFreeHeap
0x180013299  mov     ecx, ebx; dwErrCode
0x18001329b  call    cs:__imp_SetLastError
0x1800132a1  xor     eax, eax
0x1800132a3  test    ebx, ebx
0x1800132a5  mov     rbx, [rsp+58h+arg_0]
0x1800132aa  setz    al
0x1800132ad  add     rsp, 30h
0x1800132b1  pop     r15
0x1800132b3  pop     r14
0x1800132b5  pop     rdi
0x1800132b6  pop     rsi
0x1800132b7  pop     rbp
0x1800132b8  retn
```
