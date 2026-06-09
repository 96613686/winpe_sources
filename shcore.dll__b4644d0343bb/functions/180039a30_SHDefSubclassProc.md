# SHDefSubclassProc

- ea: `0x180039a30`
- end: `0x180039b3c`
- name: `SHDefSubclassProc`
- size: `268`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180039a30`
- `0x180039b44`
- `0x180039de4`
- `0x18009313c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039a8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039a8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b27`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180039a4f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180039a4f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x180039a77`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x180039a77`

## pseudocode

```c
__int64 __fastcall SHDefSubclassProc(HWND hWnd, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rbp
  _DWORD *PropW; // rax
  _DWORD *v10; // rdi
  int v11; // ebx
  struct SUBCLASS_FRAME *v12; // rbx
  int v13; // r14d
  unsigned int i; // ecx
  struct SUBCLASS_FRAME *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 (__fastcall *v18)(HWND, _QWORD, __int64, __int64, __int64, __int64); // r10
  __int64 v19; // rax
  DWORD CurrentThreadId; // eax
  __int64 v22; // rcx

  v8 = 0;
  if ( IsWindow(hWnd) )
  {
    if ( !IsWindowOnCurrentThread(hWnd) )
    {
      CurrentThreadId = GetCurrentThreadId();
      MicrosoftTelemetryAssertTriggeredArgs(v22, (unsigned int)hWnd, CurrentThreadId);
    }
    PropW = GetPropW(hWnd, L"SHCore.Subclass.Data");
    v10 = PropW;
    if ( PropW )
    {
      v11 = PropW[3];
      if ( GetCurrentThreadId() == v11 )
      {
        v12 = (struct SUBCLASS_FRAME *)*((_QWORD *)v10 + 2);
        if ( v12 )
        {
          v13 = 1;
          for ( i = *(_DWORD *)v12 - 1; !*(_QWORD *)&v10[6 * i + 6]; --i )
            ++v13;
          v15 = (struct SUBCLASS_FRAME *)*((_QWORD *)v10 + 2);
          *(_DWORD *)v12 -= v13;
          UpdateDeepestCall(v15);
          v19 = v18(hWnd, a2, a3, a4, v17, v16);
          *(_DWORD *)v12 += v13;
          v8 = v19;
          UpdateDeepestCall(v12);
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180039a30  push    rbx
0x180039a32  push    rbp
0x180039a33  push    rsi
0x180039a34  push    rdi
0x180039a35  push    r12
0x180039a37  push    r13
0x180039a39  push    r14
0x180039a3b  push    r15
0x180039a3d  sub     rsp, 48h
0x180039a41  mov     r15, r9
0x180039a44  mov     r12, r8
0x180039a47  mov     r13d, edx
0x180039a4a  mov     rsi, rcx
0x180039a4d  xor     ebp, ebp
0x180039a4f  call    cs:__imp_IsWindow
0x180039a55  test    eax, eax
0x180039a57  jz      loc_180039B0C
0x180039a5d  mov     rcx, rsi; hWnd
0x180039a60  call    ?IsWindowOnCurrentThread@@YA_NPEAUHWND__@@@Z; IsWindowOnCurrentThread(HWND__ *)
0x180039a65  test    al, al
0x180039a67  jz      loc_180039B27
0x180039a6d  lea     rdx, aShcoreSubclass_5; "SHCore.Subclass.Data"
0x180039a74  mov     rcx, rsi; hWnd
0x180039a77  call    cs:__imp_GetPropW
0x180039a7d  mov     rdi, rax
0x180039a80  test    rax, rax
0x180039a83  jz      loc_180039B0C
0x180039a89  mov     ebx, [rax+0Ch]
0x180039a8c  call    cs:__imp_GetCurrentThreadId
0x180039a92  cmp     eax, ebx
0x180039a94  jnz     short loc_180039B0C
0x180039a96  mov     rbx, [rdi+10h]
0x180039a9a  test    rbx, rbx
0x180039a9d  jz      short loc_180039B0C
0x180039a9f  mov     r9d, [rbx]
0x180039aa2  mov     r14d, 1
0x180039aa8  lea     ecx, [r9-1]
0x180039aac  mov     eax, ecx
0x180039aae  inc     rax
0x180039ab1  lea     rax, [rax+rax*2]
0x180039ab5  cmp     [rdi+rax*8], rbp
0x180039ab9  jz      short loc_180039B20
0x180039abb  mov     eax, ecx
0x180039abd  sub     r9d, r14d
0x180039ac0  inc     rax
0x180039ac3  lea     rcx, [rax+rax*2]
0x180039ac7  mov     r10, [rdi+rcx*8]
0x180039acb  mov     r8, [rdi+rcx*8+8]
0x180039ad0  mov     rdx, [rdi+rcx*8+10h]
0x180039ad5  mov     rcx, rbx; struct SUBCLASS_FRAME *
0x180039ad8  mov     [rbx], r9d
0x180039adb  call    ?UpdateDeepestCall@@YAXPEAUSUBCLASS_FRAME@@@Z; UpdateDeepestCall(SUBCLASS_FRAME *)
0x180039ae0  mov     [rsp+88h+var_60], rdx
0x180039ae5  mov     r9, r15
0x180039ae8  mov     [rsp+88h+var_68], r8
0x180039aed  mov     edx, r13d
0x180039af0  mov     r8, r12
0x180039af3  mov     rcx, rsi
0x180039af6  mov     rax, r10
0x180039af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039afe  add     [rbx], r14d
0x180039b01  mov     rcx, rbx; struct SUBCLASS_FRAME *
0x180039b04  mov     rbp, rax
0x180039b07  call    ?UpdateDeepestCall@@YAXPEAUSUBCLASS_FRAME@@@Z; UpdateDeepestCall(SUBCLASS_FRAME *)
0x180039b0c  mov     rax, rbp
0x180039b0f  add     rsp, 48h
0x180039b13  pop     r15
0x180039b15  pop     r14
0x180039b17  pop     r13
0x180039b19  pop     r12
0x180039b1b  pop     rdi
0x180039b1c  pop     rsi
0x180039b1d  pop     rbp
0x180039b1e  pop     rbx
0x180039b1f  retn
0x180039b20  inc     r14d
0x180039b23  dec     ecx
0x180039b25  jmp     short loc_180039AAC
0x180039b27  call    cs:__imp_GetCurrentThreadId
0x180039b2d  mov     r8d, eax
0x180039b30  mov     edx, esi
0x180039b32  call    MicrosoftTelemetryAssertTriggeredArgs
0x180039b37  jmp     loc_180039A6D
```
