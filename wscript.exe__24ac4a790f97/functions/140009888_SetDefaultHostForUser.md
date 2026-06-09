# SetDefaultHostForUser

- ea: `0x140009888`
- end: `0x140009976`
- name: `SetDefaultHostForUser`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140008b70`

## callees

- `0x140006744`
- `0x1400097e4`
- `0x140009888`
- `0x1400175a0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x140009900`
- `ADVAPI32!RegOpenKeyExA` at `0x140009900`
- `ADVAPI32!RegCreateKeyA` at `0x140009917`
- `ADVAPI32!RegCreateKeyA` at `0x140009917`
- `ADVAPI32!RegCloseKey` at `0x14000994d`
- `ADVAPI32!RegCloseKey` at `0x14000994d`

## pseudocode

```c
__int64 __fastcall SetDefaultHostForUser(const char *a1, const BYTE *a2)
{
  int v3; // ebx
  __int64 v4; // r8
  LSTATUS KeyA; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-138h] BYREF
  CHAR SubKey[272]; // [rsp+40h] [rbp-128h] BYREF

  hKey[0] = 0;
  v3 = StringCchPrintfA(SubKey, 0x104u, "SOFTWARE\\Classes\\%s\\%s", a1, "Shell");
  if ( v3 >= 0 )
  {
    if ( !RegOpenKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, hKey) )
      goto LABEL_7;
    KeyA = RegCreateKeyA(HKEY_CURRENT_USER, SubKey, hKey);
    v3 = KeyA;
    if ( !KeyA )
      goto LABEL_7;
    if ( KeyA > 0 )
      v3 = (unsigned __int16)KeyA | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_7:
      v3 = RegSetKeyString(hKey[0], ValueName, v4, a2);
      RegCloseKey(hKey[0]);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140009888  mov     [rsp+arg_10], rbx
0x14000988d  push    rdi
0x14000988e  sub     rsp, 160h
0x140009895  mov     rax, cs:__security_cookie
0x14000989c  xor     rax, rsp
0x14000989f  mov     [rsp+168h+var_18], rax
0x1400098a7  mov     rdi, rdx
0x1400098aa  mov     [rsp+168h+hKey], 0
0x1400098b3  lea     rax, aShell; "Shell"
0x1400098ba  mov     r9, rcx
0x1400098bd  mov     edx, 104h; unsigned __int64
0x1400098c2  mov     [rsp+168h+phkResult], rax
0x1400098c7  lea     rcx, [rsp+168h+SubKey]; char *
0x1400098cc  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\%s\\%s"
0x1400098d3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400098d8  mov     ebx, eax
0x1400098da  test    eax, eax
0x1400098dc  js      short loc_140009953
0x1400098de  lea     rax, [rsp+168h+hKey]
0x1400098e3  mov     rbx, 0FFFFFFFF80000001h
0x1400098ea  mov     rcx, rbx; hKey
0x1400098ed  mov     [rsp+168h+phkResult], rax; phkResult
0x1400098f2  mov     r9d, 20006h; samDesired
0x1400098f8  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x1400098fd  xor     r8d, r8d; ulOptions
0x140009900  call    cs:__imp_RegOpenKeyExA
0x140009906  test    eax, eax
0x140009908  jz      short loc_140009932
0x14000990a  lea     r8, [rsp+168h+hKey]; phkResult
0x14000990f  mov     rcx, rbx; hKey
0x140009912  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x140009917  call    cs:__imp_RegCreateKeyA
0x14000991d  mov     ebx, eax
0x14000991f  test    eax, eax
0x140009921  jz      short loc_140009932
0x140009923  jle     short loc_14000992E
0x140009925  movzx   ebx, ax
0x140009928  or      ebx, 80070000h
0x14000992e  test    ebx, ebx
0x140009930  js      short loc_140009953
0x140009932  mov     rcx, [rsp+168h+hKey]
0x140009937  lea     rdx, ValueName
0x14000993e  mov     r9, rdi
0x140009941  call    RegSetKeyString
0x140009946  mov     rcx, [rsp+168h+hKey]; hKey
0x14000994b  mov     ebx, eax
0x14000994d  call    cs:__imp_RegCloseKey
0x140009953  mov     eax, ebx
0x140009955  mov     rcx, [rsp+168h+var_18]
0x14000995d  xor     rcx, rsp; StackCookie
0x140009960  call    __security_check_cookie
0x140009965  mov     rbx, [rsp+168h+arg_10]
0x14000996d  add     rsp, 160h
0x140009974  pop     rdi
0x140009975  retn
```
