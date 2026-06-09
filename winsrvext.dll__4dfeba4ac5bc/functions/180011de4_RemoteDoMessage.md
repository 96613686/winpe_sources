# RemoteDoMessage

- ea: `0x180011de4`
- end: `0x1800120b4`
- name: `RemoteDoMessage`
- size: `720`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010410`

## callees

- `0x180011de4`
- `0x180012b48`
- `0x1800138ad`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180011e0d`
- `KERNELBASE!LocalAlloc` at `0x180011eaa`
- `KERNELBASE!LocalAlloc` at `0x180011ede`
- `KERNELBASE!LocalAlloc` at `0x180011e0d`
- `KERNELBASE!LocalAlloc` at `0x180011eaa`
- `KERNELBASE!LocalAlloc` at `0x180011ede`
- `ntdll!NtSetEvent` at `0x18001208e`
- `ntdll!NtSetEvent` at `0x18001208e`
- `ntdll!RtlLeaveCriticalSection` at `0x180011fd9`
- `ntdll!RtlLeaveCriticalSection` at `0x180011fd9`
- `ntdll!NtResumeThread` at `0x180012070`
- `ntdll!NtResumeThread` at `0x180012070`
- `ntdll!RtlCreateUserThread` at `0x18001203c`
- `ntdll!RtlCreateUserThread` at `0x18001203c`
- `ntdll!RtlEnterCriticalSection` at `0x180011efe`
- `ntdll!RtlEnterCriticalSection` at `0x180011efe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e5e`
- `CSRSRV!CsrAddStaticServerThread` at `0x18001205b`
- `CSRSRV!CsrAddStaticServerThread` at `0x18001205b`

## pseudocode

