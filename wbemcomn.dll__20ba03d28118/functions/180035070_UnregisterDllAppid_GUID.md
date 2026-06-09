# UnregisterDllAppid(_GUID)

- ea: `0x180035070`
- end: `0x1800352e3`
- name: `?UnregisterDllAppid@@YAJU_GUID@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x180035070`
- `0x180043fa4`
- `0x180044310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003512d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003520d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003512d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003520d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352a2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180035107`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180035107`

## string_xrefs

- `0x180035098`: `Software\Classes\Clsid\`

## pseudocode

```c
signed int __fastcall UnregisterDllAppid(GUID *rguid)
{
  signed int v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  signed int v7; // eax
  __int64 v8; // rdx
  signed int result; // eax
  signed int v10; // eax
  bool v11; // sf
  signed int v12; // eax
  signed int v13; // eax
  bool v14; // sf
  signed int v15; // eax
  unsigned __int16 v16[17]; // [rsp+20h] [rbp-B8h] BYREF
  int v17; // [rsp+42h] [rbp-96h]
  __int16 v18; // [rsp+46h] [rbp-92h]
  OLECHAR sz[57]; // [rsp+4Eh] [rbp-8Ah] BYREF

  v2 = StringCchCopyW(v16, 0x4Du, L"Software\\Classes\\Clsid\\");
  v3 = v2;
  if ( v2 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v3);
    }
  }
  if ( !StringFromGUID2(rguid, sz, 39) )
  {
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError > 0 )
      v5 = 1;
    if ( v5 )
    {
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v6);
    }
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = 34;
    goto LABEL_19;
  }
  if ( DLRegDeleteKeyW(-2147483646, (__int64)v16) )
  {
    v10 = GetLastError();
    v11 = v10 < 0;
    if ( v10 > 0 )
      v11 = 1;
    if ( v11 )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v12);
    }
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = 35;
    goto LABEL_19;
  }
  v17 = 7340097;
  v18 = 112;
  if ( !DLRegDeleteKeyW(-2147483646, (__int64)v16) )
    return 0;
  v13 = GetLastError();
  v14 = v13 < 0;
  if ( v13 > 0 )
    v14 = 1;
  if ( v14 )
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v15);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = 36;
LABEL_19:
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, (unsigned int)v7);
  }
