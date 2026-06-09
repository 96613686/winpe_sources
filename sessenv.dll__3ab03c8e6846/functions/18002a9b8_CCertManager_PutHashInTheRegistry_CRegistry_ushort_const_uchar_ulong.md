# CCertManager::PutHashInTheRegistry(CRegistry *,ushort const *,uchar *,ulong)

- ea: `0x18002a9b8`
- end: `0x18002aad8`
- name: `?PutHashInTheRegistry@CCertManager@@AEAAJPEAVCRegistry@@PEBGPEAEK@Z`
- size: `288`
- prototype: `int(CCertManager *__hidden this, struct CRegistry *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003860`
- `0x180012680`

## callees

- `0x180003f30`
- `0x180005190`
- `0x180012be0`
- `0x18002a9b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002aa8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002aa8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002aa65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002aa65`

## string_xrefs

- `0x18002aa33`: `pReg->OpenKey failed: 0x%x in %s`
- `0x18002aaae`: `CCertManager::PutHashInTheRegistry`
- `0x18002aa7e`: `pReg->WriteRegBinary failed: 0x%x in %s`
- `0x18002aaa7`: `pReg->DeleteValue failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertManager::PutHashInTheRegistry(
        CCertManager *this,
        struct CRegistry *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD cbData)
{
  struct CRegistry *v7; // rdi
  int v8; // eax
  signed int v9; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  BYTE *lpData; // [rsp+20h] [rbp-68h]
  _QWORD v14[2]; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+40h] [rbp-48h]
  __int64 v16; // [rsp+48h] [rbp-40h]
  int v17; // [rsp+50h] [rbp-38h]
  int v18; // [rsp+54h] [rbp-34h]

  v7 = a2;
  v14[0] = &CRegistry::`vftable';
  v14[1] = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = -1;
  if ( a2 )
    goto LABEL_7;
  v7 = (struct CRegistry *)v14;
  v8 = CRegistry::OpenKey(
         (CRegistry *)v14,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0x20006u,
         (const unsigned __int16 *)lpData);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_7:
    if ( a4 && cbData )
    {
      v10 = RegSetValueExW(*((HKEY *)v7 + 3), a3, 0, 3u, a4, cbData);
      v9 = v10;
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( v9 < 0 )
        _DbgPrintMessage(
          8,
          "pReg->WriteRegBinary failed: 0x%x in %s",
          (unsigned int)v9,
          "CCertManager::PutHashInTheRegistry");
    }
    else
    {
      v11 = RegDeleteValueW(*((HKEY *)v7 + 3), a3);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 < 0 )
        _DbgPrintMessage(
          8,
          "pReg->DeleteValue failed: 0x%x in %s",
          (unsigned int)v9,
          "CCertManager::PutHashInTheRegistry");
    }
  }
  else
  {
    _DbgPrintMessage(8, "pReg->OpenKey failed: 0x%x in %s", (unsigned int)v9, "CCertManager::PutHashInTheRegistry");
  }
  CRegistry::~CRegistry((CRegistry *)v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002a9b8  mov     r11, rsp
0x18002a9bb  push    rbx
0x18002a9bc  push    rbp
0x18002a9bd  push    rsi
0x18002a9be  push    rdi
0x18002a9bf  sub     rsp, 68h
0x18002a9c3  mov     rsi, r9
0x18002a9c6  mov     rbp, r8
0x18002a9c9  mov     rdi, rdx
0x18002a9cc  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002a9d3  mov     [r11-58h], rax
0x18002a9d7  mov     qword ptr [r11-50h], 0
0x18002a9df  mov     [rsp+88h+var_48], 0
0x18002a9e7  mov     qword ptr [r11-40h], 0
0x18002a9ef  or      eax, 0FFFFFFFFh
0x18002a9f2  mov     [rsp+88h+var_38], eax
0x18002a9f6  mov     [rsp+88h+var_34], eax
0x18002a9fa  test    rdx, rdx
0x18002a9fd  jnz     short loc_18002AA3C
0x18002a9ff  lea     rdi, [r11-58h]
0x18002aa03  mov     r9d, 20006h; unsigned int
0x18002aa09  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x18002aa10  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18002aa17  lea     rcx, [r11-58h]; this
0x18002aa1b  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18002aa20  mov     ebx, eax
0x18002aa22  test    eax, eax
0x18002aa24  jle     short loc_18002AA2F
0x18002aa26  movzx   ebx, ax
0x18002aa29  or      ebx, 80070000h
0x18002aa2f  test    ebx, ebx
0x18002aa31  jns     short loc_18002AA3C
0x18002aa33  lea     rdx, aPregOpenkeyFai; "pReg->OpenKey failed: 0x%x in %s"
0x18002aa3a  jmp     short loc_18002AAAE
0x18002aa3c  test    rsi, rsi
0x18002aa3f  jz      short loc_18002AA87
0x18002aa41  mov     eax, [rsp+88h+arg_20]
0x18002aa48  test    eax, eax
0x18002aa4a  jz      short loc_18002AA87
0x18002aa4c  mov     [rsp+88h+cbData], eax; cbData
0x18002aa50  mov     [rsp+88h+lpData], rsi; lpData
0x18002aa55  mov     r9d, 3; dwType
0x18002aa5b  xor     r8d, r8d; Reserved
0x18002aa5e  mov     rdx, rbp; lpValueName
0x18002aa61  mov     rcx, [rdi+18h]; hKey
0x18002aa65  call    cs:__imp_RegSetValueExW
0x18002aa6b  mov     ebx, eax
0x18002aa6d  test    eax, eax
0x18002aa6f  jle     short loc_18002AA7A
0x18002aa71  movzx   ebx, ax
0x18002aa74  or      ebx, 80070000h
0x18002aa7a  test    ebx, ebx
0x18002aa7c  jns     short loc_18002AAC3
0x18002aa7e  lea     rdx, aPregWriteregbi; "pReg->WriteRegBinary failed: 0x%x in %s"
0x18002aa85  jmp     short loc_18002AAAE
0x18002aa87  mov     rdx, rbp; lpValueName
0x18002aa8a  mov     rcx, [rdi+18h]; hKey
0x18002aa8e  call    cs:__imp_RegDeleteValueW
0x18002aa94  mov     ebx, eax
0x18002aa96  test    eax, eax
0x18002aa98  jle     short loc_18002AAA3
0x18002aa9a  movzx   ebx, ax
0x18002aa9d  or      ebx, 80070000h
0x18002aaa3  test    ebx, ebx
0x18002aaa5  jns     short loc_18002AAC3
0x18002aaa7  lea     rdx, aPregDeletevalu; "pReg->DeleteValue failed: 0x%x in %s"
0x18002aaae  lea     r9, aCcertmanagerPu; "CCertManager::PutHashInTheRegistry"
0x18002aab5  mov     r8d, ebx
0x18002aab8  mov     ecx, 8; int
0x18002aabd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002aac2  nop
0x18002aac3  lea     rcx, [rsp+88h+var_58]; this
0x18002aac8  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18002aacd  mov     eax, ebx
0x18002aacf  add     rsp, 68h
0x18002aad3  pop     rdi
0x18002aad4  pop     rsi
0x18002aad5  pop     rbp
0x18002aad6  pop     rbx
0x18002aad7  retn
```
