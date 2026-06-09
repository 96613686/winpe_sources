# pSpUtilsOpenSetupKey

- ea: `0x1800103f8`
- end: `0x1800104d1`
- name: `pSpUtilsOpenSetupKey`
- size: `217`
- prototype: `__int64 __fastcall(HANDLE *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800164e0`

## callees

- `0x18000c650`
- `0x18000f210`
- `0x1800103f8`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall pSpUtilsOpenSetupKey(HANDLE *a1, _QWORD *a2)
{
  unsigned int v4; // edi
  int v6; // [rsp+30h] [rbp-238h] BYREF
  __int64 v7; // [rsp+34h] [rbp-234h] BYREF
  WCHAR v8[264]; // [rsp+40h] [rbp-228h] BYREF

  v6 = 0;
  LODWORD(v7) = 520;
  v4 = pSetupOpenKeyEx((void *)0xFFFFFFFF80000002LL, L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup", 1u, a1);
  if ( !v4
    && a2
    && ((unsigned int)pSetupQueryValue(*a1, L"SetupOverride", &v6, v8, (unsigned int *)&v7)
     || v6 != 1
     || (unsigned int)pSetupOpenKeyEx((void *)0xFFFFFFFF80000002LL, v8, 1u, a2)) )
  {
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800103f8  mov     [rsp+arg_10], rbx
0x1800103fd  mov     [rsp+arg_18], rsi
0x180010402  push    rdi
0x180010403  sub     rsp, 260h
0x18001040a  mov     rax, cs:__security_cookie
0x180010411  xor     rax, rsp
0x180010414  mov     [rsp+268h+var_18], rax
0x18001041c  mov     rbx, rdx
0x18001041f  mov     [rsp+268h+var_238], 0
0x180010427  mov     rsi, rcx
0x18001042a  mov     dword ptr [rsp+268h+var_234], 208h
0x180010432  mov     r9, rcx
0x180010435  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001043c  mov     rcx, 0FFFFFFFF80000002h
0x180010443  mov     r8d, 1
0x180010449  call    pSetupOpenKeyEx
0x18001044e  mov     edi, eax
0x180010450  test    eax, eax
0x180010452  jnz     short loc_1800104AA
0x180010454  test    rbx, rbx
0x180010457  jz      short loc_1800104AA
0x180010459  mov     rcx, [rsi]; KeyHandle
0x18001045c  lea     rax, [rsp+268h+var_234]
0x180010461  lea     r9, [rsp+268h+var_228]
0x180010466  mov     [rsp+268h+var_248], rax; __int64
0x18001046b  lea     r8, [rsp+268h+var_238]
0x180010470  lea     rdx, aSetupoverride; "SetupOverride"
0x180010477  call    pSetupQueryValue
0x18001047c  test    eax, eax
0x18001047e  jnz     short loc_1800104A3
0x180010480  cmp     [rsp+268h+var_238], 1
0x180010485  jnz     short loc_1800104A3
0x180010487  mov     r9, rbx
0x18001048a  lea     r8d, [rdi+1]
0x18001048e  lea     rdx, [rsp+268h+var_228]
0x180010493  mov     rcx, 0FFFFFFFF80000002h
0x18001049a  call    pSetupOpenKeyEx
0x18001049f  test    eax, eax
0x1800104a1  jz      short loc_1800104AA
0x1800104a3  mov     qword ptr [rbx], 0
0x1800104aa  mov     eax, edi
0x1800104ac  mov     rcx, [rsp+268h+var_18]
0x1800104b4  xor     rcx, rsp; StackCookie
0x1800104b7  call    __security_check_cookie
0x1800104bc  lea     r11, [rsp+268h+var_8]
0x1800104c4  mov     rbx, [r11+20h]
0x1800104c8  mov     rsi, [r11+28h]
0x1800104cc  mov     rsp, r11
0x1800104cf  pop     rdi
0x1800104d0  retn
```
