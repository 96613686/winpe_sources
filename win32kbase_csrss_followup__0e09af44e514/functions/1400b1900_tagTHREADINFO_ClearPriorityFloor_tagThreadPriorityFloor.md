# tagTHREADINFO::ClearPriorityFloor(tagThreadPriorityFloor)

- ea: `0x1400b1900`
- end: `0x1400b1d3a`
- name: `?ClearPriorityFloor@tagTHREADINFO@@QEAAXW4tagThreadPriorityFloor@@@Z`
- size: `1082`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400b1900`
- `0x1400b1d40`
- `0x1400b2180`
- `0x1400b22cc`
- `0x1400b23a8`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400b1980`
- `ntoskrnl!KeBugCheckEx` at `0x1400b1980`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b194f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b194f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b193a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b193a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b1c2e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b1c2e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b1c22`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b1c22`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400b1b53`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400b1b53`
- `ntoskrnl!PsGetThreadId` at `0x1400b19e3`
- `ntoskrnl!PsGetThreadId` at `0x1400b1aeb`
- `ntoskrnl!PsGetThreadId` at `0x1400b1bbc`
- `ntoskrnl!PsGetThreadId` at `0x1400b1cab`
- `ntoskrnl!PsGetThreadId` at `0x1400b19e3`
- `ntoskrnl!PsGetThreadId` at `0x1400b1aeb`
- `ntoskrnl!PsGetThreadId` at `0x1400b1bbc`
- `ntoskrnl!PsGetThreadId` at `0x1400b1cab`
- `WIN32K!W32GetUserSessionState` at `0x1400b19fc`
- `WIN32K!W32GetUserSessionState` at `0x1400b1afa`
- `WIN32K!W32GetUserSessionState` at `0x1400b1bcb`
- `WIN32K!W32GetUserSessionState` at `0x1400b1cba`
- `WIN32K!W32GetUserSessionState` at `0x1400b19fc`
- `WIN32K!W32GetUserSessionState` at `0x1400b1afa`
- `WIN32K!W32GetUserSessionState` at `0x1400b1bcb`
- `WIN32K!W32GetUserSessionState` at `0x1400b1cba`

## pseudocode

