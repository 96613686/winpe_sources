# TetheringService::StopSharingAsync(TetheringService::StopReason)

- ea: `0x18001ff08`
- end: `0x18002001d`
- name: `?StopSharingAsync@TetheringService@@AEAAJW4StopReason@1@@Z`
- size: `277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180015bf0`
- `0x180016cd0`
- `0x180018f64`
- `0x180019170`
- `0x180019284`
- `0x18001a300`
- `0x18001a800`
- `0x18001acb4`
- `0x18001fe44`

## callees

- `0x18000299c`
- `0x18000bf74`
- `0x18001ff08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffb3`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001ffa9`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001ffa9`

## pseudocode

```c
__int64 __fastcall TetheringService::StopSharingAsync(__int64 a1, unsigned int a2)
{
  _DWORD *v4; // rax
  TetheringServiceTelemetry *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, a2);
  }
  v4 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -2147024882;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
      return v6;
    }
    v7 = 166;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v5 + 2), v7, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v6);
    return v6;
  }
  *v4 = a2;
  if ( !TrySubmitThreadpoolCallback(TetheringService::StopSharingWorkerProc, v4, (PTP_CALLBACK_ENVIRON)(a1 + 1808)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
      return v6;
    }
    v7 = 167;
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ff08  mov     [rsp+arg_0], rbx
0x18001ff0d  mov     [rsp+arg_8], rbp
0x18001ff12  push    rdi
0x18001ff13  sub     rsp, 20h
0x18001ff17  mov     ebx, edx
0x18001ff19  mov     rdi, rcx
0x18001ff1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff23  lea     rbp, WPP_GLOBAL_Control
0x18001ff2a  cmp     rcx, rbp
0x18001ff2d  jz      short loc_18001FF4D
0x18001ff2f  test    byte ptr [rcx+1Ch], 8
0x18001ff33  jz      short loc_18001FF4D
0x18001ff35  mov     rcx, [rcx+10h]
0x18001ff39  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001ff40  mov     edx, 0A5h
0x18001ff45  mov     r9d, ebx
0x18001ff48  call    WPP_SF_d
0x18001ff4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ff54  mov     ecx, 4; unsigned __int64
0x18001ff59  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ff5e  test    rax, rax
0x18001ff61  jnz     short loc_18001FF96
0x18001ff63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff6a  mov     ebx, 8007000Eh
0x18001ff6f  cmp     rcx, rbp
0x18001ff72  jz      short loc_18001FF92
0x18001ff74  test    byte ptr [rcx+1Ch], 8
0x18001ff78  jz      short loc_18001FF92
0x18001ff7a  mov     edx, 0A6h
0x18001ff7f  mov     rcx, [rcx+10h]
0x18001ff83  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001ff8a  mov     r9d, ebx
0x18001ff8d  call    WPP_SF_d
0x18001ff92  mov     eax, ebx
0x18001ff94  jmp     short loc_18002000D
0x18001ff96  lea     r8, [rdi+710h]; pcbe
0x18001ff9d  mov     [rax], ebx
0x18001ff9f  mov     rdx, rax; pv
0x18001ffa2  lea     rcx, ?StopSharingWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001ffa9  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001ffaf  test    eax, eax
0x18001ffb1  jnz     short loc_18001FFE1
0x18001ffb3  call    cs:__imp_GetLastError
0x18001ffb9  mov     ebx, eax
0x18001ffbb  test    eax, eax
0x18001ffbd  jle     short loc_18001FFC8
0x18001ffbf  movzx   ebx, ax
0x18001ffc2  or      ebx, 80070000h
0x18001ffc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffcf  cmp     rcx, rbp
0x18001ffd2  jz      short loc_18001FF92
0x18001ffd4  test    byte ptr [rcx+1Ch], 8
0x18001ffd8  jz      short loc_18001FF92
0x18001ffda  mov     edx, 0A7h
0x18001ffdf  jmp     short loc_18001FF7F
0x18001ffe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffe8  cmp     rcx, rbp
0x18001ffeb  jz      short loc_18002000B
0x18001ffed  test    byte ptr [rcx+1Ch], 8
0x18001fff1  jz      short loc_18002000B
0x18001fff3  mov     rcx, [rcx+10h]
0x18001fff7  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001fffe  mov     edx, 0A8h
0x180020003  xor     r9d, r9d
0x180020006  call    WPP_SF_d
0x18002000b  xor     eax, eax
0x18002000d  mov     rbx, [rsp+28h+arg_0]
0x180020012  mov     rbp, [rsp+28h+arg_8]
0x180020017  add     rsp, 20h
0x18002001b  pop     rdi
0x18002001c  retn
```
