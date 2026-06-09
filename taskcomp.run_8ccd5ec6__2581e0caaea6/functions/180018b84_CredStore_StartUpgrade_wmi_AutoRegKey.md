# CredStore::StartUpgrade(wmi::AutoRegKey &)

- ea: `0x180018b84`
- end: `0x180018c60`
- name: `?StartUpgrade@CredStore@@AEAA?AW4UpgradeStages@1@AEAVAutoRegKey@wmi@@@Z`
- size: `220`
- prototype: `enum CredStore::UpgradeStages __high(struct wmi::AutoRegKey *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019064`

## callees

- `0x1800187f0`
- `0x180018b84`
- `0x1800306ce`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018bef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018bef`

## string_xrefs

- `0x180018bff`: `Completed`

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
0x180018b84  mov     r11, rsp
0x180018b87  mov     [r11+8], rbx
0x180018b8b  push    rdi
0x180018b8c  sub     rsp, 70h
0x180018b90  mov     rax, cs:__security_cookie
0x180018b97  xor     rax, rsp
0x180018b9a  mov     [rsp+78h+var_18], rax
0x180018b9f  xor     eax, eax
0x180018ba1  mov     [rsp+78h+var_38], 16h
0x180018ba9  mov     [rsp+78h+String1], ax
0x180018bae  mov     rdi, rdx
0x180018bb1  mov     [rsp+78h+var_1E], eax
0x180018bb5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180018bbc  lea     rax, [r11-38h]
0x180018bc0  xorps   xmm0, xmm0
0x180018bc3  mov     [r11-48h], rax
0x180018bc7  mov     ebx, 1
0x180018bcc  lea     rax, [r11-30h]
0x180018bd0  xor     r8d, r8d; lpValue
0x180018bd3  mov     [r11-50h], rax
0x180018bd7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180018bde  mov     qword ptr [r11-58h], 0
0x180018be6  lea     r9d, [rbx+1]; dwFlags
0x180018bea  movups  [rsp+78h+var_2E], xmm0
0x180018bef  call    cs:__imp_RegGetValueW
0x180018bf6  nop     dword ptr [rax+rax+00h]
0x180018bfb  test    eax, eax
0x180018bfd  jnz     short loc_180018C33
0x180018bff  lea     rdx, aCompleted; "Completed"
0x180018c06  lea     rcx, [rsp+78h+String1]; String1
0x180018c0b  call    wcscmp_0
0x180018c10  test    eax, eax
0x180018c12  jnz     short loc_180018C19
0x180018c14  lea     ebx, [rax+3]
0x180018c17  jmp     short loc_180018C42
0x180018c19  lea     rdx, aStageOne; "Stage_One"
0x180018c20  lea     rcx, [rsp+78h+String1]; String1
0x180018c25  call    wcscmp_0
0x180018c2a  xor     ecx, ecx
0x180018c2c  test    eax, eax
0x180018c2e  setz    cl; this
0x180018c31  add     ebx, ecx
0x180018c33  mov     rdx, rdi; struct wmi::AutoRegKey *
0x180018c36  call    ?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z; CredStore::OpenCredManagerKey(wmi::AutoRegKey &)
0x180018c3b  xor     ecx, ecx
0x180018c3d  test    eax, eax
0x180018c3f  cmovs   ebx, ecx
0x180018c42  mov     eax, ebx
0x180018c44  mov     rcx, [rsp+78h+var_18]
0x180018c49  xor     rcx, rsp; StackCookie
0x180018c4c  call    __security_check_cookie
0x180018c51  mov     rbx, [rsp+78h+arg_0]
0x180018c59  add     rsp, 70h
0x180018c5d  pop     rdi
0x180018c5e  retn
```
