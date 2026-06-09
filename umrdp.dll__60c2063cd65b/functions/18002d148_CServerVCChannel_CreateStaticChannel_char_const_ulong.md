# CServerVCChannel::CreateStaticChannel(char const *,ulong)

- ea: `0x18002d148`
- end: `0x18002d267`
- name: `?CreateStaticChannel@CServerVCChannel@@QEAAJPEBDK@Z`
- size: `287`
- prototype: `int(CServerVCChannel *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005694`

## callees

- `0x18000b8f8`
- `0x18000f79c`
- `0x18002d148`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d208`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x18002d1fe`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x18002d1fe`
- `WTSAPI32!WTSVirtualChannelOpen` at `0x18002d15e`
- `WTSAPI32!WTSVirtualChannelOpen` at `0x18002d15e`
- `WTSAPI32!WTSFreeMemory` at `0x18002d257`
- `WTSAPI32!WTSFreeMemory` at `0x18002d257`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::CreateStaticChannel(CHAR *this, const char *a2, DWORD a3)
{
  HANDLE v4; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  PVOID ppBuffer; // [rsp+40h] [rbp+8h] BYREF
  const char *pBytesReturned; // [rsp+48h] [rbp+10h] BYREF

  pBytesReturned = a2;
  v4 = WTSVirtualChannelOpen(0, a3, this + 80);
  *((_QWORD *)this + 44) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 18;
    goto LABEL_6;
  }
  LODWORD(pBytesReturned) = 0;
  ppBuffer = 0;
  if ( WTSVirtualChannelQuery(v4, WTSVirtualFileHandle, &ppBuffer, (DWORD *)&pBytesReturned) )
  {
    v8 = ppBuffer;
    *((_DWORD *)this + 90) = 1;
    *((_QWORD *)this + 43) = *v8;
    WTSFreeMemory(v8);
    return 0;
  }
  LastError = GetLastError();
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 19;
LABEL_6:
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v7,
      WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
LABEL_7:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002d148  mov     [rsp+pBytesReturned], rdx
0x18002d14d  push    rbx
0x18002d14e  sub     rsp, 30h
0x18002d152  mov     edx, r8d; SessionId
0x18002d155  mov     rbx, rcx
0x18002d158  lea     r8, [rcx+50h]; pVirtualName
0x18002d15c  xor     ecx, ecx; hServer
0x18002d15e  call    cs:__imp_WTSVirtualChannelOpen
0x18002d164  mov     [rbx+160h], rax
0x18002d16b  test    rax, rax
0x18002d16e  jnz     short loc_18002D1DB
0x18002d170  call    cs:__imp_GetLastError
0x18002d176  mov     ebx, eax
0x18002d178  mov     rax, cs:WPP_GLOBAL_Control
0x18002d17f  lea     rcx, WPP_GLOBAL_Control
0x18002d186  cmp     rax, rcx
0x18002d189  jz      short loc_18002D1BF
0x18002d18b  test    byte ptr [rax+1Ch], 8
0x18002d18f  jz      short loc_18002D1BF
0x18002d191  cmp     byte ptr [rax+19h], 2
0x18002d195  jb      short loc_18002D1BF
0x18002d197  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d19c  mov     edx, 12h
0x18002d1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1a8  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18002d1af  mov     r9d, eax
0x18002d1b2  mov     [rsp+38h+var_18], ebx
0x18002d1b6  mov     rcx, [rcx+10h]
0x18002d1ba  call    WPP_SF_Dd
0x18002d1bf  test    ebx, ebx
0x18002d1c1  jle     short loc_18002D1CC
0x18002d1c3  movzx   ebx, bx
0x18002d1c6  or      ebx, 80070000h
0x18002d1cc  test    ebx, ebx
0x18002d1ce  mov     eax, 80004005h
0x18002d1d3  cmovns  ebx, eax
0x18002d1d6  jmp     loc_18002D25F
0x18002d1db  lea     r9, [rsp+38h+pBytesReturned]; pBytesReturned
0x18002d1e0  mov     dword ptr [rsp+38h+pBytesReturned], 0
0x18002d1e8  lea     r8, [rsp+38h+ppBuffer]; ppBuffer
0x18002d1ed  mov     [rsp+38h+ppBuffer], 0
0x18002d1f6  mov     edx, 1; WTS_VIRTUAL_CLASS
0x18002d1fb  mov     rcx, rax; hChannelHandle
0x18002d1fe  call    cs:__imp_WTSVirtualChannelQuery
0x18002d204  test    eax, eax
0x18002d206  jnz     short loc_18002D23E
0x18002d208  call    cs:__imp_GetLastError
0x18002d20e  mov     ebx, eax
0x18002d210  mov     rax, cs:WPP_GLOBAL_Control
0x18002d217  lea     rcx, WPP_GLOBAL_Control
0x18002d21e  cmp     rax, rcx
0x18002d221  jz      short loc_18002D1BF
0x18002d223  test    byte ptr [rax+1Ch], 8
0x18002d227  jz      short loc_18002D1BF
0x18002d229  cmp     byte ptr [rax+19h], 2
0x18002d22d  jb      short loc_18002D1BF
0x18002d22f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d234  mov     edx, 13h
0x18002d239  jmp     loc_18002D1A1
0x18002d23e  mov     rcx, [rsp+38h+ppBuffer]; pMemory
0x18002d243  mov     dword ptr [rbx+168h], 1
0x18002d24d  mov     rax, [rcx]
0x18002d250  mov     [rbx+158h], rax
0x18002d257  call    cs:__imp_WTSFreeMemory
0x18002d25d  xor     ebx, ebx
0x18002d25f  mov     eax, ebx
0x18002d261  add     rsp, 30h
0x18002d265  pop     rbx
0x18002d266  retn
```
