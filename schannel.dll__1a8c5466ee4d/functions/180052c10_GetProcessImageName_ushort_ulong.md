# GetProcessImageName(ushort *,ulong)

- ea: `0x180052c10`
- end: `0x180053080`
- name: `?GetProcessImageName@@YAKPEAGK@Z`
- size: `1136`
- prototype: `unsigned int __fastcall(unsigned __int16 *, DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callers

- `0x18002b800`
- `0x18006fb9c`

## callees

- `0x180021da8`
- `0x180043e9c`
- `0x180052c10`
- `0x180057c8c`
- `0x180057cb4`
- `0x1800597b0`
- `0x18005a10c`
- `0x18005a118`
- `0x18005a154`
- `0x18005a160`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052e7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052e7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053026`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052c81`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052c81`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180052d0c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180052d0c`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180052e50`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180052ea4`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180052e50`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180052ea4`

## pseudocode

```c
__int64 __fastcall GetProcessImageName(unsigned __int16 *a1, DWORD dwProcessId)
{
  unsigned __int16 *v3; // r15
  HANDLE v5; // r12
  DWORD LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  DWORD v9; // eax
  errno_t v10; // eax
  CCipherMill *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rsi
  void *v14; // rcx
  int TagInformation; // eax
  void *v16; // r14
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  wchar_t *v20; // rcx
  unsigned __int16 *v21; // rcx
  CCipherMill *v22; // rcx
  DWORD dwSize; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp-A0h]
  _DWORD v26[6]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t String1[2]; // [rsp+80h] [rbp-80h] BYREF
  char v28[508]; // [rsp+84h] [rbp-7Ch] BYREF
  int v29; // [rsp+280h] [rbp+180h] BYREF
  char v30[524]; // [rsp+284h] [rbp+184h] BYREF
  WCHAR ExeName[2]; // [rsp+490h] [rbp+390h] BYREF
  char v32[524]; // [rsp+494h] [rbp+394h] BYREF

  v3 = a1;
  if ( !a1 )
    return 87;
  if ( !dwProcessId )
  {
    o_wcsncpy_s_0(a1, 260, L"<UNKNOWN>", -1);
    return 0;
  }
  v5 = OpenProcess(0x1000u, 0, dwProcessId);
  if ( !v5 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids, LastError);
    return v7;
  }
  *(_DWORD *)ExeName = 0;
  memset_0(v32, 0, 0x204u);
  v8 = 260;
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(v5, 0, ExeName, &dwSize) )
  {
    v9 = GetLastError();
    v7 = v9;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids, v9);
    goto LABEL_56;
  }
  *(_DWORD *)String1 = 0;
  memset_0(v28, 0, sizeof(v28));
  v10 = wsplitpath_s(ExeName, 0, 0, 0, 0, String1, 0x100u, 0, 0);
  if ( !v10 )
  {
    v29 = 0;
    memset_0(v30, 0, 0x204u);
    v13 = -1;
    if ( wcsnicmp(String1, L"svchost", 7u) )
      goto LABEL_35;
    v26[0] = dwProcessId;
    memset(&v26[1], 0, 20);
    v26[1] = NtCurrentTeb()->SubProcessTag;
    if ( !(unsigned int)I_QueryTagInformation(0, 1, v26) )
    {
      if ( !*(_QWORD *)&v26[4] )
        goto LABEL_35;
      o_wcsncpy_s_0(&v29, 260, *(_QWORD *)&v26[4], -1);
      v14 = *(void **)&v26[4];
      goto LABEL_23;
    }
    v24[0] = dwProcessId;
    v24[1] = 0;
    v25 = 0;
    TagInformation = I_QueryTagInformation(0, 3, v24);
    if ( TagInformation )
    {
      if ( TagInformation < 0
        && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids,
          (unsigned int)TagInformation);
      }
    }
    else
    {
      v16 = v25;
      if ( v25 )
      {
        if ( *(_DWORD *)v25 == 1 )
        {
          v17 = v25[1];
          if ( *(_DWORD *)v17 == 1 )
          {
            v18 = *(_QWORD *)(v17 + 8);
            if ( v18 )
              o_wcsncpy_s_0(&v29, 260, v18, -1);
          }
        }
        v14 = v16;
LABEL_23:
        LocalFree(v14);
        goto LABEL_35;
      }
    }
    do
