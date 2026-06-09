# ResolverContextThread

- ea: `0x180011120`
- end: `0x1800113c5`
- name: `ResolverContextThread`
- size: `677`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180011120`
- `0x180011714`
- `0x1800117c8`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180011210`
- `KERNELBASE!LocalAlloc` at `0x180011210`
- `ntdll!NtSetEvent` at `0x1800112f0`
- `ntdll!NtSetEvent` at `0x180011385`
- `ntdll!NtSetEvent` at `0x1800112f0`
- `ntdll!NtSetEvent` at `0x180011385`
- `ntdll!NtWaitForSingleObject` at `0x18001117c`
- `ntdll!NtWaitForSingleObject` at `0x18001139a`
- `ntdll!NtWaitForSingleObject` at `0x18001117c`
- `ntdll!NtWaitForSingleObject` at `0x18001139a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800112bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800112bf`
- `win32u!NtUserSetInformationThread` at `0x1800111c7`
- `win32u!NtUserSetInformationThread` at `0x1800111ee`
- `win32u!NtUserSetInformationThread` at `0x18001126b`
- `win32u!NtUserSetInformationThread` at `0x1800112a1`
- `win32u!NtUserSetInformationThread` at `0x180011346`
- `win32u!NtUserSetInformationThread` at `0x180011373`
- `win32u!NtUserSetInformationThread` at `0x1800111c7`
- `win32u!NtUserSetInformationThread` at `0x1800111ee`
- `win32u!NtUserSetInformationThread` at `0x18001126b`
- `win32u!NtUserSetInformationThread` at `0x1800112a1`
- `win32u!NtUserSetInformationThread` at `0x180011346`
- `win32u!NtUserSetInformationThread` at `0x180011373`
- `USER32!MsgWaitForMultipleObjects` at `0x180011320`
- `USER32!MsgWaitForMultipleObjects` at `0x180011320`
- `USER32!PeekMessageW` at `0x180011167`
- `USER32!PeekMessageW` at `0x180011167`
- `USER32!EnumWindows` at `0x180011238`
- `USER32!EnumWindows` at `0x180011238`

## pseudocode

