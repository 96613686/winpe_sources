# DllMain

- ea: `0x18000a1bc`
- end: `0x18000a3b4`
- name: `DllMain`
- size: `504`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800015f4`

## callees

- `0x180009968`
- `0x18000a1bc`
- `0x180016010`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18000a1dc`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000a1dc`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18000a259`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18000a259`
- `ntdll!EtwUnregisterTraceGuids` at `0x18000a390`
- `ntdll!EtwUnregisterTraceGuids` at `0x18000a390`
- `ntdll!RtlInitializeCriticalSection` at `0x18000a2d4`
- `ntdll!RtlInitializeCriticalSection` at `0x18000a2d4`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a2f2`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a2f2`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // edi
  __int64 *v4; // rbx
  __int64 *v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD); // rbx
  __int64 *v9; // rbx
  __int64 *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  void (__fastcall *v13)(_QWORD); // rax
  __int64 *v14; // rbx
  __int64 *v15; // rax
  _QWORD *v16; // rbx
  _QWORD v18[7]; // [rsp+40h] [rbp-38h] BYREF

  v3 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      qword_18001D9A8 = 0;
      v4 = &WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ControlGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v5 = &WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_18001D9B0 = 1;
      do
      {
        v6 = *v5;
        v18[0] = v6;
        ++v5;
        v18[1] = 0;
        v4[4] = v6;
        ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
          WppControlCallback,
          v4,
          v6,
          1,
          v18,
          0,
          0,
          v4 + 1);
        v4 = (__int64 *)*v4;
      }
      while ( v4 );
      v8 = (void (__fastcall **)(_QWORD))&off_18001D000;
      if ( &off_18001D000 != (_UNKNOWN *)-1LL )
      {
        qword_18001DA18 = (__int64)&off_18001D000;
        if ( off_18001D000 )
        {
          do
          {
            LOBYTE(v7) = 1;
            v8[8](v7);
            v8 += 9;
          }
          while ( *v8 );
        }
      }
      v9 = off_18001D120[0];
      v10 = off_18001D128;
      while ( v9 < v10 )
      {
        if ( *v9 )
        {
          LOBYTE(v7) = 1;
          (*(void (__fastcall **)(__int64))(*v9 + 64))(v7);
          v10 = off_18001D128;
        }
        ++v9;
      }
      return RtlInitializeCriticalSection(&stru_18001DA20) >= 0;
    }
  }
  else
  {
    if ( !lpvReserved )
      RtlDeleteCriticalSection(&stru_18001DA20);
    v11 = (_QWORD *)qword_18001DA18;
    if ( qword_18001DA18 )
    {
      while ( *v11 )
      {
        v12 = v11[4];
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v13 = (void (__fastcall *)(_QWORD))v11[8];
        v11[4] = 0;
        v13(0);
        v11 += 9;
      }
    }
    v14 = off_18001D120[0];
    v15 = off_18001D128;
    while ( v14 < v15 )
    {
      if ( *v14 )
      {
        (*(void (__fastcall **)(_QWORD))(*v14 + 64))(0);
        v15 = off_18001D128;
      }
      ++v14;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v16 )
      {
        if ( v16[1] )
        {
          EtwUnregisterTraceGuids();
          v16[1] = 0;
        }
        v16 = (_QWORD *)*v16;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000a1bc  push    rbx
0x18000a1be  push    rbp
0x18000a1bf  push    rsi
0x18000a1c0  push    rdi
0x18000a1c1  sub     rsp, 58h
0x18000a1c5  xor     ebp, ebp
0x18000a1c7  mov     edi, 1
0x18000a1cc  test    edx, edx
0x18000a1ce  jz      loc_18000A2E6
0x18000a1d4  cmp     edx, edi
0x18000a1d6  jnz     loc_18000A3A9
0x18000a1dc  call    cs:__imp_DisableThreadLibraryCalls
0x18000a1e2  lea     rax, WPP_ThisDir_CTLGUID_ControlGuid
0x18000a1e9  mov     cs:qword_18001D9A8, rbp
0x18000a1f0  lea     rbx, WPP_MAIN_CB
0x18000a1f7  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000a1fe  mov     cs:WPP_GLOBAL_Control, rbx
0x18000a205  lea     rsi, WPP_REGISTRATION_GUIDS
0x18000a20c  mov     cs:WPP_MAIN_CB, rbp
0x18000a213  mov     cs:qword_18001D9B0, rdi
0x18000a21a  mov     r8, [rsi]
0x18000a21d  lea     rax, [rbx+8]
0x18000a221  mov     [rsp+78h+var_40], rax
0x18000a226  lea     rcx, WppControlCallback
0x18000a22d  mov     [rsp+78h+var_48], rbp
0x18000a232  lea     rax, [rsp+78h+var_38]
0x18000a237  mov     [rsp+78h+var_38], r8
0x18000a23c  lea     rsi, [rsi+8]
0x18000a240  mov     [rsp+78h+var_30], rbp
0x18000a245  mov     r9d, edi
0x18000a248  mov     [rsp+78h+var_50], rbp
0x18000a24d  mov     rdx, rbx
0x18000a250  mov     [rsp+78h+var_58], rax
0x18000a255  mov     [rbx+20h], r8
0x18000a259  call    cs:__imp_EtwRegisterTraceGuidsW
0x18000a25f  mov     rbx, [rbx]
0x18000a262  test    rbx, rbx
0x18000a265  jnz     short loc_18000A21A
0x18000a267  lea     rbx, off_18001D000
0x18000a26e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a272  jz      short loc_18000A299
0x18000a274  cmp     cs:off_18001D000, rbp
0x18000a27b  mov     cs:qword_18001DA18, rbx
0x18000a282  jz      short loc_18000A299
0x18000a284  mov     rax, [rbx+40h]
0x18000a288  mov     cl, dil
0x18000a28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a290  lea     rbx, [rbx+48h]
0x18000a294  cmp     [rbx], rbp
0x18000a297  jnz     short loc_18000A284
0x18000a299  mov     rbx, cs:off_18001D120
0x18000a2a0  mov     rax, cs:off_18001D128
0x18000a2a7  jmp     short loc_18000A2C8
0x18000a2a9  mov     rdx, [rbx]
0x18000a2ac  test    rdx, rdx
0x18000a2af  jz      short loc_18000A2C4
0x18000a2b1  mov     rax, [rdx+40h]
0x18000a2b5  mov     cl, dil
0x18000a2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2bd  mov     rax, cs:off_18001D128
0x18000a2c4  add     rbx, 8
0x18000a2c8  cmp     rbx, rax
0x18000a2cb  jb      short loc_18000A2A9
0x18000a2cd  lea     rcx, stru_18001DA20; CriticalSection
0x18000a2d4  call    cs:__imp_RtlInitializeCriticalSection
0x18000a2da  mov     edi, eax
0x18000a2dc  not     edi
0x18000a2de  shr     edi, 1Fh
0x18000a2e1  jmp     loc_18000A3A9
0x18000a2e6  test    r8, r8
0x18000a2e9  jnz     short loc_18000A2F8
0x18000a2eb  lea     rcx, stru_18001DA20; CriticalSection
0x18000a2f2  call    cs:__imp_RtlDeleteCriticalSection
0x18000a2f8  mov     rbx, cs:qword_18001DA18
0x18000a2ff  test    rbx, rbx
0x18000a302  jz      short loc_18000A333
0x18000a304  jmp     short loc_18000A32E
0x18000a306  mov     rcx, [rbx+20h]
0x18000a30a  test    rcx, rcx
0x18000a30d  jz      short loc_18000A31B
0x18000a30f  mov     rax, [rcx]
0x18000a312  mov     rax, [rax+10h]
0x18000a316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a31b  mov     rax, [rbx+40h]
0x18000a31f  xor     ecx, ecx
0x18000a321  mov     [rbx+20h], rbp
0x18000a325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32a  add     rbx, 48h ; 'H'
0x18000a32e  cmp     [rbx], rbp
0x18000a331  jnz     short loc_18000A306
0x18000a333  mov     rbx, cs:off_18001D120
0x18000a33a  mov     rax, cs:off_18001D128
0x18000a341  jmp     short loc_18000A361
0x18000a343  mov     rdx, [rbx]
0x18000a346  test    rdx, rdx
0x18000a349  jz      short loc_18000A35D
0x18000a34b  mov     rax, [rdx+40h]
0x18000a34f  xor     ecx, ecx
0x18000a351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a356  mov     rax, cs:off_18001D128
0x18000a35d  add     rbx, 8
0x18000a361  cmp     rbx, rax
0x18000a364  jb      short loc_18000A343
0x18000a366  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000a36d  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000a372  mov     rbx, cs:WPP_GLOBAL_Control
0x18000a379  lea     rsi, WPP_GLOBAL_Control
0x18000a380  cmp     rbx, rsi
0x18000a383  jz      short loc_18000A3A9
0x18000a385  jmp     short loc_18000A39D
0x18000a387  mov     rcx, [rbx+8]
0x18000a38b  test    rcx, rcx
0x18000a38e  jz      short loc_18000A39A
0x18000a390  call    cs:__imp_EtwUnregisterTraceGuids
0x18000a396  mov     [rbx+8], rbp
0x18000a39a  mov     rbx, [rbx]
0x18000a39d  test    rbx, rbx
0x18000a3a0  jnz     short loc_18000A387
0x18000a3a2  mov     cs:WPP_GLOBAL_Control, rsi
0x18000a3a9  mov     eax, edi
0x18000a3ab  add     rsp, 58h
0x18000a3af  pop     rdi
0x18000a3b0  pop     rsi
0x18000a3b1  pop     rbp
0x18000a3b2  pop     rbx
0x18000a3b3  retn
```
