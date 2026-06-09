# UnRegisterDLL(_GUID,ushort *)

- ea: `0x180034e00`
- end: `0x18003506a`
- name: `?UnRegisterDLL@@YAXU_GUID@@PEAG@Z`
- size: `618`
- prototype: `void __fastcall(struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000fa30`
- `0x18001016c`
- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x180034e00`
- `0x180043fa4`
- `0x180044310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180034e59`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180034e59`

## string_xrefs

- `0x180034ec4`: `SOFTWARE\CLASSES\CLSID\`
- `0x180035021`: `CLSID`
- `0x180034fbf`: `SOFTWARE\CLASSES\CLSID`

## pseudocode

```c
void __fastcall UnRegisterDLL(struct _GUID *a1, unsigned __int16 *a2)
{
  GUID v2; // xmm0
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int v6; // eax
  unsigned int v7; // ebx
  signed int v8; // eax
  int v9; // r8d
  unsigned int v10; // ebx
  int v11; // r8d
  int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  GUID rguid; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v16[128]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v17[128]; // [rsp+150h] [rbp+50h] BYREF
  OLECHAR sz[128]; // [rsp+250h] [rbp+150h] BYREF

  v2 = *a1;
  v13 = 0;
  rguid = v2;
  if ( StringFromGUID2(&rguid, sz, 128) )
  {
    v4 = StringCchCopyW(v17, 0x80u, sz);
    v5 = v4;
    if ( v4 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v5);
      }
    }
    v6 = StringCchCopyW(v16, 0x80u, L"SOFTWARE\\CLASSES\\CLSID\\");
    v7 = v6;
    if ( v6 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v6);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v7);
      }
    }
    v8 = StringCchCatW(v16, 0x80u, v17);
    v10 = v8;
    if ( v8 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v8);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v10);
      }
    }
    if ( !(unsigned int)DLRegOpenKeyExW(-2147483646, (unsigned int)v16, v9, 0x2000000, (__int64)&v13) )
    {
      DLRegDeleteKeyW(v13, L"InProcServer32");
      DLRegCloseKey(v13);
    }
    if ( !(unsigned int)DLRegOpenKeyExW(
                          -2147483646,
                          (unsigned int)L"SOFTWARE\\CLASSES\\CLSID",
                          v11,
                          0x2000000,
                          (__int64)&v13) )
    {
      DLRegDeleteKeyW(v13, v17);
      DLRegCloseKey(v13);
    }
    if ( a2 )
    {
      v14 = 0;
      if ( !(unsigned int)DLRegOpenKeyExW(-2147483646, (_DWORD)a2, v12, 0x2000000, (__int64)&v14) )
      {
        DLRegDeleteKeyW(v14, L"CLSID");
        DLRegCloseKey(v14);
      }
      DLRegDeleteKeyW(-2147483646, a2);
    }
  }
}

