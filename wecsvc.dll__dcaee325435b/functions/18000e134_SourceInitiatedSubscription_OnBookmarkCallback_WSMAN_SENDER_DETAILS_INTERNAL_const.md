# SourceInitiatedSubscription::OnBookmarkCallback(WSMAN_SENDER_DETAILS_INTERNAL const *)

- ea: `0x18000e134`
- end: `0x18000e2f2`
- name: `?OnBookmarkCallback@SourceInitiatedSubscription@@AEAAPEAUWSMAN_OBJECT@@PEBVWSMAN_SENDER_DETAILS_INTERNAL@@@Z`
- size: `446`
- prototype: `struct WSMAN_OBJECT *__fastcall(SourceInitiatedSubscription *__hidden this, const struct WSMAN_SENDER_DETAILS_INTERNAL *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000ada0`

## callees

- `0x18000195c`
- `0x1800024b0`
- `0x1800032dc`
- `0x180003e6c`
- `0x180006334`
- `0x18000e134`
- `0x18000ef44`
- `0x18000f1f8`
- `0x1800128c0`
- `0x18001351c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e27f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e27f`
- `WsmSvc!WSManEncodeObject` at `0x18000e249`
- `WsmSvc!WSManEncodeObject` at `0x18000e249`

## string_xrefs

- `0x18000e2cf`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
struct WSMAN_OBJECT *__fastcall SourceInitiatedSubscription::OnBookmarkCallback(
        SourceInitiatedSubscription *this,
        const struct WSMAN_SENDER_DETAILS_INTERNAL *a2)
{
  __int64 v3; // r15
  bool v4; // r14
  char *v5; // rdi
  char *v6; // rbx
  char *v7; // rcx
  HKEY v8; // rax
  unsigned __int16 *v9; // rbx
  __int64 v11; // rbx
  DWORD LastError; // ebx
  unsigned __int16 *v13[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v14; // [rsp+40h] [rbp-40h]
  _BYTE pExceptionObject[56]; // [rsp+48h] [rbp-38h] BYREF
  HKEY v16; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+B8h] [rbp+38h] BYREF

  *(_OWORD *)v13 = 0;
  v14 = 0;
  v17 = 0;
  v3 = *((_QWORD *)a2 + 5);
  v4 = 0;
  v5 = (char *)this + 312;
  v6 = (char *)this + 56;
  if ( !*((_QWORD *)this + 41) )
  {
    if ( *((_QWORD *)this + 10) < 8u )
      v7 = (char *)this + 56;
    else
      v7 = *(char **)v6;
    v8 = OpenSubscriptionEventSourceKey((__int64)v7, 0, 0x20019u, 1);
    v16 = v8;
    if ( v8 )
      v4 = (unsigned __int8)RegReadStringValue(v8, L"query", v5) != 0;
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v16);
  }
  LOBYTE(v16) = 0;
  if ( *((_QWORD *)v6 + 3) >= 8u )
    v6 = *(char **)v6;
  if ( (unsigned __int8)ReadBookmark((_DWORD)v6, v3, *((_BYTE *)this + 224), (unsigned int)v13, (__int64)&v16) )
  {
    v9 = v13[0];
    if ( v4 )
    {
      if ( *((_QWORD *)v5 + 3) >= 8u )
        v5 = *(char **)v5;
      if ( !IsBookMarkMatchToQueryFilter((const unsigned __int16 *)v5, v13[0]) )
      {
        std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(v13);
        return 0;
      }
    }
    if ( !(unsigned int)WSManEncodeObject(v9, (unsigned int)(LODWORD(v13[1]) - (_DWORD)v9), 0x4000, &v17) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        LastError,
        "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
        3134);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  v11 = v17;
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(v13);
  return (struct WSMAN_OBJECT *)v11;
}

