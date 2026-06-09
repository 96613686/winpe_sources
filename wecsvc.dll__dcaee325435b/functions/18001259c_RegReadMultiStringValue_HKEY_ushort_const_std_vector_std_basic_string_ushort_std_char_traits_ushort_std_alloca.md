# RegReadMultiStringValue(HKEY__ *,ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18001259c`
- end: `0x180012746`
- name: `?RegReadMultiStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `426`
- prototype: `char __fastcall(HKEY, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180007c00`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x1800062d4`
- `0x180006334`
- `0x180006898`
- `0x1800121fc`
- `0x18001259c`
- `0x180012d64`
- `0x18001fe50`

## string_xrefs

- `0x180012649`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
char __fastcall RegReadMultiStringValue(HKEY a1, __int64 a2, __int64 a3)
{
  _WORD *v5; // rbx
  _BYTE v6[4]; // [rsp+20h] [rbp-60h] BYREF
  DWORD Type; // [rsp+24h] [rbp-5Ch] BYREF
  __int128 v8; // [rsp+28h] [rbp-58h] BYREF
  __int64 v9; // [rsp+38h] [rbp-48h]
  void **pExceptionObject; // [rsp+40h] [rbp-40h] BYREF
  char v11; // [rsp+48h] [rbp-38h]
  const char *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+6Ch] [rbp-14h]
  int v17; // [rsp+70h] [rbp-10h]

  v8 = 0;
  v9 = 0;
  Type = 0;
  if ( RegReadByteArrayValue(a1, L"InactiveErrorList", &Type, (LPBYTE *)&v8) )
  {
    if ( Type != 7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, 13);
      }
      v11 = 0;
      v12 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
      v13 = 0;
      v14 = 0;
      v15 = 13;
      v16 = -1;
      v17 = 98;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v6[0] = 0;
    std::vector<unsigned char>::push_back(&v8, v6);
    v6[0] = 0;
    std::vector<unsigned char>::push_back(&v8, v6);
    v6[0] = 0;
    std::vector<unsigned char>::push_back(&v8, v6);
    v6[0] = 0;
    std::vector<unsigned char>::push_back(&v8, v6);
    v5 = (_WORD *)v8;
    while ( *v5 )
    {
      std::wstring::wstring((__int64)&pExceptionObject, (__int64)v5);
      std::vector<std::wstring>::push_back(a3, &pExceptionObject);
      v5 += (_QWORD)v12 + 1;
      std::wstring::_Tidy(&pExceptionObject, 1, 0);
    }
    std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>((__int64)&v8);
    return 1;
  }
  else
  {
    std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>((__int64)&v8);
    return 0;
  }
}

