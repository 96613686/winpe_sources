# SetWSManSessionOptionsLocales(WSMAN_SESSION *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180010058`
- end: `0x180010242`
- name: `?SetWSManSessionOptionsLocales@@YAXPEAUWSMAN_SESSION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `490`
- prototype: `DWORD __fastcall(WSMAN_SESSION_HANDLE session, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008828`
- `0x180009a10`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180010058`

## import_xrefs

- `WsmSvc!WSManSetSessionOption` at `0x18001009e`
- `WsmSvc!WSManSetSessionOption` at `0x18001016d`
- `WsmSvc!WSManSetSessionOption` at `0x18001009e`
- `WsmSvc!WSManSetSessionOption` at `0x18001016d`

## string_xrefs

- `0x180010115`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x1800101e4`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
DWORD __fastcall SetWSManSessionOptionsLocales(WSMAN_SESSION_HANDLE session, __int64 a2)
{
  bool v2; // cf
  const WCHAR *v4; // rax
  DWORD v5; // eax
  DWORD v6; // edi
  PVOID *v7; // rcx
  DWORD result; // eax
  DWORD v9; // edi
  PVOID *v10; // rcx
  WSMAN_DATA data; // [rsp+20h] [rbp-50h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  char v13; // [rsp+40h] [rbp-30h]
  const char *v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  __int64 v16; // [rsp+58h] [rbp-18h]
  DWORD v17; // [rsp+60h] [rbp-10h]
  int v18; // [rsp+64h] [rbp-Ch]
  int v19; // [rsp+68h] [rbp-8h]

  v2 = *(_QWORD *)(a2 + 24) < 8u;
  *(_QWORD *)&data.type = 1;
  *(&data.number + 1) = 0;
  if ( v2 )
    v4 = (const WCHAR *)a2;
  else
    v4 = *(const WCHAR **)a2;
  data.text.buffer = v4;
  data.text.bufferLength = *(_DWORD *)(a2 + 16);
  v5 = WSManSetSessionOption(session, WSMAN_OPTION_LOCALE, &data);
  v6 = v5;
  if ( v5 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v5);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 && *((_BYTE *)v7 + 25) >= 2u )
        WPP_SF_D(v7[2], 21, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v6);
    }
    v13 = 0;
    v14 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v15 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v16 = 0;
    v17 = v6;
    v18 = -1;
    v19 = 644;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  result = WSManSetSessionOption(session, WSMAN_OPTION_UI_LANGUAGE, &data);
  v9 = result;
  if ( result )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, result);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 && *((_BYTE *)v10 + 25) >= 2u )
        WPP_SF_D(v10[2], 23, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v9);
    }
    v13 = 0;
    v14 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v15 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v16 = 0;
    v17 = v9;
    v18 = -1;
    v19 = 655;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180010058  mov     [rsp-8+arg_0], rbx
0x18001005d  mov     [rsp-8+arg_8], rdi
0x180010062  push    rbp
0x180010063  mov     rbp, rsp
0x180010066  sub     rsp, 70h
0x18001006a  cmp     qword ptr [rdx+18h], 8
0x18001006f  mov     rbx, rcx
0x180010072  mov     qword ptr [rbp+data.type], 1
0x18001007a  mov     dword ptr [rbp+data.8+4], 0
0x180010081  jb      short loc_180010088
0x180010083  mov     rax, [rdx]
0x180010086  jmp     short loc_18001008B
0x180010088  mov     rax, rdx
0x18001008b  mov     qword ptr [rbp+data.8+8], rax
0x18001008f  lea     r8, [rbp+data]; data
0x180010093  mov     eax, [rdx+10h]
0x180010096  mov     edx, 19h; option
0x18001009b  mov     dword ptr [rbp+data.8], eax
0x18001009e  call    cs:__imp_WSManSetSessionOption
0x1800100a4  mov     edi, eax
0x1800100a6  test    eax, eax
0x1800100a8  jz      loc_180010161
0x1800100ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100b5  lea     rbx, WPP_GLOBAL_Control
0x1800100bc  cmp     rcx, rbx
0x1800100bf  jz      short loc_180010115
0x1800100c1  test    byte ptr [rcx+1Ch], 10h
0x1800100c5  jz      short loc_1800100EC
0x1800100c7  cmp     byte ptr [rcx+19h], 2
0x1800100cb  jb      short loc_1800100EC
0x1800100cd  mov     rcx, [rcx+10h]
0x1800100d1  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x1800100d8  mov     edx, 14h
0x1800100dd  mov     r9d, eax
0x1800100e0  call    WPP_SF_D
0x1800100e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100ec  cmp     rcx, rbx
0x1800100ef  jz      short loc_180010115
0x1800100f1  test    byte ptr [rcx+1Ch], 10h
0x1800100f5  jz      short loc_180010115
0x1800100f7  cmp     byte ptr [rcx+19h], 2
0x1800100fb  jb      short loc_180010115
0x1800100fd  mov     rcx, [rcx+10h]
0x180010101  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x180010108  mov     edx, 15h
0x18001010d  mov     r9d, edi
0x180010110  call    WPP_SF_D
0x180010115  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18001011c  mov     [rbp+var_30], 0
0x180010120  mov     [rbp+var_28], rax
0x180010124  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001012b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180010132  mov     [rbp+var_20], 0
0x18001013a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001013e  mov     [rbp+pExceptionObject], rax
0x180010142  mov     [rbp+var_18], 0
0x18001014a  mov     [rbp+var_10], edi
0x18001014d  mov     [rbp+var_C], 0FFFFFFFFh
0x180010154  mov     [rbp+var_8], 284h
0x18001015b  call    _CxxThrowException_0
0x180010161  lea     r8, [rbp+data]; data
0x180010165  mov     edx, 1Ah; option
0x18001016a  mov     rcx, rbx; session
0x18001016d  call    cs:__imp_WSManSetSessionOption
0x180010173  mov     edi, eax
0x180010175  test    eax, eax
0x180010177  jz      loc_180010230
0x18001017d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010184  lea     rbx, WPP_GLOBAL_Control
0x18001018b  cmp     rcx, rbx
0x18001018e  jz      short loc_1800101E4
0x180010190  test    byte ptr [rcx+1Ch], 10h
0x180010194  jz      short loc_1800101BB
0x180010196  cmp     byte ptr [rcx+19h], 2
0x18001019a  jb      short loc_1800101BB
0x18001019c  mov     rcx, [rcx+10h]
0x1800101a0  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x1800101a7  mov     edx, 16h
0x1800101ac  mov     r9d, eax
0x1800101af  call    WPP_SF_D
0x1800101b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101bb  cmp     rcx, rbx
0x1800101be  jz      short loc_1800101E4
0x1800101c0  test    byte ptr [rcx+1Ch], 10h
0x1800101c4  jz      short loc_1800101E4
0x1800101c6  cmp     byte ptr [rcx+19h], 2
0x1800101ca  jb      short loc_1800101E4
0x1800101cc  mov     rcx, [rcx+10h]
0x1800101d0  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x1800101d7  mov     edx, 17h
0x1800101dc  mov     r9d, edi
0x1800101df  call    WPP_SF_D
0x1800101e4  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x1800101eb  mov     [rbp+var_30], 0
0x1800101ef  mov     [rbp+var_28], rax
0x1800101f3  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800101fa  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180010201  mov     [rbp+var_20], 0
0x180010209  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001020d  mov     [rbp+pExceptionObject], rax
0x180010211  mov     [rbp+var_18], 0
0x180010219  mov     [rbp+var_10], edi
0x18001021c  mov     [rbp+var_C], 0FFFFFFFFh
0x180010223  mov     [rbp+var_8], 28Fh
0x18001022a  call    _CxxThrowException_0
0x180010230  lea     r11, [rsp+70h+var_s0]
0x180010235  mov     rbx, [r11+10h]
0x180010239  mov     rdi, [r11+18h]
0x18001023d  mov     rsp, r11
0x180010240  pop     rbp
0x180010241  retn
```
