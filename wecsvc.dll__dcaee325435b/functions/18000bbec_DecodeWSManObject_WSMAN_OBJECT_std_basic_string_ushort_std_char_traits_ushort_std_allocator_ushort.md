# DecodeWSManObject(WSMAN_OBJECT *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000bbec`
- end: `0x18000bd70`
- name: `?DecodeWSManObject@@YAXPEAUWSMAN_OBJECT@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180009a10`
- `0x18000d03c`
- `0x18000e2f8`
- `0x18000f7b0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180006334`
- `0x18000669c`
- `0x18000bbec`
- `0x18000bd78`

## string_xrefs

- `0x18000bc93`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000bd28`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
__int64 __fastcall DecodeWSManObject(__int64 a1, __int64 a2)
{
  const wchar_t *v3; // rdx
  __int128 v5; // [rsp+20h] [rbp-50h] BYREF
  __int64 v6; // [rsp+30h] [rbp-40h]
  void **pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  char v8; // [rsp+40h] [rbp-30h]
  const char *v9; // [rsp+48h] [rbp-28h]
  __int64 v10; // [rsp+50h] [rbp-20h]
  __int64 v11; // [rsp+58h] [rbp-18h]
  int v12; // [rsp+60h] [rbp-10h]
  int v13; // [rsp+64h] [rbp-Ch]
  int v14; // [rsp+68h] [rbp-8h]

  v5 = 0;
  v6 = 0;
  DecodeWSManObject(a1, &v5);
  v3 = (const wchar_t *)v5;
  if ( *((_QWORD *)&v5 + 1) == (_QWORD)v5 )
  {
    v3 = &word_180026AD8;
  }
  else
  {
    if ( ((BYTE8(v5) - (_BYTE)v5) & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, 13);
      }
      v8 = 0;
      v9 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v10 = 0;
      v11 = 0;
      v12 = 13;
      v13 = -1;
      v14 = 75;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    if ( *(_WORD *)(*((_QWORD *)&v5 + 1) - 2LL) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, 13);
      }
      v8 = 0;
      v9 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v10 = 0;
      v11 = 0;
      v12 = 13;
      v13 = -1;
      v14 = 80;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  std::wstring::assign(a2, v3);
  return std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(&v5);
}

```

## disassembly

```asm
0x18000bbec  mov     [rsp-8+arg_0], rbx
0x18000bbf1  push    rbp
0x18000bbf2  mov     rbp, rsp
0x18000bbf5  sub     rsp, 70h
0x18000bbf9  mov     rbx, rdx
0x18000bbfc  xorps   xmm0, xmm0
0x18000bbff  movdqu  [rbp+var_50], xmm0
0x18000bc04  mov     [rbp+var_40], 0
0x18000bc0c  lea     rdx, [rbp+var_50]
0x18000bc10  call    ?DecodeWSManObject@@YAXPEAUWSMAN_OBJECT@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; DecodeWSManObject(WSMAN_OBJECT *,std::vector<uchar> &)
0x18000bc15  mov     rax, qword ptr [rbp+var_50+8]
0x18000bc19  mov     rcx, rax
0x18000bc1c  mov     rdx, qword ptr [rbp+var_50]
0x18000bc20  sub     rcx, rdx
0x18000bc23  jnz     short loc_18000BC4C
0x18000bc25  lea     rdx, word_180026AD8
0x18000bc2c  mov     rcx, rbx
0x18000bc2f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000bc34  nop
0x18000bc35  lea     rcx, [rbp+var_50]
0x18000bc39  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18000bc3e  mov     rbx, [rsp+70h+arg_0]
0x18000bc46  add     rsp, 70h
0x18000bc4a  pop     rbp
0x18000bc4b  retn
0x18000bc4c  test    cl, 1
0x18000bc4f  jz      loc_18000BCDB
0x18000bc55  lea     rax, WPP_GLOBAL_Control
0x18000bc5c  mov     ebx, 0Dh
0x18000bc61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc68  cmp     rcx, rax
0x18000bc6b  jz      short loc_18000BC8F
0x18000bc6d  test    byte ptr [rcx+1Ch], 10h
0x18000bc71  jz      short loc_18000BC8F
0x18000bc73  cmp     byte ptr [rcx+19h], 2
0x18000bc77  jb      short loc_18000BC8F
0x18000bc79  lea     edx, [rbx-1]
0x18000bc7c  mov     r9d, ebx
0x18000bc7f  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000bc86  mov     rcx, [rcx+10h]
0x18000bc8a  call    WPP_SF_D
0x18000bc8f  mov     [rbp+var_30], 0
0x18000bc93  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000bc9a  mov     [rbp+var_28], rax
0x18000bc9e  mov     [rbp+var_20], 0
0x18000bca6  mov     [rbp+var_18], 0
0x18000bcae  mov     [rbp+var_10], ebx
0x18000bcb1  mov     [rbp+var_C], 0FFFFFFFFh
0x18000bcb8  mov     [rbp+var_8], 4Bh ; 'K'
0x18000bcbf  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000bcc6  mov     [rbp+pExceptionObject], rax
0x18000bcca  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000bcd1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bcd5  call    _CxxThrowException_0
0x18000bcdb  cmp     byte ptr [rax-2], 0
0x18000bcdf  jnz     short loc_18000BCEB
0x18000bce1  cmp     byte ptr [rax-1], 0
0x18000bce5  jz      loc_18000BC2C
0x18000bceb  lea     rax, WPP_GLOBAL_Control
0x18000bcf2  mov     ebx, 0Dh
0x18000bcf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcfe  cmp     rcx, rax
0x18000bd01  jz      short loc_18000BD24
0x18000bd03  test    byte ptr [rcx+1Ch], 10h
0x18000bd07  jz      short loc_18000BD24
0x18000bd09  cmp     byte ptr [rcx+19h], 2
0x18000bd0d  jb      short loc_18000BD24
0x18000bd0f  mov     edx, ebx
0x18000bd11  mov     r9d, ebx
0x18000bd14  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000bd1b  mov     rcx, [rcx+10h]
0x18000bd1f  call    WPP_SF_D
0x18000bd24  mov     [rbp+var_30], 0
0x18000bd28  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000bd2f  mov     [rbp+var_28], rax
0x18000bd33  mov     [rbp+var_20], 0
0x18000bd3b  mov     [rbp+var_18], 0
0x18000bd43  mov     [rbp+var_10], ebx
0x18000bd46  mov     [rbp+var_C], 0FFFFFFFFh
0x18000bd4d  mov     [rbp+var_8], 50h ; 'P'
0x18000bd54  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000bd5b  mov     [rbp+pExceptionObject], rax
0x18000bd5f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000bd66  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bd6a  call    _CxxThrowException_0
```
