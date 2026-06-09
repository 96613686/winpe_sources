# CRegistryTransaction::HrBackupKey(HKEY__ * const)

- ea: `0x18000d43c`
- end: `0x18000d541`
- name: `?HrBackupKey@CRegistryTransaction@@QEAAJQEAUHKEY__@@@Z`
- size: `261`
- prototype: `int(CRegistryTransaction *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000d294`

## callees

- `0x180007820`
- `0x18000abbc`
- `0x18000d43c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d4a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d4a4`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18000d4b3`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18000d4b3`

## pseudocode

```c
__int64 __fastcall CRegistryTransaction::HrBackupKey(CRegistryTransaction *this, HKEY a2)
{
  __int64 v2; // r9
  const WCHAR *v6; // r14
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  PVOID *v9; // rcx

  v2 = *((unsigned int *)this + 136);
  if ( (int)v2 >= 0 )
  {
    v6 = (const WCHAR *)((char *)this + 8);
    *((_QWORD *)this + 67) = 0;
    DeleteFileW((LPCWSTR)this + 4);
    v7 = RegSaveKeyW(a2, v6, 0);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_14:
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
          WPP_SF_D(v9[2], 15, WPP_b6864e106af034a19631ace060353c02_Traceguids, v8);
        return v8;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_b6864e106af034a19631ace060353c02_Traceguids,
        (_DWORD)v6,
        v8);
    }
    else
    {
      *((_QWORD *)this + 67) = a2;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b6864e106af034a19631ace060353c02_Traceguids, v2);
  return *((unsigned int *)this + 136);
}

```

## disassembly

```asm
0x18000d43c  push    rbx
0x18000d43e  push    rbp
0x18000d43f  push    rsi
0x18000d440  push    rdi
0x18000d441  push    r14
0x18000d443  sub     rsp, 30h
0x18000d447  mov     r9d, [rcx+220h]
0x18000d44e  mov     rbp, rdx
0x18000d451  mov     rsi, rcx
0x18000d454  test    r9d, r9d
0x18000d457  jns     short loc_18000D492
0x18000d459  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d460  lea     rdi, WPP_GLOBAL_Control
0x18000d467  cmp     rcx, rdi
0x18000d46a  jz      short loc_18000D487
0x18000d46c  test    byte ptr [rcx+1Ch], 4
0x18000d470  jz      short loc_18000D487
0x18000d472  mov     rcx, [rcx+10h]
0x18000d476  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d47d  mov     edx, 0Dh
0x18000d482  call    WPP_SF_D
0x18000d487  mov     eax, [rsi+220h]
0x18000d48d  jmp     loc_18000D536
0x18000d492  lea     r14, [rcx+8]
0x18000d496  mov     qword ptr [rcx+218h], 0
0x18000d4a1  mov     rcx, r14; lpFileName
0x18000d4a4  call    cs:__imp_DeleteFileW
0x18000d4aa  xor     r8d, r8d; lpSecurityAttributes
0x18000d4ad  mov     rdx, r14; lpFile
0x18000d4b0  mov     rcx, rbp; hKey
0x18000d4b3  call    cs:__imp_RegSaveKeyW
0x18000d4b9  mov     ebx, eax
0x18000d4bb  test    eax, eax
0x18000d4bd  jle     short loc_18000D4C8
0x18000d4bf  movzx   ebx, ax
0x18000d4c2  or      ebx, 80070000h
0x18000d4c8  lea     rdi, WPP_GLOBAL_Control
0x18000d4cf  test    ebx, ebx
0x18000d4d1  js      short loc_18000D4DC
0x18000d4d3  mov     [rsi+218h], rbp
0x18000d4da  jmp     short loc_18000D50A
0x18000d4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4e3  cmp     rcx, rdi
0x18000d4e6  jz      short loc_18000D534
0x18000d4e8  test    byte ptr [rcx+1Ch], 4
0x18000d4ec  jz      short loc_18000D511
0x18000d4ee  mov     rcx, [rcx+10h]
0x18000d4f2  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d4f9  mov     edx, 0Eh
0x18000d4fe  mov     [rsp+58h+var_38], ebx
0x18000d502  mov     r9, r14
0x18000d505  call    WPP_SF_SD
0x18000d50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d511  cmp     rcx, rdi
0x18000d514  jz      short loc_18000D534
0x18000d516  test    byte ptr [rcx+1Ch], 10h
0x18000d51a  jz      short loc_18000D534
0x18000d51c  mov     rcx, [rcx+10h]
0x18000d520  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d527  mov     edx, 0Fh
0x18000d52c  mov     r9d, ebx
0x18000d52f  call    WPP_SF_D
0x18000d534  mov     eax, ebx
0x18000d536  add     rsp, 30h
0x18000d53a  pop     r14
0x18000d53c  pop     rdi
0x18000d53d  pop     rsi
0x18000d53e  pop     rbp
0x18000d53f  pop     rbx
0x18000d540  retn
```