LABEL_35:
      ++v13;
    while ( *(_WORD *)&v30[2 * v13 - 4] );
    if ( v13 )
    {
      v10 = StringCchPrintfW(v3, 0x104u, L"%ls[%ls]", String1, &v29);
    }
    else
    {
      v19 = 2147483646;
      v20 = String1;
      do
      {
        if ( !v19 )
          break;
        if ( !*v20 )
          break;
        *v3++ = *v20++;
        --v19;
        --v8;
      }
      while ( v8 );
      v21 = v3 - 1;
      if ( v8 )
        v21 = v3;
      v10 = v8 == 0 ? 0x8007007A : 0;
      *v21 = 0;
    }
    if ( v10 == -2147024774 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids);
          v22 = WPP_GLOBAL_Control;
        }
        if ( v22 != (CCipherMill *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v22 + 28) & 2) != 0 )
          {
            WPP_SF_S(*((_QWORD *)v22 + 2), 15, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids, String1);
            v22 = WPP_GLOBAL_Control;
          }
          if ( v22 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 )
            WPP_SF_S(*((_QWORD *)v22 + 2), 16, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids, &v29);
        }
      }
    }
    else if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v12 = 17;
      goto LABEL_17;
    }
    v7 = 0;
    goto LABEL_56;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_18;
  v12 = 12;
LABEL_17:
  WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids, (unsigned int)v10);
LABEL_18:
  v7 = 1359;
LABEL_56:
  CloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x180052c10  mov     [rsp-8+arg_10], rbx
