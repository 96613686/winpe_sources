# WFDSConMgr::DafHelper::GenerateServiceAepID(uchar const (&)[6],std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18005fed4`
- end: `0x1800600c6`
- name: `?GenerateServiceAepID@DafHelper@WFDSConMgr@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY05$$CBEAEBV34@K@Z`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039d18`

## callees

- `0x180002600`
- `0x180002ffc`
- `0x180004260`
- `0x18000665c`
- `0x180009ff4`
- `0x18000f168`
- `0x18005c800`
- `0x18005fed4`
- `0x180060704`
- `0x1800611a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005ffd4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005ffd4`

## string_xrefs

- `0x18005ff7f`: `onecoreuap\net\wlan\wfdsconmgr\common\src\dafhelper.cpp`
- `0x18006000c`: `onecoreuap\net\wlan\wfdsconmgr\common\src\dafhelper.cpp`
- `0x180060073`: `onecoreuap\net\wlan\wfdsconmgr\common\src\dafhelper.cpp`
- `0x18005ff6d`: `Service name invalid, too long`
- `0x18005ff86`: `WFDSConMgr::DafHelper::GenerateServiceAepID`
- `0x180060013`: `WFDSConMgr::DafHelper::GenerateServiceAepID`
- `0x18006007a`: `WFDSConMgr::DafHelper::GenerateServiceAepID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall WFDSConMgr::DafHelper::GenerateServiceAepID(void *a1, int *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  int v6; // r8d
  __int64 v7; // rax
  int v8; // eax
  void *v9; // rdi
  int v10; // eax
  void *v12; // [rsp+38h] [rbp-C8h] BYREF
  int v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[512]; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+258h] [rbp+158h]
  __int16 v16; // [rsp+25Ch] [rbp+15Ch]
  int v17; // [rsp+260h] [rbp+160h]

  v12 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180092670);
    WPP_SF__MAC_S(*(_QWORD *)(v5 + 16), v5, v6, (_DWORD)a2, v4);
  }
  memset_0(v14, 0, 0x210u);
  if ( (unsigned __int64)qword_180092680 > 0xFF )
    WFDSConMgr::CException::Throw(
      -2147024785,
      "WFDSConMgr::DafHelper::GenerateServiceAepID",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\common\\src\\dafhelper.cpp",
      129,
      L"Service name invalid, too long");
  v13[0] = 10;
  v13[1] = 3;
  v15 = *a2;
  v16 = *((_WORD *)a2 + 2);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180092670);
  _o_wcscpy_s(v14, 256, v7);
  v17 = 0;
  v8 = WfdDafObjectStringEncode((int)v13);
  if ( v8 < 0 )
    WFDSConMgr::CException::Throw(
      v8,
      "WFDSConMgr::DafHelper::GenerateServiceAepID",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\common\\src\\dafhelper.cpp",
      142,
      L"WfdDafObjectStringEncode failed (getting size only)");
  v9 = operator new[](saturated_mul(1u, 2u));
  v12 = v9;
  v10 = WfdDafObjectStringEncode((int)v13);
  if ( v10 < 0 )
    WFDSConMgr::CException::Throw(
      v10,
      "WFDSConMgr::DafHelper::GenerateServiceAepID",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\common\\src\\dafhelper.cpp",
      147,
      L"WfdDafObjectStringEncode failed");
  std::wstring::wstring((__int64)a1, (__int64)v9);
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(&v12);
  return a1;
}

