# HrWriteManifestParentLink(ushort * const,ushort * const,ushort * const,ushort * const,tagXW_COMPONENT_TYPE,void * const)

- ea: `0x180010130`
- end: `0x1800102d7`
- name: `?HrWriteManifestParentLink@@YAJQEAG000W4tagXW_COMPONENT_TYPE@@QEAX@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180008b4c`

## callees

- `0x180003b90`
- `0x180007820`
- `0x180010130`
- `0x1800105c0`
- `0x1800109d8`
- `0x1800122b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800101a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800101a2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010238`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010238`

## string_xrefs

- `0x1800101c6`: `    <registryKey\n        buildFilter=""\n        keyName="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\XWizards\Components\%S\Parents\%S\"\n        >\n      <registryValue\n          buildFilter=""\n          name=""\n          value="%S"\n          valueType="REG_SZ"\n          />\n      <registryValue\n          buildFilter=""\n          name="Class Description"\n          value="%S"\n          valueType="REG_SZ"\n          />\n      <registryValue\n          `

## pseudocode

```c
__int64 __fastcall HrWriteManifestParentLink(__int64 a1, __int64 a2, __int64 *a3, __int64 a4, int a5, HANDLE hFile)
{
  __int64 *v8; // rbp
  unsigned int v9; // esi
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rcx
  SIZE_T v13; // r15
  char *v14; // rbx
  unsigned int LastErrorHRESULT; // eax
  int v16; // r8d
  DWORD NumberOfBytesWritten[4]; // [rsp+50h] [rbp-38h] BYREF

  v8 = a3;
  v9 = 0;
  if ( hFile )
  {
    v10 = -1;
    NumberOfBytesWritten[0] = 0;
    if ( a3 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *((_WORD *)a3 + v11) );
    }
    else
    {
      LODWORD(v11) = 1;
    }
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a4 + 2 * v12) );
    v13 = (unsigned int)(v12 + 713 + v11);
    v14 = (char *)CoTaskMemAlloc(v13);
    if ( v14 )
    {
      if ( !v8 )
        v8 = &qword_180017410;
      sprintf_sfn(
        v14,
        (unsigned int)v13,
        "    <registryKey\r\n"
        "        buildFilter=\"\"\r\n"
        "        keyName=\"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\XWizards\\Components\\%S\\Pa"
        "rents\\%S\\\"\r\n"
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
        "    </registryKey>\r\n",
        a1,
        a2,
        v8,
        a4,
        8,
        8,
        a5,
        *(_QWORD *)NumberOfBytesWritten);
      if ( !(unsigned int)IsDuplicateManifestFileEntry(hFile, v14) )
      {
        do
          ++v10;
        while ( v14[v10] );
        if ( !WriteFile(hFile, v14, v10, NumberOfBytesWritten, 0) )
        {
          LastErrorHRESULT = GetLastErrorHRESULT();
          v9 = LastErrorHRESULT;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v16, (_DWORD)v14, LastErrorHRESULT);
        }
      }
      CoTaskMemFree(v14);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180010130  mov     rax, rsp
0x180010133  mov     [rax+10h], rbx
0x180010137  mov     [rax+18h], rbp
0x18001013b  mov     [rax+8], rcx
0x18001013f  push    rsi
0x180010140  push    rdi
0x180010141  push    r12
0x180010143  push    r13
0x180010145  push    r15
0x180010147  sub     rsp, 60h
0x18001014b  mov     r13, rdx
0x18001014e  mov     r12, r9
0x180010151  xor     edx, edx
0x180010153  mov     rbp, r8
0x180010156  mov     esi, edx
0x180010158  cmp     [rsp+88h+hFile], rdx
0x180010160  jz      loc_18001028B
0x180010166  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001016a  mov     [rax-38h], edx
0x18001016d  test    r8, r8
0x180010170  jz      short loc_180010181
0x180010172  mov     rax, rdi
0x180010175  inc     rax
0x180010178  cmp     [r8+rax*2], dx
0x18001017d  jnz     short loc_180010175
0x18001017f  jmp     short loc_180010186
0x180010181  mov     eax, 1
0x180010186  mov     rcx, rdi
0x180010189  inc     rcx
0x18001018c  cmp     [r9+rcx*2], dx
0x180010191  jnz     short loc_180010189
0x180010193  add     rcx, 2C9h
0x18001019a  add     rax, rcx
0x18001019d  mov     ecx, eax; cb
0x18001019f  mov     r15d, eax
0x1800101a2  call    cs:__imp_CoTaskMemAlloc
0x1800101a8  mov     rbx, rax
0x1800101ab  test    rax, rax
0x1800101ae  jz      loc_18001028B
0x1800101b4  mov     r9, [rsp+88h+arg_0]
0x1800101bc  lea     rax, qword_180017410
0x1800101c3  test    rbp, rbp
0x1800101c6  lea     r8, aRegistrykeyBui_3; "    <registryKey\r\n        buildFilter"...
0x1800101cd  mov     edx, r15d; unsigned __int64
0x1800101d0  mov     rcx, rbx; char *
0x1800101d3  cmovz   rbp, rax
0x1800101d7  mov     eax, [rsp+88h+arg_20]
0x1800101de  mov     [rsp+88h+var_40], eax
0x1800101e2  mov     eax, 8
0x1800101e7  mov     [rsp+88h+var_48], eax
0x1800101eb  mov     [rsp+88h+var_50], eax
0x1800101ef  mov     [rsp+88h+var_58], r12
0x1800101f4  mov     [rsp+88h+var_60], rbp
0x1800101f9  mov     [rsp+88h+lpOverlapped], r13
0x1800101fe  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x180010203  mov     rcx, [rsp+88h+hFile]; hFile
0x18001020b  mov     rdx, rbx; char *
0x18001020e  call    ?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z; IsDuplicateManifestFileEntry(void * const,char * const)
0x180010213  test    eax, eax
0x180010215  jnz     short loc_180010279
0x180010217  inc     rdi
0x18001021a  cmp     [rbx+rdi], sil
0x18001021e  jnz     short loc_180010217
0x180010220  mov     rcx, [rsp+88h+hFile]; hFile
0x180010228  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001022d  mov     r8d, edi; nNumberOfBytesToWrite
0x180010230  mov     [rsp+88h+lpOverlapped], rsi; lpOverlapped
0x180010235  mov     rdx, rbx; lpBuffer
0x180010238  call    cs:__imp_WriteFile
0x18001023e  test    eax, eax
0x180010240  jnz     short loc_180010279
0x180010242  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180010247  mov     esi, eax
0x180010249  mov     rcx, cs:WPP_GLOBAL_Control
0x180010250  lea     rdi, WPP_GLOBAL_Control
0x180010257  cmp     rcx, rdi
0x18001025a  jz      short loc_180010280
0x18001025c  test    byte ptr [rcx+1Ch], 4
0x180010260  jz      short loc_180010280
0x180010262  mov     rcx, [rcx+10h]
0x180010266  mov     edx, 21h ; '!'
0x18001026b  mov     r9, rbx
0x18001026e  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x180010272  call    WPP_SF_sD
0x180010277  jmp     short loc_180010280
0x180010279  lea     rdi, WPP_GLOBAL_Control
0x180010280  mov     rcx, rbx; pv
0x180010283  call    cs:__imp_CoTaskMemFree
0x180010289  jmp     short loc_180010292
0x18001028b  lea     rdi, WPP_GLOBAL_Control
0x180010292  mov     rcx, cs:WPP_GLOBAL_Control
0x180010299  cmp     rcx, rdi
0x18001029c  jz      short loc_1800102BC
0x18001029e  test    byte ptr [rcx+1Ch], 10h
0x1800102a2  jz      short loc_1800102BC
0x1800102a4  mov     rcx, [rcx+10h]
0x1800102a8  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x1800102af  mov     edx, 22h ; '"'
0x1800102b4  mov     r9d, esi
0x1800102b7  call    WPP_SF_D
0x1800102bc  lea     r11, [rsp+88h+var_28]
0x1800102c1  mov     eax, esi
0x1800102c3  mov     rbx, [r11+38h]
0x1800102c7  mov     rbp, [r11+40h]
0x1800102cb  mov     rsp, r11
0x1800102ce  pop     r15
0x1800102d0  pop     r13
0x1800102d2  pop     r12
0x1800102d4  pop     rdi
0x1800102d5  pop     rsi
0x1800102d6  retn
```
