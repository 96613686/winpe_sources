# SrSmapiCreateReplicaPeer(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)

- ea: `0x180014b88`
- end: `0x180014d68`
- name: `?SrSmapiCreateReplicaPeer@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, int, char, __int64)`
- caller_count: `3`
- callee_count: `14`
- tags: `reparse_path`

## callers

- `0x1800150f0`
- `0x1800156f4`
- `0x1800158d8`

## callees

- `0x1800014e0`
- `0x1800058d4`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180014b88`
- `0x180015a54`
- `0x180015a8c`
- `0x180015ac4`
- `0x180015afc`
- `0x180015b34`
- `0x180015b6c`
- `0x18001ae10`
- `0x18001aeb8`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicaPeer(_QWORD *a1, _QWORD *a2, int a3, char a4, __int64 a5)
{
  unsigned int v9; // ebx
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  _QWORD v15[3]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-38h]
  _QWORD v17[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v18; // [rsp+68h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids);
  std::wstring::wstring((__int64)v17);
  std::wstring::wstring((__int64)v15);
  v9 = EncodeReplicaPeerbjectId((_DWORD)a1, (_DWORD)a2, a3, 20, a4, (__int64)v17);
  if ( !v9 )
  {
    v9 = EncodeReplicaPeerObjectIdForPartitionInternal(a1, a2, v15);
    if ( !v9 )
    {
      v10 = v17;
      if ( v18 > 7 )
        v10 = (_QWORD *)v17[0];
      v9 = WSP_ReplicaPeer_Set_ObjectId(a5, v10);
      if ( !v9 )
      {
        v11 = v17;
        if ( v18 > 7 )
          v11 = (_QWORD *)v17[0];
        v9 = WSP_ReplicaPeer_Set_UniqueId(a5, v11);
        if ( !v9 )
        {
          *(_BYTE *)(a5 + 248) = a4;
          *(_BYTE *)(a5 + 249) = 1;
          *(_WORD *)(a5 + 160) = -32767;
          *(_BYTE *)(a5 + 162) = 1;
          v12 = v15;
          if ( v16 > 7 )
            v12 = (_QWORD *)v15[0];
          v9 = WSP_ReplicaPeer_Set_PeerObjectId(a5, v12);
          if ( !v9 )
          {
            v13 = v15;
            if ( v16 > 7 )
              v13 = (_QWORD *)v15[0];
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
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids, v9);
  std::wstring::_Tidy_deallocate((__int64)v15);
  std::wstring::_Tidy_deallocate((__int64)v17);
  return v9;
}

```

## disassembly

