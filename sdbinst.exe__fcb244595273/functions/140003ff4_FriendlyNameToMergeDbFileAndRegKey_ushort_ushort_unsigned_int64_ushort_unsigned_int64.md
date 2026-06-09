# FriendlyNameToMergeDbFileAndRegKey(ushort *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x140003ff4`
- end: `0x14000415c`
- name: `?FriendlyNameToMergeDbFileAndRegKey@@YAHPEAG0_K01@Z`
- size: `360`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140008500`

## callees

- `0x140003ff4`
- `0x140007024`
- `0x14001008c`
- `0x140021ee4`
- `0x140022210`
- `0x14002aa4c`
- `0x14002e3e2`
- `0x14002e420`

## string_xrefs

- `0x1400040ee`: `Failed to copy string (%d)`
- `0x1400040f9`: `MergeSdb_GetInstalledSdbByFriendlyName`

## pseudocode

```c
__int64 __fastcall FriendlyNameToMergeDbFileAndRegKey(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  __int64 *v5; // rsi
  unsigned int v8; // edi
  __int64 v9; // rbx
  int MergeRegistrationInTarget; // eax
  int v11; // ebx
  int v12; // eax
  unsigned int v13; // r11d
  int v14; // eax
  __int64 v15; // r8
  __int64 v17; // [rsp+20h] [rbp-E8h]
  unsigned __int16 *v18[18]; // [rsp+30h] [rbp-D8h] BYREF
  int v19; // [rsp+C0h] [rbp-48h]
  __int64 v20; // [rsp+C8h] [rbp-40h]

  v5 = (__int64 *)&off_140030E40;
  v8 = 0;
  while ( 1 )
  {
    v9 = *v5;
    memset_0(v18, 0, sizeof(v18));
    Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v18);
    v19 = 0;
    v20 = 0;
    MergeRegistrationInTarget = Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(
                                  (Pca::MergeSdb::Utils::RegistrationInfo *)v18,
                                  v9,
                                  Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToFriendlyName,
                                  (__int64)a1);
    v11 = MergeRegistrationInTarget;
    if ( MergeRegistrationInTarget )
    {
      LODWORD(v17) = MergeRegistrationInTarget;
      AslLogCallPrintf(
        1,
        "MergeSdb_GetInstalledSdbByFriendlyName",
        1713,
        "Failed to find merge registration for target name and friendly name (%d)",
        v17);
      goto LABEL_14;
    }
    v12 = StringCchCopyW(a4, 0x104u, v18[14]);
    v11 = v12;
    if ( v12 < 0 )
    {
      if ( (v12 & 0x1FFF0000) == 0x70000 )
        v11 = (unsigned __int16)v12;
      v15 = 1718;
    }
    else
    {
      v14 = StringCchCopyW(a2, v13, v18[0]);
      v11 = v14;
      if ( v14 >= 0 )
      {
        v11 = 0;
        goto LABEL_14;
      }
      if ( (v14 & 0x1FFF0000) == 0x70000 )
        v11 = (unsigned __int16)v14;
      v15 = 1723;
    }
    LODWORD(v17) = v11;
    AslLogCallPrintf(1, "MergeSdb_GetInstalledSdbByFriendlyName", v15, "Failed to copy string (%d)", v17);
LABEL_14:
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v18);
    if ( v11 )
      return 1;
    v5 += 3;
    if ( v5 == qword_140030E88 )
      return v8;
  }
}