```c
__int64 __fastcall RemoteDoMessage(__int64 a1)
{
  _OWORD *v2; // rbx
  unsigned int v3; // ecx
  HLOCAL *v4; // rsi
  void *v5; // rcx
  HLOCAL v7; // rax
  unsigned int v8; // eax
  HLOCAL v9; // rax
  _WORD *v10; // rdx
  void *v11; // r8
  NTSTATUS v12; // eax
  unsigned int v13; // ecx
  _OWORD Reserved8[3]; // [rsp+50h] [rbp-38h] BYREF

  Reserved8[0] = 0;
  if ( PendingMessages == 25 )
    return 3221225473LL;
  v2 = LocalAlloc(0x40u, 0x60u);
  if ( !v2 )
  {
LABEL_10:
    if ( !*(_BYTE *)(a1 + 16472) )
      ReplyMessageToTerminalServer(
        3221225495LL,
        *(_QWORD *)(a1 + 16480),
        0,
        *(_QWORD *)(a1 + 16464),
        *(_QWORD *)(a1 + 16488));
    return 3221225495LL;
  }
  v3 = *(_DWORD *)(a1 + 8248);
  if ( v3 + 2 < v3 )
  {
    v4 = (HLOCAL *)v2 + 3;
LABEL_5:
    v5 = (void *)*((_QWORD *)v2 + 4);
    if ( v5 )
      LocalFree(v5);
    if ( *v4 )
      LocalFree(*v4);
    LocalFree(v2);
    goto LABEL_10;
  }
  v7 = LocalAlloc(0x40u, v3 + 2);
  v4 = (HLOCAL *)v2 + 3;
  *((_QWORD *)v2 + 3) = v7;
  if ( !v7 )
    goto LABEL_5;
  v8 = *(_DWORD *)(a1 + 16444);
  if ( v8 + 2 < v8 )
    goto LABEL_5;
  v9 = LocalAlloc(0x40u, v8 + 2);
  *((_QWORD *)v2 + 4) = v9;
  if ( !v9 )
    goto LABEL_5;
  RtlEnterCriticalSection(&gcsUserSrv);
  v10 = *v4;
  ++PendingMessages;
  *((_BYTE *)v2 + 81) = 1;
  *v2 = *(_OWORD *)(a1 + 8);
  *((_DWORD *)v2 + 4) = *(_DWORD *)(a1 + 24);
  *((_DWORD *)v2 + 5) = *(_DWORD *)(a1 + 40);
  *((_DWORD *)v2 + 11) = *(_DWORD *)(a1 + 16452);
  *((_QWORD *)v2 + 8) = *(_QWORD *)(a1 + 16480);
  *((_QWORD *)v2 + 7) = *(_QWORD *)(a1 + 16464);
  *((_QWORD *)v2 + 9) = *(_QWORD *)(a1 + 16488);
  *((_BYTE *)v2 + 80) = *(_BYTE *)(a1 + 16472);
  *((_DWORD *)v2 + 10) = *(_DWORD *)(a1 + 16448);
  *((_BYTE *)v2 + 82) = *(_BYTE *)(a1 + 16473);
  v10[(unsigned __int64)*(unsigned int *)(a1 + 8248) >> 1] = 0;
  memcpy_0(*v4, (const void *)(a1 + 56), *(unsigned int *)(a1 + 8248));
  *(_WORD *)(*((_QWORD *)v2 + 4) + 2 * ((unsigned __int64)*(unsigned int *)(a1 + 16444) >> 1)) = 0;
  memcpy_0(*((void **)v2 + 4), (const void *)(a1 + 8252), *(unsigned int *)(a1 + 16444));
  *((_QWORD *)v2 + 11) = gpchiList;
  gpchiList = (__int64)v2;
  RtlLeaveCriticalSection(&gcsUserSrv);
  if ( !ThreadHandle )
  {
    LOBYTE(v11) = 1;
    if ( RtlCreateUserThread(
           (PVOID)0xFFFFFFFFFFFFFFFFLL,
           0,
           v11,
           0,
           0,
           0,
           RemoteMessageThread,
           0,
           &ThreadHandle,
           Reserved8) >= 0 )
    {
      CsrAddStaticServerThread(ThreadHandle, Reserved8, 0);
      NtResumeThread(ThreadHandle, 0);
    }
    return 0;
  }
  if ( !g_hDoMessageEvent )
    return 3221225473LL;
  v12 = NtSetEvent(g_hDoMessageEvent, 0);
  v13 = 0;
  if ( v12 < 0 )
    return (unsigned int)v12;
  return v13;
}

```

## disassembly