```asm
0x180014b88  push    rbp
0x180014b8a  push    rbx
0x180014b8b  push    rsi
0x180014b8c  push    rdi
0x180014b8d  push    r12
0x180014b8f  push    r14
0x180014b91  push    r15
0x180014b93  mov     rbp, rsp
0x180014b96  sub     rsp, 80h
0x180014b9d  mov     rax, cs:__security_cookie
0x180014ba4  xor     rax, rsp
0x180014ba7  mov     [rbp+var_10], rax
0x180014bab  mov     r15b, r9b
0x180014bae  mov     ebx, r8d
0x180014bb1  mov     rdi, rdx
0x180014bb4  mov     r14, rcx
0x180014bb7  mov     rsi, [rbp+arg_20]
0x180014bbb  lea     r12, WPP_GLOBAL_Control
0x180014bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bc9  cmp     rcx, r12
0x180014bcc  jz      short loc_180014BE9
0x180014bce  test    byte ptr [rcx+1Ch], 4
0x180014bd2  jz      short loc_180014BE9
0x180014bd4  mov     edx, 0Ah
0x180014bd9  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014be0  mov     rcx, [rcx+10h]
0x180014be4  call    WPP_SF_
0x180014be9  lea     rcx, [rbp+var_30]
0x180014bed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014bf2  nop
0x180014bf3  lea     rcx, [rbp+var_50]
0x180014bf7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014bfc  nop
0x180014bfd  lea     rax, [rbp+var_30]
0x180014c01  mov     [rsp+80h+var_58], rax
0x180014c06  mov     [rsp+80h+var_60], r15b
0x180014c0b  mov     r9d, 14h
0x180014c11  mov     r8d, ebx
0x180014c14  mov     rdx, rdi
0x180014c17  mov     rcx, r14
0x180014c1a  call    ?EncodeReplicaPeerbjectId@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@_NAEAV23@@Z; EncodeReplicaPeerbjectId(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,bool,std::wstring &)
0x180014c1f  mov     ebx, eax
0x180014c21  test    eax, eax
0x180014c23  jnz     loc_180014D0A
0x180014c29  lea     r8, [rbp+var_50]
0x180014c2d  mov     rdx, rdi
0x180014c30  mov     rcx, r14
0x180014c33  call    ?EncodeReplicaPeerObjectIdForPartitionInternal@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; EncodeReplicaPeerObjectIdForPartitionInternal(std::wstring const &,std::wstring const &,std::wstring &)
0x180014c38  mov     ebx, eax
0x180014c3a  test    eax, eax
0x180014c3c  jnz     loc_180014D0A
0x180014c42  lea     rdx, [rbp+var_30]
0x180014c46  cmp     [rbp+var_18], 7
0x180014c4b  cmova   rdx, [rbp+var_30]
0x180014c50  mov     rcx, rsi
0x180014c53  call    WSP_ReplicaPeer_Set_ObjectId
0x180014c58  mov     ebx, eax
0x180014c5a  test    eax, eax
0x180014c5c  jnz     loc_180014D0A
0x180014c62  lea     rdx, [rbp+var_30]
0x180014c66  cmp     [rbp+var_18], 7
0x180014c6b  cmova   rdx, [rbp+var_30]
0x180014c70  mov     rcx, rsi
0x180014c73  call    WSP_ReplicaPeer_Set_UniqueId
0x180014c78  mov     ebx, eax
0x180014c7a  test    eax, eax
0x180014c7c  jnz     loc_180014D0A
0x180014c82  mov     [rsi+0F8h], r15b
0x180014c89  mov     byte ptr [rsi+0F9h], 1
0x180014c90  mov     word ptr [rsi+0A0h], 8001h
0x180014c99  mov     byte ptr [rsi+0A2h], 1
0x180014ca0  lea     rdx, [rbp+var_50]
0x180014ca4  cmp     [rbp+var_38], 7
0x180014ca9  cmova   rdx, [rbp+var_50]
0x180014cae  mov     rcx, rsi
0x180014cb1  call    WSP_ReplicaPeer_Set_PeerObjectId
0x180014cb6  mov     ebx, eax
0x180014cb8  test    eax, eax
0x180014cba  jnz     short loc_180014D0A
0x180014cbc  lea     rdx, [rbp+var_50]
0x180014cc0  cmp     [rbp+var_38], 7
0x180014cc5  cmova   rdx, [rbp+var_50]
0x180014cca  mov     rcx, rsi
0x180014ccd  call    WSP_ReplicaPeer_Set_PeerUniqueId
0x180014cd2  mov     ebx, eax
0x180014cd4  test    eax, eax
0x180014cd6  jnz     short loc_180014D0A
0x180014cd8  cmp     qword ptr [r14+18h], 7
0x180014cdd  jbe     short loc_180014CE2
0x180014cdf  mov     r14, [r14]
0x180014ce2  mov     rdx, r14
0x180014ce5  mov     rcx, rsi
0x180014ce8  call    WSP_ReplicaPeer_Set_PeerObjectName
0x180014ced  mov     ebx, eax
0x180014cef  test    eax, eax
0x180014cf1  jnz     short loc_180014D0A
0x180014cf3  cmp     qword ptr [rdi+18h], 7
0x180014cf8  jbe     short loc_180014CFD
0x180014cfa  mov     rdi, [rdi]
0x180014cfd  mov     rdx, rdi
0x180014d00  mov     rcx, rsi
0x180014d03  call    WSP_ReplicaPeer_Set_PeerSubsystemName
0x180014d08  mov     ebx, eax
0x180014d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d11  cmp     rcx, r12
0x180014d14  jz      short loc_180014D35
0x180014d16  test    byte ptr [rcx+1Ch], 1
0x180014d1a  jz      short loc_180014D35
0x180014d1c  mov     edx, 0Bh
0x180014d21  mov     r9d, ebx
0x180014d24  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014d2b  mov     rcx, [rcx+10h]
0x180014d2f  call    WPP_SF_d
0x180014d34  nop
0x180014d35  lea     rcx, [rbp+var_50]
0x180014d39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014d3e  nop
0x180014d3f  lea     rcx, [rbp+var_30]
0x180014d43  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014d48  mov     eax, ebx
0x180014d4a  mov     rcx, [rbp+var_10]
0x180014d4e  xor     rcx, rsp; StackCookie
0x180014d51  call    __security_check_cookie
0x180014d56  add     rsp, 80h
0x180014d5d  pop     r15
0x180014d5f  pop     r14
0x180014d61  pop     r12
0x180014d63  pop     rdi
0x180014d64  pop     rsi
0x180014d65  pop     rbx
0x180014d66  pop     rbp
0x180014d67  retn
```
