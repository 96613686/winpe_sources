# CipRequirePlatformManifestForSigner

- ea: `0x18004756c`
- end: `0x1800475f1`
- name: `CipRequirePlatformManifestForSigner`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180049d40`

## callees

- `0x18004756c`

## import_xrefs

- `securekernel!SeQuerySecureBootPlatformManifest` at `0x180047581`
- `securekernel!SeQuerySecureBootPlatformManifest` at `0x180047581`

## pseudocode

```c
char __fastcall CipRequirePlatformManifestForSigner(int a1)
{
  int SecureBootPlatformManifest; // eax
  int v3; // edx
  __int64 i; // r8

  if ( g_CipCheckedPlatformManifestActive != 1 )
  {
    SecureBootPlatformManifest = SeQuerySecureBootPlatformManifest(0, 0);
    g_CipCheckedPlatformManifestActive = 1;
    g_CipIsPlatformManifestActive = SecureBootPlatformManifest != -1058340858;
  }
  if ( !g_CipIsPlatformManifestActive )
    return 0;
  v3 = 0;
LABEL_5:
  if ( v3 > g_CiSignerTypeMax )
    return 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= g_CiScenarios[v3 + 224] )
    {
      ++v3;
      goto LABEL_5;
    }
    if ( a1 == *(_DWORD *)(*(_QWORD *)&g_CiScenarios[2 * v3 + 218] + 4 * i) )
      break;
  }
  return 1;
}

```

## disassembly

```asm
0x18004756c  push    rbx
0x18004756e  sub     rsp, 20h
0x180047572  cmp     cs:g_CipCheckedPlatformManifestActive, 1
0x180047579  mov     ebx, ecx
0x18004757b  jz      short loc_1800475A0
0x18004757d  xor     edx, edx
0x18004757f  xor     ecx, ecx
0x180047581  call    cs:__imp_SeQuerySecureBootPlatformManifest
0x180047588  nop     dword ptr [rax+rax+00h]
0x18004758d  cmp     eax, 0C0EB0006h
0x180047592  mov     cs:g_CipCheckedPlatformManifestActive, 1
0x180047599  setnz   cs:g_CipIsPlatformManifestActive
0x1800475a0  cmp     cs:g_CipIsPlatformManifestActive, 0
0x1800475a7  jz      short loc_1800475E8
0x1800475a9  xor     edx, edx
0x1800475ab  lea     r11, g_CiScenarios
0x1800475b2  cmp     edx, cs:g_CiSignerTypeMax
0x1800475b8  jg      short loc_1800475E8
0x1800475ba  movsxd  r9, edx
0x1800475bd  xor     r8d, r8d
0x1800475c0  mov     r10d, [r11+r9*4+380h]
0x1800475c8  cmp     r8d, r10d
0x1800475cb  jnb     short loc_1800475E0
0x1800475cd  mov     rax, [r11+r9*8+368h]
0x1800475d5  cmp     ebx, [rax+r8*4]
0x1800475d9  jz      short loc_1800475E4
0x1800475db  inc     r8d
0x1800475de  jmp     short loc_1800475C8
0x1800475e0  inc     edx
0x1800475e2  jmp     short loc_1800475B2
0x1800475e4  mov     al, 1
0x1800475e6  jmp     short loc_1800475EA
0x1800475e8  xor     al, al
0x1800475ea  add     rsp, 20h
0x1800475ee  pop     rbx
0x1800475ef  retn
```