```

## disassembly

```asm
0x18005fed4  mov     [rsp-8+arg_10], rbx
0x18005fed9  mov     [rsp-8+arg_18], rdi
0x18005fede  push    rbp
0x18005fedf  lea     rbp, [rsp-180h]
0x18005fee7  sub     rsp, 280h
0x18005feee  mov     rax, cs:__security_cookie
0x18005fef5  xor     rax, rsp
0x18005fef8  mov     [rbp+180h+var_10], rax
0x18005feff  mov     rdi, rdx
0x18005ff02  mov     rbx, rcx
0x18005ff05  mov     [rsp+280h+var_248], rcx
0x18005ff0a  lea     rax, WPP_GLOBAL_Control
0x18005ff11  mov     rdx, cs:WPP_GLOBAL_Control
0x18005ff18  cmp     rdx, rax
0x18005ff1b  jz      short loc_18005FF46
0x18005ff1d  cmp     byte ptr [rdx+19h], 4
0x18005ff21  jb      short loc_18005FF46
0x18005ff23  test    byte ptr [rdx+1Ch], 1
0x18005ff27  jz      short loc_18005FF46
0x18005ff29  lea     rcx, qword_180092670
0x18005ff30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005ff35  mov     [rsp+280h+var_260], rax
0x18005ff3a  mov     r9, rdi
0x18005ff3d  mov     rcx, [rdx+10h]
0x18005ff41  call    WPP_SF__MAC_S
0x18005ff46  xor     edx, edx; Val
0x18005ff48  mov     r8d, 210h; Size
0x18005ff4e  lea     rcx, [rsp+280h+var_228]; void *
0x18005ff53  call    memset_0
0x18005ff58  mov     [rsp+280h+var_250], 0
0x18005ff60  cmp     cs:qword_180092680, 0FFh
0x18005ff6b  jbe     short loc_18005FF98
0x18005ff6d  lea     rax, aServiceNameInv; "Service name invalid, too long"
0x18005ff74  mov     [rsp+280h+var_260], rax; unsigned __int16 *
0x18005ff79  mov     r9d, 81h; char
0x18005ff7f  lea     r8, aOnecoreuapNetW_26; "onecoreuap\\net\\wlan\\wfdsconmgr\\comm"...
0x18005ff86  lea     rdx, aWfdsconmgrDafh_5; "WFDSConMgr::DafHelper::GenerateServiceA"...
0x18005ff8d  mov     ecx, 8007006Fh; int
0x18005ff92  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18005ff98  mov     [rsp+280h+var_230], 0Ah
0x18005ffa0  mov     [rsp+280h+var_22C], 3
0x18005ffa8  mov     eax, [rdi]
0x18005ffaa  mov     [rbp+180h+var_28], eax
0x18005ffb0  movzx   eax, word ptr [rdi+4]
0x18005ffb4  mov     [rbp+180h+var_24], ax
0x18005ffbb  lea     rcx, qword_180092670
0x18005ffc2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005ffc7  mov     r8, rax
0x18005ffca  mov     edx, 100h
0x18005ffcf  lea     rcx, [rsp+280h+var_228]
0x18005ffd4  call    cs:__imp__o_wcscpy_s
0x18005ffda  mov     [rbp+180h+var_20], 0
0x18005ffe4  xor     r9d, r9d
0x18005ffe7  lea     r8, [rsp+280h+var_250]
0x18005ffec  lea     rcx, [rsp+280h+var_230]; int
0x18005fff1  call    WfdDafObjectStringEncode
0x18005fff6  test    eax, eax
0x18005fff8  jns     short loc_180060022
0x18005fffa  lea     rcx, aWfddafobjectst_0; "WfdDafObjectStringEncode failed (gettin"...
0x180060001  mov     [rsp+280h+var_260], rcx; unsigned __int16 *
0x180060006  mov     r9d, 8Eh; char
0x18006000c  lea     r8, aOnecoreuapNetW_26; "onecoreuap\\net\\wlan\\wfdsconmgr\\comm"...
0x180060013  lea     rdx, aWfdsconmgrDafh_5; "WFDSConMgr::DafHelper::GenerateServiceA"...
0x18006001a  mov     ecx, eax; int
0x18006001c  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x180060022  mov     ecx, [rsp+280h+var_250]
0x180060026  inc     ecx
0x180060028  mov     eax, 2
0x18006002d  mul     rcx
0x180060030  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180060037  cmovb   rax, rcx
0x18006003b  mov     rcx, rax; unsigned __int64
0x18006003e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180060043  mov     rdi, rax
0x180060046  mov     [rsp+280h+var_248], rax
0x18006004b  mov     r9, rax
0x18006004e  lea     r8, [rsp+280h+var_250]
0x180060053  lea     rcx, [rsp+280h+var_230]; int
0x180060058  call    WfdDafObjectStringEncode
0x18006005d  test    eax, eax
0x18006005f  jns     short loc_180060089
0x180060061  lea     rcx, aWfddafobjectst; "WfdDafObjectStringEncode failed"
0x180060068  mov     [rsp+280h+var_260], rcx; unsigned __int16 *
0x18006006d  mov     r9d, 93h; char
0x180060073  lea     r8, aOnecoreuapNetW_26; "onecoreuap\\net\\wlan\\wfdsconmgr\\comm"...
0x18006007a  lea     rdx, aWfdsconmgrDafh_5; "WFDSConMgr::DafHelper::GenerateServiceA"...
0x180060081  mov     ecx, eax; int
0x180060083  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x180060089  mov     rdx, rdi
0x18006008c  mov     rcx, rbx
0x18006008f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180060094  nop
0x180060095  lea     rcx, [rsp+280h+var_248]
0x18006009a  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x18006009f  mov     rax, rbx
0x1800600a2  mov     rcx, [rbp+180h+var_10]
0x1800600a9  xor     rcx, rsp; StackCookie
0x1800600ac  call    __security_check_cookie
0x1800600b1  lea     r11, [rsp+280h+var_s0]
0x1800600b9  mov     rbx, [r11+20h]
0x1800600bd  mov     rdi, [r11+28h]
0x1800600c1  mov     rsp, r11
0x1800600c4  pop     rbp
0x1800600c5  retn
```
