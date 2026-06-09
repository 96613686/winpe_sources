# GuidToMergeDbFileAndRegKey(_GUID,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x140004c74`
- end: `0x140004df1`
- name: `?GuidToMergeDbFileAndRegKey@@YAHU_GUID@@PEAG_K12@Z`
- size: `381`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140005b30`
- `0x140008500`

## callees

- `0x140004c74`
- `0x140007024`
- `0x14001008c`
- `0x140021ee4`
- `0x140022210`
- `0x14002aa4c`
- `0x14002e3e2`
- `0x14002e420`

## string_xrefs

- `0x140004d8e`: `MergeSdb_GetInstalledSdbByGuid`
- `0x140004d83`: `Failed to copy string (%d)`

## pseudocode

```c
__int64 __fastcall GuidToMergeDbFileAndRegKey(struct _GUID *a1, unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4)
{
  __int64 *v5; // rdi
  unsigned int v8; // esi
  __int64 v9; // rbx
  int MergeRegistrationInTarget; // eax
  int v11; // ebx
  int v12; // eax
  unsigned int v13; // r11d
  int v14; // eax
  __int64 v15; // r8
  __int64 v17; // [rsp+20h] [rbp-F8h]
  __int128 v18; // [rsp+30h] [rbp-E8h] BYREF
  unsigned __int16 *v19[18]; // [rsp+40h] [rbp-D8h] BYREF
  int v20; // [rsp+D0h] [rbp-48h]
  __int64 v21; // [rsp+D8h] [rbp-40h]

  v5 = (__int64 *)&off_140030E40;
  v8 = 0;
  while ( 1 )
  {
    v9 = *v5;
    v18 = (__int128)*a1;
    memset_0(v19, 0, sizeof(v19));
    Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v19);
    v20 = 0;
    v21 = 0;
    MergeRegistrationInTarget = Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(
                                  (Pca::MergeSdb::Utils::RegistrationInfo *)v19,
                                  v9,
                                  (__int64 (__fastcall *)(__int64, HKEY *, char *))Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToDatabaseId,
                                  (__int64)&v18);
    v11 = MergeRegistrationInTarget;
    if ( MergeRegistrationInTarget )
    {
      if ( MergeRegistrationInTarget != 2 )
      {
        LODWORD(v17) = MergeRegistrationInTarget;
        AslLogCallPrintf(
          1,
          "MergeSdb_GetInstalledSdbByGuid",
          1673,
          "Failed to find merge registration for target name and guid (%d)",
          v17);
      }
    }
    else
    {
      v12 = StringCchCopyW(a4, 0x104u, v19[14]);
      v11 = v12;
      if ( v12 < 0 )
      {
        if ( (v12 & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)v12;
        v15 = 1680;
      }
      else
      {
        v14 = StringCchCopyW(a2, v13, v19[0]);
        v11 = v14;
        if ( v14 >= 0 )
        {
          v11 = 0;
          goto LABEL_15;
        }
        if ( (v14 & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)v14;
        v15 = 1685;
      }
      LODWORD(v17) = v11;
      AslLogCallPrintf(1, "MergeSdb_GetInstalledSdbByGuid", v15, "Failed to copy string (%d)", v17);
    }
LABEL_15:
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v19);
    if ( !v11 )
      return 1;
    v5 += 3;
    if ( v5 == qword_140030E88 )
      return v8;
  }
}

