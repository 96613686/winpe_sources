# CSrClusterEventListener::ProcessGroupDeleteNotification(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180018020`
- end: `0x18001810d`
- name: `?ProcessGroupDeleteNotification@CSrClusterEventListener@@AEAAKAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180017cc4`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x180018020`
- `0x18001c684`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      std::wstring::wstring(v8, v5 + 24);
      v6 = SrSmapiPostReplicationGroupDepartureEvent(v8, *(_QWORD *)(a1 + 16));
      std::wstring::_Tidy_deallocate(v8);
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
0x180018020  mov     [rsp+arg_10], rbx
0x180018025  mov     [rsp+arg_18], rsi
0x18001802a  push    rdi
0x18001802b  sub     rsp, 50h
0x18001802f  mov     rax, cs:__security_cookie
0x180018036  xor     rax, rsp
0x180018039  mov     [rsp+58h+var_18], rax
0x18001803e  mov     rbx, rdx
0x180018041  mov     rdi, rcx
0x180018044  lea     rsi, WPP_GLOBAL_Control
0x18001804b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018052  cmp     rcx, rsi
0x180018055  jz      short loc_180018079
0x180018057  test    byte ptr [rcx+1Ch], 4
0x18001805b  jz      short loc_180018079
0x18001805d  mov     edx, 12h
0x180018062  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x180018069  mov     rcx, [rcx+10h]
0x18001806d  call    WPP_SF_
0x180018072  mov     rcx, cs:WPP_GLOBAL_Control
0x180018079  mov     rdx, [rbx]
0x18001807c  mov     rax, [rbx+8]
0x180018080  sub     rax, rdx
0x180018083  cmp     rax, 220h
0x180018089  jnb     short loc_180018092
0x18001808b  mov     ebx, 57h ; 'W'
0x180018090  jmp     short loc_1800180CA
0x180018092  xor     ebx, ebx
0x180018094  cmp     dword ptr [rdi+18h], 2
0x180018098  jnz     short loc_1800180CA
0x18001809a  add     rdx, 18h
0x18001809e  lea     rcx, [rsp+58h+var_38]
0x1800180a3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800180a8  nop
0x1800180a9  mov     rdx, [rdi+10h]
0x1800180ad  lea     rcx, [rsp+58h+var_38]
0x1800180b2  call    ?SrSmapiPostReplicationGroupDepartureEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupDepartureEvent(std::wstring const &,_MI_Context *)
0x1800180b7  mov     ebx, eax
0x1800180b9  lea     rcx, [rsp+58h+var_38]
0x1800180be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800180c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180ca  cmp     rcx, rsi
0x1800180cd  jz      short loc_1800180ED
0x1800180cf  test    byte ptr [rcx+1Ch], 1
0x1800180d3  jz      short loc_1800180ED
0x1800180d5  mov     edx, 13h
0x1800180da  mov     r9d, ebx
0x1800180dd  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x1800180e4  mov     rcx, [rcx+10h]
0x1800180e8  call    WPP_SF_d
0x1800180ed  mov     eax, ebx
0x1800180ef  mov     rcx, [rsp+58h+var_18]
0x1800180f4  xor     rcx, rsp; StackCookie
0x1800180f7  call    __security_check_cookie
0x1800180fc  mov     rbx, [rsp+58h+arg_10]
0x180018101  mov     rsi, [rsp+58h+arg_18]
0x180018106  add     rsp, 50h
0x18001810a  pop     rdi
0x18001810b  retn
```
