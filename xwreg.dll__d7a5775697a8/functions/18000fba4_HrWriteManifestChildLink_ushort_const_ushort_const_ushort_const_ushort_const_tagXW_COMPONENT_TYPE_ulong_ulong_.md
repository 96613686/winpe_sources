# HrWriteManifestChildLink(ushort * const,ushort * const,ushort * const,ushort * const,tagXW_COMPONENT_TYPE,ulong,ulong,void * const)

- ea: `0x18000fba4`
- end: `0x18000fd7a`
- name: `?HrWriteManifestChildLink@@YAJQEAG000W4tagXW_COMPONENT_TYPE@@KKQEAX@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180008b4c`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000fba4`
- `0x1800105c0`
- `0x1800109d8`
- `0x1800122b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc19`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fcd8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fcd8`

## string_xrefs

- `0x18000fc3f`: `    <registryKey\n        buildFilter=""\n        keyName="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\XWizards\Components\%S\Children\%S\"\n        >\n      <registryValue\n          buildFilter=""\n          name=""\n          value="%S"\n          valueType="REG_SZ"\n          />\n      <registryValue\n          buildFilter=""\n          name="Class Description"\n          value="%S"\n          valueType="REG_SZ"\n          />\n      <registryValue\n         `

## pseudocode

```c
__int64 __fastcall HrWriteManifestChildLink(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        HANDLE hFile)
{
  __int64 *v10; // rbp
  unsigned int v11; // esi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  SIZE_T v15; // r15
  char *v16; // rdi
  unsigned int LastErrorHRESULT; // eax
  int v18; // r8d
  DWORD NumberOfBytesWritten[4]; // [rsp+80h] [rbp-38h] BYREF

  v10 = a3;
  v11 = 0;
  if ( hFile )
  {
    v12 = -1;
    NumberOfBytesWritten[0] = 0;
    if ( a3 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)a3 + v13) );
    }
    else
    {
      LODWORD(v13) = 1;
    }
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(a4 + 2 * v14) );
    v15 = (unsigned int)(v14 + 1035 + v13);
    v16 = (char *)CoTaskMemAlloc(v15);
    if ( v16 )
    {
      if ( !v10 )
        v10 = &qword_180017410;
      sprintf_sfn(
        v16,
        (unsigned int)v15,
        "    <registryKey\r\n"
        "        buildFilter=\"\"\r\n"
        "        keyName=\"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\XWizards\\Components\\%S\\Ch"
        "ildren\\%S\\\"\r\n"
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
        "          name=\"Ordinal\"\r\n"
        "          value=\"%#0*.*lx\"\r\n"
        "          valueType=\"REG_DWORD\"\r\n"
        "          />\r\n"
        "      <registryValue\r\n"
        "          buildFilter=\"\"\r\n"
        "          name=\"User Flags\"\r\n"
        "          value=\"%#0*.*lx\"\r\n"
        "          valueType=\"REG_DWORD\"\r\n"
        "          />\r\n"
        "    </registryKey>\r\n",
        a1,
        a2,
        v10,
        a4,
        8,
        8,
        a5,
        8,
        8,
        a6,
        8,
        8,
        a7,
        *(_QWORD *)NumberOfBytesWritten);
      if ( !(unsigned int)IsDuplicateManifestFileEntry(hFile, v16) )
      {
        do
          ++v12;
        while ( v16[v12] );
        if ( !WriteFile(hFile, v16, v12, NumberOfBytesWritten, 0) )
        {
          LastErrorHRESULT = GetLastErrorHRESULT();
          v11 = LastErrorHRESULT;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v18, (_DWORD)v16, LastErrorHRESULT);
        }
      }
      CoTaskMemFree(v16);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18000fba4  mov     rax, rsp
0x18000fba7  mov     [rax+10h], rbx
0x18000fbab  mov     [rax+18h], rbp
0x18000fbaf  mov     [rax+8], rcx
0x18000fbb3  push    rsi
0x18000fbb4  push    rdi
0x18000fbb5  push    r12
0x18000fbb7  push    r13
0x18000fbb9  push    r15
0x18000fbbb  sub     rsp, 90h
0x18000fbc2  mov     r13, rdx
0x18000fbc5  mov     r12, r9
0x18000fbc8  xor     edx, edx
0x18000fbca  mov     rbp, r8
0x18000fbcd  mov     esi, edx
0x18000fbcf  cmp     [rsp+0B8h+hFile], rdx
0x18000fbd7  jz      loc_18000FD2B
0x18000fbdd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fbe1  mov     [rax-38h], edx
0x18000fbe4  test    r8, r8
0x18000fbe7  jz      short loc_18000FBF8
0x18000fbe9  mov     rax, rbx
0x18000fbec  inc     rax
0x18000fbef  cmp     [r8+rax*2], dx
0x18000fbf4  jnz     short loc_18000FBEC
0x18000fbf6  jmp     short loc_18000FBFD
0x18000fbf8  mov     eax, 1
0x18000fbfd  mov     rcx, rbx
0x18000fc00  inc     rcx
0x18000fc03  cmp     [r9+rcx*2], dx
0x18000fc08  jnz     short loc_18000FC00
0x18000fc0a  add     rcx, 40Bh
0x18000fc11  add     rax, rcx
0x18000fc14  mov     ecx, eax; cb
0x18000fc16  mov     r15d, eax
0x18000fc19  call    cs:__imp_CoTaskMemAlloc
0x18000fc1f  mov     rdi, rax
0x18000fc22  test    rax, rax
0x18000fc25  jz      loc_18000FD2B
0x18000fc2b  mov     r9, [rsp+0B8h+arg_0]
0x18000fc33  lea     rax, qword_180017410
0x18000fc3a  mov     ecx, 8
0x18000fc3f  lea     r8, aRegistrykeyBui_0; "    <registryKey\r\n        buildFilter"...
0x18000fc46  test    rbp, rbp
0x18000fc49  mov     edx, r15d; unsigned __int64
0x18000fc4c  cmovz   rbp, rax
0x18000fc50  mov     eax, [rsp+0B8h+arg_30]
0x18000fc57  mov     [rsp+0B8h+var_40], eax
0x18000fc5b  mov     eax, [rsp+0B8h+arg_28]
0x18000fc62  mov     [rsp+0B8h+var_48], ecx
0x18000fc66  mov     [rsp+0B8h+var_50], ecx
0x18000fc6a  mov     [rsp+0B8h+var_58], eax
0x18000fc6e  mov     eax, [rsp+0B8h+arg_20]
0x18000fc75  mov     [rsp+0B8h+var_60], ecx
0x18000fc79  mov     [rsp+0B8h+var_68], ecx
0x18000fc7d  mov     [rsp+0B8h+var_70], eax
0x18000fc81  mov     [rsp+0B8h+var_78], ecx
0x18000fc85  mov     [rsp+0B8h+var_80], ecx
0x18000fc89  mov     rcx, rdi; char *
0x18000fc8c  mov     [rsp+0B8h+var_88], r12
0x18000fc91  mov     [rsp+0B8h+var_90], rbp
0x18000fc96  mov     [rsp+0B8h+lpOverlapped], r13
0x18000fc9b  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x18000fca0  mov     rcx, [rsp+0B8h+hFile]; hFile
0x18000fca8  mov     rdx, rdi; char *
0x18000fcab  call    ?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z; IsDuplicateManifestFileEntry(void * const,char * const)
0x18000fcb0  test    eax, eax
0x18000fcb2  jnz     short loc_18000FD19
0x18000fcb4  inc     rbx
0x18000fcb7  cmp     [rdi+rbx], sil
0x18000fcbb  jnz     short loc_18000FCB4
0x18000fcbd  mov     rcx, [rsp+0B8h+hFile]; hFile
0x18000fcc5  lea     r9, [rsp+0B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000fccd  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000fcd0  mov     [rsp+0B8h+lpOverlapped], rsi; lpOverlapped
0x18000fcd5  mov     rdx, rdi; lpBuffer
0x18000fcd8  call    cs:__imp_WriteFile
0x18000fcde  test    eax, eax
0x18000fce0  jnz     short loc_18000FD19
0x18000fce2  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000fce7  mov     esi, eax
0x18000fce9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcf0  lea     rbx, WPP_GLOBAL_Control
0x18000fcf7  cmp     rcx, rbx
0x18000fcfa  jz      short loc_18000FD20
0x18000fcfc  test    byte ptr [rcx+1Ch], 4
0x18000fd00  jz      short loc_18000FD20
0x18000fd02  mov     rcx, [rcx+10h]
0x18000fd06  mov     edx, 1Fh
0x18000fd0b  mov     r9, rdi
0x18000fd0e  mov     dword ptr [rsp+0B8h+lpOverlapped], eax
0x18000fd12  call    WPP_SF_sD
0x18000fd17  jmp     short loc_18000FD20
0x18000fd19  lea     rbx, WPP_GLOBAL_Control
0x18000fd20  mov     rcx, rdi; pv
0x18000fd23  call    cs:__imp_CoTaskMemFree
0x18000fd29  jmp     short loc_18000FD32
0x18000fd2b  lea     rbx, WPP_GLOBAL_Control
0x18000fd32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd39  cmp     rcx, rbx
0x18000fd3c  jz      short loc_18000FD5C
0x18000fd3e  test    byte ptr [rcx+1Ch], 10h
0x18000fd42  jz      short loc_18000FD5C
0x18000fd44  mov     rcx, [rcx+10h]
0x18000fd48  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000fd4f  mov     edx, 20h ; ' '
0x18000fd54  mov     r9d, esi
0x18000fd57  call    WPP_SF_D
0x18000fd5c  lea     r11, [rsp+0B8h+var_28]
0x18000fd64  mov     eax, esi
0x18000fd66  mov     rbx, [r11+38h]
0x18000fd6a  mov     rbp, [r11+40h]
0x18000fd6e  mov     rsp, r11
0x18000fd71  pop     r15
0x18000fd73  pop     r13
0x18000fd75  pop     r12
0x18000fd77  pop     rdi
0x18000fd78  pop     rsi
0x18000fd79  retn
```
