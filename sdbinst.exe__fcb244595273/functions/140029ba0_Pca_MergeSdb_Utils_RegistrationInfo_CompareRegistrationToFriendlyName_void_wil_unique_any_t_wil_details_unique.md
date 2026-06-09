# Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToFriendlyName(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &)

- ea: `0x140029ba0`
- end: `0x140029c78`
- name: `?CompareRegistrationToFriendlyName@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, HKEY *, _BYTE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001008c`
- `0x140029ba0`
- `0x14002d278`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140029c0a`
- `KERNEL32!GetProcessHeap` at `0x140029c4f`
- `KERNEL32!GetProcessHeap` at `0x140029c0a`
- `KERNEL32!GetProcessHeap` at `0x140029c4f`
- `KERNEL32!HeapFree` at `0x140029c1a`
- `KERNEL32!HeapFree` at `0x140029c5f`
- `KERNEL32!HeapFree` at `0x140029c1a`
- `KERNEL32!HeapFree` at `0x140029c5f`

## string_xrefs

- `0x140029be3`: `Failed to read friendly name from a registration key (%d)`
- `0x140029bf0`: `Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToFriendlyName`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToFriendlyName(
        __int64 a1,
        HKEY *a2,
        _BYTE *a3)
{
  int RegValue; // eax
  unsigned int v6; // esi
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // eax

  *a3 = 0;
  RegValue = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(*a2, L"FriendlyName");
  v6 = RegValue;
  if ( RegValue )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToFriendlyName",
      956,
      "Failed to read friendly name from a registration key (%d)",
      RegValue);
    return v6;
  }
  else
  {
    v8 = -a1;
    do
    {
      v9 = *(unsigned __int16 *)(a1 + v8);
      v10 = *(unsigned __int16 *)a1 - v9;
      if ( v10 )
        break;
      a1 += 2;
    }
    while ( v9 );
    if ( !v10 )
      *a3 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x140029ba0  mov     r11, rsp
0x140029ba3  mov     [r11+8], rsi
0x140029ba7  mov     [r11+18h], rdi
0x140029bab  push    r14
0x140029bad  sub     rsp, 30h
0x140029bb1  mov     r14, r8
0x140029bb4  mov     rax, rdx
0x140029bb7  mov     rdi, rcx
0x140029bba  mov     byte ptr [r8], 0
0x140029bbe  mov     qword ptr [r11+10h], 0
0x140029bc6  lea     r8, [r11+10h]
0x140029bca  lea     rdx, ?REG_VALUE_NAME_FRIENDLY_NAME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FriendlyName"
0x140029bd1  mov     rcx, [rax]; hkey
0x140029bd4  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140029bd9  mov     esi, eax
0x140029bdb  test    eax, eax
0x140029bdd  jz      short loc_140029C24
0x140029bdf  mov     [rsp+38h+var_18], eax
0x140029be3  lea     r9, aFailedToReadFr; "Failed to read friendly name from a reg"...
0x140029bea  mov     r8d, 3BCh
0x140029bf0  lea     rdx, aPcaMergesdbUti_4; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x140029bf7  mov     ecx, 1
0x140029bfc  call    AslLogCallPrintf
0x140029c01  nop
0x140029c02  cmp     [rsp+38h+lpMem], 0
0x140029c08  jz      short loc_140029C20
0x140029c0a  call    cs:__imp_GetProcessHeap
0x140029c10  mov     rcx, rax; hHeap
0x140029c13  mov     r8, [rsp+38h+lpMem]; lpMem
0x140029c18  xor     edx, edx; dwFlags
0x140029c1a  call    cs:__imp_HeapFree
0x140029c20  mov     eax, esi
0x140029c22  jmp     short loc_140029C67
0x140029c24  mov     rdx, [rsp+38h+lpMem]
0x140029c29  sub     rdx, rdi
0x140029c2c  movzx   eax, word ptr [rdi]
0x140029c2f  movzx   ecx, word ptr [rdi+rdx]
0x140029c33  sub     eax, ecx
0x140029c35  jnz     short loc_140029C3F
0x140029c37  add     rdi, 2
0x140029c3b  test    ecx, ecx
0x140029c3d  jnz     short loc_140029C2C
0x140029c3f  test    eax, eax
0x140029c41  jnz     short loc_140029C47
0x140029c43  mov     byte ptr [r14], 1
0x140029c47  cmp     [rsp+38h+lpMem], 0
0x140029c4d  jz      short loc_140029C65
0x140029c4f  call    cs:__imp_GetProcessHeap
0x140029c55  mov     rcx, rax; hHeap
0x140029c58  mov     r8, [rsp+38h+lpMem]; lpMem
0x140029c5d  xor     edx, edx; dwFlags
0x140029c5f  call    cs:__imp_HeapFree
0x140029c65  xor     eax, eax
0x140029c67  mov     rsi, [rsp+38h+arg_0]
0x140029c6c  mov     rdi, [rsp+38h+arg_10]
0x140029c71  add     rsp, 30h
0x140029c75  pop     r14
0x140029c77  retn
```
