# ServiceShutdownTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800060b0`
- end: `0x180006251`
- name: `?ServiceShutdownTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `417`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800060b0`
- `0x180007f28`
- `0x18000dfd4`
- `0x18000e53c`
- `0x18000ea08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006202`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061bd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800061b3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800061b3`

## string_xrefs

- `0x180006172`: `SERVICE_STOP_PENDING`

## pseudocode

```c
void __fastcall ServiceShutdownTimerCallback(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)
{
  signed int LastError; // eax
  void *v5; // rcx

  if ( Context )
  {
    if ( g_RefCount > 0 )
    {
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
          (unsigned int)g_RefCount);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
      }
      _InterlockedOr64(&qword_18001F2B0, 2u);
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
          L"SERVICE_STOP_PENDING");
      }
      *(_QWORD *)(Context + 20) = 0;
      *((_DWORD *)Context + 2) = 48;
      *((_DWORD *)Context + 3) = 3;
      *((_DWORD *)Context + 7) = 3;
      *((_DWORD *)Context + 8) = 10000;
      *((_DWORD *)Context + 4) = 0;
      if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)Context, (LPSERVICE_STATUS)(Context + 8)) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
            (unsigned int)LastError);
        }
      }
      v5 = (void *)*((_QWORD *)Context + 7);
      if ( v5 )
        SetEvent(v5);
    }
    g_fShutdownTimerSet = 0;
  }
  else if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, 0, -2147418113);
  }
}

```

## disassembly

```asm
0x1800060b0  mov     [rsp+arg_8], rbx
0x1800060b5  push    rdi
0x1800060b6  sub     rsp, 30h
0x1800060ba  mov     rbx, rdx
0x1800060bd  test    rdx, rdx
0x1800060c0  jnz     short loc_180006108
0x1800060c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060c9  lea     rdi, WPP_GLOBAL_Control
0x1800060d0  cmp     rcx, rdi
0x1800060d3  jz      loc_180006246
0x1800060d9  test    byte ptr [rcx+1Ch], 2
0x1800060dd  jz      loc_180006246
0x1800060e3  mov     rcx, [rcx+10h]
0x1800060e7  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x1800060ee  mov     edx, 42h ; 'B'
0x1800060f3  mov     [rsp+38h+var_18], 8000FFFFh
0x1800060fb  xor     r9d, r9d
0x1800060fe  call    WPP_SF_qd
0x180006103  jmp     loc_180006246
0x180006108  mov     r9d, cs:?g_RefCount@@3JA; long g_RefCount
0x18000610f  mov     [rsp+38h+arg_0], rsi
0x180006114  xor     esi, esi
0x180006116  test    r9d, r9d
0x180006119  jg      loc_18000620A
0x18000611f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006126  lea     rdi, WPP_GLOBAL_Control
0x18000612d  cmp     rcx, rdi
0x180006130  jz      short loc_180006150
0x180006132  test    dword ptr [rcx+1Ch], 200h
0x180006139  jz      short loc_180006150
0x18000613b  mov     rcx, [rcx+10h]
0x18000613f  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180006146  mov     edx, 43h ; 'C'
0x18000614b  call    WPP_SF_
0x180006150  lock or cs:qword_18001F2B0, 2
0x180006159  mov     rcx, cs:WPP_GLOBAL_Control
0x180006160  cmp     rcx, rdi
0x180006163  jz      short loc_18000618A
0x180006165  test    dword ptr [rcx+1Ch], 200h
0x18000616c  jz      short loc_18000618A
0x18000616e  mov     rcx, [rcx+10h]
0x180006172  lea     r9, aServiceStopPen; "SERVICE_STOP_PENDING"
0x180006179  mov     edx, 3Fh ; '?'
0x18000617e  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180006185  call    WPP_SF_S
0x18000618a  lea     rdx, [rbx+8]; lpServiceStatus
0x18000618e  mov     [rbx+14h], rsi
0x180006192  mov     dword ptr [rdx], 30h ; '0'
0x180006198  mov     dword ptr [rbx+0Ch], 3
0x18000619f  mov     dword ptr [rbx+1Ch], 3
0x1800061a6  mov     dword ptr [rbx+20h], 2710h
0x1800061ad  mov     [rdx+8], esi
0x1800061b0  mov     rcx, [rbx]; hServiceStatus
0x1800061b3  call    cs:__imp_SetServiceStatus
0x1800061b9  test    eax, eax
0x1800061bb  jnz     short loc_1800061F9
0x1800061bd  call    cs:__imp_GetLastError
0x1800061c3  test    eax, eax
0x1800061c5  jle     short loc_1800061CF
0x1800061c7  movzx   eax, ax
0x1800061ca  or      eax, 80070000h
0x1800061cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061d6  cmp     rcx, rdi
0x1800061d9  jz      short loc_1800061F9
0x1800061db  test    byte ptr [rcx+1Ch], 2
0x1800061df  jz      short loc_1800061F9
0x1800061e1  mov     rcx, [rcx+10h]
0x1800061e5  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x1800061ec  mov     edx, 41h ; 'A'
0x1800061f1  mov     r9d, eax
0x1800061f4  call    WPP_SF_d
0x1800061f9  mov     rcx, [rbx+38h]; hEvent
0x1800061fd  test    rcx, rcx
0x180006200  jz      short loc_18000623B
0x180006202  call    cs:__imp_SetEvent
0x180006208  jmp     short loc_18000623B
0x18000620a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006211  lea     rdi, WPP_GLOBAL_Control
0x180006218  cmp     rcx, rdi
0x18000621b  jz      short loc_18000623B
0x18000621d  test    dword ptr [rcx+1Ch], 200h
0x180006224  jz      short loc_18000623B
0x180006226  mov     rcx, [rcx+10h]
0x18000622a  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180006231  mov     edx, 44h ; 'D'
0x180006236  call    WPP_SF_d
0x18000623b  mov     cs:?g_fShutdownTimerSet@@3HA, esi; int g_fShutdownTimerSet
0x180006241  mov     rsi, [rsp+38h+arg_0]
0x180006246  mov     rbx, [rsp+38h+arg_8]
0x18000624b  add     rsp, 30h
0x18000624f  pop     rdi
0x180006250  retn
```
