# CheckWSHFlag(ushort const *,HKEY__ *,HKEY__ *,bool)

- ea: `0x14000a358`
- end: `0x14000a3f1`
- name: `?CheckWSHFlag@@YA_NPEBGPEAUHKEY__@@1_N@Z`
- size: `153`
- prototype: `bool __fastcall(LPCWCH lpWideCharStr, HKEY hKey, HKEY, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005d74`
- `0x14000a238`
- `0x14000a568`

## callees

- `0x14000a358`
- `0x14001550c`

## pseudocode

```c
char __fastcall CheckWSHFlag(LPCWCH lpWideCharStr, HKEY hKey, HKEY a3, char a4)
{
  bool v5; // al
  char result; // al
  bool v10; // sf
  bool v11; // [rsp+20h] [rbp-28h] BYREF
  bool v12; // [rsp+58h] [rbp+10h] BYREF
  bool v13; // [rsp+60h] [rbp+18h] BYREF

  v13 = 1;
  v11 = 1;
  v5 = hKey == 0;
  v12 = hKey == 0;
  if ( a3 && hKey )
  {
    GetRegSettingsBool(a3, L"IgnoreUserSettings", &v12);
    v5 = v12;
  }
  if ( !v5 && GetRegSettingsBool(hKey, lpWideCharStr, &v13) >= 0 )
    return v13;
  if ( !a3 )
    return a4;
  v10 = GetRegSettingsBool(a3, lpWideCharStr, &v11) < 0;
  result = v11;
  if ( v10 )
    return a4;
  return result;
}

```

## disassembly

```asm
0x14000a358  mov     [rsp+arg_0], rbx
0x14000a35d  push    rbp
0x14000a35e  push    rsi
0x14000a35f  push    rdi
0x14000a360  sub     rsp, 30h
0x14000a364  test    rdx, rdx
0x14000a367  mov     [rsp+48h+arg_10], 1
0x14000a36c  mov     sil, r9b
0x14000a36f  mov     [rsp+48h+var_28], 1
0x14000a374  setz    al
0x14000a377  mov     rbx, r8
0x14000a37a  mov     [rsp+48h+arg_8], al
0x14000a37e  mov     rdi, rdx
0x14000a381  mov     rbp, rcx
0x14000a384  test    r8, r8
0x14000a387  jz      short loc_14000A3A6
0x14000a389  test    rdx, rdx
0x14000a38c  jz      short loc_14000A3A6
0x14000a38e  lea     r8, [rsp+48h+arg_8]; bool *
0x14000a393  mov     rcx, rbx; hKey
0x14000a396  lea     rdx, aIgnoreusersett; "IgnoreUserSettings"
0x14000a39d  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x14000a3a2  mov     al, [rsp+48h+arg_8]
0x14000a3a6  test    al, al
0x14000a3a8  jnz     short loc_14000A3C4
0x14000a3aa  lea     r8, [rsp+48h+arg_10]; bool *
0x14000a3af  mov     rdx, rbp; lpWideCharStr
0x14000a3b2  mov     rcx, rdi; hKey
0x14000a3b5  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x14000a3ba  test    eax, eax
0x14000a3bc  js      short loc_14000A3C4
0x14000a3be  mov     al, [rsp+48h+arg_10]
0x14000a3c2  jmp     short loc_14000A3E4
0x14000a3c4  test    rbx, rbx
0x14000a3c7  jz      short loc_14000A3E1
0x14000a3c9  lea     r8, [rsp+48h+var_28]; bool *
0x14000a3ce  mov     rdx, rbp; lpWideCharStr
0x14000a3d1  mov     rcx, rbx; hKey
0x14000a3d4  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x14000a3d9  test    eax, eax
0x14000a3db  mov     al, [rsp+48h+var_28]
0x14000a3df  jns     short loc_14000A3E4
0x14000a3e1  mov     al, sil
0x14000a3e4  mov     rbx, [rsp+48h+arg_0]
0x14000a3e9  add     rsp, 30h
0x14000a3ed  pop     rdi
0x14000a3ee  pop     rsi
0x14000a3ef  pop     rbp
0x14000a3f0  retn
```
