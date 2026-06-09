# InitShutdownState(void)

- ea: `0x18001a8dc`
- end: `0x18001a9a9`
- name: `?InitShutdownState@@YAJXZ`
- size: `205`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180039100`

## callees

- `0x180019714`
- `0x18001a8dc`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a951`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a969`

## pseudocode

```c
signed int InitShutdownState(void)
{
  __int128 v0; // xmm6
  char v1; // bl
  __int64 v2; // xmm7_8
  signed int result; // eax
  __int128 v4; // [rsp+20h] [rbp-48h]
  __int64 v5; // [rsp+30h] [rbp-38h]

  if ( byte_1800A3320 )
  {
    v2 = v5;
    v1 = 0;
    v0 = v4;
    byte_1800A3320 = 0;
  }
  else
  {
    v0 = xmmword_1800A3670;
    v1 = 1;
    v2 = qword_1800A3680;
  }
  memset_0(&g_shutdown, 0, 0x58u);
  result = myInitializeCriticalSection(&stru_1800A3638);
  if ( result >= 0 )
  {
    g_shutdown = 1;
    qword_1800A3660 = CreateEventW(0, 0, 0, 0);
    if ( qword_1800A3660 )
    {
      if ( v1 )
      {
        xmmword_1800A3670 = v0;
        qword_1800A3680 = v2;
      }
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a8dc  push    rbx
0x18001a8de  sub     rsp, 60h
0x18001a8e2  cmp     cs:byte_1800A3320, 0
0x18001a8e9  movaps  [rsp+68h+var_18], xmm6
0x18001a8ee  movaps  [rsp+68h+var_28], xmm7
0x18001a8f3  jnz     short loc_18001A908
0x18001a8f5  movaps  xmm6, cs:xmmword_1800A3670
0x18001a8fc  mov     bl, 1
0x18001a8fe  movsd   xmm7, cs:qword_1800A3680
0x18001a906  jmp     short loc_18001A91B
0x18001a908  movsd   xmm7, [rsp+68h+var_38]
0x18001a90e  xor     bl, bl
0x18001a910  movups  xmm6, [rsp+68h+var_48]
0x18001a915  mov     cs:byte_1800A3320, bl
0x18001a91b  xor     edx, edx; Val
0x18001a91d  lea     rcx, ?g_shutdown@@3UShutdownInfo@@A; void *
0x18001a924  lea     r8d, [rdx+58h]; Size
0x18001a928  call    memset_0
0x18001a92d  lea     rcx, stru_1800A3638; lpCriticalSection
0x18001a934  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001a939  test    eax, eax
0x18001a93b  js      short loc_18001A998
0x18001a93d  xor     r9d, r9d; lpName
0x18001a940  mov     cs:?g_shutdown@@3UShutdownInfo@@A, 1; ShutdownInfo g_shutdown
0x18001a94a  xor     r8d, r8d; bInitialState
0x18001a94d  xor     edx, edx; bManualReset
0x18001a94f  xor     ecx, ecx; lpEventAttributes
0x18001a951  call    cs:__imp_CreateEventW
0x18001a958  nop     dword ptr [rax+rax+00h]
0x18001a95d  mov     cs:qword_1800A3660, rax
0x18001a964  test    rax, rax
0x18001a967  jnz     short loc_18001A983
0x18001a969  call    cs:__imp_GetLastError
0x18001a970  nop     dword ptr [rax+rax+00h]
0x18001a975  test    eax, eax
0x18001a977  jle     short loc_18001A998
0x18001a979  movzx   eax, ax
0x18001a97c  or      eax, 80070000h
0x18001a981  jmp     short loc_18001A998
0x18001a983  test    bl, bl
0x18001a985  jz      short loc_18001A996
0x18001a987  movaps  cs:xmmword_1800A3670, xmm6
0x18001a98e  movsd   cs:qword_1800A3680, xmm7
0x18001a996  xor     eax, eax
0x18001a998  movaps  xmm6, [rsp+68h+var_18]
0x18001a99d  movaps  xmm7, [rsp+68h+var_28]
0x18001a9a2  add     rsp, 60h
0x18001a9a6  pop     rbx
0x18001a9a7  retn
```