```

## disassembly

```asm
0x18000e134  mov     [rsp-28h+arg_10], rbx
0x18000e139  mov     [rsp-28h+arg_18], rsi
0x18000e13e  push    rbp
0x18000e13f  push    rdi
0x18000e140  push    r13
0x18000e142  push    r14
0x18000e144  push    r15
0x18000e146  mov     rbp, rsp
0x18000e149  sub     rsp, 80h
0x18000e150  mov     rsi, rcx
0x18000e153  xorps   xmm0, xmm0
0x18000e156  movdqu  xmmword ptr [rbp+var_50], xmm0
0x18000e15b  mov     [rbp+var_40], 0
0x18000e163  mov     [rbp+arg_8], 0
0x18000e16b  mov     r15, [rdx+28h]
0x18000e16f  xor     r14b, r14b
0x18000e172  lea     rdi, [rcx+138h]
0x18000e179  lea     rbx, [rcx+38h]
0x18000e17d  cmp     qword ptr [rdi+10h], 0
0x18000e182  jnz     short loc_18000E1D7
0x18000e184  cmp     qword ptr [rbx+18h], 8
0x18000e189  jb      short loc_18000E190
0x18000e18b  mov     rcx, [rbx]
0x18000e18e  jmp     short loc_18000E193
0x18000e190  mov     rcx, rbx
0x18000e193  mov     r13d, 1
0x18000e199  mov     r9b, r13b
0x18000e19c  xor     edx, edx
0x18000e19e  mov     r8d, 20019h
0x18000e1a4  call    OpenSubscriptionEventSourceKey
0x18000e1a9  mov     [rbp+arg_0], rax
0x18000e1ad  test    rax, rax
0x18000e1b0  jz      short loc_18000E1CE
0x18000e1b2  mov     r8, rdi
0x18000e1b5  lea     rdx, aQuery; "query"
0x18000e1bc  mov     rcx, rax
0x18000e1bf  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18000e1c4  movzx   r14d, r14b
0x18000e1c8  test    al, al
0x18000e1ca  cmovnz  r14d, r13d
0x18000e1ce  lea     rcx, [rbp+arg_0]; this
0x18000e1d2  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000e1d7  mov     byte ptr [rbp+arg_0], 0
0x18000e1db  cmp     qword ptr [rbx+18h], 8
0x18000e1e0  jb      short loc_18000E1E5
0x18000e1e2  mov     rbx, [rbx]
0x18000e1e5  lea     rax, [rbp+arg_0]
0x18000e1e9  mov     [rsp+80h+var_60], rax
0x18000e1ee  lea     r9, [rbp+var_50]
0x18000e1f2  mov     r8b, [rsi+0E0h]
0x18000e1f9  mov     rdx, r15
0x18000e1fc  mov     rcx, rbx
0x18000e1ff  call    ?ReadBookmark@@YA_NPEBG0_NAEAV?$vector@EV?$allocator@E@std@@@std@@AEA_N@Z; ReadBookmark(ushort const *,ushort const *,bool,std::vector<uchar> &,bool &)
0x18000e204  test    al, al
0x18000e206  jz      short loc_18000E253
0x18000e208  mov     rbx, [rbp+var_50]
0x18000e20c  test    r14b, r14b
0x18000e20f  jz      short loc_18000E237
0x18000e211  cmp     qword ptr [rdi+18h], 8
0x18000e216  jb      short loc_18000E21B
0x18000e218  mov     rdi, [rdi]
0x18000e21b  mov     rdx, rbx; unsigned __int16 *
0x18000e21e  mov     rcx, rdi; unsigned __int16 *
0x18000e221  call    ?IsBookMarkMatchToQueryFilter@@YA_NPEBG0@Z; IsBookMarkMatchToQueryFilter(ushort const *,ushort const *)
0x18000e226  test    al, al
0x18000e228  jnz     short loc_18000E237
0x18000e22a  lea     rcx, [rbp+var_50]
0x18000e22e  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18000e233  xor     eax, eax
0x18000e235  jmp     short loc_18000E263
0x18000e237  mov     edx, dword ptr [rbp+var_50+8]
0x18000e23a  sub     edx, ebx
0x18000e23c  lea     r9, [rbp+arg_8]
0x18000e240  mov     r8d, 4000h
0x18000e246  mov     rcx, rbx
0x18000e249  call    cs:__imp_WSManEncodeObject
0x18000e24f  test    eax, eax
0x18000e251  jz      short loc_18000E27F
0x18000e253  mov     rbx, [rbp+arg_8]
0x18000e257  lea     rcx, [rbp+var_50]
0x18000e25b  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18000e260  mov     rax, rbx
0x18000e263  lea     r11, [rsp+80h+var_s0]
0x18000e26b  mov     rbx, [r11+40h]
0x18000e26f  mov     rsi, [r11+48h]
0x18000e273  mov     rsp, r11
0x18000e276  pop     r15
0x18000e278  pop     r14
0x18000e27a  pop     r13
0x18000e27c  pop     rdi
0x18000e27d  pop     rbp
0x18000e27e  retn
0x18000e27f  call    cs:__imp_GetLastError
0x18000e285  nop
0x18000e286  mov     ebx, eax
0x18000e288  mov     eax, 507h
0x18000e28d  test    ebx, ebx
0x18000e28f  cmovz   ebx, eax
0x18000e292  lea     rax, WPP_GLOBAL_Control
0x18000e299  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2a0  cmp     rcx, rax
0x18000e2a3  jz      short loc_18000E2C9
0x18000e2a5  test    byte ptr [rcx+1Ch], 10h
0x18000e2a9  jz      short loc_18000E2C9
0x18000e2ab  cmp     byte ptr [rcx+19h], 2
0x18000e2af  jb      short loc_18000E2C9
0x18000e2b1  mov     edx, 4Eh ; 'N'
0x18000e2b6  mov     r9d, ebx
0x18000e2b9  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000e2c0  mov     rcx, [rcx+10h]
0x18000e2c4  call    WPP_SF_D
0x18000e2c9  mov     r9d, 0C3Eh; int
0x18000e2cf  lea     r8, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000e2d6  mov     edx, ebx; unsigned int
0x18000e2d8  lea     rcx, [rbp+pExceptionObject]; this
0x18000e2dc  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000e2e1  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000e2e8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000e2ec  call    _CxxThrowException_0
```
