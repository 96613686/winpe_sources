# HrGetCurrentCallLocality(CALL_LOCALITY *)

- ea: `0x180007270`
- end: `0x1800074d5`
- name: `?HrGetCurrentCallLocality@@YAJPEAW4CALL_LOCALITY@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(enum CALL_LOCALITY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800071c0`

## callees

- `0x180007270`
- `0x1800074dc`
- `0x18003b1cc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800072b9`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800072b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800073bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800073bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000739d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000739d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072fb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800073e1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800073e1`

## pseudocode

```c
__int64 __fastcall HrGetCurrentCallLocality(enum CALL_LOCALITY *a1)
{
  int v2; // esi
  HRESULT Win32Error; // ebx
  STRSAFE_PCNZWCH v4; // rax
  HANDLE CurrentThread; // rax
  __int64 v7; // rdx
  WINBOOL IsMember; // [rsp+50h] [rbp+8h] BYREF
  void *ppInterface; // [rsp+58h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp+18h] BYREF

  hObject = 0;
  ppInterface = 0;
  if ( !a1 || !pSid )
    return 2147942487LL;
  v2 = 0;
  Win32Error = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  if ( Win32Error < 0 )
    goto LABEL_4;
  if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
  {
    Win32Error = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
    if ( Win32Error < 0 )
    {
LABEL_4:
      if ( Win32Error == -2147417833 )
      {
        *(_DWORD *)a1 = 1;
        Win32Error = 0;
        goto LABEL_6;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_7;
      v7 = 20;
LABEL_33:
      WPP_SF_d(*((_QWORD *)v4 + 2), v7, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, (unsigned int)Win32Error);
      goto LABEL_6;
    }
    v2 = 1;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
  {
    Win32Error = HrFromLastWin32Error();
    if ( !Win32Error )
      goto LABEL_6;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 19;
    goto LABEL_33;
  }
  IsMember = 0;
  if ( CheckTokenMembership(hObject, pSid, &IsMember) )
  {
    *(_DWORD *)a1 = (IsMember != 0) + 3;
    goto LABEL_6;
  }
  Win32Error = HrFromLastWin32Error();
  if ( Win32Error )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 18;
    goto LABEL_33;
  }
LABEL_6:
  v4 = WPP_GLOBAL_Control;
LABEL_7:
  if ( hObject )
  {
    CloseHandle(hObject);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
    v4 = WPP_GLOBAL_Control;
  }
  if ( ppInterface )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    v4 = WPP_GLOBAL_Control;
  }
  if ( Win32Error && v4 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v4[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 21, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, (unsigned int)Win32Error);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180007270  push    rbp
0x180007272  push    rdi
0x180007273  sub     rsp, 38h
0x180007277  xor     ebp, ebp
0x180007279  mov     rdi, rcx
0x18000727c  mov     [rsp+48h+hObject], rbp
0x180007281  mov     [rsp+48h+ppInterface], rbp
0x180007286  test    rcx, rcx
0x180007289  jz      loc_180007421
0x18000728f  cmp     cs:pSid, rbp
0x180007296  jz      loc_180007421
0x18000729c  mov     [rsp+48h+var_18], rbx
0x1800072a1  lea     rdx, [rsp+48h+ppInterface]; ppInterface
0x1800072a6  mov     [rsp+48h+var_20], rsi
0x1800072ab  lea     rcx, IID_IServerSecurity; riid
0x1800072b2  mov     [rsp+48h+var_28], r14
0x1800072b7  mov     esi, ebp
0x1800072b9  call    cs:__imp_CoGetCallContext
0x1800072c0  nop     dword ptr [rax+rax+00h]
0x1800072c5  lea     r14, WPP_GLOBAL_Control
0x1800072cc  mov     ebx, eax
0x1800072ce  test    eax, eax
0x1800072d0  jns     loc_180007368
0x1800072d6  cmp     ebx, 80010117h
0x1800072dc  jnz     loc_18000746E
0x1800072e2  mov     dword ptr [rdi], 1
0x1800072e8  mov     ebx, ebp
0x1800072ea  mov     rax, cs:WPP_GLOBAL_Control
0x1800072f1  mov     rcx, [rsp+48h+hObject]; hObject
0x1800072f6  test    rcx, rcx
0x1800072f9  jz      short loc_18000730E
0x1800072fb  call    cs:__imp_CloseHandle
0x180007302  nop     dword ptr [rax+rax+00h]
0x180007307  mov     rax, cs:WPP_GLOBAL_Control
0x18000730e  test    esi, esi
0x180007310  mov     rsi, [rsp+48h+var_20]
0x180007315  jz      short loc_18000732F
0x180007317  mov     rcx, [rsp+48h+ppInterface]
0x18000731c  mov     rax, [rcx]
0x18000731f  mov     rax, [rax+28h]
0x180007323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007328  mov     rax, cs:WPP_GLOBAL_Control
0x18000732f  mov     rcx, [rsp+48h+ppInterface]
0x180007334  test    rcx, rcx
0x180007337  jz      short loc_18000734C
0x180007339  mov     rax, [rcx]
0x18000733c  mov     rax, [rax+10h]
0x180007340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007345  mov     rax, cs:WPP_GLOBAL_Control
0x18000734c  test    ebx, ebx
0x18000734e  jnz     loc_1800074A5
0x180007354  mov     r14, [rsp+48h+var_28]
0x180007359  mov     eax, ebx
0x18000735b  mov     rbx, [rsp+48h+var_18]
0x180007360  add     rsp, 38h
0x180007364  pop     rdi
0x180007365  pop     rbp
0x180007366  retn
0x180007368  mov     rcx, [rsp+48h+ppInterface]
0x18000736d  mov     rax, [rcx]
0x180007370  mov     rax, [rax+30h]
0x180007374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007379  test    eax, eax
0x18000737b  jnz     short loc_18000739D
0x18000737d  mov     rcx, [rsp+48h+ppInterface]
0x180007382  mov     rax, [rcx]
0x180007385  mov     rax, [rax+20h]
0x180007389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000738e  mov     ebx, eax
0x180007390  test    eax, eax
0x180007392  js      loc_1800072D6
0x180007398  mov     esi, 1
0x18000739d  call    cs:__imp_GetCurrentThread
0x1800073a4  nop     dword ptr [rax+rax+00h]
0x1800073a9  lea     r9, [rsp+48h+hObject]; TokenHandle
0x1800073ae  mov     edx, 8; DesiredAccess
0x1800073b3  mov     rcx, rax; ThreadHandle
0x1800073b6  mov     r8d, 1; OpenAsSelf
0x1800073bc  call    cs:__imp_OpenThreadToken
0x1800073c3  nop     dword ptr [rax+rax+00h]
0x1800073c8  test    eax, eax
0x1800073ca  jz      short loc_18000742B
0x1800073cc  mov     rdx, cs:pSid; SidToCheck
0x1800073d3  lea     r8, [rsp+48h+IsMember]; IsMember
0x1800073d8  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x1800073dd  mov     [rsp+48h+IsMember], ebp
0x1800073e1  call    cs:__imp_CheckTokenMembership
0x1800073e8  nop     dword ptr [rax+rax+00h]
0x1800073ed  test    eax, eax
0x1800073ef  jnz     short loc_18000745B
0x1800073f1  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800073f6  mov     ebx, eax
0x1800073f8  test    eax, eax
0x1800073fa  jz      loc_1800072EA
0x180007400  mov     rax, cs:WPP_GLOBAL_Control
0x180007407  cmp     rax, r14
0x18000740a  jz      loc_1800072F1
0x180007410  test    byte ptr [rax+1Ch], 1
0x180007414  jz      loc_1800072F1
0x18000741a  mov     edx, 12h
0x18000741f  jmp     short loc_18000748D
0x180007421  mov     eax, 80070057h
0x180007426  jmp     loc_180007360
0x18000742b  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180007430  mov     ebx, eax
0x180007432  test    eax, eax
0x180007434  jz      loc_1800072EA
0x18000743a  mov     rax, cs:WPP_GLOBAL_Control
0x180007441  cmp     rax, r14
0x180007444  jz      loc_1800072F1
0x18000744a  test    byte ptr [rax+1Ch], 1
0x18000744e  jz      loc_1800072F1
0x180007454  mov     edx, 13h
0x180007459  jmp     short loc_18000748D
0x18000745b  mov     eax, ebp
0x18000745d  cmp     [rsp+48h+IsMember], eax
0x180007461  setnz   al
0x180007464  add     eax, 3
0x180007467  mov     [rdi], eax
0x180007469  jmp     loc_1800072EA
0x18000746e  mov     rax, cs:WPP_GLOBAL_Control
0x180007475  cmp     rax, r14
0x180007478  jz      loc_1800072F1
0x18000747e  test    byte ptr [rax+1Ch], 1
0x180007482  jz      loc_1800072F1
0x180007488  mov     edx, 14h
0x18000748d  mov     rcx, [rax+10h]
0x180007491  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180007498  mov     r9d, ebx
0x18000749b  call    WPP_SF_d
0x1800074a0  jmp     loc_1800072EA
0x1800074a5  cmp     rax, r14
0x1800074a8  jz      loc_180007354
0x1800074ae  test    byte ptr [rax+1Ch], 1
0x1800074b2  jz      loc_180007354
0x1800074b8  mov     rcx, [rax+10h]
0x1800074bc  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x1800074c3  mov     edx, 15h
0x1800074c8  mov     r9d, ebx
0x1800074cb  call    WPP_SF_d
0x1800074d0  jmp     loc_180007354
```
