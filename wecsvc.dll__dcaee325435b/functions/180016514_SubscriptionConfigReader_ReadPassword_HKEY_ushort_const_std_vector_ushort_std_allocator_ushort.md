# SubscriptionConfigReader::ReadPassword(HKEY__ *,ushort const *,std::vector<ushort,std::allocator<ushort>> &)

- ea: `0x180016514`
- end: `0x1800165b9`
- name: `?ReadPassword@SubscriptionConfigReader@@IEBA_NPEAUHKEY__@@PEBGAEAV?$vector@GV?$allocator@G@std@@@std@@@Z`
- size: `165`
- prototype: `char __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001483c`
- `0x180015c30`

## callees

- `0x1800062d4`
- `0x1800128c0`
- `0x180012ddc`
- `0x180016514`
- `0x18001b734`
- `0x18001fe50`

## pseudocode

```c
char __fastcall SubscriptionConfigReader::ReadPassword(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  char v9; // bl
  __int16 v11; // [rsp+20h] [rbp-48h] BYREF
  _WORD v12[8]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v13; // [rsp+38h] [rbp-30h]
  __int64 v14; // [rsp+40h] [rbp-28h]

  v14 = 7;
  v13 = 0;
  v12[0] = 0;
  a4[1] = *a4;
  v11 = 0;
  std::vector<unsigned short>::push_back(a4, &v11);
  RegReadStringValue(a2, a3, v12);
  if ( v13 )
  {
    CredentialManager::ReadCredentialByEntryId(v8, v12, a4);
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v12, v7, 0);
  return v9;
}

```

## disassembly

```asm
0x180016514  push    rbx
0x180016516  push    rsi
0x180016517  push    rdi
0x180016518  sub     rsp, 50h
0x18001651c  mov     rax, cs:__security_cookie
0x180016523  xor     rax, rsp
0x180016526  mov     [rsp+68h+var_20], rax
0x18001652b  mov     rsi, r9
0x18001652e  mov     rdi, r8
0x180016531  mov     rbx, rdx
0x180016534  mov     [rsp+68h+var_28], 7
0x18001653d  mov     [rsp+68h+var_30], 0
0x180016546  xor     eax, eax
0x180016548  mov     [rsp+68h+var_40], ax
0x18001654d  mov     rax, [r9]
0x180016550  mov     [r9+8], rax
0x180016554  xor     eax, eax
0x180016556  mov     [rsp+68h+var_48], ax
0x18001655b  lea     rdx, [rsp+68h+var_48]
0x180016560  mov     rcx, r9
0x180016563  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x180016568  lea     r8, [rsp+68h+var_40]
0x18001656d  mov     rdx, rdi
0x180016570  mov     rcx, rbx
0x180016573  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180016578  cmp     [rsp+68h+var_30], 0
0x18001657e  jnz     short loc_180016584
0x180016580  xor     ebx, ebx
0x180016582  jmp     short loc_180016593
0x180016584  mov     r8, rsi
0x180016587  lea     rdx, [rsp+68h+var_40]
0x18001658c  call    ?ReadCredentialByEntryId@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@GV?$allocator@G@std@@@3@@Z; CredentialManager::ReadCredentialByEntryId(std::wstring const &,std::vector<ushort> &)
0x180016591  mov     bl, 1
0x180016593  xor     r8d, r8d
0x180016596  mov     dl, 1
0x180016598  lea     rcx, [rsp+68h+var_40]
0x18001659d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800165a2  mov     al, bl
0x1800165a4  mov     rcx, [rsp+68h+var_20]
0x1800165a9  xor     rcx, rsp; StackCookie
0x1800165ac  call    __security_check_cookie
0x1800165b1  add     rsp, 50h
0x1800165b5  pop     rdi
0x1800165b6  pop     rsi
0x1800165b7  pop     rbx
0x1800165b8  retn
```
