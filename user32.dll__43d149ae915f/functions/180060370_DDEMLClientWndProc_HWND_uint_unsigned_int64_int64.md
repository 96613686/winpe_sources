# DDEMLClientWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180060370`
- end: `0x18006047f`
- name: `?DDEMLClientWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `271`
- prototype: `__int64 __fastcall(HWND, unsigned int, HWND, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800084f0`
- `0x18000b4e0`
- `0x18000bd00`
- `0x18000d210`
- `0x180010980`
- `0x180016310`
- `0x180019b20`
- `0x180020990`
- `0x180046dec`
- `0x18004812c`
- `0x180060370`
- `0x1800657d4`
- `0x18006e4b4`
- `0x1800784a8`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180060394`
- `ntdll!RtlEnterCriticalSection` at `0x180060394`
- `ntdll!RtlLeaveCriticalSection` at `0x1800603f8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800603f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060433`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060433`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0b41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0b41`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800a0b89`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800a0ba2`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800a0b89`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800a0ba2`

## pseudocode

```c
LRESULT __fastcall DDEMLClientWndProc(HWND a1, UINT a2, HWND a3, unsigned __int64 a4)
{
  LRESULT v8; // r15
  struct tagCONV_INFO *WindowLongPtrW; // r14
  struct tagWND *v10; // rax
  LRESULT v11; // rax
  LONG WindowLongW; // r12d
  HLOCAL v14; // rsi
  void *v15; // rax
  struct tagCL_INSTANCE_INFO *v16; // rax
  unsigned __int64 v17; // rbp
  __int64 v18; // rax
  struct tagWND *v19; // rax
  struct tagWND *v20; // rcx
  __int16 *v21; // rax
  __int16 v22; // dx
  bool v23; // zf

  v8 = 0;
  RtlEnterCriticalSection(&gcsDDEML);
  WindowLongPtrW = (struct tagCONV_INFO *)GetWindowLongPtrW(a1, 0);
  if ( a2 == 2 || a2 == 993 )
  {
    ProcessTerminateMsg(WindowLongPtrW, a3);
LABEL_5:
    v10 = ValidateHwnd(a1);
    if ( v10 )
    {
      if ( (*((_BYTE *)v10 + 18) & 8) != 0 )
        v11 = DefWindowProcA_0(a1, a2, (WPARAM)a3, a4);
      else
        v11 = DefWindowProcW_0(a1, a2, (WPARAM)a3, a4);
      v8 = v11;
    }
    goto LABEL_9;
  }
  if ( a2 != 996 )
  {
    if ( a2 != 997 )
      goto LABEL_5;
LABEL_16:
    ProcessAsyncDDEMsg(WindowLongPtrW, a2, a3, a4);
    goto LABEL_9;
  }
  WindowLongW = GetWindowLongW(a1, 44);
  if ( !WindowLongW )
    goto LABEL_16;
  v14 = LocalAlloc(0x40u, 0x80u);
  if ( !v14 || WindowLongPtrW && WindowLongW == 1 )
  {
    PostMessageW(a3, 0x3E1u, (WPARAM)a1, 0);
  }
  else
  {
    v15 = (void *)GetWindowLongPtrW(a1, 56);
    v16 = ValidateInstance(v15);
    *((_QWORD *)v14 + 1) = v16;
    if ( v16 )
    {
      *(_QWORD *)v14 = WindowLongPtrW;
      SetWindowLongPtrW(a1, 0, (LONG_PTR)v14);
      *((_QWORD *)v14 + 3) = CreateHandle((unsigned __int64)v14, 3u, *(_DWORD *)(*((_QWORD *)v14 + 1) + 16LL) & 0x7F);
      *((_WORD *)v14 + 16) = GlobalToLocalAtom(a4);
      GlobalDeleteAtom(a4);
      v17 = a4 >> 16;
      *((_WORD *)v14 + 17) = GlobalToLocalAtom(v17);
      GlobalDeleteAtom(v17);
      v18 = *((_QWORD *)v14 + 1);
      *((_QWORD *)v14 + 5) = a3;
      *((_QWORD *)v14 + 6) = a1;
      *((_WORD *)v14 + 28) = *(_WORD *)(v18 + 106) | 0x11;
      SetCommonStateFlags(a1, a3, (unsigned __int16 *)v14 + 28);
      v19 = ValidateHwnd(a3);
      v20 = v19;
      if ( v19 )
      {
        v21 = (__int16 *)*((_QWORD *)v19 + 16);
        if ( v21 )
          v21 = (__int16 *)((char *)v21 + (_QWORD)v20 - *((_QWORD *)v20 + 1));
        v22 = *v21;
        if ( (*((_BYTE *)v20 + 18) & 8) != 0 )
          v23 = v22 == *(_WORD *)(gpsi + 894);
        else
          v23 = v22 == *(_WORD *)(gpsi + 896);
        if ( v23 )
          *((_WORD *)v14 + 28) |= 4u;
      }
    }
    else
    {
      LocalFree(v14);
    }
  }
LABEL_9:
  RtlLeaveCriticalSection(&gcsDDEML);
  return v8;
}

```

## disassembly

```asm
0x180060370  push    rbx
0x180060372  push    rbp
0x180060373  push    rsi
0x180060374  push    rdi
0x180060375  push    r12
0x180060377  push    r14
0x180060379  push    r15
0x18006037b  sub     rsp, 20h
0x18006037f  mov     rbx, rcx
0x180060382  mov     rbp, r9
0x180060385  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18006038c  mov     rdi, r8
0x18006038f  mov     esi, edx
0x180060391  xor     r15d, r15d
0x180060394  call    cs:__imp_RtlEnterCriticalSection
0x18006039a  xor     edx, edx; nIndex
0x18006039c  mov     rcx, rbx; hWnd
0x18006039f  call    GetWindowLongPtrW
0x1800603a4  mov     r14, rax
0x1800603a7  mov     eax, esi
0x1800603a9  sub     eax, 2
0x1800603ac  jz      loc_18006046F
0x1800603b2  sub     eax, 3DFh
0x1800603b7  jz      loc_18006046F
0x1800603bd  sub     eax, 3
0x1800603c0  jz      short loc_180060417
0x1800603c2  cmp     eax, 1
0x1800603c5  jz      loc_18006045D
0x1800603cb  mov     rcx, rbx; HWND
0x1800603ce  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800603d3  test    rax, rax
0x1800603d6  jz      short loc_1800603F1
0x1800603d8  test    byte ptr [rax+12h], 8
0x1800603dc  mov     r9, rbp; lParam
0x1800603df  mov     r8, rdi; wParam
0x1800603e2  mov     edx, esi; Msg
0x1800603e4  mov     rcx, rbx; hWnd
0x1800603e7  jnz     short loc_180060410
0x1800603e9  call    DefWindowProcW_0
0x1800603ee  mov     r15, rax
0x1800603f1  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800603f8  call    cs:__imp_RtlLeaveCriticalSection
0x1800603fe  mov     rax, r15
0x180060401  add     rsp, 20h
0x180060405  pop     r15
0x180060407  pop     r14
0x180060409  pop     r12
0x18006040b  pop     rdi
0x18006040c  pop     rsi
0x18006040d  pop     rbp
0x18006040e  pop     rbx
0x18006040f  retn
0x180060410  call    DefWindowProcA_0
0x180060415  jmp     short loc_1800603EE
0x180060417  mov     edx, 2Ch ; ','; nIndex
0x18006041c  mov     rcx, rbx; hWnd
0x18006041f  call    GetWindowLongW
0x180060424  mov     r12d, eax
0x180060427  test    eax, eax
0x180060429  jz      short loc_18006045D
0x18006042b  mov     edx, 80h; uBytes
0x180060430  lea     ecx, [rdx-40h]; uFlags
0x180060433  call    cs:__imp_LocalAlloc
0x180060439  mov     rsi, rax
0x18006043c  test    rax, rax
0x18006043f  jz      loc_1800A0C29
0x180060445  test    r14, r14
0x180060448  jz      loc_1800A0B20
0x18006044e  cmp     r12d, 1
0x180060452  jnz     loc_1800A0B20
0x180060458  jmp     loc_1800A0C29
0x18006045d  mov     r9, rbp; __int64
0x180060460  mov     r8, rdi; HWND
0x180060463  mov     edx, esi; unsigned int
0x180060465  mov     rcx, r14; struct tagCONV_INFO *
0x180060468  call    ?ProcessAsyncDDEMsg@@YAXPEAUtagCONV_INFO@@IPEAUHWND__@@_J@Z; ProcessAsyncDDEMsg(tagCONV_INFO *,uint,HWND__ *,__int64)
0x18006046d  jmp     short loc_1800603F1
0x18006046f  mov     rdx, rdi; HWND
0x180060472  mov     rcx, r14; struct tagCONV_INFO *
0x180060475  call    ?ProcessTerminateMsg@@YAXPEAUtagCONV_INFO@@PEAUHWND__@@@Z; ProcessTerminateMsg(tagCONV_INFO *,HWND__ *)
0x18006047a  jmp     loc_1800603CB
0x1800a0b20  mov     edx, 38h ; '8'; nIndex
0x1800a0b25  mov     rcx, rbx; hWnd
0x1800a0b28  call    GetWindowLongPtrW
0x1800a0b2d  mov     rcx, rax; void *
0x1800a0b30  call    ?ValidateInstance@@YAPEAUtagCL_INSTANCE_INFO@@PEAX@Z; ValidateInstance(void *)
0x1800a0b35  mov     [rsi+8], rax
0x1800a0b39  test    rax, rax
0x1800a0b3c  jnz     short loc_1800A0B4D
0x1800a0b3e  mov     rcx, rsi; hMem
0x1800a0b41  call    cs:__imp_LocalFree
0x1800a0b47  nop
0x1800a0b48  jmp     loc_1800603F1
0x1800a0b4d  mov     r8, rsi; dwNewLong
0x1800a0b50  mov     [rsi], r14
0x1800a0b53  xor     edx, edx; nIndex
0x1800a0b55  mov     rcx, rbx; hWnd
0x1800a0b58  call    SetWindowLongPtrW
0x1800a0b5d  mov     rax, [rsi+8]
0x1800a0b61  mov     edx, 3; unsigned int
0x1800a0b66  mov     rcx, rsi; unsigned __int64
0x1800a0b69  mov     r8d, [rax+10h]
0x1800a0b6d  and     r8d, 7Fh; unsigned int
0x1800a0b71  call    ?CreateHandle@@YAPEAX_KKK@Z; CreateHandle(unsigned __int64,ulong,ulong)
0x1800a0b76  movzx   ecx, bp; unsigned __int16
0x1800a0b79  mov     [rsi+18h], rax
0x1800a0b7d  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x1800a0b82  movzx   ecx, bp; nAtom
0x1800a0b85  mov     [rsi+20h], ax
0x1800a0b89  call    cs:__imp_GlobalDeleteAtom
0x1800a0b8f  shr     rbp, 10h
0x1800a0b93  movzx   ecx, bp; unsigned __int16
0x1800a0b96  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x1800a0b9b  movzx   ecx, bp; nAtom
0x1800a0b9e  mov     [rsi+22h], ax
0x1800a0ba2  call    cs:__imp_GlobalDeleteAtom
0x1800a0ba8  mov     rax, [rsi+8]
0x1800a0bac  lea     r14, [rsi+38h]
0x1800a0bb0  mov     [rsi+28h], rdi
0x1800a0bb4  mov     r8, r14; unsigned __int16 *
0x1800a0bb7  mov     [rsi+30h], rbx
0x1800a0bbb  mov     rdx, rdi; HWND
0x1800a0bbe  movzx   ecx, word ptr [rax+6Ah]
0x1800a0bc2  or      cx, 11h
0x1800a0bc6  mov     [r14], cx
0x1800a0bca  mov     rcx, rbx; hWnd
0x1800a0bcd  call    ?SetCommonStateFlags@@YAXPEAUHWND__@@0PEAG@Z; SetCommonStateFlags(HWND__ *,HWND__ *,ushort *)
0x1800a0bd2  mov     rcx, rdi; HWND
0x1800a0bd5  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800a0bda  mov     rcx, rax
0x1800a0bdd  test    rax, rax
0x1800a0be0  jz      loc_1800603F1
0x1800a0be6  mov     rax, [rax+80h]
0x1800a0bed  test    rax, rax
0x1800a0bf0  jz      short loc_1800A0BF9
0x1800a0bf2  sub     rax, [rcx+8]
0x1800a0bf6  add     rax, rcx
0x1800a0bf9  test    byte ptr [rcx+12h], 8
0x1800a0bfd  movzx   edx, word ptr [rax]
0x1800a0c00  mov     rax, cs:gpsi
0x1800a0c07  jnz     short loc_1800A0C12
0x1800a0c09  cmp     dx, [rax+380h]
0x1800a0c10  jmp     short loc_1800A0C19
0x1800a0c12  cmp     dx, [rax+37Eh]
0x1800a0c19  jnz     loc_1800603F1
0x1800a0c1f  or      word ptr [r14], 4
0x1800a0c24  jmp     loc_1800603F1
0x1800a0c29  xor     r9d, r9d; lParam
0x1800a0c2c  mov     r8, rbx; wParam
0x1800a0c2f  mov     edx, 3E1h; Msg
0x1800a0c34  mov     rcx, rdi; hWnd
0x1800a0c37  call    PostMessageW
0x1800a0c3c  nop
0x1800a0c3d  jmp     loc_1800603F1
```
