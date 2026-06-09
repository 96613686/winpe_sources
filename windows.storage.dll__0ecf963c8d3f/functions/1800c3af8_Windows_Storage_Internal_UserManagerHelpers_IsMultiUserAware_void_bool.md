# Windows::Storage::Internal::UserManagerHelpers::IsMultiUserAware(void *,bool *)

- ea: `0x1800c3af8`
- end: `0x1800c3cad`
- name: `?IsMultiUserAware@UserManagerHelpers@Internal@Storage@Windows@@SAJPEAXPEA_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(void *, bool *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800c2ff4`
- `0x1801a9b90`
- `0x1801aa190`
- `0x1802036ac`
- `0x180203a70`

## callees

- `0x1800432f0`
- `0x1800c3af8`
- `0x180293290`
- `0x1802b8868`
- `0x1805e4f80`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800c3b0b`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800c3b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800c3b4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800c3b4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800c3bad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800c3bf1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800c3c1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800c3bad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800c3bf1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800c3c1c`

## string_xrefs

- `0x1800c3b70`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::Internal::UserManagerHelpers::IsMultiUserAware(PackageNameUtils *a1, bool *a2)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  HSTRING *v9; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  int IsEffectiveSupportedUsersMultiple; // eax
  int v12[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+28h] [rbp-20h] BYREF
  char v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku() )
    return 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  if ( PackageNameUtils::GetPackageFullNameFromToken(a1, &string, v9) == -2147009196 )
  {
    WindowsDeleteString(string);
    return 0;
  }
  v16 = 0;
  *(_QWORD *)v12 = &v16;
  v13 = 0;
  v14 = 1;
  v5 = SRCacheManager_Open(0, &v13);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(v12);
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)v5,
      v12[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\usermanagerstatichelpers.cpp",
      (const char *)v5,
      v12[0]);
    v6 = v16;
    v16 = 0;
    if ( v6 )
      SRCacheManager_Close(v6);
LABEL_6:
    WindowsDeleteString(string);
    return v5;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  IsEffectiveSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
                                        (struct StateRepository::Cache::Manager_NoThrow *)&v16,
                                        StringRawBuffer,
                                        a2);
  v5 = IsEffectiveSupportedUsersMultiple;
  if ( IsEffectiveSupportedUsersMultiple < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\usermanagerstatichelpers.cpp",
      (const char *)(unsigned int)IsEffectiveSupportedUsersMultiple,
      v12[0]);
    v7 = v16;
    v16 = 0;
    if ( v7 )
      SRCacheManager_Close(v7);
    goto LABEL_6;
  }
  v8 = v16;
  v16 = 0;
  if ( v8 )
    SRCacheManager_Close(v8);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800c3af8  mov     [rsp+arg_0], rbx
