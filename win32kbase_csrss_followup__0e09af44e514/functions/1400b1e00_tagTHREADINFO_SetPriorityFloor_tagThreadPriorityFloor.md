# tagTHREADINFO::SetPriorityFloor(tagThreadPriorityFloor)

- ea: `0x1400b1e00`
- end: `0x1400b2177`
- name: `?SetPriorityFloor@tagTHREADINFO@@QEAAXW4tagThreadPriorityFloor@@@Z`
- size: `887`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400b1e00`
- `0x1400b2180`
- `0x1400b22cc`
- `0x1400b23a8`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400b1e7a`
- `ntoskrnl!KeBugCheckEx` at `0x1400b1e7a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b1e48`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b1e48`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b1e33`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b1e33`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b210a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b210a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b20fe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b20fe`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400b2030`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400b2030`
- `ntoskrnl!PsGetThreadId` at `0x1400b1edf`
- `ntoskrnl!PsGetThreadId` at `0x1400b1fbd`
- `ntoskrnl!PsGetThreadId` at `0x1400b209d`
- `ntoskrnl!PsGetThreadId` at `0x1400b1edf`
- `ntoskrnl!PsGetThreadId` at `0x1400b1fbd`
- `ntoskrnl!PsGetThreadId` at `0x1400b209d`
- `WIN32K!W32GetUserSessionState` at `0x1400b1ef8`
- `WIN32K!W32GetUserSessionState` at `0x1400b1fcc`
- `WIN32K!W32GetUserSessionState` at `0x1400b20ac`
- `WIN32K!W32GetUserSessionState` at `0x1400b1ef8`
- `WIN32K!W32GetUserSessionState` at `0x1400b1fcc`
- `WIN32K!W32GetUserSessionState` at `0x1400b20ac`

## pseudocode