```c
void __fastcall tagTHREADINFO::ClearPriorityFloor(_QWORD *a1, unsigned int a2)
{
  char v2; // r15
  __int64 v4; // rsi
  __int64 v5; // rbx
  int v6; // esi
  CTouchProcessor **v7; // r9
  __int64 v8; // r8
  bool v9; // r12
  bool v10; // r13
  __int64 UserSessionState; // rax
  int v12; // r8d
  int v13; // edx
  bool v14; // zf
  int v15; // edx
  unsigned __int16 v16; // ax
  unsigned int v17; // ebp
  bool v18; // di
  bool v19; // si
  char ThreadId; // bl
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  int v24; // edx
  __int64 v25; // rdx
  bool v26; // r12
  __int16 v27; // si
  int v28; // ebp
  char v29; // di
  char v30; // bl
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  bool v35; // di
  bool v36; // si
  char v37; // bl
  __int64 v38; // rcx
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  int BugCheckParameter4; // [rsp+20h] [rbp-88h]
  int v43; // [rsp+28h] [rbp-80h]
  int v44; // [rsp+38h] [rbp-70h]
  char v45; // [rsp+B8h] [rbp+10h]

  v2 = 1;
  if ( a2 > 1 )
    goto LABEL_3;
  _mm_lfence();
  v4 = a2;
  v5 = LOBYTE(asc_140255710[4 * a2]);
  v45 = asc_140255710[4 * a2];
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 216, 0);
  if ( !*((_BYTE *)a1 + v5 + 1744) )
    goto LABEL_3;
  v6 = *(_DWORD *)&asc_140255710[4 * v4 + 2];
  if ( (*((_DWORD *)a1 + 435) & v6) != v6 )
    goto LABEL_3;
  v7 = &WPP_GLOBAL_Control;
  v8 = 4096;
  v9 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v10 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId((PETHREAD)*a1);
    UserSessionState = W32GetUserSessionState(a1[57]);
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v9;
    WPP_RECORDER_AND_TRACE_SF_DDdd(*((_QWORD *)WPP_GLOBAL_Control + 3), v13, v12, *(_QWORD *)(UserSessionState + 69136));
    v8 = 4096;
    v7 = &WPP_GLOBAL_Control;
  }
  *((_DWORD *)a1 + 435) &= ~v6;
  v14 = (*((_BYTE *)a1 + (unsigned int)v5 + 1744))-- == 1;
  if ( v14 )
  {
    v15 = 1 << v5;
    if ( ((1 << v5) & (unsigned __int16)a1[217]) == 1 << v5 )
    {
      v16 = a1[217] & ~(_WORD)v15;
      *((_WORD *)a1 + 868) = v16;
      if ( v16 < v15 )
      {
        v14 = !_BitScanReverse(&v17, v16);
        if ( v14 )
        {
          v18 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
            v22 = W32GetUserSessionState(v21);
            LOBYTE(v23) = v19;
            LOBYTE(v24) = v18;
            WPP_RECORDER_AND_TRACE_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v24,
              v23,
              *(_QWORD *)(v22 + 69136),
              4,
              13,
              20,
              (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
              ThreadId);
            LOBYTE(v5) = v45;
          }
          v25 = 0;
        }
        else
        {
          v35 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v36 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v35 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v37 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
            v39 = W32GetUserSessionState(v38);
            LOBYTE(v40) = v36;
            LOBYTE(v41) = v35;
            WPP_RECORDER_AND_TRACE_SF_dD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v41,
              v40,
              *(_QWORD *)(v39 + 69136),
              4,
              13,
              19,
              (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
              v17,
              v37);
            LOBYTE(v5) = v45;
          }
          v25 = v17;
        }
        PsAdjustWin32kPriorityFloor(*a1, v25, v8, v7);
      }
      goto LABEL_22;
    }
LABEL_3:
    KeBugCheckEx(0x164u, 0x41u, 0, 0, 0);
  }
LABEL_22:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v2 = 0;
  }
  v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v27 = *((_WORD *)a1 + 868);
    v28 = *((_DWORD *)a1 + 435);
    v29 = *((_BYTE *)a1 + (unsigned __int8)v5 + 1744);
    v30 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
    v32 = W32GetUserSessionState(v31);
    LOBYTE(v33) = v26;
    LOBYTE(v34) = v2;
    WPP_RECORDER_AND_TRACE_SF_DdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v34,
      v33,
      *(_QWORD *)(v32 + 69136),
      BugCheckParameter4,
      v43,
      21,
      v44,
      v30,
      v45,
      v29,
      v28,
      v27);
  }
  ExReleasePushLockExclusiveEx(a1 + 216, 0, v8, v7);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400b1900  mov     [rsp+arg_0], rbx
0x1400b1905  push    rbp
0x1400b1906  push    rsi
0x1400b1907  push    rdi
0x1400b1908  push    r12
0x1400b190a  push    r13
0x1400b190c  push    r14
0x1400b190e  push    r15
0x1400b1910  sub     rsp, 70h
0x1400b1914  mov     r15d, 1
0x1400b191a  mov     r14, rcx
0x1400b191d  cmp     edx, r15d
0x1400b1920  ja      short loc_1400B1968
0x1400b1922  lfence
0x1400b1925  mov     esi, edx
0x1400b1927  lea     r12, asc_140255710; "\r"
0x1400b192e  movzx   ebx, byte ptr [r12+rsi*8]
0x1400b1933  mov     [rsp+0A8h+arg_8], bl
0x1400b193a  call    cs:__imp_KeEnterCriticalRegion
0x1400b1941  nop     dword ptr [rax+rax+00h]
0x1400b1946  xor     edx, edx
0x1400b1948  lea     rcx, [r14+6C0h]
0x1400b194f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400b1956  nop     dword ptr [rax+rax+00h]
0x1400b195b  cmp     byte ptr [r14+rbx+6D0h], 0
0x1400b1964  mov     ebp, ebx
0x1400b1966  jnz     short loc_1400B198D
0x1400b1968  xor     r9d, r9d; BugCheckParameter3
0x1400b196b  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400b1974  xor     r8d, r8d; BugCheckParameter2
0x1400b1977  mov     ecx, 164h; BugCheckCode
0x1400b197c  lea     edx, [r9+41h]; BugCheckParameter1
0x1400b1980  call    cs:__imp_KeBugCheckEx
0x1400b198d  mov     esi, [r12+rsi*8+4]
0x1400b1992  mov     eax, esi
0x1400b1994  and     eax, [r14+6CCh]
0x1400b199b  cmp     eax, esi
0x1400b199d  jnz     short loc_1400B1968
0x1400b199f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b19a6  lea     r9, WPP_GLOBAL_Control
0x1400b19ad  mov     r8d, 1000h
0x1400b19b3  cmp     rcx, r9
0x1400b19b6  jz      short loc_1400B19C2
0x1400b19b8  test    [rcx+2Ch], r8d
0x1400b19bc  jnz     loc_1400B1C61
0x1400b19c2  xor     r12b, r12b
0x1400b19c5  lea     r10, WPP_RECORDER_INITIALIZED
0x1400b19cc  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400b19d3  setnz   r13b
0x1400b19d7  test    r12b, r12b
0x1400b19da  jz      loc_1400B1C53
0x1400b19e0  mov     rcx, [r14]; Thread
0x1400b19e3  call    cs:__imp_PsGetThreadId
0x1400b19ea  nop     dword ptr [rax+rax+00h]
0x1400b19ef  mov     rcx, [r14+1C8h]
0x1400b19f6  mov     rdi, rax
0x1400b19f9  mov     ebx, [rcx+38h]
0x1400b19fc  call    cs:__imp_W32GetUserSessionState
0x1400b1a03  nop     dword ptr [rax+rax+00h]
0x1400b1a08  movzx   ecx, bpl
0x1400b1a0c  mov     r8b, r13b
0x1400b1a0f  mov     [rsp+0A8h+var_50], ecx
0x1400b1a13  mov     dl, r12b
0x1400b1a16  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1a1d  mov     r9, [rax+10E10h]
0x1400b1a24  mov     [rsp+0A8h+var_58], esi
0x1400b1a28  mov     [rsp+0A8h+var_60], edi
0x1400b1a2c  mov     rcx, [rcx+18h]
0x1400b1a30  mov     [rsp+0A8h+var_68], ebx
0x1400b1a34  mov     [rsp+0A8h+var_78], 12h
0x1400b1a3b  call    WPP_RECORDER_AND_TRACE_SF_DDdd
0x1400b1a40  mov     r8d, 1000h
0x1400b1a46  lea     r9, WPP_GLOBAL_Control
0x1400b1a4d  lea     r10, WPP_RECORDER_INITIALIZED
0x1400b1a54  mov     bl, bpl
0x1400b1a57  not     esi
0x1400b1a59  and     [r14+6CCh], esi
0x1400b1a60  add     byte ptr [r14+rbp+6D0h], 0FFh
0x1400b1a69  jnz     loc_1400B1B5F
0x1400b1a6f  mov     cl, bl
0x1400b1a71  mov     edx, r15d
0x1400b1a74  shl     edx, cl
0x1400b1a76  movzx   ecx, word ptr [r14+6C8h]
0x1400b1a7e  mov     eax, ecx
0x1400b1a80  and     eax, edx
0x1400b1a82  cmp     eax, edx
0x1400b1a84  jnz     loc_1400B1968
0x1400b1a8a  movzx   eax, dx
0x1400b1a8d  not     ax
0x1400b1a90  and     ax, cx
0x1400b1a93  movzx   ecx, ax
0x1400b1a96  mov     [r14+6C8h], cx
0x1400b1a9e  cmp     ecx, edx
0x1400b1aa0  jge     loc_1400B1B5F
0x1400b1aa6  bsr     ebp, ecx
0x1400b1aa9  mov     [rsp+0A8h+arg_10], 0
0x1400b1ab4  jnz     loc_1400B1C73
0x1400b1aba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1ac1  cmp     rcx, r9
0x1400b1ac4  jz      short loc_1400B1AD0
0x1400b1ac6  test    [rcx+2Ch], r8d
0x1400b1aca  jnz     loc_1400B1D19
0x1400b1ad0  xor     dil, dil
0x1400b1ad3  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400b1ada  setnz   sil
0x1400b1ade  test    dil, dil
0x1400b1ae1  jnz     short loc_1400B1AE8
0x1400b1ae3  test    sil, sil
0x1400b1ae6  jz      short loc_1400B1B4E
0x1400b1ae8  mov     rcx, [r14]; Thread
0x1400b1aeb  call    cs:__imp_PsGetThreadId
0x1400b1af2  nop     dword ptr [rax+rax+00h]
0x1400b1af7  mov     rbx, rax
0x1400b1afa  call    cs:__imp_W32GetUserSessionState
0x1400b1b01  nop     dword ptr [rax+rax+00h]
0x1400b1b06  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1b0d  mov     r8b, sil
0x1400b1b10  mov     [rsp+0A8h+var_68], ebx
0x1400b1b14  mov     dl, dil
0x1400b1b17  mov     r9, [rax+10E10h]
0x1400b1b1e  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400b1b25  mov     rcx, [rcx+18h]
0x1400b1b29  mov     [rsp+0A8h+var_70], rax
0x1400b1b2e  mov     [rsp+0A8h+var_78], 14h
0x1400b1b35  mov     [rsp+0A8h+var_80], 0Dh
0x1400b1b3d  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400b1b42  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400b1b47  mov     bl, [rsp+0A8h+arg_8]
0x1400b1b4e  xor     edx, edx
0x1400b1b50  mov     rcx, [r14]
0x1400b1b53  call    cs:__imp_PsAdjustWin32kPriorityFloor
0x1400b1b5a  nop     dword ptr [rax+rax+00h]
0x1400b1b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1b66  lea     rax, WPP_GLOBAL_Control
0x1400b1b6d  cmp     rcx, rax
0x1400b1b70  jz      short loc_1400B1B7F
0x1400b1b72  test    dword ptr [rcx+2Ch], 1000h
0x1400b1b79  jnz     loc_1400B1D2B
0x1400b1b7f  xor     r15b, r15b
0x1400b1b82  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b1b89  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b1b90  setnz   r12b
0x1400b1b94  test    r15b, r15b
0x1400b1b97  jnz     short loc_1400B1B9E
0x1400b1b99  test    r12b, r12b
0x1400b1b9c  jz      short loc_1400B1C19
0x1400b1b9e  mov     rcx, [r14]; Thread
0x1400b1ba1  movzx   esi, word ptr [r14+6C8h]
0x1400b1ba9  mov     ebp, [r14+6CCh]
0x1400b1bb0  movzx   eax, bl
0x1400b1bb3  movzx   edi, byte ptr [rax+r14+6D0h]
0x1400b1bbc  call    cs:__imp_PsGetThreadId
0x1400b1bc3  nop     dword ptr [rax+rax+00h]
0x1400b1bc8  mov     rbx, rax
0x1400b1bcb  call    cs:__imp_W32GetUserSessionState
0x1400b1bd2  nop     dword ptr [rax+rax+00h]
0x1400b1bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1bde  mov     r8b, r12b
0x1400b1be1  movzx   r10d, [rsp+0A8h+arg_8]
0x1400b1bea  mov     dl, r15b
0x1400b1bed  mov     [rsp+0A8h+var_48], esi
0x1400b1bf1  mov     r9, [rax+10E10h]
0x1400b1bf8  mov     rcx, [rcx+18h]
0x1400b1bfc  mov     [rsp+0A8h+var_50], ebp
0x1400b1c00  mov     [rsp+0A8h+var_58], edi
0x1400b1c04  mov     [rsp+0A8h+var_60], r10d
0x1400b1c09  mov     [rsp+0A8h+var_68], ebx
0x1400b1c0d  mov     [rsp+0A8h+var_78], 15h
0x1400b1c14  call    WPP_RECORDER_AND_TRACE_SF_DdddD
0x1400b1c19  xor     edx, edx
0x1400b1c1b  lea     rcx, [r14+6C0h]
0x1400b1c22  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400b1c29  nop     dword ptr [rax+rax+00h]
0x1400b1c2e  call    cs:__imp_KeLeaveCriticalRegion
0x1400b1c35  nop     dword ptr [rax+rax+00h]
0x1400b1c3a  mov     rbx, [rsp+0A8h+arg_0]
0x1400b1c42  add     rsp, 70h
0x1400b1c46  pop     r15
0x1400b1c48  pop     r14
0x1400b1c4a  pop     r13
0x1400b1c4c  pop     r12
0x1400b1c4e  pop     rdi
0x1400b1c4f  pop     rsi
0x1400b1c50  pop     rbp
0x1400b1c51  retn
0x1400b1c53  test    r13b, r13b
0x1400b1c56  jnz     loc_1400B19E0
0x1400b1c5c  jmp     loc_1400B1A57
0x1400b1c61  cmp     byte ptr [rcx+29h], 4
0x1400b1c65  jb      loc_1400B19C2
0x1400b1c6b  mov     r12b, r15b
0x1400b1c6e  jmp     loc_1400B19C5
0x1400b1c73  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1c7a  cmp     rcx, r9
0x1400b1c7d  jz      short loc_1400B1C90
0x1400b1c7f  test    [rcx+2Ch], r8d
0x1400b1c83  jz      short loc_1400B1C90
0x1400b1c85  cmp     byte ptr [rcx+29h], 4
0x1400b1c89  jb      short loc_1400B1C90
0x1400b1c8b  mov     dil, r15b
0x1400b1c8e  jmp     short loc_1400B1C93
0x1400b1c90  xor     dil, dil
0x1400b1c93  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400b1c9a  setnz   sil
0x1400b1c9e  test    dil, dil
0x1400b1ca1  jnz     short loc_1400B1CA8
0x1400b1ca3  test    sil, sil
0x1400b1ca6  jz      short loc_1400B1D12
0x1400b1ca8  mov     rcx, [r14]; Thread
0x1400b1cab  call    cs:__imp_PsGetThreadId
0x1400b1cb2  nop     dword ptr [rax+rax+00h]
0x1400b1cb7  mov     rbx, rax
0x1400b1cba  call    cs:__imp_W32GetUserSessionState
0x1400b1cc1  nop     dword ptr [rax+rax+00h]
0x1400b1cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1ccd  mov     r8b, sil
0x1400b1cd0  mov     [rsp+0A8h+var_60], ebx
0x1400b1cd4  mov     dl, dil
0x1400b1cd7  mov     [rsp+0A8h+var_68], ebp
0x1400b1cdb  mov     r9, [rax+10E10h]
0x1400b1ce2  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400b1ce9  mov     rcx, [rcx+18h]
0x1400b1ced  mov     [rsp+0A8h+var_70], rax
0x1400b1cf2  mov     [rsp+0A8h+var_78], 13h
0x1400b1cf9  mov     [rsp+0A8h+var_80], 0Dh
0x1400b1d01  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400b1d06  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1400b1d0b  mov     bl, [rsp+0A8h+arg_8]
0x1400b1d12  mov     edx, ebp
0x1400b1d14  jmp     loc_1400B1B50
0x1400b1d19  cmp     byte ptr [rcx+29h], 4
0x1400b1d1d  jb      loc_1400B1AD0
0x1400b1d23  mov     dil, r15b
0x1400b1d26  jmp     loc_1400B1AD3
0x1400b1d2b  cmp     byte ptr [rcx+29h], 4
0x1400b1d2f  jnb     loc_1400B1B82
0x1400b1d35  jmp     loc_1400B1B7F
```
