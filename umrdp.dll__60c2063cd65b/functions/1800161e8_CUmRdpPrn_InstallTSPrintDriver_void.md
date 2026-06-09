# CUmRdpPrn::InstallTSPrintDriver(void)

- ea: `0x1800161e8`
- end: `0x1800164c2`
- name: `?InstallTSPrintDriver@CUmRdpPrn@@AEAAJXZ`
- size: `730`
- prototype: `__int64 __fastcall(CUmRdpPrn *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180015428`

## callees

- `0x180005c10`
- `0x18000b8f8`
- `0x18000f75c`
- `0x18000f79c`
- `0x1800134cc`
- `0x1800161e8`
- `0x180017d14`
- `0x180017ee0`
- `0x180047ebe`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180016337`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180016337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016438`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::InstallTSPrintDriver(CUmRdpPrn *this)
{
  signed int v1; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // r8
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // edx
  int v11; // r8d
  __int64 (__fastcall *v12)(__int64, _DWORD **); // rax
  __int64 v13; // rax
  unsigned int v14; // eax
  __int64 v15; // r8
  signed int LastError; // eax
  _DWORD *v18; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v20; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+80h] [rbp-80h]
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  v1 = dword_18005C198;
  if ( dword_18005C198 != 1 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 12;
LABEL_38:
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v4,
        WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
        CurrentThreadActivityIdPrefix,
        v1);
      return (unsigned int)dword_18005C198;
    }
    return (unsigned int)v1;
  }
  v5 = CUmRdpPrn::PrinterDriverInstalled(this, XPSDriverName);
  v1 = v5;
  if ( v5 != 2 )
  {
    if ( v5 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 13, v7, v6);
      }
      if ( v1 > 0 )
        v1 = (unsigned __int16)v1 | 0x80070000;
    }
    dword_18005C198 = v1;
    return (unsigned int)v1;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      14,
      WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
      v8);
  }
  memset_0(v19, 0, 0x48u);
  v18 = 0;
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_33;
  }
  dword_18005C198 = StringCchCatW(Buffer, 0x104u, L"\\inf\\tsprint.inf");
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v10, v11, v9, (__int64)Buffer);
  }
  memset_0(v19, 0, 0x48u);
  v19[0] = 72;
  v20 = Buffer;
  v21 = XPSDriverName;
  v18 = v19;
  v12 = (__int64 (__fastcall *)(__int64, _DWORD **))*((_QWORD *)this + 22);
  v22 = 4100;
  v1 = v12(4, &v18);
  if ( !v1 )
  {
LABEL_33:
    v13 = *(_QWORD *)&WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  v13 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 16, v15, v14);
    v13 = *(_QWORD *)&WPP_GLOBAL_Control;
  }
  if ( v1 > 0 )
    v1 = (unsigned __int16)v1 | 0x80070000;
