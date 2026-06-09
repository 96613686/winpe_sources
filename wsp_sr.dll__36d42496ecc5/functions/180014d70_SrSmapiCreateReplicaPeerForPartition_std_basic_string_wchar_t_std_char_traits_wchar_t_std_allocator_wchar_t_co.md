# SrSmapiCreateReplicaPeerForPartition(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)

- ea: `0x180014d70`
- end: `0x180014f27`
- name: `?SrSmapiCreateReplicaPeerForPartition@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z`
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
- `0x180014d70`
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
__int64 __fastcall SrSmapiCreateReplicaPeerForPartition(_QWORD *a1, _QWORD *a2, int a3, char a4, __int64 a5)
{
  unsigned int v9; // ebx
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  _QWORD v15[3]; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-50h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids);
  std::wstring::wstring((__int64)v15);
  v9 = EncodeReplicaPeerbjectId((_DWORD)a1, (_DWORD)a2, a3, 17, a4, (__int64)v15);
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
        *(_WORD *)(a5 + 160) = 0x8000;
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids, v9);
  std::wstring::_Tidy_deallocate((__int64)v15);
  return v9;
}

```

## disassembly

```asm
0x180014d70  push    rbx
0x180014d72  push    rbp
0x180014d73  push    rsi
0x180014d74  push    rdi
0x180014d75  push    r14
0x180014d77  push    r15
0x180014d79  sub     rsp, 68h
0x180014d7d  mov     rax, cs:__security_cookie
0x180014d84  xor     rax, rsp
0x180014d87  mov     [rsp+98h+var_48], rax
0x180014d8c  mov     bpl, r9b
0x180014d8f  mov     ebx, r8d
0x180014d92  mov     r14, rdx
0x180014d95  mov     rdi, rcx
0x180014d98  mov     rsi, [rsp+98h+arg_20]
0x180014da0  lea     r15, WPP_GLOBAL_Control
0x180014da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dae  cmp     rcx, r15
0x180014db1  jz      short loc_180014DCE
0x180014db3  test    byte ptr [rcx+1Ch], 4
0x180014db7  jz      short loc_180014DCE
0x180014db9  mov     edx, 0Ch
0x180014dbe  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014dc5  mov     rcx, [rcx+10h]
0x180014dc9  call    WPP_SF_
0x180014dce  lea     rcx, [rsp+98h+var_68]
0x180014dd3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014dd8  nop
0x180014dd9  lea     rax, [rsp+98h+var_68]
0x180014dde  mov     [rsp+98h+var_70], rax
0x180014de3  mov     [rsp+98h+var_78], bpl
0x180014de8  mov     r9d, 11h
0x180014dee  mov     r8d, ebx
0x180014df1  mov     rdx, r14
0x180014df4  mov     rcx, rdi
0x180014df7  call    ?EncodeReplicaPeerbjectId@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@_NAEAV23@@Z; EncodeReplicaPeerbjectId(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,bool,std::wstring &)
0x180014dfc  mov     ebx, eax
0x180014dfe  test    eax, eax
0x180014e00  jnz     loc_180014ED6
0x180014e06  lea     rdx, [rsp+98h+var_68]
0x180014e0b  cmp     [rsp+98h+var_50], 7
0x180014e11  cmova   rdx, [rsp+98h+var_68]
0x180014e17  mov     rcx, rsi
0x180014e1a  call    WSP_ReplicaPeer_Set_ObjectId
0x180014e1f  mov     ebx, eax
0x180014e21  test    eax, eax
0x180014e23  jnz     loc_180014ED6
0x180014e29  lea     rdx, [rsp+98h+var_68]
0x180014e2e  cmp     [rsp+98h+var_50], 7
0x180014e34  cmova   rdx, [rsp+98h+var_68]
0x180014e3a  mov     rcx, rsi
0x180014e3d  call    WSP_ReplicaPeer_Set_UniqueId
0x180014e42  mov     ebx, eax
0x180014e44  test    eax, eax
0x180014e46  jnz     loc_180014ED6
0x180014e4c  mov     [rsi+0F8h], bpl
0x180014e53  mov     byte ptr [rsi+0F9h], 1
0x180014e5a  mov     word ptr [rsi+0A0h], 8000h
0x180014e63  mov     byte ptr [rsi+0A2h], 1
0x180014e6a  cmp     qword ptr [rdi+18h], 7
0x180014e6f  jbe     short loc_180014E76
0x180014e71  mov     rdx, [rdi]
0x180014e74  jmp     short loc_180014E79
0x180014e76  mov     rdx, rdi
0x180014e79  mov     rcx, rsi
0x180014e7c  call    WSP_ReplicaPeer_Set_PeerObjectId
0x180014e81  mov     ebx, eax
0x180014e83  test    eax, eax
0x180014e85  jnz     short loc_180014ED6
0x180014e87  cmp     qword ptr [rdi+18h], 7
0x180014e8c  jbe     short loc_180014E93
0x180014e8e  mov     rdx, [rdi]
0x180014e91  jmp     short loc_180014E96
0x180014e93  mov     rdx, rdi
0x180014e96  mov     rcx, rsi
0x180014e99  call    WSP_ReplicaPeer_Set_PeerUniqueId
0x180014e9e  mov     ebx, eax
0x180014ea0  test    eax, eax
0x180014ea2  jnz     short loc_180014ED6
0x180014ea4  cmp     qword ptr [rdi+18h], 7
0x180014ea9  jbe     short loc_180014EAE
0x180014eab  mov     rdi, [rdi]
0x180014eae  mov     rdx, rdi
0x180014eb1  mov     rcx, rsi
0x180014eb4  call    WSP_ReplicaPeer_Set_PeerObjectName
0x180014eb9  mov     ebx, eax
0x180014ebb  test    eax, eax
0x180014ebd  jnz     short loc_180014ED6
0x180014ebf  cmp     qword ptr [r14+18h], 7
0x180014ec4  jbe     short loc_180014EC9
0x180014ec6  mov     r14, [r14]
0x180014ec9  mov     rdx, r14
0x180014ecc  mov     rcx, rsi
0x180014ecf  call    WSP_ReplicaPeer_Set_PeerSubsystemName
0x180014ed4  mov     ebx, eax
0x180014ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014edd  cmp     rcx, r15
0x180014ee0  jz      short loc_180014F01
0x180014ee2  test    byte ptr [rcx+1Ch], 1
0x180014ee6  jz      short loc_180014F01
0x180014ee8  mov     edx, 0Dh
0x180014eed  mov     r9d, ebx
0x180014ef0  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014ef7  mov     rcx, [rcx+10h]
0x180014efb  call    WPP_SF_d
0x180014f00  nop
0x180014f01  lea     rcx, [rsp+98h+var_68]
0x180014f06  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014f0b  mov     eax, ebx
0x180014f0d  mov     rcx, [rsp+98h+var_48]
0x180014f12  xor     rcx, rsp; StackCookie
0x180014f15  call    __security_check_cookie
0x180014f1a  add     rsp, 68h
0x180014f1e  pop     r15
0x180014f20  pop     r14
0x180014f22  pop     rdi
0x180014f23  pop     rsi
0x180014f24  pop     rbp
0x180014f25  pop     rbx
0x180014f26  retn
```
