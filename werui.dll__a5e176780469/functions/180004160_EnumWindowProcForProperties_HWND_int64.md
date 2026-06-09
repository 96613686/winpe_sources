# EnumWindowProcForProperties(HWND__ *,__int64)

- ea: `0x180004160`
- end: `0x180004258`
- name: `?EnumWindowProcForProperties@@YAHPEAUHWND__@@_J@Z`
- size: `248`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180004160`
- `0x180016c50`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800041a1`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800041a1`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x1800041b5`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x1800041b5`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x1800041e3`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x1800041e3`

## pseudocode

```c
__int64 __fastcall EnumWindowProcForProperties(HWND a1, __int64 a2)
{
  DWORD v4; // eax
  LONG right; // r9d
  LONG bottom; // r11d
  LONG top; // esi
  unsigned int v8; // r8d
  DWORD dwProcessId; // [rsp+20h] [rbp-50h] BYREF
  tagWINDOWINFO pwi; // [rsp+28h] [rbp-48h] BYREF

  dwProcessId = 0;
  memset(&pwi, 0, sizeof(pwi));
  GetWindowThreadProcessId(a1, &dwProcessId);
  pwi.cbSize = 60;
  if ( GetWindowInfo(a1, &pwi) )
  {
    v4 = dwProcessId;
    if ( (pwi.dwStyle & 8) != 0 )
    {
      if ( dwProcessId == *(_DWORD *)a2 )
        *(_DWORD *)(a2 + 16) = 1;
      else
        *(_DWORD *)(a2 + 36) = 1;
    }
    if ( v4 == *(_DWORD *)a2 )
    {
      if ( IsWindowVisible(a1) )
      {
        right = pwi.rcWindow.right;
        bottom = pwi.rcWindow.bottom;
        top = pwi.rcWindow.top;
        v8 = (pwi.rcWindow.bottom - pwi.rcWindow.top) * (pwi.rcWindow.right - pwi.rcWindow.left);
        if ( v8 )
        {
          if ( v8 > (*(_DWORD *)(a2 + 28) - *(_DWORD *)(a2 + 20)) * (*(_DWORD *)(a2 + 32) - *(_DWORD *)(a2 + 24)) )
          {
            *(_DWORD *)(a2 + 20) = pwi.rcWindow.left;
            *(_DWORD *)(a2 + 24) = top;
            *(_DWORD *)(a2 + 28) = right;
            *(_DWORD *)(a2 + 32) = bottom;
            *(_QWORD *)(a2 + 8) = a1;
          }
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004160  mov     [rsp-18h+arg_10], rbx
0x180004165  push    rbp
0x180004166  push    rsi
0x180004167  push    rdi
0x180004168  mov     rbp, rsp
0x18000416b  sub     rsp, 70h
0x18000416f  mov     rax, cs:__security_cookie
0x180004176  xor     rax, rsp
0x180004179  mov     [rbp+var_8], rax
0x18000417d  xorps   xmm0, xmm0
0x180004180  mov     [rbp+dwProcessId], 0
0x180004187  mov     rbx, rdx
0x18000418a  mov     rdi, rcx
0x18000418d  movups  xmmword ptr [rbp+pwi.rcClient.bottom], xmm0
0x180004191  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180004195  movups  xmmword ptr [rbp+pwi.dwWindowStatus], xmm0
0x180004199  movups  xmmword ptr [rbp+pwi.cbSize], xmm0
0x18000419d  movups  xmmword ptr [rbp+pwi.rcWindow.bottom], xmm0
0x1800041a1  call    cs:__imp_GetWindowThreadProcessId
0x1800041a7  lea     rdx, [rbp+pwi]; pwi
0x1800041ab  mov     [rbp+pwi.cbSize], 3Ch ; '<'
0x1800041b2  mov     rcx, rdi; hwnd
0x1800041b5  call    cs:__imp_GetWindowInfo
0x1800041bb  test    eax, eax
0x1800041bd  jz      short loc_180004237
0x1800041bf  test    byte ptr [rbp+pwi.dwStyle], 8
0x1800041c3  mov     eax, [rbp+dwProcessId]
0x1800041c6  jz      short loc_1800041DC
0x1800041c8  cmp     eax, [rbx]
0x1800041ca  jnz     short loc_1800041D5
0x1800041cc  mov     dword ptr [rbx+10h], 1
0x1800041d3  jmp     short loc_1800041DC
0x1800041d5  mov     dword ptr [rbx+24h], 1
0x1800041dc  cmp     eax, [rbx]
0x1800041de  jnz     short loc_180004237
0x1800041e0  mov     rcx, rdi; hWnd
0x1800041e3  call    cs:__imp_IsWindowVisible
0x1800041e9  test    eax, eax
0x1800041eb  jz      short loc_180004237
0x1800041ed  mov     r9d, [rbp+pwi.rcWindow.right]
0x1800041f1  mov     r8d, r9d
0x1800041f4  mov     r11d, [rbp+pwi.rcWindow.bottom]
0x1800041f8  mov     eax, r11d
0x1800041fb  mov     r10d, [rbp+pwi.rcWindow.left]
0x1800041ff  sub     r8d, r10d
0x180004202  mov     esi, [rbp+pwi.rcWindow.top]
0x180004205  sub     eax, esi
0x180004207  imul    r8d, eax
0x18000420b  test    r8d, r8d
0x18000420e  jz      short loc_180004237
0x180004210  mov     edx, [rbx+20h]
0x180004213  sub     edx, [rbx+18h]
0x180004216  mov     ecx, [rbx+1Ch]
0x180004219  sub     ecx, [rbx+14h]
0x18000421c  imul    edx, ecx
0x18000421f  cmp     r8d, edx
0x180004222  jbe     short loc_180004237
0x180004224  mov     [rbx+14h], r10d
0x180004228  mov     [rbx+18h], esi
0x18000422b  mov     [rbx+1Ch], r9d
0x18000422f  mov     [rbx+20h], r11d
0x180004233  mov     [rbx+8], rdi
0x180004237  mov     eax, 1
0x18000423c  mov     rcx, [rbp+var_8]
0x180004240  xor     rcx, rsp; StackCookie
0x180004243  call    __security_check_cookie
0x180004248  mov     rbx, [rsp+70h+arg_10]
0x180004250  add     rsp, 70h
0x180004254  pop     rdi
0x180004255  pop     rsi
0x180004256  pop     rbp
0x180004257  retn
```
