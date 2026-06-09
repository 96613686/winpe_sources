# BoostHardError

- ea: `0x18000b9a8`
- end: `0x18000bbc8`
- name: `BoostHardError`
- size: `544`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005474`
- `0x18000592c`
- `0x180005b70`
- `0x1800070ac`
- `0x180008c10`
- `0x180009688`
- `0x1800109d0`

## callees

- `0x18000b9a8`
- `0x18000da7c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000b9e7`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba64`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba89`
- `ntdll!RtlLeaveCriticalSection` at `0x18000baf1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb89`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b9e7`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba64`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba89`
- `ntdll!RtlLeaveCriticalSection` at `0x18000baf1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb89`
- `ntdll!RtlEnterCriticalSection` at `0x18000b9cc`
- `ntdll!RtlEnterCriticalSection` at `0x18000baa2`
- `ntdll!RtlEnterCriticalSection` at `0x18000b9cc`
- `ntdll!RtlEnterCriticalSection` at `0x18000baa2`
- `win32u!NtUserHardErrorControl` at `0x18000bb33`
- `win32u!NtUserHardErrorControl` at `0x18000bb61`
- `win32u!NtUserHardErrorControl` at `0x18000bb33`
- `win32u!NtUserHardErrorControl` at `0x18000bb61`
- `USER32!EnumThreadWindows` at `0x18000bb0e`
- `USER32!EnumThreadWindows` at `0x18000bb0e`
- `USER32!SetForegroundWindow` at `0x18000bb4b`
- `USER32!SetForegroundWindow` at `0x18000bb4b`
- `USER32!PostThreadMessageW` at `0x18000ba7b`
- `USER32!PostThreadMessageW` at `0x18000bbac`
- `USER32!PostThreadMessageW` at `0x18000ba7b`
- `USER32!PostThreadMessageW` at `0x18000bbac`

## pseudocode

```c
__int64 __fastcall BoostHardError(__int64 a1, int a2)
{
  unsigned int v5; // ebp
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rsi
  int v9; // eax
  DWORD v10; // ebx
  __int64 *v11; // rdx
  DWORD v12; // ebx
  _OWORD v13[4]; // [rsp+20h] [rbp-48h] BYREF
  LPARAM lParam; // [rsp+80h] [rbp+18h] BYREF

  v13[0] = 0;
  RtlEnterCriticalSection(&gcsUserSrv);
  if ( !gphiList )
  {
    RtlLeaveCriticalSection(&gcsUserSrv);
    return 0;
  }
  v5 = 0;
  v6 = &gphiList;
  *(_QWORD *)&v13[0] = 0;
  while ( a1 != -1 )
  {
    v7 = *(_QWORD *)(*v6 + 8);
    if ( v7 )
    {
      if ( *(_QWORD *)(v7 + 40) == a1 )
        break;
    }
    v6 = (__int64 *)*v6;
LABEL_13:
    if ( !*v6 )
      goto LABEL_21;
  }
  v5 = 1;
  if ( a2 == 1 )
  {
    v8 = *v6;
    *v6 = *(_QWORD *)*v6;
    v9 = *(_DWORD *)(v8 + 136);
    if ( (v9 & 1) != 0 )
    {
      v10 = gdwHardErrorThreadId;
      *(_DWORD *)(v8 + 136) = v9 | 2;
      RtlLeaveCriticalSection(&gcsUserSrv);
      PostThreadMessageW(v10, 0x12u, 0, 0);
    }
    else
    {
      RtlLeaveCriticalSection(&gcsUserSrv);
      ReplyHardError(v8, 1);
    }
    RtlEnterCriticalSection(&gcsUserSrv);
    v6 = &gphiList;
    goto LABEL_13;
  }
  if ( a2 )
  {
LABEL_21:
    RtlLeaveCriticalSection(&gcsUserSrv);
    if ( a2 == 1 )
    {
      if ( gdwHardErrorThreadId )
        PostThreadMessageW(gdwHardErrorThreadId, 0, 0, 0);
    }
    return v5;
  }
  v11 = (__int64 *)*v6;
  if ( (*(_BYTE *)(*v6 + 136) & 1) == 0 )
  {
    *v6 = *v11;
    *v11 = gphiList;
    gphiList = (__int64)v11;
    goto LABEL_21;
  }
  v12 = gdwHardErrorThreadId;
  lParam = 0;
  RtlLeaveCriticalSection(&gcsUserSrv);
  EnumThreadWindows(v12, FindWindowFromThread, (LPARAM)&lParam);
  if ( lParam && !(unsigned int)NtUserHardErrorControl(5, 0, v13) )
  {
    SetForegroundWindow((HWND)lParam);
    NtUserHardErrorControl(6, 0, v13);
  }
  return v5;
}

```

