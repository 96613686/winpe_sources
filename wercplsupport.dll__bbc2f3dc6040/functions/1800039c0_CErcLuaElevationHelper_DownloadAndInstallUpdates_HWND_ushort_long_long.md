# CErcLuaElevationHelper::DownloadAndInstallUpdates(HWND__ *,ushort *,long *,long *)

- ea: `0x1800039c0`
- end: `0x180003a8b`
- name: `?DownloadAndInstallUpdates@CErcLuaElevationHelper@@UEAAJPEAUHWND__@@PEAGPEAJ2@Z`
- size: `203`
- prototype: `__int64 __fastcall(CErcLuaElevationHelper *__hidden this, HWND, unsigned __int16 *, int *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180003868`
- `0x1800039c0`
- `0x180006c9c`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelper::DownloadAndInstallUpdates(
        CErcLuaElevationHelper *this,
        HWND a2,
        unsigned __int16 *a3,
        int *a4,
        int *a5)
{
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int128 v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  v11 = 0;
  v10 = 0;
  if ( a5 && a4 && a3 )
  {
    *a4 = 0;
    *a5 = 0;
    v6 = CErcLuaDownloadAndInstall::DownloadAndInstallUpdates((CErcLuaDownloadAndInstall *)&v10, a2, a3);
    if ( v6 >= 0 )
    {
      v6 = 0;
      *a4 = v11;
      *a5 = HIDWORD(v11);
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 15;
LABEL_12:
        WPP_SF_d(v7[2], v8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, (unsigned int)v6);
      }
    }
  }
  else
  {
    v6 = -2147024809;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 14;
      goto LABEL_12;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800039c0  mov     rax, rsp
0x1800039c3  mov     [rax+8], rbx
0x1800039c7  mov     [rax+10h], rsi
0x1800039cb  push    rdi
0x1800039cc  sub     rsp, 40h
0x1800039d0  mov     rsi, [rsp+48h+arg_20]
0x1800039d5  xorps   xmm0, xmm0
0x1800039d8  mov     qword ptr [rax-18h], 0
0x1800039e0  mov     rdi, r9
0x1800039e3  movdqu  xmmword ptr [rax-28h], xmm0
0x1800039e8  test    rsi, rsi
0x1800039eb  jz      short loc_180003A43
0x1800039ed  test    r9, r9
0x1800039f0  jz      short loc_180003A43
0x1800039f2  test    r8, r8
0x1800039f5  jz      short loc_180003A43
0x1800039f7  mov     dword ptr [r9], 0
0x1800039fe  lea     rcx, [rax-28h]; this
0x180003a02  mov     dword ptr [rsi], 0
0x180003a08  call    ?DownloadAndInstallUpdates@CErcLuaDownloadAndInstall@@QEAAJPEAUHWND__@@PEAG@Z; CErcLuaDownloadAndInstall::DownloadAndInstallUpdates(HWND__ *,ushort *)
0x180003a0d  mov     ebx, eax
0x180003a0f  test    eax, eax
0x180003a11  jns     short loc_180003A33
0x180003a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a1a  lea     rax, WPP_GLOBAL_Control
0x180003a21  cmp     rcx, rax
0x180003a24  jz      short loc_180003A79
0x180003a26  test    byte ptr [rcx+1Ch], 1
0x180003a2a  jz      short loc_180003A79
0x180003a2c  mov     edx, 0Fh
0x180003a31  jmp     short loc_180003A66
0x180003a33  mov     eax, [rsp+48h+var_18]
0x180003a37  xor     ebx, ebx
0x180003a39  mov     [rdi], eax
0x180003a3b  mov     eax, [rsp+48h+var_14]
0x180003a3f  mov     [rsi], eax
0x180003a41  jmp     short loc_180003A79
0x180003a43  mov     ebx, 80070057h
0x180003a48  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a4f  lea     rax, WPP_GLOBAL_Control
0x180003a56  cmp     rcx, rax
0x180003a59  jz      short loc_180003A79
0x180003a5b  test    byte ptr [rcx+1Ch], 1
0x180003a5f  jz      short loc_180003A79
0x180003a61  mov     edx, 0Eh
0x180003a66  mov     rcx, [rcx+10h]
0x180003a6a  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003a71  mov     r9d, ebx
0x180003a74  call    WPP_SF_d
0x180003a79  mov     rsi, [rsp+48h+arg_8]
0x180003a7e  mov     eax, ebx
0x180003a80  mov     rbx, [rsp+48h+arg_0]
0x180003a85  add     rsp, 40h
0x180003a89  pop     rdi
0x180003a8a  retn
```
