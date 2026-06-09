# UnmaximizeChildWindows(HWND__ *)

- ea: `0x18008776c`
- end: `0x1800878d9`
- name: `?UnmaximizeChildWindows@@YAHPEAUHWND__@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18008705c`

## callees

- `0x18000d210`
- `0x18000e280`
- `0x18003c5f0`
- `0x18004d100`
- `0x18008776c`

## import_xrefs

- `win32u!NtUserGetForegroundWindow` at `0x180087870`
- `win32u!NtUserGetForegroundWindow` at `0x180087870`
- `win32u!NtUserShowWindowAsync` at `0x180087838`
- `win32u!NtUserShowWindowAsync` at `0x180087838`
- `win32u!NtUserShowWindow` at `0x180087845`
- `win32u!NtUserShowWindow` at `0x180087845`
- `win32u!NtUserSetWindowPos` at `0x180087898`
- `win32u!NtUserSetWindowPos` at `0x180087898`
- `win32u!NtUserRedrawWindow` at `0x1800878b4`
- `win32u!NtUserRedrawWindow` at `0x1800878b4`
- `win32u!NtUserLockWindowUpdate` at `0x180087817`
- `win32u!NtUserLockWindowUpdate` at `0x1800878a0`
- `win32u!NtUserLockWindowUpdate` at `0x180087817`
- `win32u!NtUserLockWindowUpdate` at `0x1800878a0`
- `ntdll!RtlFreeHeap` at `0x180087861`
- `ntdll!RtlFreeHeap` at `0x180087861`

## pseudocode

```c
__int64 __fastcall UnmaximizeChildWindows(HWND hWnd)
{
  HWND Window; // rax
  unsigned int v3; // r15d
  unsigned int v4; // edi
  HWND CurrentThreadDesktopHwnd; // rax
  PVOID v6; // r13
  HWND v7; // rbp
  HWND *v8; // r14
  HWND v9; // rsi
  struct tagWND *v10; // rax
  __int64 ForegroundWindow; // rax
  PVOID P; // [rsp+78h] [rbp+10h] BYREF

  P = 0;
  if ( !GetWindow(hWnd, 5u) )
    return 0;
  Window = GetWindow(hWnd, 5u);
  v3 = BuildHwndList(0, Window, 0, 0, 0, (struct _tagHWNDCACHE **)&P);
  if ( !v3 )
    return 0;
  v4 = 0;
  CurrentThreadDesktopHwnd = GetCurrentThreadDesktopHwnd();
  v6 = P;
  v7 = CurrentThreadDesktopHwnd;
  v8 = (HWND *)((char *)P + 8);
  do
  {
    v9 = *v8;
    if ( *v8 )
    {
      v10 = ValidateHwnd(*v8);
      if ( v10 )
      {
        if ( (*((_BYTE *)v10 + 31) & 0x11) == 0x11 )
        {
          if ( !v4 && hWnd == v7 )
          {
            NtUserLockWindowUpdate(hWnd);
            v4 = 1;
LABEL_11:
            NtUserShowWindowAsync(v9, 4);
            goto LABEL_13;
          }
          v4 = 1;
          if ( hWnd == v7 )
            goto LABEL_11;
          NtUserShowWindow(v9, 1);
        }
      }
    }
LABEL_13:
    ++v8;
    --v3;
  }
  while ( v3 );
  RtlFreeHeap(pUserHeap, 0, v6);
  if ( v4 && hWnd == v7 )
  {
    ForegroundWindow = NtUserGetForegroundWindow();
    if ( ForegroundWindow )
      NtUserSetWindowPos(ForegroundWindow, 0, 0, 0, v3, v3, 16403);
    NtUserLockWindowUpdate(0);
    NtUserRedrawWindow(hWnd, 0, 0, 1157);
  }
  return v4;
}

```

## disassembly

