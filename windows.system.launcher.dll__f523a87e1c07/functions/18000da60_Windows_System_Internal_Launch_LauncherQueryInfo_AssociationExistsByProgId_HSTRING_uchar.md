# Windows::System::Internal::Launch::LauncherQueryInfo::AssociationExistsByProgId(HSTRING__ *,uchar *)

- ea: `0x18000da60`
- end: `0x18000dd31`
- name: `?AssociationExistsByProgId@LauncherQueryInfo@Launch@Internal@System@Windows@@EEAAJPEAUHSTRING__@@PEAE@Z`
- size: `721`
- prototype: `int(Windows::System::Internal::Launch::LauncherQueryInfo *__hidden this, HSTRING, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006280`
- `0x18000c398`
- `0x18000da60`
- `0x18000e08c`
- `0x18000e680`
- `0x18000f194`
- `0x180010c04`
- `0x180017b70`
- `0x1800596d8`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000dafe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000dafe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000db22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000db94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000db22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000db94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dbd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dc12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dc51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dbd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dc12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dc51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dba0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dc9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dba0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dc9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000daa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000daa8`

## string_xrefs

- `0x18000dce0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::Internal::Launch::LauncherQueryInfo::AssociationExistsByProgId(
        Windows::System::Internal::Launch::LauncherQueryInfo *this,
        HSTRING a2,
        unsigned __int8 *a3)
{
  HRESULT v5; // eax
  const WCHAR *StringRawBuffer; // rcx
  const unsigned __int16 *v7; // rdx
  unsigned __int8 v8; // di
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  const char *v12; // r9
  __int64 result; // rax
  unsigned __int16 *v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  int v20; // [rsp+20h] [rbp-B8h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+30h] [rbp-A8h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-A0h]
  __int64 v24; // [rsp+40h] [rbp-98h] BYREF
  char v25; // [rsp+48h] [rbp-90h]
  __int64 v26; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v27[72]; // [rsp+58h] [rbp-80h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  *a3 = 0;
  WindowsDeleteString(0);
  newString = 0;
  v5 = WindowsDuplicateString(a2, &newString);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BF,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v5,
        v20);
    StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
    if ( !DynamicProgIdHelpers::IsProgIdEnabled(StringRawBuffer, v7) )
    {
      *a3 = 0;
      WindowsDeleteString(newString);
      return 0;
    }
    v22 = 0;
    v23 = &v22;
    v24 = 0;
    v8 = 1;
    v25 = 1;
    v9 = SRCacheManager_Open(0, &v24);
    if ( v25 )
    {
      v10 = *v23;
      *v23 = v24;
      if ( v10 )
        SRCacheManager_Close(v10);
    }
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
        (const char *)(unsigned int)v9,
        v20);
    else
      v9 = 0;
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C9,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v9,
        v20);
    v26 = 0;
    memset_0(v27, 0, 0x44u);
    v28 = 0;
    LOBYTE(v20) = 0;
    if ( (unsigned __int8)GetUserOrDefaultAccount(
                            (struct StateRepository::Cache::Manager_NoThrow *)&v22,
                            (struct StateRepository::Cache::Entity::User_NoThrow *)&v26) )
    {
      v14 = (unsigned __int16 *)WindowsGetStringRawBuffer(newString, 0);
      v15 = StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::ExistsByUserOrDefaultAccountAndProgID(
              (struct StateRepository::Cache::Manager_NoThrow *)&v22,
              v26,
              v14,
              (bool *)&v20);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6D0,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v15,
          v20);
      if ( (_BYTE)v20 )
        goto LABEL_13;
      v16 = WindowsGetStringRawBuffer(newString, 0);
      v17 = StateRepository::Cache::Entity::Protocol_NoThrow::ExistsByUserOrDefaultAccountAndProgID(
              (struct StateRepository::Cache::Manager_NoThrow *)&v22,
              v26,
              v16,
              (bool *)&v20);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6D3,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v17,
          v20);
      if ( (_BYTE)v20 )
        goto LABEL_13;
      v18 = WindowsGetStringRawBuffer(newString, 0);
      v19 = StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow::ExistsByUserOrDefaultAccountAndProgID(
              (struct StateRepository::Cache::Manager_NoThrow *)&v22,
              v26,
              v18,
              (bool *)&v20);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6D6,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v19,
          v20);
    }
    if ( !(_BYTE)v20 )
      v8 = 0;
LABEL_13:
    *a3 = v8;
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCacheManager_Close(v11);
    WindowsDeleteString(newString);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6DD,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18000da60  mov     [rsp+arg_0], rbx