0x1800c3afd  push    rdi
0x1800c3afe  sub     rsp, 40h
0x1800c3b02  mov     rdi, rdx
0x1800c3b05  mov     rbx, rcx
0x1800c3b08  mov     byte ptr [rdx], 0
0x1800c3b0b  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x1800c3b11  test    al, al
0x1800c3b13  jnz     loc_1800C3C34
0x1800c3b19  xor     eax, eax
0x1800c3b1b  mov     rbx, [rsp+48h+arg_0]
0x1800c3b20  add     rsp, 40h
0x1800c3b24  pop     rdi
0x1800c3b25  retn
0x1800c3b26  mov     [rsp+48h+arg_8], 0
0x1800c3b2f  lea     rax, [rsp+48h+arg_8]
0x1800c3b34  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800c3b39  mov     [rsp+48h+var_20], 0
0x1800c3b42  mov     [rsp+48h+var_18], 1
0x1800c3b47  lea     rdx, [rsp+48h+var_20]
0x1800c3b4c  xor     ecx, ecx
0x1800c3b4e  call    cs:__imp_SRCacheManager_Open
0x1800c3b54  mov     ebx, eax
0x1800c3b56  lea     rcx, [rsp+48h+var_28]
0x1800c3b5b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1800c3b60  test    ebx, ebx
0x1800c3b62  jns     loc_1800C3C78
0x1800c3b68  mov     rcx, [rsp+48h]; this
0x1800c3b6d  mov     r9d, ebx; char *
0x1800c3b70  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800c3b77  mov     edx, 0A5h; void *
0x1800c3b7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3b81  mov     rcx, [rsp+48h]; this
0x1800c3b86  mov     r9d, ebx; char *
0x1800c3b89  lea     r8, aOnecoreuapShel_119; "onecoreuap\\shell\\windows.storage\\cap"...
0x1800c3b90  mov     edx, 34h ; '4'; void *
0x1800c3b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3b9a  mov     rcx, [rsp+48h+arg_8]
0x1800c3b9f  mov     [rsp+48h+arg_8], 0
0x1800c3ba8  test    rcx, rcx
0x1800c3bab  jz      short loc_1800C3BB3
0x1800c3bad  call    cs:__imp_SRCacheManager_Close
0x1800c3bb3  mov     rcx, [rsp+48h+string]; string
0x1800c3bb8  call    cs:__imp_WindowsDeleteString
0x1800c3bbe  mov     eax, ebx
0x1800c3bc0  jmp     loc_1800C3B1B
0x1800c3bc5  mov     rcx, [rsp+48h]; this
0x1800c3bca  mov     r9d, ebx; char *
0x1800c3bcd  lea     r8, aOnecoreuapShel_119; "onecoreuap\\shell\\windows.storage\\cap"...
0x1800c3bd4  mov     edx, 36h ; '6'; void *
0x1800c3bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3bde  mov     rcx, [rsp+48h+arg_8]
0x1800c3be3  mov     [rsp+48h+arg_8], 0
0x1800c3bec  test    rcx, rcx
0x1800c3bef  jz      short loc_1800C3BF7
0x1800c3bf1  call    cs:__imp_SRCacheManager_Close
0x1800c3bf7  mov     rcx, [rsp+48h+string]; string
0x1800c3bfc  call    cs:__imp_WindowsDeleteString
0x1800c3c02  mov     eax, ebx
0x1800c3c04  jmp     loc_1800C3B1B
0x1800c3c09  mov     rcx, [rsp+48h+arg_8]
0x1800c3c0e  mov     [rsp+48h+arg_8], 0
0x1800c3c17  test    rcx, rcx
0x1800c3c1a  jz      short loc_1800C3C22
0x1800c3c1c  call    cs:__imp_SRCacheManager_Close
0x1800c3c22  mov     rcx, [rsp+48h+string]; string
0x1800c3c27  call    cs:__imp_WindowsDeleteString
0x1800c3c2d  xor     eax, eax
0x1800c3c2f  jmp     loc_1800C3B1B
0x1800c3c34  mov     [rsp+48h+string], 0
0x1800c3c3d  xor     ecx, ecx; string
0x1800c3c3f  call    cs:__imp_WindowsDeleteString
0x1800c3c45  mov     [rsp+48h+string], 0
0x1800c3c4e  lea     rdx, [rsp+48h+string]; void *
0x1800c3c53  mov     rcx, rbx; this
0x1800c3c56  call    ?GetPackageFullNameFromToken@PackageNameUtils@@YAJPEAXPEAPEAUHSTRING__@@@Z; PackageNameUtils::GetPackageFullNameFromToken(void *,HSTRING__ * *)
0x1800c3c5b  cmp     eax, 80073D54h
0x1800c3c60  jnz     loc_1800C3B26
0x1800c3c66  mov     rcx, [rsp+48h+string]; string
0x1800c3c6b  call    cs:__imp_WindowsDeleteString
0x1800c3c71  xor     eax, eax
0x1800c3c73  jmp     loc_1800C3B1B
0x1800c3c78  xor     edx, edx; length
0x1800c3c7a  mov     rcx, [rsp+48h+string]; string
0x1800c3c7f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3c85  mov     r8, rdi; bool *
0x1800c3c88  mov     rdx, rax; unsigned __int16 *
0x1800c3c8b  lea     rcx, [rsp+48h+arg_8]; struct StateRepository::Cache::Manager_NoThrow *
0x1800c3c90  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800c3c95  mov     ebx, eax
0x1800c3c97  test    eax, eax
0x1800c3c99  jns     loc_1800C3C09
0x1800c3c9f  jmp     loc_1800C3BC5
0x1800c3ca4  mov     eax, dword ptr [rsp+48h+arg_8]
0x1800c3ca8  jmp     loc_1800C3B1B
```