```

## disassembly

```asm
0x180034e00  mov     [rsp-8+arg_10], rbx
0x180034e05  mov     [rsp-8+arg_18], rdi
0x180034e0a  push    rbp
0x180034e0b  push    r13
0x180034e0d  push    r15
0x180034e0f  lea     rbp, [rsp-260h]
0x180034e17  sub     rsp, 360h
0x180034e1e  mov     rax, cs:__security_cookie
0x180034e25  xor     rax, rsp
0x180034e28  mov     [rbp+270h+var_20], rax
0x180034e2f  movups  xmm0, xmmword ptr [rcx]
0x180034e32  mov     rdi, rdx
0x180034e35  mov     [rsp+370h+var_340], 0
0x180034e3e  mov     r15d, 80h
0x180034e44  lea     rdx, [rbp+270h+sz]; lpsz
0x180034e4b  mov     r8d, r15d; cchMax
0x180034e4e  lea     rcx, [rsp+370h+rguid]; rguid
0x180034e53  movdqu  xmmword ptr [rsp+370h+rguid.Data1], xmm0
0x180034e59  call    cs:__imp_StringFromGUID2
0x180034e5f  test    eax, eax
0x180034e61  jz      loc_180035042
0x180034e67  lea     r8, [rbp+270h+sz]; unsigned __int16 *
0x180034e6e  mov     edx, r15d; unsigned __int64
0x180034e71  lea     rcx, [rbp+270h+var_220]; unsigned __int16 *
0x180034e75  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034e7a  lea     r13, WPP_GLOBAL_Control
0x180034e81  mov     ebx, eax
0x180034e83  test    eax, eax
0x180034e85  jns     short loc_180034EC4
0x180034e87  mov     edx, eax; int
0x180034e89  lea     rcx, qword_18006A9C0; this
0x180034e90  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e9c  cmp     rcx, r13
0x180034e9f  jz      short loc_180034EC4
0x180034ea1  test    byte ptr [rcx+1Ch], 1
0x180034ea5  jz      short loc_180034EC4
0x180034ea7  cmp     byte ptr [rcx+19h], 2
0x180034eab  jb      short loc_180034EC4
0x180034ead  mov     rcx, [rcx+10h]
0x180034eb1  lea     edx, [r15-72h]
0x180034eb5  mov     r9d, ebx
0x180034eb8  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180034ebf  call    WPP_SF_D
0x180034ec4  lea     r8, aSoftwareClasse_0; "SOFTWARE\\CLASSES\\CLSID\\"
0x180034ecb  mov     rdx, r15; unsigned __int64
0x180034ece  lea     rcx, [rsp+370h+var_320]; unsigned __int16 *
0x180034ed3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034ed8  mov     ebx, eax
0x180034eda  test    eax, eax
0x180034edc  jns     short loc_180034F1C
0x180034ede  mov     edx, eax; int
0x180034ee0  lea     rcx, qword_18006A9C0; this
0x180034ee7  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ef3  cmp     rcx, r13
0x180034ef6  jz      short loc_180034F1C
0x180034ef8  test    byte ptr [rcx+1Ch], 1
0x180034efc  jz      short loc_180034F1C
0x180034efe  cmp     byte ptr [rcx+19h], 2
0x180034f02  jb      short loc_180034F1C
0x180034f04  mov     rcx, [rcx+10h]
0x180034f08  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180034f0f  mov     edx, 0Fh
0x180034f14  mov     r9d, ebx
0x180034f17  call    WPP_SF_D
0x180034f1c  lea     r8, [rbp+270h+var_220]; unsigned __int16 *
0x180034f20  mov     rdx, r15; unsigned __int64
0x180034f23  lea     rcx, [rsp+370h+var_320]; unsigned __int16 *
0x180034f28  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034f2d  mov     ebx, eax
0x180034f2f  test    eax, eax
0x180034f31  jns     short loc_180034F71
0x180034f33  mov     edx, eax; int
0x180034f35  lea     rcx, qword_18006A9C0; this
0x180034f3c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f48  cmp     rcx, r13
0x180034f4b  jz      short loc_180034F71
0x180034f4d  test    byte ptr [rcx+1Ch], 1
0x180034f51  jz      short loc_180034F71
0x180034f53  cmp     byte ptr [rcx+19h], 2
0x180034f57  jb      short loc_180034F71
0x180034f59  mov     rcx, [rcx+10h]
0x180034f5d  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180034f64  mov     edx, 10h
0x180034f69  mov     r9d, ebx
0x180034f6c  call    WPP_SF_D
0x180034f71  lea     rax, [rsp+370h+var_340]
0x180034f76  mov     rbx, 0FFFFFFFF80000002h
0x180034f7d  mov     rcx, rbx
0x180034f80  mov     [rsp+370h+var_350], rax
0x180034f85  mov     r9d, 2000000h
0x180034f8b  lea     rdx, [rsp+370h+var_320]
0x180034f90  call    DLRegOpenKeyExW
0x180034f95  test    eax, eax
0x180034f97  jnz     short loc_180034FB4
0x180034f99  mov     rcx, [rsp+370h+var_340]
0x180034f9e  lea     rdx, aInprocserver32_1; "InProcServer32"
0x180034fa5  call    DLRegDeleteKeyW
0x180034faa  mov     rcx, [rsp+370h+var_340]
0x180034faf  call    DLRegCloseKey
0x180034fb4  lea     rax, [rsp+370h+var_340]
0x180034fb9  mov     r9d, 2000000h
0x180034fbf  lea     rdx, aSoftwareClasse_1; "SOFTWARE\\CLASSES\\CLSID"
0x180034fc6  mov     [rsp+370h+var_350], rax
0x180034fcb  mov     rcx, rbx
0x180034fce  call    DLRegOpenKeyExW
0x180034fd3  test    eax, eax
0x180034fd5  jnz     short loc_180034FEF
0x180034fd7  mov     rcx, [rsp+370h+var_340]
0x180034fdc  lea     rdx, [rbp+270h+var_220]
0x180034fe0  call    DLRegDeleteKeyW
0x180034fe5  mov     rcx, [rsp+370h+var_340]
0x180034fea  call    DLRegCloseKey
0x180034fef  test    rdi, rdi
0x180034ff2  jz      short loc_180035042
0x180034ff4  lea     rax, [rsp+370h+var_338]
0x180034ff9  mov     [rsp+370h+var_338], 0
0x180035002  mov     r9d, 2000000h
0x180035008  mov     [rsp+370h+var_350], rax
0x18003500d  mov     rdx, rdi
0x180035010  mov     rcx, rbx
0x180035013  call    DLRegOpenKeyExW
0x180035018  test    eax, eax
0x18003501a  jnz     short loc_180035037
0x18003501c  mov     rcx, [rsp+370h+var_338]
0x180035021  lea     rdx, aClsid; "CLSID"
0x180035028  call    DLRegDeleteKeyW
0x18003502d  mov     rcx, [rsp+370h+var_338]
0x180035032  call    DLRegCloseKey
0x180035037  mov     rdx, rdi
0x18003503a  mov     rcx, rbx
0x18003503d  call    DLRegDeleteKeyW
0x180035042  mov     rcx, [rbp+270h+var_20]
0x180035049  xor     rcx, rsp; StackCookie
0x18003504c  call    __security_check_cookie
0x180035051  lea     r11, [rsp+370h+var_10]
0x180035059  mov     rbx, [r11+30h]
0x18003505d  mov     rdi, [r11+38h]
0x180035061  mov     rsp, r11
0x180035064  pop     r15
0x180035066  pop     r13
0x180035068  pop     rbp
0x180035069  retn
```
