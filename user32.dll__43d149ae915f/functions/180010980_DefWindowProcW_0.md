# DefWindowProcW_0

- ea: `0x180010980`
- end: `0x180010b63`
- name: `DefWindowProcW_0`
- size: `483`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `9`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010950`
- `0x180011680`
- `0x180019b90`
- `0x18005a210`
- `0x18005c9a0`
- `0x18005ded0`
- `0x180060370`
- `0x1800782a0`
- `0x18007f9e0`

## callees

- `0x180007ef0`
- `0x18000d210`
- `0x18000f140`
- `0x180010980`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserLoadUserApiHook` at `0x180010adb`
- `win32u!NtUserLoadUserApiHook` at `0x180010adb`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x180010acd`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x180010acd`
- `ntdll!RtlEnterCriticalSection` at `0x180010af2`
- `ntdll!RtlEnterCriticalSection` at `0x180010af2`
- `ntdll!RtlLeaveCriticalSection` at `0x180010b2c`
- `ntdll!RtlLeaveCriticalSection` at `0x180010b2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010b52`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010b52`

## pseudocode

```c
LRESULT __stdcall DefWindowProcW_0(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  BOOL v8; // eax
  int v9; // ebx
  struct tagWND *v10; // rax
  LRESULT v11; // rdi
  __int64 v12; // rax
  signed __int32 v13; // eax
  HMODULE v15; // rbx
  int (*v16)(unsigned int, void *); // rsi

  v8 = ghmodUserApiHook && gfUserApiHook;
  if ( !*(_DWORD *)&gfServerProcess && !v8 && (*(_BYTE *)gpsi & 0x10) != 0 && !RtlIsThreadWithinLoaderCallout() )
    NtUserLoadUserApiHook();
  _InterlockedIncrement(&gcCallUserApiHook);
  if ( ghmodUserApiHook && gfUserApiHook )
  {
    v9 = 1;
  }
  else
  {
    _InterlockedDecrement(&gcCallUserApiHook);
    v9 = 0;
  }
  if ( qword_1800C8068
    && (v12 = Msg >> 3, (unsigned int)v12 < dword_1800C8070)
    && ((unsigned __int8)(1 << (Msg & 7)) & *(_BYTE *)(v12 + qword_1800C8068)) != 0 )
  {
    v11 = ((__int64 (__fastcall *)(HWND, _QWORD, WPARAM, LPARAM))off_1800C8060)(hWnd, Msg, wParam, lParam);
  }
  else
  {
    v10 = ValidateHwnd(hWnd);
    if ( v10 || Msg == 306 || Msg == 309 || Msg == 310 || Msg == 312 )
      v11 = RealDefWindowProcWorker(v10, Msg, wParam, lParam, 0);
    else
      v11 = 0;
  }
  if ( v9 )
  {
    v13 = _InterlockedExchangeAdd(&gcCallUserApiHook, 0xFFFFFFFF);
    if ( !gcLoadUserApiHook && v13 == 1 )
    {
      RtlEnterCriticalSection(&gcsUserApiHook);
      if ( gcLoadUserApiHook )
      {
        v15 = 0;
        v16 = 0;
      }
      else
      {
        v15 = ghmodUserApiHook;
        v16 = gpfnInitUserApi;
        ghmodUserApiHook = 0;
        gpfnInitUserApi = 0;
      }
      RtlLeaveCriticalSection(&gcsUserApiHook);
      if ( v16 )
        ((void (__fastcall *)(__int64, _QWORD))v16)(1, 0);
      if ( v15 )
        FreeLibrary(v15);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180010980  push    rbx
0x180010982  push    rsi
0x180010983  push    rdi
0x180010984  push    r14
0x180010986  push    r15
0x180010988  sub     rsp, 40h
0x18001098c  mov     r14, r9
0x18001098f  mov     r15, r8
0x180010992  mov     edi, edx
0x180010994  mov     rsi, rcx
0x180010997  cmp     cs:ghmodUserApiHook, 0
0x18001099f  jz      loc_180010AA8
0x1800109a5  cmp     cs:gfUserApiHook, 0
0x1800109ac  jz      loc_180010AA8
0x1800109b2  mov     eax, 1
0x1800109b7  cmp     cs:gfServerProcess, 0
0x1800109be  jnz     short loc_1800109C8
0x1800109c0  test    eax, eax
0x1800109c2  jz      loc_180010ABD
0x1800109c8  lock inc cs:gcCallUserApiHook
0x1800109cf  cmp     cs:ghmodUserApiHook, 0
0x1800109d7  jz      loc_180010AAF
0x1800109dd  cmp     cs:gfUserApiHook, 0
0x1800109e4  jz      loc_180010AAF
0x1800109ea  mov     ebx, 1
0x1800109ef  mov     [rsp+68h+var_38], ebx
0x1800109f3  mov     r8, cs:qword_1800C8068
0x1800109fa  test    r8, r8
0x1800109fd  jnz     short loc_180010A46
0x1800109ff  mov     rcx, rsi; HWND
0x180010a02  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180010a07  test    rax, rax
0x180010a0a  jz      short loc_180010A29
0x180010a0c  mov     [rsp+68h+var_48], 0; unsigned int
0x180010a14  mov     r9, r14; __int64
0x180010a17  mov     r8, r15; unsigned __int64
0x180010a1a  mov     edx, edi; unsigned int
0x180010a1c  mov     rcx, rax; struct tagWND *
0x180010a1f  call    ?RealDefWindowProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z; RealDefWindowProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)
0x180010a24  mov     rdi, rax
0x180010a27  jmp     short loc_180010A7F
0x180010a29  mov     ecx, edi
0x180010a2b  sub     ecx, 132h
0x180010a31  jz      short loc_180010A0C
0x180010a33  sub     ecx, 3
0x180010a36  jz      short loc_180010A0C
0x180010a38  sub     ecx, 1
0x180010a3b  jz      short loc_180010A0C
0x180010a3d  cmp     ecx, 2
0x180010a40  jz      short loc_180010A0C
0x180010a42  xor     edi, edi
0x180010a44  jmp     short loc_180010A7F
0x180010a46  mov     eax, edi
0x180010a48  shr     eax, 3
0x180010a4b  cmp     eax, cs:dword_1800C8070
0x180010a51  jnb     short loc_1800109FF
0x180010a53  mov     ecx, edi
0x180010a55  and     ecx, 7
0x180010a58  mov     edx, 1
0x180010a5d  shl     edx, cl
0x180010a5f  test    [rax+r8], dl
0x180010a63  jz      short loc_1800109FF
0x180010a65  mov     r9, r14
0x180010a68  mov     r8, r15
0x180010a6b  mov     edx, edi
0x180010a6d  mov     rcx, rsi
0x180010a70  mov     rax, cs:off_1800C8060
0x180010a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a7c  mov     rdi, rax
0x180010a7f  test    ebx, ebx
0x180010a81  jz      short loc_180010A99
0x180010a83  mov     eax, 0FFFFFFFFh
0x180010a88  lock xadd cs:gcCallUserApiHook, eax
0x180010a90  cmp     cs:?gcLoadUserApiHook@@3JA, 0; long gcLoadUserApiHook
0x180010a97  jz      short loc_180010AE6
0x180010a99  mov     rax, rdi
0x180010a9c  add     rsp, 40h
0x180010aa0  pop     r15
0x180010aa2  pop     r14
0x180010aa4  pop     rdi
0x180010aa5  pop     rsi
0x180010aa6  pop     rbx
0x180010aa7  retn
0x180010aa8  xor     eax, eax
0x180010aaa  jmp     loc_1800109B7
0x180010aaf  lock dec cs:gcCallUserApiHook
0x180010ab6  xor     ebx, ebx
0x180010ab8  jmp     loc_1800109EF
0x180010abd  mov     rax, cs:gpsi
0x180010ac4  test    byte ptr [rax], 10h
0x180010ac7  jz      loc_1800109C8
0x180010acd  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x180010ad3  test    al, al
0x180010ad5  jnz     loc_1800109C8
0x180010adb  call    cs:__imp_NtUserLoadUserApiHook
0x180010ae1  jmp     loc_1800109C8
0x180010ae6  cmp     eax, 1
0x180010ae9  jnz     short loc_180010A99
0x180010aeb  lea     rcx, ?gcsUserApiHook@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180010af2  call    cs:__imp_RtlEnterCriticalSection
0x180010af8  cmp     cs:?gcLoadUserApiHook@@3JA, 0; long gcLoadUserApiHook
0x180010aff  jnz     short loc_180010B5D
0x180010b01  mov     rbx, cs:ghmodUserApiHook
0x180010b08  mov     rsi, cs:?gpfnInitUserApi@@3P6AHKPEAX@ZEA; int (*gpfnInitUserApi)(ulong,void *)
0x180010b0f  mov     cs:ghmodUserApiHook, 0
0x180010b1a  mov     cs:?gpfnInitUserApi@@3P6AHKPEAX@ZEA, 0; int (*gpfnInitUserApi)(ulong,void *)
0x180010b25  lea     rcx, ?gcsUserApiHook@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180010b2c  call    cs:__imp_RtlLeaveCriticalSection
0x180010b32  test    rsi, rsi
0x180010b35  jz      short loc_180010B46
0x180010b37  xor     edx, edx
0x180010b39  mov     ecx, 1
0x180010b3e  mov     rax, rsi
0x180010b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b46  test    rbx, rbx
0x180010b49  jz      loc_180010A99
0x180010b4f  mov     rcx, rbx; hLibModule
0x180010b52  call    cs:__imp_FreeLibrary
0x180010b58  jmp     loc_180010A99
0x180010b5d  xor     ebx, ebx
0x180010b5f  xor     esi, esi
0x180010b61  jmp     short loc_180010B25
0x1800973d0  push    rbp
0x1800973d2  sub     rsp, 30h
0x1800973d6  mov     rbp, rdx
0x1800973d9  cmp     dword ptr [rbp+30h], 0
0x1800973dd  jz      short loc_1800973E5
0x1800973df  call    _EndUserApiHook
0x1800973e4  nop
0x1800973e5  add     rsp, 30h
0x1800973e9  pop     rbp
0x1800973ea  retn
```
