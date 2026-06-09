# CServerVCChannel::CreateDynamicChannel_WTSAPI(char const *,ulong,__MIDL___MIDL_itf_tscaddon_0000_0007_0001,int)

- ea: `0x18002d0e0`
- end: `0x18002d142`
- name: `?CreateDynamicChannel_WTSAPI@CServerVCChannel@@QEAAJPEBDKW4__MIDL___MIDL_itf_tscaddon_0000_0007_0001@@H@Z`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005694`

## callees

- `0x18002d0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d115`
- `WINSTA!WinStationVirtualOpenEx` at `0x18002d10a`
- `WINSTA!WinStationVirtualOpenEx` at `0x18002d10a`

## pseudocode

```c
signed int __fastcall CServerVCChannel::CreateDynamicChannel_WTSAPI(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5)
{
  __int64 v6; // rax
  signed int result; // eax

  v6 = WinStationVirtualOpenEx(0, a3, a2, (2 * a4) | (a5 != 0 ? 9 : 1));
  if ( v6 )
  {
    *(_QWORD *)(a1 + 344) = v6;
    result = 0;
    *(_DWORD *)(a1 + 360) = 1;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002d0e0  push    rbx
0x18002d0e2  sub     rsp, 20h
0x18002d0e6  neg     [rsp+28h+arg_20]
0x18002d0ea  mov     eax, r9d
0x18002d0ed  mov     r10d, r8d
0x18002d0f0  mov     rbx, rcx
0x18002d0f3  sbb     r9d, r9d
0x18002d0f6  mov     r8, rdx
0x18002d0f9  and     r9d, 8
0x18002d0fd  add     eax, eax
0x18002d0ff  inc     r9d
0x18002d102  mov     edx, r10d
0x18002d105  or      r9d, eax
0x18002d108  xor     ecx, ecx
0x18002d10a  call    cs:__imp_WinStationVirtualOpenEx
0x18002d110  test    rax, rax
0x18002d113  jnz     short loc_18002D129
0x18002d115  call    cs:__imp_GetLastError
0x18002d11b  test    eax, eax
0x18002d11d  jle     short loc_18002D13C
0x18002d11f  movzx   eax, ax
0x18002d122  or      eax, 80070000h
0x18002d127  jmp     short loc_18002D13C
0x18002d129  mov     [rbx+158h], rax
0x18002d130  xor     eax, eax
0x18002d132  mov     dword ptr [rbx+168h], 1
0x18002d13c  add     rsp, 20h
0x18002d140  pop     rbx
0x18002d141  retn
```