LABEL_20:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180035070  mov     [rsp+arg_8], rbx
0x180035075  mov     [rsp+arg_10], rdi
0x18003507a  push    r14
0x18003507c  sub     rsp, 0D0h
0x180035083  mov     rax, cs:__security_cookie
0x18003508a  xor     rax, rsp
0x18003508d  mov     [rsp+0D8h+var_18], rax
0x180035095  mov     rdi, rcx
0x180035098  lea     r8, aSoftwareClasse_2; "Software\\Classes\\Clsid\\"
0x18003509f  lea     rcx, [rsp+0D8h+var_B8]; unsigned __int16 *
0x1800350a4  mov     edx, 4Dh ; 'M'; unsigned __int64
0x1800350a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800350ae  lea     r14, WPP_GLOBAL_Control
0x1800350b5  mov     ebx, eax
0x1800350b7  test    eax, eax
0x1800350b9  jns     short loc_1800350F9
0x1800350bb  mov     edx, eax; int
0x1800350bd  lea     rcx, qword_18006A9C0; this
0x1800350c4  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800350c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350d0  cmp     rcx, r14
0x1800350d3  jz      short loc_1800350F9
0x1800350d5  test    byte ptr [rcx+1Ch], 1
0x1800350d9  jz      short loc_1800350F9
0x1800350db  cmp     byte ptr [rcx+19h], 2
0x1800350df  jb      short loc_1800350F9
0x1800350e1  mov     rcx, [rcx+10h]
0x1800350e5  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x1800350ec  mov     edx, 21h ; '!'
0x1800350f1  mov     r9d, ebx
0x1800350f4  call    WPP_SF_D
0x1800350f9  mov     r8d, 27h ; '''; cchMax
0x1800350ff  lea     rdx, [rsp+0D8h+sz]; lpsz
0x180035104  mov     rcx, rdi; rguid
0x180035107  call    cs:__imp_StringFromGUID2
0x18003510d  test    eax, eax
0x18003510f  jnz     loc_1800351A8
0x180035115  call    cs:__imp_GetLastError
0x18003511b  mov     ebx, 80070000h
0x180035120  test    eax, eax
0x180035122  jle     short loc_18003512B
0x180035124  movzx   eax, ax
0x180035127  or      eax, ebx
0x180035129  test    eax, eax
0x18003512b  jns     short loc_18003514A
0x18003512d  call    cs:__imp_GetLastError
0x180035133  test    eax, eax
0x180035135  jle     short loc_18003513C
0x180035137  movzx   eax, ax
0x18003513a  or      eax, ebx
0x18003513c  mov     edx, eax; int
0x18003513e  lea     rcx, qword_18006A9C0; this
0x180035145  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003514a  mov     rax, cs:WPP_GLOBAL_Control
0x180035151  cmp     rax, r14
0x180035154  jz      short loc_180035190
0x180035156  test    byte ptr [rax+1Ch], 1
0x18003515a  jz      short loc_180035190
0x18003515c  cmp     byte ptr [rax+19h], 2
0x180035160  jb      short loc_180035190
0x180035162  call    cs:__imp_GetLastError
0x180035168  test    eax, eax
0x18003516a  jle     short loc_180035171
0x18003516c  movzx   eax, ax
0x18003516f  or      eax, ebx
0x180035171  mov     edx, 22h ; '"'
0x180035176  mov     rcx, cs:WPP_GLOBAL_Control
0x18003517d  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180035184  mov     r9d, eax
0x180035187  mov     rcx, [rcx+10h]
0x18003518b  call    WPP_SF_D
0x180035190  call    cs:__imp_GetLastError
0x180035196  test    eax, eax
0x180035198  jle     loc_1800352BD
0x18003519e  movzx   eax, ax
0x1800351a1  or      eax, ebx
0x1800351a3  jmp     loc_1800352BD
0x1800351a8  mov     rbx, 0FFFFFFFF80000002h
0x1800351af  lea     rdx, [rsp+0D8h+var_B8]
0x1800351b4  mov     rcx, rbx
0x1800351b7  call    DLRegDeleteKeyW
0x1800351bc  test    eax, eax
0x1800351be  jz      short loc_180035226
0x1800351c0  call    cs:__imp_GetLastError
0x1800351c6  mov     ebx, 80070000h
0x1800351cb  test    eax, eax
0x1800351cd  jle     short loc_1800351D6
0x1800351cf  movzx   eax, ax
0x1800351d2  or      eax, ebx
0x1800351d4  test    eax, eax
0x1800351d6  jns     short loc_1800351F5
0x1800351d8  call    cs:__imp_GetLastError
0x1800351de  test    eax, eax
0x1800351e0  jle     short loc_1800351E7
0x1800351e2  movzx   eax, ax
0x1800351e5  or      eax, ebx
0x1800351e7  mov     edx, eax; int
0x1800351e9  lea     rcx, qword_18006A9C0; this
0x1800351f0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800351f5  mov     rax, cs:WPP_GLOBAL_Control
0x1800351fc  cmp     rax, r14
0x1800351ff  jz      short loc_180035190
0x180035201  test    byte ptr [rax+1Ch], 1
0x180035205  jz      short loc_180035190
0x180035207  cmp     byte ptr [rax+19h], 2
0x18003520b  jb      short loc_180035190
0x18003520d  call    cs:__imp_GetLastError
0x180035213  test    eax, eax
0x180035215  jle     short loc_18003521C
0x180035217  movzx   eax, ax
0x18003521a  or      eax, ebx
0x18003521c  mov     edx, 23h ; '#'
0x180035221  jmp     loc_180035176
0x180035226  mov     eax, 70h ; 'p'
0x18003522b  mov     [rsp+0D8h+var_96], 700041h
0x180035233  lea     rdx, [rsp+0D8h+var_B8]
0x180035238  mov     [rsp+0D8h+var_92], ax
0x18003523d  mov     rcx, rbx
0x180035240  call    DLRegDeleteKeyW
0x180035245  test    eax, eax
0x180035247  jz      short loc_1800352BB
0x180035249  call    cs:__imp_GetLastError
0x18003524f  mov     ebx, 80070000h
0x180035254  test    eax, eax
0x180035256  jle     short loc_18003525F
0x180035258  movzx   eax, ax
0x18003525b  or      eax, ebx
0x18003525d  test    eax, eax
0x18003525f  jns     short loc_18003527E
0x180035261  call    cs:__imp_GetLastError
0x180035267  test    eax, eax
0x180035269  jle     short loc_180035270
0x18003526b  movzx   eax, ax
0x18003526e  or      eax, ebx
0x180035270  mov     edx, eax; int
0x180035272  lea     rcx, qword_18006A9C0; this
0x180035279  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003527e  mov     rax, cs:WPP_GLOBAL_Control
0x180035285  cmp     rax, r14
0x180035288  jz      loc_180035190
0x18003528e  test    byte ptr [rax+1Ch], 1
0x180035292  jz      loc_180035190
0x180035298  cmp     byte ptr [rax+19h], 2
0x18003529c  jb      loc_180035190
0x1800352a2  call    cs:__imp_GetLastError
0x1800352a8  test    eax, eax
0x1800352aa  jle     short loc_1800352B1
0x1800352ac  movzx   eax, ax
0x1800352af  or      eax, ebx
0x1800352b1  mov     edx, 24h ; '$'
0x1800352b6  jmp     loc_180035176
0x1800352bb  xor     eax, eax
0x1800352bd  mov     rcx, [rsp+0D8h+var_18]
0x1800352c5  xor     rcx, rsp; StackCookie
0x1800352c8  call    __security_check_cookie
0x1800352cd  lea     r11, [rsp+0D8h+var_8]
0x1800352d5  mov     rbx, [r11+18h]
0x1800352d9  mov     rdi, [r11+20h]
0x1800352dd  mov     rsp, r11
0x1800352e0  pop     r14
0x1800352e2  retn
```
