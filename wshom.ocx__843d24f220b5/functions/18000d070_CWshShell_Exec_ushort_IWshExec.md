# CWshShell::Exec(ushort *,IWshExec * *)

- ea: `0x18000d070`
- end: `0x18000d3c5`
- name: `?Exec@CWshShell@@UEAAJPEAGPEAPEAUIWshExec@@@Z`
- size: `853`
- prototype: `int(CWshShell *__hidden this, unsigned __int16 *, struct IWshExec **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004060`
- `0x18000564c`
- `0x180005d20`
- `0x180009c04`
- `0x18000ce3c`
- `0x18000cf70`
- `0x18000d070`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d30a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d30a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d105`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d105`
- `KERNEL32!CreatePipe` at `0x18000d134`
- `KERNEL32!CreatePipe` at `0x18000d16b`
- `KERNEL32!CreatePipe` at `0x18000d184`
- `KERNEL32!CreatePipe` at `0x18000d134`
- `KERNEL32!CreatePipe` at `0x18000d16b`
- `KERNEL32!CreatePipe` at `0x18000d184`
- `KERNEL32!DuplicateHandle` at `0x18000d1b7`
- `KERNEL32!DuplicateHandle` at `0x18000d1e5`
- `KERNEL32!DuplicateHandle` at `0x18000d213`
- `KERNEL32!DuplicateHandle` at `0x18000d1b7`
- `KERNEL32!DuplicateHandle` at `0x18000d1e5`
- `KERNEL32!DuplicateHandle` at `0x18000d213`
- `KERNEL32!GetLastError` at `0x18000d13e`
- `KERNEL32!GetLastError` at `0x18000d13e`
- `KERNEL32!CloseHandle` at `0x18000d225`
- `KERNEL32!CloseHandle` at `0x18000d23b`
- `KERNEL32!CloseHandle` at `0x18000d251`
- `KERNEL32!CloseHandle` at `0x18000d319`
- `KERNEL32!CloseHandle` at `0x18000d328`
- `KERNEL32!CloseHandle` at `0x18000d337`
- `KERNEL32!CloseHandle` at `0x18000d346`
- `KERNEL32!CloseHandle` at `0x18000d355`
- `KERNEL32!CloseHandle` at `0x18000d364`
- `KERNEL32!CloseHandle` at `0x18000d373`
- `KERNEL32!CloseHandle` at `0x18000d382`
- `KERNEL32!CloseHandle` at `0x18000d391`
- `KERNEL32!CloseHandle` at `0x18000d225`
- `KERNEL32!CloseHandle` at `0x18000d23b`
- `KERNEL32!CloseHandle` at `0x18000d251`
- `KERNEL32!CloseHandle` at `0x18000d319`
- `KERNEL32!CloseHandle` at `0x18000d328`
- `KERNEL32!CloseHandle` at `0x18000d337`
- `KERNEL32!CloseHandle` at `0x18000d346`
- `KERNEL32!CloseHandle` at `0x18000d355`
- `KERNEL32!CloseHandle` at `0x18000d364`
- `KERNEL32!CloseHandle` at `0x18000d373`
- `KERNEL32!CloseHandle` at `0x18000d382`
- `KERNEL32!CloseHandle` at `0x18000d391`
- `KERNEL32!GetCurrentProcess` at `0x18000d18e`
- `KERNEL32!GetCurrentProcess` at `0x18000d18e`

## pseudocode

