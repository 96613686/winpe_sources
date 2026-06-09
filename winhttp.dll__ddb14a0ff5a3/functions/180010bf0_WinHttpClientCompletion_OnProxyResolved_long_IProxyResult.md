# WinHttpClientCompletion::OnProxyResolved(long,IProxyResult *)

- ea: `0x180010bf0`
- end: `0x180010eac`
- name: `?OnProxyResolved@WinHttpClientCompletion@@UEAAJJPEAUIProxyResult@@@Z`
- size: `700`
- prototype: `int(WinHttpClientCompletion *__hidden this, int, struct IProxyResult *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006210`
- `0x180010bf0`
- `0x180010eb4`
- `0x180010f50`
- `0x180011000`
- `0x1800a1d10`
- `0x1800cf454`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010cbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010cbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010cb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010cb4`
- `ntdll!EtwEventActivityIdControl` at `0x180010cec`
- `ntdll!EtwEventActivityIdControl` at `0x180010cec`

## pseudocode

```c
__int64 __fastcall WinHttpClientCompletion::OnProxyResolved(
        WinHttpClientCompletion *this,
        int a2,
        struct IProxyResult *a3)
{
  char v6; // dl
  char *v7; // rbx
  struct _GUID *v8; // rax
  __int64 v9; // rcx
  signed __int32 v10; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int v13; // ecx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v17; // [rsp+20h] [rbp-88h]
  int v18; // [rsp+38h] [rbp-70h] BYREF
  struct _GUID v19; // [rsp+3Ch] [rbp-6Ch] BYREF
  int v20; // [rsp+4Ch] [rbp-5Ch]
  __int128 v21; // [rsp+50h] [rbp-58h] BYREF
  struct _GUID v22; // [rsp+60h] [rbp-48h] BYREF
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = xmmword_180107A60;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_dq(1029, 30, (unsigned int)WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids, a2, (__int64)a3);
    v6 = xmmword_180107A60;
  }
  v18 = 0;
  v20 = 0;
  v19 = 0;
  if ( (v6 & 0x20) != 0 )
    WPP_SF_dq(1029, 24, (unsigned int)WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids, a2, (__int64)a3);
  v7 = (char *)this + 276;
  v8 = &v19;
  v21 = 0;
  v9 = 16;
  v22 = 0;
  do
  {
    LOBYTE(v8->Data1) = 0;
    v8 = (struct _GUID *)((char *)v8 + 1);
    --v9;
  }
  while ( v9 );
  WxEtwGetActivityId(&v22);
  if ( this == (WinHttpClientCompletion *)-276LL )
  {
    v10 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    TickCount = GetTickCount();
    CurrentProcessId = GetCurrentProcessId();
    *(_QWORD *)&v21 = __PAIR64__(v10, (unsigned int)retaddr);
    *((_QWORD *)&v21 + 1) = __PAIR64__(CurrentProcessId, TickCount);
    v7 = (char *)&v21;
  }
  EtwEventActivityIdControl(2, v7);
  v13 = *((_DWORD *)this + 18);
  v19 = v22;
  v20 = 0;
  v18 = 1;
  if ( v13 > 1 )
  {
    v14 = -2147024809;
  }
  else
  {
    if ( v13 )
    {
      v14 = WinHttpClientCompletion::StateComplete((WinHttpClientCompletion *)((char *)this - 16), a2, a3);
      v15 = v14;
      goto LABEL_13;
    }
    v14 = WinHttpClientCompletion::StateStart((WinHttpClientCompletion *)((char *)this - 16));
    if ( v14 >= 0 )
    {
      v15 = 787429;
      if ( v14 == 787429 )
        goto LABEL_13;
      v14 = -2147418113;
    }
  }
  v15 = v14;
LABEL_13:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 25, WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids, (unsigned int)v14, v17);
  AutoEtwActivity::End((AutoEtwActivity *)&v18);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 31, WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids, v15, v17);
  return v15;
}

