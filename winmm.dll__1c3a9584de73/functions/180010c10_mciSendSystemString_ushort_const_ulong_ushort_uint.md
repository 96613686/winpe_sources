# mciSendSystemString(ushort const *,ulong,ushort *,uint)

- ea: `0x180010c10`
- end: `0x180010de2`
- name: `?mciSendSystemString@@YAKPEBGKPEAGI@Z`
- size: `466`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fa8c`
- `0x18000fb24`
- `0x1800102a8`
- `0x180010504`

## callees

- `0x180007020`
- `0x18000a02c`
- `0x18000b6d4`
- `0x180010c10`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d95`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180010cab`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180010d0a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180010cab`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180010d0a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageA` at `0x180010d45`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageA` at `0x180010d45`

## pseudocode

```c
__int64 __fastcall mciSendSystemString(const unsigned __int16 *a1, int a2, unsigned __int16 *a3, int a4)
{
  DWORD CurrentDirectoryW; // eax
  DWORD v10; // ebx
  __int64 v11; // rax
  _DWORD *v12; // rdi
  __int64 v13; // rsi
  DWORD CurrentThreadId; // eax
  HWND v15; // rcx
  unsigned int v16; // ebx

  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids, a1);
  }
  if ( (unsigned int)CreatehwndNotify() )
  {
    CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
    if ( CurrentDirectoryW )
    {
      v10 = CurrentDirectoryW + 1;
      v11 = winmmAlloc(2 * (CurrentDirectoryW + 1) + 48);
      v12 = (_DWORD *)v11;
      if ( v11 )
      {
        v13 = v11 + 48;
        if ( GetCurrentDirectoryW(v10, (LPWSTR)(v11 + 48)) )
        {
          *(_QWORD *)v12 = a1;
          v12[2] = a2;
          *((_QWORD *)v12 + 2) = a3;
          v12[6] = a4;
          CurrentThreadId = GetCurrentThreadId();
          v15 = hwndNotify;
          *((_QWORD *)v12 + 4) = CurrentThreadId;
          *((_QWORD *)v12 + 5) = v13;
          v16 = SendMessageA(v15, 0x3CAu, 0, (LPARAM)v12);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
          }
          v16 = 307;
        }
        HeapFree(hHeap, 0, v12);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
        }
        return 264;
      }
      return v16;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
      }
      return 307;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
    }
    return 277;
  }
}

```

## disassembly