```c
__int64 __fastcall ResolverContextThread(__int64 a1)
{
  __int64 v2; // r15
  int v3; // esi
  int v4; // ebp
  __int64 v5; // rdi
  _QWORD *v6; // rax
  _DWORD *v7; // rsi
  int v8; // edi
  __int64 v9; // rdi
  _DWORD *v10; // r14
  __int64 i; // rdi
  __int128 v13; // [rsp+30h] [rbp-88h] BYREF
  __int64 v14; // [rsp+40h] [rbp-78h]
  struct tagMSG Msg; // [rsp+48h] [rbp-70h] BYREF

  v14 = 0;
  memset(&Msg, 0, sizeof(Msg));
  v13 = 0;
  PeekMessageW(&Msg, 0, 0x400u, 0x400u, 0);
  NtWaitForSingleObject(*(HANDLE *)(a1 + 64), 0, 0);
  while ( (*(_BYTE *)(a1 + 96) & 1) == 0 )
  {
    v2 = *(_QWORD *)(a1 + 16);
    v3 = 0;
    v14 = 0;
    v4 = 0;
    v13 = 0;
    if ( *(_DWORD *)(a1 + 100) )
      goto LABEL_30;
    NtUserSetInformationThread(-2, 12, v2 + 16);
    *(_QWORD *)&v13 = *(_QWORD *)(v2 + 24);
    v3 = 1;
    if ( (int)NtUserSetInformationThread(-2, 8, &v13) < 0 )
      goto LABEL_30;
    v5 = *(_QWORD *)(v2 + 16);
    v6 = LocalAlloc(0x40u, 0x518u);
    v7 = v6;
    if ( v6 )
    {
      *v6 = v5;
      EnumWindows(ResolverEnumWindowsProc, (LPARAM)v6);
      ResolverSortEnumeratedWindows(v7);
      v9 = 0;
      v10 = v7 + 6;
      if ( v7[2] )
      {
        while ( (int)NtUserSetInformationThread(-2, 13, &v10[2 * v9]) >= 0 )
        {
          v9 = (unsigned int)(v9 + 1);
          if ( (unsigned int)v9 >= v7[2] )
            goto LABEL_9;
        }
LABEL_10:
        v8 = 0;
      }
      else
      {
LABEL_9:
        for ( i = (unsigned int)(64 - v7[3]); (unsigned int)i < 0x40; i = (unsigned int)(i + 1) )
        {
          if ( (int)NtUserSetInformationThread(-2, 13, &v10[2 * i]) < 0 )
            goto LABEL_10;
        }
        v8 = 1;
      }
      LocalFree(v7);
    }
    else
    {
      v8 = 0;
    }
    v3 = 1;
    v4 = 1;
    if ( !v8 )
    {
LABEL_30:
      if ( !*(_DWORD *)(a1 + 100) )
        *(_DWORD *)(a1 + 100) = 260;
      NtSetEvent(*(HANDLE *)(v2 + 32), 0);
    }
    while ( MsgWaitForMultipleObjects(1u, (const HANDLE *)(a1 + 80), 0, 0xFFFFFFFF, 0x1CFFu) )
      ResolverProcessMessages(a1, v2);
    if ( v3 )
      NtUserSetInformationThread(-2, 14, *(_QWORD *)(a1 + 16) + 16LL);
    ResolverProcessMessages(a1, v2);
    if ( v4 )
      NtUserSetInformationThread(-2, 9, &v13);
    NtSetEvent(*(HANDLE *)(a1 + 72), 0);
    NtWaitForSingleObject(*(HANDLE *)(a1 + 64), 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180011120  push    rbx
0x180011122  push    rbp
0x180011123  push    rsi
0x180011124  push    rdi
0x180011125  push    r12
0x180011127  push    r14
0x180011129  push    r15
0x18001112b  sub     rsp, 80h
0x180011132  xorps   xmm0, xmm0
0x180011135  xor     eax, eax
0x180011137  mov     r8d, 400h; wMsgFilterMin
0x18001113d  mov     [rsp+0B8h+var_78], rax
0x180011142  mov     rbx, rcx
0x180011145  mov     [rsp+0B8h+wRemoveMsg], eax; wRemoveMsg
0x180011149  mov     r9d, r8d; wMsgFilterMax
0x18001114c  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180011151  xor     edx, edx; hWnd
0x180011153  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x180011158  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x18001115d  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x180011162  movups  [rsp+0B8h+var_88], xmm0
0x180011167  call    cs:__imp_PeekMessageW
0x18001116e  nop     dword ptr [rax+rax+00h]
0x180011173  mov     rcx, [rbx+40h]; Handle
0x180011177  xor     r8d, r8d; Timeout
0x18001117a  xor     edx, edx; Alertable
0x18001117c  call    cs:__imp_NtWaitForSingleObject
0x180011183  nop     dword ptr [rax+rax+00h]
0x180011188  test    byte ptr [rbx+60h], 1
0x18001118c  jnz     loc_1800113B0
0x180011192  mov     r14, 0FFFFFFFFFFFFFFFEh
0x180011199  mov     r15, [rbx+10h]
0x18001119d  xor     eax, eax
0x18001119f  xor     esi, esi
0x1800111a1  mov     [rsp+0B8h+var_78], rax
0x1800111a6  xor     ebp, ebp
0x1800111a8  xorps   xmm0, xmm0
0x1800111ab  movups  [rsp+0B8h+var_88], xmm0
0x1800111b0  cmp     [rbx+64h], eax
0x1800111b3  jnz     loc_1800112DD
0x1800111b9  lea     r9d, [rsi+8]
0x1800111bd  mov     rcx, r14
0x1800111c0  lea     r8, [r15+10h]
0x1800111c4  lea     edx, [rsi+0Ch]
0x1800111c7  call    cs:__imp_NtUserSetInformationThread
0x1800111ce  nop     dword ptr [rax+rax+00h]
0x1800111d3  mov     rax, [r15+18h]
0x1800111d7  lea     r9d, [rbp+18h]
0x1800111db  lea     r8, [rsp+0B8h+var_88]
0x1800111e0  mov     qword ptr [rsp+0B8h+var_88], rax
0x1800111e5  lea     edx, [rbp+8]
0x1800111e8  mov     rcx, r14
0x1800111eb  lea     esi, [rbp+1]
0x1800111ee  call    cs:__imp_NtUserSetInformationThread
0x1800111f5  nop     dword ptr [rax+rax+00h]
0x1800111fa  test    eax, eax
0x1800111fc  js      loc_1800112DD
0x180011202  mov     rdi, [r15+10h]
0x180011206  lea     ebp, [rsi+3Fh]
0x180011209  mov     ecx, ebp; uFlags
0x18001120b  mov     edx, 518h; uBytes
0x180011210  call    cs:__imp_LocalAlloc
0x180011217  nop     dword ptr [rax+rax+00h]
0x18001121c  mov     rsi, rax
0x18001121f  test    rax, rax
0x180011222  jnz     short loc_18001122B
0x180011224  xor     edi, edi
0x180011226  jmp     loc_1800112D2
0x18001122b  mov     rdx, rsi; lParam
0x18001122e  mov     [rax], rdi
0x180011231  lea     rcx, ResolverEnumWindowsProc; lpEnumFunc
0x180011238  call    cs:__imp_EnumWindows
0x18001123f  nop     dword ptr [rax+rax+00h]
0x180011244  mov     rcx, rsi
0x180011247  call    ResolverSortEnumeratedWindows
0x18001124c  xor     edi, edi
0x18001124e  lea     r14, [rsi+18h]
0x180011252  cmp     [rsi+8], edi
0x180011255  jbe     short loc_180011282
0x180011257  mov     edx, 0Dh
0x18001125c  lea     r8, [r14+rdi*8]
0x180011260  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180011267  lea     r9d, [rdx-5]
0x18001126b  call    cs:__imp_NtUserSetInformationThread
0x180011272  nop     dword ptr [rax+rax+00h]
0x180011277  test    eax, eax
0x180011279  js      short loc_180011289
0x18001127b  inc     edi
0x18001127d  cmp     edi, [rsi+8]
0x180011280  jb      short loc_180011257
0x180011282  mov     edi, ebp
0x180011284  sub     edi, [rsi+0Ch]
0x180011287  jmp     short loc_1800112B3
0x180011289  xor     edi, edi
0x18001128b  jmp     short loc_1800112BC
0x18001128d  mov     edx, 0Dh
0x180011292  lea     r8, [r14+rdi*8]
0x180011296  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18001129d  lea     r9d, [rdx-5]
0x1800112a1  call    cs:__imp_NtUserSetInformationThread
0x1800112a8  nop     dword ptr [rax+rax+00h]
0x1800112ad  test    eax, eax
0x1800112af  js      short loc_180011289
0x1800112b1  inc     edi
0x1800112b3  cmp     edi, ebp
0x1800112b5  jb      short loc_18001128D
0x1800112b7  mov     edi, 1
0x1800112bc  mov     rcx, rsi; hMem
0x1800112bf  call    cs:__imp_LocalFree
0x1800112c6  nop     dword ptr [rax+rax+00h]
0x1800112cb  mov     r14, 0FFFFFFFFFFFFFFFEh
0x1800112d2  mov     esi, 1
0x1800112d7  mov     ebp, esi
0x1800112d9  test    edi, edi
0x1800112db  jnz     short loc_180011309
0x1800112dd  cmp     dword ptr [rbx+64h], 0
0x1800112e1  jnz     short loc_1800112EA
0x1800112e3  mov     dword ptr [rbx+64h], 104h
0x1800112ea  mov     rcx, [r15+20h]; EventHandle
0x1800112ee  xor     edx, edx; PreviousState
0x1800112f0  call    cs:__imp_NtSetEvent
0x1800112f7  nop     dword ptr [rax+rax+00h]
0x1800112fc  jmp     short loc_180011309
0x1800112fe  mov     rdx, r15
0x180011301  mov     rcx, rbx
0x180011304  call    ResolverProcessMessages
0x180011309  xor     r8d, r8d; fWaitAll
0x18001130c  mov     [rsp+0B8h+wRemoveMsg], 1CFFh; dwWakeMask
0x180011314  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180011318  lea     rdx, [rbx+50h]; pHandles
0x18001131c  lea     ecx, [r8+1]; nCount
0x180011320  call    cs:__imp_MsgWaitForMultipleObjects
0x180011327  nop     dword ptr [rax+rax+00h]
0x18001132c  test    eax, eax
0x18001132e  jnz     short loc_1800112FE
0x180011330  test    esi, esi
0x180011332  jz      short loc_180011352
0x180011334  mov     r8, [rbx+10h]
0x180011338  lea     edx, [rax+0Eh]
0x18001133b  add     r8, 10h
0x18001133f  lea     r9d, [rax+8]
0x180011343  mov     rcx, r14
0x180011346  call    cs:__imp_NtUserSetInformationThread
0x18001134d  nop     dword ptr [rax+rax+00h]
0x180011352  mov     rdx, r15
0x180011355  mov     rcx, rbx
0x180011358  call    ResolverProcessMessages
0x18001135d  test    ebp, ebp
0x18001135f  jz      short loc_18001137F
0x180011361  mov     r9d, 18h
0x180011367  lea     r8, [rsp+0B8h+var_88]
0x18001136c  mov     rcx, r14
0x18001136f  lea     edx, [r9-0Fh]
0x180011373  call    cs:__imp_NtUserSetInformationThread
0x18001137a  nop     dword ptr [rax+rax+00h]
0x18001137f  mov     rcx, [rbx+48h]; EventHandle
0x180011383  xor     edx, edx; PreviousState
0x180011385  call    cs:__imp_NtSetEvent
0x18001138c  nop     dword ptr [rax+rax+00h]
0x180011391  mov     rcx, [rbx+40h]; Handle
0x180011395  xor     r8d, r8d; Timeout
0x180011398  xor     edx, edx; Alertable
0x18001139a  call    cs:__imp_NtWaitForSingleObject
0x1800113a1  nop     dword ptr [rax+rax+00h]
0x1800113a6  test    byte ptr [rbx+60h], 1
0x1800113aa  jz      loc_180011199
0x1800113b0  xor     eax, eax
0x1800113b2  add     rsp, 80h
0x1800113b9  pop     r15
0x1800113bb  pop     r14
0x1800113bd  pop     r12
0x1800113bf  pop     rdi
0x1800113c0  pop     rsi
0x1800113c1  pop     rbp
0x1800113c2  pop     rbx
0x1800113c3  retn
```
