# HrWriteManifestCoreEntry(ushort * const,ushort * const,ushort * const,tagXW_COMPONENT_TYPE,ushort * const,ulong,void * const)

- ea: `0x18000fd80`
- end: `0x18000ff5d`
- name: `?HrWriteManifestCoreEntry@@YAJQEAG00W4tagXW_COMPONENT_TYPE@@0KQEAX@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180007b28`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000fd80`
- `0x1800105c0`
- `0x1800109d8`
- `0x1800122b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe12`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000febb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000febb`

## string_xrefs

- `0x18000fe38`: `    <registryKey\n        buildFilter=""\n        keyName="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\XWizards\Components\%S\"\n        >\n      <registryValue\n          buildFilter=""\n          name=""\n          value="%S"\n          valueType="REG_SZ"\n          />\n      <registryValue\n          buildFilter=""\n          name="Behavior"\n          value="%#0*.*lx"\n          valueType="REG_DWORD"\n          />\n      <registryValue\n          buildFilter`

## pseudocode

```c
__int64 __fastcall HrWriteManifestCoreEntry(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        HANDLE hFile)
{
  __int64 *v8; // rbp
  unsigned int v9; // esi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // r15d
  char *v15; // rdi
  unsigned int LastErrorHRESULT; // eax
  int v17; // r8d
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-38h] BYREF

  v8 = a2;
  v9 = 0;
  if ( hFile )
  {
    v10 = -1;
    NumberOfBytesWritten = 0;
    if ( a2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *((_WORD *)a2 + v11) );
    }
    else
    {
      LODWORD(v11) = 1;
    }
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a5 + 2 * v12) );
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(a3 + 2 * v13) );
    v14 = v12 + 972 + v11 + v13;
    v15 = (char *)CoTaskMemAlloc(v14);
    if ( v15 )
    {
      if ( !v8 )
        v8 = &qword_180017410;
      sprintf_sfn(
        v15,
        v14,
        "    <registryKey\r\n"
        "        buildFilter=\"\"\r\n"
        "        keyName=\"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\XWizards\\Components\\%S\\\""
        "\r\n"
        "        >\r\n"
        "      <registryValue\r\n"
        "          buildFilter=\"\"\r\n"
        "          name=\"\"\r\n"
        "          value=\"%S\"\r\n"
        "          valueType=\"REG_SZ\"\r\n"
        "          />\r\n"
        "      <registryValue\r\n"
        "          buildFilter=\"\"\r\n"
        "          name=\"Behavior\"\r\n"
        "          value=\"%#0*.*lx\"\r\n"
        "          valueType=\"REG_DWORD\"\r\n"
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
        v8,
        8,
        8,
        a6,
        a5,
        8,
        8,
        a4,
        a3);
      if ( !(unsigned int)IsDuplicateManifestFileEntry(hFile, v15) )
      {
        do
          ++v10;
        while ( v15[v10] );
        if ( !WriteFile(hFile, v15, v10, &NumberOfBytesWritten, 0) )
        {
          LastErrorHRESULT = GetLastErrorHRESULT();
          v9 = LastErrorHRESULT;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v17, (_DWORD)v15, LastErrorHRESULT);
        }
      }
      CoTaskMemFree(v15);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000fd80  mov     rax, rsp
0x18000fd83  mov     [rax+10h], rbx
0x18000fd87  mov     [rax+18h], rbp
0x18000fd8b  mov     [rax+20h], r9d
0x18000fd8f  mov     [rax+8], rcx
0x18000fd93  push    rsi
0x18000fd94  push    rdi
0x18000fd95  push    r12
0x18000fd97  push    r13
0x18000fd99  push    r15
0x18000fd9b  sub     rsp, 80h
0x18000fda2  mov     r13, r8
0x18000fda5  mov     rbp, rdx
0x18000fda8  xor     r8d, r8d
0x18000fdab  mov     esi, r8d
0x18000fdae  cmp     [rsp+0A8h+hFile], r8
0x18000fdb6  jz      loc_18000FF0E
0x18000fdbc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fdc0  mov     [rax-38h], r8d
0x18000fdc4  test    rdx, rdx
0x18000fdc7  jz      short loc_18000FDD8
0x18000fdc9  mov     rax, rbx
0x18000fdcc  inc     rax
0x18000fdcf  cmp     [rdx+rax*2], r8w
0x18000fdd4  jnz     short loc_18000FDCC
0x18000fdd6  jmp     short loc_18000FDDD
0x18000fdd8  mov     eax, 1
0x18000fddd  mov     r12, [rsp+0A8h+arg_20]
0x18000fde5  mov     rdx, rbx
0x18000fde8  inc     rdx
0x18000fdeb  cmp     [r12+rdx*2], r8w
0x18000fdf0  jnz     short loc_18000FDE8
0x18000fdf2  mov     rcx, rbx
0x18000fdf5  inc     rcx
0x18000fdf8  cmp     [r13+rcx*2+0], r8w
0x18000fdfe  jnz     short loc_18000FDF5
0x18000fe00  add     rdx, 3CCh
0x18000fe07  add     rax, rdx
0x18000fe0a  add     rcx, rax
0x18000fe0d  mov     r15d, ecx
0x18000fe10  mov     ecx, ecx; cb
0x18000fe12  call    cs:__imp_CoTaskMemAlloc
0x18000fe18  mov     rdi, rax
0x18000fe1b  test    rax, rax
0x18000fe1e  jz      loc_18000FF0E
0x18000fe24  mov     r9, [rsp+0A8h+arg_0]
0x18000fe2c  lea     rax, qword_180017410
0x18000fe33  mov     [rsp+0A8h+var_48], r13
0x18000fe38  lea     r8, aRegistrykeyBui_1; "    <registryKey\r\n        buildFilter"...
0x18000fe3f  mov     ecx, 8
0x18000fe44  test    rbp, rbp
0x18000fe47  mov     edx, r15d; unsigned __int64
0x18000fe4a  cmovz   rbp, rax
0x18000fe4e  mov     eax, [rsp+0A8h+arg_18]
0x18000fe55  mov     [rsp+0A8h+var_50], eax
0x18000fe59  mov     eax, [rsp+0A8h+arg_28]
0x18000fe60  mov     [rsp+0A8h+var_58], ecx
0x18000fe64  mov     [rsp+0A8h+var_60], ecx
0x18000fe68  mov     [rsp+0A8h+var_68], r12
0x18000fe6d  mov     [rsp+0A8h+var_70], eax
0x18000fe71  mov     [rsp+0A8h+var_78], ecx
0x18000fe75  mov     [rsp+0A8h+var_80], ecx
0x18000fe79  mov     rcx, rdi; char *
0x18000fe7c  mov     [rsp+0A8h+lpOverlapped], rbp
0x18000fe81  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x18000fe86  mov     rcx, [rsp+0A8h+hFile]; hFile
0x18000fe8e  mov     rdx, rdi; char *
0x18000fe91  call    ?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z; IsDuplicateManifestFileEntry(void * const,char * const)
0x18000fe96  test    eax, eax
0x18000fe98  jnz     short loc_18000FEFC
0x18000fe9a  inc     rbx
0x18000fe9d  cmp     [rdi+rbx], sil
0x18000fea1  jnz     short loc_18000FE9A
0x18000fea3  mov     rcx, [rsp+0A8h+hFile]; hFile
0x18000feab  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000feb0  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000feb3  mov     [rsp+0A8h+lpOverlapped], rsi; lpOverlapped
0x18000feb8  mov     rdx, rdi; lpBuffer
0x18000febb  call    cs:__imp_WriteFile
0x18000fec1  test    eax, eax
0x18000fec3  jnz     short loc_18000FEFC
0x18000fec5  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000feca  mov     esi, eax
0x18000fecc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fed3  lea     rbx, WPP_GLOBAL_Control
0x18000feda  cmp     rcx, rbx
0x18000fedd  jz      short loc_18000FF03
0x18000fedf  test    byte ptr [rcx+1Ch], 4
0x18000fee3  jz      short loc_18000FF03
0x18000fee5  mov     rcx, [rcx+10h]
0x18000fee9  mov     edx, 17h
0x18000feee  mov     r9, rdi
0x18000fef1  mov     dword ptr [rsp+0A8h+lpOverlapped], eax
0x18000fef5  call    WPP_SF_sD
0x18000fefa  jmp     short loc_18000FF03
0x18000fefc  lea     rbx, WPP_GLOBAL_Control
0x18000ff03  mov     rcx, rdi; pv
0x18000ff06  call    cs:__imp_CoTaskMemFree
0x18000ff0c  jmp     short loc_18000FF15
0x18000ff0e  lea     rbx, WPP_GLOBAL_Control
0x18000ff15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff1c  cmp     rcx, rbx
0x18000ff1f  jz      short loc_18000FF3F
0x18000ff21  test    byte ptr [rcx+1Ch], 10h
0x18000ff25  jz      short loc_18000FF3F
0x18000ff27  mov     rcx, [rcx+10h]
0x18000ff2b  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000ff32  mov     edx, 18h
0x18000ff37  mov     r9d, esi
0x18000ff3a  call    WPP_SF_D
0x18000ff3f  lea     r11, [rsp+0A8h+var_28]
0x18000ff47  mov     eax, esi
0x18000ff49  mov     rbx, [r11+38h]
0x18000ff4d  mov     rbp, [r11+40h]
0x18000ff51  mov     rsp, r11
0x18000ff54  pop     r15
0x18000ff56  pop     r13
0x18000ff58  pop     r12
0x18000ff5a  pop     rdi
0x18000ff5b  pop     rsi
0x18000ff5c  retn
```
