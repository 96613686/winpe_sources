# IndexEnumerator::LoadMoniker(HKEY__ *,HKEY__ *,ulong,JobMoniker &)

- ea: `0x180026154`
- end: `0x180026433`
- name: `?LoadMoniker@IndexEnumerator@@CAJPEAUHKEY__@@0KAEAVJobMoniker@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, DWORD dwIndex, struct JobMoniker *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003a0c4`

## callees

- `0x18001a430`
- `0x180022600`
- `0x180026154`
- `0x18002643c`
- `0x180040b70`
- `0x180053e54`
- `0x180056794`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026204`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800261fa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800261fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026283`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026283`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002631c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002631c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002640e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002640e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IndexEnumerator::LoadMoniker(HKEY hKey, HKEY a2, DWORD dwIndex, struct JobMoniker *a4)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  int v11; // edx
  LSTATUS v12; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  GUID iid; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR Data[264]; // [rsp+D0h] [rbp-30h] BYREF

  phkResult = 0;
  memset_0(Data, 0, 0x20Au);
  cbData = 522;
  Type = -1;
  cchName = 40;
  memset_0(Name, 0, sizeof(Name));
  if ( RegEnumKeyExW(hKey, dwIndex, Name, &cchName, 0, 0, 0, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids,
        (unsigned int)Name,
        v9);
    }
    goto LABEL_30;
  }
  v10 = RegOpenKeyExW(a2, Name, 0, 0x20019u, &phkResult);
  v9 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids,
        (unsigned int)Name,
        v9);
    }
LABEL_15:
    if ( tsched::IsErrorNotFound((tsched *)v9, v11) )
      v9 = -2147216626;
    goto LABEL_30;
  }
  v12 = RegQueryValueExW(phkResult, L"Path", 0, &Type, (LPBYTE)Data, &cbData);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids,
        (unsigned int)L"Path",
        (__int64)Name,
        v9);
    }
    goto LABEL_15;
  }
  if ( Type == 1 )
  {
    JobMoniker::JobMoniker(&iid, Data, Name);
    JobMoniker::operator=(a4, &iid);
    v9 = 0;
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
  }
  else
  {
    v9 = -2147216627;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids,
        (unsigned int)L"Path",
        (__int64)Name,
        13);
    }
  }
LABEL_30:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v9;
}

```

## disassembly

