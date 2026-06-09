# SrSmapiCreateReplicaPeerFromReplicationGroup(_MSFT_ReplicaPeer const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_WSP_ReplicaPeer *)

- ea: `0x1800150f0`
- end: `0x1800151f8`
- name: `?SrSmapiCreateReplicaPeerFromReplicationGroup@@YA?AW4_MI_Result@@PEBU_MSFT_ReplicaPeer@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1PEAU_WSP_ReplicaPeer@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009554`

## callees

- `0x1800014e0`
- `0x1800058d4`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180014b88`
- `0x1800150f0`
- `0x18001c098`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicaPeerFromReplicationGroup(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  unsigned int ReplicaPeer; // ebx
  int v10; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v11[4]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids);
  std::wstring::wstring((__int64)v12);
  v10 = 0;
  std::wstring::wstring((__int64)v11);
  ReplicaPeer = UnpackObjectId(*(_QWORD *)(a1 + 64), &v10, 0, v11);
  if ( !ReplicaPeer )
    ReplicaPeer = SrSmapiCreateReplicaPeer(a2, a3, v10, 0, a4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids, ReplicaPeer);
  std::wstring::_Tidy_deallocate((__int64)v11);
  std::wstring::_Tidy_deallocate((__int64)v12);
  return ReplicaPeer;
}

```

## disassembly

```asm
0x1800150f0  push    rbx
0x1800150f2  push    rbp
0x1800150f3  push    rsi
0x1800150f4  push    rdi
0x1800150f5  push    r14
0x1800150f7  sub     rsp, 80h
0x1800150fe  mov     rax, cs:__security_cookie
0x180015105  xor     rax, rsp
0x180015108  mov     [rsp+0A8h+var_30], rax
0x18001510d  mov     rbp, r9
0x180015110  mov     rsi, r8
0x180015113  mov     rdi, rdx
0x180015116  mov     rbx, rcx
0x180015119  lea     r14, WPP_GLOBAL_Control
0x180015120  mov     rcx, cs:WPP_GLOBAL_Control
0x180015127  cmp     rcx, r14
0x18001512a  jz      short loc_180015147
0x18001512c  test    byte ptr [rcx+1Ch], 4
0x180015130  jz      short loc_180015147
0x180015132  mov     edx, 10h
0x180015137  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x18001513e  mov     rcx, [rcx+10h]
0x180015142  call    WPP_SF_
0x180015147  lea     rcx, [rsp+0A8h+var_50]
0x18001514c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015151  nop
0x180015152  mov     [rsp+0A8h+var_78], 0
0x18001515a  lea     rcx, [rsp+0A8h+var_70]
0x18001515f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015164  nop
0x180015165  lea     r9, [rsp+0A8h+var_70]
0x18001516a  xor     r8d, r8d
0x18001516d  lea     rdx, [rsp+0A8h+var_78]
0x180015172  mov     rcx, [rbx+40h]
0x180015176  call    ?UnpackObjectId@@YA?AW4_MI_Result@@PEB_WPEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UnpackObjectId(wchar_t const *,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *,std::wstring &)
0x18001517b  mov     ebx, eax
0x18001517d  test    eax, eax
0x18001517f  jnz     short loc_18001519B
0x180015181  mov     [rsp+0A8h+var_88], rbp
0x180015186  xor     r9d, r9d
0x180015189  mov     r8d, [rsp+0A8h+var_78]
0x18001518e  mov     rdx, rsi
0x180015191  mov     rcx, rdi
0x180015194  call    ?SrSmapiCreateReplicaPeer@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z; SrSmapiCreateReplicaPeer(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)
0x180015199  mov     ebx, eax
0x18001519b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151a2  cmp     rcx, r14
0x1800151a5  jz      short loc_1800151C6
0x1800151a7  test    byte ptr [rcx+1Ch], 1
0x1800151ab  jz      short loc_1800151C6
0x1800151ad  mov     edx, 11h
0x1800151b2  mov     r9d, ebx
0x1800151b5  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x1800151bc  mov     rcx, [rcx+10h]
0x1800151c0  call    WPP_SF_d
0x1800151c5  nop
0x1800151c6  lea     rcx, [rsp+0A8h+var_70]
0x1800151cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800151d0  nop
0x1800151d1  lea     rcx, [rsp+0A8h+var_50]
0x1800151d6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800151db  mov     eax, ebx
0x1800151dd  mov     rcx, [rsp+0A8h+var_30]
0x1800151e2  xor     rcx, rsp; StackCookie
0x1800151e5  call    __security_check_cookie
0x1800151ea  add     rsp, 80h
0x1800151f1  pop     r14
0x1800151f3  pop     rdi
0x1800151f4  pop     rsi
0x1800151f5  pop     rbp
0x1800151f6  pop     rbx
0x1800151f7  retn
```
