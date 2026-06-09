# CServiceControl::Start(void)

- ea: `0x140091d60`
- end: `0x140091e77`
- name: `?Start@CServiceControl@@QEAAHXZ`
- size: `279`
- prototype: `__int64 __fastcall(CServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1400479b0`

## callees

- `0x14003b714`
- `0x14003f17c`
- `0x140047798`
- `0x140091a70`
- `0x140091d60`

## import_xrefs

- `ADVAPI32!StartServiceW` at `0x140091dea`
- `ADVAPI32!StartServiceW` at `0x140091dea`
- `KERNEL32!GetLastError` at `0x140091df7`
- `KERNEL32!GetLastError` at `0x140091df7`

## pseudocode

```c
__int64 __fastcall CServiceControl::Start(SC_HANDLE *this)
{
  unsigned int v2; // eax
  unsigned int started; // ebx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_cb23d491edf93b904e2862226171c496_Traceguids);
  v2 = CServiceControl::OpenServiceW((CServiceControl *)this, 0);
  started = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_cb23d491edf93b904e2862226171c496_Traceguids, v2);
  }
  if ( started == 1 )
  {
    started = StartServiceW(this[2], 0, 0);
    if ( started != 1 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_cb23d491edf93b904e2862226171c496_Traceguids, LastError);
      }
    }
  }
  CServiceControl::CloseServiceManager((CServiceControl *)this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_cb23d491edf93b904e2862226171c496_Traceguids, started);
  }
  return started;
}

```

## disassembly

```asm
0x140091d60  mov     [rsp+arg_0], rbx
0x140091d65  mov     [rsp+arg_8], rsi
0x140091d6a  push    rdi
0x140091d6b  sub     rsp, 20h
0x140091d6f  mov     rdi, rcx
0x140091d72  mov     rcx, cs:WPP_GLOBAL_Control
0x140091d79  lea     rsi, WPP_GLOBAL_Control
0x140091d80  cmp     rcx, rsi
0x140091d83  jz      short loc_140091DA0
0x140091d85  test    byte ptr [rcx+1Ch], 1
0x140091d89  jz      short loc_140091DA0
0x140091d8b  mov     rcx, [rcx+10h]
0x140091d8f  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091d96  mov     edx, 20h ; ' '
0x140091d9b  call    WPP_SF_
0x140091da0  xor     edx, edx; int
0x140091da2  mov     rcx, rdi; this
0x140091da5  call    ?OpenServiceW@CServiceControl@@AEAAHH@Z; CServiceControl::OpenServiceW(int)
0x140091daa  mov     ebx, eax
0x140091dac  mov     rcx, cs:WPP_GLOBAL_Control
0x140091db3  cmp     rcx, rsi
0x140091db6  jz      short loc_140091DDC
0x140091db8  test    byte ptr [rcx+1Ch], 2
0x140091dbc  jz      short loc_140091DDC
0x140091dbe  cmp     byte ptr [rcx+19h], 4
0x140091dc2  jb      short loc_140091DDC
0x140091dc4  mov     rcx, [rcx+10h]
0x140091dc8  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091dcf  mov     edx, 21h ; '!'
0x140091dd4  mov     r9d, eax
0x140091dd7  call    WPP_SF_d
0x140091ddc  cmp     ebx, 1
0x140091ddf  jnz     short loc_140091E2D
0x140091de1  mov     rcx, [rdi+10h]; hService
0x140091de5  xor     r8d, r8d; lpServiceArgVectors
0x140091de8  xor     edx, edx; dwNumServiceArgs
0x140091dea  call    cs:__imp_StartServiceW
0x140091df0  mov     ebx, eax
0x140091df2  cmp     eax, 1
0x140091df5  jz      short loc_140091E2D
0x140091df7  call    cs:__imp_GetLastError
0x140091dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140091e04  cmp     rcx, rsi
0x140091e07  jz      short loc_140091E2D
0x140091e09  test    byte ptr [rcx+1Ch], 2
0x140091e0d  jz      short loc_140091E2D
0x140091e0f  cmp     byte ptr [rcx+19h], 4
0x140091e13  jb      short loc_140091E2D
0x140091e15  mov     rcx, [rcx+10h]
0x140091e19  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091e20  mov     edx, 22h ; '"'
0x140091e25  mov     r9d, eax
0x140091e28  call    WPP_SF_d
0x140091e2d  mov     rcx, rdi; this
0x140091e30  call    ?CloseServiceManager@CServiceControl@@AEAAXXZ; CServiceControl::CloseServiceManager(void)
0x140091e35  mov     rcx, cs:WPP_GLOBAL_Control
0x140091e3c  cmp     rcx, rsi
0x140091e3f  jz      short loc_140091E65
0x140091e41  test    byte ptr [rcx+1Ch], 1
0x140091e45  jz      short loc_140091E65
0x140091e47  cmp     byte ptr [rcx+19h], 5
0x140091e4b  jb      short loc_140091E65
0x140091e4d  mov     rcx, [rcx+10h]
0x140091e51  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091e58  mov     edx, 23h ; '#'
0x140091e5d  mov     r9d, ebx
0x140091e60  call    WPP_SF_d
0x140091e65  mov     rsi, [rsp+28h+arg_8]
0x140091e6a  mov     eax, ebx
0x140091e6c  mov     rbx, [rsp+28h+arg_0]
0x140091e71  add     rsp, 20h
0x140091e75  pop     rdi
0x140091e76  retn
```
