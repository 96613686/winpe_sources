# CSrClusterEventListener::ProcessGroupDeleteNotification(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800181a0`
- end: `0x18001828c`
- name: `?ProcessGroupDeleteNotification@CSrClusterEventListener@@AEAAKAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180017e70`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x1800181a0`
- `0x18001c588`

## pseudocode

```c
__int64 __fastcall CSrClusterEventListener::ProcessGroupDeleteNotification(__int64 a1, __int64 *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  _BYTE v8[32]; // [rsp+20h] [rbp-38h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *a2;
  if ( (unsigned __int64)(a2[1] - *a2) >= 0x220 )
  {
    v6 = 0;
    if ( *(_DWORD *)(a1 + 24) == 2 )
    {
      std::wstring::wstring((__int64)v8, v5 + 24);
      v6 = SrSmapiPostReplicationGroupDepartureEvent(v8, *(_QWORD *)(a1 + 16));
      std::wstring::_Tidy_deallocate((__int64)v8);
      v4 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_d(v4[2], 19, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800181a0  mov     [rsp+arg_10], rbx
0x1800181a5  mov     [rsp+arg_18], rsi
0x1800181aa  push    rdi
0x1800181ab  sub     rsp, 50h
0x1800181af  mov     rax, cs:__security_cookie
0x1800181b6  xor     rax, rsp
0x1800181b9  mov     [rsp+58h+var_18], rax
0x1800181be  mov     rbx, rdx
0x1800181c1  mov     rdi, rcx
0x1800181c4  lea     rsi, WPP_GLOBAL_Control
0x1800181cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181d2  cmp     rcx, rsi
0x1800181d5  jz      short loc_1800181F9
0x1800181d7  test    byte ptr [rcx+1Ch], 4
0x1800181db  jz      short loc_1800181F9
0x1800181dd  mov     edx, 12h
0x1800181e2  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x1800181e9  mov     rcx, [rcx+10h]
0x1800181ed  call    WPP_SF_
0x1800181f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181f9  mov     rdx, [rbx]
0x1800181fc  mov     rax, [rbx+8]
0x180018200  sub     rax, rdx
0x180018203  cmp     rax, 220h
0x180018209  jnb     short loc_180018212
0x18001820b  mov     ebx, 57h ; 'W'
0x180018210  jmp     short loc_18001824A
0x180018212  xor     ebx, ebx
0x180018214  cmp     dword ptr [rdi+18h], 2
0x180018218  jnz     short loc_18001824A
0x18001821a  add     rdx, 18h
0x18001821e  lea     rcx, [rsp+58h+var_38]
0x180018223  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180018228  nop
0x180018229  mov     rdx, [rdi+10h]
0x18001822d  lea     rcx, [rsp+58h+var_38]
0x180018232  call    ?SrSmapiPostReplicationGroupDepartureEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupDepartureEvent(std::wstring const &,_MI_Context *)
0x180018237  mov     ebx, eax
0x180018239  lea     rcx, [rsp+58h+var_38]
0x18001823e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018243  mov     rcx, cs:WPP_GLOBAL_Control
0x18001824a  cmp     rcx, rsi
0x18001824d  jz      short loc_18001826D
0x18001824f  test    byte ptr [rcx+1Ch], 1
0x180018253  jz      short loc_18001826D
0x180018255  mov     edx, 13h
0x18001825a  mov     r9d, ebx
0x18001825d  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x180018264  mov     rcx, [rcx+10h]
0x180018268  call    WPP_SF_d
0x18001826d  mov     eax, ebx
0x18001826f  mov     rcx, [rsp+58h+var_18]
0x180018274  xor     rcx, rsp; StackCookie
0x180018277  call    __security_check_cookie
0x18001827c  mov     rbx, [rsp+58h+arg_10]
0x180018281  mov     rsi, [rsp+58h+arg_18]
0x180018286  add     rsp, 50h
0x18001828a  pop     rdi
0x18001828b  retn
```
