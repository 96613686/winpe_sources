# RegReadStringValue(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800128c0`
- end: `0x1800129ea`
- name: `?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `298`
- prototype: `char __fastcall(HKEY, const WCHAR *, __int64)`
- caller_count: `15`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e134`
- `0x18000f1f8`
- `0x18000f3d0`
- `0x18001483c`
- `0x1800159e0`
- `0x180015c30`
- `0x180016098`
- `0x1800161e4`
- `0x180016514`
- `0x1800165c0`
- `0x180017510`
- `0x18001764c`
- `0x18001780c`
- `0x180017b8c`
- `0x18001b998`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180006334`
- `0x18000669c`
- `0x1800121fc`
- `0x1800128c0`
- `0x180012d64`

## string_xrefs

- `0x180012957`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
char __fastcall RegReadStringValue(HKEY a1, const WCHAR *a2, __int64 a3)
{
  DWORD Type; // [rsp+20h] [rbp-60h] BYREF
  __int128 v6; // [rsp+28h] [rbp-58h] BYREF
  __int64 v7; // [rsp+38h] [rbp-48h]
  void **pExceptionObject; // [rsp+40h] [rbp-40h] BYREF
  char v9; // [rsp+48h] [rbp-38h]
  const char *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+6Ch] [rbp-14h]
  int v15; // [rsp+70h] [rbp-10h]
  char v16; // [rsp+A8h] [rbp+28h] BYREF

  Type = 0;
  v6 = 0;
  v7 = 0;
  if ( RegReadByteArrayValue(a1, a2, &Type, (LPBYTE *)&v6) )
  {
    if ( Type - 1 > 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, 13);
      }
      v9 = 0;
      v10 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
      v11 = 0;
      v12 = 0;
      v13 = 13;
      v14 = -1;
      v15 = 74;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v16 = 0;
    std::vector<unsigned char>::push_back(&v6, &v16);
    v16 = 0;
    std::vector<unsigned char>::push_back(&v6, &v16);
    std::wstring::assign(a3, v6);
    std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>((__int64)&v6);
    return 1;
  }
  else
  {
    std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>((__int64)&v6);
    return 0;
  }
}

```

## disassembly

```asm
0x1800128c0  mov     [rsp-8+arg_0], rbx
0x1800128c5  push    rbp
0x1800128c6  mov     rbp, rsp
0x1800128c9  sub     rsp, 80h
0x1800128d0  mov     rbx, r8
0x1800128d3  mov     [rbp+Type], 0
0x1800128da  xorps   xmm0, xmm0
0x1800128dd  movdqu  [rbp+var_58], xmm0
0x1800128e2  mov     [rbp+var_48], 0
0x1800128ea  lea     r9, [rbp+var_58]
0x1800128ee  lea     r8, [rbp+Type]; lpType
0x1800128f2  call    ?RegReadByteArrayValue@@YA_NPEAUHKEY__@@PEBGAEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; RegReadByteArrayValue(HKEY__ *,ushort const *,ulong &,std::vector<uchar> &)
0x1800128f7  test    al, al
0x1800128f9  jnz     short loc_18001290B
0x1800128fb  lea     rcx, [rbp+var_58]
0x1800128ff  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x180012904  xor     al, al
0x180012906  jmp     loc_1800129D9
0x18001290b  mov     eax, [rbp+Type]
0x18001290e  dec     eax
0x180012910  cmp     eax, 1
0x180012913  jbe     loc_18001299F
0x180012919  lea     rax, WPP_GLOBAL_Control
0x180012920  mov     ebx, 0Dh
0x180012925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001292c  cmp     rcx, rax
0x18001292f  jz      short loc_180012953
0x180012931  test    byte ptr [rcx+1Ch], 1
0x180012935  jz      short loc_180012953
0x180012937  cmp     byte ptr [rcx+19h], 2
0x18001293b  jb      short loc_180012953
0x18001293d  lea     edx, [rbx+1]
0x180012940  mov     r9d, ebx
0x180012943  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x18001294a  mov     rcx, [rcx+10h]
0x18001294e  call    WPP_SF_D
0x180012953  mov     [rbp+var_38], 0
0x180012957  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x18001295e  mov     [rbp+var_30], rax
0x180012962  mov     [rbp+var_28], 0
0x18001296a  mov     [rbp+var_20], 0
0x180012972  mov     [rbp+var_18], ebx
0x180012975  mov     [rbp+var_14], 0FFFFFFFFh
0x18001297c  mov     [rbp+var_10], 4Ah ; 'J'
0x180012983  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001298a  mov     [rbp+pExceptionObject], rax
0x18001298e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012995  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012999  call    _CxxThrowException_0
0x18001299f  mov     [rbp+arg_18], 0
0x1800129a3  lea     rdx, [rbp+arg_18]
0x1800129a7  lea     rcx, [rbp+var_58]
0x1800129ab  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x1800129b0  mov     [rbp+arg_18], 0
0x1800129b4  lea     rdx, [rbp+arg_18]
0x1800129b8  lea     rcx, [rbp+var_58]
0x1800129bc  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x1800129c1  mov     rdx, qword ptr [rbp+var_58]
0x1800129c5  mov     rcx, rbx
0x1800129c8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800129cd  nop
0x1800129ce  lea     rcx, [rbp+var_58]
0x1800129d2  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x1800129d7  mov     al, 1
0x1800129d9  mov     rbx, [rsp+80h+arg_0]
0x1800129e1  add     rsp, 80h
0x1800129e8  pop     rbp
0x1800129e9  retn
```
