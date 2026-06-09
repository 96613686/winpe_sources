# ReadBookmark(ushort const *,ushort const *,bool,std::vector<uchar,std::allocator<uchar>> &,bool &)

- ea: `0x18000f1f8`
- end: `0x18000f3c8`
- name: `?ReadBookmark@@YA_NPEBG0_NAEAV?$vector@EV?$allocator@E@std@@@std@@AEA_N@Z`
- size: `464`
- prototype: `char __fastcall(__int64, __int64, char, unsigned __int16 **, _BYTE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18000c724`
- `0x18000e134`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003e6c`
- `0x180005d08`
- `0x1800062d4`
- `0x18000669c`
- `0x18000ef44`
- `0x18000f1f8`
- `0x180011270`
- `0x1800128c0`
- `0x18001fe50`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000f293`
- `msvcrt!_wcsicmp` at `0x18000f293`

## string_xrefs

- `0x18000f34c`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
char __fastcall ReadBookmark(__int64 a1, __int64 a2, char a3, unsigned __int16 **a4, _BYTE *a5)
{
  HKEY v7; // rbx
  __int64 v8; // rdx
  const wchar_t *v9; // rcx
  const unsigned __int16 *v11; // r8
  __int64 v12; // rdx
  unsigned int v13; // ebx
  HKEY v14; // [rsp+20h] [rbp-41h] BYREF
  void **pExceptionObject; // [rsp+28h] [rbp-39h] BYREF
  char v16; // [rsp+30h] [rbp-31h]
  const char *v17; // [rsp+38h] [rbp-29h]
  __int64 v18; // [rsp+40h] [rbp-21h]
  __int64 v19; // [rsp+48h] [rbp-19h]
  unsigned int v20; // [rsp+50h] [rbp-11h]
  int v21; // [rsp+54h] [rbp-Dh]
  int v22; // [rsp+58h] [rbp-9h]
  wchar_t *String1[2]; // [rsp+60h] [rbp-1h] BYREF
  __int64 v24; // [rsp+70h] [rbp+Fh]
  unsigned __int64 v25; // [rsp+78h] [rbp+17h]

  *a5 = 0;
  v14 = 0;
  v7 = OpenSubscriptionEventSourceKey(a1, a2, 0x20019u, 1);
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v14);
  v14 = v7;
  v25 = 7;
  v24 = 0;
  LOWORD(String1[0]) = 0;
  if ( v7 && (unsigned __int8)RegReadStringValue(v7, L"Bookmark", String1) )
  {
    v9 = (const wchar_t *)String1;
    if ( v25 >= 8 )
      v9 = String1[0];
    if ( !_wcsicmp(v9, &word_180026AD8) )
    {
      *a5 = 1;
LABEL_8:
      LOBYTE(v8) = 1;
      std::wstring::_Tidy(String1, v8, 0);
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v14);
      return 0;
    }
  }
  else
  {
    if ( !a3 )
      goto LABEL_8;
    std::wstring::assign(String1, L"http://schemas.dmtf.org/wbem/wsman/1/wsman/bookmark/earliest");
  }
  std::vector<unsigned char>::resize(a4, 2 * v24 + 2);
  v11 = (const unsigned __int16 *)String1;
  if ( v25 >= 8 )
    v11 = String1[0];
  v13 = StringCchCopyW(*a4, v24 + 1, v11);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v13);
    }
    v16 = 0;
    v17 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v18 = 0;
    v19 = 0;
    v20 = v13;
    v21 = -1;
    v22 = 507;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(String1, v12, 0);
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v14);
  return 1;
}

