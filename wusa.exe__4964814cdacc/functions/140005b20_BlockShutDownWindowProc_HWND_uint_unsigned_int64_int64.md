# BlockShutDownWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140005b20`
- end: `0x140005c67`
- name: `?BlockShutDownWindowProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `327`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005b20`
- `0x14001327c`
- `0x1400133f0`
- `0x140013490`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x140005b7e`
- `KERNEL32!GetCommandLineW` at `0x140005b95`
- `KERNEL32!GetCommandLineW` at `0x140005b7e`
- `KERNEL32!GetCommandLineW` at `0x140005b95`
- `USER32!PeekMessageW` at `0x140005bf7`
- `USER32!PeekMessageW` at `0x140005bf7`
- `USER32!MsgWaitForMultipleObjects` at `0x140005c19`
- `USER32!MsgWaitForMultipleObjects` at `0x140005c19`
- `USER32!DefWindowProcW` at `0x140005b3c`
- `USER32!DispatchMessageW` at `0x140005be0`
- `USER32!DispatchMessageW` at `0x140005be0`
- `USER32!TranslateMessage` at `0x140005bd5`
- `USER32!TranslateMessage` at `0x140005bd5`

## pseudocode

```c
LRESULT __fastcall BlockShutDownWindowProc(HWND a1, UINT a2, WPARAM a3, LPARAM a4)
{
  LPWSTR CommandLineW; // rax
  LPWSTR v7; // rax
  DWORD v8; // eax
  MSG Msg; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 == 17 )
  {
    WusaLogDebugEventA(
      L"BlockShutDownWindowProc",
      102,
      "WM_QUERYENDSESSION received, wParam: 0X%x, lParam: 0X%x",
      a3,
      a4);
  }
  else
  {
    if ( a2 != 22 )
      return DefWindowProcW(a1, a2, a3, a4);
    WusaLogDebugEventA(L"BlockShutDownWindowProc", 107, "WM_ENDSESSION received, wParam: 0X%x, lParam: 0X%x", a3, a4);
    if ( a3 )
    {
      if ( dword_140020250 )
      {
        if ( dword_14002017C )
        {
          CommandLineW = GetCommandLineW();
          WusaEventUninstallRebootInitiated(off_1400201D8, CommandLineW);
        }
        else
        {
          v7 = GetCommandLineW();
          WusaEventInstallRebootInitiated(off_1400201D8, v7);
        }
      }
      while ( 1 )
      {
        v8 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
        if ( !v8 )
          break;
        if ( v8 != 1 )
        {
          WusaLogDebugEventA(
            L"BlockShutDownWindowProc",
            158,
            "Failed. Unexpected return from MsgWaitForMultipleObjects()");
          return 0;
        }
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          if ( Msg.message != 22 )
          {
            TranslateMessage(&Msg);
            DispatchMessageW(&Msg);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005b20  push    rbx
0x140005b22  sub     rsp, 60h
0x140005b26  mov     rbx, r8
0x140005b29  cmp     edx, 11h
0x140005b2c  jz      loc_140005C3F
0x140005b32  cmp     edx, 16h
0x140005b35  jz      short loc_140005B43
0x140005b37  add     rsp, 60h
0x140005b3b  pop     rbx
0x140005b3c  jmp     cs:__imp_DefWindowProcW
0x140005b43  mov     qword ptr [rsp+68h+wRemoveMsg], r9
0x140005b48  lea     r8, aWmEndsessionRe; "WM_ENDSESSION received, wParam: 0X%x, l"...
0x140005b4f  mov     r9, rbx
0x140005b52  lea     rcx, aBlockshutdownw; "BlockShutDownWindowProc"
0x140005b59  mov     edx, 6Bh ; 'k'
0x140005b5e  call    WusaLogDebugEventA
0x140005b63  test    rbx, rbx
0x140005b66  jz      loc_140005C5F
0x140005b6c  cmp     cs:dword_140020250, 0
0x140005b73  jz      short loc_140005BAA
0x140005b75  cmp     cs:dword_14002017C, 0
0x140005b7c  jz      short loc_140005B95
0x140005b7e  call    cs:__imp_GetCommandLineW
0x140005b84  mov     rcx, cs:off_1400201D8
0x140005b8b  mov     rdx, rax
0x140005b8e  call    WusaEventUninstallRebootInitiated
0x140005b93  jmp     short loc_140005BAA
0x140005b95  call    cs:__imp_GetCommandLineW
0x140005b9b  mov     rcx, cs:off_1400201D8
0x140005ba2  mov     rdx, rax
0x140005ba5  call    WusaEventInstallRebootInitiated
0x140005baa  mov     ebx, 1
0x140005baf  jmp     short loc_140005C01
0x140005bb1  cmp     eax, ebx
0x140005bb3  jnz     short loc_140005C25
0x140005bb5  xorps   xmm0, xmm0
0x140005bb8  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x140005bbd  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x140005bc2  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x140005bc7  jmp     short loc_140005BE6
0x140005bc9  cmp     [rsp+68h+Msg.message], 16h
0x140005bce  jz      short loc_140005BE6
0x140005bd0  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140005bd5  call    cs:__imp_TranslateMessage
0x140005bdb  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140005be0  call    cs:__imp_DispatchMessageW
0x140005be6  xor     r9d, r9d; wMsgFilterMax
0x140005be9  mov     [rsp+68h+wRemoveMsg], ebx; wRemoveMsg
0x140005bed  xor     r8d, r8d; wMsgFilterMin
0x140005bf0  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140005bf5  xor     edx, edx; hWnd
0x140005bf7  call    cs:__imp_PeekMessageW
0x140005bfd  test    eax, eax
0x140005bff  jnz     short loc_140005BC9
0x140005c01  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140005c05  mov     [rsp+68h+wRemoveMsg], 1CFFh; dwWakeMask
0x140005c0d  xor     r8d, r8d; fWaitAll
0x140005c10  lea     rdx, pHandles; pHandles
0x140005c17  mov     ecx, ebx; nCount
0x140005c19  call    cs:__imp_MsgWaitForMultipleObjects
0x140005c1f  test    eax, eax
0x140005c21  jnz     short loc_140005BB1
0x140005c23  jmp     short loc_140005C5F
0x140005c25  lea     r8, aFailedUnexpect; "Failed. Unexpected return from MsgWaitF"...
0x140005c2c  mov     edx, 9Eh
0x140005c31  lea     rcx, aBlockshutdownw; "BlockShutDownWindowProc"
0x140005c38  call    WusaLogDebugEventA
0x140005c3d  jmp     short loc_140005C5F
0x140005c3f  mov     qword ptr [rsp+68h+wRemoveMsg], r9
0x140005c44  lea     r8, aWmQueryendsess; "WM_QUERYENDSESSION received, wParam: 0X"...
0x140005c4b  mov     r9, rbx
0x140005c4e  lea     rcx, aBlockshutdownw; "BlockShutDownWindowProc"
0x140005c55  mov     edx, 66h ; 'f'
0x140005c5a  call    WusaLogDebugEventA
0x140005c5f  xor     eax, eax
0x140005c61  add     rsp, 60h
0x140005c65  pop     rbx
0x140005c66  retn
```
