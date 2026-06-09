# RegistryPaths::GetLegacyChannelRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x140019094`
- end: `0x140019156`
- name: `?GetLegacyChannelRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z`
- size: `194`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14001d828`
- `0x14002ab70`
- `0x14002bd08`

## callees

- `0x14000d6e8`
- `0x140019094`
- `0x14001915c`
- `0x14001a9b8`
- `0x140022cec`

## pseudocode

```c
__int64 __fastcall RegistryPaths::GetLegacyChannelRegPath(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  unsigned int EventlogServiceRegPath; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(a1, a3, a4);
  if ( EventlogServiceRegPath )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return EventlogServiceRegPath;
    }
    v8 = 13;
    goto LABEL_13;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(a4, 92)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          a4,
                          *a2,
                          a2[1]) )
  {
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  EventlogServiceRegPath = 14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 14;
LABEL_13:
    WPP_SF_d(v7[2], v8, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids, EventlogServiceRegPath);
  }
  return EventlogServiceRegPath;
}

```

## disassembly

```asm
0x140019094  mov     [rsp+arg_0], rbx
0x140019099  mov     [rsp+arg_8], rsi
0x14001909e  push    rdi
0x14001909f  sub     rsp, 20h
0x1400190a3  mov     rax, r8
0x1400190a6  mov     rsi, rdx
0x1400190a9  mov     rdx, rax
0x1400190ac  mov     r8, r9
0x1400190af  mov     rdi, r9
0x1400190b2  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400190b7  mov     ebx, eax
0x1400190b9  test    eax, eax
0x1400190bb  jz      short loc_1400190E3
0x1400190bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190c4  lea     rdx, WPP_GLOBAL_Control
0x1400190cb  cmp     rcx, rdx
0x1400190ce  jz      short loc_140019144
0x1400190d0  test    byte ptr [rcx+1Ch], 4
0x1400190d4  jz      short loc_140019144
0x1400190d6  cmp     byte ptr [rcx+19h], 2
0x1400190da  jb      short loc_140019144
0x1400190dc  mov     edx, 0Dh
0x1400190e1  jmp     short loc_140019131
0x1400190e3  mov     edx, 5Ch ; '\'
0x1400190e8  mov     rcx, rdi
0x1400190eb  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400190f0  test    al, al
0x1400190f2  jz      short loc_14001910B
0x1400190f4  mov     r8, [rsi+8]
0x1400190f8  mov     rcx, rdi
0x1400190fb  mov     rdx, [rsi]
0x1400190fe  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140019103  test    al, al
0x140019105  jz      short loc_14001910B
0x140019107  xor     eax, eax
0x140019109  jmp     short loc_140019146
0x14001910b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019112  lea     rdx, WPP_GLOBAL_Control
0x140019119  mov     ebx, 0Eh
0x14001911e  cmp     rcx, rdx
0x140019121  jz      short loc_140019144
0x140019123  test    byte ptr [rcx+1Ch], 4
0x140019127  jz      short loc_140019144
0x140019129  cmp     byte ptr [rcx+19h], 2
0x14001912d  jb      short loc_140019144
0x14001912f  mov     edx, ebx
0x140019131  mov     rcx, [rcx+10h]
0x140019135  lea     r8, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids
0x14001913c  mov     r9d, ebx
0x14001913f  call    WPP_SF_d
0x140019144  mov     eax, ebx
0x140019146  mov     rbx, [rsp+28h+arg_0]
0x14001914b  mov     rsi, [rsp+28h+arg_8]
0x140019150  add     rsp, 20h
0x140019154  pop     rdi
0x140019155  retn
```
