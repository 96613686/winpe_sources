# SetEnvVarInRegistry(long,ushort const *,ushort const *)

- ea: `0x18001642c`
- end: `0x180016573`
- name: `?SetEnvVarInRegistry@@YAJJPEBG0@Z`
- size: `327`
- prototype: `int(int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002832c`

## callees

- `0x180003f30`
- `0x180012be0`
- `0x1800160a8`
- `0x18001642c`
- `0x180016630`
- `0x180017b30`
- `0x18001a280`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800164bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800164bb`

## string_xrefs

- `0x180016538`: `SetEnvVarInRegistry`
- `0x180016503`: `RegEnv.CreateUserKey failed: 0x%x in %s`
- `0x18001652e`: `RegEnv.WriteRegString(SESSIONNAME) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall SetEnvVarInRegistry(unsigned int a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v5; // eax
  int Key; // ebx
  bool v7; // sf
  const char *v8; // rdx
  int v9; // eax
  unsigned int *v11; // [rsp+20h] [rbp-69h]
  struct _SECURITY_ATTRIBUTES *v12; // [rsp+28h] [rbp-61h]
  HKEY phkResult; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v14[2]; // [rsp+48h] [rbp-41h] BYREF
  int v15; // [rsp+58h] [rbp-31h]
  __int64 v16; // [rsp+60h] [rbp-29h]
  int v17; // [rsp+68h] [rbp-21h]
  int v18; // [rsp+6Ch] [rbp-1Dh]
  unsigned __int16 v19[40]; // [rsp+70h] [rbp-19h] BYREF

  v14[1] = 0;
  v14[0] = &CRegistry::`vftable';
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = -1;
  v5 = StringCchPrintfW(v19, 0x21u, L"Volatile Environment\\%lu", a1);
  Key = v5;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(8, "StringCbPrintf failed: 0x%x in %s", (unsigned int)v5, "SetEnvVarInRegistry");
    goto LABEL_14;
  }
  phkResult = 0;
  Key = RegOpenCurrentUser(0x20006u, &phkResult);
  if ( !Key )
  {
    Key = CRegistry::CreateKey((CRegistry *)v14, phkResult, v19, 0x20006u, v11, v12, 1u);
    RegCloseKey(phkResult);
  }
  v7 = Key < 0;
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key | 0x80070000;
    v7 = Key < 0;
  }
  if ( v7 )
  {
    v8 = "RegEnv.CreateUserKey failed: 0x%x in %s";
LABEL_13:
    _DbgPrintMessage(8, v8, (unsigned int)Key, "SetEnvVarInRegistry");
    goto LABEL_14;
  }
  v9 = CRegistry::WriteRegString((CRegistry *)v14, a2, a3);
  Key = v9;
  if ( v9 > 0 )
    Key = (unsigned __int16)v9 | 0x80070000;
  if ( Key < 0 )
  {
    v8 = "RegEnv.WriteRegString(SESSIONNAME) failed: 0x%x in %s";
    goto LABEL_13;
  }
LABEL_14:
  CRegistry::~CRegistry((CRegistry *)v14);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18001642c  mov     [rsp-8+arg_18], rbx
0x180016431  push    rbp
0x180016432  push    rsi
0x180016433  push    rdi
0x180016434  lea     rbp, [rsp-47h]
0x180016439  sub     rsp, 0D0h
0x180016440  mov     rax, cs:__security_cookie
0x180016447  xor     rax, rsp
0x18001644a  mov     [rbp+57h+var_20], rax
0x18001644e  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180016455  mov     [rbp+57h+var_90], 0
0x18001645d  mov     [rbp+57h+var_98], rax
0x180016461  mov     rsi, r8
0x180016464  or      eax, 0FFFFFFFFh
0x180016467  mov     [rbp+57h+var_88], 0
0x18001646e  mov     rdi, rdx
0x180016471  mov     [rbp+57h+var_80], 0
0x180016479  mov     r9d, ecx
0x18001647c  mov     [rbp+57h+var_78], eax
0x18001647f  lea     r8, aVolatileEnviro; "Volatile Environment\\%lu"
0x180016486  mov     [rbp+57h+var_74], eax
0x180016489  lea     edx, [rax+22h]; unsigned __int64
0x18001648c  lea     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180016490  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016495  mov     ebx, eax
0x180016497  test    eax, eax
0x180016499  jns     short loc_1800164AA
0x18001649b  mov     r8d, eax
0x18001649e  lea     rdx, aStringcbprintf; "StringCbPrintf failed: 0x%x in %s"
0x1800164a5  jmp     loc_180016538
0x1800164aa  lea     rdx, [rbp+57h+phkResult]; phkResult
0x1800164ae  mov     [rbp+57h+phkResult], 0
0x1800164b6  mov     ecx, 20006h; samDesired
0x1800164bb  call    cs:__imp_RegOpenCurrentUser
0x1800164c1  mov     ebx, eax
0x1800164c3  test    eax, eax
0x1800164c5  jnz     short loc_1800164F2
0x1800164c7  mov     rdx, [rbp+57h+phkResult]; HKEY
0x1800164cb  lea     r8, [rbp+57h+var_70]; unsigned __int16 *
0x1800164cf  mov     r9d, 20006h; unsigned int
0x1800164d5  mov     [rsp+0E0h+var_B0], 1; unsigned int
0x1800164dd  lea     rcx, [rbp+57h+var_98]; this
0x1800164e1  call    ?CreateKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGKPEAKPEAU_SECURITY_ATTRIBUTES@@K@Z; CRegistry::CreateKey(HKEY__ *,ushort const *,ulong,ulong *,_SECURITY_ATTRIBUTES *,ulong)
0x1800164e6  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800164ea  mov     ebx, eax
0x1800164ec  call    cs:__imp_RegCloseKey
0x1800164f2  test    ebx, ebx
0x1800164f4  jle     short loc_180016501
0x1800164f6  movzx   ebx, bx
0x1800164f9  or      ebx, 80070000h
0x1800164ff  test    ebx, ebx
0x180016501  jns     short loc_18001650C
0x180016503  lea     rdx, aRegenvCreateus; "RegEnv.CreateUserKey failed: 0x%x in %s"
0x18001650a  jmp     short loc_180016535
0x18001650c  mov     r8, rsi; unsigned __int16 *
0x18001650f  lea     rcx, [rbp+57h+var_98]; this
0x180016513  mov     rdx, rdi; unsigned __int16 *
0x180016516  call    ?WriteRegString@CRegistry@@QEAAKPEBG0@Z; CRegistry::WriteRegString(ushort const *,ushort const *)
0x18001651b  mov     ebx, eax
0x18001651d  test    eax, eax
0x18001651f  jle     short loc_18001652A
0x180016521  movzx   ebx, ax
0x180016524  or      ebx, 80070000h
0x18001652a  test    ebx, ebx
0x18001652c  jns     short loc_180016549
0x18001652e  lea     rdx, aRegenvWritereg_0; "RegEnv.WriteRegString(SESSIONNAME) fail"...
0x180016535  mov     r8d, ebx
0x180016538  lea     r9, aSetenvvarinreg; "SetEnvVarInRegistry"
0x18001653f  mov     ecx, 8; int
0x180016544  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016549  lea     rcx, [rbp+57h+var_98]; this
0x18001654d  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180016552  mov     eax, ebx
0x180016554  mov     rcx, [rbp+57h+var_20]
0x180016558  xor     rcx, rsp; StackCookie
0x18001655b  call    __security_check_cookie
0x180016560  mov     rbx, [rsp+0E0h+arg_18]
0x180016568  add     rsp, 0D0h
0x18001656f  pop     rdi
0x180016570  pop     rsi
0x180016571  pop     rbp
0x180016572  retn
```
