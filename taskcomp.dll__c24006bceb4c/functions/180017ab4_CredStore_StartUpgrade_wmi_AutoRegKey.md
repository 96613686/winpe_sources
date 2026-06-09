# CredStore::StartUpgrade(wmi::AutoRegKey &)

- ea: `0x180017ab4`
- end: `0x180017b89`
- name: `?StartUpgrade@CredStore@@AEAA?AW4UpgradeStages@1@AEAVAutoRegKey@wmi@@@Z`
- size: `213`
- prototype: `enum CredStore::UpgradeStages __high(struct wmi::AutoRegKey *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017f74`

## callees

- `0x180017758`
- `0x180017ab4`
- `0x18002e57e`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017b1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017b1f`

## string_xrefs

- `0x180017b29`: `Completed`

## pseudocode

```c
__int64 __fastcall CredStore::StartUpgrade(__int64 a1, HKEY *a2)
{
  unsigned int v3; // ebx
  _BOOL8 v4; // rcx
  DWORD v6; // [rsp+40h] [rbp-38h] BYREF
  wchar_t String1; // [rsp+48h] [rbp-30h] BYREF
  __int128 v8; // [rsp+4Ah] [rbp-2Eh]
  int v9; // [rsp+5Ah] [rbp-1Eh]

  v6 = 22;
  String1 = 0;
  v9 = 0;
  v3 = 1;
  v8 = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CredWom",
          0,
          2u,
          0,
          &String1,
          &v6) )
  {
    if ( !wcscmp_0(&String1, L"Completed") )
      return 3;
    v4 = wcscmp_0(&String1, L"Stage_One") == 0;
    v3 = v4 + 1;
  }
  if ( CredStore::OpenCredManagerKey((CredStore *)v4, a2) < 0 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x180017ab4  mov     r11, rsp
0x180017ab7  mov     [r11+8], rbx
0x180017abb  push    rdi
0x180017abc  sub     rsp, 70h
0x180017ac0  mov     rax, cs:__security_cookie
0x180017ac7  xor     rax, rsp
0x180017aca  mov     [rsp+78h+var_18], rax
0x180017acf  xor     eax, eax
0x180017ad1  mov     [rsp+78h+var_38], 16h
0x180017ad9  mov     [rsp+78h+String1], ax
0x180017ade  mov     rdi, rdx
0x180017ae1  mov     [rsp+78h+var_1E], eax
0x180017ae5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180017aec  lea     rax, [r11-38h]
0x180017af0  xorps   xmm0, xmm0
0x180017af3  mov     [r11-48h], rax
0x180017af7  mov     ebx, 1
0x180017afc  lea     rax, [r11-30h]
0x180017b00  xor     r8d, r8d; lpValue
0x180017b03  mov     [r11-50h], rax
0x180017b07  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180017b0e  mov     qword ptr [r11-58h], 0
0x180017b16  lea     r9d, [rbx+1]; dwFlags
0x180017b1a  movups  [rsp+78h+var_2E], xmm0
0x180017b1f  call    cs:__imp_RegGetValueW
0x180017b25  test    eax, eax
0x180017b27  jnz     short loc_180017B5D
0x180017b29  lea     rdx, aCompleted; "Completed"
0x180017b30  lea     rcx, [rsp+78h+String1]; String1
0x180017b35  call    wcscmp_0
0x180017b3a  test    eax, eax
0x180017b3c  jnz     short loc_180017B43
0x180017b3e  lea     ebx, [rax+3]
0x180017b41  jmp     short loc_180017B6C
0x180017b43  lea     rdx, aStageOne; "Stage_One"
0x180017b4a  lea     rcx, [rsp+78h+String1]; String1
0x180017b4f  call    wcscmp_0
0x180017b54  xor     ecx, ecx
0x180017b56  test    eax, eax
0x180017b58  setz    cl; this
0x180017b5b  add     ebx, ecx
0x180017b5d  mov     rdx, rdi; struct wmi::AutoRegKey *
0x180017b60  call    ?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z; CredStore::OpenCredManagerKey(wmi::AutoRegKey &)
0x180017b65  xor     ecx, ecx
0x180017b67  test    eax, eax
0x180017b69  cmovs   ebx, ecx
0x180017b6c  mov     eax, ebx
0x180017b6e  mov     rcx, [rsp+78h+var_18]
0x180017b73  xor     rcx, rsp; StackCookie
0x180017b76  call    __security_check_cookie
0x180017b7b  mov     rbx, [rsp+78h+arg_0]
0x180017b83  add     rsp, 70h
0x180017b87  pop     rdi
0x180017b88  retn
```
