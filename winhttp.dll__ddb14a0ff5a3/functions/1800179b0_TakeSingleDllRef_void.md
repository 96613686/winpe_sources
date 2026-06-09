# TakeSingleDllRef(void)

- ea: `0x1800179b0`
- end: `0x180017af1`
- name: `?TakeSingleDllRef@@YAJXZ`
- size: `321`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180017678`

## callees

- `0x1800179b0`
- `0x180018420`
- `0x18001851c`
- `0x180018ee8`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800179eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800179eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180017a29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180017a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ae6`

## pseudocode

```c
__int64 TakeSingleDllRef(void)
{
  struct _TP_WAIT *v0; // rsi
  HANDLE EventA; // rax
  void *v2; // rdi
  signed int v3; // ebx
  signed int v5; // eax
  signed int LastError; // eax
  struct _TP_WAIT *v7; // [rsp+28h] [rbp-20h] BYREF
  HMODULE phModule; // [rsp+30h] [rbp-18h] BYREF

  v0 = 0;
  v7 = 0;
  phModule = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  v2 = EventA;
  if ( EventA )
  {
    v3 = WxCreateThreadpoolWait(
           (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int))FailFastThreadpoolWaitCallback<&void SafeTerminateDll(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)>,
           EventA,
           0,
           &v7);
    if ( v3 >= 0 )
    {
      if ( GetModuleHandleExA(4u, (LPCSTR)TakeSingleDllRef, &phModule) )
      {
        WxSetThreadpoolWait(v7, v2, 0);
        g_hTerminateEvent = v2;
        v2 = 0;
        v3 = 0;
        goto LABEL_5;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147418113;
    }
    v0 = v7;
  }
  else
  {
    v5 = GetLastError();
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147418113;
  }
LABEL_5:
  WxCloseThreadpoolWait(v0);
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800179b0  mov     r11, rsp
0x1800179b3  mov     [r11+8], rbx
0x1800179b7  mov     [r11+10h], rsi
0x1800179bb  push    rdi
0x1800179bc  sub     rsp, 40h
0x1800179c0  mov     rax, cs:__security_cookie
0x1800179c7  xor     rax, rsp
0x1800179ca  mov     [rsp+48h+var_10], rax
0x1800179cf  xor     esi, esi
0x1800179d1  mov     [rsp+48h+var_24], 0
0x1800179d9  xor     r9d, r9d; lpName
0x1800179dc  mov     [r11-20h], rsi
0x1800179e0  xor     r8d, r8d; bInitialState
0x1800179e3  mov     [r11-18h], rsi
0x1800179e7  xor     edx, edx; bManualReset
0x1800179e9  xor     ecx, ecx; lpEventAttributes
0x1800179eb  call    cs:__imp_CreateEventA
0x1800179f1  mov     rdi, rax
0x1800179f4  test    rax, rax
0x1800179f7  jz      loc_180017A91
0x1800179fd  lea     r9, [rsp+48h+var_20]; struct _TP_WAIT **
0x180017a02  xor     r8d, r8d; struct _TP_CALLBACK_ENVIRON_V3 *
0x180017a05  mov     rdx, rax; void *
0x180017a08  lea     rcx, ??$FailFastThreadpoolWaitCallback@$1?SafeTerminateDll@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)
0x180017a0f  call    ?WxCreateThreadpoolWait@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z; WxCreateThreadpoolWait(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_WAIT * *)
0x180017a14  mov     ebx, eax
0x180017a16  test    eax, eax
0x180017a18  js      short loc_180017A82
0x180017a1a  lea     r8, [rsp+48h+phModule]; phModule
0x180017a1f  lea     rdx, ?TakeSingleDllRef@@YAJXZ; lpModuleName
0x180017a26  lea     ecx, [rsi+4]; dwFlags
0x180017a29  call    cs:__imp_GetModuleHandleExA
0x180017a2f  test    eax, eax
0x180017a31  jz      loc_180017ABA
0x180017a37  mov     rcx, [rsp+48h+var_20]; struct _TP_WAIT *
0x180017a3c  xor     r8d, r8d; struct _FILETIME *
0x180017a3f  mov     rdx, rdi; void *
0x180017a42  call    ?WxSetThreadpoolWait@@YAXPEAU_TP_WAIT@@PEAXPEAU_FILETIME@@@Z; WxSetThreadpoolWait(_TP_WAIT *,void *,_FILETIME *)
0x180017a47  mov     cs:?g_hTerminateEvent@@3PEAXEA, rdi; void * g_hTerminateEvent
0x180017a4e  xor     edi, edi
0x180017a50  xor     ebx, ebx
0x180017a52  mov     rcx, rsi; struct _TP_WAIT *
0x180017a55  call    ?WxCloseThreadpoolWait@@YAXPEAU_TP_WAIT@@@Z; WxCloseThreadpoolWait(_TP_WAIT *)
0x180017a5a  test    rdi, rdi
0x180017a5d  jnz     loc_180017AE3
0x180017a63  mov     eax, ebx
0x180017a65  mov     rcx, [rsp+48h+var_10]
0x180017a6a  xor     rcx, rsp; StackCookie
0x180017a6d  call    __security_check_cookie
0x180017a72  mov     rbx, [rsp+48h+arg_0]
0x180017a77  mov     rsi, [rsp+48h+arg_8]
0x180017a7c  add     rsp, 40h
0x180017a80  pop     rdi
0x180017a81  retn
0x180017a82  mov     [rsp+48h+var_24], 0F2h
0x180017a8a  mov     rsi, [rsp+48h+var_20]
0x180017a8f  jmp     short loc_180017A52
0x180017a91  call    cs:__imp_GetLastError
0x180017a97  mov     ebx, eax
0x180017a99  test    eax, eax
0x180017a9b  jle     short loc_180017AA6
0x180017a9d  movzx   ebx, ax
0x180017aa0  or      ebx, 80070000h
0x180017aa6  test    ebx, ebx
0x180017aa8  mov     [rsp+48h+var_24], 0EAh
0x180017ab0  mov     eax, 8000FFFFh
0x180017ab5  cmovns  ebx, eax
0x180017ab8  jmp     short loc_180017A52
0x180017aba  call    cs:__imp_GetLastError
0x180017ac0  mov     ebx, eax
0x180017ac2  test    eax, eax
0x180017ac4  jle     short loc_180017ACF
0x180017ac6  movzx   ebx, ax
0x180017ac9  or      ebx, 80070000h
0x180017acf  test    ebx, ebx
0x180017ad1  mov     [rsp+48h+var_24], 0FAh
0x180017ad9  mov     eax, 8000FFFFh
0x180017ade  cmovns  ebx, eax
0x180017ae1  jmp     short loc_180017A8A
0x180017ae3  mov     rcx, rdi; hObject
0x180017ae6  call    cs:__imp_CloseHandle
0x180017aec  jmp     loc_180017A63
```
