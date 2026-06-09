# IsCamCxhOnlyUser(ushort const *)

- ea: `0x140015b94`
- end: `0x140015c37`
- name: `?IsCamCxhOnlyUser@@YA_NPEBG@Z`
- size: `163`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015e24`

## callees

- `0x140015b94`
- `0x140016dc8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140015bd8`
- `ADVAPI32!RegOpenKeyExW` at `0x140015bd8`
- `ADVAPI32!RegCloseKey` at `0x140015c17`
- `ADVAPI32!RegCloseKey` at `0x140015c17`

## pseudocode

```c
char __fastcall IsCamCxhOnlyUser(const unsigned __int16 *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // r9d
  bool v4; // sf
  int v6; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  if ( !a1 )
    return 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\CandidateAccountManager",
         0,
         0x20019u,
         &hKey);
  v4 = v2 < 0;
  if ( v2 > 0 )
    v4 = 1;
  if ( !v4 && (SHRegGetBOOLWithREGSAM(hKey, a1, L"CxhOnlyUse", v3, &v6), RegCloseKey(hKey), v6) )
    return 1;
  else
    return 0;
}

```

## disassembly

```asm
0x140015b94  push    rbx
0x140015b96  sub     rsp, 30h
0x140015b9a  mov     [rsp+38h+arg_0], 0
0x140015ba2  mov     rbx, rcx
0x140015ba5  test    rcx, rcx
0x140015ba8  jz      loc_140015C2E
0x140015bae  lea     rax, [rsp+38h+hKey]
0x140015bb3  mov     [rsp+38h+hKey], 0
0x140015bbc  mov     r9d, 20019h; samDesired
0x140015bc2  mov     [rsp+38h+phkResult], rax; phkResult
0x140015bc7  xor     r8d, r8d; ulOptions
0x140015bca  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140015bd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015bd8  call    cs:__imp_RegOpenKeyExW
0x140015bdf  nop     dword ptr [rax+rax+00h]
0x140015be4  test    eax, eax
0x140015be6  jle     short loc_140015BF2
0x140015be8  movzx   eax, ax
0x140015beb  or      eax, 80070000h
0x140015bf0  test    eax, eax
0x140015bf2  js      short loc_140015C2E
0x140015bf4  mov     rcx, [rsp+38h+hKey]; HKEY
0x140015bf9  lea     rax, [rsp+38h+arg_0]
0x140015bfe  lea     r8, aCxhonlyuse; "CxhOnlyUse"
0x140015c05  mov     [rsp+38h+phkResult], rax; int *
0x140015c0a  mov     rdx, rbx; unsigned __int16 *
0x140015c0d  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x140015c12  mov     rcx, [rsp+38h+hKey]; hKey
0x140015c17  call    cs:__imp_RegCloseKey
0x140015c1e  nop     dword ptr [rax+rax+00h]
0x140015c23  cmp     [rsp+38h+arg_0], 0
0x140015c28  jz      short loc_140015C2E
0x140015c2a  mov     al, 1
0x140015c2c  jmp     short loc_140015C30
0x140015c2e  xor     al, al
0x140015c30  add     rsp, 30h
0x140015c34  pop     rbx
0x140015c35  retn
```
