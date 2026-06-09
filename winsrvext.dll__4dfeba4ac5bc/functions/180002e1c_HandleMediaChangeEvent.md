# HandleMediaChangeEvent

- ea: `0x180002e1c`
- end: `0x180002f35`
- name: `HandleMediaChangeEvent`
- size: `281`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003650`

## callees

- `0x180002e1c`
- `0x1800138f0`

## import_xrefs

- `win32u!NtUserGetDeviceChangeInfo` at `0x180002f04`
- `win32u!NtUserGetDeviceChangeInfo` at `0x180002f04`
- `win32u!NtUserSetInformationThread` at `0x180002e94`
- `win32u!NtUserSetInformationThread` at `0x180002ef8`
- `win32u!NtUserSetInformationThread` at `0x180002e94`
- `win32u!NtUserSetInformationThread` at `0x180002ef8`
- `USER32!BroadcastSystemMessageW` at `0x180002ed7`
- `USER32!BroadcastSystemMessageW` at `0x180002ed7`

## pseudocode

```c
__int64 HandleMediaChangeEvent()
{
  __int64 result; // rax
  int v1; // ebx
  DWORD Info; // [rsp+30h] [rbp-40h] BYREF
  __int128 v3; // [rsp+38h] [rbp-38h] BYREF
  __int64 v4; // [rsp+48h] [rbp-28h]
  LPARAM lParam[2]; // [rsp+50h] [rbp-20h] BYREF
  int v6; // [rsp+60h] [rbp-10h]

  Info = 0;
  v6 = 0;
  v4 = 0;
  *(_OWORD *)lParam = 0;
  v3 = 0;
  while ( 1 )
  {
    result = NtUserGetDeviceChangeInfo();
    v1 = result;
    if ( !(_DWORD)result )
      break;
    LODWORD(lParam[0]) = 20;
    *(LPARAM *)((char *)lParam + 4) = 2;
    LOWORD(v6) = 1;
    HIDWORD(lParam[1]) = result & 0x7FFFFFFF;
    Info = 16;
    if ( (int)NtUserSetInformationThread(-2, 7, &v3) >= 0 )
    {
      BroadcastSystemMessageW(
        (v1 >> 31) & 0x80 | 0x20,
        &Info,
        0x219u,
        (((__int64)v1 >> 63) & 0xFFFFFFFFFFFFFFFCuLL) + 32772,
        (LPARAM)lParam);
      NtUserSetInformationThread(-2, 9, &v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002e1c  mov     [rsp-8+arg_0], rbx
0x180002e21  push    rbp
0x180002e22  mov     rbp, rsp
0x180002e25  sub     rsp, 70h
0x180002e29  mov     rax, cs:__security_cookie
0x180002e30  xor     rax, rsp
0x180002e33  mov     [rbp+var_8], rax
0x180002e37  xor     eax, eax
0x180002e39  mov     [rbp+Info], 0
0x180002e40  xorps   xmm0, xmm0
0x180002e43  mov     [rbp+var_10], eax
0x180002e46  xorps   xmm1, xmm1
0x180002e49  mov     [rbp+var_28], rax
0x180002e4d  movups  xmmword ptr [rbp+var_20], xmm0
0x180002e51  movups  [rbp+var_38], xmm1
0x180002e55  jmp     loc_180002F04
0x180002e5a  mov     eax, 1
0x180002e5f  mov     dword ptr [rbp+var_20], 14h
0x180002e66  mov     ecx, ebx
0x180002e68  mov     [rbp+var_20+4], 2
0x180002e70  btr     ecx, 1Fh
0x180002e74  mov     word ptr [rbp+var_10], ax
0x180002e78  mov     dword ptr [rbp+var_20+0Ch], ecx
0x180002e7b  lea     r8, [rbp+var_38]
0x180002e7f  lea     r9d, [rax+17h]
0x180002e83  mov     [rbp+Info], 10h
0x180002e8a  lea     edx, [rax+6]
0x180002e8d  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180002e94  call    cs:__imp_NtUserSetInformationThread
0x180002e9b  nop     dword ptr [rax+rax+00h]
0x180002ea0  test    eax, eax
0x180002ea2  js      short loc_180002F04
0x180002ea4  movsxd  r9, ebx
0x180002ea7  lea     rax, [rbp+var_20]
0x180002eab  sar     r9, 3Fh
0x180002eaf  lea     rdx, [rbp+Info]; lpInfo
0x180002eb3  sar     ebx, 1Fh
0x180002eb6  and     r9, 0FFFFFFFFFFFFFFFCh
0x180002eba  and     ebx, 80h
0x180002ec0  mov     [rsp+70h+lParam], rax; lParam
0x180002ec5  or      ebx, 20h
0x180002ec8  add     r9, 8004h; wParam
0x180002ecf  mov     ecx, ebx; flags
0x180002ed1  mov     r8d, 219h; Msg
0x180002ed7  call    cs:__imp_BroadcastSystemMessageW
0x180002ede  nop     dword ptr [rax+rax+00h]
0x180002ee3  mov     r9d, 18h
0x180002ee9  lea     r8, [rbp+var_38]
0x180002eed  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180002ef4  lea     edx, [r9-0Fh]
0x180002ef8  call    cs:__imp_NtUserSetInformationThread
0x180002eff  nop     dword ptr [rax+rax+00h]
0x180002f04  call    cs:__imp_NtUserGetDeviceChangeInfo
0x180002f0b  nop     dword ptr [rax+rax+00h]
0x180002f10  mov     ebx, eax
0x180002f12  test    eax, eax
0x180002f14  jnz     loc_180002E5A
0x180002f1a  mov     rcx, [rbp+var_8]
0x180002f1e  xor     rcx, rsp; StackCookie
0x180002f21  call    __security_check_cookie
0x180002f26  mov     rbx, [rsp+70h+arg_0]
0x180002f2e  add     rsp, 70h
0x180002f32  pop     rbp
0x180002f33  retn
```
