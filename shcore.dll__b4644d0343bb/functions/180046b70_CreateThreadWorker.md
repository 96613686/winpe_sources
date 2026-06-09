# _CreateThreadWorker

- ea: `0x180046b70`
- end: `0x180046e8b`
- name: `_CreateThreadWorker`
- size: `795`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpModuleName@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046b30`
- `0x180046b50`

## callees

- `0x18001b9d0`
- `0x18001c82c`
- `0x180046b70`
- `0x180046ea0`
- `0x1800672e8`
- `0x1800681d4`
- `0x180068340`
- `0x18006d8cc`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046e0a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046e0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180046c47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180046c47`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046c76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046c76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046cd3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046cd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046e2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046e2a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046cb0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046cb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046cf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046d24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046cf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046d24`
- `ntdll!RtlGetThreadWorkOnBehalfTicket` at `0x180046d54`
- `ntdll!RtlGetThreadWorkOnBehalfTicket` at `0x180046d54`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180046d85`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180046d85`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180046e70`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180046e70`

## string_xrefs

- `0x180046db1`: `onecore\shell\shcore\libs\thread\thread.cpp`

## pseudocode

```c
_BOOL8 __fastcall CreateThreadWorker(const WCHAR *lpModuleName, __int64 a2, int a3, __int64 a4, _QWORD *a5)
{
  char v9; // r14
  int v10; // esi
  int Error; // ebx
  __int64 v12; // rax
  HANDLE v13; // rdi
  HRESULT v15; // eax
  DWORD v16; // ecx
  int dwCreationFlags; // [rsp+20h] [rbp-61h]
  __int64 v18; // [rsp+30h] [rbp-51h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-49h] BYREF
  const WCHAR *Parameter; // [rsp+40h] [rbp-41h] BYREF
  __int64 v21; // [rsp+48h] [rbp-39h]
  HANDLE hHandle; // [rsp+50h] [rbp-31h]
  __int64 v23; // [rsp+58h] [rbp-29h]
  int v24; // [rsp+60h] [rbp-21h]
  IUnknown *ppunk; // [rsp+68h] [rbp-19h] BYREF
  struct IUnknown *v26; // [rsp+70h] [rbp-11h]
  HMODULE phModule; // [rsp+78h] [rbp-9h] BYREF
  int v28; // [rsp+80h] [rbp-1h]
  HKL KeyboardLayout; // [rsp+90h] [rbp+Fh]
  __int64 v30; // [rsp+A0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]
  DWORD ThreadId; // [rsp+F0h] [rbp+6Fh] BYREF
  DWORD dwindex; // [rsp+F8h] [rbp+77h] BYREF

  v18 = 0;
  memset_0(&Parameter, 0, 0x68u);
  if ( a4 )
    RtlGetThreadWorkOnBehalfTicket(&v18, 6);
  v9 = 1;
  v10 = a3 & 1;
  if ( (a3 & 1) != 0 && a4 )
  {
LABEL_5:
    ((void (__fastcall *)(__int64))lpModuleName)(a2);
    Error = 0;
LABEL_38:
    if ( v9 )
    {
      if ( ppunk )
        ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
      if ( v26 )
        ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
      if ( phModule )
        FreeLibrary(phModule);
    }
    if ( Error < 0 )
    {
      v16 = (unsigned __int16)Error;
      if ( (Error & 0x1FFF0000) != 0x70000 )
        v16 = Error;
      SetLastError(v16);
    }
    return Error >= 0;
  }
  if ( (a3 & 8) != 0 && (a3 & 0x1000) != 0
    || (a3 & 0x4000) != 0 && ((a3 & 0x1000) != 0 || (a3 & 8) != 0)
    || (a3 & 0x800) != 0 && !(unsigned __int8)IsOleInitializePresent() )
  {
    goto LABEL_36;
  }
  if ( (a3 & 0x400) != 0 )
  {
    if ( !(unsigned __int8)IsGetKeyboardLayoutPresent() )
      goto LABEL_36;
    KeyboardLayout = GetKeyboardLayout(0);
  }
  if ( (a3 & 2) != 0 )
  {
    v15 = SHGetThreadRef(&ppunk);
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"onecore\\shell\\shcore\\libs\\thread\\thread.cpp",
        (const char *)(unsigned int)v15,
        dwCreationFlags);
LABEL_36:
      Error = -2147024809;
      goto LABEL_37;
    }
  }
  if ( (a3 & 4) != 0 )
  {
    v26 = g_punkProcessRef;
    if ( g_punkProcessRef )
      ((void (__fastcall *)(struct IUnknown *))g_punkProcessRef->lpVtbl->AddRef)(g_punkProcessRef);
  }
  if ( (a3 & 0x2000) == 0 )
    GetModuleHandleExW(4u, lpModuleName, &phModule);
  v12 = v30;
  Parameter = lpModuleName;
  if ( a4 )
    v12 = v18;
  v30 = v12;
  v21 = a4;
  v23 = a2;
  v24 = a3;
  hHandle = CreateEventW(0, 0, 0, 0);
  if ( hHandle )
  {
    ThreadId = 0;
    v13 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)WrapperThreadProc, &Parameter, 0, &ThreadId);
    if ( v13 )
    {
      v9 = 0;
      if ( !v21 || (a3 & 0x200) != 0 )
      {
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
      }
      else if ( (a3 & 0x40) != 0 )
      {
        pHandles = hHandle;
        dwindex = 0;
        CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      }
      else
      {
        SHWaitForThreadWithWakeMask(hHandle, 0xFFFFFFFFLL);
      }
      Error = v28;
      if ( v28 >= 0 && a5 )
        *a5 = v13;
      else
        CloseHandle(v13);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    CloseHandle(hHandle);
  }
  else
  {
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
  {
LABEL_37:
    if ( !v10 )
      goto LABEL_38;
    goto LABEL_5;
  }
  return Error >= 0;
}

