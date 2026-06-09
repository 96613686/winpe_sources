# Pca::MergeSdb::Utils::RegistrationInfo::GatherInformationForFile(ushort const *,ushort const *,Pca::MergeSdb::MergeInputTypeConfig)

- ea: `0x14002ab60`
- end: `0x14002ac44`
- name: `?GatherInformationForFile@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKPEBG0UMergeInputTypeConfig@34@@Z`
- size: `228`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *, const WCHAR *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140027c80`

## callees

- `0x14001008c`
- `0x140021ee4`
- `0x140022210`
- `0x14002ab60`
- `0x14002c36c`
- `0x14002df00`
- `0x14002e134`
- `0x14002e420`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::GatherInformationForFile(
        Pca::MergeSdb::Utils::RegistrationInfo *a1,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  _BYTE v11[144]; // [rsp+30h] [rbp-B8h] BYREF

  if ( *a4 >= 5 )
    return 87;
  Pca::MergeSdb::Utils::RegistrationInfo::Reset(a1);
  Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v11);
  v9 = Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile((Pca::MergeSdb::Utils::SdbFileData *)v11, a2, a3);
  v10 = v9;
  if ( v9 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::GatherInformationForFile",
      899,
      "Failed to load sdb data from file '%S' (%d)",
      a2,
      v9);
  }
  else
  {
    Pca::MergeSdb::Utils::SdbFileData::Swap(a1, (struct Pca::MergeSdb::Utils::SdbFileData *)v11);
    *((_QWORD *)a1 + 19) = &qword_1400311F0[3 * (int)*a4];
    v10 = 0;
  }
  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v11);
  return v10;
}

```

## disassembly

```asm
0x14002ab60  mov     [rsp+arg_18], rbx
0x14002ab65  push    rbp
0x14002ab66  push    rsi
0x14002ab67  push    rdi
0x14002ab68  sub     rsp, 0D0h
0x14002ab6f  mov     rax, cs:__security_cookie
0x14002ab76  xor     rax, rsp
0x14002ab79  mov     [rsp+0E8h+var_28], rax
0x14002ab81  mov     rbp, r9
0x14002ab84  mov     rbx, r8
0x14002ab87  mov     rsi, rdx
0x14002ab8a  mov     rdi, rcx
0x14002ab8d  cmp     dword ptr [r9], 5
0x14002ab91  jb      short loc_14002AB9D
0x14002ab93  mov     eax, 57h ; 'W'
0x14002ab98  jmp     loc_14002AC21
0x14002ab9d  call    ?Reset@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegistrationInfo::Reset(void)
0x14002aba2  lea     rcx, [rsp+0E8h+var_B8]; this
0x14002aba7  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x14002abac  nop
0x14002abad  mov     r8, rbx; unsigned __int16 *
0x14002abb0  mov     rdx, rsi; FileName
0x14002abb3  lea     rcx, [rsp+0E8h+var_B8]; this
0x14002abb8  call    ?LoadFromSdbFile@SdbFileData@Utils@MergeSdb@Pca@@QEAAKPEBG0@Z; Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile(ushort const *,ushort const *)
0x14002abbd  mov     ebx, eax
0x14002abbf  test    eax, eax
0x14002abc1  jz      short loc_14002ABEC
0x14002abc3  mov     [rsp+0E8h+var_C0], eax
0x14002abc7  mov     [rsp+0E8h+var_C8], rsi
0x14002abcc  lea     r9, aFailedToLoadSd_0; "Failed to load sdb data from file '%S' "...
0x14002abd3  mov     r8d, 383h
0x14002abd9  lea     rdx, aPcaMergesdbUti_3; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002abe0  mov     ecx, 1
0x14002abe5  call    AslLogCallPrintf
0x14002abea  jmp     short loc_14002AC15
0x14002abec  lea     rdx, [rsp+0E8h+var_B8]; struct Pca::MergeSdb::Utils::SdbFileData *
0x14002abf1  mov     rcx, rdi; this
0x14002abf4  call    ?Swap@SdbFileData@Utils@MergeSdb@Pca@@QEAAXAEAV1234@@Z; Pca::MergeSdb::Utils::SdbFileData::Swap(Pca::MergeSdb::Utils::SdbFileData &)
0x14002abf9  movsxd  rax, dword ptr [rbp+0]
0x14002abfd  lea     rcx, [rax+rax*2]
0x14002ac01  lea     rax, qword_1400311F0
0x14002ac08  lea     rax, [rax+rcx*8]
0x14002ac0c  mov     [rdi+98h], rax
0x14002ac13  xor     ebx, ebx
0x14002ac15  lea     rcx, [rsp+0E8h+var_B8]; this
0x14002ac1a  call    ??1SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::~SdbFileData(void)
0x14002ac1f  mov     eax, ebx
0x14002ac21  mov     rcx, [rsp+0E8h+var_28]
0x14002ac29  xor     rcx, rsp; StackCookie
0x14002ac2c  call    __security_check_cookie
0x14002ac31  mov     rbx, [rsp+0E8h+arg_18]
0x14002ac39  add     rsp, 0D0h
0x14002ac40  pop     rdi
0x14002ac41  pop     rsi
0x14002ac42  pop     rbp
0x14002ac43  retn
```
