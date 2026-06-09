# SubscriptionConfigReader::GetExpires(_FILETIME &)

- ea: `0x180016098`
- end: `0x1800161db`
- name: `?GetExpires@SubscriptionConfigReader@@QEBA_NAEAU_FILETIME@@@Z`
- size: `323`
- prototype: `char __fastcall(SubscriptionConfigReader *this, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001483c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800062d4`
- `0x1800128c0`
- `0x180016098`
- `0x18001f9e8`
- `0x18001fe50`

## pseudocode

```c
char __fastcall SubscriptionConfigReader::GetExpires(SubscriptionConfigReader *this, struct _FILETIME *a2)
{
  const unsigned __int16 *v3; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-19h] BYREF
  char v6; // [rsp+28h] [rbp-11h]
  const char *v7; // [rsp+30h] [rbp-9h]
  __int64 v8; // [rsp+38h] [rbp-1h]
  __int64 v9; // [rsp+40h] [rbp+7h]
  int v10; // [rsp+48h] [rbp+Fh]
  int v11; // [rsp+4Ch] [rbp+13h]
  int v12; // [rsp+50h] [rbp+17h]
  unsigned __int16 *v13[3]; // [rsp+58h] [rbp+1Fh] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp+37h]
  struct _SYSTEMTIME v15; // [rsp+78h] [rbp+3Fh] BYREF

  v14 = 7;
  v13[2] = 0;
  LOWORD(v13[0]) = 0;
  if ( (unsigned __int8)RegReadStringValue(*((_QWORD *)this + 2), L"Expires", v13) )
  {
    v3 = (const unsigned __int16 *)v13;
    if ( v14 >= 8 )
      v3 = v13[0];
    v15 = 0;
    if ( !StringToSystemTime(v3, &v15, a2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v6 = 0;
      v7 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v8 = 0;
      v9 = 0;
      v10 = 13;
      v11 = -1;
      v12 = 323;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::wstring::_Tidy(v13, 1, 0);
    return 1;
  }
  else
  {
    std::wstring::_Tidy(v13, 1, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180016098  mov     [rsp-8+arg_10], rbx
0x18001609d  push    rbp
0x18001609e  lea     rbp, [rsp-57h]
0x1800160a3  sub     rsp, 90h
0x1800160aa  mov     rax, cs:__security_cookie
0x1800160b1  xor     rax, rsp
0x1800160b4  mov     [rbp+57h+var_8], rax
0x1800160b8  mov     rbx, rdx
0x1800160bb  mov     [rbp+57h+var_20], 7
0x1800160c3  mov     [rbp+57h+var_28], 0
0x1800160cb  xor     eax, eax
0x1800160cd  mov     word ptr [rbp+57h+var_38], ax
0x1800160d1  lea     r8, [rbp+57h+var_38]
0x1800160d5  lea     rdx, aExpires; "Expires"
0x1800160dc  mov     rcx, [rcx+10h]
0x1800160e0  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x1800160e5  test    al, al
0x1800160e7  jz      loc_1800161AE
0x1800160ed  lea     rcx, [rbp+57h+var_38]
0x1800160f1  cmp     [rbp+57h+var_20], 8
0x1800160f6  cmovnb  rcx, [rbp+57h+var_38]; unsigned __int16 *
0x1800160fb  xorps   xmm0, xmm0
0x1800160fe  movups  xmmword ptr [rbp+57h+var_18.wYear], xmm0
0x180016102  mov     r8, rbx; struct _FILETIME *
0x180016105  lea     rdx, [rbp+57h+var_18]; struct _SYSTEMTIME *
0x180016109  call    ?StringToSystemTime@@YA_NPEBGAEAU_SYSTEMTIME@@PEAU_FILETIME@@@Z; StringToSystemTime(ushort const *,_SYSTEMTIME &,_FILETIME *)
0x18001610e  test    al, al
0x180016110  jnz     loc_18001619C
0x180016116  lea     rax, WPP_GLOBAL_Control
0x18001611d  mov     ebx, 0Dh
0x180016122  mov     rcx, cs:WPP_GLOBAL_Control
0x180016129  cmp     rcx, rax
0x18001612c  jz      short loc_180016150
0x18001612e  test    byte ptr [rcx+1Ch], 40h
0x180016132  jz      short loc_180016150
0x180016134  cmp     byte ptr [rcx+19h], 2
0x180016138  jb      short loc_180016150
0x18001613a  lea     edx, [rbx+9]
0x18001613d  mov     r9d, ebx
0x180016140  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180016147  mov     rcx, [rcx+10h]
0x18001614b  call    WPP_SF_D
0x180016150  mov     [rbp+57h+var_68], 0
0x180016154  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x18001615b  mov     [rbp+57h+var_60], rax
0x18001615f  mov     [rbp+57h+var_58], 0
0x180016167  mov     [rbp+57h+var_50], 0
0x18001616f  mov     [rbp+57h+var_48], ebx
0x180016172  mov     [rbp+57h+var_44], 0FFFFFFFFh
0x180016179  mov     [rbp+57h+var_40], 143h
0x180016180  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180016187  mov     [rbp+57h+pExceptionObject], rax
0x18001618b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180016192  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180016196  call    _CxxThrowException_0
0x18001619c  xor     r8d, r8d
0x18001619f  mov     dl, 1
0x1800161a1  lea     rcx, [rbp+57h+var_38]
0x1800161a5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800161aa  mov     al, 1
0x1800161ac  jmp     short loc_1800161BE
0x1800161ae  xor     r8d, r8d
0x1800161b1  mov     dl, 1
0x1800161b3  lea     rcx, [rbp+57h+var_38]
0x1800161b7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800161bc  xor     al, al
0x1800161be  mov     rcx, [rbp+57h+var_8]
0x1800161c2  xor     rcx, rsp; StackCookie
0x1800161c5  call    __security_check_cookie
0x1800161ca  mov     rbx, [rsp+90h+arg_10]
0x1800161d2  add     rsp, 90h
0x1800161d9  pop     rbp
0x1800161da  retn
```
