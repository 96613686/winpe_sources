# SrSmapiCreateReplicaPeer(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)

- ea: `0x180014a3c`
- end: `0x180014c1d`
- name: `?SrSmapiCreateReplicaPeer@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z`
- size: `481`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `reparse_path`

## callers

- `0x180014fa4`
- `0x1800155a8`
- `0x18001578c`

## callees

- `0x1800014e0`
- `0x18000590c`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x180014a3c`
- `0x180015908`
- `0x180015940`
- `0x180015978`
- `0x1800159b0`
- `0x1800159e8`
- `0x180015a20`
- `0x18001ae28`
- `0x18001aed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  std::wstring::wstring(v17);
  std::wstring::wstring(v15);
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
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v17);
  return v9;
}

```

## disassembly

```asm
0x180014a3c  push    rbp
0x180014a3e  push    rbx
0x180014a3f  push    rsi
0x180014a40  push    rdi
0x180014a41  push    r12
0x180014a43  push    r14
0x180014a45  push    r15
0x180014a47  mov     rbp, rsp
0x180014a4a  sub     rsp, 80h
0x180014a51  mov     rax, cs:__security_cookie
0x180014a58  xor     rax, rsp
0x180014a5b  mov     [rbp+var_10], rax
0x180014a5f  mov     r15b, r9b
0x180014a62  mov     ebx, r8d
0x180014a65  mov     rdi, rdx
0x180014a68  mov     r14, rcx
0x180014a6b  mov     rsi, [rbp+arg_20]
0x180014a6f  lea     r12, WPP_GLOBAL_Control
0x180014a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a7d  cmp     rcx, r12
0x180014a80  jz      short loc_180014A9D
0x180014a82  test    byte ptr [rcx+1Ch], 4
0x180014a86  jz      short loc_180014A9D
0x180014a88  mov     edx, 0Ah
0x180014a8d  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014a94  mov     rcx, [rcx+10h]
0x180014a98  call    WPP_SF_
0x180014a9d  lea     rcx, [rbp+var_30]
0x180014aa1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014aa6  nop
0x180014aa7  lea     rcx, [rbp+var_50]
0x180014aab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014ab0  nop
0x180014ab1  lea     rax, [rbp+var_30]
0x180014ab5  mov     [rsp+80h+var_58], rax
0x180014aba  mov     [rsp+80h+var_60], r15b
0x180014abf  mov     r9d, 14h
0x180014ac5  mov     r8d, ebx
0x180014ac8  mov     rdx, rdi
0x180014acb  mov     rcx, r14
0x180014ace  call    ?EncodeReplicaPeerbjectId@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@_NAEAV23@@Z; EncodeReplicaPeerbjectId(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,bool,std::wstring &)
0x180014ad3  mov     ebx, eax
0x180014ad5  test    eax, eax
0x180014ad7  jnz     loc_180014BBE
0x180014add  lea     r8, [rbp+var_50]
0x180014ae1  mov     rdx, rdi
0x180014ae4  mov     rcx, r14
0x180014ae7  call    ?EncodeReplicaPeerObjectIdForPartitionInternal@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; EncodeReplicaPeerObjectIdForPartitionInternal(std::wstring const &,std::wstring const &,std::wstring &)
0x180014aec  mov     ebx, eax
0x180014aee  test    eax, eax
0x180014af0  jnz     loc_180014BBE
0x180014af6  lea     rdx, [rbp+var_30]
0x180014afa  cmp     [rbp+var_18], 7
0x180014aff  cmova   rdx, [rbp+var_30]
0x180014b04  mov     rcx, rsi
0x180014b07  call    WSP_ReplicaPeer_Set_ObjectId
0x180014b0c  mov     ebx, eax
0x180014b0e  test    eax, eax
0x180014b10  jnz     loc_180014BBE
0x180014b16  lea     rdx, [rbp+var_30]
0x180014b1a  cmp     [rbp+var_18], 7
0x180014b1f  cmova   rdx, [rbp+var_30]
0x180014b24  mov     rcx, rsi
0x180014b27  call    WSP_ReplicaPeer_Set_UniqueId
0x180014b2c  mov     ebx, eax
0x180014b2e  test    eax, eax
0x180014b30  jnz     loc_180014BBE
0x180014b36  mov     [rsi+0F8h], r15b
0x180014b3d  mov     byte ptr [rsi+0F9h], 1
0x180014b44  mov     word ptr [rsi+0A0h], 8001h
0x180014b4d  mov     byte ptr [rsi+0A2h], 1
0x180014b54  lea     rdx, [rbp+var_50]
0x180014b58  cmp     [rbp+var_38], 7
0x180014b5d  cmova   rdx, [rbp+var_50]
0x180014b62  mov     rcx, rsi
0x180014b65  call    WSP_ReplicaPeer_Set_PeerObjectId
0x180014b6a  mov     ebx, eax
0x180014b6c  test    eax, eax
0x180014b6e  jnz     short loc_180014BBE
0x180014b70  lea     rdx, [rbp+var_50]
0x180014b74  cmp     [rbp+var_38], 7
0x180014b79  cmova   rdx, [rbp+var_50]
0x180014b7e  mov     rcx, rsi
0x180014b81  call    WSP_ReplicaPeer_Set_PeerUniqueId
0x180014b86  mov     ebx, eax
0x180014b88  test    eax, eax
0x180014b8a  jnz     short loc_180014BBE
0x180014b8c  cmp     qword ptr [r14+18h], 7
0x180014b91  jbe     short loc_180014B96
0x180014b93  mov     r14, [r14]
0x180014b96  mov     rdx, r14
0x180014b99  mov     rcx, rsi
0x180014b9c  call    WSP_ReplicaPeer_Set_PeerObjectName
0x180014ba1  mov     ebx, eax
0x180014ba3  test    eax, eax
0x180014ba5  jnz     short loc_180014BBE
0x180014ba7  cmp     qword ptr [rdi+18h], 7
0x180014bac  jbe     short loc_180014BB1
0x180014bae  mov     rdi, [rdi]
0x180014bb1  mov     rdx, rdi
0x180014bb4  mov     rcx, rsi
0x180014bb7  call    WSP_ReplicaPeer_Set_PeerSubsystemName
0x180014bbc  mov     ebx, eax
0x180014bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bc5  cmp     rcx, r12
0x180014bc8  jz      short loc_180014BE9
0x180014bca  test    byte ptr [rcx+1Ch], 1
0x180014bce  jz      short loc_180014BE9
0x180014bd0  mov     edx, 0Bh
0x180014bd5  mov     r9d, ebx
0x180014bd8  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014bdf  mov     rcx, [rcx+10h]
0x180014be3  call    WPP_SF_d
0x180014be8  nop
0x180014be9  lea     rcx, [rbp+var_50]
0x180014bed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014bf2  nop
0x180014bf3  lea     rcx, [rbp+var_30]
0x180014bf7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014bfc  mov     eax, ebx
0x180014bfe  mov     rcx, [rbp+var_10]
0x180014c02  xor     rcx, rsp; StackCookie
0x180014c05  call    __security_check_cookie
0x180014c0a  add     rsp, 80h
0x180014c11  pop     r15
0x180014c13  pop     r14
0x180014c15  pop     r12
0x180014c17  pop     rdi
0x180014c18  pop     rsi
0x180014c19  pop     rbx
0x180014c1a  pop     rbp
0x180014c1b  retn
```
