# RegistryPaths::GetPersistedAutoLoggerRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14002f198`
- end: `0x14002f27e`
- name: `?GetPersistedAutoLoggerRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z`
- size: `230`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140013658`
- `0x140014988`
- `0x14001e458`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x14000d6e8`
- `0x14001a9b8`
- `0x140022cec`
- `0x14002f0d8`
- `0x14002f198`

## pseudocode

```c
__int64 __fastcall RegistryPaths::GetPersistedAutoLoggerRegPath(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rcx
  __int64 v7; // r10
  unsigned int AutoLoggersRegPath; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _BYTE v12[40]; // [rsp+20h] [rbp-28h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v12);
  AutoLoggersRegPath = RegistryPaths::GetAutoLoggersRegPath(v6, v7, a4, v12);
  if ( AutoLoggersRegPath )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    v10 = 11;
    goto LABEL_13;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(a4, 92)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          a4,
                          *a2,
                          a2[1]) )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v12);
    return 0;
  }
  v9 = WPP_GLOBAL_Control;
  AutoLoggersRegPath = 14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 12;
LABEL_13:
    WPP_SF_d(v9[2], v10, WPP_102b51fcdce430aa865b164defc92936_Traceguids, AutoLoggersRegPath);
  }
LABEL_14:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v12);
  return AutoLoggersRegPath;
}

```

## disassembly

```asm
0x14002f198  mov     [rsp+arg_0], rbx
0x14002f19d  mov     [rsp+arg_8], rsi
0x14002f1a2  push    rdi
0x14002f1a3  sub     rsp, 40h
0x14002f1a7  lea     rcx, [rsp+48h+var_28]
0x14002f1ac  mov     rdi, r9
0x14002f1af  mov     r10, r8
0x14002f1b2  mov     rsi, rdx
0x14002f1b5  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002f1ba  mov     rdx, r10
0x14002f1bd  lea     r9, [rsp+48h+var_28]
0x14002f1c2  mov     r8, rdi
0x14002f1c5  call    ?GetAutoLoggersRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggersRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002f1ca  mov     ebx, eax
0x14002f1cc  test    eax, eax
0x14002f1ce  jz      short loc_14002F1F6
0x14002f1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f1d7  lea     rdx, WPP_GLOBAL_Control
0x14002f1de  cmp     rcx, rdx
0x14002f1e1  jz      short loc_14002F262
0x14002f1e3  test    byte ptr [rcx+1Ch], 4
0x14002f1e7  jz      short loc_14002F262
0x14002f1e9  cmp     byte ptr [rcx+19h], 2
0x14002f1ed  jb      short loc_14002F262
0x14002f1ef  mov     edx, 0Bh
0x14002f1f4  jmp     short loc_14002F24F
0x14002f1f6  mov     edx, 5Ch ; '\'
0x14002f1fb  mov     rcx, rdi
0x14002f1fe  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002f203  test    al, al
0x14002f205  jz      short loc_14002F228
0x14002f207  mov     r8, [rsi+8]
0x14002f20b  mov     rcx, rdi
0x14002f20e  mov     rdx, [rsi]
0x14002f211  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002f216  test    al, al
0x14002f218  jz      short loc_14002F228
0x14002f21a  lea     rcx, [rsp+48h+var_28]
0x14002f21f  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002f224  xor     eax, eax
0x14002f226  jmp     short loc_14002F26E
0x14002f228  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f22f  lea     rdx, WPP_GLOBAL_Control
0x14002f236  mov     ebx, 0Eh
0x14002f23b  cmp     rcx, rdx
0x14002f23e  jz      short loc_14002F262
0x14002f240  test    byte ptr [rcx+1Ch], 4
0x14002f244  jz      short loc_14002F262
0x14002f246  cmp     byte ptr [rcx+19h], 2
0x14002f24a  jb      short loc_14002F262
0x14002f24c  lea     edx, [rbx-2]
0x14002f24f  mov     rcx, [rcx+10h]
0x14002f253  lea     r8, WPP_102b51fcdce430aa865b164defc92936_Traceguids
0x14002f25a  mov     r9d, ebx
0x14002f25d  call    WPP_SF_d
0x14002f262  lea     rcx, [rsp+48h+var_28]
0x14002f267  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002f26c  mov     eax, ebx
0x14002f26e  mov     rbx, [rsp+48h+arg_0]
0x14002f273  mov     rsi, [rsp+48h+arg_8]
0x14002f278  add     rsp, 40h
0x14002f27c  pop     rdi
0x14002f27d  retn
```
