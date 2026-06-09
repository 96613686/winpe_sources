# CServiceControl::SetStartType(ulong)

- ea: `0x140091ba8`
- end: `0x140091d5a`
- name: `?SetStartType@CServiceControl@@QEAAHK@Z`
- size: `434`
- prototype: `__int64 __fastcall(CServiceControl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1400479b0`

## callees

- `0x14003b714`
- `0x14003f17c`
- `0x140047798`
- `0x140091a70`
- `0x140091ba8`

## import_xrefs

- `ADVAPI32!ChangeServiceConfig2W` at `0x140091c71`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140091c71`
- `ADVAPI32!ChangeServiceConfigW` at `0x140091cda`
- `ADVAPI32!ChangeServiceConfigW` at `0x140091cda`
- `KERNEL32!GetLastError` at `0x140091c7e`
- `KERNEL32!GetLastError` at `0x140091ce7`
- `KERNEL32!GetLastError` at `0x140091c7e`
- `KERNEL32!GetLastError` at `0x140091ce7`

## pseudocode

```c
__int64 __fastcall CServiceControl::SetStartType(SC_HANDLE *this, int a2)
{
  PVOID *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  SC_HANDLE v6; // rcx
  DWORD LastError; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int Info; // [rsp+98h] [rbp+10h] BYREF

  Info = a2;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_cb23d491edf93b904e2862226171c496_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 4u )
      WPP_SF_d(v3[2], 27, WPP_cb23d491edf93b904e2862226171c496_Traceguids, 1);
  }
  v4 = CServiceControl::OpenServiceW((CServiceControl *)this, 1);
  v5 = v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_cb23d491edf93b904e2862226171c496_Traceguids, v4);
  }
  if ( v5 == 1 )
  {
    v6 = this[2];
    Info = 1;
    v5 = ChangeServiceConfig2W(v6, 3u, &Info);
    if ( v5 == 1 )
    {
      v5 = ChangeServiceConfigW(this[2], 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
      if ( v5 != 1 )
      {
        LastError = GetLastError();
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v9 = 30;
          goto LABEL_23;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 29;
LABEL_23:
        WPP_SF_d(v8[2], v9, WPP_cb23d491edf93b904e2862226171c496_Traceguids, LastError);
      }
    }
  }
  CServiceControl::CloseServiceManager((CServiceControl *)this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_cb23d491edf93b904e2862226171c496_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140091ba8  mov     [rsp+Info], edx
0x140091bac  push    rbx
0x140091bad  push    rdi
0x140091bae  push    r14
0x140091bb0  push    r15
0x140091bb2  sub     rsp, 68h
0x140091bb6  mov     rdi, rcx
0x140091bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140091bc0  lea     r14, WPP_GLOBAL_Control
0x140091bc7  lea     r15, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091bce  cmp     rcx, r14
0x140091bd1  jz      short loc_140091C17
0x140091bd3  test    byte ptr [rcx+1Ch], 1
0x140091bd7  jz      short loc_140091BF1
0x140091bd9  mov     rcx, [rcx+10h]
0x140091bdd  mov     edx, 1Ah
0x140091be2  mov     r8, r15
0x140091be5  call    WPP_SF_
0x140091bea  mov     rcx, cs:WPP_GLOBAL_Control
0x140091bf1  cmp     rcx, r14
0x140091bf4  jz      short loc_140091C17
0x140091bf6  test    byte ptr [rcx+1Ch], 2
0x140091bfa  jz      short loc_140091C17
0x140091bfc  cmp     byte ptr [rcx+19h], 4
0x140091c00  jb      short loc_140091C17
0x140091c02  mov     rcx, [rcx+10h]
0x140091c06  mov     edx, 1Bh
0x140091c0b  mov     r8, r15
0x140091c0e  lea     r9d, [rdx-1Ah]
0x140091c12  call    WPP_SF_d
0x140091c17  mov     edx, 1; int
0x140091c1c  mov     rcx, rdi; this
0x140091c1f  call    ?OpenServiceW@CServiceControl@@AEAAHH@Z; CServiceControl::OpenServiceW(int)
0x140091c24  mov     ebx, eax
0x140091c26  mov     rcx, cs:WPP_GLOBAL_Control
0x140091c2d  cmp     rcx, r14
0x140091c30  jz      short loc_140091C52
0x140091c32  test    byte ptr [rcx+1Ch], 2
0x140091c36  jz      short loc_140091C52
0x140091c38  cmp     byte ptr [rcx+19h], 4
0x140091c3c  jb      short loc_140091C52
0x140091c3e  mov     rcx, [rcx+10h]
0x140091c42  mov     edx, 1Ch
0x140091c47  mov     r9d, eax
0x140091c4a  mov     r8, r15
0x140091c4d  call    WPP_SF_d
0x140091c52  cmp     ebx, 1
0x140091c55  jnz     loc_140091D19
0x140091c5b  mov     rcx, [rdi+10h]; hService
0x140091c5f  lea     r8, [rsp+88h+Info]; lpInfo
0x140091c67  lea     edx, [rbx+2]; dwInfoLevel
0x140091c6a  mov     [rsp+88h+Info], ebx
0x140091c71  call    cs:__imp_ChangeServiceConfig2W
0x140091c77  mov     ebx, eax
0x140091c79  cmp     eax, 1
0x140091c7c  jz      short loc_140091CA7
0x140091c7e  call    cs:__imp_GetLastError
0x140091c84  mov     rcx, cs:WPP_GLOBAL_Control
0x140091c8b  cmp     rcx, r14
0x140091c8e  jz      loc_140091D19
0x140091c94  test    byte ptr [rcx+1Ch], 2
0x140091c98  jz      short loc_140091D19
0x140091c9a  cmp     byte ptr [rcx+19h], 2
0x140091c9e  jb      short loc_140091D19
0x140091ca0  mov     edx, 1Dh
0x140091ca5  jmp     short loc_140091D0A
0x140091ca7  mov     rcx, [rdi+10h]; hService
0x140091cab  xor     eax, eax
0x140091cad  mov     [rsp+88h+lpDisplayName], rax; lpDisplayName
0x140091cb2  or      edx, 0FFFFFFFFh; dwServiceType
0x140091cb5  mov     [rsp+88h+lpPassword], rax; lpPassword
0x140091cba  mov     r9d, edx; dwErrorControl
0x140091cbd  mov     [rsp+88h+lpServiceStartName], rax; lpServiceStartName
0x140091cc2  mov     [rsp+88h+lpDependencies], rax; lpDependencies
0x140091cc7  lea     r8d, [rax+2]; dwStartType
0x140091ccb  mov     [rsp+88h+lpdwTagId], rax; lpdwTagId
0x140091cd0  mov     [rsp+88h+lpLoadOrderGroup], rax; lpLoadOrderGroup
0x140091cd5  mov     [rsp+88h+lpBinaryPathName], rax; lpBinaryPathName
0x140091cda  call    cs:__imp_ChangeServiceConfigW
0x140091ce0  mov     ebx, eax
0x140091ce2  cmp     eax, 1
0x140091ce5  jz      short loc_140091D19
0x140091ce7  call    cs:__imp_GetLastError
0x140091ced  mov     rcx, cs:WPP_GLOBAL_Control
0x140091cf4  cmp     rcx, r14
0x140091cf7  jz      short loc_140091D19
0x140091cf9  test    byte ptr [rcx+1Ch], 2
0x140091cfd  jz      short loc_140091D19
0x140091cff  cmp     byte ptr [rcx+19h], 4
0x140091d03  jb      short loc_140091D19
0x140091d05  mov     edx, 1Eh
0x140091d0a  mov     rcx, [rcx+10h]
0x140091d0e  mov     r9d, eax
0x140091d11  mov     r8, r15
0x140091d14  call    WPP_SF_d
0x140091d19  mov     rcx, rdi; this
0x140091d1c  call    ?CloseServiceManager@CServiceControl@@AEAAXXZ; CServiceControl::CloseServiceManager(void)
0x140091d21  mov     rcx, cs:WPP_GLOBAL_Control
0x140091d28  cmp     rcx, r14
0x140091d2b  jz      short loc_140091D4D
0x140091d2d  test    byte ptr [rcx+1Ch], 1
0x140091d31  jz      short loc_140091D4D
0x140091d33  cmp     byte ptr [rcx+19h], 5
0x140091d37  jb      short loc_140091D4D
0x140091d39  mov     rcx, [rcx+10h]
0x140091d3d  mov     edx, 1Fh
0x140091d42  mov     r9d, ebx
0x140091d45  mov     r8, r15
0x140091d48  call    WPP_SF_d
0x140091d4d  mov     eax, ebx
0x140091d4f  add     rsp, 68h
0x140091d53  pop     r15
0x140091d55  pop     r14
0x140091d57  pop     rdi
0x140091d58  pop     rbx
0x140091d59  retn
```
