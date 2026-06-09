# AllocateDriverGlobalIFRLog

- ea: `0x14002d27c`
- end: `0x14002d36b`
- name: `AllocateDriverGlobalIFRLog`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14002f078`

## callees

- `0x14000e1c0`
- `0x140014d10`
- `0x14002d27c`

## import_xrefs

- `WppRecorder!imp_WppRecorderConfigure` at `0x14002d2d2`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14002d2d2`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14002d33b`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14002d33b`

## pseudocode

```c
__int64 AllocateDriverGlobalIFRLog()
{
  size_t v0; // rdx
  __int64 result; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v3; // [rsp+30h] [rbp-40h] BYREF
  __int128 v4; // [rsp+40h] [rbp-30h]
  char pszDest[16]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v6; // [rsp+60h] [rbp-10h]

  v6 = 0;
  v2[0] = 16;
  v2[1] = 0x200000002LL;
  v3 = 0;
  v4 = 0;
  *(_OWORD *)pszDest = 0;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, v2);
  *(_QWORD *)&v3 = 56;
  pszDest[0] = 0;
  HIDWORD(v4) = 16;
  *(_QWORD *)&v4 = 0;
  BYTE8(v4) = 0;
  v6 = 0x200000002LL;
  *((_QWORD *)&v3 + 1) = 0xC800000200LL;
  RtlStringCchCopyA(pszDest, v0, "DriverGlobal");
  result = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v3, &g_RecorderLog);
  if ( (int)result < 0 )
    g_RecorderLog = 0;
  return result;
}

```

## disassembly

```asm
0x14002d27c  push    rbp
0x14002d27e  mov     rbp, rsp
0x14002d281  sub     rsp, 70h
0x14002d285  mov     rax, cs:__security_cookie
0x14002d28c  xor     rax, rsp
0x14002d28f  mov     [rbp+var_8], rax
0x14002d293  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d29a  lea     rdx, [rbp+var_50]
0x14002d29e  xorps   xmm1, xmm1
0x14002d2a1  xor     eax, eax
0x14002d2a3  xorps   xmm0, xmm0
0x14002d2a6  mov     [rbp+var_10], rax
0x14002d2aa  movups  [rbp+var_50], xmm0
0x14002d2ae  mov     dword ptr [rbp+var_50], 10h
0x14002d2b5  mov     dword ptr [rbp+var_50+8], 2
0x14002d2bc  mov     dword ptr [rbp+var_50+0Ch], 2
0x14002d2c3  mov     byte ptr [rbp+var_50+4], al
0x14002d2c6  movups  [rbp+var_40], xmm1
0x14002d2ca  movups  [rbp+var_30], xmm1
0x14002d2ce  movups  xmmword ptr [rbp+pszDest], xmm1
0x14002d2d2  call    cs:__imp_imp_WppRecorderConfigure
0x14002d2d9  nop     dword ptr [rax+rax+00h]
0x14002d2de  lea     r8, pszSrc; "DriverGlobal"
0x14002d2e5  mov     qword ptr [rbp+var_40], 38h ; '8'
0x14002d2ed  lea     rcx, [rbp+pszDest]; pszDest
0x14002d2f1  mov     dword ptr [rbp+var_40+0Ch], 0C8h
0x14002d2f8  mov     [rbp+pszDest], 0
0x14002d2fc  mov     dword ptr [rbp+var_30+0Ch], 10h
0x14002d303  mov     qword ptr [rbp+var_30], 0
0x14002d30b  mov     byte ptr [rbp+var_30+8], 0
0x14002d30f  mov     dword ptr [rbp+var_10], 2
0x14002d316  mov     dword ptr [rbp+var_10+4], 2
0x14002d31d  mov     dword ptr [rbp+var_40+8], 200h
0x14002d324  call    RtlStringCchCopyA
0x14002d329  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d330  lea     r8, g_RecorderLog
0x14002d337  lea     rdx, [rbp+var_40]
0x14002d33b  call    cs:__imp_imp_WppRecorderLogCreate
0x14002d342  nop     dword ptr [rax+rax+00h]
0x14002d347  test    eax, eax
0x14002d349  js      short loc_14002D35E
0x14002d34b  mov     rcx, [rbp+var_8]
0x14002d34f  xor     rcx, rsp; StackCookie
0x14002d352  call    __security_check_cookie
0x14002d357  add     rsp, 70h
0x14002d35b  pop     rbp
0x14002d35c  retn
0x14002d35e  mov     cs:g_RecorderLog, 0
0x14002d369  jmp     short loc_14002D34B
```
