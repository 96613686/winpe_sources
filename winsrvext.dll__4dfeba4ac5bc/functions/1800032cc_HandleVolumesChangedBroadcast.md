# HandleVolumesChangedBroadcast

- ea: `0x1800032cc`
- end: `0x18000342f`
- name: `HandleVolumesChangedBroadcast`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002230`

## callees

- `0x1800032cc`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180003305`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180003305`
- `win32u!NtUserSetInformationThread` at `0x18000333b`
- `win32u!NtUserSetInformationThread` at `0x180003402`
- `win32u!NtUserSetInformationThread` at `0x18000333b`
- `win32u!NtUserSetInformationThread` at `0x180003402`
- `USER32!BroadcastSystemMessageW` at `0x180003393`
- `USER32!BroadcastSystemMessageW` at `0x1800033e1`
- `USER32!BroadcastSystemMessageW` at `0x180003393`
- `USER32!BroadcastSystemMessageW` at `0x1800033e1`

## pseudocode

```c
signed int HandleVolumesChangedBroadcast()
{
  signed int result; // eax
  int v1; // ebx
  int v2; // ecx
  int v3; // ecx
  DWORD Info; // [rsp+30h] [rbp-40h] BYREF
  __int128 v5; // [rsp+38h] [rbp-38h] BYREF
  __int64 v6; // [rsp+48h] [rbp-28h]
  LPARAM lParam[2]; // [rsp+50h] [rbp-20h] BYREF
  int v8; // [rsp+60h] [rbp-10h]

  Info = 0;
  v6 = 0;
  v8 = 0;
  v5 = 0;
  *(_OWORD *)lParam = 0;
  result = GetLogicalDrives();
  v1 = result;
  if ( result != gLastLogicalDrives )
  {
    Info = 16;
    result = NtUserSetInformationThread(-2, 7, &v5);
    if ( result >= 0 )
    {
      v2 = gLastLogicalDrives;
      if ( (gLastLogicalDrives & ~v1) != 0 )
      {
        HIDWORD(lParam[1]) = gLastLogicalDrives & ~v1;
        LOWORD(v8) = 0;
        LODWORD(lParam[0]) = 20;
        *(LPARAM *)((char *)lParam + 4) = 2;
        BroadcastSystemMessageW(0x20u, &Info, 0x219u, 0x8004u, (LPARAM)lParam);
        v2 = gLastLogicalDrives;
      }
      v3 = v1 & ~v2;
      if ( v3 )
      {
        HIDWORD(lParam[1]) = v3;
        LOWORD(v8) = 0;
        LODWORD(lParam[0]) = 20;
        *(LPARAM *)((char *)lParam + 4) = 2;
        BroadcastSystemMessageW(0x20u, &Info, 0x219u, 0x8000u, (LPARAM)lParam);
      }
      result = NtUserSetInformationThread(-2, 9, &v5);
      gLastLogicalDrives = v1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800032cc  mov     [rsp-8+arg_0], rbx
0x1800032d1  push    rbp
0x1800032d2  mov     rbp, rsp
0x1800032d5  sub     rsp, 70h
0x1800032d9  mov     rax, cs:__security_cookie
0x1800032e0  xor     rax, rsp
0x1800032e3  mov     [rbp+var_8], rax
0x1800032e7  xor     eax, eax
0x1800032e9  mov     [rbp+Info], 0
0x1800032f0  xorps   xmm0, xmm0
0x1800032f3  mov     [rbp+var_28], rax
0x1800032f7  xorps   xmm1, xmm1
0x1800032fa  mov     [rbp+var_10], eax
0x1800032fd  movups  [rbp+var_38], xmm0
0x180003301  movups  xmmword ptr [rbp+var_20], xmm1
0x180003305  call    cs:__imp_GetLogicalDrives
0x18000330c  nop     dword ptr [rax+rax+00h]
0x180003311  cmp     eax, cs:gLastLogicalDrives
0x180003317  mov     ebx, eax
0x180003319  jz      loc_180003414
0x18000331f  mov     r9d, 18h
0x180003325  mov     [rbp+Info], 10h
0x18000332c  lea     r8, [rbp+var_38]
0x180003330  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180003337  lea     edx, [r9-11h]
0x18000333b  call    cs:__imp_NtUserSetInformationThread
0x180003342  nop     dword ptr [rax+rax+00h]
0x180003347  test    eax, eax
0x180003349  js      loc_180003414
0x18000334f  mov     ecx, cs:gLastLogicalDrives
0x180003355  mov     edx, ebx
0x180003357  not     edx
0x180003359  and     edx, ecx
0x18000335b  jz      short loc_1800033A5
0x18000335d  xor     eax, eax
0x18000335f  mov     dword ptr [rbp+var_20+0Ch], edx
0x180003362  mov     word ptr [rbp+var_10], ax
0x180003366  lea     rdx, [rbp+Info]; lpInfo
0x18000336a  lea     rax, [rbp+var_20]
0x18000336e  mov     dword ptr [rbp+var_20], 14h
0x180003375  mov     r9d, 8004h; wParam
0x18000337b  mov     [rsp+70h+lParam], rax; lParam
0x180003380  mov     r8d, 219h; Msg
0x180003386  mov     [rbp+var_20+4], 2
0x18000338e  mov     ecx, 20h ; ' '; flags
0x180003393  call    cs:__imp_BroadcastSystemMessageW
0x18000339a  nop     dword ptr [rax+rax+00h]
0x18000339f  mov     ecx, cs:gLastLogicalDrives
0x1800033a5  not     ecx
0x1800033a7  and     ecx, ebx
0x1800033a9  jz      short loc_1800033ED
0x1800033ab  xor     eax, eax
0x1800033ad  mov     dword ptr [rbp+var_20+0Ch], ecx
0x1800033b0  mov     word ptr [rbp+var_10], ax
0x1800033b4  lea     rdx, [rbp+Info]; lpInfo
0x1800033b8  lea     rax, [rbp+var_20]
0x1800033bc  mov     dword ptr [rbp+var_20], 14h
0x1800033c3  mov     r9d, 8000h; wParam
0x1800033c9  mov     [rsp+70h+lParam], rax; lParam
0x1800033ce  mov     r8d, 219h; Msg
0x1800033d4  mov     [rbp+var_20+4], 2
0x1800033dc  mov     ecx, 20h ; ' '; flags
0x1800033e1  call    cs:__imp_BroadcastSystemMessageW
0x1800033e8  nop     dword ptr [rax+rax+00h]
0x1800033ed  mov     r9d, 18h
0x1800033f3  lea     r8, [rbp+var_38]
0x1800033f7  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1800033fe  lea     edx, [r9-0Fh]
0x180003402  call    cs:__imp_NtUserSetInformationThread
0x180003409  nop     dword ptr [rax+rax+00h]
0x18000340e  mov     cs:gLastLogicalDrives, ebx
0x180003414  mov     rcx, [rbp+var_8]
0x180003418  xor     rcx, rsp; StackCookie
0x18000341b  call    __security_check_cookie
0x180003420  mov     rbx, [rsp+70h+arg_0]
0x180003428  add     rsp, 70h
0x18000342c  pop     rbp
0x18000342d  retn
```
