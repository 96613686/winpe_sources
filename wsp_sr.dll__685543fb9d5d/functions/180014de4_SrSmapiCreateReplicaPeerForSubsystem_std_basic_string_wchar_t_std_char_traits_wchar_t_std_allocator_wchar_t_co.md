# SrSmapiCreateReplicaPeerForSubsystem(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)

- ea: `0x180014de4`
- end: `0x180014f9c`
- name: `?SrSmapiCreateReplicaPeerForSubsystem@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path`

## callers

- `0x1800155a8`

## callees

- `0x1800014e0`
- `0x18000590c`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x180014de4`
- `0x180015908`
- `0x180015940`
- `0x180015978`
- `0x1800159b0`
- `0x1800159e8`
- `0x180015a20`
- `0x18001aed0`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicaPeerForSubsystem(_QWORD *a1, _QWORD *a2, int a3, char a4, __int64 a5)
{
  unsigned int v9; // ebx
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  _QWORD v15[3]; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-50h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids);
  std::wstring::wstring(v15);
  v9 = EncodeReplicaPeerbjectId((_DWORD)a1, (_DWORD)a2, a3, 2, a4, (__int64)v15);
  if ( !v9 )
  {
    v10 = v15;
    if ( v16 > 7 )
      v10 = (_QWORD *)v15[0];
    v9 = WSP_ReplicaPeer_Set_ObjectId(a5, v10);
    if ( !v9 )
    {
      v11 = v15;
      if ( v16 > 7 )
        v11 = (_QWORD *)v15[0];
      v9 = WSP_ReplicaPeer_Set_UniqueId(a5, v11);
      if ( !v9 )
      {
        *(_BYTE *)(a5 + 248) = a4;
        *(_BYTE *)(a5 + 249) = 1;
        *(_WORD *)(a5 + 160) = -32766;
        *(_BYTE *)(a5 + 162) = 1;
        v12 = a1[3] <= 7u ? a1 : (_QWORD *)*a1;
        v9 = WSP_ReplicaPeer_Set_PeerObjectId(a5, v12);
        if ( !v9 )
        {
          v13 = a1[3] <= 7u ? a1 : (_QWORD *)*a1;
          v9 = WSP_ReplicaPeer_Set_PeerUniqueId(a5, v13);
          if ( !v9 )
          {
            if ( a1[3] > 7u )
              a1 = (_QWORD *)*a1;
            v9 = WSP_ReplicaPeer_Set_PeerObjectName(a5, a1);
            if ( !v9 )
            {
              if ( a2[3] > 7u )
                a2 = (_QWORD *)*a2;
              v9 = WSP_ReplicaPeer_Set_PeerSubsystemName(a5, a2);
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids, v9);
  std::wstring::_Tidy_deallocate(v15);
  return v9;
}

```

## disassembly

