# SxspDoesMSIStillNeedAssembly(ushort const *,int &)

- ea: `0x18005fb10`
- end: `0x18005fcf9`
- name: `?SxspDoesMSIStillNeedAssembly@@YAHPEBGAEAH@Z`
- size: `489`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005cfa0`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18001e5d0`
- `0x180020820`
- `0x180059490`
- `0x18005d2b0`
- `0x18005d38c`
- `0x18005d5cc`
- `0x18005fb10`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fbb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fbca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fc0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fc7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fbb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fbca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fc0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fc7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fc24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fc24`

## string_xrefs

- `0x18005fbd9`: `msi.dll`
- `0x18005fc1d`: `MsiProvideAssemblyW`

## pseudocode

```c
__int64 __fastcall SxspDoesMSIStillNeedAssembly(const unsigned __int16 *a1, int *a2)
{
  const char *v4; // rcx
  char **v5; // rcx
  FARPROC ProcAddress; // rax
  DWORD v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // ebx
  HMODULE hModule; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h]
  __int64 *v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+70h] [rbp-90h]
  int *v18; // [rsp+78h] [rbp-88h]
  _BYTE v19[176]; // [rsp+80h] [rbp-80h] BYREF

  v12 = 0;
  v15 = &qword_180074EB0;
  v14 = 0;
  v18 = &v12;
  v13 = 1;
  v16 = 544438355;
  v17 = 4257;
  CFrame::BaseEnter((CFrame *)&v13);
  hModule = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v19);
  *a2 = 1;
  if ( a1 )
  {
    SetLastError(0);
    if ( (unsigned int)CDynamicLinkLibrary::Win32LoadLibrary(&hModule, L"msi.dll", 0) )
    {
      SetLastError(0);
      ProcAddress = GetProcAddress(hModule, "MsiProvideAssemblyW");
      if ( ProcAddress )
      {
        v7 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, __int64, __int64, _QWORD, _QWORD))ProcAddress)(
               a1,
               0,
               4294967292LL,
               1,
               0,
               0);
        v8 = v7;
        if ( v7 )
        {
          if ( v7 != 2 && v7 != 1607 )
          {
            SetLastError(v7);
            CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v13, v8);
            FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180074E30);
            goto LABEL_15;
          }
          *a2 = 0;
        }
        else
        {
          *a2 = 1;
        }
        v12 = 1;
        goto LABEL_15;
      }
      v5 = off_180074E50;
    }
    else
    {
      v5 = off_180074E70;
    }
    *v18 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v5);
  }
  else
  {
    v17 = 4266;
    FusionpTraceParameterCheck(v4);
    SetLastError(0x57u);
    *v18 = 0;
  }
LABEL_15:
  v9 = v12;
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v19);
  CHandleTemplate<&void * hNull,COperatorFreeLibrary>::~CHandleTemplate<&void * hNull,COperatorFreeLibrary>(&hModule);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v13);
  return v9;
}

