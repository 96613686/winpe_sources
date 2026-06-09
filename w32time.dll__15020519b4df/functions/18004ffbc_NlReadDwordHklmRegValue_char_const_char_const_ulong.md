# NlReadDwordHklmRegValue(char const *,char const *,ulong *)

- ea: `0x18004ffbc`
- end: `0x180050097`
- name: `?NlReadDwordHklmRegValue@@YAEPEBD0PEAK@Z`
- size: `219`
- prototype: `unsigned __int8 __fastcall(const char *, const char *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180031358`

## callees

- `0x18004ffbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050067`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050067`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180050055`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180050055`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180050010`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180050010`

## pseudocode

```c
unsigned __int8 __fastcall NlReadDwordHklmRegValue(const char *a1, const char *a2, unsigned int *a3)
{
  LSTATUS ValueA; // ebx
  unsigned __int8 result; // al
  HKEY hkey; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwType; // [rsp+70h] [rbp+20h] BYREF
  int v8; // [rsp+74h] [rbp+24h]
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF
  int v10; // [rsp+7Ch] [rbp+2Ch]
  unsigned int pvData; // [rsp+88h] [rbp+38h] BYREF

  v10 = HIDWORD(a2);
  v8 = HIDWORD(a1);
  hkey = 0;
  pdwType = 0;
  pvData = 0;
  pcbData = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\Setup", 0, 1u, &hkey) )
    return 0;
  pcbData = 4;
  ValueA = RegGetValueA(hkey, 0, "SystemSetupInProgress", 0xFFFFu, &pdwType, &pvData, &pcbData);
  RegCloseKey(hkey);
  if ( ValueA || pdwType != 4 || pcbData != 4 )
    return 0;
  result = 1;
  *a3 = pvData;
  return result;
}

```

## disassembly

```asm
0x18004ffbc  mov     qword ptr [rsp-18h+arg_8], rdx
0x18004ffc1  mov     qword ptr [rsp-18h+pdwType], rcx
0x18004ffc6  push    rbp
0x18004ffc7  push    rbx
0x18004ffc8  push    rdi
0x18004ffc9  mov     rbp, rsp
0x18004ffcc  sub     rsp, 50h
0x18004ffd0  mov     rdi, r8
0x18004ffd3  mov     [rbp+hkey], 0
0x18004ffdb  lea     rax, [rbp+hkey]
0x18004ffdf  mov     [rbp+pdwType], 0
0x18004ffe6  xor     r8d, r8d; ulOptions
0x18004ffe9  mov     [rsp+50h+phkResult], rax; phkResult
0x18004ffee  mov     r9d, 1; samDesired
0x18004fff4  mov     [rbp+arg_18], 0
0x18004fffb  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x180050002  mov     [rbp+arg_8], 0
0x180050009  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050010  call    cs:__imp_RegOpenKeyExA
0x180050017  nop     dword ptr [rax+rax+00h]
0x18005001c  test    eax, eax
0x18005001e  jnz     short loc_18005008C
0x180050020  mov     rcx, [rbp+hkey]; hkey
0x180050024  lea     rax, [rbp+arg_8]
0x180050028  mov     [rsp+50h+pcbData], rax; pcbData
0x18005002d  lea     r8, aSystemsetupinp; "SystemSetupInProgress"
0x180050034  lea     rax, [rbp+arg_18]
0x180050038  mov     [rbp+arg_8], 4
0x18005003f  mov     [rsp+50h+pvData], rax; pvData
0x180050044  mov     r9d, 0FFFFh; dwFlags
0x18005004a  lea     rax, [rbp+pdwType]
0x18005004e  xor     edx, edx; lpSubKey
0x180050050  mov     [rsp+50h+phkResult], rax; pdwType
0x180050055  call    cs:__imp_RegGetValueA
0x18005005c  nop     dword ptr [rax+rax+00h]
0x180050061  mov     rcx, [rbp+hkey]; hKey
0x180050065  mov     ebx, eax
0x180050067  call    cs:__imp_RegCloseKey
0x18005006e  nop     dword ptr [rax+rax+00h]
0x180050073  test    ebx, ebx
0x180050075  jnz     short loc_18005008C
0x180050077  cmp     [rbp+pdwType], 4
0x18005007b  jnz     short loc_18005008C
0x18005007d  cmp     [rbp+arg_8], 4
0x180050081  jnz     short loc_18005008C
0x180050083  mov     ecx, [rbp+arg_18]
0x180050086  mov     al, 1
0x180050088  mov     [rdi], ecx
0x18005008a  jmp     short loc_18005008E
0x18005008c  xor     al, al
0x18005008e  add     rsp, 50h
0x180050092  pop     rdi
0x180050093  pop     rbx
0x180050094  pop     rbp
0x180050095  retn
```
