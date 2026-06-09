# CNTFSSecurity::TreeSetSecurityThread(void *)

- ea: `0x180007e00`
- end: `0x180008105`
- name: `?TreeSetSecurityThread@CNTFSSecurity@@KAKPEAX@Z`
- size: `773`
- prototype: `__int64 __fastcall(unsigned int *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800069b8`
- `0x180007e00`
- `0x1800167b4`
- `0x180019404`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800080d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800080d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008083`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008083`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007ffb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007ffb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008009`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007ec7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007ec7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180007e74`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180007e74`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180007ea7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180007ea7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180007ee6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180007ee6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800080e9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800080e9`
- `ADVAPI32!TreeSetNamedSecurityInfoW` at `0x180007fe8`
- `ADVAPI32!TreeSetNamedSecurityInfoW` at `0x180007fe8`
- `USER32!SetCursor` at `0x180007f34`
- `USER32!SetCursor` at `0x180008098`
- `USER32!SetCursor` at `0x180007f34`
- `USER32!SetCursor` at `0x180008098`
- `USER32!LoadCursorW` at `0x180007f2b`
- `USER32!LoadCursorW` at `0x180007f2b`
- `ole32!CoInitialize` at `0x180007e55`
- `ole32!CoInitialize` at `0x180007e55`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::TreeSetSecurityThread(unsigned int *Parameter)
{
  unsigned int v3; // edi
  HCURSOR v4; // r12
  void *v5; // rsi
  __int64 v6; // r14
  HRESULT v7; // eax
  int v8; // r13d
  signed int v9; // ebx
  signed int LastError; // eax
  HCURSOR CursorW; // rax
  __int64 v12; // rdx
  __int64 v13; // rsi
  unsigned int v14; // edx
  void *v15; // rcx
  __int64 v16; // rcx
  void *v17; // rcx
  char v18; // [rsp+28h] [rbp-41h]
  int v19; // [rsp+60h] [rbp-9h] BYREF
  int v20; // [rsp+64h] [rbp-5h]
  PACL pSacl; // [rsp+68h] [rbp-1h] BYREF
  PACL pDacl; // [rsp+70h] [rbp+7h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+Fh] BYREF
  WORD pControl; // [rsp+D0h] [rbp+67h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+D8h] [rbp+6Fh] BYREF
  WINBOOL bDaclPresent; // [rsp+E0h] [rbp+77h] BYREF
  DWORD dwRevision; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( !Parameter )
    return 2147942487LL;
  v3 = *Parameter;
  v4 = 0;
  v5 = (void *)*((_QWORD *)Parameter + 2);
  v6 = *((_QWORD *)Parameter + 1);
  dwRevision = 0;
  pOwner = 0;
  pDacl = 0;
  pSacl = 0;
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  pControl = 0;
  v7 = CoInitialize(0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( !GetSecurityDescriptorControl(v5, &pControl, &dwRevision)
      || (v3 & 1) != 0 && !GetSecurityDescriptorOwner(v5, &pOwner, &bOwnerDefaulted)
      || (v3 & 4) != 0 && !GetSecurityDescriptorDacl(v5, &bDaclPresent, &pDacl, &bOwnerDefaulted)
      || (v3 & 0x48) != 0 && !GetSecurityDescriptorSacl(v5, &bDaclPresent, &pSacl, &bOwnerDefaulted) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError <= 0 )
        goto LABEL_36;
      v9 = (unsigned __int16)LastError;
LABEL_35:
      v9 |= 0x80070000;
      goto LABEL_36;
    }
    if ( (v3 & 4) != 0 )
    {
      if ( (pControl & 0x1000) != 0 )
        v3 |= 0x80000000;
      else
        v3 |= 0x20000000u;
    }
    if ( (v3 & 0x48) != 0 )
    {
      if ( (pControl & 0x2000) != 0 )
        v3 |= 0x40000000u;
      else
        v3 |= 0x10000000u;
    }
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v4 = SetCursor(CursorW);
    CNTFSSecurity::CreateProgressDialog((CNTFSSecurity *)v6, v3);
    if ( (v3 & 8) != 0 )
    {
      v12 = 1;
    }
    else
    {
      if ( (v3 & 1) != 0 )
      {
        v19 = 9;
        v20 = 18;
        v12 = 2;
LABEL_29:
        v13 = EnablePrivileges(&v19, v12);
LABEL_30:
        v9 = TreeSetNamedSecurityInfoW(
               *(LPWSTR *)(v6 + 56),
               SE_FILE_OBJECT,
               v3,
               pOwner,
               0,
               pDacl,
               pSacl,
               Parameter[8],
               ProgressFunction,
               ProgressInvokePrePostError,
               Parameter);
        if ( v13 != -1 )
        {
          SetThreadToken(0, (HANDLE)v13);
          if ( v13 )
            CloseHandle((HANDLE)v13);
        }
        if ( v9 <= 0 )
          goto LABEL_36;
        v9 = (unsigned __int16)v9;
        goto LABEL_35;
      }
      v13 = -1;
      if ( (v3 & 0x40) == 0 )
        goto LABEL_30;
      v20 = 17;
      v12 = 2;
    }
    v19 = 8;
    goto LABEL_29;
  }
  v9 = v7;
