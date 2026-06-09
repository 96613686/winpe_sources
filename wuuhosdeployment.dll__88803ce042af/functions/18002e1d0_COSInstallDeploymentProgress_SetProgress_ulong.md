# COSInstallDeploymentProgress::SetProgress(ulong)

- ea: `0x18002e1d0`
- end: `0x18002e41c`
- name: `?SetProgress@COSInstallDeploymentProgress@@UEAAJK@Z`
- size: `588`
- prototype: `__int64 __fastcall(COSInstallDeploymentProgress *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18002e1d0`
- `0x18002e424`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## string_xrefs

- `0x18002e23a`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstallDeploymentProgress.cpp`
- `0x18002e3fd`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstallDeploymentProgress.cpp`
- `0x18002e343`: `Failed to report progress to agent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COSInstallDeploymentProgress::SetProgress(COSInstallDeploymentProgress *this, unsigned int a2)
{
  int IsMergedUpdate; // eax
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int128 v11; // xmm1
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // edi
  __int64 v17; // r9
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-E0h]
  bool v20; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+50h] [rbp-B0h]
  int *v23; // [rsp+60h] [rbp-A0h]
  char v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  __int128 v26; // [rsp+78h] [rbp-88h] BYREF
  int v27; // [rsp+88h] [rbp-78h]
  _DWORD v28[56]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v25 = 0;
  memset(v28, 0, 0xD8u);
  v28[0] = 1;
  v20 = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstallDeploymentProgress.cpp",
      (const char *)0x80004003LL,
      v19);
    return 2147500035LL;
  }
  v28[7] = 100;
  if ( a2 > 0x64 )
    a2 = 99;
  v28[6] = a2;
  v23 = &v25;
  v24 = 1;
  IsMergedUpdate = COSInstallDeploymentProgress::IsMergedUpdate(this, &v20);
  v6 = IsMergedUpdate;
  v25 = IsMergedUpdate;
  if ( IsMergedUpdate < 0 )
  {
    v7 = 100;
LABEL_22:
    v17 = (unsigned int)IsMergedUpdate;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstallDeploymentProgress.cpp",
      (const char *)v17,
      v19);
    v16 = v6;
    v6 = v25;
    goto LABEL_14;
  }
  if ( v20 )
  {
    v8 = 0;
    v9 = *((_QWORD *)this + 7);
    if ( *(_DWORD *)(v9 + 20) )
    {
      while ( 1 )
      {
        v26 = 0;
        v27 = 0;
        if ( (unsigned int)v8 >= *(_DWORD *)(v9 + 20) )
          break;
        v10 = *(_QWORD *)(v9 + 8);
        v11 = *(_OWORD *)(v10 + 20 * v8);
        v12 = *(_DWORD *)(v10 + 20 * v8 + 16);
        v25 = 0;
        v13 = *((_QWORD *)this + 8);
        if ( (unsigned int)v8 >= *(_DWORD *)(v13 + 20) )
        {
          v6 = -2145124345;
          v25 = -2145124345;
          v17 = 2149842951LL;
          v7 = 114;
          goto LABEL_23;
        }
        v14 = *(_QWORD *)(v13 + 8);
        v26 = *(_OWORD *)(v14 + 20 * v8);
        v27 = *(_DWORD *)(v14 + 20 * v8 + 16);
        v15 = *((_QWORD *)this + 9);
        v21 = v11;
        v22 = v12;
        IsMergedUpdate = (*(__int64 (__fastcall **)(__int64, __int128 *, _DWORD *, __int128 *))(*(_QWORD *)v15 + 24LL))(
                           v15,
                           &v21,
                           v28,
                           &v26);
        v6 = IsMergedUpdate;
        v25 = IsMergedUpdate;
        if ( IsMergedUpdate < 0 )
        {
          v7 = 117;
          goto LABEL_22;
        }
        v8 = (unsigned int)(v8 + 1);
        v9 = *((_QWORD *)this + 7);
        if ( (unsigned int)v8 >= *(_DWORD *)(v9 + 20) )
          goto LABEL_13;
      }
      v6 = -2145124345;
      v25 = -2145124345;
      v17 = 2149842951LL;
      v7 = 111;
      goto LABEL_23;
    }
  }
  else
  {
    v18 = *((_QWORD *)this + 9);
    v21 = *((_OWORD *)this + 1);
    v22 = *((_DWORD *)this + 8);
    IsMergedUpdate = (*(__int64 (__fastcall **)(__int64, __int128 *, _DWORD *, char *))(*(_QWORD *)v18 + 24LL))(
                       v18,
                       &v21,
                       v28,
                       (char *)this + 36);
    v6 = IsMergedUpdate;
    v25 = IsMergedUpdate;
    if ( IsMergedUpdate < 0 )
    {
      v7 = 123;
      goto LABEL_22;
    }
  }
LABEL_13:
  v16 = 0;
LABEL_14:
  if ( v6 < 0 )
    WUTrace(0, 0, 4096, 3);
  return v16;
}

```