```c
void __fastcall tagTHREADINFO::SetPriorityFloor(_QWORD *a1, unsigned int a2)
{
  char v2; // r15
  __int64 v4; // rsi
  __int64 v5; // r13
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r12
  int v9; // esi
  bool v10; // bp
  __int64 UserSessionState; // rax
  int v12; // edx
  int v13; // r8d
  bool v14; // si
  char ThreadId; // bl
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // edx
  int v19; // r8d
  _WORD *v20; // rax
  bool v21; // r13
  __int16 v22; // di
  int v23; // esi
  char v24; // bp
  char v25; // bl
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // r8d
  int v29; // edx
  int BugCheckParameter4; // [rsp+20h] [rbp-88h]
  int v31; // [rsp+28h] [rbp-80h]
  int v32; // [rsp+38h] [rbp-70h]
  bool v33; // [rsp+B8h] [rbp+10h]
  bool v34; // [rsp+B8h] [rbp+10h]

  v2 = 1;
  if ( a2 > 1
    || (_mm_lfence(),
        v4 = a2,
        v5 = LOBYTE(asc_140255710[4 * a2]),
        KeEnterCriticalRegion(),
        ExAcquirePushLockExclusiveEx(a1 + 216, 0),
        v8 = (unsigned int)v5,
        *((_BYTE *)a1 + v5 + 1744) == 0xFF)
    || (v9 = *(_DWORD *)&asc_140255710[4 * v4 + 2], (v9 & *((_DWORD *)a1 + 435)) == v9) )
  {
    KeBugCheckEx(0x164u, 0x41u, 0, 0, 0);
  }
  v10 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v33 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId((PETHREAD)*a1);
    UserSessionState = W32GetUserSessionState(a1[57]);
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v33;
    WPP_RECORDER_AND_TRACE_SF_DDdd(*((_QWORD *)WPP_GLOBAL_Control + 3), v12, v13, *(_QWORD *)(UserSessionState + 69136));
  }
  *((_DWORD *)a1 + 435) |= v9;
  if ( ++*((_BYTE *)a1 + v5 + 1744) == 1 )
  {
    if ( *((unsigned __int16 *)a1 + 868) >= 1 << v5 )
    {
      v20 = a1 + 217;
    }
    else
    {
      v14 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
        v17 = W32GetUserSessionState(v16);
        LOBYTE(v18) = v14;
        LOBYTE(v19) = v34;
        WPP_RECORDER_AND_TRACE_SF_dD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v18,
          v19,
          *(_QWORD *)(v17 + 69136),
          4,
          13,
          16,
          (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
          v5,
          ThreadId);
      }
      PsAdjustWin32kPriorityFloor(*a1, (unsigned int)v5, v6, v7);
      v20 = a1 + 217;
    }
    *((_WORD *)a1 + 868) = *v20 | (1 << v5);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v2 = 0;
  }
  v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = *((_WORD *)a1 + 868);
    v23 = *((_DWORD *)a1 + 435);
    v24 = *((_BYTE *)a1 + v8 + 1744);
    v25 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
    v27 = W32GetUserSessionState(v26);
    LOBYTE(v28) = v21;
    LOBYTE(v29) = v2;
    WPP_RECORDER_AND_TRACE_SF_DdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v29,
      v28,
      *(_QWORD *)(v27 + 69136),
      BugCheckParameter4,
      v31,
      17,
      v32,
      v25,
      v8,
      v24,
      v23,
      v22);
  }
  ExReleasePushLockExclusiveEx(a1 + 216, 0, v6, v7);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400b1e00  mov     [rsp+arg_0], rbx
0x1400b1e05  push    rbp
0x1400b1e06  push    rsi
0x1400b1e07  push    rdi
0x1400b1e08  push    r12
0x1400b1e0a  push    r13
0x1400b1e0c  push    r14
0x1400b1e0e  push    r15
0x1400b1e10  sub     rsp, 70h
0x1400b1e14  mov     r15d, 1
0x1400b1e1a  mov     r14, rcx
0x1400b1e1d  cmp     edx, r15d
0x1400b1e20  ja      short loc_1400B1E62
0x1400b1e22  lfence
0x1400b1e25  mov     esi, edx
0x1400b1e27  lea     rdi, asc_140255710; "\r"
0x1400b1e2e  movzx   r13d, byte ptr [rdi+rsi*8]
0x1400b1e33  call    cs:__imp_KeEnterCriticalRegion
0x1400b1e3a  nop     dword ptr [rax+rax+00h]
0x1400b1e3f  xor     edx, edx
0x1400b1e41  lea     rcx, [r14+6C0h]
0x1400b1e48  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400b1e4f  nop     dword ptr [rax+rax+00h]
0x1400b1e54  cmp     byte ptr [r13+r14+6D0h], 0FFh
0x1400b1e5d  mov     r12d, r13d
0x1400b1e60  jnz     short loc_1400B1E87
0x1400b1e62  xor     r9d, r9d; BugCheckParameter3
0x1400b1e65  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400b1e6e  xor     r8d, r8d; BugCheckParameter2
0x1400b1e71  mov     ecx, 164h; BugCheckCode
0x1400b1e76  lea     edx, [r9+41h]; BugCheckParameter1
0x1400b1e7a  call    cs:__imp_KeBugCheckEx
0x1400b1e87  mov     esi, [rdi+rsi*8+4]
0x1400b1e8b  mov     eax, [r14+6CCh]
0x1400b1e92  and     eax, esi
0x1400b1e94  cmp     eax, esi
0x1400b1e96  jz      short loc_1400B1E62
0x1400b1e98  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1e9f  lea     rbx, WPP_GLOBAL_Control
0x1400b1ea6  cmp     rcx, rbx
0x1400b1ea9  jz      short loc_1400B1EB8
0x1400b1eab  test    dword ptr [rcx+2Ch], 1000h
0x1400b1eb2  jnz     loc_1400B2144
0x1400b1eb8  xor     bpl, bpl
0x1400b1ebb  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400b1ec2  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400b1ec9  setnz   al
0x1400b1ecc  mov     [rsp+0A8h+arg_8], al
0x1400b1ed3  test    bpl, bpl
0x1400b1ed6  jz      loc_1400B212F
0x1400b1edc  mov     rcx, [r14]; Thread
0x1400b1edf  call    cs:__imp_PsGetThreadId
0x1400b1ee6  nop     dword ptr [rax+rax+00h]
0x1400b1eeb  mov     rcx, [r14+1C8h]
0x1400b1ef2  mov     rdi, rax
0x1400b1ef5  mov     ebx, [rcx+38h]
0x1400b1ef8  call    cs:__imp_W32GetUserSessionState
0x1400b1eff  nop     dword ptr [rax+rax+00h]
0x1400b1f04  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1f0b  mov     dl, bpl
0x1400b1f0e  mov     r8b, [rsp+0A8h+arg_8]
0x1400b1f16  mov     [rsp+0A8h+var_50], r13d
0x1400b1f1b  mov     r9, [rax+10E10h]
0x1400b1f22  mov     rcx, [rcx+18h]
0x1400b1f26  mov     [rsp+0A8h+var_58], esi
0x1400b1f2a  mov     [rsp+0A8h+var_60], edi
0x1400b1f2e  mov     [rsp+0A8h+var_68], ebx
0x1400b1f32  mov     [rsp+0A8h+var_78], 0Fh
0x1400b1f39  call    WPP_RECORDER_AND_TRACE_SF_DDdd
0x1400b1f3e  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400b1f45  lea     rbx, WPP_GLOBAL_Control
0x1400b1f4c  or      [r14+6CCh], esi
0x1400b1f53  add     [r13+r14+6D0h], r15b
0x1400b1f5b  cmp     [r13+r14+6D0h], r15b
0x1400b1f63  jnz     loc_1400B204A
0x1400b1f69  mov     cl, r13b
0x1400b1f6c  lea     rbp, [r14+6C8h]
0x1400b1f73  movzx   eax, word ptr [rbp+0]
0x1400b1f77  mov     edi, r15d
0x1400b1f7a  shl     edi, cl
0x1400b1f7c  cmp     eax, edi
0x1400b1f7e  jge     loc_1400B213C
0x1400b1f84  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1f8b  cmp     rcx, rbx
0x1400b1f8e  jz      short loc_1400B1F9D
0x1400b1f90  test    dword ptr [rcx+2Ch], 1000h
0x1400b1f97  jnz     loc_1400B2156
0x1400b1f9d  xor     sil, sil
0x1400b1fa0  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400b1fa7  setnz   al
0x1400b1faa  mov     [rsp+0A8h+arg_8], al
0x1400b1fb1  test    sil, sil
0x1400b1fb4  jnz     short loc_1400B1FBA
0x1400b1fb6  test    al, al
0x1400b1fb8  jz      short loc_1400B202A
0x1400b1fba  mov     rcx, [r14]; Thread
0x1400b1fbd  call    cs:__imp_PsGetThreadId
0x1400b1fc4  nop     dword ptr [rax+rax+00h]
0x1400b1fc9  mov     rbx, rax
0x1400b1fcc  call    cs:__imp_W32GetUserSessionState
0x1400b1fd3  nop     dword ptr [rax+rax+00h]
0x1400b1fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1fdf  mov     dl, sil
0x1400b1fe2  mov     r8b, [rsp+0A8h+arg_8]
0x1400b1fea  mov     [rsp+0A8h+var_60], ebx
0x1400b1fee  mov     r9, [rax+10E10h]
0x1400b1ff5  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400b1ffc  mov     rcx, [rcx+18h]
0x1400b2000  mov     [rsp+0A8h+var_68], r13d
0x1400b2005  mov     [rsp+0A8h+var_70], rax
0x1400b200a  mov     [rsp+0A8h+var_78], 10h
0x1400b2011  mov     [rsp+0A8h+var_80], 0Dh
0x1400b2019  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400b201e  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1400b2023  lea     rbx, WPP_GLOBAL_Control
0x1400b202a  mov     rcx, [r14]
0x1400b202d  mov     edx, r13d
0x1400b2030  call    cs:__imp_PsAdjustWin32kPriorityFloor
0x1400b2037  nop     dword ptr [rax+rax+00h]
0x1400b203c  lea     rax, [r14+6C8h]
0x1400b2043  or      di, [rax]
0x1400b2046  mov     [rbp+0], di
0x1400b204a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2051  cmp     rcx, rbx
0x1400b2054  jz      short loc_1400B2063
0x1400b2056  test    dword ptr [rcx+2Ch], 1000h
0x1400b205d  jnz     loc_1400B2168
0x1400b2063  xor     r15b, r15b
0x1400b2066  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b206d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b2074  setnz   r13b
0x1400b2078  test    r15b, r15b
0x1400b207b  jnz     short loc_1400B2082
0x1400b207d  test    r13b, r13b
0x1400b2080  jz      short loc_1400B20F5
0x1400b2082  mov     rcx, [r14]; Thread
0x1400b2085  movzx   edi, word ptr [r14+6C8h]
0x1400b208d  mov     esi, [r14+6CCh]
0x1400b2094  movzx   ebp, byte ptr [r12+r14+6D0h]
0x1400b209d  call    cs:__imp_PsGetThreadId
0x1400b20a4  nop     dword ptr [rax+rax+00h]
0x1400b20a9  mov     rbx, rax
0x1400b20ac  call    cs:__imp_W32GetUserSessionState
0x1400b20b3  nop     dword ptr [rax+rax+00h]
0x1400b20b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b20bf  mov     r8b, r13b
0x1400b20c2  mov     [rsp+0A8h+var_48], edi
0x1400b20c6  mov     dl, r15b
0x1400b20c9  mov     [rsp+0A8h+var_50], esi
0x1400b20cd  mov     r9, [rax+10E10h]
0x1400b20d4  mov     rcx, [rcx+18h]
0x1400b20d8  mov     [rsp+0A8h+var_58], ebp
0x1400b20dc  movzx   r10d, r12b
0x1400b20e0  mov     [rsp+0A8h+var_60], r10d
0x1400b20e5  mov     [rsp+0A8h+var_68], ebx
0x1400b20e9  mov     [rsp+0A8h+var_78], 11h
0x1400b20f0  call    WPP_RECORDER_AND_TRACE_SF_DdddD
0x1400b20f5  xor     edx, edx
0x1400b20f7  lea     rcx, [r14+6C0h]
0x1400b20fe  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400b2105  nop     dword ptr [rax+rax+00h]
0x1400b210a  call    cs:__imp_KeLeaveCriticalRegion
0x1400b2111  nop     dword ptr [rax+rax+00h]
0x1400b2116  mov     rbx, [rsp+0A8h+arg_0]
0x1400b211e  add     rsp, 70h
0x1400b2122  pop     r15
0x1400b2124  pop     r14
0x1400b2126  pop     r13
0x1400b2128  pop     r12
0x1400b212a  pop     rdi
0x1400b212b  pop     rsi
0x1400b212c  pop     rbp
0x1400b212d  retn
0x1400b212f  test    al, al
0x1400b2131  jz      loc_1400B1F4C
0x1400b2137  jmp     loc_1400B1EDC
0x1400b213c  mov     rax, rbp
0x1400b213f  jmp     loc_1400B2043
0x1400b2144  cmp     byte ptr [rcx+29h], 4
0x1400b2148  jb      loc_1400B1EB8
0x1400b214e  mov     bpl, r15b
0x1400b2151  jmp     loc_1400B1EBB
0x1400b2156  cmp     byte ptr [rcx+29h], 4
0x1400b215a  jb      loc_1400B1F9D
0x1400b2160  mov     sil, r15b
0x1400b2163  jmp     loc_1400B1FA0
0x1400b2168  cmp     byte ptr [rcx+29h], 4
0x1400b216c  jnb     loc_1400B2066
0x1400b2172  jmp     loc_1400B2063
```