```

## disassembly

```asm
0x18000f1f8  push    rbp
0x18000f1fa  push    rbx
0x18000f1fb  push    rsi
0x18000f1fc  push    rdi
0x18000f1fd  push    r14
0x18000f1ff  lea     rbp, [rsp-2Fh]
0x18000f204  sub     rsp, 90h
0x18000f20b  mov     rax, cs:__security_cookie
0x18000f212  xor     rax, rsp
0x18000f215  mov     [rbp+4Fh+var_30], rax
0x18000f219  mov     r14, r9
0x18000f21c  mov     sil, r8b
0x18000f21f  mov     rdi, [rbp+4Fh+arg_20]
0x18000f223  mov     byte ptr [rdi], 0
0x18000f226  mov     [rbp+4Fh+var_90], 0
0x18000f22e  mov     r9b, 1
0x18000f231  mov     r8d, 20019h
0x18000f237  call    OpenSubscriptionEventSourceKey
0x18000f23c  mov     rbx, rax
0x18000f23f  lea     rcx, [rbp+4Fh+var_90]; this
0x18000f243  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000f248  mov     [rbp+4Fh+var_90], rbx
0x18000f24c  mov     [rbp+4Fh+var_38], 7
0x18000f254  mov     [rbp+4Fh+var_40], 0
0x18000f25c  xor     ecx, ecx
0x18000f25e  mov     word ptr [rbp+4Fh+String1], cx
0x18000f262  test    rbx, rbx
0x18000f265  jz      short loc_18000F2A2
0x18000f267  lea     r8, [rbp+4Fh+String1]
0x18000f26b  lea     rdx, aBookmark; "Bookmark"
0x18000f272  mov     rcx, rbx
0x18000f275  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18000f27a  test    al, al
0x18000f27c  jz      short loc_18000F2A2
0x18000f27e  lea     rcx, [rbp+4Fh+String1]
0x18000f282  cmp     [rbp+4Fh+var_38], 8
0x18000f287  cmovnb  rcx, [rbp+4Fh+String1]; String1
0x18000f28c  lea     rdx, word_180026AD8; String2
0x18000f293  call    cs:__imp__wcsicmp
0x18000f299  test    eax, eax
0x18000f29b  jnz     short loc_18000F2D6
0x18000f29d  mov     byte ptr [rdi], 1
0x18000f2a0  jmp     short loc_18000F2A7
0x18000f2a2  test    sil, sil
0x18000f2a5  jnz     short loc_18000F2C6
0x18000f2a7  xor     r8d, r8d
0x18000f2aa  mov     dl, 1
0x18000f2ac  lea     rcx, [rbp+4Fh+String1]
0x18000f2b0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f2b5  nop
0x18000f2b6  lea     rcx, [rbp+4Fh+var_90]; this
0x18000f2ba  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000f2bf  xor     al, al
0x18000f2c1  jmp     loc_18000F3AE
0x18000f2c6  lea     rdx, aHttpSchemasDmt; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18000f2cd  lea     rcx, [rbp+4Fh+String1]
0x18000f2d1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000f2d6  mov     rdx, [rbp+4Fh+var_40]
0x18000f2da  lea     rdx, ds:2[rdx*2]
0x18000f2e2  mov     rcx, r14
0x18000f2e5  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000f2ea  lea     r8, [rbp+4Fh+String1]
0x18000f2ee  cmp     [rbp+4Fh+var_38], 8
0x18000f2f3  cmovnb  r8, [rbp+4Fh+String1]; unsigned __int16 *
0x18000f2f8  mov     rdx, [rbp+4Fh+var_40]
0x18000f2fc  inc     rdx; unsigned __int64
0x18000f2ff  mov     rcx, [r14]; unsigned __int16 *
0x18000f302  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f307  mov     ebx, eax
0x18000f309  test    eax, eax
0x18000f30b  jz      loc_18000F394
0x18000f311  lea     rax, WPP_GLOBAL_Control
0x18000f318  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f31f  cmp     rcx, rax
0x18000f322  jz      short loc_18000F348
0x18000f324  test    byte ptr [rcx+1Ch], 10h
0x18000f328  jz      short loc_18000F348
0x18000f32a  cmp     byte ptr [rcx+19h], 2
0x18000f32e  jb      short loc_18000F348
0x18000f330  mov     edx, 13h
0x18000f335  mov     r9d, ebx
0x18000f338  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000f33f  mov     rcx, [rcx+10h]
0x18000f343  call    WPP_SF_D
0x18000f348  mov     [rbp+4Fh+var_80], 0
0x18000f34c  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000f353  mov     [rbp+4Fh+var_78], rax
0x18000f357  mov     [rbp+4Fh+var_70], 0
0x18000f35f  mov     [rbp+4Fh+var_68], 0
0x18000f367  mov     [rbp+4Fh+var_60], ebx
0x18000f36a  mov     [rbp+4Fh+var_5C], 0FFFFFFFFh
0x18000f371  mov     [rbp+4Fh+var_58], 1FBh
0x18000f378  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000f37f  mov     [rbp+4Fh+pExceptionObject], rax
0x18000f383  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000f38a  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000f38e  call    _CxxThrowException_0
0x18000f394  xor     r8d, r8d
0x18000f397  mov     dl, 1
0x18000f399  lea     rcx, [rbp+4Fh+String1]
0x18000f39d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f3a2  nop
0x18000f3a3  lea     rcx, [rbp+4Fh+var_90]; this
0x18000f3a7  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000f3ac  mov     al, 1
0x18000f3ae  mov     rcx, [rbp+4Fh+var_30]
0x18000f3b2  xor     rcx, rsp; StackCookie
0x18000f3b5  call    __security_check_cookie
0x18000f3ba  add     rsp, 90h
0x18000f3c1  pop     r14
0x18000f3c3  pop     rdi
0x18000f3c4  pop     rsi
0x18000f3c5  pop     rbx
0x18000f3c6  pop     rbp
0x18000f3c7  retn
```
