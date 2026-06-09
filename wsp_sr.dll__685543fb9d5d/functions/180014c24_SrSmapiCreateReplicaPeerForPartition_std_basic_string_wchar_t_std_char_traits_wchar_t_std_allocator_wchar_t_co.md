# SrSmapiCreateReplicaPeerForPartition(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)

- ea: `0x180014c24`
- end: `0x180014ddc`
- name: `?SrSmapiCreateReplicaPeerForPartition@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z`
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
- `0x180014c24`
- `0x180015908`
- `0x180015940`
- `0x180015978`
- `0x1800159b0`
- `0x1800159e8`
- `0x180015a20`
- `0x18001aed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  std::wstring::wstring(v15);
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
  std::wstring::_Tidy_deallocate(v15);
  return v9;
}

```

## disassembly

```asm
0x180014c24  push    rbx
0x180014c26  push    rbp
0x180014c27  push    rsi
0x180014c28  push    rdi
0x180014c29  push    r14
0x180014c2b  push    r15
0x180014c2d  sub     rsp, 68h
0x180014c31  mov     rax, cs:__security_cookie
0x180014c38  xor     rax, rsp
0x180014c3b  mov     [rsp+98h+var_48], rax
0x180014c40  mov     bpl, r9b
0x180014c43  mov     ebx, r8d
0x180014c46  mov     r14, rdx
0x180014c49  mov     rdi, rcx
0x180014c4c  mov     rsi, [rsp+98h+arg_20]
0x180014c54  lea     r15, WPP_GLOBAL_Control
0x180014c5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c62  cmp     rcx, r15
0x180014c65  jz      short loc_180014C82
0x180014c67  test    byte ptr [rcx+1Ch], 4
0x180014c6b  jz      short loc_180014C82
0x180014c6d  mov     edx, 0Ch
0x180014c72  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014c79  mov     rcx, [rcx+10h]
0x180014c7d  call    WPP_SF_
0x180014c82  lea     rcx, [rsp+98h+var_68]
0x180014c87  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014c8c  nop
0x180014c8d  lea     rax, [rsp+98h+var_68]
0x180014c92  mov     [rsp+98h+var_70], rax
0x180014c97  mov     [rsp+98h+var_78], bpl
0x180014c9c  mov     r9d, 11h
0x180014ca2  mov     r8d, ebx
0x180014ca5  mov     rdx, r14
0x180014ca8  mov     rcx, rdi
0x180014cab  call    ?EncodeReplicaPeerbjectId@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@_NAEAV23@@Z; EncodeReplicaPeerbjectId(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,bool,std::wstring &)
0x180014cb0  mov     ebx, eax
0x180014cb2  test    eax, eax
0x180014cb4  jnz     loc_180014D8A
0x180014cba  lea     rdx, [rsp+98h+var_68]
0x180014cbf  cmp     [rsp+98h+var_50], 7
0x180014cc5  cmova   rdx, [rsp+98h+var_68]
0x180014ccb  mov     rcx, rsi
0x180014cce  call    WSP_ReplicaPeer_Set_ObjectId
0x180014cd3  mov     ebx, eax
0x180014cd5  test    eax, eax
0x180014cd7  jnz     loc_180014D8A
0x180014cdd  lea     rdx, [rsp+98h+var_68]
0x180014ce2  cmp     [rsp+98h+var_50], 7
0x180014ce8  cmova   rdx, [rsp+98h+var_68]
0x180014cee  mov     rcx, rsi
0x180014cf1  call    WSP_ReplicaPeer_Set_UniqueId
0x180014cf6  mov     ebx, eax
0x180014cf8  test    eax, eax
0x180014cfa  jnz     loc_180014D8A
0x180014d00  mov     [rsi+0F8h], bpl
0x180014d07  mov     byte ptr [rsi+0F9h], 1
0x180014d0e  mov     word ptr [rsi+0A0h], 8000h
0x180014d17  mov     byte ptr [rsi+0A2h], 1
0x180014d1e  cmp     qword ptr [rdi+18h], 7
0x180014d23  jbe     short loc_180014D2A
0x180014d25  mov     rdx, [rdi]
0x180014d28  jmp     short loc_180014D2D
0x180014d2a  mov     rdx, rdi
0x180014d2d  mov     rcx, rsi
0x180014d30  call    WSP_ReplicaPeer_Set_PeerObjectId
0x180014d35  mov     ebx, eax
0x180014d37  test    eax, eax
0x180014d39  jnz     short loc_180014D8A
0x180014d3b  cmp     qword ptr [rdi+18h], 7
0x180014d40  jbe     short loc_180014D47
0x180014d42  mov     rdx, [rdi]
0x180014d45  jmp     short loc_180014D4A
0x180014d47  mov     rdx, rdi
0x180014d4a  mov     rcx, rsi
0x180014d4d  call    WSP_ReplicaPeer_Set_PeerUniqueId
0x180014d52  mov     ebx, eax
0x180014d54  test    eax, eax
0x180014d56  jnz     short loc_180014D8A
0x180014d58  cmp     qword ptr [rdi+18h], 7
0x180014d5d  jbe     short loc_180014D62
0x180014d5f  mov     rdi, [rdi]
0x180014d62  mov     rdx, rdi
0x180014d65  mov     rcx, rsi
0x180014d68  call    WSP_ReplicaPeer_Set_PeerObjectName
0x180014d6d  mov     ebx, eax
0x180014d6f  test    eax, eax
0x180014d71  jnz     short loc_180014D8A
0x180014d73  cmp     qword ptr [r14+18h], 7
0x180014d78  jbe     short loc_180014D7D
0x180014d7a  mov     r14, [r14]
0x180014d7d  mov     rdx, r14
0x180014d80  mov     rcx, rsi
0x180014d83  call    WSP_ReplicaPeer_Set_PeerSubsystemName
0x180014d88  mov     ebx, eax
0x180014d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d91  cmp     rcx, r15
0x180014d94  jz      short loc_180014DB5
0x180014d96  test    byte ptr [rcx+1Ch], 1
0x180014d9a  jz      short loc_180014DB5
0x180014d9c  mov     edx, 0Dh
0x180014da1  mov     r9d, ebx
0x180014da4  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014dab  mov     rcx, [rcx+10h]
0x180014daf  call    WPP_SF_d
0x180014db4  nop
0x180014db5  lea     rcx, [rsp+98h+var_68]
0x180014dba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014dbf  mov     eax, ebx
0x180014dc1  mov     rcx, [rsp+98h+var_48]
0x180014dc6  xor     rcx, rsp; StackCookie
0x180014dc9  call    __security_check_cookie
0x180014dce  add     rsp, 68h
0x180014dd2  pop     r15
0x180014dd4  pop     r14
0x180014dd6  pop     rdi
0x180014dd7  pop     rsi
0x180014dd8  pop     rbp
0x180014dd9  pop     rbx
0x180014dda  retn
```
