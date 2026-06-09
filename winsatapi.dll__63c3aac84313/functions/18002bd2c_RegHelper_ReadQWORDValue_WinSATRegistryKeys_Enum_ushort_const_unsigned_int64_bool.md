# RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)

- ea: `0x18002bd2c`
- end: `0x18002be45`
- name: `?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z`
- size: `281`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021294`
- `0x1800213d0`
- `0x180021904`

## callees

- `0x18000e234`
- `0x1800173a4`
- `0x18002bd2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdcd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdcd`

## pseudocode

```c
__int64 __fastcall RegHelper::ReadQWORDValue(int a1, const WCHAR *a2, _QWORD *a3, _BYTE *a4)
{
  const WCHAR *v7; // r8
  unsigned int v8; // edi
  LSTATUS v9; // eax
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey[4]; // [rsp+40h] [rbp-20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+20h] BYREF

  memset(hKey, 0, 24);
  *(_QWORD *)Data = 0;
  if ( a1 )
  {
    if ( a1 != 1 )
    {
      ATL::CRegKey::Close(hKey);
      return 87;
    }
    v7 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI";
  }
  else
  {
    v7 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT";
  }
  v8 = ATL::CRegKey::Open(hKey, HKEY_LOCAL_MACHINE, v7, 0x20019u);
  if ( v8 )
  {
LABEL_10:
    ATL::CRegKey::Close(hKey);
    return v8;
  }
  Type = 0;
  cbData = 8;
  v9 = RegQueryValueExW(hKey[0], a2, 0, &Type, Data, &cbData);
  if ( v9 )
  {
    if ( v9 != 2 )
      goto LABEL_9;
    if ( a4 )
      *a4 = 1;
    *(_QWORD *)Data = 0;
  }
  else
  {
    if ( Type != 11 )
    {
      v9 = 13;
LABEL_9:
      v8 = v9;
      goto LABEL_10;
    }
    if ( a4 )
      *a4 = 0;
  }
  *a3 = *(_QWORD *)Data;
  ATL::CRegKey::Close(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002bd2c  mov     [rsp-18h+arg_8], rbx
0x18002bd31  mov     [rsp-18h+arg_10], rsi
0x18002bd36  push    rbp
0x18002bd37  push    rdi
0x18002bd38  push    r14
0x18002bd3a  mov     rbp, rsp
0x18002bd3d  sub     rsp, 60h
0x18002bd41  mov     [rbp+hKey], 0
0x18002bd49  mov     rbx, r9
0x18002bd4c  mov     [rbp+var_18], 0
0x18002bd54  mov     rsi, r8
0x18002bd57  mov     [rbp+var_10], 0
0x18002bd5f  mov     r14, rdx
0x18002bd62  mov     qword ptr [rbp+Data], 0
0x18002bd6a  test    ecx, ecx
0x18002bd6c  jnz     short loc_18002BD77
0x18002bd6e  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002bd75  jmp     short loc_18002BD87
0x18002bd77  cmp     ecx, 1
0x18002bd7a  jnz     loc_18002BE22
0x18002bd80  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002bd87  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002bd8e  lea     rcx, [rbp+hKey]; this
0x18002bd92  mov     r9d, 20019h; unsigned int
0x18002bd98  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002bd9d  mov     edi, eax
0x18002bd9f  test    eax, eax
0x18002bda1  jnz     short loc_18002BDE2
0x18002bda3  mov     rcx, [rbp+hKey]; hKey
0x18002bda7  lea     r9, [rbp+Type]; lpType
0x18002bdab  mov     [rbp+Type], eax
0x18002bdae  xor     r8d, r8d; lpReserved
0x18002bdb1  lea     rax, [rbp+cbData]
0x18002bdb5  mov     [rbp+cbData], 8
0x18002bdbc  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002bdc1  mov     rdx, r14; lpValueName
0x18002bdc4  lea     rax, [rbp+Data]
0x18002bdc8  mov     [rsp+60h+lpData], rax; lpData
0x18002bdcd  call    cs:__imp_RegQueryValueExW
0x18002bdd3  test    eax, eax
0x18002bdd5  jnz     short loc_18002BDF9
0x18002bdd7  cmp     [rbp+Type], 0Bh
0x18002bddb  jz      short loc_18002BDEF
0x18002bddd  lea     eax, [rdi+0Dh]
0x18002bde0  mov     edi, eax
0x18002bde2  lea     rcx, [rbp+hKey]; this
0x18002bde6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002bdeb  mov     eax, edi
0x18002bded  jmp     short loc_18002BE30
0x18002bdef  test    rbx, rbx
0x18002bdf2  jz      short loc_18002BE0E
0x18002bdf4  mov     byte ptr [rbx], 0
0x18002bdf7  jmp     short loc_18002BE0E
0x18002bdf9  cmp     eax, 2
0x18002bdfc  jnz     short loc_18002BDE0
0x18002bdfe  test    rbx, rbx
0x18002be01  jz      short loc_18002BE06
0x18002be03  mov     byte ptr [rbx], 1
0x18002be06  mov     qword ptr [rbp+Data], 0
0x18002be0e  mov     rax, qword ptr [rbp+Data]
0x18002be12  lea     rcx, [rbp+hKey]; this
0x18002be16  mov     [rsi], rax
0x18002be19  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002be1e  xor     eax, eax
0x18002be20  jmp     short loc_18002BE30
0x18002be22  lea     rcx, [rbp+hKey]; this
0x18002be26  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002be2b  mov     eax, 57h ; 'W'
0x18002be30  lea     r11, [rsp+60h+var_s0]
0x18002be35  mov     rbx, [r11+28h]
0x18002be39  mov     rsi, [r11+30h]
0x18002be3d  mov     rsp, r11
0x18002be40  pop     r14
0x18002be42  pop     rdi
0x18002be43  pop     rbp
0x18002be44  retn
```