```asm
0x180011de4  push    rbx
0x180011de6  push    rbp
0x180011de7  push    rsi
0x180011de8  push    rdi
0x180011de9  sub     rsp, 68h
0x180011ded  cmp     cs:PendingMessages, 19h
0x180011df4  xorps   xmm0, xmm0
0x180011df7  movups  [rsp+88h+var_38], xmm0
0x180011dfc  mov     rbp, rcx
0x180011dff  jz      loc_1800120A5
0x180011e05  mov     edx, 60h ; '`'; uBytes
0x180011e0a  lea     ecx, [rdx-20h]; uFlags
0x180011e0d  call    cs:__imp_LocalAlloc
0x180011e14  nop     dword ptr [rax+rax+00h]
0x180011e19  mov     rbx, rax
0x180011e1c  test    rax, rax
0x180011e1f  jz      short loc_180011E6A
0x180011e21  mov     ecx, [rbp+2038h]
0x180011e27  lea     eax, [rcx+2]
0x180011e2a  cmp     eax, ecx
0x180011e2c  jnb     short loc_180011EA3
0x180011e2e  lea     rsi, [rbx+18h]
0x180011e32  mov     rcx, [rbx+20h]; hMem
0x180011e36  test    rcx, rcx
0x180011e39  jz      short loc_180011E47
0x180011e3b  call    cs:__imp_LocalFree
0x180011e42  nop     dword ptr [rax+rax+00h]
0x180011e47  mov     rcx, [rsi]; hMem
0x180011e4a  test    rcx, rcx
0x180011e4d  jz      short loc_180011E5B
0x180011e4f  call    cs:__imp_LocalFree
0x180011e56  nop     dword ptr [rax+rax+00h]
0x180011e5b  mov     rcx, rbx; hMem
0x180011e5e  call    cs:__imp_LocalFree
0x180011e65  nop     dword ptr [rax+rax+00h]
0x180011e6a  cmp     byte ptr [rbp+4058h], 0
0x180011e71  mov     ebx, 0C0000017h
0x180011e76  jnz     short loc_180011E9C
0x180011e78  mov     rcx, [rbp+4068h]
0x180011e7f  xor     r8d, r8d
0x180011e82  mov     r9, [rbp+4050h]
0x180011e89  mov     rdx, [rbp+4060h]
0x180011e90  mov     [rsp+88h+Reserved3], rcx
0x180011e95  mov     ecx, ebx
0x180011e97  call    ReplyMessageToTerminalServer
0x180011e9c  mov     eax, ebx
0x180011e9e  jmp     loc_1800120AA
0x180011ea3  mov     edx, eax; uBytes
0x180011ea5  mov     ecx, 40h ; '@'; uFlags
0x180011eaa  call    cs:__imp_LocalAlloc
0x180011eb1  nop     dword ptr [rax+rax+00h]
0x180011eb6  lea     rsi, [rbx+18h]
0x180011eba  mov     [rsi], rax
0x180011ebd  test    rax, rax
0x180011ec0  jz      loc_180011E32
0x180011ec6  mov     eax, [rbp+403Ch]
0x180011ecc  lea     ecx, [rax+2]
0x180011ecf  cmp     ecx, eax
0x180011ed1  jb      loc_180011E32
0x180011ed7  mov     edx, ecx; uBytes
0x180011ed9  mov     ecx, 40h ; '@'; uFlags
0x180011ede  call    cs:__imp_LocalAlloc
0x180011ee5  nop     dword ptr [rax+rax+00h]
0x180011eea  mov     [rbx+20h], rax
0x180011eee  test    rax, rax
0x180011ef1  jz      loc_180011E32
0x180011ef7  lea     rcx, gcsUserSrv; CriticalSection
0x180011efe  call    cs:__imp_RtlEnterCriticalSection
0x180011f05  nop     dword ptr [rax+rax+00h]
0x180011f0a  mov     rdx, [rsi]
0x180011f0d  inc     cs:PendingMessages
0x180011f13  mov     byte ptr [rbx+51h], 1
0x180011f17  movups  xmm0, xmmword ptr [rbp+8]
0x180011f1b  movdqu  xmmword ptr [rbx], xmm0
0x180011f1f  mov     eax, [rbp+18h]
0x180011f22  mov     [rbx+10h], eax
0x180011f25  mov     eax, [rbp+28h]
0x180011f28  mov     [rbx+14h], eax
0x180011f2b  mov     eax, [rbp+4044h]
0x180011f31  mov     [rbx+2Ch], eax
0x180011f34  mov     rax, [rbp+4060h]
0x180011f3b  mov     [rbx+40h], rax
0x180011f3f  mov     rax, [rbp+4050h]
0x180011f46  mov     [rbx+38h], rax
0x180011f4a  mov     rax, [rbp+4068h]
0x180011f51  mov     [rbx+48h], rax
0x180011f55  mov     al, [rbp+4058h]
0x180011f5b  mov     [rbx+50h], al
0x180011f5e  mov     eax, [rbp+4040h]
0x180011f64  mov     [rbx+28h], eax
0x180011f67  mov     al, [rbp+4059h]
0x180011f6d  mov     [rbx+52h], al
0x180011f70  xor     eax, eax
0x180011f72  mov     r8d, [rbp+2038h]
0x180011f79  shr     r8, 1
0x180011f7c  mov     [rdx+r8*2], ax
0x180011f81  lea     rdx, [rbp+38h]; Src
0x180011f85  mov     r8d, [rbp+2038h]; Size
0x180011f8c  mov     rcx, [rsi]; void *
0x180011f8f  call    memcpy_0
0x180011f94  mov     r8d, [rbp+403Ch]
0x180011f9b  xor     eax, eax
0x180011f9d  mov     rdx, [rbx+20h]
0x180011fa1  shr     r8, 1
0x180011fa4  mov     [rdx+r8*2], ax
0x180011fa9  lea     rdx, [rbp+203Ch]; Src
0x180011fb0  mov     r8d, [rbp+403Ch]; Size
0x180011fb7  mov     rcx, [rbx+20h]; void *
0x180011fbb  call    memcpy_0
0x180011fc0  mov     rax, cs:gpchiList
0x180011fc7  lea     rcx, gcsUserSrv; CriticalSection
0x180011fce  mov     [rbx+58h], rax
0x180011fd2  mov     cs:gpchiList, rbx
0x180011fd9  call    cs:__imp_RtlLeaveCriticalSection
0x180011fe0  nop     dword ptr [rax+rax+00h]
0x180011fe5  cmp     cs:ThreadHandle, 0
0x180011fed  jnz     loc_180012080
0x180011ff3  lea     rax, [rsp+88h+var_38]
0x180011ff8  xor     r9d, r9d; Reserved2
0x180011ffb  mov     [rsp+88h+Reserved8], rax; Reserved8
0x180012000  mov     r8b, 1; Reserved1
0x180012003  lea     rax, ThreadHandle
0x18001200a  xor     edx, edx; OutThreadHandle
0x18001200c  mov     [rsp+88h+Reserved7], rax; Reserved7
0x180012011  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180012015  mov     [rsp+88h+Reserved6], 0; Reserved6
0x18001201e  lea     rax, RemoteMessageThread
0x180012025  mov     [rsp+88h+Reserved5], rax; Reserved5
0x18001202a  mov     [rsp+88h+Reserved4], 0; Reserved4
0x180012033  mov     [rsp+88h+Reserved3], 0; Reserved3
0x18001203c  call    cs:__imp_RtlCreateUserThread
0x180012043  nop     dword ptr [rax+rax+00h]
0x180012048  test    eax, eax
0x18001204a  js      short loc_18001207C
0x18001204c  mov     rcx, cs:ThreadHandle
0x180012053  lea     rdx, [rsp+88h+var_38]
0x180012058  xor     r8d, r8d
0x18001205b  call    cs:__imp_CsrAddStaticServerThread
0x180012062  nop     dword ptr [rax+rax+00h]
0x180012067  mov     rcx, cs:ThreadHandle; ThreadHandle
0x18001206e  xor     edx, edx; SuspendCount
0x180012070  call    cs:__imp_NtResumeThread
0x180012077  nop     dword ptr [rax+rax+00h]
0x18001207c  xor     eax, eax
0x18001207e  jmp     short loc_1800120AA
0x180012080  mov     rcx, cs:g_hDoMessageEvent; EventHandle
0x180012087  test    rcx, rcx
0x18001208a  jz      short loc_1800120A5
0x18001208c  xor     edx, edx; PreviousState
0x18001208e  call    cs:__imp_NtSetEvent
0x180012095  nop     dword ptr [rax+rax+00h]
0x18001209a  xor     ecx, ecx
0x18001209c  test    eax, eax
0x18001209e  cmovs   ecx, eax
0x1800120a1  mov     eax, ecx
0x1800120a3  jmp     short loc_1800120AA
0x1800120a5  mov     eax, 0C0000001h
0x1800120aa  add     rsp, 68h
0x1800120ae  pop     rdi
0x1800120af  pop     rsi
0x1800120b0  pop     rbp
0x1800120b1  pop     rbx
0x1800120b2  retn
```