0x180052c15  push    rbp
0x180052c16  push    rsi
0x180052c17  push    rdi
0x180052c18  push    r12
0x180052c1a  push    r13
0x180052c1c  push    r14
0x180052c1e  push    r15
0x180052c20  lea     rbp, [rsp-5B0h]
0x180052c28  sub     rsp, 6B0h
0x180052c2f  mov     rax, cs:__security_cookie
0x180052c36  xor     rax, rsp
0x180052c39  mov     [rbp+5E0h+var_40], rax
0x180052c40  xor     r13d, r13d
0x180052c43  mov     r14d, edx
0x180052c46  mov     r15, rcx
0x180052c49  test    rcx, rcx
0x180052c4c  jnz     short loc_180052C56
0x180052c4e  lea     eax, [rcx+57h]
0x180052c51  jmp     loc_18005302E
0x180052c56  test    r14d, r14d
0x180052c59  jnz     short loc_180052C77
0x180052c5b  or      r9, 0FFFFFFFFFFFFFFFFh
0x180052c5f  lea     r8, aUnknown_0; "<UNKNOWN>"
0x180052c66  mov     edx, 104h
0x180052c6b  call    _o_wcsncpy_s_0
0x180052c70  xor     eax, eax
0x180052c72  jmp     loc_18005302E
0x180052c77  mov     r8d, r14d; dwProcessId
0x180052c7a  xor     edx, edx; bInheritHandle
0x180052c7c  mov     ecx, 1000h; dwDesiredAccess
0x180052c81  call    cs:__imp_OpenProcess
0x180052c87  mov     r12, rax
0x180052c8a  test    rax, rax
0x180052c8d  jnz     short loc_180052CD5
0x180052c8f  call    cs:__imp_GetLastError
0x180052c95  mov     ebx, eax
0x180052c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c9e  lea     rdi, WPP_GLOBAL_Control
0x180052ca5  cmp     rcx, rdi
0x180052ca8  jz      loc_18005302C
0x180052cae  test    byte ptr [rcx+1Ch], 2
0x180052cb2  jz      loc_18005302C
0x180052cb8  mov     rcx, [rcx+10h]
0x180052cbc  lea     edx, [r12+0Ah]
0x180052cc1  mov     r9d, eax
0x180052cc4  lea     r8, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids
0x180052ccb  call    WPP_SF_d
0x180052cd0  jmp     loc_18005302C
0x180052cd5  mov     edi, 204h
0x180052cda  mov     dword ptr [rbp+5E0h+ExeName], r13d
0x180052ce1  mov     r8d, edi; Size
0x180052ce4  lea     rcx, [rbp+5E0h+var_24C]; void *
0x180052ceb  xor     edx, edx; Val
0x180052ced  call    memset_0
0x180052cf2  mov     ebx, 104h
0x180052cf7  lea     r9, [rsp+6E0h+dwSize]; lpdwSize
0x180052cfc  lea     r8, [rbp+5E0h+ExeName]; lpExeName
0x180052d03  mov     [rsp+6E0h+dwSize], ebx
0x180052d07  xor     edx, edx; dwFlags
0x180052d09  mov     rcx, r12; hProcess
0x180052d0c  call    cs:__imp_QueryFullProcessImageNameW
0x180052d12  test    eax, eax
0x180052d14  jnz     short loc_180052D5C
0x180052d16  call    cs:__imp_GetLastError
0x180052d1c  mov     ebx, eax
0x180052d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d25  lea     rdi, WPP_GLOBAL_Control
0x180052d2c  cmp     rcx, rdi
0x180052d2f  jz      loc_180053023
0x180052d35  test    byte ptr [rcx+1Ch], 2
0x180052d39  jz      loc_180053023
0x180052d3f  mov     rcx, [rcx+10h]
0x180052d43  lea     r8, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids
0x180052d4a  mov     edx, 0Bh
0x180052d4f  mov     r9d, eax
0x180052d52  call    WPP_SF_d
0x180052d57  jmp     loc_180053023
0x180052d5c  xor     edx, edx; Val
0x180052d5e  mov     dword ptr [rbp+5E0h+String1], r13d
0x180052d62  mov     r8d, 1FCh; Size
0x180052d68  lea     rcx, [rbp+5E0h+var_65C]; void *
0x180052d6c  call    memset_0
0x180052d71  mov     [rsp+6E0h+ExtCount], r13; ExtCount
0x180052d76  lea     rax, [rbp+5E0h+String1]
0x180052d7a  mov     [rsp+6E0h+Ext], r13; Ext
0x180052d7f  lea     rcx, [rbp+5E0h+ExeName]; FullPath
0x180052d86  mov     [rsp+6E0h+FilenameCount], 100h; FilenameCount
0x180052d8f  xor     r9d, r9d; Dir
0x180052d92  mov     [rsp+6E0h+Filename], rax; Filename
0x180052d97  xor     r8d, r8d; DriveCount
0x180052d9a  xor     edx, edx; Drive
0x180052d9c  mov     [rsp+6E0h+DirCount], r13; DirCount
0x180052da1  call    _wsplitpath_s
0x180052da6  test    eax, eax
0x180052da8  jz      short loc_180052DE5
0x180052daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180052db1  lea     rdi, WPP_GLOBAL_Control
0x180052db8  cmp     rcx, rdi
0x180052dbb  jz      short loc_180052DDB
0x180052dbd  test    byte ptr [rcx+1Ch], 2
0x180052dc1  jz      short loc_180052DDB
0x180052dc3  mov     edx, 0Ch
0x180052dc8  mov     rcx, [rcx+10h]
0x180052dcc  lea     r8, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids
0x180052dd3  mov     r9d, eax
0x180052dd6  call    WPP_SF_d
0x180052ddb  mov     ebx, 54Fh
0x180052de0  jmp     loc_180053023
0x180052de5  mov     r8, rdi; Size
0x180052de8  mov     [rbp+5E0h+var_460], r13d
0x180052def  xor     edx, edx; Val
0x180052df1  lea     rcx, [rbp+5E0h+var_45C]; void *
0x180052df8  call    memset_0
0x180052dfd  mov     r8d, 7; MaxCount
0x180052e03  lea     rdx, aSvchost; "svchost"
0x180052e0a  lea     rcx, [rbp+5E0h+String1]; String1
0x180052e0e  call    _wcsnicmp
0x180052e13  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180052e17  lea     rdi, WPP_GLOBAL_Control
0x180052e1e  test    eax, eax
0x180052e20  jnz     loc_180052F13
0x180052e26  xor     eax, eax
0x180052e28  mov     [rsp+6E0h+var_678], r14d
0x180052e2d  xorps   xmm0, xmm0
0x180052e30  mov     [rsp+6E0h+var_664], eax
0x180052e34  movups  xmmword ptr [rsp+6E0h+hMem], xmm0
0x180052e39  mov     rax, gs:1720h
0x180052e42  lea     r8, [rsp+6E0h+var_678]
0x180052e47  lea     edx, [rsi+2]
0x180052e4a  mov     dword ptr [rsp+6E0h+hMem], eax
0x180052e4e  xor     ecx, ecx
0x180052e50  call    cs:__imp_I_QueryTagInformation
0x180052e56  test    eax, eax
0x180052e58  jnz     short loc_180052E8A
0x180052e5a  mov     r8, [rsp+6E0h+hMem+0Ch]
0x180052e5f  test    r8, r8
0x180052e62  jz      loc_180052F13
0x180052e68  mov     r9, rsi
0x180052e6b  lea     rcx, [rbp+5E0h+var_460]
0x180052e72  mov     rdx, rbx
0x180052e75  call    _o_wcsncpy_s_0
0x180052e7a  mov     rcx, [rsp+6E0h+hMem+0Ch]; hMem
0x180052e7f  call    cs:__imp_LocalFree
0x180052e85  jmp     loc_180052F13
0x180052e8a  xor     eax, eax
0x180052e8c  mov     [rsp+6E0h+var_688], r14d
0x180052e91  lea     r8, [rsp+6E0h+var_688]
0x180052e96  mov     [rsp+6E0h+var_684], eax
0x180052e9a  xor     ecx, ecx
0x180052e9c  mov     [rsp+6E0h+var_680], rax
0x180052ea1  lea     edx, [rax+3]
0x180052ea4  call    cs:__imp_I_QueryTagInformation
0x180052eaa  test    eax, eax
0x180052eac  jnz     short loc_180052EE7
0x180052eae  mov     r14, [rsp+6E0h+var_680]
0x180052eb3  test    r14, r14
0x180052eb6  jz      short loc_180052F13
0x180052eb8  cmp     dword ptr [r14], 1
0x180052ebc  jnz     short loc_180052EE2
0x180052ebe  mov     rax, [r14+8]
0x180052ec2  cmp     dword ptr [rax], 1
0x180052ec5  jnz     short loc_180052EE2
0x180052ec7  mov     r8, [rax+8]
0x180052ecb  test    r8, r8
0x180052ece  jz      short loc_180052EE2
0x180052ed0  mov     r9, rsi
0x180052ed3  lea     rcx, [rbp+5E0h+var_460]
0x180052eda  mov     rdx, rbx
0x180052edd  call    _o_wcsncpy_s_0
0x180052ee2  mov     rcx, r14
0x180052ee5  jmp     short loc_180052E7F
0x180052ee7  jns     short loc_180052F13
0x180052ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ef0  cmp     rcx, rdi
0x180052ef3  jz      short loc_180052F13
0x180052ef5  test    byte ptr [rcx+1Ch], 2
0x180052ef9  jz      short loc_180052F13
0x180052efb  mov     rcx, [rcx+10h]
0x180052eff  lea     r8, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids
0x180052f06  mov     edx, 0Dh
0x180052f0b  mov     r9d, eax
0x180052f0e  call    WPP_SF_d
0x180052f13  lea     rax, [rbp+5E0h+var_460]
0x180052f1a  inc     rsi
0x180052f1d  cmp     [rax+rsi*2], r13w
0x180052f22  jnz     short loc_180052F1A
0x180052f24  mov     r14d, 8007007Ah
0x180052f2a  test    rsi, rsi
0x180052f2d  jz      short loc_180052F53
0x180052f2f  lea     rax, [rbp+5E0h+var_460]
0x180052f36  mov     rdx, rbx; unsigned __int64
0x180052f39  lea     r9, [rbp+5E0h+String1]
0x180052f3d  mov     [rsp+6E0h+DirCount], rax
0x180052f42  lea     r8, aLsLs; "%ls[%ls]"
0x180052f49  mov     rcx, r15; unsigned __int16 *
0x180052f4c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052f51  jmp     short loc_180052F97
0x180052f53  mov     eax, 7FFFFFFEh
0x180052f58  lea     rcx, [rbp+5E0h+String1]
0x180052f5c  test    rax, rax
0x180052f5f  jz      short loc_180052F7E
0x180052f61  movzx   edx, word ptr [rcx]
0x180052f64  test    dx, dx
0x180052f67  jz      short loc_180052F7E
0x180052f69  mov     [r15], dx
0x180052f6d  add     rcx, 2
0x180052f71  add     r15, 2
0x180052f75  dec     rax
0x180052f78  sub     rbx, 1
0x180052f7c  jnz     short loc_180052F5C
0x180052f7e  test    rbx, rbx
0x180052f81  lea     rcx, [r15-2]
0x180052f85  cmovnz  rcx, r15
0x180052f89  neg     rbx
0x180052f8c  sbb     eax, eax
0x180052f8e  not     eax
0x180052f90  and     eax, r14d
0x180052f93  mov     [rcx], r13w
0x180052f97  cmp     eax, r14d
0x180052f9a  jnz     loc_180053058
0x180052fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180052fa7  cmp     rcx, rdi
0x180052faa  jz      short loc_180053020
0x180052fac  test    byte ptr [rcx+1Ch], 2
0x180052fb0  jz      short loc_180052FCE
0x180052fb2  mov     rcx, [rcx+10h]
0x180052fb6  lea     r8, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids
0x180052fbd  mov     edx, 0Eh
0x180052fc2  call    WPP_SF_
0x180052fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180052fce  cmp     rcx, rdi
0x180052fd1  jz      short loc_180053020
0x180052fd3  test    byte ptr [rcx+1Ch], 2
0x180052fd7  jz      short loc_180052FF9
0x180052fd9  mov     rcx, [rcx+10h]
0x180052fdd  lea     r9, [rbp+5E0h+String1]
0x180052fe1  mov     edx, 0Fh
0x180052fe6  lea     r8, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids
0x180052fed  call    WPP_SF_S
0x180052ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ff9  cmp     rcx, rdi
0x180052ffc  jz      short loc_180053020
0x180052ffe  test    byte ptr [rcx+1Ch], 2
0x180053002  jz      short loc_180053020
0x180053004  mov     rcx, [rcx+10h]
0x180053008  lea     r9, [rbp+5E0h+var_460]
0x18005300f  mov     edx, 10h
0x180053014  lea     r8, WPP_9aabd5a85b1936ba1b439cc6fb98167f_Traceguids
0x18005301b  call    WPP_SF_S
0x180053020  mov     ebx, r13d
0x180053023  mov     rcx, r12; hObject
0x180053026  call    cs:__imp_CloseHandle
0x18005302c  mov     eax, ebx
0x18005302e  mov     rcx, [rbp+5E0h+var_40]
0x180053035  xor     rcx, rsp; StackCookie
0x180053038  call    __security_check_cookie
0x18005303d  mov     rbx, [rsp+6E0h+arg_10]
0x180053045  add     rsp, 6B0h
0x18005304c  pop     r15
0x18005304e  pop     r14
0x180053050  pop     r13
0x180053052  pop     r12
0x180053054  pop     rdi
0x180053055  pop     rsi
0x180053056  pop     rbp
0x180053057  retn
0x180053058  test    eax, eax
0x18005305a  jns     short loc_180053020
0x18005305c  mov     rcx, cs:WPP_GLOBAL_Control
0x180053063  cmp     rcx, rdi
0x180053066  jz      loc_180052DDB
0x18005306c  test    byte ptr [rcx+1Ch], 1
0x180053070  jz      loc_180052DDB
0x180053076  mov     edx, 11h
0x18005307b  jmp     loc_180052DC8
```
