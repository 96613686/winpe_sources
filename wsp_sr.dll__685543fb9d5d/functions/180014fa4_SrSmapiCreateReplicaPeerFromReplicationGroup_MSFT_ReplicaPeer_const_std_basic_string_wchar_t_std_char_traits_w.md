# SrSmapiCreateReplicaPeerFromReplicationGroup(_MSFT_ReplicaPeer const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_WSP_ReplicaPeer *)

- ea: `0x180014fa4`
- end: `0x1800150ad`
- name: `?SrSmapiCreateReplicaPeerFromReplicationGroup@@YA?AW4_MI_Result@@PEBU_MSFT_ReplicaPeer@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1PEAU_WSP_ReplicaPeer@@@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009714`

## callees

- `0x1800014e0`
- `0x18000590c`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x180014a3c`
- `0x180014fa4`
- `0x18001c114`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiCreateReplicaPeerFromReplicationGroup(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  unsigned int ReplicaPeer; // ebx
  int v10; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids);
  std::wstring::wstring(v12);
  v10 = 0;
  std::wstring::wstring(v11);
  ReplicaPeer = UnpackObjectId(*(_QWORD *)(a1 + 64), &v10, 0, v11);
  if ( !ReplicaPeer )
    ReplicaPeer = SrSmapiCreateReplicaPeer(a2, a3, v10, 0, a4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids, ReplicaPeer);
  std::wstring::_Tidy_deallocate(v11);
  std::wstring::_Tidy_deallocate(v12);
  return ReplicaPeer;
}

```

## disassembly

```asm
0x180014fa4  push    rbx
0x180014fa6  push    rbp
0x180014fa7  push    rsi
0x180014fa8  push    rdi
0x180014fa9  push    r14
0x180014fab  sub     rsp, 80h
0x180014fb2  mov     rax, cs:__security_cookie
0x180014fb9  xor     rax, rsp
0x180014fbc  mov     [rsp+0A8h+var_30], rax
0x180014fc1  mov     rbp, r9
0x180014fc4  mov     rsi, r8
0x180014fc7  mov     rdi, rdx
0x180014fca  mov     rbx, rcx
0x180014fcd  lea     r14, WPP_GLOBAL_Control
0x180014fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fdb  cmp     rcx, r14
0x180014fde  jz      short loc_180014FFB
0x180014fe0  test    byte ptr [rcx+1Ch], 4
0x180014fe4  jz      short loc_180014FFB
0x180014fe6  mov     edx, 10h
0x180014feb  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180014ff2  mov     rcx, [rcx+10h]
0x180014ff6  call    WPP_SF_
0x180014ffb  lea     rcx, [rsp+0A8h+var_50]
0x180015000  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015005  nop
0x180015006  mov     [rsp+0A8h+var_78], 0
0x18001500e  lea     rcx, [rsp+0A8h+var_70]
0x180015013  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015018  nop
0x180015019  lea     r9, [rsp+0A8h+var_70]
0x18001501e  xor     r8d, r8d
0x180015021  lea     rdx, [rsp+0A8h+var_78]
0x180015026  mov     rcx, [rbx+40h]
0x18001502a  call    ?UnpackObjectId@@YA?AW4_MI_Result@@PEB_WPEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UnpackObjectId(wchar_t const *,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *,std::wstring &)
0x18001502f  mov     ebx, eax
0x180015031  test    eax, eax
0x180015033  jnz     short loc_18001504F
0x180015035  mov     [rsp+0A8h+var_88], rbp
0x18001503a  xor     r9d, r9d
0x18001503d  mov     r8d, [rsp+0A8h+var_78]
0x180015042  mov     rdx, rsi
0x180015045  mov     rcx, rdi
0x180015048  call    ?SrSmapiCreateReplicaPeer@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4WSP_SUBSYSTEM_TYPE@@_NPEAU_WSP_ReplicaPeer@@@Z; SrSmapiCreateReplicaPeer(std::wstring const &,std::wstring const &,WSP_SUBSYSTEM_TYPE,bool,_WSP_ReplicaPeer *)
0x18001504d  mov     ebx, eax
0x18001504f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015056  cmp     rcx, r14
0x180015059  jz      short loc_18001507A
0x18001505b  test    byte ptr [rcx+1Ch], 1
0x18001505f  jz      short loc_18001507A
0x180015061  mov     edx, 11h
0x180015066  mov     r9d, ebx
0x180015069  lea     r8, WPP_cc3ca51cc80e3dc3dcf6456d044a4742_Traceguids
0x180015070  mov     rcx, [rcx+10h]
0x180015074  call    WPP_SF_d
0x180015079  nop
0x18001507a  lea     rcx, [rsp+0A8h+var_70]
0x18001507f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015084  nop
0x180015085  lea     rcx, [rsp+0A8h+var_50]
0x18001508a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001508f  mov     eax, ebx
0x180015091  mov     rcx, [rsp+0A8h+var_30]
0x180015096  xor     rcx, rsp; StackCookie
0x180015099  call    __security_check_cookie
0x18001509e  add     rsp, 80h
0x1800150a5  pop     r14
0x1800150a7  pop     rdi
0x1800150a8  pop     rsi
0x1800150a9  pop     rbp
0x1800150aa  pop     rbx
0x1800150ab  retn
```
