# COfflineObjectItem::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x18000f2c0`
- end: `0x18000f5af`
- name: `?InvokeCommand@COfflineObjectItem@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(COfflineObjectItem *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b880`
- `0x18000bce0`
- `0x18000e28c`
- `0x18000e688`
- `0x18000f2c0`
- `0x18001c10c`
- `0x18001c5c0`
- `0x18001d338`
- `0x18001d420`
- `0x18001d4dc`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000f343`
- `KERNEL32!LocalAlloc` at `0x18000f343`
- `KERNEL32!LocalFree` at `0x18000f57d`
- `KERNEL32!LocalFree` at `0x18000f57d`
- `ole32!OleSetClipboard` at `0x18000f558`
- `ole32!OleSetClipboard` at `0x18000f558`
- `SHELL32!ShellExecuteExW` at `0x18000f477`
- `SHELL32!ShellExecuteExW` at `0x18000f477`
- `SHELL32!__imp_ILFree` at `0x18000f536`
- `SHELL32!__imp_ILFree` at `0x18000f536`

## pseudocode

```c
__int64 __fastcall COfflineObjectItem::InvokeCommand(COfflineObjectItem *this, struct _CMINVOKECOMMANDINFO *a2)
{
  char *v4; // r14
  __int64 v5; // rcx
  int CmdID; // r15d
  signed int v8; // edx
  int updated; // edi
  __int64 i; // r12
  __int64 v11; // r13
  __int64 v12; // rax
  int v13; // ecx
  enum SUBSCRIPTIONTYPE ItemCategory; // eax
  __int32 v15; // eax
  __int32 v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct _GUID v20; // xmm2
  enum SUBSCRIPTIONTYPE v21; // eax
  __int32 v22; // eax
  __int32 v23; // eax
  __int64 v24; // r8
  unsigned int v25; // r9d
  signed int v26; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v27; // [rsp+28h] [rbp-D8h] BYREF
  struct _GUID v28; // [rsp+30h] [rbp-D0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+B4h] [rbp-4Ch]
  __int64 v32; // [rsp+BCh] [rbp-44h]
  unsigned __int16 v33[2482]; // [rsp+2DCh] [rbp+1DCh] BYREF

  v27 = (unsigned __int16 *)a2;
  v4 = 0;
  CmdID = GetCmdID(a2->lpVerb);
  if ( CmdID == 4 )
  {
    if ( !(unsigned int)ConfirmDelete(a2->hwnd) )
      return 1;
  }
  else if ( CmdID == 1 )
  {
    v4 = (char *)LocalAlloc(0x40u, 16LL * *((unsigned int *)this + 14));
    if ( !v4 )
      return 2147942414LL;
  }
  v8 = 0;
  updated = 0;
  v26 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 14); i = (unsigned int)(i + 1) )
  {
    v11 = *(_QWORD *)(*((_QWORD *)this + 8) + 8 * i);
    if ( !v11 )
      continue;
    if ( !CmdID )
    {
      if ( (unsigned int)i >= 0xA )
        return 1;
      v13 = *(_DWORD *)(v11 + 52);
      v28 = *(struct _GUID *)(v11 + 164);
      ItemCategory = GetItemCategory(v13, &v28);
      if ( ItemCategory == SUBSTYPE_URL || (v15 = ItemCategory - 1) == 0 || (v16 = v15 - 1) == 0 || v16 == 2 )
      {
        memset_0(&pExecInfo, 0, sizeof(pExecInfo));
        v17 = *(_QWORD *)(v11 + 200) + 8LL;
        pExecInfo.cbSize = 112;
        pExecInfo.lpFile = (LPCWSTR)(v11 + v17);
        pExecInfo.nShow = 1;
        pExecInfo.hwnd = (HWND)*((_QWORD *)v27 + 1);
        updated = ShellExecuteExW(&pExecInfo);
      }
      goto LABEL_25;
    }
    v5 = (unsigned int)(CmdID - 1);
    if ( CmdID == 1 )
    {
      v12 = 2LL * v8++;
      v26 = v8;
      *(_OWORD *)&v4[8 * v12] = *(_OWORD *)(v11 + 128);
      continue;
    }
    if ( CmdID == 3 )
    {
      OleSetClipboard((LPDATAOBJECT)(((unsigned __int64)this + 24) & -(__int64)(this != 0)));
      return (unsigned int)updated;
    }
    v5 = (unsigned int)(CmdID - 4);
    if ( CmdID == 4 )
    {
      updated = DoDeleteSubscription((struct OOEntry *)(v11 + 8));
      if ( updated >= 0 )
        GenerateEvent(4, *(LPCITEMIDLIST *)(*((_QWORD *)this + 8) + 8 * i));
LABEL_25:
      v8 = v26;
      continue;
    }
    if ( CmdID == 5 )
    {
      _mm_lfence();
      v18 = *(_QWORD *)(*((_QWORD *)this + 8) + 8 * i) + 8LL;
      v31 = 0;
      v32 = 0;
      *(_DWORD *)(v18 + 4) = 0;
      CopyToOOEBuf(v18, v30);
      v19 = *(_QWORD *)(*((_QWORD *)this + 8) + 8 * i);
      v20 = *(struct _GUID *)(v19 + 164);
      LODWORD(v19) = *(_DWORD *)(v19 + 52);
      v28 = v20;
      v21 = GetItemCategory(v19, &v28);
      if ( (v21 == SUBSTYPE_URL || (v22 = v21 - 1) == 0 || (v23 = v22 - 1) == 0 || (unsigned int)(v23 - 1) <= 1)
        && CreatePropSheet(*((_QWORD *)v27 + 1), (__int64)v30) > 0 )
      {
        v27 = 0;
        updated = LoadSubscription(v33, &v27, v24, v25);
        if ( updated >= 0 )
        {
          ILFree(*(LPITEMIDLIST *)(*((_QWORD *)this + 8) + 8 * i));
          *(_QWORD *)(*((_QWORD *)this + 8) + 8 * i) = v27;
        }
      }
      return (unsigned int)updated;
    }
    updated = -2147467259;
  }
  if ( CmdID == 1 )
  {
    updated = SendUpdateRequests(v5, v4, v8);
    LocalFree(v4);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000f2c0  mov     [rsp-8+arg_10], rbx
0x18000f2c5  push    rbp
0x18000f2c6  push    rsi
0x18000f2c7  push    rdi
0x18000f2c8  push    r12
0x18000f2ca  push    r13
0x18000f2cc  push    r14
0x18000f2ce  push    r15
0x18000f2d0  lea     rbp, [rsp-1550h]
0x18000f2d8  mov     eax, 1650h
0x18000f2dd  call    _alloca_probe
0x18000f2e2  sub     rsp, rax
0x18000f2e5  mov     rax, cs:__security_cookie
0x18000f2ec  xor     rax, rsp
0x18000f2ef  mov     [rbp+1580h+var_40], rax
0x18000f2f6  mov     rbx, rcx
0x18000f2f9  mov     [rsp+1680h+var_1658], rdx
0x18000f2fe  mov     rcx, [rdx+10h]; lpString2
0x18000f302  mov     rdi, rdx
0x18000f305  call    _GetCmdID
0x18000f30a  xor     r14d, r14d
0x18000f30d  mov     r15d, eax
0x18000f310  cmp     eax, 4
0x18000f313  jnz     short loc_18000F332
0x18000f315  mov     r8, [rbx+40h]
0x18000f319  mov     edx, [rbx+38h]
0x18000f31c  mov     rcx, [rdi+8]; hWnd
0x18000f320  call    ConfirmDelete
0x18000f325  test    eax, eax
0x18000f327  jnz     short loc_18000F35B
0x18000f329  lea     eax, [r15-3]
0x18000f32d  jmp     loc_18000F585
0x18000f332  cmp     r15d, 1
0x18000f336  jnz     short loc_18000F35B
0x18000f338  mov     edx, [rbx+38h]
0x18000f33b  lea     ecx, [r15+3Fh]; uFlags
0x18000f33f  shl     rdx, 4; uBytes
0x18000f343  call    cs:__imp_LocalAlloc
0x18000f349  mov     r14, rax
0x18000f34c  test    rax, rax
0x18000f34f  jnz     short loc_18000F35B
0x18000f351  mov     eax, 8007000Eh
0x18000f356  jmp     loc_18000F585
0x18000f35b  xor     edx, edx
0x18000f35d  xor     edi, edi
0x18000f35f  mov     [rsp+1680h+var_1660], edx
0x18000f363  xor     r12d, r12d
0x18000f366  cmp     r12d, [rbx+38h]
0x18000f36a  jnb     loc_18000F567
0x18000f370  mov     rax, [rbx+40h]
0x18000f374  mov     r13, [rax+r12*8]
0x18000f378  test    r13, r13
0x18000f37b  jz      loc_18000F483
0x18000f381  mov     ecx, r15d
0x18000f384  test    r15d, r15d
0x18000f387  jz      short loc_18000F3F8
0x18000f389  sub     ecx, 1
0x18000f38c  jz      short loc_18000F3D9
0x18000f38e  sub     ecx, 2
0x18000f391  jz      loc_18000F54B
0x18000f397  sub     ecx, 1
0x18000f39a  jz      short loc_18000F3AF
0x18000f39c  cmp     ecx, 1
0x18000f39f  jz      loc_18000F48B
0x18000f3a5  mov     edi, 80004005h
0x18000f3aa  jmp     loc_18000F483
0x18000f3af  lea     rcx, [r13+8]; struct OOEntry *
0x18000f3b3  call    ?DoDeleteSubscription@@YAJPEFAUOOEntry@@@Z; DoDeleteSubscription(OOEntry *)
0x18000f3b8  mov     edi, eax
0x18000f3ba  test    eax, eax
0x18000f3bc  js      loc_18000F47F
0x18000f3c2  mov     rdx, [rbx+40h]
0x18000f3c6  mov     ecx, 4; wEventId
0x18000f3cb  mov     rdx, [rdx+r12*8]; pidl2
0x18000f3cf  call    _GenerateEvent
0x18000f3d4  jmp     loc_18000F47F
0x18000f3d9  movups  xmm0, xmmword ptr [r13+80h]
0x18000f3e1  movsxd  rax, edx
0x18000f3e4  add     rax, rax
0x18000f3e7  inc     edx
0x18000f3e9  mov     [rsp+1680h+var_1660], edx
0x18000f3ed  movdqu  xmmword ptr [r14+rax*8], xmm0
0x18000f3f3  jmp     loc_18000F483
0x18000f3f8  cmp     r12d, 0Ah
0x18000f3fc  jnb     loc_18000F560
0x18000f402  movups  xmm0, xmmword ptr [r13+0A4h]
0x18000f40a  mov     ecx, [r13+34h]; int
0x18000f40e  lea     rdx, [rsp+1680h+var_1650]; struct _GUID *
0x18000f413  movdqu  xmmword ptr [rsp+1680h+var_1650.Data1], xmm0
0x18000f419  call    ?GetItemCategory@@YA?AW4SUBSCRIPTIONTYPE@@HAEBU_GUID@@@Z; GetItemCategory(int,_GUID const &)
0x18000f41e  test    eax, eax
0x18000f420  jz      short loc_18000F431
0x18000f422  sub     eax, 1
0x18000f425  jz      short loc_18000F431
0x18000f427  sub     eax, 1
0x18000f42a  jz      short loc_18000F431
0x18000f42c  cmp     eax, 2
0x18000f42f  jnz     short loc_18000F47F
0x18000f431  mov     esi, 70h ; 'p'
0x18000f436  lea     rcx, [rsp+1680h+pExecInfo]; void *
0x18000f43b  mov     r8d, esi; Size
0x18000f43e  xor     edx, edx; Val
0x18000f440  call    memset_0
0x18000f445  mov     rcx, [r13+0C8h]
0x18000f44c  mov     rax, [rsp+1680h+var_1658]
0x18000f451  add     rcx, 8
0x18000f455  add     rcx, r13
0x18000f458  mov     [rsp+1680h+pExecInfo.cbSize], esi
0x18000f45c  mov     [rsp+1680h+pExecInfo.lpFile], rcx
0x18000f461  lea     rcx, [rsp+1680h+pExecInfo]; pExecInfo
0x18000f466  mov     [rsp+1680h+pExecInfo.nShow], 1
0x18000f46e  mov     rax, [rax+8]
0x18000f472  mov     [rsp+1680h+pExecInfo.hwnd], rax
0x18000f477  call    cs:__imp_ShellExecuteExW
0x18000f47d  mov     edi, eax
0x18000f47f  mov     edx, [rsp+1680h+var_1660]
0x18000f483  inc     r12d
0x18000f486  jmp     loc_18000F366
0x18000f48b  lfence
0x18000f48e  mov     rax, [rbx+40h]
0x18000f492  lea     rdx, [rbp+1580h+var_15D0]
0x18000f496  mov     rcx, [rax+r12*8]
0x18000f49a  add     rcx, 8
0x18000f49e  mov     [rbp+1580h+var_15CC], 0
0x18000f4a6  mov     [rbp+1580h+var_15C4], 0
0x18000f4ae  mov     dword ptr [rcx+4], 0
0x18000f4b5  call    CopyToOOEBuf
0x18000f4ba  mov     r11, [rbx+40h]
0x18000f4be  lea     rdx, [rsp+1680h+var_1650]; struct _GUID *
0x18000f4c3  mov     rcx, [r11+r12*8]
0x18000f4c7  movups  xmm2, xmmword ptr [rcx+0A4h]
0x18000f4ce  mov     ecx, [rcx+34h]; int
0x18000f4d1  movdqu  xmmword ptr [rsp+1680h+var_1650.Data1], xmm2
0x18000f4d7  call    ?GetItemCategory@@YA?AW4SUBSCRIPTIONTYPE@@HAEBU_GUID@@@Z; GetItemCategory(int,_GUID const &)
0x18000f4dc  test    eax, eax
0x18000f4de  jz      short loc_18000F4F8
0x18000f4e0  sub     eax, 1
0x18000f4e3  jz      short loc_18000F4F8
0x18000f4e5  sub     eax, 1
0x18000f4e8  jz      short loc_18000F4F8
0x18000f4ea  sub     eax, 1
0x18000f4ed  jz      short loc_18000F4F8
0x18000f4ef  cmp     eax, 1
0x18000f4f2  jnz     loc_18000F583
0x18000f4f8  mov     rax, [rsp+1680h+var_1658]
0x18000f4fd  lea     rdx, [rbp+1580h+var_15D0]
0x18000f501  mov     rcx, [rax+8]
0x18000f505  call    _CreatePropSheet
0x18000f50a  test    eax, eax
0x18000f50c  jle     short loc_18000F583
0x18000f50e  lea     rdx, [rsp+1680h+var_1658]
0x18000f513  mov     [rsp+1680h+var_1658], 0
0x18000f51c  lea     rcx, [rbp+1580h+var_13A4]
0x18000f523  call    LoadSubscription
0x18000f528  mov     edi, eax
0x18000f52a  test    eax, eax
0x18000f52c  js      short loc_18000F583
0x18000f52e  mov     rcx, [rbx+40h]
0x18000f532  mov     rcx, [rcx+r12*8]; pidl
0x18000f536  call    cs:__imp_ILFree
0x18000f53c  mov     rcx, [rbx+40h]
0x18000f540  mov     rax, [rsp+1680h+var_1658]
0x18000f545  mov     [rcx+r12*8], rax
0x18000f549  jmp     short loc_18000F583
0x18000f54b  lea     rax, [rbx+18h]
0x18000f54f  neg     rbx
0x18000f552  sbb     rcx, rcx
0x18000f555  and     rcx, rax; pDataObj
0x18000f558  call    cs:__imp_OleSetClipboard
0x18000f55e  jmp     short loc_18000F583
0x18000f560  mov     edi, 1
0x18000f565  jmp     short loc_18000F583
0x18000f567  cmp     r15d, 1
0x18000f56b  jnz     short loc_18000F583
0x18000f56d  mov     r8d, edx
0x18000f570  mov     rdx, r14
0x18000f573  call    SendUpdateRequests
0x18000f578  mov     rcx, r14; hMem
0x18000f57b  mov     edi, eax
0x18000f57d  call    cs:__imp_LocalFree
0x18000f583  mov     eax, edi
0x18000f585  mov     rcx, [rbp+1580h+var_40]
0x18000f58c  xor     rcx, rsp; StackCookie
0x18000f58f  call    __security_check_cookie
0x18000f594  mov     rbx, [rsp+1680h+arg_10]
0x18000f59c  add     rsp, 1650h
0x18000f5a3  pop     r15
0x18000f5a5  pop     r14
0x18000f5a7  pop     r13
0x18000f5a9  pop     r12
0x18000f5ab  pop     rdi
0x18000f5ac  pop     rsi
0x18000f5ad  pop     rbp
0x18000f5ae  retn
```