0x18000da65  push    rsi
0x18000da66  push    rdi
0x18000da67  push    r14
0x18000da69  sub     rsp, 0C0h
0x18000da70  mov     rax, cs:__security_cookie
0x18000da77  xor     rax, rsp
0x18000da7a  mov     [rsp+0D8h+var_28], rax
0x18000da82  mov     rsi, r8
0x18000da85  mov     rbx, rdx
0x18000da88  xor     r14d, r14d
0x18000da8b  mov     [r8], r14b
0x18000da8e  mov     [rsp+0D8h+newString], r14
0x18000da93  xor     ecx, ecx; string
0x18000da95  call    cs:__imp_WindowsDeleteString
0x18000da9b  mov     [rsp+0D8h+newString], r14
0x18000daa0  lea     rdx, [rsp+0D8h+newString]; newString
0x18000daa5  mov     rcx, rbx; string
0x18000daa8  call    cs:__imp_WindowsDuplicateString
0x18000daae  mov     rcx, [rsp+0D8h]; this
0x18000dab6  test    eax, eax
0x18000dab8  js      loc_18000DCAC
0x18000dabe  xor     edx, edx; length
0x18000dac0  mov     rcx, [rsp+0D8h+newString]; string
0x18000dac5  call    cs:__imp_WindowsGetStringRawBuffer
0x18000dacb  mov     rcx, rax; sourceString
0x18000dace  call    ?IsProgIdEnabled@DynamicProgIdHelpers@@YA_NPEBG@Z; DynamicProgIdHelpers::IsProgIdEnabled(ushort const *)
0x18000dad3  test    al, al
0x18000dad5  jz      loc_18000DC97
0x18000dadb  mov     [rsp+0D8h+var_A8], r14
0x18000dae0  lea     rax, [rsp+0D8h+var_A8]
0x18000dae5  mov     [rsp+0D8h+var_A0], rax
0x18000daea  mov     [rsp+0D8h+var_98], r14
0x18000daef  mov     dil, 1
0x18000daf2  mov     [rsp+0D8h+var_90], dil
0x18000daf7  lea     rdx, [rsp+0D8h+var_98]
0x18000dafc  xor     ecx, ecx
0x18000dafe  call    cs:__imp_SRCacheManager_Open
0x18000db04  mov     ebx, eax
0x18000db06  cmp     [rsp+0D8h+var_90], r14b
0x18000db0b  jz      short loc_18000DB28
0x18000db0d  mov     rdx, [rsp+0D8h+var_A0]
0x18000db12  mov     rcx, [rdx]
0x18000db15  mov     rax, [rsp+0D8h+var_98]
0x18000db1a  mov     [rdx], rax
0x18000db1d  test    rcx, rcx
0x18000db20  jz      short loc_18000DB28
0x18000db22  call    cs:__imp_SRCacheManager_Close
0x18000db28  test    ebx, ebx
0x18000db2a  js      loc_18000DCD5
0x18000db30  mov     ebx, r14d
0x18000db33  mov     rcx, [rsp+0D8h]; this
0x18000db3b  test    ebx, ebx
0x18000db3d  js      loc_18000DCC1
0x18000db43  mov     [rsp+0D8h+var_88], r14
0x18000db48  xor     edx, edx; Val
0x18000db4a  lea     r8d, [rdx+44h]; Size
0x18000db4e  lea     rcx, [rsp+0D8h+var_80]; void *
0x18000db53  call    memset_0
0x18000db58  mov     [rsp+0D8h+var_38], r14
0x18000db60  mov     byte ptr [rsp+0D8h+var_B8], r14b; int
0x18000db65  lea     rdx, [rsp+0D8h+var_88]; struct StateRepository::Cache::Entity::User_NoThrow *
0x18000db6a  lea     rcx, [rsp+0D8h+var_A8]; struct StateRepository::Cache::Manager_NoThrow *
0x18000db6f  call    ?GetUserOrDefaultAccount@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@AEAVUser_NoThrow@Entity@23@@Z; GetUserOrDefaultAccount(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &)
0x18000db74  test    al, al
0x18000db76  jnz     short loc_18000DBCC
0x18000db78  cmp     byte ptr [rsp+0D8h+var_B8], r14b
0x18000db7d  jnz     short loc_18000DB82
0x18000db7f  mov     dil, r14b
0x18000db82  mov     [rsi], dil
0x18000db85  mov     rcx, [rsp+0D8h+var_A8]
0x18000db8a  mov     [rsp+0D8h+var_A8], r14
0x18000db8f  test    rcx, rcx
0x18000db92  jz      short loc_18000DB9B
0x18000db94  call    cs:__imp_SRCacheManager_Close
0x18000db9a  nop
0x18000db9b  mov     rcx, [rsp+0D8h+newString]; string
0x18000dba0  call    cs:__imp_WindowsDeleteString
0x18000dba6  xor     eax, eax
0x18000dba8  mov     rcx, [rsp+0D8h+var_28]
0x18000dbb0  xor     rcx, rsp; StackCookie
0x18000dbb3  call    __security_check_cookie
0x18000dbb8  mov     rbx, [rsp+0D8h+arg_0]
0x18000dbc0  add     rsp, 0C0h
0x18000dbc7  pop     r14
0x18000dbc9  pop     rdi
0x18000dbca  pop     rsi
0x18000dbcb  retn
0x18000dbcc  xor     edx, edx; length
0x18000dbce  mov     rcx, [rsp+0D8h+newString]; string
0x18000dbd3  call    cs:__imp_WindowsGetStringRawBuffer
0x18000dbd9  lea     r9, [rsp+0D8h+var_B8]; bool *
0x18000dbde  mov     r8, rax; unsigned __int16 *
0x18000dbe1  mov     rdx, [rsp+0D8h+var_88]; __int64
0x18000dbe6  lea     rcx, [rsp+0D8h+var_A8]; struct StateRepository::Cache::Manager_NoThrow *
0x18000dbeb  call    ?ExistsByUserOrDefaultAccountAndProgID@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::ExistsByUserOrDefaultAccountAndProgID(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,bool &)
0x18000dbf0  mov     rcx, [rsp+0D8h]; this
0x18000dbf8  test    eax, eax
0x18000dbfa  js      loc_18000DCF6
0x18000dc00  cmp     byte ptr [rsp+0D8h+var_B8], r14b
0x18000dc05  jnz     loc_18000DB82
0x18000dc0b  xor     edx, edx; length
0x18000dc0d  mov     rcx, [rsp+0D8h+newString]; string
0x18000dc12  call    cs:__imp_WindowsGetStringRawBuffer
0x18000dc18  lea     r9, [rsp+0D8h+var_B8]; bool *
0x18000dc1d  mov     r8, rax; unsigned __int16 *
0x18000dc20  mov     rdx, [rsp+0D8h+var_88]; __int64
0x18000dc25  lea     rcx, [rsp+0D8h+var_A8]; struct StateRepository::Cache::Manager_NoThrow *
0x18000dc2a  call    ?ExistsByUserOrDefaultAccountAndProgID@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_N@Z; StateRepository::Cache::Entity::Protocol_NoThrow::ExistsByUserOrDefaultAccountAndProgID(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,bool &)
0x18000dc2f  mov     rcx, [rsp+0D8h]; this
0x18000dc37  test    eax, eax
0x18000dc39  js      loc_18000DD0F
0x18000dc3f  cmp     byte ptr [rsp+0D8h+var_B8], r14b
0x18000dc44  jnz     loc_18000DB82
0x18000dc4a  xor     edx, edx; length
0x18000dc4c  mov     rcx, [rsp+0D8h+newString]; string
0x18000dc51  call    cs:__imp_WindowsGetStringRawBuffer
0x18000dc57  lea     r9, [rsp+0D8h+var_B8]; bool *
0x18000dc5c  mov     r8, rax; unsigned __int16 *
0x18000dc5f  mov     rdx, [rsp+0D8h+var_88]; __int64
0x18000dc64  lea     rcx, [rsp+0D8h+var_A8]; struct StateRepository::Cache::Manager_NoThrow *
0x18000dc69  call    ?ExistsByUserOrDefaultAccountAndProgID@AppUriHandlerLauncherInfo_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow::ExistsByUserOrDefaultAccountAndProgID(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,bool &)
0x18000dc6e  mov     rcx, [rsp+0D8h]; this
0x18000dc76  test    eax, eax
0x18000dc78  jns     loc_18000DB78
0x18000dc7e  mov     r9d, eax; char *
0x18000dc81  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000dc88  mov     edx, 6D6h; void *
0x18000dc8d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dc92  jmp     loc_18000DB78
0x18000dc97  mov     [rsi], r14b
0x18000dc9a  mov     rcx, [rsp+0D8h+newString]; string
0x18000dc9f  call    cs:__imp_WindowsDeleteString
0x18000dca5  xor     eax, eax
0x18000dca7  jmp     loc_18000DBA8
0x18000dcac  mov     r9d, eax; char *
0x18000dcaf  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000dcb6  mov     edx, 6BFh; void *
0x18000dcbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000dcc1  mov     r9d, ebx; char *
0x18000dcc4  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000dccb  mov     edx, 6C9h; void *
0x18000dcd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000dcd5  mov     rcx, [rsp+0D8h]; this
0x18000dcdd  mov     r9d, ebx; char *
0x18000dce0  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000dce7  mov     edx, 0A5h; void *
0x18000dcec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcf1  jmp     loc_18000DB33
0x18000dcf6  mov     r9d, eax; char *
0x18000dcf9  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000dd00  mov     edx, 6D0h; void *
0x18000dd05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dd0a  jmp     loc_18000DC00
0x18000dd0f  mov     r9d, eax; char *
0x18000dd12  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000dd19  mov     edx, 6D3h; void *
0x18000dd1e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dd23  jmp     loc_18000DC3F
0x18000dd28  mov     eax, dword ptr [rsp+0D8h+newString]
0x18000dd2c  jmp     loc_18000DBA8
```
