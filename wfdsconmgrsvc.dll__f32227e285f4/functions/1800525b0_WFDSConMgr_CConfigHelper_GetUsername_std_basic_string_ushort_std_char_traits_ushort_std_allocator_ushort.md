# WFDSConMgr::CConfigHelper::GetUsername(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800525b0`
- end: `0x1800526ea`
- name: `?GetUsername@CConfigHelper@WFDSConMgr@@UEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180004260`
- `0x180009ff4`
- `0x18000adcc`
- `0x18001a928`
- `0x1800525b0`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800525eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005264a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800525eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005264a`

## string_xrefs

- `0x180052673`: `onecoreuap\net\wlan\wfdsconmgr\conmgr\src\confighelper.cpp`
- `0x1800526d1`: `onecoreuap\net\wlan\wfdsconmgr\conmgr\src\confighelper.cpp`
- `0x18005267a`: `WFDSConMgr::CConfigHelper::GetUsername`
- `0x1800526d8`: `WFDSConMgr::CConfigHelper::GetUsername`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CConfigHelper::GetUsername(_QWORD **a1, __int64 a2)
{
  int v4; // ebx
  DWORD LastError; // eax
  void *v6; // rbx
  char v7; // al
  __int64 v8; // rax
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF
  void *v10; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD, unsigned int *))(*a1[1] + 40LL))(a1[1], 3, 0, &v9);
  LastError = GetLastError();
  if ( v4 || LastError != 234 )
    WFDSConMgr::CException::Throw(
      13,
      "WFDSConMgr::CConfigHelper::GetUsername",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\confighelper.cpp",
      36,
      L"GetUsername succeeded with null buffer, expected ERROR_MORE_DATA",
      a1);
  v6 = operator new[](saturated_mul(v9, 2u));
  v10 = v6;
  if ( !(*(unsigned int (__fastcall **)(_QWORD *, __int64, void *, unsigned int *))(*a1[1] + 40LL))(a1[1], 3, v6, &v9) )
  {
    v7 = GetLastError();
    WFDSConMgr::CException::Throw(
      v7,
      "WFDSConMgr::CConfigHelper::GetUsername",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\confighelper.cpp",
      43,
      L"GetUsername failed",
      a1);
  }
  v8 = std::_WChar_traits<unsigned short>::length(v6);
  std::wstring::_Assign<unsigned short>(a2, v6, v8);
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(&v10);
}

```

## disassembly

```asm
0x1800525b0  mov     [rsp+arg_8], rbx
0x1800525b5  mov     [rsp+arg_18], rsi
0x1800525ba  push    rdi
0x1800525bb  sub     rsp, 30h
0x1800525bf  mov     rsi, rdx
0x1800525c2  mov     rdi, rcx
0x1800525c5  mov     [rsp+38h+arg_0], 0
0x1800525cd  mov     rcx, [rcx+8]
0x1800525d1  mov     rax, [rcx]
0x1800525d4  lea     r9, [rsp+38h+arg_0]
0x1800525d9  xor     r8d, r8d
0x1800525dc  lea     edx, [r8+3]
0x1800525e0  mov     rax, [rax+28h]
0x1800525e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525e9  mov     ebx, eax
0x1800525eb  call    cs:__imp_GetLastError
0x1800525f1  test    ebx, ebx
0x1800525f3  jnz     loc_1800526BA
0x1800525f9  cmp     eax, 0EAh
0x1800525fe  jnz     loc_1800526BA
0x180052604  mov     ecx, [rsp+38h+arg_0]
0x180052608  lea     eax, [rbx+2]
0x18005260b  mul     rcx
0x18005260e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180052615  cmovb   rax, rcx
0x180052619  mov     rcx, rax; unsigned __int64
0x18005261c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180052621  mov     rbx, rax
0x180052624  mov     [rsp+38h+arg_10], rax
0x180052629  mov     rcx, [rdi+8]
0x18005262d  mov     r8, [rcx]
0x180052630  mov     rax, [r8+28h]
0x180052634  lea     r9, [rsp+38h+arg_0]
0x180052639  mov     r8, rbx
0x18005263c  mov     edx, 3
0x180052641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052646  test    eax, eax
0x180052648  jnz     short loc_180052689
0x18005264a  call    cs:__imp_GetLastError
0x180052650  test    eax, eax
0x180052652  jle     short loc_18005265C
0x180052654  movzx   eax, ax
0x180052657  or      eax, 80070000h
0x18005265c  mov     [rsp+38h+var_10], rdi; void *
0x180052661  lea     rcx, aGetusernameFai; "GetUsername failed"
0x180052668  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x18005266d  mov     r9d, 22Bh; char
0x180052673  lea     r8, aOnecoreuapNetW_14; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005267a  lea     rdx, aWfdsconmgrCcon_9; "WFDSConMgr::CConfigHelper::GetUsername"
0x180052681  mov     ecx, eax; char
0x180052683  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180052689  mov     rcx, rbx
0x18005268c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180052691  mov     r8, rax
0x180052694  mov     rdx, rbx
0x180052697  mov     rcx, rsi
0x18005269a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005269f  nop
0x1800526a0  lea     rcx, [rsp+38h+arg_10]
0x1800526a5  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x1800526aa  mov     rbx, [rsp+38h+arg_8]
0x1800526af  mov     rsi, [rsp+38h+arg_18]
0x1800526b4  add     rsp, 30h
0x1800526b8  pop     rdi
0x1800526b9  retn
0x1800526ba  mov     [rsp+38h+var_10], rdi; void *
0x1800526bf  lea     rax, aGetusernameSuc; "GetUsername succeeded with null buffer,"...
0x1800526c6  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x1800526cb  mov     r9d, 224h; char
0x1800526d1  lea     r8, aOnecoreuapNetW_14; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800526d8  lea     rdx, aWfdsconmgrCcon_9; "WFDSConMgr::CConfigHelper::GetUsername"
0x1800526df  mov     ecx, 8007000Dh; char
0x1800526e4  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