```

## disassembly

```asm
0x140003ff4  mov     [rsp+arg_10], rbx
0x140003ff9  push    rbp
0x140003ffa  push    rsi
0x140003ffb  push    rdi
0x140003ffc  push    r14
0x140003ffe  push    r15
0x140004000  sub     rsp, 0E0h
0x140004007  mov     rax, cs:__security_cookie
0x14000400e  xor     rax, rsp
0x140004011  mov     [rsp+108h+var_38], rax
0x140004019  mov     r14, r9
0x14000401c  lea     rsi, off_140030E40; "sysmain.sdb"
0x140004023  mov     rbp, rdx
0x140004026  mov     r15, rcx
0x140004029  xor     edi, edi
0x14000402b  mov     rbx, [rsi]
0x14000402e  lea     rcx, [rsp+108h+var_D8]; void *
0x140004033  xor     edx, edx; Val
0x140004035  mov     r8d, 90h; Size
0x14000403b  call    memset_0
0x140004040  lea     rcx, [rsp+108h+var_D8]; this
0x140004045  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x14000404a  mov     r9, r15
0x14000404d  mov     [rsp+108h+var_48], edi
0x140004054  lea     r8, ?CompareRegistrationToFriendlyName@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z; Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToFriendlyName(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &)
0x14000405b  mov     [rsp+108h+var_40], rdi
0x140004063  mov     rdx, rbx
0x140004066  lea     rcx, [rsp+108h+var_D8]; this
0x14000406b  call    ?FindMergeRegistrationInTarget@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV1234@PEBGP6AKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z2@Z; Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(Pca::MergeSdb::Utils::RegistrationInfo &,ushort const *,ulong (*)(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &),void *)
0x140004070  mov     ebx, eax
0x140004072  test    eax, eax
0x140004074  jz      short loc_140004089
0x140004076  mov     [rsp+108h+var_E8], eax
0x14000407a  lea     r9, aFailedToFindMe_0; "Failed to find merge registration for t"...
0x140004081  mov     r8d, 6B1h
0x140004087  jmp     short loc_1400040F9
0x140004089  mov     r8, [rsp+108h+var_68]; unsigned __int16 *
0x140004091  mov     r11d, 104h
0x140004097  mov     edx, r11d; unsigned __int64
0x14000409a  mov     rcx, r14; unsigned __int16 *
0x14000409d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400040a2  mov     ebx, eax
0x1400040a4  test    eax, eax
0x1400040a6  js      short loc_1400040D9
0x1400040a8  mov     r8, [rsp+108h+var_D8]; unsigned __int16 *
0x1400040ad  mov     edx, r11d; unsigned __int64
0x1400040b0  mov     rcx, rbp; unsigned __int16 *
0x1400040b3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400040b8  mov     ebx, eax
0x1400040ba  test    eax, eax
0x1400040bc  js      short loc_1400040C2
0x1400040be  xor     ebx, ebx
0x1400040c0  jmp     short loc_14000410A
0x1400040c2  and     eax, 1FFF0000h
0x1400040c7  cmp     eax, 70000h
0x1400040cc  jnz     short loc_1400040D1
0x1400040ce  movzx   ebx, bx
0x1400040d1  mov     r8d, 6BBh
0x1400040d7  jmp     short loc_1400040EE
0x1400040d9  and     eax, 1FFF0000h
0x1400040de  cmp     eax, 70000h
0x1400040e3  jnz     short loc_1400040E8
0x1400040e5  movzx   ebx, bx
0x1400040e8  mov     r8d, 6B6h
0x1400040ee  lea     r9, aFailedToCopySt; "Failed to copy string (%d)"
0x1400040f5  mov     [rsp+108h+var_E8], ebx
0x1400040f9  lea     rdx, aMergesdbGetins; "MergeSdb_GetInstalledSdbByFriendlyName"
0x140004100  mov     ecx, 1
0x140004105  call    AslLogCallPrintf
0x14000410a  lea     rcx, [rsp+108h+var_D8]; this
0x14000410f  call    ??1SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::~SdbFileData(void)
0x140004114  test    ebx, ebx
0x140004116  jnz     short loc_14000412E
0x140004118  add     rsi, 18h
0x14000411c  lea     rax, qword_140030E88
0x140004123  cmp     rsi, rax
0x140004126  jnz     loc_14000402B
0x14000412c  jmp     short loc_140004133
0x14000412e  mov     edi, 1
0x140004133  mov     eax, edi
0x140004135  mov     rcx, [rsp+108h+var_38]
0x14000413d  xor     rcx, rsp; StackCookie
0x140004140  call    __security_check_cookie
0x140004145  mov     rbx, [rsp+108h+arg_10]
0x14000414d  add     rsp, 0E0h
0x140004154  pop     r15
0x140004156  pop     r14
0x140004158  pop     rdi
0x140004159  pop     rsi
0x14000415a  pop     rbp
0x14000415b  retn
```