```

## disassembly

```asm
0x140004c74  mov     [rsp+arg_10], rbx
0x140004c79  push    rbp
0x140004c7a  push    rsi
0x140004c7b  push    rdi
0x140004c7c  push    r14
0x140004c7e  push    r15
0x140004c80  sub     rsp, 0F0h
0x140004c87  mov     rax, cs:__security_cookie
0x140004c8e  xor     rax, rsp
0x140004c91  mov     [rsp+118h+var_38], rax
0x140004c99  mov     r14, r9
0x140004c9c  lea     rdi, off_140030E40; "sysmain.sdb"
0x140004ca3  mov     rbp, rdx
0x140004ca6  mov     r15, rcx
0x140004ca9  xor     esi, esi
0x140004cab  movaps  xmm0, xmmword ptr [r15]
0x140004caf  lea     rcx, [rsp+118h+var_D8]; void *
0x140004cb4  mov     rbx, [rdi]
0x140004cb7  xor     edx, edx; Val
0x140004cb9  mov     r8d, 90h; Size
0x140004cbf  movdqa  [rsp+118h+var_E8], xmm0
0x140004cc5  call    memset_0
0x140004cca  lea     rcx, [rsp+118h+var_D8]; this
0x140004ccf  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x140004cd4  lea     r9, [rsp+118h+var_E8]
0x140004cd9  mov     [rsp+118h+var_48], esi
0x140004ce0  lea     r8, ?CompareRegistrationToDatabaseId@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z; Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToDatabaseId(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &)
0x140004ce7  mov     [rsp+118h+var_40], rsi
0x140004cef  mov     rdx, rbx
0x140004cf2  lea     rcx, [rsp+118h+var_D8]; this
0x140004cf7  call    ?FindMergeRegistrationInTarget@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV1234@PEBGP6AKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z2@Z; Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(Pca::MergeSdb::Utils::RegistrationInfo &,ushort const *,ulong (*)(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &),void *)
0x140004cfc  mov     ebx, eax
0x140004cfe  test    eax, eax
0x140004d00  jz      short loc_140004D1E
0x140004d02  cmp     eax, 2
0x140004d05  jz      loc_140004D9F
0x140004d0b  mov     [rsp+118h+var_F8], eax
0x140004d0f  lea     r9, aFailedToFindMe; "Failed to find merge registration for t"...
0x140004d16  mov     r8d, 689h
0x140004d1c  jmp     short loc_140004D8E
0x140004d1e  mov     r8, [rsp+118h+var_68]; unsigned __int16 *
0x140004d26  mov     r11d, 104h
0x140004d2c  mov     edx, r11d; unsigned __int64
0x140004d2f  mov     rcx, r14; unsigned __int16 *
0x140004d32  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140004d37  mov     ebx, eax
0x140004d39  test    eax, eax
0x140004d3b  js      short loc_140004D6E
0x140004d3d  mov     r8, [rsp+118h+var_D8]; unsigned __int16 *
0x140004d42  mov     edx, r11d; unsigned __int64
0x140004d45  mov     rcx, rbp; unsigned __int16 *
0x140004d48  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140004d4d  mov     ebx, eax
0x140004d4f  test    eax, eax
0x140004d51  js      short loc_140004D57
0x140004d53  xor     ebx, ebx
0x140004d55  jmp     short loc_140004D9F
0x140004d57  and     eax, 1FFF0000h
0x140004d5c  cmp     eax, 70000h
0x140004d61  jnz     short loc_140004D66
0x140004d63  movzx   ebx, bx
0x140004d66  mov     r8d, 695h
0x140004d6c  jmp     short loc_140004D83
0x140004d6e  and     eax, 1FFF0000h
0x140004d73  cmp     eax, 70000h
0x140004d78  jnz     short loc_140004D7D
0x140004d7a  movzx   ebx, bx
0x140004d7d  mov     r8d, 690h
0x140004d83  lea     r9, aFailedToCopySt; "Failed to copy string (%d)"
0x140004d8a  mov     [rsp+118h+var_F8], ebx
0x140004d8e  lea     rdx, aMergesdbGetins_0; "MergeSdb_GetInstalledSdbByGuid"
0x140004d95  mov     ecx, 1
0x140004d9a  call    AslLogCallPrintf
0x140004d9f  lea     rcx, [rsp+118h+var_D8]; this
0x140004da4  call    ??1SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::~SdbFileData(void)
0x140004da9  test    ebx, ebx
0x140004dab  jz      short loc_140004DC3
0x140004dad  add     rdi, 18h
0x140004db1  lea     rax, qword_140030E88
0x140004db8  cmp     rdi, rax
0x140004dbb  jnz     loc_140004CAB
0x140004dc1  jmp     short loc_140004DC8
0x140004dc3  mov     esi, 1
0x140004dc8  mov     eax, esi
0x140004dca  mov     rcx, [rsp+118h+var_38]
0x140004dd2  xor     rcx, rsp; StackCookie
0x140004dd5  call    __security_check_cookie
0x140004dda  mov     rbx, [rsp+118h+arg_10]
0x140004de2  add     rsp, 0F0h
0x140004de9  pop     r15
0x140004deb  pop     r14
0x140004ded  pop     rdi
0x140004dee  pop     rsi
0x140004def  pop     rbp
0x140004df0  retn
```
