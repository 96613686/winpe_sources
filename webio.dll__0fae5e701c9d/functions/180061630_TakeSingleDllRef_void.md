# TakeSingleDllRef(void)

- ea: `0x180061630`
- end: `0x180061783`
- name: `?TakeSingleDllRef@@YAJXZ`
- size: `339`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180055300`

## callees

- `0x180061630`
- `0x1800617c8`
- `0x1800619fc`
- `0x180061a30`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061740`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800616a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800616a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006166b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006166b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061772`

## pseudocode

```c
__int64 TakeSingleDllRef(void)
{
  struct _TP_WAIT *v0; // rsi
  HANDLE EventA; // rax
  void (*v2)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int); // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v3; // r8
  void *v4; // rdi
  signed int v5; // ebx
  struct _FILETIME *v6; // r8
  signed int v8; // eax
  signed int LastError; // eax
  struct _TP_WAIT *v10; // [rsp+28h] [rbp-20h] BYREF
  HMODULE phModule; // [rsp+30h] [rbp-18h] BYREF

  v0 = 0;
  v10 = 0;
  phModule = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  v4 = EventA;
  if ( EventA )
  {
    v5 = WxCreateThreadpoolWait(v2, EventA, v3, &v10);
    if ( v5 >= 0 )
    {
      if ( GetModuleHandleExA(4u, (LPCSTR)TakeSingleDllRef, &phModule) )
      {
        WxSetThreadpoolWait(v10, v4, v6);
        g_hTerminateEvent = v4;
        v4 = 0;
        v5 = 0;
        goto LABEL_5;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147418113;
    }
    v0 = v10;
  }
  else
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147418113;
  }
LABEL_5:
  WxCloseThreadpoolWait(v0);
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180061630  mov     r11, rsp
0x180061633  mov     [r11+8], rbx
0x180061637  mov     [r11+10h], rsi
0x18006163b  push    rdi
0x18006163c  sub     rsp, 40h
0x180061640  mov     rax, cs:__security_cookie
0x180061647  xor     rax, rsp
0x18006164a  mov     [rsp+48h+var_10], rax
0x18006164f  xor     esi, esi
0x180061651  mov     [rsp+48h+var_24], 0
0x180061659  xor     r9d, r9d; lpName
0x18006165c  mov     [r11-20h], rsi
0x180061660  xor     r8d, r8d; bInitialState
0x180061663  mov     [r11-18h], rsi
0x180061667  xor     edx, edx; bManualReset
0x180061669  xor     ecx, ecx; lpEventAttributes
0x18006166b  call    cs:__imp_CreateEventA
0x180061672  nop     dword ptr [rax+rax+00h]
0x180061677  mov     rdi, rax
0x18006167a  test    rax, rax
0x18006167d  jz      loc_180061711
0x180061683  lea     r9, [rsp+48h+var_20]; struct _TP_WAIT **
0x180061688  mov     rdx, rax; void *
0x18006168b  call    ?WxCreateThreadpoolWait@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z; WxCreateThreadpoolWait(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_WAIT * *)
0x180061690  mov     ebx, eax
0x180061692  test    eax, eax
0x180061694  js      short loc_180061702
0x180061696  lea     r8, [rsp+48h+phModule]; phModule
0x18006169b  lea     rdx, ?TakeSingleDllRef@@YAJXZ; lpModuleName
0x1800616a2  lea     ecx, [rsi+4]; dwFlags
0x1800616a5  call    cs:__imp_GetModuleHandleExA
0x1800616ac  nop     dword ptr [rax+rax+00h]
0x1800616b1  test    eax, eax
0x1800616b3  jz      loc_180061740
0x1800616b9  mov     rcx, [rsp+48h+var_20]; struct _TP_WAIT *
0x1800616be  mov     rdx, rdi; void *
0x1800616c1  call    ?WxSetThreadpoolWait@@YAXPEAU_TP_WAIT@@PEAXPEAU_FILETIME@@@Z; WxSetThreadpoolWait(_TP_WAIT *,void *,_FILETIME *)
0x1800616c6  mov     cs:?g_hTerminateEvent@@3PEAXEA, rdi; void * g_hTerminateEvent
0x1800616cd  xor     edi, edi
0x1800616cf  xor     ebx, ebx
0x1800616d1  mov     rcx, rsi; struct _TP_WAIT *
0x1800616d4  call    ?WxCloseThreadpoolWait@@YAXPEAU_TP_WAIT@@@Z; WxCloseThreadpoolWait(_TP_WAIT *)
0x1800616d9  test    rdi, rdi
0x1800616dc  jnz     loc_18006176F
0x1800616e2  mov     eax, ebx
0x1800616e4  mov     rcx, [rsp+48h+var_10]
0x1800616e9  xor     rcx, rsp; StackCookie
0x1800616ec  call    __security_check_cookie
0x1800616f1  mov     rbx, [rsp+48h+arg_0]
0x1800616f6  mov     rsi, [rsp+48h+arg_8]
0x1800616fb  add     rsp, 40h
0x1800616ff  pop     rdi
0x180061700  retn
0x180061702  mov     [rsp+48h+var_24], 0F2h
0x18006170a  mov     rsi, [rsp+48h+var_20]
0x18006170f  jmp     short loc_1800616D1
0x180061711  call    cs:__imp_GetLastError
0x180061718  nop     dword ptr [rax+rax+00h]
0x18006171d  mov     ebx, eax
0x18006171f  test    eax, eax
0x180061721  jle     short loc_18006172C
0x180061723  movzx   ebx, ax
0x180061726  or      ebx, 80070000h
0x18006172c  test    ebx, ebx
0x18006172e  mov     [rsp+48h+var_24], 0EAh
0x180061736  mov     eax, 8000FFFFh
0x18006173b  cmovns  ebx, eax
0x18006173e  jmp     short loc_1800616D1
0x180061740  call    cs:__imp_GetLastError
0x180061747  nop     dword ptr [rax+rax+00h]
0x18006174c  mov     ebx, eax
0x18006174e  test    eax, eax
0x180061750  jle     short loc_18006175B
0x180061752  movzx   ebx, ax
0x180061755  or      ebx, 80070000h
0x18006175b  test    ebx, ebx
0x18006175d  mov     [rsp+48h+var_24], 0FAh
0x180061765  mov     eax, 8000FFFFh
0x18006176a  cmovns  ebx, eax
0x18006176d  jmp     short loc_18006170A
0x18006176f  mov     rcx, rdi; hObject
0x180061772  call    cs:__imp_CloseHandle
0x180061779  nop     dword ptr [rax+rax+00h]
0x18006177e  jmp     loc_1800616E2
```