## disassembly

```asm
0x18002e1d0  mov     [rsp-8+arg_8], rbx
0x18002e1d5  mov     [rsp-8+arg_10], rsi
0x18002e1da  mov     [rsp-8+arg_18], rdi
0x18002e1df  push    rbp
0x18002e1e0  lea     rbp, [rsp-80h]
0x18002e1e5  sub     rsp, 180h
0x18002e1ec  mov     rax, cs:__security_cookie
0x18002e1f3  xor     rax, rsp
0x18002e1f6  mov     [rbp+80h+var_10], rax
0x18002e1fa  mov     ebx, edx
0x18002e1fc  mov     rdi, rcx
0x18002e1ff  mov     [rsp+180h+var_110], 0
0x18002e207  xor     edx, edx; Val
0x18002e209  mov     r8d, 0D8h; Size
0x18002e20f  lea     rcx, [rbp+80h+var_F0]; void *
0x18002e213  call    memset
0x18002e218  mov     [rbp+80h+var_F0], 1
0x18002e21f  mov     [rsp+180h+var_150], 0
0x18002e224  cmp     qword ptr [rdi+48h], 0
0x18002e229  jnz     short loc_18002E252
0x18002e22b  mov     rcx, [rbp+88h]; this
0x18002e232  mov     ebx, 80004003h
0x18002e237  mov     r9d, ebx; char *
0x18002e23a  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002e241  mov     edx, 45h ; 'E'; void *
0x18002e246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e24b  mov     eax, ebx
0x18002e24d  jmp     loc_18002E368
0x18002e252  mov     esi, 64h ; 'd'
0x18002e257  mov     [rbp+80h+var_D4], esi
0x18002e25a  lea     eax, [rsi-1]
0x18002e25d  cmp     ebx, esi
0x18002e25f  cmova   ebx, eax
0x18002e262  mov     [rbp+80h+var_D8], ebx
0x18002e265  lea     rax, [rsp+180h+var_110]
0x18002e26a  mov     [rsp+180h+var_120], rax
0x18002e26f  mov     [rsp+180h+var_118], 1
0x18002e274  lea     rdx, [rsp+180h+var_150]; bool *
0x18002e279  mov     rcx, rdi; this
0x18002e27c  call    ?IsMergedUpdate@COSInstallDeploymentProgress@@AEAAJPEA_N@Z; COSInstallDeploymentProgress::IsMergedUpdate(bool *)
0x18002e281  mov     ebx, eax
0x18002e283  mov     [rsp+180h+var_110], eax
0x18002e287  test    eax, eax
0x18002e289  jns     short loc_18002E292
0x18002e28b  mov     edx, esi
0x18002e28d  jmp     loc_18002E3FA
0x18002e292  cmp     [rsp+180h+var_150], 0
0x18002e297  jz      loc_18002E3BA
0x18002e29d  xor     esi, esi
0x18002e29f  mov     rcx, [rdi+38h]
0x18002e2a3  cmp     [rcx+14h], esi
0x18002e2a6  jbe     loc_18002E33D
0x18002e2ac  xorps   xmm0, xmm0
0x18002e2af  xor     eax, eax
0x18002e2b1  movups  [rsp+180h+var_108], xmm0
0x18002e2b6  mov     [rbp+80h+var_F8], eax
0x18002e2b9  cmp     esi, [rcx+14h]
0x18002e2bc  jnb     loc_18002E3A7
0x18002e2c2  lea     rdx, [rsi+rsi*4]
0x18002e2c6  mov     rax, [rcx+8]
0x18002e2ca  movups  xmm1, xmmword ptr [rax+rdx*4]
0x18002e2ce  mov     r8d, [rax+rdx*4+10h]
0x18002e2d3  mov     [rsp+180h+var_110], 0
0x18002e2db  mov     rax, [rdi+40h]
0x18002e2df  cmp     esi, [rax+14h]
0x18002e2e2  jnb     loc_18002E394
0x18002e2e8  mov     rax, [rax+8]
0x18002e2ec  movups  xmm0, xmmword ptr [rax+rdx*4]
0x18002e2f0  movups  [rsp+180h+var_108], xmm0
0x18002e2f5  mov     eax, [rax+rdx*4+10h]
0x18002e2f9  mov     [rbp+80h+var_F8], eax
0x18002e2fc  mov     rcx, [rdi+48h]
0x18002e300  movaps  [rsp+180h+var_140], xmm1
0x18002e305  mov     [rsp+180h+var_130], r8d
0x18002e30a  mov     rax, [rcx]
0x18002e30d  lea     r9, [rsp+180h+var_108]
0x18002e312  lea     r8, [rbp+80h+var_F0]
0x18002e316  lea     rdx, [rsp+180h+var_140]
0x18002e31b  mov     rax, [rax+18h]
0x18002e31f  call    _guard_dispatch_icall
0x18002e324  mov     ebx, eax
0x18002e326  mov     [rsp+180h+var_110], eax
0x18002e32a  test    eax, eax
0x18002e32c  js      short loc_18002E38D
0x18002e32e  inc     esi
0x18002e330  mov     rcx, [rdi+38h]
0x18002e334  cmp     esi, [rcx+14h]
0x18002e337  jb      loc_18002E2AC
0x18002e33d  xor     edi, edi
0x18002e33f  test    ebx, ebx
0x18002e341  jns     short loc_18002E366
0x18002e343  lea     rax, aFailedToReport; "Failed to report progress to agent"
0x18002e34a  mov     [rsp+180h+var_158], rax
0x18002e34f  mov     [rsp+180h+var_160], ebx
0x18002e353  xor     edx, edx
0x18002e355  xor     ecx, ecx
0x18002e357  lea     r9d, [rdx+3]
0x18002e35b  mov     r8d, 1000h
0x18002e361  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e366  mov     eax, edi
0x18002e368  mov     rcx, [rbp+80h+var_10]
0x18002e36c  xor     rcx, rsp; StackCookie
0x18002e36f  call    __security_check_cookie
0x18002e374  lea     r11, [rsp+180h+var_s0]
0x18002e37c  mov     rbx, [r11+18h]
0x18002e380  mov     rsi, [r11+20h]
0x18002e384  mov     rdi, [r11+28h]
0x18002e388  mov     rsp, r11
0x18002e38b  pop     rbp
0x18002e38c  retn
0x18002e38d  mov     edx, 75h ; 'u'
0x18002e392  jmp     short loc_18002E3FA
0x18002e394  mov     ebx, 80240007h
0x18002e399  mov     [rsp+180h+var_110], ebx
0x18002e39d  mov     r9d, ebx
0x18002e3a0  mov     edx, 72h ; 'r'
0x18002e3a5  jmp     short loc_18002E3FD
0x18002e3a7  mov     ebx, 80240007h
0x18002e3ac  mov     [rsp+180h+var_110], ebx
0x18002e3b0  mov     r9d, ebx
0x18002e3b3  mov     edx, 6Fh ; 'o'
0x18002e3b8  jmp     short loc_18002E3FD
0x18002e3ba  mov     rcx, [rdi+48h]
0x18002e3be  movups  xmm0, xmmword ptr [rdi+10h]
0x18002e3c2  movaps  [rsp+180h+var_140], xmm0
0x18002e3c7  mov     eax, [rdi+20h]
0x18002e3ca  mov     [rsp+180h+var_130], eax
0x18002e3ce  lea     r9, [rdi+24h]
0x18002e3d2  mov     rax, [rcx]
0x18002e3d5  lea     r8, [rbp+80h+var_F0]
0x18002e3d9  lea     rdx, [rsp+180h+var_140]
0x18002e3de  mov     rax, [rax+18h]
0x18002e3e2  call    _guard_dispatch_icall
0x18002e3e7  mov     ebx, eax
0x18002e3e9  mov     [rsp+180h+var_110], eax
0x18002e3ed  test    eax, eax
0x18002e3ef  jns     loc_18002E33D
0x18002e3f5  mov     edx, 7Bh ; '{'; void *
0x18002e3fa  mov     r9d, eax; char *
0x18002e3fd  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002e404  mov     rcx, [rbp+88h]; this
0x18002e40b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e410  mov     edi, ebx
0x18002e412  mov     ebx, [rsp+180h+var_110]
0x18002e416  jmp     loc_18002E33F
```
