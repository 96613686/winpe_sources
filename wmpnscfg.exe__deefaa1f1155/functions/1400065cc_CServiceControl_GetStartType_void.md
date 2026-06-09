# CServiceControl::GetStartType(void)

- ea: `0x1400065cc`
- end: `0x14000675d`
- name: `?GetStartType@CServiceControl@@QEAAKXZ`
- size: `401`
- prototype: `__int64 __fastcall(SC_HANDLE *this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140005658`

## callees

- `0x1400053b4`
- `0x1400053dc`
- `0x140006474`
- `0x1400065cc`
- `0x140006848`
- `0x140006978`
- `0x1400069bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000674c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000674c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000664e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000664e`
- `ADVAPI32!QueryServiceConfigW` at `0x1400066ad`
- `ADVAPI32!QueryServiceConfigW` at `0x1400066ad`
- `KERNEL32!GetLastError` at `0x1400066b8`
- `KERNEL32!GetLastError` at `0x1400066b8`

## pseudocode

```c
__int64 __fastcall CServiceControl::GetStartType(SC_HANDLE *this, int a2)
{
  DWORD dwStartType; // edi
  unsigned int v4; // eax
  unsigned int v5; // ebx
  struct _QUERY_SERVICE_CONFIGW *v6; // rbx
  SC_HANDLE v7; // rcx
  DWORD LastError; // eax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD pcbBytesNeeded; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
  dwStartType = 0;
  v4 = CServiceControl::OpenServiceW((CServiceControl *)this, a2);
  v5 = v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_cb23d491edf93b904e2862226171c496_Traceguids, v4);
  }
  if ( v5 == 1 )
  {
    v6 = (struct _QUERY_SERVICE_CONFIGW *)malloc(0x2000u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_cb23d491edf93b904e2862226171c496_Traceguids, v6 != 0);
    }
    if ( v6 )
    {
      v7 = this[2];
      pcbBytesNeeded = 0;
      if ( QueryServiceConfigW(v7, v6, 0x2000u, &pcbBytesNeeded) )
      {
        dwStartType = v6->dwStartType;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
        }
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v9, LastError);
        }
      }
    }
  }
  else
  {
    v6 = 0;
  }
  CServiceControl::CloseServiceManager((CServiceControl *)this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, dwStartType);
  }
  free(v6);
  return dwStartType;
}

```

## disassembly

