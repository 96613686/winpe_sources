# HandleRemoteNetDeviceChangeEvent

- ea: `0x180003128`
- end: `0x1800032c5`
- name: `HandleRemoteNetDeviceChangeEvent`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003650`

## callees

- `0x180003128`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800031b3`
- `ntdll!NtQueryInformationProcess` at `0x1800031b3`
- `win32u!NtUserSetInformationThread` at `0x180003173`
- `win32u!NtUserSetInformationThread` at `0x180003297`
- `win32u!NtUserSetInformationThread` at `0x180003173`
- `win32u!NtUserSetInformationThread` at `0x180003297`
- `USER32!BroadcastSystemMessageW` at `0x18000322b`
- `USER32!BroadcastSystemMessageW` at `0x18000326b`
- `USER32!BroadcastSystemMessageW` at `0x18000322b`
- `USER32!BroadcastSystemMessageW` at `0x18000326b`

## pseudocode

```c
__int64 HandleRemoteNetDeviceChangeEvent()
{
  __int64 result; // rax
  int v1; // ebx
  unsigned int i; // ecx
  int v3; // ecx
  DWORD Info; // [rsp+30h] [rbp-19h] BYREF
  __int128 v5; // [rsp+38h] [rbp-11h] BYREF
  __int64 v6; // [rsp+48h] [rbp-1h]
  _OWORD ProcessInformation[2]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v8; // [rsp+70h] [rbp+27h]
  LPARAM lParam[2]; // [rsp+78h] [rbp+2Fh] BYREF
  int v10; // [rsp+88h] [rbp+3Fh]

  v10 = 0;
  v6 = 0;
  *(_OWORD *)lParam = 0;
  v5 = 0;
  result = NtUserSetInformationThread(-2, 7, &v5);
  if ( (int)result >= 0 )
  {
    while ( 1 )
    {
      v1 = 0;
      v8 = 0;
      memset(ProcessInformation, 0, sizeof(ProcessInformation));
      if ( NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessDeviceMap, ProcessInformation, 0x24u, 0) >= 0 )
      {
        for ( i = 2; i < 0x1A; ++i )
        {
          if ( *((_BYTE *)ProcessInformation + i + 4) == 4 )
            v1 |= 1 << i;
        }
      }
      v3 = LastNetDrives;
      if ( v1 == LastNetDrives )
        break;
      LODWORD(lParam[0]) = 20;
      *(LPARAM *)((char *)lParam + 4) = 2;
      LOWORD(v10) = 2;
      HIDWORD(lParam[1]) = LastNetDrives & ~v1;
      if ( HIDWORD(lParam[1]) )
      {
        Info = 24;
        BroadcastSystemMessageW(0x68u, &Info, 0x219u, 0x8004u, (LPARAM)lParam);
        v3 = LastNetDrives;
      }
      HIDWORD(lParam[1]) = v1 & ~v3;
      if ( HIDWORD(lParam[1]) )
      {
        Info = 24;
        BroadcastSystemMessageW(0x68u, &Info, 0x219u, 0x8000u, (LPARAM)lParam);
      }
      LastNetDrives = v1;
    }
    return NtUserSetInformationThread(-2, 9, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x180003128  mov     [rsp-8+arg_0], rbx
0x18000312d  mov     [rsp-8+arg_8], rsi
0x180003132  push    rbp
0x180003133  lea     rbp, [rsp-57h]
0x180003138  sub     rsp, 0A0h
0x18000313f  mov     rax, cs:__security_cookie
0x180003146  xor     rax, rsp
0x180003149  mov     [rbp+57h+var_10], rax
0x18000314d  xor     eax, eax
0x18000314f  lea     r8, [rbp+57h+var_68]
0x180003153  xorps   xmm0, xmm0
0x180003156  mov     [rbp+57h+var_18], eax
0x180003159  xorps   xmm1, xmm1
0x18000315c  mov     [rbp+57h+var_58], rax
0x180003160  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x180003164  lea     r9d, [rax+18h]
0x180003168  lea     edx, [rax+7]
0x18000316b  lea     rcx, [rax-2]
0x18000316f  movups  [rbp+57h+var_68], xmm1
0x180003173  call    cs:__imp_NtUserSetInformationThread
0x18000317a  nop     dword ptr [rax+rax+00h]
0x18000317f  test    eax, eax
0x180003181  js      loc_1800032A3
0x180003187  mov     esi, 2
0x18000318c  xorps   xmm0, xmm0
0x18000318f  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x180003193  xor     eax, eax
0x180003195  xor     ebx, ebx
0x180003197  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000319b  mov     [rbp+57h+var_30], rax
0x18000319f  movups  [rbp+57h+ProcessInformation], xmm0
0x1800031a3  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1800031a8  lea     r9d, [rbx+24h]; ProcessInformationLength
0x1800031ac  lea     edx, [rbx+17h]; ProcessInformationClass
0x1800031af  movups  [rbp+57h+var_40], xmm0
0x1800031b3  call    cs:__imp_NtQueryInformationProcess
0x1800031ba  nop     dword ptr [rax+rax+00h]
0x1800031bf  test    eax, eax
0x1800031c1  js      short loc_1800031DE
0x1800031c3  mov     ecx, esi
0x1800031c5  mov     eax, ecx
0x1800031c7  cmp     byte ptr [rbp+rax+57h+ProcessInformation+4], 4
0x1800031cc  jnz     short loc_1800031D7
0x1800031ce  mov     eax, 1
0x1800031d3  shl     eax, cl
0x1800031d5  or      ebx, eax
0x1800031d7  inc     ecx
0x1800031d9  cmp     ecx, 1Ah
0x1800031dc  jb      short loc_1800031C5
0x1800031de  mov     ecx, cs:LastNetDrives
0x1800031e4  cmp     ebx, ecx
0x1800031e6  jz      loc_180003282
0x1800031ec  mov     eax, ebx
0x1800031ee  mov     dword ptr [rbp+57h+lParam], 14h
0x1800031f5  not     eax
0x1800031f7  mov     [rbp+57h+lParam+4], rsi
0x1800031fb  and     eax, ecx
0x1800031fd  mov     word ptr [rbp+57h+var_18], si
0x180003201  mov     dword ptr [rbp+57h+lParam+0Ch], eax
0x180003204  jz      short loc_18000323D
0x180003206  lea     rax, [rbp+57h+lParam]
0x18000320a  mov     [rbp+57h+Info], 18h
0x180003211  mov     r9d, 8004h; wParam
0x180003217  mov     [rsp+0A0h+ReturnLength], rax; lParam
0x18000321c  mov     r8d, 219h; Msg
0x180003222  lea     rdx, [rbp+57h+Info]; lpInfo
0x180003226  mov     ecx, 68h ; 'h'; flags
0x18000322b  call    cs:__imp_BroadcastSystemMessageW
0x180003232  nop     dword ptr [rax+rax+00h]
0x180003237  mov     ecx, cs:LastNetDrives
0x18000323d  not     ecx
0x18000323f  and     ecx, ebx
0x180003241  mov     dword ptr [rbp+57h+lParam+0Ch], ecx
0x180003244  jz      short loc_180003277
0x180003246  lea     rax, [rbp+57h+lParam]
0x18000324a  mov     [rbp+57h+Info], 18h
0x180003251  mov     r9d, 8000h; wParam
0x180003257  mov     [rsp+0A0h+ReturnLength], rax; lParam
0x18000325c  mov     r8d, 219h; Msg
0x180003262  lea     rdx, [rbp+57h+Info]; lpInfo
0x180003266  mov     ecx, 68h ; 'h'; flags
0x18000326b  call    cs:__imp_BroadcastSystemMessageW
0x180003272  nop     dword ptr [rax+rax+00h]
0x180003277  mov     cs:LastNetDrives, ebx
0x18000327d  jmp     loc_18000318C
0x180003282  mov     r9d, 18h
0x180003288  lea     r8, [rbp+57h+var_68]
0x18000328c  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180003293  lea     edx, [r9-0Fh]
0x180003297  call    cs:__imp_NtUserSetInformationThread
0x18000329e  nop     dword ptr [rax+rax+00h]
0x1800032a3  mov     rcx, [rbp+57h+var_10]
0x1800032a7  xor     rcx, rsp; StackCookie
0x1800032aa  call    __security_check_cookie
0x1800032af  lea     r11, [rsp+0A0h+var_s0]
0x1800032b7  mov     rbx, [r11+10h]
0x1800032bb  mov     rsi, [r11+18h]
0x1800032bf  mov     rsp, r11
0x1800032c2  pop     rbp
0x1800032c3  retn
```