LABEL_36:
  if ( Parameter[6] )
  {
    if ( (v3 & 8) != 0 )
    {
      v14 = 83;
    }
    else if ( (v3 & 1) != 0 )
    {
      v14 = 84;
    }
    else
    {
      v14 = 82;
      if ( (v3 & 0x40) != 0 )
        v14 = 81;
    }
    MsgPopup(*(HWND *)(v6 + 328), v14, 0x57u, 0x10030u, g_hInstance, v18);
    v9 = 1;
  }
  v15 = *(void **)(v6 + 344);
  if ( v15 )
  {
    LocalFree(v15);
    *(_QWORD *)(v6 + 344) = 0;
  }
  if ( v4 )
    SetCursor(v4);
  v16 = *(_QWORD *)(v6 + 320);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 320) + 16LL))(*(_QWORD *)(v6 + 320));
    v17 = *(void **)(v6 + 392);
    *(_QWORD *)(v6 + 320) = 0;
    SetEvent(v17);
  }
  *(_QWORD *)(v6 + 328) = 0;
  if ( v8 >= 0 )
    CoUninitialize();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007e00  push    rbp
0x180007e02  push    rbx
0x180007e03  push    rsi
0x180007e04  push    rdi
0x180007e05  push    r12
0x180007e07  push    r13
0x180007e09  push    r14
0x180007e0b  push    r15
0x180007e0d  lea     rbp, [rsp-1Fh]
0x180007e12  sub     rsp, 88h
0x180007e19  xor     ebx, ebx
0x180007e1b  mov     r15, rcx
0x180007e1e  test    rcx, rcx
0x180007e21  jnz     short loc_180007E2D
0x180007e23  mov     eax, 80070057h
0x180007e28  jmp     loc_1800080F1
0x180007e2d  mov     edi, [rcx]
0x180007e2f  mov     r12, rbx
0x180007e32  mov     rsi, [rcx+10h]
0x180007e36  mov     r14, [rcx+8]
0x180007e3a  xor     ecx, ecx; pvReserved
0x180007e3c  mov     [rbp+57h+dwRevision], ebx
0x180007e3f  mov     [rbp+57h+pOwner], rbx
0x180007e43  mov     [rbp+57h+pDacl], rbx
0x180007e47  mov     [rbp+57h+pSacl], rbx
0x180007e4b  mov     [rbp+57h+bOwnerDefaulted], ebx
0x180007e4e  mov     [rbp+57h+bDaclPresent], ebx
0x180007e51  mov     [rbp+57h+pControl], bx
0x180007e55  call    cs:__imp_CoInitialize
0x180007e5b  mov     r13d, eax
0x180007e5e  test    eax, eax
0x180007e60  jns     short loc_180007E69
0x180007e62  mov     ebx, eax
0x180007e64  jmp     loc_18000801C
0x180007e69  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x180007e6d  mov     rcx, rsi; pSecurityDescriptor
0x180007e70  lea     rdx, [rbp+57h+pControl]; pControl
0x180007e74  call    cs:__imp_GetSecurityDescriptorControl
0x180007e7a  test    eax, eax
0x180007e7c  jnz     short loc_180007E96
0x180007e7e  call    cs:__imp_GetLastError
0x180007e84  mov     ebx, eax
0x180007e86  test    eax, eax
0x180007e88  jle     loc_18000801C
0x180007e8e  movzx   ebx, ax
0x180007e91  jmp     loc_180008016
0x180007e96  test    dil, 1
0x180007e9a  jz      short loc_180007EB1
0x180007e9c  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180007ea0  mov     rcx, rsi; pSecurityDescriptor
0x180007ea3  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180007ea7  call    cs:__imp_GetSecurityDescriptorOwner
0x180007ead  test    eax, eax
0x180007eaf  jz      short loc_180007E7E
0x180007eb1  mov     ebx, edi
0x180007eb3  and     ebx, 4
0x180007eb6  jz      short loc_180007ED1
0x180007eb8  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbDaclDefaulted
0x180007ebc  mov     rcx, rsi; pSecurityDescriptor
0x180007ebf  lea     r8, [rbp+57h+pDacl]; pDacl
0x180007ec3  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180007ec7  call    cs:__imp_GetSecurityDescriptorDacl
0x180007ecd  test    eax, eax
0x180007ecf  jz      short loc_180007E7E
0x180007ed1  test    dil, 48h
0x180007ed5  jz      short loc_180007EF0
0x180007ed7  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x180007edb  mov     rcx, rsi; pSecurityDescriptor
0x180007ede  lea     r8, [rbp+57h+pSacl]; pSacl
0x180007ee2  lea     rdx, [rbp+57h+bDaclPresent]; lpbSaclPresent
0x180007ee6  call    cs:__imp_GetSecurityDescriptorSacl
0x180007eec  test    eax, eax
0x180007eee  jz      short loc_180007E7E
0x180007ef0  test    ebx, ebx
0x180007ef2  jz      short loc_180007F09
0x180007ef4  mov     eax, 1000h
0x180007ef9  test    [rbp+57h+pControl], ax
0x180007efd  jz      short loc_180007F05
0x180007eff  bts     edi, 1Fh
0x180007f03  jmp     short loc_180007F09
0x180007f05  bts     edi, 1Dh
0x180007f09  test    dil, 48h
0x180007f0d  jz      short loc_180007F24
0x180007f0f  mov     eax, 2000h
0x180007f14  test    [rbp+57h+pControl], ax
0x180007f18  jz      short loc_180007F20
0x180007f1a  bts     edi, 1Eh
0x180007f1e  jmp     short loc_180007F24
0x180007f20  bts     edi, 1Ch
0x180007f24  mov     edx, 7F02h; lpCursorName
0x180007f29  xor     ecx, ecx; hInstance
0x180007f2b  call    cs:__imp_LoadCursorW
0x180007f31  mov     rcx, rax; hCursor
0x180007f34  call    cs:__imp_SetCursor
0x180007f3a  mov     edx, edi; unsigned int
0x180007f3c  mov     rcx, r14; this
0x180007f3f  mov     r12, rax
0x180007f42  call    ?CreateProgressDialog@CNTFSSecurity@@IEAAXK@Z; CNTFSSecurity::CreateProgressDialog(ulong)
0x180007f47  mov     eax, 8
0x180007f4c  test    al, dil
0x180007f4f  jz      short loc_180007F5A
0x180007f51  lea     edx, [rax-7]
0x180007f54  lea     rcx, [rbp+57h+var_60]
0x180007f58  jmp     short loc_180007F91
0x180007f5a  test    dil, 1
0x180007f5e  jz      short loc_180007F79
0x180007f60  mov     [rbp+57h+var_60], 9
0x180007f67  lea     rcx, [rbp+57h+var_60]
0x180007f6b  mov     [rbp+57h+var_5C], 12h
0x180007f72  mov     edx, 2
0x180007f77  jmp     short loc_180007F94
0x180007f79  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007f7d  test    dil, 40h
0x180007f81  jz      short loc_180007F9C
0x180007f83  mov     [rbp+57h+var_5C], 11h
0x180007f8a  lea     edx, [rsi+3]
0x180007f8d  lea     rcx, [rbp+57h+var_60]
0x180007f91  mov     [rbp+57h+var_60], eax
0x180007f94  call    EnablePrivileges
0x180007f99  mov     rsi, rax
0x180007f9c  mov     r9, [rbp+57h+pOwner]; pOwner
0x180007fa0  lea     rax, ?ProgressFunction@@YAXPEAGKPEAW4_PROGRESS_INVOKE_SETTING@@PEAXH@Z; ProgressFunction(ushort *,ulong,_PROGRESS_INVOKE_SETTING *,void *,int)
0x180007fa7  mov     rcx, [r14+38h]; pObjectName
0x180007fab  mov     r8d, edi; SecurityInfo
0x180007fae  mov     [rsp+0C0h+Args], r15; Args
0x180007fb3  mov     edx, 1; ObjectType
0x180007fb8  mov     [rsp+0C0h+ProgressInvokeSetting], 6; ProgressInvokeSetting
0x180007fc0  mov     [rsp+0C0h+fnProgress], rax; fnProgress
0x180007fc5  mov     eax, [r15+20h]
0x180007fc9  mov     [rsp+0C0h+dwAction], eax; dwAction
0x180007fcd  mov     rax, [rbp+57h+pSacl]
0x180007fd1  mov     [rsp+0C0h+var_90], rax; pSacl
0x180007fd6  mov     rax, [rbp+57h+pDacl]
0x180007fda  mov     [rsp+0C0h+var_98], rax; char
0x180007fdf  mov     [rsp+0C0h+pGroup], 0; pGroup
0x180007fe8  call    cs:__imp_TreeSetNamedSecurityInfoW
0x180007fee  mov     ebx, eax
0x180007ff0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180007ff4  jz      short loc_18000800F
0x180007ff6  mov     rdx, rsi; Token
0x180007ff9  xor     ecx, ecx; Thread
0x180007ffb  call    cs:__imp_SetThreadToken
0x180008001  test    rsi, rsi
0x180008004  jz      short loc_18000800F
0x180008006  mov     rcx, rsi; hObject
0x180008009  call    cs:__imp_CloseHandle
0x18000800f  test    ebx, ebx
0x180008011  jle     short loc_18000801C
0x180008013  movzx   ebx, bx
0x180008016  or      ebx, 80070000h
0x18000801c  cmp     dword ptr [r15+18h], 0
0x180008021  jz      short loc_180008075
0x180008023  test    dil, 8
0x180008027  jz      short loc_180008030
0x180008029  mov     edx, 53h ; 'S'
0x18000802e  jmp     short loc_18000804C
0x180008030  test    dil, 1
0x180008034  jz      short loc_18000803D
0x180008036  mov     edx, 54h ; 'T'
0x18000803b  jmp     short loc_18000804C
0x18000803d  mov     edx, 52h ; 'R'
0x180008042  test    dil, 40h
0x180008046  lea     eax, [rdx-1]
0x180008049  cmovnz  edx, eax; unsigned int
0x18000804c  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180008053  mov     r9d, 10030h; uType
0x180008059  mov     rcx, [r14+148h]; hWnd
0x180008060  mov     r8d, 57h ; 'W'; unsigned int
0x180008066  mov     [rsp+0C0h+pGroup], rax; hAppInst
0x18000806b  call    MsgPopup
0x180008070  mov     ebx, 1
0x180008075  mov     rcx, [r14+158h]; hMem
0x18000807c  xor     edi, edi
0x18000807e  test    rcx, rcx
0x180008081  jz      short loc_180008090
0x180008083  call    cs:__imp_LocalFree
0x180008089  mov     [r14+158h], rdi
0x180008090  test    r12, r12
0x180008093  jz      short loc_18000809E
0x180008095  mov     rcx, r12; hCursor
0x180008098  call    cs:__imp_SetCursor
0x18000809e  mov     rcx, [r14+140h]
0x1800080a5  test    rcx, rcx
0x1800080a8  jz      short loc_1800080DD
0x1800080aa  mov     rax, [rcx]
0x1800080ad  mov     rax, [rax+20h]
0x1800080b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b6  mov     rcx, [r14+140h]
0x1800080bd  mov     rax, [rcx]
0x1800080c0  mov     rax, [rax+10h]
0x1800080c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c9  mov     rcx, [r14+188h]; hEvent
0x1800080d0  mov     [r14+140h], rdi
0x1800080d7  call    cs:__imp_SetEvent
0x1800080dd  mov     [r14+148h], rdi
0x1800080e4  test    r13d, r13d
0x1800080e7  js      short loc_1800080EF
0x1800080e9  call    cs:__imp_CoUninitialize
0x1800080ef  mov     eax, ebx
0x1800080f1  add     rsp, 88h
0x1800080f8  pop     r15
0x1800080fa  pop     r14
0x1800080fc  pop     r13
0x1800080fe  pop     r12
0x180008100  pop     rdi
0x180008101  pop     rsi
0x180008102  pop     rbx
0x180008103  pop     rbp
0x180008104  retn
```