```asm
0x1400065cc  push    rbx
0x1400065ce  push    rbp
0x1400065cf  push    rsi
0x1400065d0  push    rdi
0x1400065d1  sub     rsp, 28h
0x1400065d5  mov     rsi, rcx
0x1400065d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065df  lea     rbp, WPP_GLOBAL_Control
0x1400065e6  cmp     rcx, rbp
0x1400065e9  jz      short loc_140006606
0x1400065eb  test    byte ptr [rcx+1Ch], 1
0x1400065ef  jz      short loc_140006606
0x1400065f1  mov     rcx, [rcx+10h]
0x1400065f5  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x1400065fc  mov     edx, 14h
0x140006601  call    WPP_SF_
0x140006606  xor     edi, edi
0x140006608  mov     rcx, rsi; this
0x14000660b  call    ?OpenServiceW@CServiceControl@@AEAAHH@Z; CServiceControl::OpenServiceW(int)
0x140006610  mov     ebx, eax
0x140006612  mov     rcx, cs:WPP_GLOBAL_Control
0x140006619  cmp     rcx, rbp
0x14000661c  jz      short loc_140006640
0x14000661e  test    byte ptr [rcx+1Ch], 2
0x140006622  jz      short loc_140006640
0x140006624  cmp     byte ptr [rcx+19h], 4
0x140006628  jb      short loc_140006640
0x14000662a  mov     rcx, [rcx+10h]
0x14000662e  lea     edx, [rdi+15h]
0x140006631  mov     r9d, eax
0x140006634  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x14000663b  call    WPP_SF_d
0x140006640  cmp     ebx, 1
0x140006643  jnz     loc_14000671B
0x140006649  mov     ecx, 2000h; Size
0x14000664e  call    cs:__imp_malloc
0x140006654  xor     r9d, r9d
0x140006657  mov     rbx, rax
0x14000665a  test    rax, rax
0x14000665d  setnz   r9b
0x140006661  mov     rcx, cs:WPP_GLOBAL_Control
0x140006668  cmp     rcx, rbp
0x14000666b  jz      short loc_14000668E
0x14000666d  test    byte ptr [rcx+1Ch], 2
0x140006671  jz      short loc_14000668E
0x140006673  cmp     byte ptr [rcx+19h], 4
0x140006677  jb      short loc_14000668E
0x140006679  mov     rcx, [rcx+10h]
0x14000667d  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140006684  mov     edx, 16h
0x140006689  call    WPP_SF_d
0x14000668e  test    rbx, rbx
0x140006691  jz      loc_14000671D
0x140006697  mov     rcx, [rsi+10h]; hService
0x14000669b  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x1400066a0  mov     r8d, 2000h; cbBufSize
0x1400066a6  mov     [rsp+48h+pcbBytesNeeded], edi
0x1400066aa  mov     rdx, rbx; lpServiceConfig
0x1400066ad  call    cs:__imp_QueryServiceConfigW
0x1400066b3  cmp     eax, 1
0x1400066b6  jz      short loc_1400066E9
0x1400066b8  call    cs:__imp_GetLastError
0x1400066be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066c5  cmp     rcx, rbp
0x1400066c8  jz      short loc_14000671D
0x1400066ca  test    byte ptr [rcx+1Ch], 2
0x1400066ce  jz      short loc_14000671D
0x1400066d0  cmp     byte ptr [rcx+19h], 4
0x1400066d4  jb      short loc_14000671D
0x1400066d6  mov     rcx, [rcx+10h]
0x1400066da  mov     edx, 17h
0x1400066df  mov     r9d, eax
0x1400066e2  call    WPP_SF_D
0x1400066e7  jmp     short loc_14000671D
0x1400066e9  mov     edi, [rbx+4]
0x1400066ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066f3  cmp     rcx, rbp
0x1400066f6  jz      short loc_14000671D
0x1400066f8  test    byte ptr [rcx+1Ch], 2
0x1400066fc  jz      short loc_14000671D
0x1400066fe  cmp     byte ptr [rcx+19h], 4
0x140006702  jb      short loc_14000671D
0x140006704  mov     rcx, [rcx+10h]
0x140006708  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x14000670f  mov     edx, 18h
0x140006714  call    WPP_SF_
0x140006719  jmp     short loc_14000671D
0x14000671b  xor     ebx, ebx
0x14000671d  mov     rcx, rsi; this
0x140006720  call    ?CloseServiceManager@CServiceControl@@AEAAXXZ; CServiceControl::CloseServiceManager(void)
0x140006725  mov     rcx, cs:WPP_GLOBAL_Control
0x14000672c  cmp     rcx, rbp
0x14000672f  jz      short loc_140006749
0x140006731  test    byte ptr [rcx+1Ch], 1
0x140006735  jz      short loc_140006749
0x140006737  cmp     byte ptr [rcx+19h], 5
0x14000673b  jb      short loc_140006749
0x14000673d  mov     rcx, [rcx+10h]
0x140006741  mov     r9d, edi
0x140006744  call    WPP_SF_L
0x140006749  mov     rcx, rbx; Block
0x14000674c  call    cs:__imp_free
0x140006752  mov     eax, edi
0x140006754  add     rsp, 28h
0x140006758  pop     rdi
0x140006759  pop     rsi
0x14000675a  pop     rbp
0x14000675b  pop     rbx
0x14000675c  retn
```