```

## disassembly

```asm
0x180046b70  mov     [rsp-8+arg_0], rbx
0x180046b75  mov     [rsp-8+arg_8], rsi
0x180046b7a  push    rbp
0x180046b7b  push    rdi
0x180046b7c  push    r12
0x180046b7e  push    r14
0x180046b80  push    r15
0x180046b82  lea     rbp, [rsp-2Fh]
0x180046b87  sub     rsp, 0B0h
0x180046b8e  mov     r12, rdx
0x180046b91  mov     [rbp+4Fh+var_A0], 0
0x180046b99  xor     edx, edx; Val
0x180046b9b  mov     ebx, r8d
0x180046b9e  mov     r15, rcx
0x180046ba1  mov     rdi, r9
0x180046ba4  lea     rcx, [rbp+4Fh+Parameter]; void *
0x180046ba8  lea     r8d, [rdx+68h]; Size
0x180046bac  call    memset_0
0x180046bb1  test    rdi, rdi
0x180046bb4  jnz     loc_180046D4B
0x180046bba  mov     esi, ebx
0x180046bbc  mov     r14b, 1
0x180046bbf  and     esi, 1
0x180046bc2  jz      short loc_180046BDB
0x180046bc4  test    rdi, rdi
0x180046bc7  jz      short loc_180046BDB
0x180046bc9  mov     rcx, r12
0x180046bcc  mov     rax, r15
0x180046bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bd4  xor     ebx, ebx
0x180046bd6  jmp     loc_180046DD2
0x180046bdb  mov     eax, ebx
0x180046bdd  mov     ecx, ebx
0x180046bdf  and     eax, 1000h
0x180046be4  and     ecx, 8
0x180046be7  jnz     loc_180046E35
0x180046bed  bt      ebx, 0Eh
0x180046bf1  jb      loc_180046E3E
0x180046bf7  bt      ebx, 0Bh
0x180046bfb  jb      loc_180046E4F
0x180046c01  bt      ebx, 0Ah
0x180046c05  jb      loc_180046E61
0x180046c0b  test    bl, 2
0x180046c0e  jnz     loc_180046D9C
0x180046c14  test    bl, 4
0x180046c17  jz      short loc_180046C35
0x180046c19  mov     rcx, cs:?g_punkProcessRef@@3PEAUIUnknown@@EA; IUnknown * g_punkProcessRef
0x180046c20  mov     [rbp+4Fh+var_60], rcx
0x180046c24  test    rcx, rcx
0x180046c27  jz      short loc_180046C35
0x180046c29  mov     rax, [rcx]
0x180046c2c  mov     rax, [rax+8]
0x180046c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c35  bt      ebx, 0Dh
0x180046c39  jb      short loc_180046C4D
0x180046c3b  lea     r8, [rbp+4Fh+phModule]; phModule
0x180046c3f  mov     rdx, r15; lpModuleName
0x180046c42  mov     ecx, 4; dwFlags
0x180046c47  call    cs:__imp_GetModuleHandleExW
0x180046c4d  mov     rax, [rbp+4Fh+var_30]
0x180046c51  test    rdi, rdi
0x180046c54  mov     [rbp+4Fh+Parameter], r15
0x180046c58  cmovnz  rax, [rbp+4Fh+var_A0]
0x180046c5d  xor     r9d, r9d; lpName
0x180046c60  xor     r8d, r8d; bInitialState
0x180046c63  mov     [rbp+4Fh+var_30], rax
0x180046c67  xor     edx, edx; bManualReset
0x180046c69  mov     [rbp+4Fh+var_88], rdi
0x180046c6d  xor     ecx, ecx; lpEventAttributes
0x180046c6f  mov     [rbp+4Fh+var_78], r12
0x180046c73  mov     [rbp+4Fh+var_70], ebx
0x180046c76  call    cs:__imp_CreateEventW
0x180046c7c  mov     [rbp+4Fh+hHandle], rax
0x180046c80  test    rax, rax
0x180046c83  jz      loc_180046E7F
0x180046c89  lea     rax, [rbp+4Fh+ThreadId]
0x180046c8d  mov     [rbp+4Fh+ThreadId], 0
0x180046c94  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x180046c99  lea     r9, [rbp+4Fh+Parameter]; lpParameter
0x180046c9d  lea     r8, _WrapperThreadProc; lpStartAddress
0x180046ca4  mov     [rsp+0D0h+dwCreationFlags], 0; dwCreationFlags
0x180046cac  xor     edx, edx; dwStackSize
0x180046cae  xor     ecx, ecx; lpThreadAttributes
0x180046cb0  call    cs:__imp_CreateThread
0x180046cb6  mov     rdi, rax
0x180046cb9  test    rax, rax
0x180046cbc  jz      loc_180046D90
0x180046cc2  xor     r14b, r14b
0x180046cc5  cmp     [rbp+4Fh+var_88], 0
0x180046cca  jnz     short loc_180046D2C
0x180046ccc  mov     rcx, [rbp+4Fh+hHandle]; hHandle
0x180046cd0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180046cd3  call    cs:__imp_WaitForSingleObject
0x180046cd9  mov     ebx, [rbp+4Fh+var_50]
0x180046cdc  test    ebx, ebx
0x180046cde  js      short loc_180046D21
0x180046ce0  mov     rax, [rbp+4Fh+arg_20]
0x180046ce4  test    rax, rax
0x180046ce7  jz      short loc_180046D21
0x180046ce9  mov     [rax], rdi
0x180046cec  mov     rcx, [rbp+4Fh+hHandle]; hObject
0x180046cf0  call    cs:__imp_CloseHandle
0x180046cf6  test    ebx, ebx
0x180046cf8  js      loc_180046DCA
0x180046cfe  not     ebx
0x180046d00  lea     r11, [rsp+0D0h+var_20]
0x180046d08  mov     rsi, [r11+38h]
0x180046d0c  shr     ebx, 1Fh
0x180046d0f  mov     eax, ebx
0x180046d11  mov     rbx, [r11+30h]
0x180046d15  mov     rsp, r11
0x180046d18  pop     r15
0x180046d1a  pop     r14
0x180046d1c  pop     r12
0x180046d1e  pop     rdi
0x180046d1f  pop     rbp
0x180046d20  retn
0x180046d21  mov     rcx, rdi; hObject
0x180046d24  call    cs:__imp_CloseHandle
0x180046d2a  jmp     short loc_180046CEC
0x180046d2c  bt      ebx, 9
0x180046d30  jb      short loc_180046CCC
0x180046d32  mov     r8d, 40h ; '@'
0x180046d38  or      edx, 0FFFFFFFFh; dwTimeout
0x180046d3b  test    r8b, bl
0x180046d3e  jnz     short loc_180046D5F
0x180046d40  mov     rcx, [rbp+4Fh+hHandle]
0x180046d44  call    SHWaitForThreadWithWakeMask
0x180046d49  jmp     short loc_180046CD9
0x180046d4b  mov     edx, 6
0x180046d50  lea     rcx, [rbp+4Fh+var_A0]
0x180046d54  call    cs:__imp_RtlGetThreadWorkOnBehalfTicket
0x180046d5a  jmp     loc_180046BBA
0x180046d5f  mov     rax, [rbp+4Fh+hHandle]
0x180046d63  lea     r9, [rbp+4Fh+pHandles]; pHandles
0x180046d67  mov     r8d, 1; cHandles
0x180046d6d  mov     [rbp+4Fh+pHandles], rax
0x180046d71  lea     rax, [rbp+4Fh+dwindex]
0x180046d75  mov     [rbp+4Fh+dwindex], 0
0x180046d7c  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; lpdwindex
0x180046d81  lea     ecx, [r8+7]; dwFlags
0x180046d85  call    cs:__imp_CoWaitForMultipleHandles
0x180046d8b  jmp     loc_180046CD9
0x180046d90  call    ResultFromKnownLastError
0x180046d95  mov     ebx, eax
0x180046d97  jmp     loc_180046CEC
0x180046d9c  lea     rcx, [rbp+4Fh+ppunk]; ppunk
0x180046da0  call    SHGetThreadRef
0x180046da5  test    eax, eax
0x180046da7  jns     loc_180046C14
0x180046dad  mov     rcx, [rbp+57h]; this
0x180046db1  lea     r8, aOnecoreShellSh_10; "onecore\\shell\\shcore\\libs\\thread\\t"...
0x180046db8  mov     r9d, eax; char *
0x180046dbb  mov     edx, 1F2h; void *
0x180046dc0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046dc5  mov     ebx, 80070057h
0x180046dca  test    esi, esi
0x180046dcc  jnz     loc_180046BC9
0x180046dd2  test    r14b, r14b
0x180046dd5  jz      short loc_180046E10
0x180046dd7  mov     rcx, [rbp+4Fh+ppunk]
0x180046ddb  test    rcx, rcx
0x180046dde  jz      short loc_180046DEC
0x180046de0  mov     rax, [rcx]
0x180046de3  mov     rax, [rax+10h]
0x180046de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dec  mov     rcx, [rbp+4Fh+var_60]
0x180046df0  test    rcx, rcx
0x180046df3  jz      short loc_180046E01
0x180046df5  mov     rax, [rcx]
0x180046df8  mov     rax, [rax+10h]
0x180046dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e01  mov     rcx, [rbp+4Fh+phModule]; hLibModule
0x180046e05  test    rcx, rcx
0x180046e08  jz      short loc_180046E10
0x180046e0a  call    cs:__imp_FreeLibrary
0x180046e10  test    ebx, ebx
0x180046e12  jns     loc_180046CFE
0x180046e18  mov     eax, ebx
0x180046e1a  movzx   ecx, bx
0x180046e1d  and     eax, 1FFF0000h
0x180046e22  cmp     eax, 70000h
0x180046e27  cmovnz  ecx, ebx; dwErrCode
0x180046e2a  call    cs:__imp_SetLastError
0x180046e30  jmp     loc_180046CFE
0x180046e35  test    eax, eax
0x180046e37  jnz     short loc_180046DC5
0x180046e39  jmp     loc_180046BED
0x180046e3e  test    eax, eax
0x180046e40  jnz     short loc_180046DC5
0x180046e42  test    ecx, ecx
0x180046e44  jnz     loc_180046DC5
0x180046e4a  jmp     loc_180046BF7
0x180046e4f  call    IsOleInitializePresent
0x180046e54  test    al, al
0x180046e56  jz      loc_180046DC5
0x180046e5c  jmp     loc_180046C01
0x180046e61  call    IsGetKeyboardLayoutPresent
0x180046e66  test    al, al
0x180046e68  jz      loc_180046DC5
0x180046e6e  xor     ecx, ecx; idThread
0x180046e70  call    cs:__imp_GetKeyboardLayout
0x180046e76  mov     [rbp+4Fh+var_40], rax
0x180046e7a  jmp     loc_180046C0B
0x180046e7f  call    ResultFromKnownLastError
0x180046e84  mov     ebx, eax
0x180046e86  jmp     loc_180046CF6
```