```asm
0x180010c10  push    rbx
0x180010c12  push    rbp
0x180010c13  push    rsi
0x180010c14  push    rdi
0x180010c15  push    r12
0x180010c17  push    r13
0x180010c19  push    r14
0x180010c1b  push    r15
0x180010c1d  sub     rsp, 28h
0x180010c21  mov     r14d, r9d
0x180010c24  mov     r15, r8
0x180010c27  mov     r12d, edx
0x180010c2a  mov     rbp, rcx
0x180010c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c34  lea     rsi, WPP_GLOBAL_Control
0x180010c3b  lea     rbx, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180010c42  mov     r13d, 400000h
0x180010c48  cmp     rcx, rsi
0x180010c4b  jz      short loc_180010C6D
0x180010c4d  test    [rcx+1Ch], r13d
0x180010c51  jz      short loc_180010C6D
0x180010c53  cmp     byte ptr [rcx+19h], 5
0x180010c57  jb      short loc_180010C6D
0x180010c59  mov     rcx, [rcx+10h]
0x180010c5d  mov     edx, 29h ; ')'
0x180010c62  mov     r9, rbp
0x180010c65  mov     r8, rbx
0x180010c68  call    WPP_SF_S
0x180010c6d  call    CreatehwndNotify
0x180010c72  test    eax, eax
0x180010c74  jnz     short loc_180010CA7
0x180010c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c7d  cmp     rcx, rsi
0x180010c80  jz      short loc_180010C9D
0x180010c82  test    [rcx+1Ch], r13d
0x180010c86  jz      short loc_180010C9D
0x180010c88  cmp     byte ptr [rcx+19h], 1
0x180010c8c  jb      short loc_180010C9D
0x180010c8e  mov     rcx, [rcx+10h]
0x180010c92  lea     edx, [rax+2Ah]
0x180010c95  mov     r8, rbx
0x180010c98  call    WPP_SF_
0x180010c9d  mov     eax, 115h
0x180010ca2  jmp     loc_180010DD1
0x180010ca7  xor     edx, edx; lpBuffer
0x180010ca9  xor     ecx, ecx; nBufferLength
0x180010cab  call    cs:__imp_GetCurrentDirectoryW
0x180010cb1  test    eax, eax
0x180010cb3  jnz     short loc_180010CE6
0x180010cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cbc  cmp     rcx, rsi
0x180010cbf  jz      short loc_180010CDC
0x180010cc1  test    [rcx+1Ch], r13d
0x180010cc5  jz      short loc_180010CDC
0x180010cc7  cmp     byte ptr [rcx+19h], 1
0x180010ccb  jb      short loc_180010CDC
0x180010ccd  mov     rcx, [rcx+10h]
0x180010cd1  lea     edx, [rax+2Bh]
0x180010cd4  mov     r8, rbx
0x180010cd7  call    WPP_SF_
0x180010cdc  mov     eax, 133h
0x180010ce1  jmp     loc_180010DD1
0x180010ce6  lea     ebx, [rax+1]
0x180010ce9  lea     ecx, ds:30h[rbx*2]; Size
0x180010cf0  call    winmmAlloc
0x180010cf5  mov     rdi, rax
0x180010cf8  test    rax, rax
0x180010cfb  jz      loc_180010D9D
0x180010d01  lea     rsi, [rax+30h]
0x180010d05  mov     ecx, ebx; nBufferLength
0x180010d07  mov     rdx, rsi; lpBuffer
0x180010d0a  call    cs:__imp_GetCurrentDirectoryW
0x180010d10  test    eax, eax
0x180010d12  jz      short loc_180010D50
0x180010d14  mov     [rdi], rbp
0x180010d17  mov     [rdi+8], r12d
0x180010d1b  mov     [rdi+10h], r15
0x180010d1f  mov     [rdi+18h], r14d
0x180010d23  call    cs:__imp_GetCurrentThreadId
0x180010d29  mov     rcx, cs:hwndNotify; hWnd
0x180010d30  mov     r9, rdi; lParam
0x180010d33  mov     eax, eax
0x180010d35  xor     r8d, r8d; wParam
0x180010d38  mov     edx, 3CAh; Msg
0x180010d3d  mov     [rdi+20h], rax
0x180010d41  mov     [rdi+28h], rsi
0x180010d45  call    cs:__imp_SendMessageA
0x180010d4b  mov     rbx, rax
0x180010d4e  jmp     short loc_180010D89
0x180010d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d57  lea     rax, WPP_GLOBAL_Control
0x180010d5e  cmp     rcx, rax
0x180010d61  jz      short loc_180010D84
0x180010d63  test    [rcx+1Ch], r13d
0x180010d67  jz      short loc_180010D84
0x180010d69  cmp     byte ptr [rcx+19h], 1
0x180010d6d  jb      short loc_180010D84
0x180010d6f  mov     rcx, [rcx+10h]
0x180010d73  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180010d7a  mov     edx, 2Dh ; '-'
0x180010d7f  call    WPP_SF_
0x180010d84  mov     ebx, 133h
0x180010d89  mov     rcx, cs:hHeap; hHeap
0x180010d90  mov     r8, rdi; lpMem
0x180010d93  xor     edx, edx; dwFlags
0x180010d95  call    cs:__imp_HeapFree
0x180010d9b  jmp     short loc_180010DCF
0x180010d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010da4  cmp     rcx, rsi
0x180010da7  jz      short loc_180010DCA
0x180010da9  test    [rcx+1Ch], r13d
0x180010dad  jz      short loc_180010DCA
0x180010daf  cmp     byte ptr [rcx+19h], 1
0x180010db3  jb      short loc_180010DCA
0x180010db5  mov     rcx, [rcx+10h]
0x180010db9  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180010dc0  mov     edx, 2Eh ; '.'
0x180010dc5  call    WPP_SF_
0x180010dca  mov     ebx, 108h
0x180010dcf  mov     eax, ebx
0x180010dd1  add     rsp, 28h
0x180010dd5  pop     r15
0x180010dd7  pop     r14
0x180010dd9  pop     r13
0x180010ddb  pop     r12
0x180010ddd  pop     rdi
0x180010dde  pop     rsi
0x180010ddf  pop     rbp
0x180010de0  pop     rbx
0x180010de1  retn
```
