# DisplayDuiFromEapConfig

- ea: `0x180016b60`
- end: `0x180016d45`
- name: `DisplayDuiFromEapConfig`
- size: `485`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, __int64, unsigned int, struct _PLAP_INPUT_FIELD_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180013120`

## callees

- `0x1800160f0`
- `0x180016240`
- `0x180016b60`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180016c90`
- `msvcrt!_beginthreadex` at `0x180016c90`
- `KERNEL32!CloseHandle` at `0x180016d1a`
- `KERNEL32!CloseHandle` at `0x180016d1a`
- `KERNEL32!HeapAlloc` at `0x180016c3a`
- `KERNEL32!HeapAlloc` at `0x180016c3a`
- `KERNEL32!GetProcessHeap` at `0x180016c28`
- `KERNEL32!GetProcessHeap` at `0x180016d22`
- `KERNEL32!GetProcessHeap` at `0x180016c28`
- `KERNEL32!GetProcessHeap` at `0x180016d22`
- `KERNEL32!HeapFree` at `0x180016d30`
- `KERNEL32!HeapFree` at `0x180016d30`
- `USER32!PeekMessageW` at `0x180016ce3`
- `USER32!PeekMessageW` at `0x180016ce3`
- `USER32!DispatchMessageW` at `0x180016ccb`
- `USER32!DispatchMessageW` at `0x180016ccb`
- `USER32!MsgWaitForMultipleObjects` at `0x180016d07`
- `USER32!MsgWaitForMultipleObjects` at `0x180016d07`

## pseudocode

```c
__int64 __fastcall DisplayDuiFromEapConfig(
        HWND a1,
        HINSTANCE a2,
        __int64 a3,
        unsigned int a4,
        struct _PLAP_INPUT_FIELD_DATA *a5)
{
  bool v9; // zf
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v13; // rax
  unsigned int *v14; // rdi
  void *v15; // rax
  HANDLE v16; // rax
  MSG Msg; // [rsp+30h] [rbp-68h] BYREF
  HANDLE pHandles; // [rsp+B0h] [rbp+18h] BYREF

  pHandles = 0;
  if ( a3 && (*(_DWORD *)a3 != 1 || *(_DWORD *)(a3 + 20) != 1) )
  {
    if ( a4 != 2 )
      return (unsigned int)DisplayDuiFromEapConfigInternal(a1, a2, (struct _CREDS_DLG_PARAMETERS *)a3, a4, a5);
    switch ( *(_DWORD *)a5 )
    {
      case 0:
        if ( *((_DWORD *)a5 + 645) != 1 )
        {
          v9 = *((_DWORD *)a5 + 645) == 3;
          break;
        }
        return DisplayStandardDialog((struct _CREDS_DLG_PARAMETERS *)a3, a5);
      case 1:
        if ( !*((_DWORD *)a5 + 645) )
          return DisplayStandardDialog((struct _CREDS_DLG_PARAMETERS *)a3, a5);
        v9 = *((_DWORD *)a5 + 645) == 2;
        break;
      case 2:
        if ( *((_DWORD *)a5 + 645) == 3 )
          return DisplayStandardDialog((struct _CREDS_DLG_PARAMETERS *)a3, a5);
        v9 = *((_DWORD *)a5 + 645) == 1;
        break;
      case 3:
        if ( *((_DWORD *)a5 + 645) == 2 )
          return DisplayStandardDialog((struct _CREDS_DLG_PARAMETERS *)a3, a5);
        v9 = *((_DWORD *)a5 + 645) == 0;
        break;
      default:
        return (unsigned int)DisplayDuiFromEapConfigInternal(a1, a2, (struct _CREDS_DLG_PARAMETERS *)a3, a4, a5);
    }
    if ( v9 )
      return DisplayStandardDialog((struct _CREDS_DLG_PARAMETERS *)a3, a5);
    return (unsigned int)DisplayDuiFromEapConfigInternal(a1, a2, (struct _CREDS_DLG_PARAMETERS *)a3, a4, a5);
  }
  ProcessHeap = GetProcessHeap();
  v13 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, 0x30u);
  v14 = v13;
  if ( v13 )
  {
    v13[8] = a4;
    *v13 = 0;
    *((_QWORD *)v13 + 2) = a2;
    *((_QWORD *)v13 + 1) = a1;
    *((_QWORD *)v13 + 3) = a3;
    *((_QWORD *)v13 + 5) = a5;
    v15 = (void *)_beginthreadex(0, 0, DisplayDuiFromEapConfigWorker, v13, 0, 0);
    if ( v15 == (void *)-1LL )
    {
      v11 = 1003;
    }
    else
    {
      pHandles = v15;
      do
      {
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) && Msg.message != 18 )
          DispatchMessageW(&Msg);
      }
      while ( MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu) == 1 );
      CloseHandle(pHandles);
      v11 = *v14;
    }
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v14);
  }
  else
  {
    return 14;
  }
  return v11;
}

```