```

## disassembly

```asm
0x18001259c  mov     [rsp-8+arg_8], rbx
0x1800125a1  mov     [rsp-8+arg_18], rdi
0x1800125a6  push    rbp
0x1800125a7  mov     rbp, rsp
0x1800125aa  sub     rsp, 80h
0x1800125b1  mov     rax, cs:__security_cookie
0x1800125b8  xor     rax, rsp
0x1800125bb  mov     [rbp+var_8], rax
0x1800125bf  mov     rdi, r8
0x1800125c2  xorps   xmm0, xmm0
0x1800125c5  movdqu  [rbp+var_58], xmm0
0x1800125ca  mov     [rbp+var_48], 0
0x1800125d2  mov     [rbp+Type], 0
0x1800125d9  lea     r9, [rbp+var_58]
0x1800125dd  lea     r8, [rbp+Type]; lpType
0x1800125e1  lea     rdx, aInactiveerrorl; "InactiveErrorList"
0x1800125e8  call    ?RegReadByteArrayValue@@YA_NPEAUHKEY__@@PEBGAEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; RegReadByteArrayValue(HKEY__ *,ushort const *,ulong &,std::vector<uchar> &)
0x1800125ed  test    al, al
0x1800125ef  jnz     short loc_180012601
0x1800125f1  lea     rcx, [rbp+var_58]
0x1800125f5  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x1800125fa  xor     al, al
0x1800125fc  jmp     loc_180012725
0x180012601  cmp     [rbp+Type], 7
0x180012605  jz      loc_180012691
0x18001260b  lea     rax, WPP_GLOBAL_Control
0x180012612  mov     ebx, 0Dh
0x180012617  mov     rcx, cs:WPP_GLOBAL_Control
0x18001261e  cmp     rcx, rax
0x180012621  jz      short loc_180012645
0x180012623  test    byte ptr [rcx+1Ch], 1
0x180012627  jz      short loc_180012645
0x180012629  cmp     byte ptr [rcx+19h], 2
0x18001262d  jb      short loc_180012645
0x18001262f  lea     edx, [rbx+2]
0x180012632  mov     r9d, ebx
0x180012635  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x18001263c  mov     rcx, [rcx+10h]
0x180012640  call    WPP_SF_D
0x180012645  mov     [rbp+var_38], 0
0x180012649  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180012650  mov     [rbp+var_30], rax
0x180012654  mov     [rbp+var_28], 0
0x18001265c  mov     [rbp+var_20], 0
0x180012664  mov     [rbp+var_18], ebx
0x180012667  mov     [rbp+var_14], 0FFFFFFFFh
0x18001266e  mov     [rbp+var_10], 62h ; 'b'
0x180012675  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001267c  mov     [rbp+pExceptionObject], rax
0x180012680  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012687  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001268b  call    _CxxThrowException_0
0x180012691  mov     [rbp+var_60], 0
0x180012695  lea     rdx, [rbp+var_60]
0x180012699  lea     rcx, [rbp+var_58]
0x18001269d  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x1800126a2  mov     [rbp+var_60], 0
0x1800126a6  lea     rdx, [rbp+var_60]
0x1800126aa  lea     rcx, [rbp+var_58]
0x1800126ae  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x1800126b3  mov     [rbp+var_60], 0
0x1800126b7  lea     rdx, [rbp+var_60]
0x1800126bb  lea     rcx, [rbp+var_58]
0x1800126bf  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x1800126c4  mov     [rbp+var_60], 0
0x1800126c8  lea     rdx, [rbp+var_60]
0x1800126cc  lea     rcx, [rbp+var_58]
0x1800126d0  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x1800126d5  mov     rbx, qword ptr [rbp+var_58]
0x1800126d9  xor     eax, eax
0x1800126db  cmp     ax, [rbx]
0x1800126de  jz      short loc_18001271A
0x1800126e0  mov     rdx, rbx
0x1800126e3  lea     rcx, [rbp+pExceptionObject]
0x1800126e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800126ec  nop
0x1800126ed  lea     rdx, [rbp+pExceptionObject]
0x1800126f1  mov     rcx, rdi
0x1800126f4  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800126f9  mov     rax, [rbp+var_30]
0x1800126fd  lea     rbx, [rbx+rax*2]
0x180012701  add     rbx, 2
0x180012705  xor     r8d, r8d
0x180012708  mov     dl, 1
0x18001270a  lea     rcx, [rbp+pExceptionObject]
0x18001270e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012713  xor     ecx, ecx
0x180012715  cmp     cx, [rbx]
0x180012718  jnz     short loc_1800126E0
0x18001271a  lea     rcx, [rbp+var_58]
0x18001271e  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x180012723  mov     al, 1
0x180012725  mov     rcx, [rbp+var_8]
0x180012729  xor     rcx, rsp; StackCookie
0x18001272c  call    __security_check_cookie
0x180012731  lea     r11, [rsp+80h+var_s0]
0x180012739  mov     rbx, [r11+18h]
0x18001273d  mov     rdi, [r11+28h]
0x180012741  mov     rsp, r11
0x180012744  pop     rbp
0x180012745  retn
```