```asm
0x18008776c  mov     [rsp+arg_0], rbx
0x180087771  mov     [rsp+arg_10], rbp
0x180087776  push    rsi
0x180087777  push    rdi
0x180087778  push    r13
0x18008777a  push    r14
0x18008777c  push    r15
0x18008777e  sub     rsp, 40h
0x180087782  mov     edi, 5
0x180087787  mov     [rsp+68h+P], 0
0x180087790  mov     edx, edi; uCmd
0x180087792  mov     rbx, rcx
0x180087795  call    GetWindow
0x18008779a  test    rax, rax
0x18008779d  jz      loc_1800878BE
0x1800877a3  mov     edx, edi; uCmd
0x1800877a5  mov     rcx, rbx; hWnd
0x1800877a8  call    GetWindow
0x1800877ad  mov     rdx, rax; HWND
0x1800877b0  xor     r9d, r9d; int
0x1800877b3  lea     rax, [rsp+68h+P]
0x1800877b8  xor     r8d, r8d; int
0x1800877bb  mov     [rsp+68h+var_40], rax; struct _tagHWNDCACHE **
0x1800877c0  xor     ecx, ecx; HDESK
0x1800877c2  mov     [rsp+68h+var_48], 0; unsigned int
0x1800877ca  call    ?BuildHwndList@@YAKPEAUHDESK__@@PEAUHWND__@@HHKPEAPEAU_tagHWNDCACHE@@@Z; BuildHwndList(HDESK__ *,HWND__ *,int,int,ulong,_tagHWNDCACHE * *)
0x1800877cf  mov     r15d, eax
0x1800877d2  test    eax, eax
0x1800877d4  jz      loc_1800878BE
0x1800877da  xor     edi, edi
0x1800877dc  call    GetCurrentThreadDesktopHwnd
0x1800877e1  mov     r13, [rsp+68h+P]
0x1800877e6  mov     rbp, rax
0x1800877e9  lea     r14, [r13+8]
0x1800877ed  mov     rsi, [r14]
0x1800877f0  test    rsi, rsi
0x1800877f3  jz      short loc_18008784B
0x1800877f5  mov     rcx, rsi; HWND
0x1800877f8  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800877fd  test    rax, rax
0x180087800  jz      short loc_18008784B
0x180087802  mov     al, [rax+1Fh]
0x180087805  and     al, 11h
0x180087807  cmp     al, 11h
0x180087809  jnz     short loc_18008784B
0x18008780b  test    edi, edi
0x18008780d  jnz     short loc_180087824
0x18008780f  cmp     rbx, rbp
0x180087812  jnz     short loc_180087824
0x180087814  mov     rcx, rbx
0x180087817  call    cs:__imp_NtUserLockWindowUpdate
0x18008781d  mov     edi, 1
0x180087822  jmp     short loc_180087830
0x180087824  mov     eax, 1
0x180087829  mov     edi, eax
0x18008782b  cmp     rbx, rbp
0x18008782e  jnz     short loc_180087840
0x180087830  mov     edx, 4
0x180087835  mov     rcx, rsi
0x180087838  call    cs:__imp_NtUserShowWindowAsync
0x18008783e  jmp     short loc_18008784B
0x180087840  mov     edx, eax
0x180087842  mov     rcx, rsi
0x180087845  call    cs:__imp_NtUserShowWindow
0x18008784b  add     r14, 8
0x18008784f  add     r15d, 0FFFFFFFFh
0x180087853  jnz     short loc_1800877ED
0x180087855  mov     rcx, cs:pUserHeap; HeapHandle
0x18008785c  mov     r8, r13; P
0x18008785f  xor     edx, edx; Flags
0x180087861  call    cs:__imp_RtlFreeHeap
0x180087867  test    edi, edi
0x180087869  jz      short loc_1800878BA
0x18008786b  cmp     rbx, rbp
0x18008786e  jnz     short loc_1800878BA
0x180087870  call    cs:__imp_NtUserGetForegroundWindow
0x180087876  test    rax, rax
0x180087879  jz      short loc_18008789E
0x18008787b  mov     [rsp+68h+var_38], 4013h
0x180087883  xor     r9d, r9d
0x180087886  mov     dword ptr [rsp+68h+var_40], r15d
0x18008788b  xor     r8d, r8d
0x18008788e  xor     edx, edx
0x180087890  mov     [rsp+68h+var_48], r15d
0x180087895  mov     rcx, rax
0x180087898  call    cs:__imp_NtUserSetWindowPos
0x18008789e  xor     ecx, ecx
0x1800878a0  call    cs:__imp_NtUserLockWindowUpdate
0x1800878a6  mov     r9d, 485h
0x1800878ac  xor     r8d, r8d
0x1800878af  xor     edx, edx
0x1800878b1  mov     rcx, rbx
0x1800878b4  call    cs:__imp_NtUserRedrawWindow
0x1800878ba  mov     eax, edi
0x1800878bc  jmp     short loc_1800878C0
0x1800878be  xor     eax, eax
0x1800878c0  lea     r11, [rsp+68h+var_28]
0x1800878c5  mov     rbx, [r11+30h]
0x1800878c9  mov     rbp, [r11+40h]
0x1800878cd  mov     rsp, r11
0x1800878d0  pop     r15
0x1800878d2  pop     r14
0x1800878d4  pop     r13
0x1800878d6  pop     rdi
0x1800878d7  pop     rsi
0x1800878d8  retn
```