```

## disassembly

```asm
0x18005fb10  mov     [rsp-8+arg_10], rbx
0x18005fb15  push    rbp
0x18005fb16  push    rdi
0x18005fb17  push    r14
0x18005fb19  lea     rbp, [rsp-40h]
0x18005fb1e  sub     rsp, 140h
0x18005fb25  mov     rax, cs:__security_cookie
0x18005fb2c  xor     rax, rsp
0x18005fb2f  mov     [rbp+50h+var_20], rax
0x18005fb33  lea     rax, qword_180074EB0
0x18005fb3a  mov     [rsp+150h+var_108], 0
0x18005fb42  mov     [rsp+150h+var_F0], rax
0x18005fb47  mov     rdi, rcx
0x18005fb4a  lea     rax, [rsp+150h+var_108]
0x18005fb4f  mov     [rsp+150h+var_F8], 0
0x18005fb58  mov     r14d, 1
0x18005fb5e  mov     [rsp+150h+var_D8], rax
0x18005fb63  lea     rcx, [rsp+150h+var_100]; this
0x18005fb68  mov     [rsp+150h+var_100], r14d
0x18005fb6d  mov     rbx, rdx
0x18005fb70  mov     [rsp+150h+var_E8], 20737853h
0x18005fb79  mov     [rsp+150h+var_E0], 10A1h
0x18005fb81  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005fb86  lea     rcx, [rbp+50h+var_D0]
0x18005fb8a  mov     [rsp+150h+hModule], 0
0x18005fb93  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005fb98  mov     [rbx], r14d
0x18005fb9b  test    rdi, rdi
0x18005fb9e  jnz     short loc_18005FBC8
0x18005fba0  mov     [rsp+150h+var_E0], 10AAh
0x18005fba8  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18005fbad  lea     ecx, [rdi+57h]; dwErrCode
0x18005fbb0  call    cs:__imp_SetLastError
0x18005fbb7  nop     dword ptr [rax+rax+00h]
0x18005fbbc  mov     rax, [rsp+150h+var_D8]
0x18005fbc1  mov     [rax], edi
0x18005fbc3  jmp     loc_18005FCB5
0x18005fbc8  xor     ecx, ecx; dwErrCode
0x18005fbca  call    cs:__imp_SetLastError
0x18005fbd1  nop     dword ptr [rax+rax+00h]
0x18005fbd6  xor     r8d, r8d; unsigned int
0x18005fbd9  lea     rdx, aMsiDll; "msi.dll"
0x18005fbe0  lea     rcx, [rsp+150h+hModule]; this
0x18005fbe5  call    ?Win32LoadLibrary@CDynamicLinkLibrary@@QEAAHPEBGK@Z; CDynamicLinkLibrary::Win32LoadLibrary(ushort const *,ulong)
0x18005fbea  test    eax, eax
0x18005fbec  jnz     short loc_18005FC0A
0x18005fbee  lea     rcx, off_180074E70; struct _CALL_SITE_INFO *
0x18005fbf5  mov     rax, [rsp+150h+var_D8]
0x18005fbfa  mov     dword ptr [rax], 0
0x18005fc00  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005fc05  jmp     loc_18005FCB5
0x18005fc0a  xor     ecx, ecx; dwErrCode
0x18005fc0c  call    cs:__imp_SetLastError
0x18005fc13  nop     dword ptr [rax+rax+00h]
0x18005fc18  mov     rcx, [rsp+150h+hModule]; hModule
0x18005fc1d  lea     rdx, aMsiprovideasse; "MsiProvideAssemblyW"
0x18005fc24  call    cs:__imp_GetProcAddress
0x18005fc2b  nop     dword ptr [rax+rax+00h]
0x18005fc30  test    rax, rax
0x18005fc33  jnz     short loc_18005FC3E
0x18005fc35  lea     rcx, off_180074E50; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005fc3c  jmp     short loc_18005FBF5
0x18005fc3e  mov     [rsp+150h+var_128], 0
0x18005fc47  mov     r9d, r14d
0x18005fc4a  xor     edx, edx
0x18005fc4c  mov     [rsp+150h+var_130], 0
0x18005fc55  mov     r8d, 0FFFFFFFCh
0x18005fc5b  mov     rcx, rdi
0x18005fc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc63  mov     edi, eax
0x18005fc65  mov     ecx, eax
0x18005fc67  test    eax, eax
0x18005fc69  jz      short loc_18005FCAD
0x18005fc6b  sub     ecx, 2
0x18005fc6e  jz      short loc_18005FCA5
0x18005fc70  sub     ecx, 55h ; 'U'
0x18005fc73  jz      short loc_18005FC7D
0x18005fc75  cmp     ecx, 5F0h
0x18005fc7b  jz      short loc_18005FCA5
0x18005fc7d  mov     ecx, edi; dwErrCode
0x18005fc7f  call    cs:__imp_SetLastError
0x18005fc86  nop     dword ptr [rax+rax+00h]
0x18005fc8b  mov     edx, edi; unsigned int
0x18005fc8d  lea     rcx, [rsp+150h+var_100]; this
0x18005fc92  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18005fc97  lea     rcx, off_180074E30; struct _CALL_SITE_INFO *
0x18005fc9e  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18005fca3  jmp     short loc_18005FCB5
0x18005fca5  mov     dword ptr [rbx], 0
0x18005fcab  jmp     short loc_18005FCB0
0x18005fcad  mov     [rbx], r14d
0x18005fcb0  mov     [rsp+150h+var_108], r14d
0x18005fcb5  mov     ebx, [rsp+150h+var_108]
0x18005fcb9  lea     rcx, [rbp+50h+var_D0]
0x18005fcbd  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005fcc2  lea     rcx, [rsp+150h+hModule]
0x18005fcc7  call    ??1?$CHandleTemplate@$1?hNull@@3QEAXEAVCOperatorFreeLibrary@@@@QEAA@XZ; CHandleTemplate<&void * hNull,COperatorFreeLibrary>::~CHandleTemplate<&void * hNull,COperatorFreeLibrary>(void)
0x18005fccc  lea     rcx, [rsp+150h+var_100]; this
0x18005fcd1  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005fcd6  mov     eax, ebx
0x18005fcd8  mov     rcx, [rbp+50h+var_20]
0x18005fcdc  xor     rcx, rsp; StackCookie
0x18005fcdf  call    __security_check_cookie
0x18005fce4  mov     rbx, [rsp+150h+arg_10]
0x18005fcec  add     rsp, 140h
0x18005fcf3  pop     r14
0x18005fcf5  pop     rdi
0x18005fcf6  pop     rbp
0x18005fcf7  retn
```
