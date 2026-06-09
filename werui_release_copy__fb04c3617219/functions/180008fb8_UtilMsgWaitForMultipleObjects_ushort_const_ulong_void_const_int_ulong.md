# UtilMsgWaitForMultipleObjects(ushort const *,ulong,void * * const,int,ulong)

- ea: `0x180008fb8`
- end: `0x1800090ca`
- name: `?UtilMsgWaitForMultipleObjects@@YAKPEBGKQEAPEAXHK@Z`
- size: `274`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, void **const, int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180007a70`
- `0x1800090d0`
- `0x180009350`
- `0x18000daa0`

## callees

- `0x1800025c4`
- `0x180002684`
- `0x180008fb8`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x180009035`
- `KERNEL32!WaitForMultipleObjects` at `0x18000904c`
- `KERNEL32!WaitForMultipleObjects` at `0x180009035`
- `KERNEL32!WaitForMultipleObjects` at `0x18000904c`
- `KERNEL32!GetLastError` at `0x180009016`
- `KERNEL32!GetLastError` at `0x180009016`
- `KERNEL32!GetTickCount64` at `0x180008fc6`
- `KERNEL32!GetTickCount64` at `0x1800090bf`
- `KERNEL32!GetTickCount64` at `0x180008fc6`
- `KERNEL32!GetTickCount64` at `0x1800090bf`
- `KERNEL32!SetLastError` at `0x180008fe1`
- `KERNEL32!SetLastError` at `0x180008fe1`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1800090b5`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1800090b5`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18000908f`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18000908f`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x18000909a`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x18000909a`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18000900e`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18000900e`

## pseudocode

```c
__int64 __fastcall UtilMsgWaitForMultipleObjects(const unsigned __int16 *a1, DWORD a2, void **const a3)
{
  ULONGLONG TickCount64; // rax
  DWORD v6; // ebx
  DWORD LastError; // eax
  MSG Msg; // [rsp+30h] [rbp-58h] BYREF

  TickCount64 = GetTickCount64();
  if ( TickCount64 + 0xFFFFFFFF >= TickCount64 )
  {
    while ( 1 )
    {
      if ( !(unsigned __int8)IsMsgWaitForMultipleObjectsPresent()
        || (v6 = MsgWaitForMultipleObjects(a2, a3, 0, 0xFFFFFFFF, 0x1CFFu), LastError = GetLastError(), v6 == -1)
        && (LastError == 127 || LastError == 120) )
      {
        v6 = WaitForMultipleObjects(a2, a3, 0, 0xFFFFFFFF);
      }
      if ( v6 != a2 )
        break;
      v6 = WaitForMultipleObjects(a2, a3, 0, 0);
      if ( v6 != 258 )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( (unsigned __int8)IsPostMessageWPresent()
        && (unsigned __int8)IsPostMessageWPresent()
        && (unsigned __int8)IsPostMessageWPresent() )
      {
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      GetTickCount64();
    }
  }
  else
  {
    v6 = -1;
    SetLastError(0x216u);
  }
  return v6;
}

```

## disassembly

```asm
0x180008fb8  push    rbx
0x180008fba  push    rbp
0x180008fbb  push    rsi
0x180008fbc  push    rdi
0x180008fbd  sub     rsp, 68h
0x180008fc1  mov     rsi, r8
0x180008fc4  mov     edi, edx
0x180008fc6  call    cs:__imp_GetTickCount64
0x180008fcc  mov     ebp, 0FFFFFFFFh
0x180008fd1  lea     rcx, [rax+rbp]
0x180008fd5  cmp     rcx, rax
0x180008fd8  jnb     short loc_180008FF2
0x180008fda  mov     ecx, 216h; dwErrCode
0x180008fdf  mov     ebx, ebp
0x180008fe1  call    cs:__imp_SetLastError
0x180008fe7  mov     eax, ebx
0x180008fe9  add     rsp, 68h
0x180008fed  pop     rdi
0x180008fee  pop     rsi
0x180008fef  pop     rbp
0x180008ff0  pop     rbx
0x180008ff1  retn
0x180008ff2  call    IsMsgWaitForMultipleObjectsPresent
0x180008ff7  test    al, al
0x180008ff9  jz      short loc_18000902A
0x180008ffb  mov     r9d, ebp; dwMilliseconds
0x180008ffe  mov     [rsp+88h+dwWakeMask], 1CFFh; dwWakeMask
0x180009006  xor     r8d, r8d; fWaitAll
0x180009009  mov     rdx, rsi; pHandles
0x18000900c  mov     ecx, edi; nCount
0x18000900e  call    cs:__imp_MsgWaitForMultipleObjects
0x180009014  mov     ebx, eax
0x180009016  call    cs:__imp_GetLastError
0x18000901c  cmp     ebx, ebp
0x18000901e  jnz     short loc_18000903D
0x180009020  cmp     eax, 7Fh
0x180009023  jz      short loc_18000902A
0x180009025  cmp     eax, 78h ; 'x'
0x180009028  jnz     short loc_18000903D
0x18000902a  mov     r9d, ebp; dwMilliseconds
0x18000902d  xor     r8d, r8d; bWaitAll
0x180009030  mov     rdx, rsi; lpHandles
0x180009033  mov     ecx, edi; nCount
0x180009035  call    cs:__imp_WaitForMultipleObjects
0x18000903b  mov     ebx, eax
0x18000903d  cmp     ebx, edi
0x18000903f  jnz     short loc_180008FE7
0x180009041  xor     r9d, r9d; dwMilliseconds
0x180009044  xor     r8d, r8d; bWaitAll
0x180009047  mov     rdx, rsi; lpHandles
0x18000904a  mov     ecx, edi; nCount
0x18000904c  call    cs:__imp_WaitForMultipleObjects
0x180009052  mov     ebx, eax
0x180009054  cmp     eax, 102h
0x180009059  jnz     short loc_180008FE7
0x18000905b  xorps   xmm0, xmm0
0x18000905e  movups  xmmword ptr [rsp+88h+Msg.hwnd], xmm0
0x180009063  movups  xmmword ptr [rsp+88h+Msg.wParam], xmm0
0x180009068  movups  xmmword ptr [rsp+88h+Msg.time], xmm0
0x18000906d  call    IsPostMessageWPresent
0x180009072  test    al, al
0x180009074  jz      short loc_1800090BF
0x180009076  call    IsPostMessageWPresent
0x18000907b  test    al, al
0x18000907d  jz      short loc_1800090BF
0x18000907f  call    IsPostMessageWPresent
0x180009084  test    al, al
0x180009086  jz      short loc_1800090BF
0x180009088  jmp     short loc_1800090A0
0x18000908a  lea     rcx, [rsp+88h+Msg]; lpMsg
0x18000908f  call    cs:__imp_TranslateMessage
0x180009095  lea     rcx, [rsp+88h+Msg]; lpMsg
0x18000909a  call    cs:__imp_DispatchMessageW
0x1800090a0  xor     r9d, r9d; wMsgFilterMax
0x1800090a3  mov     [rsp+88h+dwWakeMask], 1; wRemoveMsg
0x1800090ab  xor     r8d, r8d; wMsgFilterMin
0x1800090ae  lea     rcx, [rsp+88h+Msg]; lpMsg
0x1800090b3  xor     edx, edx; hWnd
0x1800090b5  call    cs:__imp_PeekMessageW
0x1800090bb  test    eax, eax
0x1800090bd  jnz     short loc_18000908A
0x1800090bf  call    cs:__imp_GetTickCount64
0x1800090c5  jmp     loc_180008FF2
```