```

## disassembly

```asm
0x180010bf0  mov     [rsp+arg_18], rbx
0x180010bf5  push    rsi
0x180010bf6  push    rdi
0x180010bf7  push    r12
0x180010bf9  push    r14
0x180010bfb  push    r15
0x180010bfd  sub     rsp, 80h
0x180010c04  mov     rax, cs:__security_cookie
0x180010c0b  xor     rax, rsp
0x180010c0e  mov     [rsp+0A8h+var_38], rax
0x180010c13  mov     r12, r8
0x180010c16  mov     r15d, edx
0x180010c19  mov     r14, rcx
0x180010c1c  mov     dl, byte ptr cs:xmmword_180107A60
0x180010c22  mov     edi, 405h
0x180010c27  test    dl, 20h
0x180010c2a  jnz     loc_180010E38
0x180010c30  xor     eax, eax
0x180010c32  mov     [rsp+0A8h+var_74], 0
0x180010c3a  xorps   xmm0, xmm0
0x180010c3d  mov     [rsp+0A8h+var_70], eax
0x180010c41  mov     [rsp+0A8h+var_5C], eax
0x180010c45  movups  [rsp+0A8h+var_6C], xmm0
0x180010c4a  mov     [rsp+0A8h+var_74], 0
0x180010c52  test    dl, 20h
0x180010c55  jnz     loc_180010E5E
0x180010c5b  test    eax, eax
0x180010c5d  jnz     loc_180010E82
0x180010c63  xorps   xmm0, xmm0
0x180010c66  lea     rbx, [r14+114h]
0x180010c6d  xorps   xmm1, xmm1
0x180010c70  lea     rax, [rsp+0A8h+var_6C]
0x180010c75  movups  [rsp+0A8h+var_58], xmm0
0x180010c7a  mov     ecx, 10h
0x180010c7f  movups  xmmword ptr [rsp+0A8h+var_48.Data1], xmm1
0x180010c84  mov     byte ptr [rax], 0
0x180010c87  inc     rax
0x180010c8a  sub     rcx, 1
0x180010c8e  jnz     short loc_180010C84
0x180010c90  lea     rcx, [rsp+0A8h+var_48]; struct _GUID *
0x180010c95  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x180010c9a  test    rbx, rbx
0x180010c9d  jnz     short loc_180010CDC
0x180010c9f  mov     rdi, [rsp+0A8h]
0x180010ca7  lea     esi, [rbx+1]
0x180010caa  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180010cb2  inc     esi
0x180010cb4  call    cs:__imp_GetTickCount
0x180010cba  mov     ebx, eax
0x180010cbc  call    cs:__imp_GetCurrentProcessId
0x180010cc2  mov     dword ptr [rsp+0A8h+var_58], edi
0x180010cc6  mov     edi, 405h
0x180010ccb  mov     dword ptr [rsp+0A8h+var_58+8], ebx
0x180010ccf  lea     rbx, [rsp+0A8h+var_58]
0x180010cd4  mov     dword ptr [rsp+0A8h+var_58+0Ch], eax
0x180010cd8  mov     dword ptr [rsp+0A8h+var_58+4], esi
0x180010cdc  mov     rdx, rbx
0x180010cdf  mov     [rsp+0A8h+var_74], 0
0x180010ce7  mov     ecx, 2
0x180010cec  call    cs:__imp_EtwEventActivityIdControl
0x180010cf2  test    eax, eax
0x180010cf4  jle     short loc_180010D00
0x180010cf6  movzx   eax, ax
0x180010cf9  or      eax, 80070000h
0x180010cfe  test    eax, eax
0x180010d00  js      loc_180010E10
0x180010d06  mov     rax, qword ptr [rsp+0A8h+var_48.Data1]
0x180010d0b  mov     ecx, [r14+48h]
0x180010d0f  mov     qword ptr [rsp+0A8h+var_6C], rax
0x180010d14  mov     rax, qword ptr [rsp+0A8h+var_48.Data4]
0x180010d19  mov     qword ptr [rsp+0A8h+var_6C+8], rax
0x180010d1e  mov     [rsp+0A8h+var_5C], 0
0x180010d26  mov     [rsp+0A8h+var_70], 1
0x180010d2e  cmp     ecx, 1
0x180010d31  ja      loc_180010DD6
0x180010d37  xor     eax, eax
0x180010d39  test    ecx, ecx
0x180010d3b  jnz     short loc_180010DAE
0x180010d3d  lea     rcx, [r14-10h]; this
0x180010d41  call    ?StateStart@WinHttpClientCompletion@@AEAAJXZ; WinHttpClientCompletion::StateStart(void)
0x180010d46  test    eax, eax
0x180010d48  js      loc_180010DEA
0x180010d4e  mov     ebx, 0C03E5h
0x180010d53  cmp     eax, ebx
0x180010d55  jnz     loc_180010DF4
0x180010d5b  test    byte ptr cs:xmmword_180107A60, 20h
0x180010d62  jnz     loc_180010E1D
0x180010d68  lea     rcx, [rsp+0A8h+var_70]; this
0x180010d6d  call    ?End@AutoEtwActivity@@QEAAXXZ; AutoEtwActivity::End(void)
0x180010d72  test    ebx, ebx
0x180010d74  js      loc_180010E03
0x180010d7a  test    byte ptr cs:xmmword_180107A60, 20h
0x180010d81  jnz     loc_180010E91
0x180010d87  mov     eax, ebx
0x180010d89  mov     rcx, [rsp+0A8h+var_38]
0x180010d8e  xor     rcx, rsp; StackCookie
0x180010d91  call    __security_check_cookie
0x180010d96  mov     rbx, [rsp+0A8h+arg_18]
0x180010d9e  add     rsp, 80h
0x180010da5  pop     r15
0x180010da7  pop     r14
0x180010da9  pop     r12
0x180010dab  pop     rdi
0x180010dac  pop     rsi
0x180010dad  retn
0x180010dae  cmp     ecx, 1
0x180010db1  jnz     short loc_180010DD2
0x180010db3  mov     r8, r12; struct IProxyResult *
0x180010db6  lea     rcx, [r14-10h]; this
0x180010dba  mov     edx, r15d; int
0x180010dbd  call    ?StateComplete@WinHttpClientCompletion@@AEAAJJPEAUIProxyResult@@@Z; WinHttpClientCompletion::StateComplete(long,IProxyResult *)
0x180010dc2  mov     ebx, eax
0x180010dc4  test    eax, eax
0x180010dc6  jns     short loc_180010D5B
0x180010dc8  mov     [rsp+0A8h+var_74], 27Dh
0x180010dd0  jmp     short loc_180010D5B
0x180010dd2  xor     ebx, ebx
0x180010dd4  jmp     short loc_180010D5B
0x180010dd6  mov     eax, 80070057h
0x180010ddb  mov     [rsp+0A8h+var_74], 26Dh
0x180010de3  mov     ebx, eax
0x180010de5  jmp     loc_180010D5B
0x180010dea  mov     [rsp+0A8h+var_74], 271h
0x180010df2  jmp     short loc_180010DE3
0x180010df4  mov     eax, 8000FFFFh
0x180010df9  mov     [rsp+0A8h+var_74], 277h
0x180010e01  jmp     short loc_180010DE3
0x180010e03  mov     [rsp+0A8h+var_74], 34Ch
0x180010e0b  jmp     loc_180010D7A
0x180010e10  mov     [rsp+0A8h+var_74], 90h
0x180010e18  jmp     loc_180010D06
0x180010e1d  mov     edx, 19h
0x180010e22  lea     r8, WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids
0x180010e29  mov     ecx, edi
0x180010e2b  mov     r9d, eax
0x180010e2e  call    WPP_SF_d
0x180010e33  jmp     loc_180010D68
0x180010e38  mov     edx, 1Eh
0x180010e3d  mov     [rsp+0A8h+var_88], r12
0x180010e42  mov     ecx, edi
0x180010e44  lea     r8, WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids
0x180010e4b  mov     r9d, r15d
0x180010e4e  call    WPP_SF_dq
0x180010e53  mov     dl, byte ptr cs:xmmword_180107A60
0x180010e59  jmp     loc_180010C30
0x180010e5e  mov     edx, 18h
0x180010e63  mov     [rsp+0A8h+var_88], r12
0x180010e68  mov     ecx, edi
0x180010e6a  lea     r8, WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids
0x180010e71  mov     r9d, r15d
0x180010e74  call    WPP_SF_dq
0x180010e79  mov     eax, [rsp+0A8h+var_70]
0x180010e7d  jmp     loc_180010C5B
0x180010e82  lea     rcx, [rsp+0A8h+var_70]; this
0x180010e87  call    ?End@AutoEtwActivity@@QEAAXXZ; AutoEtwActivity::End(void)
0x180010e8c  jmp     loc_180010C63
0x180010e91  mov     edx, 1Fh
0x180010e96  lea     r8, WPP_146f06c3ee3a36ac0c51f70dba0fa87e_Traceguids
0x180010e9d  mov     ecx, edi
0x180010e9f  mov     r9d, ebx
0x180010ea2  call    WPP_SF_d
0x180010ea7  jmp     loc_180010D87
```
