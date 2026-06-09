# HrWriteManifestFactoryEntry(ushort * const,ushort * const,ushort * const,tagXW_COMPONENT_TYPE,ushort * const,void * const)

- ea: `0x18000ff64`
- end: `0x180010128`
- name: `?HrWriteManifestFactoryEntry@@YAJQEAG00W4tagXW_COMPONENT_TYPE@@0QEAX@Z`
- size: `452`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, int, __int64, HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000bac8`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000ff64`
- `0x1800105c0`
- `0x1800109d8`
- `0x1800122b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fff3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010089`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010089`

## string_xrefs

- `0x180010019`: `    <registryKey\n        buildFilter=""\n        keyName="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\XWizards\Factory\%S\"\n        >\n      <registryValue\n          buildFilter=""\n          name=""\n          value="%S"\n          valueType="REG_SZ"\n          />\n      <registryValue\n          buildFilter=""\n          name="Class Description"\n          value="%S"\n          valueType="REG_SZ"\n          />\n      <registryValue\n          buildFilter=""`

## pseudocode

```c
__int64 __fastcall HrWriteManifestFactoryEntry(__int64 a1, __int64 *a2, __int64 a3, int a4, __int64 a5, HANDLE hFile)
{
  __int64 *v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // r15d
  char *v14; // rdi
  unsigned int LastErrorHRESULT; // eax
  int v16; // r8d
  DWORD NumberOfBytesWritten[4]; // [rsp+50h] [rbp-38h] BYREF

  v7 = a2;
  v8 = 0;
  if ( hFile )
  {
    v9 = -1;
    NumberOfBytesWritten[0] = 0;
    if ( a2 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)a2 + v10) );
    }
    else
    {
      LODWORD(v10) = 1;
    }
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a5 + 2 * v11) );
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a3 + 2 * v12) );
    v13 = v11 + 809 + v10 + v12;
    v14 = (char *)CoTaskMemAlloc(v13);
    if ( v14 )
    {
      if ( !v7 )
        v7 = &qword_180017410;
      sprintf_sfn(
        v14,
        v13,
        "    <registryKey\r\n"
        "        buildFilter=\"\"\r\n"
        "        keyName=\"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\XWizards\\Factory\\%S\\\"\r\n"
        "        >\r\n"
        "      <registryValue\r\n"
        "          buildFilter=\"\"\r\n"
        "          name=\"\"\r\n"
        "          value=\"%S\"\r\n"
        "          valueType=\"REG_SZ\"\r\n"
        "          />\r\n"
        "      <registryValue\r\n"
        "          buildFilter=\"\"\r\n"
        "          name=\"Class Description\"\r\n"
        "          value=\"%S\"\r\n"
        "          valueType=\"REG_SZ\"\r\n"
        "          />\r\n"
        "      <registryValue\r\n"
        "          buildFilter=\"\"\r\n"
        "          name=\"Class Type\"\r\n"
        "          value=\"%#0*.*lx\"\r\n"
        "          valueType=\"REG_DWORD\"\r\n"
        "          />\r\n"
        "      <registryValue\r\n"
        "          buildFilter=\"\"\r\n"
        "          name=\"File Name\"\r\n"
        "          value=\"%S\"\r\n"
        "          valueType=\"REG_EXPAND_SZ\"\r\n"
        "          />\r\n"
        "    </registryKey>\r\n",
        a1,
        v7,
        a5,
        8,
        8,
        a4,
        a3,
        *(_QWORD *)NumberOfBytesWritten);
      if ( !(unsigned int)IsDuplicateManifestFileEntry(hFile, v14) )
      {
        do
          ++v9;
        while ( v14[v9] );
        if ( !WriteFile(hFile, v14, v9, NumberOfBytesWritten, 0) )
        {
          LastErrorHRESULT = GetLastErrorHRESULT();
          v8 = LastErrorHRESULT;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v16, (_DWORD)v14, LastErrorHRESULT);
        }
      }
      CoTaskMemFree(v14);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000ff64  mov     rax, rsp
0x18000ff67  mov     [rax+10h], rbx
0x18000ff6b  mov     [rax+18h], rbp
0x18000ff6f  mov     [rax+20h], r9d
0x18000ff73  mov     [rax+8], rcx
0x18000ff77  push    rsi
0x18000ff78  push    rdi
0x18000ff79  push    r12
0x18000ff7b  push    r13
0x18000ff7d  push    r15
0x18000ff7f  sub     rsp, 60h
0x18000ff83  mov     r13, r8
0x18000ff86  mov     rbp, rdx
0x18000ff89  xor     r8d, r8d
0x18000ff8c  mov     esi, r8d
0x18000ff8f  cmp     [rsp+88h+hFile], r8
0x18000ff97  jz      loc_1800100DC
0x18000ff9d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ffa1  mov     [rax-38h], r8d
0x18000ffa5  test    rdx, rdx
0x18000ffa8  jz      short loc_18000FFB9
0x18000ffaa  mov     rax, rbx
0x18000ffad  inc     rax
0x18000ffb0  cmp     [rdx+rax*2], r8w
0x18000ffb5  jnz     short loc_18000FFAD
0x18000ffb7  jmp     short loc_18000FFBE
0x18000ffb9  mov     eax, 1
0x18000ffbe  mov     r12, [rsp+88h+arg_20]
0x18000ffc6  mov     rdx, rbx
0x18000ffc9  inc     rdx
0x18000ffcc  cmp     [r12+rdx*2], r8w
0x18000ffd1  jnz     short loc_18000FFC9
0x18000ffd3  mov     rcx, rbx
0x18000ffd6  inc     rcx
0x18000ffd9  cmp     [r13+rcx*2+0], r8w
0x18000ffdf  jnz     short loc_18000FFD6
0x18000ffe1  add     rdx, 329h
0x18000ffe8  add     rax, rdx
0x18000ffeb  add     rcx, rax
0x18000ffee  mov     r15d, ecx
0x18000fff1  mov     ecx, ecx; cb
0x18000fff3  call    cs:__imp_CoTaskMemAlloc
0x18000fff9  mov     rdi, rax
0x18000fffc  test    rax, rax
0x18000ffff  jz      loc_1800100DC
0x180010005  mov     r9, [rsp+88h+arg_0]
0x18001000d  lea     rax, qword_180017410
0x180010014  mov     [rsp+88h+var_40], r13
0x180010019  lea     r8, aRegistrykeyBui_2; "    <registryKey\r\n        buildFilter"...
0x180010020  test    rbp, rbp
0x180010023  mov     edx, r15d; unsigned __int64
0x180010026  mov     rcx, rdi; char *
0x180010029  cmovz   rbp, rax
0x18001002d  mov     eax, [rsp+88h+arg_18]
0x180010034  mov     [rsp+88h+var_48], eax
0x180010038  mov     eax, 8
0x18001003d  mov     [rsp+88h+var_50], eax
0x180010041  mov     [rsp+88h+var_58], eax
0x180010045  mov     [rsp+88h+var_60], r12
0x18001004a  mov     [rsp+88h+lpOverlapped], rbp
0x18001004f  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x180010054  mov     rcx, [rsp+88h+hFile]; hFile
0x18001005c  mov     rdx, rdi; char *
0x18001005f  call    ?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z; IsDuplicateManifestFileEntry(void * const,char * const)
0x180010064  test    eax, eax
0x180010066  jnz     short loc_1800100CA
0x180010068  inc     rbx
0x18001006b  cmp     [rdi+rbx], sil
0x18001006f  jnz     short loc_180010068
0x180010071  mov     rcx, [rsp+88h+hFile]; hFile
0x180010079  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001007e  mov     r8d, ebx; nNumberOfBytesToWrite
0x180010081  mov     [rsp+88h+lpOverlapped], rsi; lpOverlapped
0x180010086  mov     rdx, rdi; lpBuffer
0x180010089  call    cs:__imp_WriteFile
0x18001008f  test    eax, eax
0x180010091  jnz     short loc_1800100CA
0x180010093  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180010098  mov     esi, eax
0x18001009a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100a1  lea     rbx, WPP_GLOBAL_Control
0x1800100a8  cmp     rcx, rbx
0x1800100ab  jz      short loc_1800100D1
0x1800100ad  test    byte ptr [rcx+1Ch], 4
0x1800100b1  jz      short loc_1800100D1
0x1800100b3  mov     rcx, [rcx+10h]
0x1800100b7  mov     edx, 19h
0x1800100bc  mov     r9, rdi
0x1800100bf  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x1800100c3  call    WPP_SF_sD
0x1800100c8  jmp     short loc_1800100D1
0x1800100ca  lea     rbx, WPP_GLOBAL_Control
0x1800100d1  mov     rcx, rdi; pv
0x1800100d4  call    cs:__imp_CoTaskMemFree
0x1800100da  jmp     short loc_1800100E3
0x1800100dc  lea     rbx, WPP_GLOBAL_Control
0x1800100e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100ea  cmp     rcx, rbx
0x1800100ed  jz      short loc_18001010D
0x1800100ef  test    byte ptr [rcx+1Ch], 10h
0x1800100f3  jz      short loc_18001010D
0x1800100f5  mov     rcx, [rcx+10h]
0x1800100f9  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x180010100  mov     edx, 1Ah
0x180010105  mov     r9d, esi
0x180010108  call    WPP_SF_D
0x18001010d  lea     r11, [rsp+88h+var_28]
0x180010112  mov     eax, esi
0x180010114  mov     rbx, [r11+38h]
0x180010118  mov     rbp, [r11+40h]
0x18001011c  mov     rsp, r11
0x18001011f  pop     r15
0x180010121  pop     r13
0x180010123  pop     r12
0x180010125  pop     rdi
0x180010126  pop     rsi
0x180010127  retn
```