## disassembly

```asm
0x18000b9a8  push    rbx
0x18000b9aa  push    rbp
0x18000b9ab  push    rsi
0x18000b9ac  push    rdi
0x18000b9ad  push    r13
0x18000b9af  push    r14
0x18000b9b1  sub     rsp, 38h
0x18000b9b5  mov     r14, rcx
0x18000b9b8  lea     r13, gcsUserSrv
0x18000b9bf  xorps   xmm0, xmm0
0x18000b9c2  mov     rcx, r13; CriticalSection
0x18000b9c5  mov     edi, edx
0x18000b9c7  movups  [rsp+68h+var_48], xmm0
0x18000b9cc  call    cs:__imp_RtlEnterCriticalSection
0x18000b9d3  nop     dword ptr [rax+rax+00h]
0x18000b9d8  mov     rax, cs:gphiList
0x18000b9df  test    rax, rax
0x18000b9e2  jnz     short loc_18000B9FA
0x18000b9e4  mov     rcx, r13; CriticalSection
0x18000b9e7  call    cs:__imp_RtlLeaveCriticalSection
0x18000b9ee  nop     dword ptr [rax+rax+00h]
0x18000b9f3  xor     eax, eax
0x18000b9f5  jmp     loc_18000BBBA
0x18000b9fa  xor     ebp, ebp
0x18000b9fc  lea     rcx, gphiList
0x18000ba03  mov     qword ptr [rsp+68h+var_48], rbp
0x18000ba08  test    rax, rax
0x18000ba0b  jz      loc_18000BB86
0x18000ba11  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000ba15  jz      short loc_18000BA31
0x18000ba17  mov     rdx, [rcx]
0x18000ba1a  mov     rax, [rdx+8]
0x18000ba1e  test    rax, rax
0x18000ba21  jz      short loc_18000BA29
0x18000ba23  cmp     [rax+28h], r14
0x18000ba27  jz      short loc_18000BA31
0x18000ba29  mov     rcx, rdx
0x18000ba2c  jmp     loc_18000BAB5
0x18000ba31  mov     ebp, 1
0x18000ba36  cmp     edi, ebp
0x18000ba38  jnz     loc_18000BAC4
0x18000ba3e  mov     rsi, [rcx]
0x18000ba41  mov     rax, [rsi]
0x18000ba44  mov     [rcx], rax
0x18000ba47  mov     rcx, r13; CriticalSection
0x18000ba4a  mov     eax, [rsi+88h]
0x18000ba50  test    bpl, al
0x18000ba53  jz      short loc_18000BA89
0x18000ba55  mov     ebx, cs:gdwHardErrorThreadId
0x18000ba5b  or      eax, 2
0x18000ba5e  mov     [rsi+88h], eax
0x18000ba64  call    cs:__imp_RtlLeaveCriticalSection
0x18000ba6b  nop     dword ptr [rax+rax+00h]
0x18000ba70  xor     r9d, r9d; lParam
0x18000ba73  lea     edx, [rbp+11h]; Msg
0x18000ba76  xor     r8d, r8d; wParam
0x18000ba79  mov     ecx, ebx; idThread
0x18000ba7b  call    cs:__imp_PostThreadMessageW
0x18000ba82  nop     dword ptr [rax+rax+00h]
0x18000ba87  jmp     short loc_18000BA9F
0x18000ba89  call    cs:__imp_RtlLeaveCriticalSection
0x18000ba90  nop     dword ptr [rax+rax+00h]
0x18000ba95  mov     edx, ebp
0x18000ba97  mov     rcx, rsi
0x18000ba9a  call    ReplyHardError
0x18000ba9f  mov     rcx, r13; CriticalSection
0x18000baa2  call    cs:__imp_RtlEnterCriticalSection
0x18000baa9  nop     dword ptr [rax+rax+00h]
0x18000baae  lea     rcx, gphiList
0x18000bab5  cmp     qword ptr [rcx], 0
0x18000bab9  jnz     loc_18000BA11
0x18000babf  jmp     loc_18000BB86
0x18000bac4  test    edi, edi
0x18000bac6  jnz     loc_18000BB86
0x18000bacc  mov     rdx, [rcx]
0x18000bacf  test    [rdx+88h], bpl
0x18000bad6  jz      loc_18000BB6F
0x18000badc  mov     ebx, cs:gdwHardErrorThreadId
0x18000bae2  mov     rcx, r13; CriticalSection
0x18000bae5  mov     [rsp+68h+lParam], 0
0x18000baf1  call    cs:__imp_RtlLeaveCriticalSection
0x18000baf8  nop     dword ptr [rax+rax+00h]
0x18000bafd  lea     r8, [rsp+68h+lParam]; lParam
0x18000bb05  mov     ecx, ebx; dwThreadId
0x18000bb07  lea     rdx, FindWindowFromThread; lpfn
0x18000bb0e  call    cs:__imp_EnumThreadWindows
0x18000bb15  nop     dword ptr [rax+rax+00h]
0x18000bb1a  cmp     [rsp+68h+lParam], 0
0x18000bb23  jz      loc_18000BBB8
0x18000bb29  lea     r8, [rsp+68h+var_48]
0x18000bb2e  xor     edx, edx
0x18000bb30  lea     ecx, [rdi+5]
0x18000bb33  call    cs:__imp_NtUserHardErrorControl
0x18000bb3a  nop     dword ptr [rax+rax+00h]
0x18000bb3f  test    eax, eax
0x18000bb41  jnz     short loc_18000BBB8
0x18000bb43  mov     rcx, [rsp+68h+lParam]; hWnd
0x18000bb4b  call    cs:__imp_SetForegroundWindow
0x18000bb52  nop     dword ptr [rax+rax+00h]
0x18000bb57  lea     r8, [rsp+68h+var_48]
0x18000bb5c  xor     edx, edx
0x18000bb5e  lea     ecx, [rdi+6]
0x18000bb61  call    cs:__imp_NtUserHardErrorControl
0x18000bb68  nop     dword ptr [rax+rax+00h]
0x18000bb6d  jmp     short loc_18000BBB8
0x18000bb6f  mov     rax, [rdx]
0x18000bb72  mov     [rcx], rax
0x18000bb75  mov     rax, cs:gphiList
0x18000bb7c  mov     [rdx], rax
0x18000bb7f  mov     cs:gphiList, rdx
0x18000bb86  mov     rcx, r13; CriticalSection
0x18000bb89  call    cs:__imp_RtlLeaveCriticalSection
0x18000bb90  nop     dword ptr [rax+rax+00h]
0x18000bb95  cmp     edi, 1
0x18000bb98  jnz     short loc_18000BBB8
0x18000bb9a  mov     ecx, cs:gdwHardErrorThreadId; idThread
0x18000bba0  test    ecx, ecx
0x18000bba2  jz      short loc_18000BBB8
0x18000bba4  xor     r9d, r9d; lParam
0x18000bba7  xor     r8d, r8d; wParam
0x18000bbaa  xor     edx, edx; Msg
0x18000bbac  call    cs:__imp_PostThreadMessageW
0x18000bbb3  nop     dword ptr [rax+rax+00h]
0x18000bbb8  mov     eax, ebp
0x18000bbba  add     rsp, 38h
0x18000bbbe  pop     r14
0x18000bbc0  pop     r13
0x18000bbc2  pop     rdi
0x18000bbc3  pop     rsi
0x18000bbc4  pop     rbp
0x18000bbc5  pop     rbx
0x18000bbc6  retn
```