```asm
0x180026154  push    rbp
0x180026156  push    rbx
0x180026157  push    rsi
0x180026158  push    rdi
0x180026159  push    r14
0x18002615b  lea     rbp, [rsp-1F0h]
0x180026163  sub     rsp, 2F0h
0x18002616a  mov     rax, cs:__security_cookie
0x180026171  xor     rax, rsp
0x180026174  mov     [rbp+210h+var_30], rax
0x18002617b  mov     r14, r9
0x18002617e  mov     edi, r8d
0x180026181  mov     rsi, rdx
0x180026184  mov     rbx, rcx
0x180026187  mov     [rsp+310h+phkResult], 0
0x180026190  xor     edx, edx; Val
0x180026192  mov     r8d, 20Ah; Size
0x180026198  lea     rcx, [rbp+210h+Data]; void *
0x18002619c  call    memset_0
0x1800261a1  mov     [rsp+310h+cbData], 20Ah
0x1800261a9  mov     [rsp+310h+Type], 0FFFFFFFFh
0x1800261b1  mov     [rsp+310h+cchName], 28h ; '('
0x1800261b9  xor     edx, edx; Val
0x1800261bb  lea     r8d, [rdx+50h]; Size
0x1800261bf  lea     rcx, [rbp+210h+Name]; void *
0x1800261c3  call    memset_0
0x1800261c8  mov     [rsp+310h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800261d1  mov     [rsp+310h+lpcchClass], 0; lpcchClass
0x1800261da  mov     [rsp+310h+lpClass], 0; lpClass
0x1800261e3  mov     [rsp+310h+lpReserved], 0; lpReserved
0x1800261ec  lea     r9, [rsp+310h+cchName]; lpcchName
0x1800261f1  lea     r8, [rbp+210h+Name]; lpName
0x1800261f5  mov     edx, edi; dwIndex
0x1800261f7  mov     rcx, rbx; hKey
0x1800261fa  call    cs:__imp_RegEnumKeyExW
0x180026200  test    eax, eax
0x180026202  jz      short loc_180026269
0x180026204  call    cs:__imp_GetLastError
0x18002620a  mov     ebx, eax
0x18002620c  test    eax, eax
0x18002620e  jle     short loc_180026219
0x180026210  movzx   ebx, ax
0x180026213  or      ebx, 80070000h
0x180026219  lea     rax, WPP_GLOBAL_Control
0x180026220  mov     rcx, cs:WPP_GLOBAL_Control
0x180026227  cmp     rcx, rax
0x18002622a  jz      loc_180026404
0x180026230  test    dword ptr [rcx+1Ch], 40000h
0x180026237  jz      loc_180026404
0x18002623d  cmp     byte ptr [rcx+19h], 2
0x180026241  jb      loc_180026404
0x180026247  mov     edx, 0Eh
0x18002624c  mov     dword ptr [rsp+310h+lpReserved], ebx
0x180026250  lea     r9, [rbp+210h+Name]
0x180026254  lea     r8, WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids
0x18002625b  mov     rcx, [rcx+10h]
0x18002625f  call    WPP_SF_Sd
0x180026264  jmp     loc_180026404
0x180026269  lea     rax, [rsp+310h+phkResult]
0x18002626e  mov     [rsp+310h+lpReserved], rax; phkResult
0x180026273  mov     r9d, 20019h; samDesired
0x180026279  xor     r8d, r8d; ulOptions
0x18002627c  lea     rdx, [rbp+210h+Name]; lpSubKey
0x180026280  mov     rcx, rsi; hKey
0x180026283  call    cs:__imp_RegOpenKeyExW
0x180026289  mov     ebx, eax
0x18002628b  test    eax, eax
0x18002628d  jz      short loc_1800262F2
0x18002628f  jle     short loc_18002629A
0x180026291  movzx   ebx, ax
0x180026294  or      ebx, 80070000h
0x18002629a  lea     rax, WPP_GLOBAL_Control
0x1800262a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262a8  cmp     rcx, rax
0x1800262ab  jz      short loc_1800262D9
0x1800262ad  test    dword ptr [rcx+1Ch], 40000h
0x1800262b4  jz      short loc_1800262D9
0x1800262b6  cmp     byte ptr [rcx+19h], 2
0x1800262ba  jb      short loc_1800262D9
0x1800262bc  mov     edx, 0Fh
0x1800262c1  mov     dword ptr [rsp+310h+lpReserved], ebx
0x1800262c5  lea     r9, [rbp+210h+Name]
0x1800262c9  lea     r8, WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids
0x1800262d0  mov     rcx, [rcx+10h]
0x1800262d4  call    WPP_SF_Sd
0x1800262d9  mov     ecx, ebx; this
0x1800262db  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x1800262e0  test    al, al
0x1800262e2  jz      loc_180026404
0x1800262e8  mov     ebx, 8004130Eh
0x1800262ed  jmp     loc_180026404
0x1800262f2  lea     rax, [rsp+310h+cbData]
0x1800262f7  mov     [rsp+310h+lpClass], rax; lpcbData
0x1800262fc  lea     rax, [rbp+210h+Data]
0x180026300  mov     [rsp+310h+lpReserved], rax; lpData
0x180026305  lea     r9, [rsp+310h+Type]; lpType
0x18002630a  xor     r8d, r8d; lpReserved
0x18002630d  lea     rdi, aPath; "Path"
0x180026314  mov     rdx, rdi; lpValueName
0x180026317  mov     rcx, [rsp+310h+phkResult]; hKey
0x18002631c  call    cs:__imp_RegQueryValueExW
0x180026322  mov     ebx, eax
0x180026324  test    eax, eax
0x180026326  jz      short loc_18002637F
0x180026328  jle     short loc_180026333
0x18002632a  movzx   ebx, ax
0x18002632d  or      ebx, 80070000h
0x180026333  lea     rax, WPP_GLOBAL_Control
0x18002633a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026341  cmp     rcx, rax
0x180026344  jz      short loc_1800262D9
0x180026346  test    dword ptr [rcx+1Ch], 40000h
0x18002634d  jz      short loc_1800262D9
0x18002634f  cmp     byte ptr [rcx+19h], 2
0x180026353  jb      short loc_1800262D9
0x180026355  mov     edx, 10h
0x18002635a  mov     dword ptr [rsp+310h+lpClass], ebx
0x18002635e  lea     rax, [rbp+210h+Name]
0x180026362  mov     [rsp+310h+lpReserved], rax
0x180026367  mov     r9, rdi
0x18002636a  lea     r8, WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids
0x180026371  mov     rcx, [rcx+10h]
0x180026375  call    WPP_SF_SSD
0x18002637a  jmp     loc_1800262D9
0x18002637f  cmp     [rsp+310h+Type], 1
0x180026384  jz      short loc_1800263D8
0x180026386  mov     ebx, 8004130Dh
0x18002638b  lea     rax, WPP_GLOBAL_Control
0x180026392  mov     rcx, cs:WPP_GLOBAL_Control
0x180026399  cmp     rcx, rax
0x18002639c  jz      short loc_180026404
0x18002639e  test    dword ptr [rcx+1Ch], 40000h
0x1800263a5  jz      short loc_180026404
0x1800263a7  cmp     byte ptr [rcx+19h], 2
0x1800263ab  jb      short loc_180026404
0x1800263ad  mov     edx, 11h
0x1800263b2  mov     dword ptr [rsp+310h+lpClass], 8004130Dh
0x1800263ba  lea     rax, [rbp+210h+Name]
0x1800263be  mov     [rsp+310h+lpReserved], rax
0x1800263c3  mov     r9, rdi
0x1800263c6  lea     r8, WPP_3a28f766f52e3b91612b0fe468777cfd_Traceguids
0x1800263cd  mov     rcx, [rcx+10h]
0x1800263d1  call    WPP_SF_SSD
0x1800263d6  jmp     short loc_180026404
0x1800263d8  lea     r8, [rbp+210h+Name]; unsigned __int16 *
0x1800263dc  lea     rdx, [rbp+210h+Data]; psz
0x1800263e0  lea     rcx, [rsp+310h+iid]; lpiid
0x1800263e5  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x1800263ea  lea     rdx, [rsp+310h+iid]
0x1800263ef  mov     rcx, r14
0x1800263f2  call    ??4JobMoniker@@QEAAAEAV0@AEBV0@@Z; JobMoniker::operator=(JobMoniker const &)
0x1800263f7  xor     ebx, ebx
0x1800263f9  lea     rcx, [rsp+310h+iid]; this
0x1800263fe  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180026403  nop
0x180026404  mov     rcx, [rsp+310h+phkResult]; hKey
0x180026409  test    rcx, rcx
0x18002640c  jz      short loc_180026414
0x18002640e  call    cs:__imp_RegCloseKey
0x180026414  mov     eax, ebx
0x180026416  mov     rcx, [rbp+210h+var_30]
0x18002641d  xor     rcx, rsp; StackCookie
0x180026420  call    __security_check_cookie
0x180026425  add     rsp, 2F0h
0x18002642c  pop     r14
0x18002642e  pop     rdi
0x18002642f  pop     rsi
0x180026430  pop     rbx
0x180026431  pop     rbp
0x180026432  retn
```
