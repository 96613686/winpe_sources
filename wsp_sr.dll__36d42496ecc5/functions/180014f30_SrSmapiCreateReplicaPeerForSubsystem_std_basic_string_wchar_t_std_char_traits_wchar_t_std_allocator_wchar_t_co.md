# SrSmapiCreateReplicaPeerForSubsystem(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)

- ea: `0x180014f30`
- end: `0x1800150e7`
- name: `?SrSmapiCreateReplicaPeerForSubsystem@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, int, char, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path`

## callers

- `0x1800156f4`

## callees

- `0x1800014e0`
- `0x1800058d4`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180014f30`
- `0x180015a54`
- `0x180015a8c`
- `0x180015ac4`
- `0x180015afc`
- `0x180015b34`
- `0x180015b6c`
- `0x18001aeb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  std::wstring::wstring((__int64)v15);
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
  std::wstring::_Tidy_deallocate((__int64)v15);
  return v9;
}

```

## disassembly

```asm
0x180014f30  push    rbx
0x180014f32  push    rbp
0x180014f33  push    rsi
0x180014f34  push    rdi
0x180014f35  push    r14
0x180014f37  push    r15
0x180014f39  sub     rsp, 68h
0x180014f3d  mov     rax, cs:__security_cookie
0x180014f44  xor     rax, rsp
0x180014f47  mov     [rsp+98h+var_48], rax
0x180014f4c  mov     bpl, r9b
0x180014f4f  mov     ebx, r8d
0x180014f52  mov     r14, rdx
0x180014f55  mov     rdi, rcx
0x180014f58  mov     rsi, [rsp+98h+arg_20]
0x180014f60  lea     r15, WPP_GLOBAL_Control
0x180014f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f6e  cmp     rcx, r15
0x180014f71  jz      short loc_180014F8E
0x180014f73  test    byte ptr [rcx+1Ch], 4
0x180014f77  jz      short loc_180014F8E
0x180014f79  mov     edx, 0Eh
0x180014f7e  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014f85  mov     rcx, [rcx+10h]
0x180014f89  call    WPP_SF_
0x180014f8e  lea     rcx, [rsp+98h+var_68]
0x180014f93  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014f98  nop
0x180014f99  lea     rax, [rsp+98h+var_68]
0x180014f9e  mov     [rsp+98h+var_70], rax
0x180014fa3  mov     [rsp+98h+var_78], bpl
0x180014fa8  mov     r9d, 2
0x180014fae  mov     r8d, ebx
0x180014fb1  mov     rdx, r14
0x180014fb4  mov     rcx, rdi
0x180014fb7  call    ?EncodeReplicaPeerbjectId@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@_NAEAV23@@Z; EncodeReplicaPeerbjectId(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,bool,std::wstring &)
0x180014fbc  mov     ebx, eax
0x180014fbe  test    eax, eax
0x180014fc0  jnz     loc_180015096
0x180014fc6  lea     rdx, [rsp+98h+var_68]
0x180014fcb  cmp     [rsp+98h+var_50], 7
0x180014fd1  cmova   rdx, [rsp+98h+var_68]
0x180014fd7  mov     rcx, rsi
0x180014fda  call    WSP_ReplicaPeer_Set_ObjectId
0x180014fdf  mov     ebx, eax
0x180014fe1  test    eax, eax
0x180014fe3  jnz     loc_180015096
0x180014fe9  lea     rdx, [rsp+98h+var_68]
0x180014fee  cmp     [rsp+98h+var_50], 7
0x180014ff4  cmova   rdx, [rsp+98h+var_68]
0x180014ffa  mov     rcx, rsi
0x180014ffd  call    WSP_ReplicaPeer_Set_UniqueId
0x180015002  mov     ebx, eax
0x180015004  test    eax, eax
0x180015006  jnz     loc_180015096
0x18001500c  mov     [rsi+0F8h], bpl
0x180015013  mov     byte ptr [rsi+0F9h], 1
0x18001501a  mov     word ptr [rsi+0A0h], 8002h
0x180015023  mov     byte ptr [rsi+0A2h], 1
0x18001502a  cmp     qword ptr [rdi+18h], 7
0x18001502f  jbe     short loc_180015036
0x180015031  mov     rdx, [rdi]
0x180015034  jmp     short loc_180015039
0x180015036  mov     rdx, rdi
0x180015039  mov     rcx, rsi
0x18001503c  call    WSP_ReplicaPeer_Set_PeerObjectId
0x180015041  mov     ebx, eax
0x180015043  test    eax, eax
0x180015045  jnz     short loc_180015096
0x180015047  cmp     qword ptr [rdi+18h], 7
0x18001504c  jbe     short loc_180015053
0x18001504e  mov     rdx, [rdi]
0x180015051  jmp     short loc_180015056
0x180015053  mov     rdx, rdi
0x180015056  mov     rcx, rsi
0x180015059  call    WSP_ReplicaPeer_Set_PeerUniqueId
0x18001505e  mov     ebx, eax
0x180015060  test    eax, eax
0x180015062  jnz     short loc_180015096
0x180015064  cmp     qword ptr [rdi+18h], 7
0x180015069  jbe     short loc_18001506E
0x18001506b  mov     rdi, [rdi]
0x18001506e  mov     rdx, rdi
0x180015071  mov     rcx, rsi
0x180015074  call    WSP_ReplicaPeer_Set_PeerObjectName
0x180015079  mov     ebx, eax
0x18001507b  test    eax, eax
0x18001507d  jnz     short loc_180015096
0x18001507f  cmp     qword ptr [r14+18h], 7
0x180015084  jbe     short loc_180015089
0x180015086  mov     r14, [r14]
0x180015089  mov     rdx, r14
0x18001508c  mov     rcx, rsi
0x18001508f  call    WSP_ReplicaPeer_Set_PeerSubsystemName
0x180015094  mov     ebx, eax
0x180015096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001509d  cmp     rcx, r15
0x1800150a0  jz      short loc_1800150C1
0x1800150a2  test    byte ptr [rcx+1Ch], 1
0x1800150a6  jz      short loc_1800150C1
0x1800150a8  mov     edx, 0Fh
0x1800150ad  mov     r9d, ebx
0x1800150b0  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x1800150b7  mov     rcx, [rcx+10h]
0x1800150bb  call    WPP_SF_d
0x1800150c0  nop
0x1800150c1  lea     rcx, [rsp+98h+var_68]
0x1800150c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800150cb  mov     eax, ebx
0x1800150cd  mov     rcx, [rsp+98h+var_48]
0x1800150d2  xor     rcx, rsp; StackCookie
0x1800150d5  call    __security_check_cookie
0x1800150da  add     rsp, 68h
0x1800150de  pop     r15
0x1800150e0  pop     r14
0x1800150e2  pop     rdi
0x1800150e3  pop     rsi
0x1800150e4  pop     rbp
0x1800150e5  pop     rbx
0x1800150e6  retn
```