```c
__int64 __fastcall CWshShell::Exec(CWshShell *this, unsigned __int16 *a2, struct IWshExec **a3)
{
  CWshExec *v5; // rdi
  signed int v6; // ebx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rbx
  int v9; // eax
  int NewProcessW; // eax
  HANDLE hSourceHandle; // [rsp+40h] [rbp-19h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-11h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-9h] BYREF
  HANDLE v14; // [rsp+58h] [rbp-1h] BYREF
  HANDLE v15; // [rsp+60h] [rbp+7h] BYREF
  CWshExec *v16; // [rsp+68h] [rbp+Fh] BYREF
  HANDLE hWritePipe; // [rsp+70h] [rbp+17h] BYREF
  HANDLE v18; // [rsp+78h] [rbp+1Fh] BYREF
  HANDLE v19; // [rsp+80h] [rbp+27h] BYREF
  struct _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+88h] [rbp+2Fh] BYREF
  BSTR pbstr; // [rsp+D0h] [rbp+77h] BYREF
  HANDLE hReadPipe; // [rsp+D8h] [rbp+7Fh] BYREF

  memset(&PipeAttributes, 0, sizeof(PipeAttributes));
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  pbstr = 0;
  v5 = 0;
  v16 = 0;
  TargetHandle = 0;
  hWritePipe = 0;
  hReadPipe = 0;
  v18 = 0;
  v14 = 0;
  hSourceHandle = 0;
  v15 = 0;
  v19 = 0;
  hObject = 0;
  v6 = ExpandEnvStrings(a2, &pbstr);
  if ( v6 >= 0 )
  {
    if ( pbstr && SysStringLen(pbstr) )
    {
      PipeAttributes.nLength = 24;
      PipeAttributes.lpSecurityDescriptor = 0;
      PipeAttributes.bInheritHandle = 1;
      if ( CreatePipe(&hReadPipe, &hWritePipe, &PipeAttributes, 0)
        && CreatePipe(&v18, &hSourceHandle, &PipeAttributes, 0)
        && CreatePipe(&hObject, &v19, &PipeAttributes, 0)
        && (CurrentProcess = GetCurrentProcess(),
            DuplicateHandle(CurrentProcess, hReadPipe, CurrentProcess, &TargetHandle, 0, 0, 2u))
        && DuplicateHandle(CurrentProcess, hSourceHandle, CurrentProcess, &v14, 0, 0, 2u)
        && DuplicateHandle(CurrentProcess, hObject, CurrentProcess, &v15, 0, 0, 2u)
        && CloseHandle(hReadPipe)
        && (hReadPipe = 0, CloseHandle(hSourceHandle))
        && (hSourceHandle = 0, CloseHandle(hObject)) )
      {
        hObject = 0;
        v9 = CWshExec::Create(TargetHandle, v14, v15, &v16);
        v5 = v16;
        v6 = v9;
        TargetHandle = 0;
        v14 = 0;
        v15 = 0;
        if ( v9 >= 0 )
        {
          if ( Global::g_fWindowsNT )
            NewProcessW = CreateNewProcessW(v16, (__int64)v19);
          else
            NewProcessW = CreateNewProcessA(v16, pbstr, (__int64)v19);
          v6 = NewProcessW;
          if ( NewProcessW >= 0 )
          {
            *a3 = v5;
            v6 = 0;
            v5 = 0;
          }
          else
          {
            Signal_ExceptionHR(&IID_IWshShell, L"WshShell.Exec", NewProcessW, pbstr);
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      Signal_Exception(&IID_IWshShell, L"WshShell.Exec", 0x1011u);
      v6 = -2147352567;
    }
  }
  SysFreeString(pbstr);
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( hWritePipe )
    CloseHandle(hWritePipe);
  if ( hReadPipe )
    CloseHandle(hReadPipe);
  if ( v18 )
    CloseHandle(v18);
  if ( v14 )
    CloseHandle(v14);
  if ( hSourceHandle )
    CloseHandle(hSourceHandle);
  if ( v15 )
    CloseHandle(v15);
  if ( v19 )
    CloseHandle(v19);
  if ( hObject )
    CloseHandle(hObject);
  if ( v5 )
    (*(void (__fastcall **)(CWshExec *))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d070  mov     [rsp-8+arg_0], rbx
0x18000d075  mov     [rsp-8+arg_8], rsi
0x18000d07a  push    rbp
0x18000d07b  push    rdi
0x18000d07c  push    r15
0x18000d07e  lea     rbp, [rsp-47h]
0x18000d083  sub     rsp, 0A0h
0x18000d08a  xor     ecx, ecx
0x18000d08c  xor     r15d, r15d
0x18000d08f  mov     qword ptr [rbp+57h+PipeAttributes.bInheritHandle], rcx
0x18000d093  xorps   xmm0, xmm0
0x18000d096  mov     rsi, r8
0x18000d099  mov     rax, rdx
0x18000d09c  movups  xmmword ptr [rbp+57h+PipeAttributes.nLength], xmm0
0x18000d0a0  test    r8, r8
0x18000d0a3  jnz     short loc_18000D0AF
0x18000d0a5  mov     eax, 80004003h
0x18000d0aa  jmp     loc_18000D3AD
0x18000d0af  lea     rdx, [rbp+57h+pbstr]; unsigned __int16 **
0x18000d0b3  mov     [r8], r15
0x18000d0b6  mov     rcx, rax; unsigned __int16 *
0x18000d0b9  mov     [rbp+57h+pbstr], r15
0x18000d0bd  mov     rdi, r15
0x18000d0c0  mov     [rbp+57h+var_48], r15
0x18000d0c4  mov     [rbp+57h+TargetHandle], r15
0x18000d0c8  mov     [rbp+57h+hWritePipe], r15
0x18000d0cc  mov     [rbp+57h+hReadPipe], r15
0x18000d0d0  mov     [rbp+57h+var_38], r15
0x18000d0d4  mov     [rbp+57h+var_58], r15
0x18000d0d8  mov     [rbp+57h+hSourceHandle], r15
0x18000d0dc  mov     [rbp+57h+var_50], r15
0x18000d0e0  mov     [rbp+57h+var_30], r15
0x18000d0e4  mov     [rbp+57h+hObject], r15
0x18000d0e8  call    ?ExpandEnvStrings@@YAJPEAGPEAPEAG@Z; ExpandEnvStrings(ushort *,ushort * *)
0x18000d0ed  mov     ebx, eax
0x18000d0ef  test    eax, eax
0x18000d0f1  js      loc_18000D306
0x18000d0f7  cmp     [rbp+57h+pbstr], r15
0x18000d0fb  jz      loc_18000D2E8
0x18000d101  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18000d105  call    cs:__imp_SysStringLen
0x18000d10b  test    eax, eax
0x18000d10d  jz      loc_18000D2E8
0x18000d113  xor     r9d, r9d; nSize
0x18000d116  mov     [rbp+57h+PipeAttributes.nLength], 18h
0x18000d11d  lea     r8, [rbp+57h+PipeAttributes]; lpPipeAttributes
0x18000d121  mov     [rbp+57h+PipeAttributes.lpSecurityDescriptor], r15
0x18000d125  lea     rdx, [rbp+57h+hWritePipe]; hWritePipe
0x18000d129  mov     [rbp+57h+PipeAttributes.bInheritHandle], 1
0x18000d130  lea     rcx, [rbp+57h+hReadPipe]; hReadPipe
0x18000d134  call    cs:__imp_CreatePipe
0x18000d13a  test    eax, eax
0x18000d13c  jnz     short loc_18000D15C
0x18000d13e  call    cs:__imp_GetLastError
0x18000d144  mov     ebx, eax
0x18000d146  test    eax, eax
0x18000d148  jle     loc_18000D306
0x18000d14e  movzx   ebx, ax
0x18000d151  or      ebx, 80070000h
0x18000d157  jmp     loc_18000D306
0x18000d15c  xor     r9d, r9d; nSize
0x18000d15f  lea     r8, [rbp+57h+PipeAttributes]; lpPipeAttributes
0x18000d163  lea     rdx, [rbp+57h+hSourceHandle]; hWritePipe
0x18000d167  lea     rcx, [rbp+57h+var_38]; hReadPipe
0x18000d16b  call    cs:__imp_CreatePipe
0x18000d171  test    eax, eax
0x18000d173  jz      short loc_18000D13E
0x18000d175  xor     r9d, r9d; nSize
0x18000d178  lea     r8, [rbp+57h+PipeAttributes]; lpPipeAttributes
0x18000d17c  lea     rdx, [rbp+57h+var_30]; hWritePipe
0x18000d180  lea     rcx, [rbp+57h+hObject]; hReadPipe
0x18000d184  call    cs:__imp_CreatePipe
0x18000d18a  test    eax, eax
0x18000d18c  jz      short loc_18000D13E
0x18000d18e  call    cs:__imp_GetCurrentProcess
0x18000d194  mov     rdx, [rbp+57h+hReadPipe]; hSourceHandle
0x18000d198  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18000d19c  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x18000d1a4  mov     r8, rax; hTargetProcessHandle
0x18000d1a7  mov     rcx, rax; hSourceProcessHandle
0x18000d1aa  mov     [rsp+0B0h+bInheritHandle], r15d; bInheritHandle
0x18000d1af  mov     rbx, rax
0x18000d1b2  mov     [rsp+0B0h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000d1b7  call    cs:__imp_DuplicateHandle
0x18000d1bd  test    eax, eax
0x18000d1bf  jz      loc_18000D13E
0x18000d1c5  mov     rdx, [rbp+57h+hSourceHandle]; hSourceHandle
0x18000d1c9  lea     r9, [rbp+57h+var_58]; lpTargetHandle
0x18000d1cd  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x18000d1d5  mov     r8, rbx; hTargetProcessHandle
0x18000d1d8  mov     [rsp+0B0h+bInheritHandle], r15d; bInheritHandle
0x18000d1dd  mov     rcx, rbx; hSourceProcessHandle
0x18000d1e0  mov     [rsp+0B0h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000d1e5  call    cs:__imp_DuplicateHandle
0x18000d1eb  test    eax, eax
0x18000d1ed  jz      loc_18000D13E
0x18000d1f3  mov     rdx, [rbp+57h+hObject]; hSourceHandle
0x18000d1f7  lea     r9, [rbp+57h+var_50]; lpTargetHandle
0x18000d1fb  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x18000d203  mov     r8, rbx; hTargetProcessHandle
0x18000d206  mov     [rsp+0B0h+bInheritHandle], r15d; bInheritHandle
0x18000d20b  mov     rcx, rbx; hSourceProcessHandle
0x18000d20e  mov     [rsp+0B0h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000d213  call    cs:__imp_DuplicateHandle
0x18000d219  test    eax, eax
0x18000d21b  jz      loc_18000D13E
0x18000d221  mov     rcx, [rbp+57h+hReadPipe]; hObject
0x18000d225  call    cs:__imp_CloseHandle
0x18000d22b  test    eax, eax
0x18000d22d  jz      loc_18000D13E
0x18000d233  mov     rcx, [rbp+57h+hSourceHandle]; hObject
0x18000d237  mov     [rbp+57h+hReadPipe], r15
0x18000d23b  call    cs:__imp_CloseHandle
0x18000d241  test    eax, eax
0x18000d243  jz      loc_18000D13E
0x18000d249  mov     rcx, [rbp+57h+hObject]; hObject
0x18000d24d  mov     [rbp+57h+hSourceHandle], r15
0x18000d251  call    cs:__imp_CloseHandle
0x18000d257  test    eax, eax
0x18000d259  jz      loc_18000D13E
0x18000d25f  mov     r8, [rbp+57h+var_50]; HANDLE
0x18000d263  lea     r9, [rbp+57h+var_48]; struct CWshExec **
0x18000d267  mov     rdx, [rbp+57h+var_58]; HANDLE
0x18000d26b  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18000d26f  mov     [rbp+57h+hObject], r15
0x18000d273  call    ?Create@CWshExec@@SAJPEAX00PEAPEAV1@@Z; CWshExec::Create(void *,void *,void *,CWshExec * *)
0x18000d278  mov     rdi, [rbp+57h+var_48]
0x18000d27c  mov     ebx, eax
0x18000d27e  mov     [rbp+57h+TargetHandle], r15
0x18000d282  mov     [rbp+57h+var_58], r15
0x18000d286  mov     [rbp+57h+var_50], r15
0x18000d28a  test    eax, eax
0x18000d28c  js      short loc_18000D306
0x18000d28e  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x18000d295  mov     rcx, rdi; this
0x18000d298  mov     rax, [rbp+57h+var_30]
0x18000d29c  mov     r9, [rbp+57h+var_38]
0x18000d2a0  mov     r8, [rbp+57h+hWritePipe]
0x18000d2a4  mov     rdx, [rbp+57h+pbstr]; lpWideCharStr
0x18000d2a8  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax; __int64
0x18000d2ad  jz      short loc_18000D2B6
0x18000d2af  call    CreateNewProcessW
0x18000d2b4  jmp     short loc_18000D2BB
0x18000d2b6  call    CreateNewProcessA
0x18000d2bb  mov     ebx, eax
0x18000d2bd  test    eax, eax
0x18000d2bf  jns     short loc_18000D2DD
0x18000d2c1  mov     r9, [rbp+57h+pbstr]
0x18000d2c5  lea     rdx, aWshshellExec; "WshShell.Exec"
0x18000d2cc  mov     r8d, eax; int
0x18000d2cf  lea     rcx, IID_IWshShell; struct _GUID *
0x18000d2d6  call    ?Signal_ExceptionHR@@YAJAEBU_GUID@@PEBGJZZ; Signal_ExceptionHR(_GUID const &,ushort const *,long,...)
0x18000d2db  jmp     short loc_18000D306
0x18000d2dd  mov     [rsi], rdi
0x18000d2e0  mov     ebx, r15d
0x18000d2e3  mov     rdi, r15
0x18000d2e6  jmp     short loc_18000D306
0x18000d2e8  mov     r8d, 1011h; unsigned int
0x18000d2ee  lea     rdx, aWshshellExec; "WshShell.Exec"
0x18000d2f5  lea     rcx, IID_IWshShell; struct _GUID *
0x18000d2fc  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x18000d301  mov     ebx, 80020009h
0x18000d306  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18000d30a  call    cs:__imp_SysFreeString
0x18000d310  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18000d314  test    rcx, rcx
0x18000d317  jz      short loc_18000D31F
0x18000d319  call    cs:__imp_CloseHandle
0x18000d31f  mov     rcx, [rbp+57h+hWritePipe]; hObject
0x18000d323  test    rcx, rcx
0x18000d326  jz      short loc_18000D32E
0x18000d328  call    cs:__imp_CloseHandle
0x18000d32e  mov     rcx, [rbp+57h+hReadPipe]; hObject
0x18000d332  test    rcx, rcx
0x18000d335  jz      short loc_18000D33D
0x18000d337  call    cs:__imp_CloseHandle
0x18000d33d  mov     rcx, [rbp+57h+var_38]; hObject
0x18000d341  test    rcx, rcx
0x18000d344  jz      short loc_18000D34C
0x18000d346  call    cs:__imp_CloseHandle
0x18000d34c  mov     rcx, [rbp+57h+var_58]; hObject
0x18000d350  test    rcx, rcx
0x18000d353  jz      short loc_18000D35B
0x18000d355  call    cs:__imp_CloseHandle
0x18000d35b  mov     rcx, [rbp+57h+hSourceHandle]; hObject
0x18000d35f  test    rcx, rcx
0x18000d362  jz      short loc_18000D36A
0x18000d364  call    cs:__imp_CloseHandle
0x18000d36a  mov     rcx, [rbp+57h+var_50]; hObject
0x18000d36e  test    rcx, rcx
0x18000d371  jz      short loc_18000D379
0x18000d373  call    cs:__imp_CloseHandle
0x18000d379  mov     rcx, [rbp+57h+var_30]; hObject
0x18000d37d  test    rcx, rcx
0x18000d380  jz      short loc_18000D388
0x18000d382  call    cs:__imp_CloseHandle
0x18000d388  mov     rcx, [rbp+57h+hObject]; hObject
0x18000d38c  test    rcx, rcx
0x18000d38f  jz      short loc_18000D397
0x18000d391  call    cs:__imp_CloseHandle
0x18000d397  test    rdi, rdi
0x18000d39a  jz      short loc_18000D3AB
0x18000d39c  mov     rax, [rdi]
0x18000d39f  mov     rcx, rdi
0x18000d3a2  mov     rax, [rax+10h]
0x18000d3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3ab  mov     eax, ebx
0x18000d3ad  lea     r11, [rsp+0B0h+var_10]
0x18000d3b5  mov     rbx, [r11+20h]
0x18000d3b9  mov     rsi, [r11+28h]
0x18000d3bd  mov     rsp, r11
0x18000d3c0  pop     r15
0x18000d3c2  pop     rdi
0x18000d3c3  pop     rbp
0x18000d3c4  retn
```
