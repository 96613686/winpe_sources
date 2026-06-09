# DllMain

- ea: `0x180001f0c`
- end: `0x180002061`
- name: `DllMain`
- size: `341`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001f0c`
- `0x18000249c`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x180001fa4`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180001fa4`
- `ntdll!EtwUnregisterTraceGuids` at `0x180002033`
- `ntdll!EtwUnregisterTraceGuids` at `0x180002033`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 *v3; // rdi
  __int64 *v4; // rsi
  __int64 v5; // r8
  _QWORD *v6; // rdi
  _QWORD v8[3]; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason == 1 )
  {
    qword_180012170 = 1;
    qword_180012168 = 0;
    v3 = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
    v4 = &WPP_REGISTRATION_GUIDS;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    do
    {
      v5 = *v4;
      v8[0] = v5;
      ++v4;
      v8[1] = 0;
      v3[4] = v5;
      ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
        WppControlCallback,
        v3,
        v5,
        1,
        v8,
        0,
        0,
        v3 + 1);
      v3 = (__int64 *)*v3;
    }
    while ( v3 );
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids);
  }
  else if ( !fdwReason )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control )
      {
        while ( v6 )
        {
          if ( v6[1] )
          {
            EtwUnregisterTraceGuids();
            v6[1] = 0;
          }
          v6 = (_QWORD *)*v6;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001f0c  mov     [rsp+arg_0], rbx
0x180001f11  mov     [rsp+arg_8], rsi
0x180001f16  push    rdi
0x180001f17  sub     rsp, 50h
0x180001f1b  cmp     edx, 1
0x180001f1e  jnz     loc_180001FE7
0x180001f24  xor     ebx, ebx
0x180001f26  mov     cs:qword_180012170, 1
0x180001f31  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180001f38  mov     cs:qword_180012168, rbx
0x180001f3f  lea     rdi, WPP_MAIN_CB
0x180001f46  mov     cs:WPP_MAIN_CB, rbx
0x180001f4d  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180001f54  lea     rsi, WPP_REGISTRATION_GUIDS
0x180001f5b  mov     cs:WPP_GLOBAL_Control, rdi
0x180001f62  mov     r8, [rsi]
0x180001f65  lea     rax, [rdi+8]
0x180001f69  mov     [rsp+58h+var_20], rax
0x180001f6e  lea     rcx, WppControlCallback
0x180001f75  mov     [rsp+58h+var_28], rbx
0x180001f7a  lea     rax, [rsp+58h+var_18]
0x180001f7f  mov     [rsp+58h+var_18], r8
0x180001f84  lea     rsi, [rsi+8]
0x180001f88  mov     [rsp+58h+var_10], rbx
0x180001f8d  mov     r9d, 1
0x180001f93  mov     [rsp+58h+var_30], rbx
0x180001f98  mov     rdx, rdi
0x180001f9b  mov     [rsp+58h+var_38], rax
0x180001fa0  mov     [rdi+20h], r8
0x180001fa4  call    cs:__imp_EtwRegisterTraceGuidsW
0x180001faa  mov     rdi, [rdi]
0x180001fad  test    rdi, rdi
0x180001fb0  jnz     short loc_180001F62
0x180001fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fb9  lea     rsi, WPP_GLOBAL_Control
0x180001fc0  cmp     rcx, rsi
0x180001fc3  jz      loc_18000204C
0x180001fc9  test    dword ptr [rcx+1Ch], 400h
0x180001fd0  jz      short loc_18000204C
0x180001fd2  mov     rcx, [rcx+10h]
0x180001fd6  lea     edx, [rdi+0Ah]
0x180001fd9  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x180001fe0  call    WPP_SF_
0x180001fe5  jmp     short loc_18000204C
0x180001fe7  xor     ebx, ebx
0x180001fe9  test    edx, edx
0x180001feb  jnz     short loc_18000204C
0x180001fed  mov     rdi, cs:WPP_GLOBAL_Control
0x180001ff4  lea     rsi, WPP_GLOBAL_Control
0x180001ffb  cmp     rdi, rsi
0x180001ffe  jz      short loc_18000204C
0x180002000  test    dword ptr [rdi+1Ch], 400h
0x180002007  jz      short loc_180002023
0x180002009  mov     rcx, [rdi+10h]
0x18000200d  lea     edx, [rbx+0Bh]
0x180002010  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x180002017  call    WPP_SF_
0x18000201c  mov     rdi, cs:WPP_GLOBAL_Control
0x180002023  cmp     rdi, rsi
0x180002026  jz      short loc_18000204C
0x180002028  jmp     short loc_180002040
0x18000202a  mov     rcx, [rdi+8]
0x18000202e  test    rcx, rcx
0x180002031  jz      short loc_18000203D
0x180002033  call    cs:__imp_EtwUnregisterTraceGuids
0x180002039  mov     [rdi+8], rbx
0x18000203d  mov     rdi, [rdi]
0x180002040  test    rdi, rdi
0x180002043  jnz     short loc_18000202A
0x180002045  mov     cs:WPP_GLOBAL_Control, rsi
0x18000204c  mov     rbx, [rsp+58h+arg_0]
0x180002051  mov     eax, 1
0x180002056  mov     rsi, [rsp+58h+arg_8]
0x18000205b  add     rsp, 50h
0x18000205f  pop     rdi
0x180002060  retn
```