## disassembly

```asm
0x180016b60  mov     rax, rsp
0x180016b63  push    rbx
0x180016b64  push    rbp
0x180016b65  push    rsi
0x180016b66  push    rdi
0x180016b67  push    r14
0x180016b69  push    r15
0x180016b6b  sub     rsp, 68h
0x180016b6f  mov     qword ptr [rax+18h], 0
0x180016b77  mov     esi, r9d
0x180016b7a  mov     rbx, r8
0x180016b7d  mov     rbp, rdx
0x180016b80  mov     r14, rcx
0x180016b83  mov     r15d, 1
0x180016b89  test    r8, r8
0x180016b8c  jz      loc_180016C28
0x180016b92  cmp     [r8], r15d
0x180016b95  jnz     short loc_180016BA1
0x180016b97  cmp     [r8+14h], r15d
0x180016b9b  jz      loc_180016C28
0x180016ba1  mov     rax, [rsp+98h+arg_20]
0x180016ba9  cmp     esi, 2
0x180016bac  jnz     short loc_180016C1C
0x180016bae  cmp     dword ptr [rax], 0
0x180016bb1  jnz     short loc_180016BC5
0x180016bb3  cmp     [rax+0A14h], r15d
0x180016bba  jz      short loc_180016C0A
0x180016bbc  cmp     dword ptr [rax+0A14h], 3
0x180016bc3  jmp     short loc_180016C08
0x180016bc5  cmp     [rax], r15d
0x180016bc8  jnz     short loc_180016BDC
0x180016bca  cmp     dword ptr [rax+0A14h], 0
0x180016bd1  jz      short loc_180016C0A
0x180016bd3  cmp     dword ptr [rax+0A14h], 2
0x180016bda  jmp     short loc_180016C08
0x180016bdc  cmp     dword ptr [rax], 2
0x180016bdf  jnz     short loc_180016BF3
0x180016be1  cmp     dword ptr [rax+0A14h], 3
0x180016be8  jz      short loc_180016C0A
0x180016bea  cmp     [rax+0A14h], r15d
0x180016bf1  jmp     short loc_180016C08
0x180016bf3  cmp     dword ptr [rax], 3
0x180016bf6  jnz     short loc_180016C1C
0x180016bf8  cmp     dword ptr [rax+0A14h], 2
0x180016bff  jz      short loc_180016C0A
0x180016c01  cmp     dword ptr [rax+0A14h], 0
0x180016c08  jnz     short loc_180016C1C
0x180016c0a  mov     rdx, rax; struct _PLAP_INPUT_FIELD_DATA *
0x180016c0d  mov     rcx, rbx; struct _CREDS_DLG_PARAMETERS *
0x180016c10  call    ?DisplayStandardDialog@@YAKPEAU_CREDS_DLG_PARAMETERS@@PEAU_PLAP_INPUT_FIELD_DATA@@@Z; DisplayStandardDialog(_CREDS_DLG_PARAMETERS *,_PLAP_INPUT_FIELD_DATA *)
0x180016c15  mov     ebx, eax
0x180016c17  jmp     loc_180016D36
0x180016c1c  mov     qword ptr [rsp+98h+InitFlag], rax; struct _PLAP_INPUT_FIELD_DATA *
0x180016c21  call    ?DisplayDuiFromEapConfigInternal@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEAU_CREDS_DLG_PARAMETERS@@KPEAU_PLAP_INPUT_FIELD_DATA@@@Z; DisplayDuiFromEapConfigInternal(HWND__ *,HINSTANCE__ *,_CREDS_DLG_PARAMETERS *,ulong,_PLAP_INPUT_FIELD_DATA *)
0x180016c26  jmp     short loc_180016C15
0x180016c28  call    cs:__imp_GetProcessHeap
0x180016c2e  mov     edx, 8; dwFlags
0x180016c33  mov     rcx, rax; hHeap
0x180016c36  lea     r8d, [rdx+28h]; dwBytes
0x180016c3a  call    cs:__imp_HeapAlloc
0x180016c40  mov     rdi, rax
0x180016c43  test    rax, rax
0x180016c46  jnz     short loc_180016C50
0x180016c48  lea     ebx, [rax+0Eh]
0x180016c4b  jmp     loc_180016D36
0x180016c50  mov     [rax+20h], esi
0x180016c53  lea     r8, ?DisplayDuiFromEapConfigWorker@@YAIPEAX@Z; StartAddress
0x180016c5a  mov     dword ptr [rax], 0
0x180016c60  mov     r9, rdi; ArgList
0x180016c63  mov     [rax+10h], rbp
0x180016c67  xor     edx, edx; StackSize
0x180016c69  mov     [rax+8], r14
0x180016c6d  xor     ecx, ecx; Security
0x180016c6f  mov     [rax+18h], rbx
0x180016c73  mov     rax, [rsp+98h+arg_20]
0x180016c7b  mov     [rsp+98h+ThrdAddr], 0; ThrdAddr
0x180016c84  mov     [rdi+28h], rax
0x180016c88  mov     [rsp+98h+InitFlag], 0; InitFlag
0x180016c90  call    cs:__imp__beginthreadex
0x180016c96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016c9a  jnz     short loc_180016CA3
0x180016c9c  mov     ebx, 3EBh
0x180016ca1  jmp     short loc_180016D22
0x180016ca3  mov     [rsp+98h+pHandles], rax
0x180016cab  xorps   xmm0, xmm0
0x180016cae  movups  xmmword ptr [rsp+98h+Msg.hwnd], xmm0
0x180016cb3  movups  xmmword ptr [rsp+98h+Msg.wParam], xmm0
0x180016cb8  movups  xmmword ptr [rsp+98h+Msg.time], xmm0
0x180016cbd  jmp     short loc_180016CD1
0x180016cbf  cmp     [rsp+98h+Msg.message], 12h
0x180016cc4  jz      short loc_180016CED
0x180016cc6  lea     rcx, [rsp+98h+Msg]; lpMsg
0x180016ccb  call    cs:__imp_DispatchMessageW
0x180016cd1  xor     r9d, r9d; wMsgFilterMax
0x180016cd4  mov     [rsp+98h+InitFlag], r15d; wRemoveMsg
0x180016cd9  xor     r8d, r8d; wMsgFilterMin
0x180016cdc  lea     rcx, [rsp+98h+Msg]; lpMsg
0x180016ce1  xor     edx, edx; hWnd
0x180016ce3  call    cs:__imp_PeekMessageW
0x180016ce9  test    eax, eax
0x180016ceb  jnz     short loc_180016CBF
0x180016ced  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180016cf1  mov     [rsp+98h+InitFlag], 1CFFh; dwWakeMask
0x180016cf9  xor     r8d, r8d; fWaitAll
0x180016cfc  lea     rdx, [rsp+98h+pHandles]; pHandles
0x180016d04  mov     ecx, r15d; nCount
0x180016d07  call    cs:__imp_MsgWaitForMultipleObjects
0x180016d0d  cmp     eax, r15d
0x180016d10  jz      short loc_180016CAB
0x180016d12  mov     rcx, [rsp+98h+pHandles]; hObject
0x180016d1a  call    cs:__imp_CloseHandle
0x180016d20  mov     ebx, [rdi]
0x180016d22  call    cs:__imp_GetProcessHeap
0x180016d28  mov     r8, rdi; lpMem
0x180016d2b  xor     edx, edx; dwFlags
0x180016d2d  mov     rcx, rax; hHeap
0x180016d30  call    cs:__imp_HeapFree
0x180016d36  mov     eax, ebx
0x180016d38  add     rsp, 68h
0x180016d3c  pop     r15
0x180016d3e  pop     r14
0x180016d40  pop     rdi
0x180016d41  pop     rsi
0x180016d42  pop     rbp
0x180016d43  pop     rbx
0x180016d44  retn
```
