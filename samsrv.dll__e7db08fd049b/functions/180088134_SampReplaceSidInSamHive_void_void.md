# SampReplaceSidInSamHive(void *,void *)

- ea: `0x180088134`
- end: `0x18008830b`
- name: `?SampReplaceSidInSamHive@@YAJPEAX0@Z`
- size: `471`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800887a0`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x180088134`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1800881b0`
- `ntdll!RtlAdjustPrivilege` at `0x1800881cb`
- `ntdll!RtlAdjustPrivilege` at `0x1800881e4`
- `ntdll!RtlAdjustPrivilege` at `0x1800881fd`
- `ntdll!RtlAdjustPrivilege` at `0x180088216`
- `ntdll!RtlAdjustPrivilege` at `0x18008824b`
- `ntdll!RtlAdjustPrivilege` at `0x180088265`
- `ntdll!RtlAdjustPrivilege` at `0x18008827f`
- `ntdll!RtlAdjustPrivilege` at `0x180088299`
- `ntdll!RtlAdjustPrivilege` at `0x1800882b3`
- `ntdll!RtlAdjustPrivilege` at `0x1800881b0`
- `ntdll!RtlAdjustPrivilege` at `0x1800881cb`
- `ntdll!RtlAdjustPrivilege` at `0x1800881e4`
- `ntdll!RtlAdjustPrivilege` at `0x1800881fd`
- `ntdll!RtlAdjustPrivilege` at `0x180088216`
- `ntdll!RtlAdjustPrivilege` at `0x18008824b`
- `ntdll!RtlAdjustPrivilege` at `0x180088265`
- `ntdll!RtlAdjustPrivilege` at `0x18008827f`
- `ntdll!RtlAdjustPrivilege` at `0x180088299`
- `ntdll!RtlAdjustPrivilege` at `0x1800882b3`
- `setupcl!SclExecuteRequest` at `0x18008822f`
- `setupcl!SclExecuteRequest` at `0x18008822f`

## pseudocode

```c
__int64 __fastcall SampReplaceSidInSamHive(void *a1, void *a2)
{
  NTSTATUS v4; // ebx
  unsigned __int8 OldValue; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v7; // [rsp+31h] [rbp-CFh] BYREF
  unsigned __int8 v8; // [rsp+32h] [rbp-CEh] BYREF
  unsigned __int8 v9; // [rsp+33h] [rbp-CDh] BYREF
  unsigned __int8 v10[12]; // [rsp+34h] [rbp-CCh] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  void *v12; // [rsp+48h] [rbp-B8h]
  void *v13; // [rsp+50h] [rbp-B0h]

  OldValue = 1;
  v7 = 1;
  v8 = 1;
  v9 = 1;
  v10[0] = 1;
  memset_0(&v11, 0, 0x478u);
  v11 = 516;
  v12 = a1;
  v13 = a2;
  v4 = RtlAdjustPrivilege(0x11u, 1u, 0, &OldValue);
  if ( v4 >= 0 )
  {
    v4 = RtlAdjustPrivilege(0x12u, 1u, 0, &v7);
    if ( v4 >= 0 )
    {
      v4 = RtlAdjustPrivilege(9u, 1u, 0, &v8);
      if ( v4 >= 0 )
      {
        v4 = RtlAdjustPrivilege(8u, 1u, 0, &v9);
        if ( v4 >= 0 )
        {
          v4 = RtlAdjustPrivilege(7u, 1u, 0, v10);
          if ( v4 >= 0 )
            v4 = SclExecuteRequest(&v11, 0, 0, 0);
        }
      }
    }
  }
  if ( !OldValue )
    RtlAdjustPrivilege(0x11u, 0, 0, &OldValue);
  if ( !v7 )
    RtlAdjustPrivilege(0x12u, 0, 0, &v7);
  if ( !v8 )
    RtlAdjustPrivilege(9u, 0, 0, &v8);
  if ( !v9 )
    RtlAdjustPrivilege(8u, 0, 0, &v9);
  if ( !v10[0] )
    RtlAdjustPrivilege(7u, 0, 0, v10);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 208, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v4, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180088134  mov     [rsp-8+arg_10], rbx
0x180088139  mov     [rsp-8+arg_18], rdi
0x18008813e  push    rbp
0x18008813f  lea     rbp, [rsp-3D0h]
0x180088147  sub     rsp, 4D0h
0x18008814e  mov     rax, cs:__security_cookie
0x180088155  xor     rax, rsp
0x180088158  mov     [rbp+3D0h+var_10], rax
0x18008815f  mov     rdi, rdx
0x180088162  mov     [rsp+4D0h+OldValue], 1
0x180088167  mov     rbx, rcx
0x18008816a  mov     [rsp+4D0h+var_49F], 1
0x18008816f  xor     edx, edx; Val
0x180088171  mov     [rsp+4D0h+var_49E], 1
0x180088176  lea     rcx, [rsp+4D0h+var_490]; void *
0x18008817b  mov     [rsp+4D0h+var_49D], 1
0x180088180  mov     r8d, 478h; Size
0x180088186  mov     [rsp+4D0h+var_49C], 1
0x18008818b  call    memset_0
0x180088190  xor     r8d, r8d; ForThread
0x180088193  mov     [rsp+4D0h+var_490], 204h
0x18008819b  lea     r9, [rsp+4D0h+OldValue]; OldValue
0x1800881a0  mov     [rsp+4D0h+var_488], rbx
0x1800881a5  mov     dl, 1; NewValue
0x1800881a7  mov     [rsp+4D0h+var_480], rdi
0x1800881ac  lea     ecx, [r8+11h]; Privilege
0x1800881b0  call    cs:__imp_RtlAdjustPrivilege
0x1800881b6  xor     edi, edi
0x1800881b8  mov     ebx, eax
0x1800881ba  test    eax, eax
0x1800881bc  js      short loc_180088237
0x1800881be  lea     r9, [rsp+4D0h+var_49F]; OldValue
0x1800881c3  xor     r8d, r8d; ForThread
0x1800881c6  mov     dl, 1; NewValue
0x1800881c8  lea     ecx, [rdi+12h]; Privilege
0x1800881cb  call    cs:__imp_RtlAdjustPrivilege
0x1800881d1  mov     ebx, eax
0x1800881d3  test    eax, eax
0x1800881d5  js      short loc_180088237
0x1800881d7  lea     r9, [rsp+4D0h+var_49E]; OldValue
0x1800881dc  xor     r8d, r8d; ForThread
0x1800881df  mov     dl, 1; NewValue
0x1800881e1  lea     ecx, [rdi+9]; Privilege
0x1800881e4  call    cs:__imp_RtlAdjustPrivilege
0x1800881ea  mov     ebx, eax
0x1800881ec  test    eax, eax
0x1800881ee  js      short loc_180088237
0x1800881f0  lea     r9, [rsp+4D0h+var_49D]; OldValue
0x1800881f5  xor     r8d, r8d; ForThread
0x1800881f8  mov     dl, 1; NewValue
0x1800881fa  lea     ecx, [rdi+8]; Privilege
0x1800881fd  call    cs:__imp_RtlAdjustPrivilege
0x180088203  mov     ebx, eax
0x180088205  test    eax, eax
0x180088207  js      short loc_180088237
0x180088209  lea     r9, [rsp+4D0h+var_49C]; OldValue
0x18008820e  xor     r8d, r8d; ForThread
0x180088211  mov     dl, 1; NewValue
0x180088213  lea     ecx, [rdi+7]; Privilege
0x180088216  call    cs:__imp_RtlAdjustPrivilege
0x18008821c  mov     ebx, eax
0x18008821e  test    eax, eax
0x180088220  js      short loc_180088237
0x180088222  xor     r9d, r9d
0x180088225  lea     rcx, [rsp+4D0h+var_490]
0x18008822a  xor     r8d, r8d
0x18008822d  xor     edx, edx
0x18008822f  call    cs:__imp_SclExecuteRequest
0x180088235  mov     ebx, eax
0x180088237  cmp     [rsp+4D0h+OldValue], dil
0x18008823c  jnz     short loc_180088251
0x18008823e  xor     edx, edx; NewValue
0x180088240  lea     r9, [rsp+4D0h+OldValue]; OldValue
0x180088245  xor     r8d, r8d; ForThread
0x180088248  lea     ecx, [rdx+11h]; Privilege
0x18008824b  call    cs:__imp_RtlAdjustPrivilege
0x180088251  cmp     [rsp+4D0h+var_49F], dil
0x180088256  jnz     short loc_18008826B
0x180088258  xor     edx, edx; NewValue
0x18008825a  lea     r9, [rsp+4D0h+var_49F]; OldValue
0x18008825f  xor     r8d, r8d; ForThread
0x180088262  lea     ecx, [rdx+12h]; Privilege
0x180088265  call    cs:__imp_RtlAdjustPrivilege
0x18008826b  cmp     [rsp+4D0h+var_49E], dil
0x180088270  jnz     short loc_180088285
0x180088272  xor     edx, edx; NewValue
0x180088274  lea     r9, [rsp+4D0h+var_49E]; OldValue
0x180088279  xor     r8d, r8d; ForThread
0x18008827c  lea     ecx, [rdx+9]; Privilege
0x18008827f  call    cs:__imp_RtlAdjustPrivilege
0x180088285  cmp     [rsp+4D0h+var_49D], dil
0x18008828a  jnz     short loc_18008829F
0x18008828c  xor     edx, edx; NewValue
0x18008828e  lea     r9, [rsp+4D0h+var_49D]; OldValue
0x180088293  xor     r8d, r8d; ForThread
0x180088296  lea     ecx, [rdx+8]; Privilege
0x180088299  call    cs:__imp_RtlAdjustPrivilege
0x18008829f  cmp     [rsp+4D0h+var_49C], dil
0x1800882a4  jnz     short loc_1800882B9
0x1800882a6  xor     edx, edx; NewValue
0x1800882a8  lea     r9, [rsp+4D0h+var_49C]; OldValue
0x1800882ad  xor     r8d, r8d; ForThread
0x1800882b0  lea     ecx, [rdx+7]; Privilege
0x1800882b3  call    cs:__imp_RtlAdjustPrivilege
0x1800882b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800882c0  test    dword ptr [rcx+44h], 20000h
0x1800882c7  jz      short loc_1800882E5
0x1800882c9  mov     rcx, [rcx+38h]
0x1800882cd  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x1800882d4  mov     edx, 0D0h
0x1800882d9  mov     [rsp+4D0h+var_4B0], ebx
0x1800882dd  mov     r9d, ebx
0x1800882e0  call    WPP_SF_Dd
0x1800882e5  mov     eax, ebx
0x1800882e7  mov     rcx, [rbp+3D0h+var_10]
0x1800882ee  xor     rcx, rsp; StackCookie
0x1800882f1  call    __security_check_cookie
0x1800882f6  lea     r11, [rsp+4D0h+var_s0]
0x1800882fe  mov     rbx, [r11+20h]
0x180088302  mov     rdi, [r11+28h]
0x180088306  mov     rsp, r11
0x180088309  pop     rbp
0x18008830a  retn
```