```asm
0x180014de4  push    rbx
0x180014de6  push    rbp
0x180014de7  push    rsi
0x180014de8  push    rdi
0x180014de9  push    r14
0x180014deb  push    r15
0x180014ded  sub     rsp, 68h
0x180014df1  mov     rax, cs:__security_cookie
0x180014df8  xor     rax, rsp
0x180014dfb  mov     [rsp+98h+var_48], rax
0x180014e00  mov     bpl, r9b
0x180014e03  mov     ebx, r8d
0x180014e06  mov     r14, rdx
0x180014e09  mov     rdi, rcx
0x180014e0c  mov     rsi, [rsp+98h+arg_20]
0x180014e14  lea     r15, WPP_GLOBAL_Control
0x180014e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e22  cmp     rcx, r15
0x180014e25  jz      short loc_180014E42
0x180014e27  test    byte ptr [rcx+1Ch], 4
0x180014e2b  jz      short loc_180014E42
0x180014e2d  mov     edx, 0Eh
0x180014e32  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014e39  mov     rcx, [rcx+10h]
0x180014e3d  call    WPP_SF_
0x180014e42  lea     rcx, [rsp+98h+var_68]
0x180014e47  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014e4c  nop
0x180014e4d  lea     rax, [rsp+98h+var_68]
0x180014e52  mov     [rsp+98h+var_70], rax
0x180014e57  mov     [rsp+98h+var_78], bpl
0x180014e5c  mov     r9d, 2
0x180014e62  mov     r8d, ebx
0x180014e65  mov     rdx, r14
0x180014e68  mov     rcx, rdi
0x180014e6b  call    ?EncodeReplicaPeerbjectId@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@_NAEAV23@@Z; EncodeReplicaPeerbjectId(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,bool,std::wstring &)
0x180014e70  mov     ebx, eax
0x180014e72  test    eax, eax
0x180014e74  jnz     loc_180014F4A
0x180014e7a  lea     rdx, [rsp+98h+var_68]
0x180014e7f  cmp     [rsp+98h+var_50], 7
0x180014e85  cmova   rdx, [rsp+98h+var_68]
0x180014e8b  mov     rcx, rsi
0x180014e8e  call    WSP_ReplicaPeer_Set_ObjectId
0x180014e93  mov     ebx, eax
0x180014e95  test    eax, eax
0x180014e97  jnz     loc_180014F4A
0x180014e9d  lea     rdx, [rsp+98h+var_68]
0x180014ea2  cmp     [rsp+98h+var_50], 7
0x180014ea8  cmova   rdx, [rsp+98h+var_68]
0x180014eae  mov     rcx, rsi
0x180014eb1  call    WSP_ReplicaPeer_Set_UniqueId
0x180014eb6  mov     ebx, eax
0x180014eb8  test    eax, eax
0x180014eba  jnz     loc_180014F4A
0x180014ec0  mov     [rsi+0F8h], bpl
0x180014ec7  mov     byte ptr [rsi+0F9h], 1
0x180014ece  mov     word ptr [rsi+0A0h], 8002h
0x180014ed7  mov     byte ptr [rsi+0A2h], 1
0x180014ede  cmp     qword ptr [rdi+18h], 7
0x180014ee3  jbe     short loc_180014EEA
0x180014ee5  mov     rdx, [rdi]
0x180014ee8  jmp     short loc_180014EED
0x180014eea  mov     rdx, rdi
0x180014eed  mov     rcx, rsi
0x180014ef0  call    WSP_ReplicaPeer_Set_PeerObjectId
0x180014ef5  mov     ebx, eax
0x180014ef7  test    eax, eax
0x180014ef9  jnz     short loc_180014F4A
0x180014efb  cmp     qword ptr [rdi+18h], 7
0x180014f00  jbe     short loc_180014F07
0x180014f02  mov     rdx, [rdi]
0x180014f05  jmp     short loc_180014F0A
0x180014f07  mov     rdx, rdi
0x180014f0a  mov     rcx, rsi
0x180014f0d  call    WSP_ReplicaPeer_Set_PeerUniqueId
0x180014f12  mov     ebx, eax
0x180014f14  test    eax, eax
0x180014f16  jnz     short loc_180014F4A
0x180014f18  cmp     qword ptr [rdi+18h], 7
0x180014f1d  jbe     short loc_180014F22
0x180014f1f  mov     rdi, [rdi]
0x180014f22  mov     rdx, rdi
0x180014f25  mov     rcx, rsi
0x180014f28  call    WSP_ReplicaPeer_Set_PeerObjectName
0x180014f2d  mov     ebx, eax
0x180014f2f  test    eax, eax
0x180014f31  jnz     short loc_180014F4A
0x180014f33  cmp     qword ptr [r14+18h], 7
0x180014f38  jbe     short loc_180014F3D
0x180014f3a  mov     r14, [r14]
0x180014f3d  mov     rdx, r14
0x180014f40  mov     rcx, rsi
0x180014f43  call    WSP_ReplicaPeer_Set_PeerSubsystemName
0x180014f48  mov     ebx, eax
0x180014f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f51  cmp     rcx, r15
0x180014f54  jz      short loc_180014F75
0x180014f56  test    byte ptr [rcx+1Ch], 1
0x180014f5a  jz      short loc_180014F75
0x180014f5c  mov     edx, 0Fh
0x180014f61  mov     r9d, ebx
0x180014f64  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014f6b  mov     rcx, [rcx+10h]
0x180014f6f  call    WPP_SF_d
0x180014f74  nop
0x180014f75  lea     rcx, [rsp+98h+var_68]
0x180014f7a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014f7f  mov     eax, ebx
0x180014f81  mov     rcx, [rsp+98h+var_48]
0x180014f86  xor     rcx, rsp; StackCookie
0x180014f89  call    __security_check_cookie
0x180014f8e  add     rsp, 68h
0x180014f92  pop     r15
0x180014f94  pop     r14
0x180014f96  pop     rdi
0x180014f97  pop     rsi
0x180014f98  pop     rbp
0x180014f99  pop     rbx
0x180014f9a  retn
```