LABEL_34:
  dword_18005C198 = v1;
  if ( (unsigned int *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 1) != 0 && *(_BYTE *)(v13 + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = 17;
    goto LABEL_38;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800161e8  mov     [rsp-8+arg_8], rbx
0x1800161ed  mov     [rsp-8+arg_10], rsi
0x1800161f2  push    rbp
0x1800161f3  push    rdi
0x1800161f4  push    r15
0x1800161f6  lea     rbp, [rsp-1B0h]
0x1800161fe  sub     rsp, 2B0h
0x180016205  mov     rax, cs:__security_cookie
0x18001620c  xor     rax, rsp
0x18001620f  mov     [rbp+1C0h+var_20], rax
0x180016216  mov     ebx, cs:dword_18005C198
0x18001621c  mov     rsi, rcx
0x18001621f  cmp     ebx, 1
0x180016222  jz      short loc_18001625E
0x180016224  mov     rax, cs:WPP_GLOBAL_Control
0x18001622b  lea     rdi, WPP_GLOBAL_Control
0x180016232  cmp     rax, rdi
0x180016235  jz      loc_180016499
0x18001623b  test    byte ptr [rax+1Ch], 1
0x18001623f  jz      loc_180016499
0x180016245  cmp     byte ptr [rax+19h], 4
0x180016249  jb      loc_180016499
0x18001624f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180016254  mov     edx, 0Ch
0x180016259  jmp     loc_180016475
0x18001625e  lea     r15, ?XPSDriverName@@3PAGA; "Remote Desktop Easy Print"
0x180016265  mov     rdx, r15; unsigned __int16 *
0x180016268  call    ?PrinterDriverInstalled@CUmRdpPrn@@AEAAKPEBG@Z; CUmRdpPrn::PrinterDriverInstalled(ushort const *)
0x18001626d  mov     ebx, eax
0x18001626f  cmp     eax, 2
0x180016272  jz      short loc_1800162D0
0x180016274  test    eax, eax
0x180016276  jz      short loc_1800162C5
0x180016278  mov     rax, cs:WPP_GLOBAL_Control
0x18001627f  lea     rdi, WPP_GLOBAL_Control
0x180016286  cmp     rax, rdi
0x180016289  jz      short loc_1800162B8
0x18001628b  test    byte ptr [rax+1Ch], 1
0x18001628f  jz      short loc_1800162B8
0x180016291  cmp     byte ptr [rax+19h], 2
0x180016295  jb      short loc_1800162B8
0x180016297  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001629c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162a3  mov     edx, 0Dh
0x1800162a8  mov     r9d, eax
0x1800162ab  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x1800162af  mov     rcx, [rcx+10h]
0x1800162b3  call    WPP_SF_Dl
0x1800162b8  test    ebx, ebx
0x1800162ba  jle     short loc_1800162C5
0x1800162bc  movzx   ebx, bx
0x1800162bf  or      ebx, 80070000h
0x1800162c5  mov     cs:dword_18005C198, ebx
0x1800162cb  jmp     loc_180016499
0x1800162d0  mov     rax, cs:WPP_GLOBAL_Control
0x1800162d7  lea     rdi, WPP_GLOBAL_Control
0x1800162de  cmp     rax, rdi
0x1800162e1  jz      short loc_180016313
0x1800162e3  test    byte ptr [rax+1Ch], 1
0x1800162e7  jz      short loc_180016313
0x1800162e9  cmp     byte ptr [rax+19h], 4
0x1800162ed  jb      short loc_180016313
0x1800162ef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800162f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162fb  lea     r8, WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids
0x180016302  mov     edx, 0Eh
0x180016307  mov     r9d, eax
0x18001630a  mov     rcx, [rcx+10h]
0x18001630e  call    WPP_SF_D
0x180016313  xor     edx, edx; Val
0x180016315  lea     rcx, [rsp+2C0h+var_280]; void *
0x18001631a  lea     r8d, [rdx+48h]; Size
0x18001631e  call    memset_0
0x180016323  mov     ebx, 104h
0x180016328  mov     [rsp+2C0h+var_290], 0
0x180016331  mov     edx, ebx; uSize
0x180016333  lea     rcx, [rbp+1C0h+Buffer]; lpBuffer
0x180016337  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001633d  test    eax, eax
0x18001633f  jz      loc_180016438
0x180016345  lea     r8, aInfTsprintInf; "\\inf\\tsprint.inf"
0x18001634c  mov     edx, ebx; unsigned __int64
0x18001634e  lea     rcx, [rbp+1C0h+Buffer]; unsigned __int16 *
0x180016352  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016357  mov     cs:dword_18005C198, eax
0x18001635d  mov     rax, cs:WPP_GLOBAL_Control
0x180016364  cmp     rax, rdi
0x180016367  jz      short loc_180016396
0x180016369  test    byte ptr [rax+1Ch], 1
0x18001636d  jz      short loc_180016396
0x18001636f  cmp     byte ptr [rax+19h], 4
0x180016373  jb      short loc_180016396
0x180016375  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001637a  lea     rcx, [rbp+1C0h+Buffer]
0x18001637e  mov     r9d, eax
0x180016381  mov     [rsp+2C0h+var_2A0], rcx
0x180016386  mov     rcx, cs:WPP_GLOBAL_Control
0x18001638d  mov     rcx, [rcx+10h]
0x180016391  call    WPP_SF_DSS
0x180016396  xor     edx, edx; Val
0x180016398  lea     rcx, [rsp+2C0h+var_280]; void *
0x18001639d  lea     r8d, [rdx+48h]; Size
0x1800163a1  call    memset_0
0x1800163a6  lea     rax, [rbp+1C0h+Buffer]
0x1800163aa  mov     [rsp+2C0h+var_280], 48h ; 'H'
0x1800163b2  mov     [rsp+2C0h+var_270], rax
0x1800163b7  lea     rdx, [rsp+2C0h+var_290]
0x1800163bc  lea     rax, [rsp+2C0h+var_280]
0x1800163c1  mov     [rsp+2C0h+var_260], r15
0x1800163c6  mov     [rsp+2C0h+var_290], rax
0x1800163cb  mov     ecx, 4
0x1800163d0  mov     rax, [rsi+0B0h]
0x1800163d7  mov     [rbp+1C0h+var_240], 1004h
0x1800163de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163e3  mov     ebx, eax
0x1800163e5  test    eax, eax
0x1800163e7  jz      short loc_18001644D
0x1800163e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800163f0  cmp     rax, rdi
0x1800163f3  jz      short loc_180016429
0x1800163f5  test    byte ptr [rax+1Ch], 1
0x1800163f9  jz      short loc_180016429
0x1800163fb  cmp     byte ptr [rax+19h], 2
0x1800163ff  jb      short loc_180016429
0x180016401  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180016406  mov     rcx, cs:WPP_GLOBAL_Control
0x18001640d  mov     edx, 10h
0x180016412  mov     r9d, eax
0x180016415  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x180016419  mov     rcx, [rcx+10h]
0x18001641d  call    WPP_SF_Dl
0x180016422  mov     rax, cs:WPP_GLOBAL_Control
0x180016429  test    ebx, ebx
0x18001642b  jle     short loc_180016454
0x18001642d  movzx   ebx, bx
0x180016430  or      ebx, 80070000h
0x180016436  jmp     short loc_180016454
0x180016438  call    cs:__imp_GetLastError
0x18001643e  mov     ebx, eax
0x180016440  test    eax, eax
0x180016442  jle     short loc_18001644D
0x180016444  movzx   ebx, ax
0x180016447  or      ebx, 80070000h
0x18001644d  mov     rax, cs:WPP_GLOBAL_Control
0x180016454  mov     cs:dword_18005C198, ebx
0x18001645a  cmp     rax, rdi
0x18001645d  jz      short loc_180016499
0x18001645f  test    byte ptr [rax+1Ch], 1
0x180016463  jz      short loc_180016499
0x180016465  cmp     byte ptr [rax+19h], 4
0x180016469  jb      short loc_180016499
0x18001646b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180016470  mov     edx, 11h
0x180016475  mov     rcx, cs:WPP_GLOBAL_Control
0x18001647c  lea     r8, WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids
0x180016483  mov     r9d, eax
0x180016486  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x18001648a  mov     rcx, [rcx+10h]
0x18001648e  call    WPP_SF_Dd
0x180016493  mov     ebx, cs:dword_18005C198
0x180016499  mov     eax, ebx
0x18001649b  mov     rcx, [rbp+1C0h+var_20]
0x1800164a2  xor     rcx, rsp; StackCookie
0x1800164a5  call    __security_check_cookie
0x1800164aa  lea     r11, [rsp+2C0h+var_10]
0x1800164b2  mov     rbx, [r11+28h]
0x1800164b6  mov     rsi, [r11+30h]
0x1800164ba  mov     rsp, r11
0x1800164bd  pop     r15
0x1800164bf  pop     rdi
0x1800164c0  pop     rbp
0x1800164c1  retn
```
